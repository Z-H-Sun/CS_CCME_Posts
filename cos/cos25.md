# ChemDraw Applications 25 for Windows / Mac 一键破解
**<p align="center">Z.-H. Sun 25年7月20日<br>更新于 25年7月20日</p>**

## 更早的版本
* [ChemOffice for Win / ChemDraw for Mac 20\~23](/cos/cos20.md)
* [ChemOffice for Win 19 / 18 / 17](/cos/cow2.md)
* [ChemDraw for Mac 19 / 18 / 17](/cos/cdm2.md)

## 简介

和过去的版本相比，没有什么功能上的更新。ChemDraw 更改了欢迎横幅和关于对话框的背景图片，可能更加现代化和美观？Chem3D 一众其他软件则没有任何更新，更名为 ChemDraw Applications，完全沦为 ChemDraw 的下级产品，看样子以后也不太会有更新的动力了。

目前 Revvity 公司的中心放在了在线应用 Signals Notebook 的开发上，更新速度还算勤快，但没有机构订阅的话反正是完全无法破解和用不上的了（摊手）。

Windows 版全面支持非管理员账户、仅为当前用户安装（不过大部分 PC 用户电脑上基本就一个账户且拥有管理员权限，所以意义不是很大……）。

Mac 版的 ChemDraw 增加了对新版 Macbook（也就是搭载了 Apple Silicon M1-M4 芯片的 Arm64 系统）的支持。这个还是有很大意义的：如果按照宣传的那样， Rosetta 在 MacOS 27 及以后不再支持，那么旧版本的 ChemDraw（也包括其他诸如 MestReNova 之类还在 x86_64 上跑的软件）都将无法运行了。

破解效果图（上：Win；下：Mac）：

<p align="center">
<img width="60%" height="60%" src="/cos/250.png">
<img width="60%" height="60%" src="/cos/255.png">
</p>

## 本方法优点
* 本法为通用破解补丁，预计之后再出新版也能轻松解决（*存疑，待观察*），无需满网找资源
* 便捷，一键解决，无需一个个手动替换
* 破解更完全，具备网传破解版没有的功能（如Office内嵌对象编辑，Chem3D hotlink等，见更早版本的推送）

## 使用方法
### Windows
* 只需直接下载运行单文件版安装破解程序`cos25.0_Crack.exe`，即可正常使用。请按程序提示操作。

  * [Google Drive](https://drive.google.com/open?id=1FT3l0msiLPsarmT78JQ8_sgbdJLMY4_X)
  * [百度网盘](https://pan.baidu.com/s/1smDXW8GNTPErq_yjilDhLg?pwd=csme)
  * 所有密码为 `csme`

> [!note]
> 因为某些不可抗力（详见 [Issue #26](https://github.com/Z-H-Sun/CS_CCME_Posts/issues/26#issuecomment-1830689605)），在 Google Drive 上，自 20.0 版起的安装包只能以 RAR 压缩包形式发布。解压密码为 `csme`，解压出相应的单个 EXE 安装文件后运行即可。虽然二次压缩看上去很蠢，但也是不得已而为之。或者可以前往百度网盘以直接下载单个 EXE 安装文件。

* 第一步：按提示点 OK：

<p align="center"><img width="60%" height="60%" src="/cos/251.png"></p>

* 第二步：出现命令行界面（黑窗口），按提示操作（如果不懂，一般只要按 <kbd>Y</kbd> 键或等一会即可（等待 10 秒后自动以默认模式进行））：

  * 将会启动两次安装程序。第一次装的是 ChemDraw，请按提示进行安装。
  * 第二次装的是剩余的 Chem3D / ChemFinder / ChemScript 等 ChemDraw Applications；如果不需要可以跳过（安装界面点 Cancel 即可）

<p align="center"><img width="60%" height="60%" src="/cos/252.png"></p>

* 第三步：回到命令行界面（黑窗口），启动破解程序。破解过程中，如下左图所示，按窗口提示操作（一般而言，第一个问题按 <kbd>Y</kbd> 键，接下来按 <kbd>P</kbd> 键）；<br>
  或者直接等一会即可（等待 10 秒后自动以默认模式进行）。<br>
  最后可以选填注册信息，不影响破解，只是可以在软件的“关于”对话框中显示这些用户自定义的信息（见下右图）。

|![](/cos/253.png)|![](/cos/230.png)|
|---|---|

* 然后就完成了！可以选择是否删除安装包产生的临时文件夹。

* **若已经安装了未破解版、更高或更低版本、或网传不完全破解版**，则可单独下载使用 [通用破解补丁](https://github.com/Z-H-Sun/MRN-ADF_Patch/releases/download/v2.20/COS_Win_Patch.exe)

  * 如果已经下载运行了上面的单文件版安装破解程序，因其本身就会自动运行该破解补丁程序，**故无需再另行下载此补丁**

#### 疑难解答

#### 无法选择性安装

ChemDraw Applications 25 会一股脑儿安装 Chem3D / ChemFinder / ChemDraw for Excel / ChemScript，无法只安装其中一部分。懒人安装版使用了官方安装程序，因此无法解决这个问题。但其实，只要不嫌（稍微）麻烦的话，可以不要用官方安装程序，直接双击打开安装程序目录中的 `Revvity\ChemDrawApplications\Revvity_ChemDraw_Applications_25.0.2_x64.msi` 手动配置即可。

<details>

其实这个 ChemDraw Applications 的 MSI 文件不只会装 Chem3D / ChemFinder / ...，同时也会安装 ChemDraw，因此事实上完全没必要像官方安装程序一样装两次：第一次装了 ChemDraw；第二次先把 ChemDraw 卸了再装，还说什么“必须已经先装了 ChemDraw 才可以继续运行这个安装程序”什么的，简直脑残……

</details>

---

#### Windows Defender / 其他杀毒软件误报

没办法，7Z 的自解压安装程序就是有这个原罪，没有大公司的数字签名很容易被误报为恶意程序（因为实际行为就很符合这个的标准）。

* 请直接放行即可。
* 如果仍然心存怀疑，可以移步别处下载官方版，然后单独下载使用 [破解补丁](https://github.com/Z-H-Sun/MRN-ADF_Patch/releases/download/v2.20/COS_Win_Patch.exe)（见上方说明）。
* 如果对破解补丁的安全性也有怀疑，可以自己安装任意版本的 [Ruby 运行环境](https://rubyinstaller.org/)，自行运行破解补丁脚本，其代码开源于此处：[Patch.rb](https://github.com/Z-H-Sun/MRN-ADF_Patch/blob/tags/hidden/COS_for_Win/Patch.rb)

---

#### 破解过程中出现红色（Failed）的解决方法
破解过程中如果出现红色失败信息，且提示为`Error occurred: #<Errno::EACCES: Permission denied - [文件名]>`，说明该文件正在被占用，无法写入。请关闭所有 ChemOffice 相关程序后重试。

<details>

但有时，"ChemDrawCtl22.dll" 等文件仍然提示正在占用。这可能是由于 Windows 资源管理器的缩略图缓存 (Thumbnail Cache) 服务正在工作中。最简单的方法就是重启电脑。也可以在任务管理器中结束命令行为`dllhost.exe /ProcessiD:{ab8902b4-09ca-4bb6-b78d-a8f59079a8d5}`的进程，如下图所示。

![](https://user-images.githubusercontent.com/48094808/232275061-82b274aa-6118-4368-b706-139d43ebaddc.png)

等价地，可以在`powershell`中执行以下命令：
```powershell
$prc = get-wmiobject win32_process -filter "commandline like '%dllhost%ab8902b4%'"
$prc | select-object processid,commandline
$prc | remove-wmiobject
```
其中第一行查找相关进程，第二行会显示相应的进程信息，第三行结束该进程。在该过程中你可能需要管理员权限。
</details>

---

#### “多用户使用”警告弹窗

之前版本中，若多个 Windows ChemDraw 用户在同一局域网内，可能出现弹窗提示。新版破解补丁已修复此问题。

---

### Mac
* 先下载官方程序包`ChemDraw25.dmg`，然后双击打开，正常安装。

  * [Google Drive](https://drive.google.com/open?id=1GRwysPQhOYnrriZTKSRc05Mf_Q7xd5DC)
  * [百度网盘](https://pan.baidu.com/s/1PDgXv4qrZHybyqf_niM2eA?pwd=csme)
* 先正常运行一遍 ChemDraw，系统验证过后再进行后续破解步骤 **（非常重要！）**
* 下载[补丁程序](https://github.com/Z-H-Sun/MRN-ADF_Patch/releases/download/v2.20/CDM_Crack)至任意位置
  * 上面的网盘文件夹里也有这个文件 `CDM_Crack`，择一方式下载即可
* 确保 “**终端 (Terminal)**” 程序具有 “**完全磁盘访问 (Full Disk Access)**” 权限 **（非常重要！）**
  * 进入 设置 (System Preferences) -> 隐私与安全性 (Security & Privacy) -> 完全磁盘访问权限 (Full Disk Access)，确认 终端 (Terminal) 在列表中，否则请单击 + 图标并添加、启用 实用工具 (Utilities) -> 终端 (Terminal)
* 通过 LauchPad 打开一个 “**终端 (Terminal)**” 窗口，输入 `ruby `，注意在字母y后**还有一个空格（非常重要！）**，然后将访达 (Finder) 中的补丁程序文件拖拽至终端窗口中（将会补全其路径），最后回车运行即可
  * 或者也可直接输入 `ruby "<path/to>/CDM_Crack"`
  * 如果出现错误，请确保“终端”拥有“完全磁盘访问权限”（见上条）；或者，可能是因为需要管理员权限，此时请运行 `sudo ruby "<path/to>/CDM_Crack"`
* 程序会自动检测 Mac 上安装的所有17及以上版本的 ChemDraw（如下图所示）：

  * 对于未经破解的 ChemDraw 版本，程序将在用户按下<kbd>y</kbd>键后开始破解【Patch】
  * 对于已打过补丁的 ChemDraw 版本，程序将在用户按下<kbd>y</kbd>键后将软件回复至初始（未破解）状态【Restore】
  * 对于任一情况，若用户按下<kbd>n</kbd>键都将忽略这个版本
<p align="center"><img width="60%" height="60%" src="/cos/256.png"></p>

> [!note]
> 对于 25 版及以上的 ChemDraw，请特别注意破解程序最后显示的额外信息（见上图）。如果你使用的是搭载 Intel 芯片的老 Mac 电脑，那么恭喜你，你可以忽略这一段话并直接开始正常使用 ChemDraw 25。如果你不幸正在用 M1/M2/M3/M4 芯片的新 Mac，那么请做以下步骤：

* 仅针对使用 Apple Silicon 芯片的新 Mac 用户（详见 [Issue #36](https://github.com/Z-H-Sun/CS_CCME_Posts/issues/36)）：
    * 请安装 Rosetta，并在 ChemDraw 应用程序上点右键，选择“显示简介”，然后在“通用”部分勾选“使用Rosetta 打开 (Open using Rosetta)”选项。**这样就可以了。**
    * 如果你无法使用 Rosetta，那么必须在补丁程序最后按<kbd>y</kbd>键进行数字签名。
      * 这需要你拥有 `codesign`，如果没有的话请安装 Xcode Command Line Tools。

运行ChemDraw，点击Install按钮后，**即可正常激活**。在ChemDraw -> About窗口中，Licensed to后为空**是正常现象**。

> [!note]
> 23 版及以上 ChemDraw 会弹窗询问选择何种注册模式，请选择第二种——Activation Code（见下图）。

<p align="center"><img width="60%" height="60%" src="/cos/232.png"></p>

以上安装破解过程在Mac OS 11-15 上测试通过。
