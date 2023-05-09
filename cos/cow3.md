# ChemOffice 2018/2019 激活原理

## 网传破解版原理
ChemOffice应用程序在检测激活的部分是用.NET写的，因此很容易反编译和修改。网传破解版只改动了一个字节的二进制数据：简而言之，就是将程序集中`IsActivated`函数最后的`Return result`改为了`Return True`，就直接让程序误以为已激活，从而达成破解目的。

虽然非常高效，但这么破解有几个问题：
* 网传破解版漏改了几个关键应用程序/动态链接库/控件；
* 更重要的是，有些功能会检查“ActivationLevel”（如分为Viewer、Prime、Ultra、Professional等），并不依赖`IsActivated`函数，显然作此只改动是不能解决这个问题的。

由此导致的问题详见「[为什么使用本方法](/cos/cow2.md#为什么使用本方法)」及「[破解补丁vs本方法](/cos/cow2.md#破解补丁vs本方法)」。

## 总述
因此，推荐使用[本方法](/cos/cow2.md)。本方法中，`Patch.exe`由**开源Ruby代码**[Patch.rb](https://github.com/Z-H-Sun/MRN-ADF_Patch/blob/hidden/COS_for_Win/Patch.rb)经[Exerb](http://sourceforge.jp/projects/exerb/)编译而成，依赖于可执行文件`./Activation/activate18或19.exe`（基于官方安装包中的`Activate.exe`文件修改，见[此处](https://github.com/Z-H-Sun/MRN-ADF_Patch/tree/hidden/COS_for_Win/Activation))。

## 18版一键破解原理
参考「[本方法原理](/cos/cow.md#本方法原理)」。简而言之，迫使程序采用旧注册机制；因此，首先`Patch.exe`将相关的`FlxC*.dll`全部重命名，使程序找不到新注册机制相关的动态链接库，从而回滚至旧注册机制。随后，`Patch.exe`会调用官方安装包中的`Activate.exe`（它相当于是将每个ChemOffice组件中和激活相关的部分单独分离出来）。但**为了方便用户“一键激活”**，利用[`dnSpy`](https://github.com/0xd4d/dnSpy)工具更改了`ActivationDlg`中部分`TextBox`和`Label`控件的Caption，更改了默认的`m_actcode`（激活码（设为6\*E-7\*\*W3-5\*-Q\*5P-J3\*\*X-O\*\*X-35\*\*N））和`m_uinfo`（包含用户名（设为电脑当前用户名）、序列号（设为87\*-38\*\*99-9\*\*4）等信息）。部分修改代码见下

<p align="center"><img width="100%" height="100%" src="/cos/principle1.png"></p>

在多数情况下，激活后会在注册表`HKCU/Software/PerkinElmerInformatics/ChemBioOffice/[版本号]/Ultra`下写入相关注册信息，**这样的话不会有任何问题**。但在少数情况下（测试时未能发现触发条件），不会在`HKCU`(Current User)主根键下写入信息，而是会写入`HKLM`(Local Machine)主根键；而在`HKLM/Software`下，64位平台会区分32位注册表或64位注册表。因为`Activate.exe`是32位程序，上述键会被重定向至`HKLM/Software/Wow6432Node/PerkinElmerInformatics/ChemBioOffice/[版本号]/Ultra`，从而只会影响32位ChemOffice组件**而不会被64位的组件所识别**。因此，在最后`Patch.exe`还会将上述键复制一份到64位注册表的`HKLM/Software/PerkinElmerInformatics/ChemBioOffice/[版本号]/Ultra`，以保证64位ChemOffice组件也能正常激活。

## 19版一键破解原理
本节是在上一节的基础上进行说明的，关于`FlxC*.dll`、`Activate.exe`、注册表的修改的讨论见上节。自19.0版本起，旧的注册机制被埋得更深了，仅仅靠上述方法已失效。可见官方有意淘汰此机制，但仍然未完全删干净代码（不知道为什么……）

首先，`buttonActivate`（“Activate”按钮）在一开始被设为`.Enabled = False`，但在之前版本中，当序列号、激活码通过验证时，会重新将其设为“可用”；而19.0版本删除了修改`Enabled`属性的代码，其将一直保持`False`状态，即**一直为“灰色”状态**。其次，直接删掉了`buttonActivate`的`Click`事件。所以该按钮其实只剩个空壳，实际上**不响应任何序列号、激活码的输入状态了**。

参考之前版本，将实现激活的代码“移花接木”到了`buttonActivateLater`上，这样就不会有`Enabled`的问题。还好代码不是很长，只是返回一个`m_response`和`m_message`即可（下图），验证工作会交给其他模块完成。

<p align="center"><img width="100%" height="100%" src="/cos/principle2.png"></p>

改完之后尝试一下，发现不行，弹出了这么个提示窗口

<p align="center"><img width="50%" height="50%" src="/cos/principle3.png"></p>

在`dnSpy`中搜索“While you entered a valid”，找到三个字串，其中两个经验证为“it is not valid for ChemDraw 19.0”，而我们感兴趣的为“it is for an older version of this software”。使用“分析”工具，找到读取于`DisplayActivationDialogOriginal`函数，附近代码如下图所示。找到相关函数为`IsValidatedBy`（也有三个，必须找到对应的那一个），把返回值全部改为`True`即可（如下图）。

<p align="center"><img width="100%" height="100%" src="/cos/principle4.png"></p>

然后运行一遍`Activate.exe`，已经能正常工作了。但此时运行`ChemDraw`等程序，依然弹出“需要注册”的窗口。这是因为这些组件内部，`IsValidatedBy`函数**依然判定为“假”**。所以在`Patch.exe`中，搜索了所有的应用程序/动态链接库/控件，根据二进制数据的“模式”，**将所有`IsValidatedBy`函数进行上述更改**。详细代码见[Patch.rb](https://github.com/Z-H-Sun/MRN-ADF_Patch/blob/hidden/COS_for_Win/Patch.rb)。

之后**一切**就能正常工作了，和正常激活版本无异。

## 关于Activate19.exe报毒的担心
不知道做了什么修改触发了某*数字*杀毒软件的报警。希望上述原理描述能减轻用户的疑惑，请放心放行。

如果**实在不想运行**`Acitvate19.exe`，可以在运行`Patch.exe`后，**手动填写注册表项**`HKCU/Software/PerkinElmerInformatics/ChemBioOffice/19.0/Ultra`，添加如下`REG_SZ`字符串键（改掉星号和谐符，你懂的）：
```
Activation Code = 6*E-7**W3-5*-Q*5P-J3**X-O**X-35**N
Email = 随便
Organization = 随便
Serial Number = 87*-38**99-9**4
Success = True
User Name = 随便
```
或者，找到之前激活的18版本的ChemOffice相关的注册表项，将项名`18.0`改为`19.0`也行。**上述方法未经大量测试，不保证一定能成功**。