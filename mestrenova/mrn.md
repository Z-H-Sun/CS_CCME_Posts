# MestReNova 12.0.0~14.2.0 [Win/Mac/Ubuntu] [x86/x64] 通用补丁
**<p align="center">Z.-H. Sun 2020年3月15日 更新于 2020年11月22日</p>**

目前MestReNova的Windows平台下已更新到14.2.0 ~~12.0.4~~，但网上只有14.0 ~~12.0.2~~破解，且只支持32位；Mac平台只有“史蒂芬周博客”的12.0.0破解，而且“Mnova Verify”插件的许可文件写得有问题；没有Linux平台的破解。

而本补丁是Windows、Mac、Ubuntu（新增） 32/64位、12.0.0~14.2.0 ~~12.0.4~~版本通用的，只需先下载安装官方程序，然后双击运行本补丁即可正常使用。补丁程序**源码**公开在该[仓库](https://github.com/Z-H-Sun/MRN-ADF_Patch)中。

## 仅对 Mac 用户的附加说明 (2020/11/22)

（原因详见[Issue #3](https://github.com/Z-H-Sun/CS_CCME_Posts/issues/3)）

* 对于 14.2.0 及以上版本，请使用[最新的补丁程序](https://github.com/Z-H-Sun/MRN-ADF_Patch/releases/download/v2.12/MRN_Crack_Mac)，其中解决了数字签名的问题从而**防止闪退**
* 如果你已经将系统更新至 MacOS 11，那么使用低版本的 MestReNova 会闪退，这是由于 NMR Predictor 插件对新系统不兼容的问题（系统库缺失），可采取以下两种办法 **之一**：

  * 更新至最新版本 14.2.0 并使用最新补丁程序 **（推荐）；或**
  * 暂时屏蔽 NMR Predictor，反正用处不是很大。最简单的方法是删除对应的许可文件（显示包内容 > Contents > MacOS > license > NMRPredict Desktop.lic），只要对应部分没有激活则相应的问题程序就不会运行

## 使用方法
* 下载、安装对应平台版本的[官方安装程序](http://mestrelab.com/download/mnova/)
* 下载破解补丁文件至任意位置：[Windows](https://github.com/Z-H-Sun/MRN-ADF_Patch/releases/download/v2.10/MestReNovaCrack.exe) / [Mac](https://github.com/Z-H-Sun/MRN-ADF_Patch/releases/download/v2.12/MRN_Crack_Mac) / [Ubuntu](https://github.com/Z-H-Sun/MRN-ADF_Patch/releases/download/v2.10/MRN_Crack_Ubuntu)

* Windows下：

  * 双击运行破解补丁。若MestReNova安装在系统盘，需**右键 -> 以管理员身份**运行
  * 即使装有超过一个版本的MestReNova，程序也能找出所有版本的安装路径（见下图）。直接回车将对所有版本进行破解，或输入需要破解的某一个版本的序号。本补丁可能不支持非12.0的更低级版本，请将它们排除在外。
<p align="center"><img src="/mestrenova/3.jpg" height="80%" width="80%"></p>

* Mac下：

  * 最好通过另一台Windows电脑下载程序安装包及补丁文件，U盘拷贝至此Mac电脑。安装结束后以“终端 (Terminal)”方式打开补丁文件，按y确认
  * 具体操作，或过程中产生任何问题，请参见[一般操作流程及疑难解答](/MAC.md)。
  * 以下情况有一定可能会发生：如果首次运行时，软件提示“Cache目录设置不正常，是否解决”，**请选择“是”并按照提示输入管理员账号密码即可**（否则会提示许可验证失败，代码0x8000000E）
<p align="center"><img src="/mestrenova/2.jpg" height="80%" width="80%"></p>

* Ubuntu下（新增）：

  * 请首先配置`ruby`环境。使用`sudo apt-get install ruby-full`安装最新版ruby，或者对于non-sudoer用户可选择自行编译
  * 终端中运行`ruby </path/to/>MRN_Crack_Ubuntu`，按y确认
* 本补丁运行时已经包含了写入许可文件的步骤，因此运行结束后即可正常打开和运行MestReNova 12.0~14.2。

## 运行效果图
*<p align="center"><img src="/mestrenova/1.jpg" height="30%" width="30%">  <img src="/mestrenova/0.jpg" height="39%" width="39%"><br>左：Windows；右：Mac</p>*
