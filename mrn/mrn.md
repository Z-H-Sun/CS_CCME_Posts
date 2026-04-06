# MestReNova 12\~17 [Win/Mac/Ubuntu] [x86/x64] 通用补丁 + 全网最全插件许可
**<p align="center">Z.-H. Sun 2020年3月15日</p>**
**<p align="center">更新于 2026年4月6日</p>**

目前MestReNova的Windows平台下已更新到17.0.0 ~~12.0.4~~，但网上只有14.0 ~~12.0.2~~破解，且只支持32位；Mac平台只有“史蒂芬周博客”的12.0.0破解，而且“Mnova Verify”插件的许可文件写得有问题；没有Linux平台的破解。现行破解版的插件许可不全面，有些插件无法运行。

而本补丁是Windows、Mac、Ubuntu 32/64位、12.0.0~17.0.0 ~~12.0.4~~版本通用的，且包含了所有插件的许可，只需先下载安装官方程序，然后双击运行本补丁即可正常使用。补丁程序**源码**公开在该[仓库](https://github.com/Z-H-Sun/MRN-ADF_Patch)中。

> [!note]
> 中国大陆地区访问 MestReNova 官网会强制自动跳转到代理商页面（详见 [Issue 29](https://github.com/Z-H-Sun/CS_CCME_Posts/issues/29)）。可以访问 <ins>[此页面](mnlink.md)</ins> 浏览最新版本软件的官方安装包链接。该页面每月刷新一次。

---

**26/4/6 更新**：解决[Issue #40](https://github.com/Z-H-Sun/CS_CCME_Posts/issues/40)，新增`GCNN Predictor`插件许可，新增了 17.0 Mac/Ubuntu 版的破解支持。

**25/7/20 更新**：增加了大量新插件的许可支持，如Chemometrics、Screen 2D、DFT Predictor、Mnova Hub、MANIQ、USP-ID Plug-in等。

**22/5/18 更新**：应[Issue #10](https://github.com/Z-H-Sun/CS_CCME_Posts/issues/10)的请求，新增了`ElViS`、`MestrelabPredictor`、`BioHOS`、`StereoFitter`等插件的许可，修正了`IUPAC Name`插件的许可。

## 仅对 Mac 用户的附加说明 (2020/11/22)

<details><summary>新版不再会有该问题。点此展开</summary>

（原因详见[Issue #3](https://github.com/Z-H-Sun/CS_CCME_Posts/issues/3)）

* 对于 14.2.0 及以上版本，请使用[最新的补丁程序](https://github.com/Z-H-Sun/MRN-ADF_Patch/releases/download/v2.20/MRN_Crack_Mac)，其中解决了数字签名的问题从而**防止闪退**
* 如果你已经将系统更新至 MacOS 11，那么使用低版本的 MestReNova 会闪退，这是由于 NMR Predictor 插件对新系统不兼容的问题（系统库缺失），可采取以下两种办法 **之一**：

  * 更新至最新版本 14.2.0 并使用最新补丁程序 **（推荐）；或**
  * 暂时屏蔽 NMR Predictor，反正用处不是很大。最简单的方法是删除对应的许可文件（显示包内容 > Contents > MacOS > license > NMRPredict Desktop.lic），只要对应部分没有激活则相应的问题程序就不会运行

</details>

## 使用方法
* 下载、安装对应平台版本的[官方安装程序](https://mestrelab.com/download)
* 下载破解补丁文件至任意位置：[Windows](https://github.com/Z-H-Sun/MRN-ADF_Patch/releases/download/v2.21/MestReNovaCrack.exe) / [Mac](https://github.com/Z-H-Sun/MRN-ADF_Patch/releases/download/v2.21/MRN_Crack_Mac) / [Ubuntu](https://github.com/Z-H-Sun/MRN-ADF_Patch/releases/download/v2.21/MRN_Crack_Ubuntu)

---

### Windows

  * 双击运行破解补丁。若MestReNova安装在系统盘，需**右键 -> 以管理员身份**运行
  * 即使装有超过一个版本的MestReNova，程序也能找出所有版本的安装路径（见下图）。直接回车将对所有版本进行破解，或输入需要破解的某一个版本的序号。本补丁可能不支持非12.0的更低级版本，请将它们排除在外。
<p align="center"><img src="/mrn/3.jpg" height="80%" width="80%"></p>

---

### Mac

  * 先正常运行一遍 MestReNova，系统验证过后再进行后续破解步骤 **（非常重要！）**
  * 确保 “**终端 (Terminal)**” 程序具有 “**完全磁盘访问 (Full Disk Access)**” 权限 **（非常重要！）**
    * 进入 设置 (System Preferences) -> 隐私与安全性 (Security & Privacy) -> 完全磁盘访问权限 (Full Disk Access)，确认 终端 (Terminal) 在列表中，否则请单击 + 图标并添加、启用 实用工具 (Utilities) -> 终端 (Terminal)
  * 通过 LauchPad 打开一个 “**终端 (Terminal)**” 窗口，输入 `ruby `，注意在字母y后**还有一个空格（非常重要！）**，然后将访达 (Finder) 中的补丁程序文件拖拽至终端窗口中（将会补全其路径），最后回车运行即可
    * 或者也可直接输入 `ruby "<path/to>/MRN_Crack_Mac"`
    * 如果出现错误，请确保“终端”拥有“完全磁盘访问权限”（见上条）；或者，可能是因为需要管理员权限，此时请运行 `sudo ruby "<path/to>/MRN_Crack_Mac"`
  * 以下情况有一定可能会发生：如果首次运行时，软件提示“Cache目录设置不正常，是否解决”，**请选择“是”并按照提示输入管理员账号密码即可**（否则会提示许可验证失败，代码0x8000000E）

> [!note]
> 对于 17.0 及以上的 Mac 版本，请特别注意破解程序最后显示的额外信息。如果你使用的是搭载 Intel 芯片的老 Mac 电脑，那么恭喜你，你可以忽略这一段话并直接开始正常使用。如果你不幸正在用 M1/M2/M3/M4/M5 芯片的新 Mac，那么请做以下步骤：

* 仅针对使用 Apple Silicon 芯片的新 Mac 用户（详见 [Issue #40](https://github.com/Z-H-Sun/CS_CCME_Posts/issues/40)）：
    * 请安装 Rosetta，并在应用程序上点右键，选择“显示简介”，然后在“通用”部分勾选“使用Rosetta 打开 (Open using Rosetta)”选项。**这样就可以了。**
    * 如果你无法使用 Rosetta，那么必须在补丁程序最后按<kbd>y</kbd>键进行数字签名。
      * 这需要你拥有 `codesign`，如果没有的话请安装 Xcode Command Line Tools。

<p align="center"><img src="/mrn/2.png" height="80%" width="80%"></p>

---

### Ubuntu

**注意：仅支持 x86_64 版本，暂不支持 ARM64 版。**

  * 请首先配置`ruby`环境。使用`sudo apt-get install ruby-full`安装最新版ruby，或者对于non-sudoer用户可选择自行编译
  * 终端中运行`sudo ruby </path/to/>MRN_Crack_Ubuntu`，按y确认

---

### 关于插件
* 本补丁运行时已经包含了写入许可文件的步骤，因此补丁运行结束后即可正常打开和运行MestReNova 12.0~17.0
* 如果要使用 MestReNova 中一开始默认未开启的插件，请前往 Advanced Plug-ins... 窗口中启用，然后重启软件。部分插件需要前往 [MestReNova 官网](https://mestrelab.com/main-product/mnova) 下载，然后按照指示进行安装。本补丁已包含了这些额外插件的许可。从下图中可见，所有插件都是免费或已解锁的状态。

<p align="center"><img src="/mrn/4.png" height="50%" width="50%"></p>

## 运行效果图
<p align="center"><img src="/mrn/0.png" height="80%" width="80%"></p>
