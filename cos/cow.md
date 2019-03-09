# ChemOffice 2018完美激活方法: Simple, Powerful, and Patcher-Free
**<p align="center">Z.-H. Sun 2月3日</p>**

在[Mac版ChemDraw 18下载安装资源](/cos/cdm.md)中我们提到，ChemOffice 18最受瞩目的新特性是**添加了Reaxys结构/反应式搜索的支持**（原先只支持SciFinder搜索），以及**添加了“插件”功能**（自带：ChemACX的CAS号/性质/价格查询功能）。在试用了Windows版一个月之后，我还注意到了这些细微但有趣的变化：

## 新版本特性
* 新添了底部的状态栏，显示各按钮、菜单的功能说明
* 修复了拖动子窗口时的Office样式卡顿残影特效（*不明白这个梗的试一下就知道了233*）
* 在微软官宣弃坑XP又四年后，ChemDraw总算开启了XP界面视觉样式（控件的外观会略有不同，不了解的可搜索一下“XP视觉样式”）
* 跟进了64位OS的支持（2017版出了64位资源管理器缩略图预览支持，今年新添了64位ChemScript和64位Excel插件支持。虽然安装包标明还有64位的Chem3D和ChemFinder，但实测是没有的）
* 依然没有支持Unicode。

先上破解完成后的运行效果图：
<p align="center"><img width="80%" height="80%" src="/cos/5.webp"></p>

## 官方包下载安装
在破解以前，首先要下载安装官方试用版。下载地址（同时提供17.0、18.0版）：[Baidu Pan](https://pan.baidu.com/s/1rlPilrRh4n4q6k1qG1rNsA)；[Google Drive](https://drive.google.com/open?id=1agD0ldESX_AKDAwgTELehil1RoNxfihH)。**根据对应文件夹说明，按需下载运行即可，不必全部下载。**

* 首先按次序运行.msi安装文件。例如，先安装`1. ChemOffice_Suite_2018.msi`，再安装`2. ChemOffice_64-bit_Support_18.0.msi`，ChemScript大家一般用不到就可以不装（*因为支持的Python版本在3.2以下，用的人太少了，唯一有用的是Excel插件中的CombiChem（反应式）功能；如果要装的话请务必选对版本，比如**装了32位的Excel就应该装32位ChemScript，反之亦然**，否则无法启用*）

* 其实`2. ChemOffice_64-bit_Support_18.0.msi`也可以不安装。因为安装之后，.cdx文件和Office中嵌入的ChemDraw对象就会默认以64位的ChemDraw打开，但目前ChemDraw的64位支持**做得并不是太好**，例如由于没有64位的Chem3D所以没有Chem3D hotlink的选项。不过这些差别都比较细枝末节，不太影响日常使用，**就像32位和64位的Office一样，各有优缺点**，大家权衡利弊自行决定即可。

* 如果运行ChemDraw程序后，提示缺失`vcruntime140.dll`（18版）或`vcruntime100.dll`（17版），说明没装VC运行库，请到网盘的`依赖项/VCRedist`这个目录下找安装程序。如果提示缺少.NET 4.0框架（一般Win10不会）也可在该目录中找到对应安装程序。

## 激活方法
这个方法同样适用于2017版。

* 首先下载安装官方试用版（见上）

* 进入32位验证程序所在路径C:\Program Files (x86)\PerkinElmerInformatics\ChemOffice2018\Common\DLLs，找到`FlxComm.dll`和`FlxCore.dll`这两个文件（若把程序装在了其他位置，则到相应路径中找），把它们**删掉或随便改成其他名字**，如下图所示
<p align="center"><img width="80%" height="80%" src="/cos/10.jpg"></p>

* 如果安装了`64-bit support`，那么还要对64位验证程序所在目录进行类似操作（文件名比前面多一个“64”，一般位于C:\Program Files\PerkinElmerInformatics\ChemOffice2018\Common\DLLs）。

* 然后运行其中任何一个ChemOffice程序（如ChemDraw），打开后就会跳出旧版的**离线激活窗口**（下左图）而不再是**联网激活**了（下右图），可以用2016版的序列号激活码激活。只要激活一次即可。
<p align="center"><img width="80%" height="80%" src="/cos/9.jpg"></p>

* 如果之前运行过补丁，未跳出激活窗口，则可在ChemDraw的"Help"菜单项下单击"Activate ChemDraw..."即可跳出激活窗口。**同样地，只需激活一次**。

* 参考注册信息：

> **Name:** 必填，但是可以随便填，Email可以不填；**Serial Number:** 875-385499-9864；**Activation Code:** 6UE-7IMW3-5W-QZ5P-J3PCX-OHDX-35GRN。

经过安装-删（重命名）文件-激活三步简单操作，即可解锁ChemOffice 2018或2017全部功能，与正版没有任何区别。*我在知乎上还看到有一种改注册表的方法：[17版](https://zhuanlan.zhihu.com/p/37268905), [18版](https://zhuanlan.zhihu.com/p/48973696)也可以实现旧版激活，原理和上面的方法完全相同。不过有些读者可能对注册表操作不太了解，我也觉得还是改文件来得更加方便一些。*

## 破解补丁vs本方法
在[这篇文章](/cos/cow_legacy.md)中，分享了Windows平台下的ChemOffice 17/18破解补丁。文中提到，使用补丁破解完后仍然存在一些小的缺陷，不过对日常使用影响较小，再去通过分析代码/修改可执行文件来激活这些功能的话投入/产出比就太高了。在最近的使用过程中，发现了这种简单快捷的激活方法（操作方法见上），**无需运行任何破解补丁**（即不对官方可执行文件进行修改），但能**完美地弥补破解补丁的所有缺陷，激活后与正版程序运行效果完全一样**。

之前，网传的ChemOffice 2017版的破解补丁也存在同样的问题。

* ChemDraw for Excel的部分功能无法实现，提示“需要更高的激活等级”。原因是**ChemDraw ActiveX控件未能破解**。正版激活的ChemDraw for Excel运行效果图如下所示；补丁破解无法正常显示化合物结构图和熔点/分子量等属性。
<p align="center"><img width="80%" height="80%" src="/cos/6.jpg"></p>

* ChemDraw (32-bit)中无法取得与Chem3D hotlink的关联，画好一个结构后Chem3D hotlink window中仍然不显示任何内容（64-bit程序本身无此功能，不在讨论范围内）。原因是**Chem3D ActiveX控件未能破解**。正版激活的Chem3D hotlink功能效果图如下所示。
<p align="center"><img width="60%" height="60%" src="/cos/7.webp"></p>

* *好吧这个其实并不能算是一个（可能只是心理上的差别）*。在About窗口中，正版激活的程序会显示License to whom，序列号是什么；补丁破解版（相当于试用版）这里是空的。
<p align="center"><img width="60%" height="60%" src="/cos/8.jpg"></p>

## 本方法原理
为什么2017版之后网上就找不到序列号和激活码了？简而言之，是因为PerkinElmer**更改了注册验证机制**，以前那一套基于序列号/激活码离线激活的那一套已经不管用了，目前采用的是基于联网数据库的在线激活方式（就像你不可能再找得到Office 365密钥而只能用微软账号去激活一样）。这两种不同方式的激活窗口长得完全不一样（见上）。

然而事实上2017版之后的程序并不是完全移除了离线激活的代码，而仅是将离线激活的入口隐藏了起来（*emmmmm*.....）。正常打开一个程序会跳出联网激活的窗口，但如果联网激活**完全**不可用时，便会跳出离线激活窗口，这样就能**用2016版的序列号/注册码激活了**（不过相信我，简单地断开网络连接是没有用的）。上面就简单介绍了启用这个旧版激活窗口的方法，操作上还是很简单易行的。
