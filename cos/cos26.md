# ChemDraw Applications 26 for Windows / Mac 一键破解
**<p align="center">Z.-H. Sun 26年8月27日</p>**

## 更早的版本
* [ChemDraw Applications for Windows / Mac 25](/cos/cos25.md)
* [ChemOffice for Win / ChemDraw for Mac 20\~23](/cos/cos20.md)
* [ChemOffice for Win 19 / 18 / 17](/cos/cow2.md)
* [ChemDraw for Mac 19 / 18 / 17](/cos/cdm2.md)

## 下载安装

从 26 版本起，为缓解个人网盘压力，节省发布时间，将不再提供一键安装破解的懒人包。因此，请先在下方链接下载并正常执行官方安装程序，这样还有一个好处在于安全性也会更高（有可校验的官方数字签名背书）。Revvity 并未对官方安装程序的下载地址进行限制，普通人无需账号登录也可正常访问。

### Windows 版下载
* [ChemDraw 26.0.0.6141](https://static.chemistry.revvitycloud.com/chemdraw/updates/ChemDraw_26.0.0.exe)

  *SHA256: DB5F0C04E817C6A28B59F6EEC91D5A1B1B3700ADE851B4A42FCD435DF5746FAC*

如果除了 ChemDraw 以外，还想安装 Chem3D / ChemFinder / ChemDraw for Excel / ChemScript 等其他组件，可选择继续安装：

* [ChemDraw Applications 26.0.0.6141](https://static.chemistry.revvitycloud.com/chemdraw/updates/ChemDraw_Applications_26.0.0.exe)

  *SHA256: 57E44BD9A314E82E9579E94F399B211F475C00DE7C45CB567411939F7A2C0E6F*

注意：ChemDraw Applications 26 会一股脑儿安装 Chem3D / ChemFinder / ChemDraw for Excel / ChemScript，无法只安装其中一部分。

<details><summary>如果非要只装一部分，且不嫌（稍微）麻烦一点的话……</summary>

* 可以在官方安装程序解压完成后，进入解压目录中（一般是 `%appdata%\RevvitySignalsSoftware\Installers\ChemDraw_Applications_26.0.0`），***以管理员身份打开***（最简单的方法是在有管理员权限的命令行中启动）`Revvity\ChemDrawApplications\Revvity_ChemDraw_Applications_26.0.0_x64.msi` 手动配置即可。
* 其实这个 ChemDraw Applications 的 MSI 文件不只会装 Chem3D / ChemFinder / ...，同时也会安装 ChemDraw，因此事实上完全没必要像官方安装程序一样装两次：第一次装了 ChemDraw；第二次先把 ChemDraw 卸了再装，还说什么“必须已经先装了 ChemDraw 才可以继续运行这个安装程序”什么的，简直脑残……

</details>

随后请跳转至 [Windows 版破解](#windows-版破解) 一节继续。

---

### MacOS 版下载
* [ChemDraw for Mac 26.0.0.6599](https://static.chemistry.revvitycloud.com/chemdraw/updates/cd26.0.0.dmg) (122.16 MB)

  *SHA256: E6E8D605CAE73A3C7C8D255F19A58CB7269204CA03DCB494BC9CA0774551CB20*

随后请跳转至 [MacOS 版破解](#macos-版破解) 一节继续。

---

### 其他版本 / 获取最新版本

<details><summary>其他官方链接……</summary>

* ChemDraw Applications
  * [25.0.0 版](https://static.chemistry.revvitycloud.com/chemdraw/updates/ChemDraw_Applications_25.0.0.exe)、[25.0.2 版](https://static.chemistry.revvitycloud.com/chemdraw/updates/ChemDraw_Applications_25.0.2.exe)
  * 最新版本及其下载地址可以在此 [XML 文件](https://static.chemistry.revvitycloud.com/chemdraw/updates/ChemDrawApplicationsUpdate.xml) 的内容中读取
* ChemDraw (Windows)
  * [25.0.0 版](https://static.chemistry.revvitycloud.com/chemdraw/updates/ChemDraw_25.0.0.exe)、[25.0.2 版](https://static.chemistry.revvitycloud.com/chemdraw/updates/ChemDraw_25.0.2.exe)
  * 最新版本及其下载地址可以在此 [XML 文件](https://static.chemistry.revvitycloud.com/chemdraw/updates/ChemDrawWindowsUpdate.xml) 的内容中读取
* ChemDraw (Mac)
  * [25.0.0 版](https://static.chemistry.revvitycloud.com/chemdraw/updates/cd25.0.0.dmg)、[25.0.2 版](https://static.chemistry.revvitycloud.com/chemdraw/updates/cd25.0.2.dmg)
  * 最新版本及其下载地址可以在此 [XML 文件](https://static.chemistry.revvitycloud.com/chemdraw/updates/ChemDrawMacUpdate.xml) 的内容中读取

</details>

<details><summary>如果想要自动化爬取上述信息……</summary>

* 可以爬取 XML 文件查找所需信息。下面的 Python 样例读取了版本号、发布时间、下载地址、校验号等信息：
  ``` Python
  import requests
  import xml.etree.ElementTree as ET
  BASE_URL = "https://static.chemistry.revvitycloud.com/chemdraw/updates/"
  
  CDA_XML_FN = "ChemDrawApplicationsUpdate.xml"
  CD_XML_FN = "ChemDrawWindowsUpdate.xml"
  CDM_XML_FN = "ChemDrawMacUpdate.xml"
  
  def cd_xml_info(filename):
      print(filename)
      res = requests.get(BASE_URL+filename, allow_redirects=True, timeout=10)
      if res.status_code != 200:
          print("Retrieval failed with status code " + str(res.status_code))
          print()
          return
      root = ET.fromstring(res.content)
      for element in root.iter():
          if element.tag.rsplit("}", 1)[-1].lower() != "item": continue # strip an XML namespace, if present; similar below. Ex:'{http://example.com}item' -> 'item'
          for child in element.iter():
              key = child.tag.rsplit("}", 1)[-1].lower()
              if key == "title": print(child.text) # # strip an XML namespace, if present. Ex:'{http://example.com}item' -> 'item'
              elif key == "pubdate": print("Published on", child.text)
              elif key == "sha256": print("SHA256\t", child.text)
              else:
                  for k, v in child.attrib.items():
                      k = k.rsplit("}", 1)[-1].lower()
                      if k == "url": print("URL\t", v)
                      elif k == "version": print("Ver\t", v) # sparkle:version => '{http://www.andymatuschak.org/xml-namespaces/sparkle}version
                      elif k == "length" and v:
                          print("Size\t", v, end = " ")
                          try: print("(%.2f MB)" % (int(v)/1048576))
                          except ValueError: pass
      print()
  
  for n in (CDA_XML_FN, CD_XML_FN, CDM_XML_FN):
      cd_xml_info(n)
  ```
  
* 可以扫描官网内形如 `a.b.c` 的版本。下面的 Python 样例扫描了主版本号从 25 至 27，次版本号和修订号从 0 至 2 的结果：
  ``` Python
  import requests
  BASE_URL = "https://static.chemistry.revvitycloud.com/chemdraw/updates/"
  
  CDA_EXE_FN = "ChemDraw_Applications_2{a}.{b}.{c}.exe"
  CD_EXE_FN = "ChemDraw_2{a}.{b}.{c}.exe"
  CDM_DMG_FN = "cd2{a}.{b}.{c}.dmg"
  
  A_RANGE = (5, 6, 7)
  BC_RANGE = (0, 1, 2)
  
  def cd_exe_info(filename, a, b, c):
      f = filename.format(a=a, b=b, c=c)
      print(f)
      res = requests.head(BASE_URL+f, allow_redirects=True, timeout=10)
      if res.status_code != 200:
          print("Failed with status code " + str(res.status_code))
          print()
          return
      size = res.headers.get("Content-Length")
      if size:
          print("FOUND. Size = " + size, end = " ")
          try: print("(%.2f MB)" % (int(size)/1048576))
          except ValueError: pass
      else:
          print("FOUND. Size unknown")
      print()
  
  for n in (CDA_EXE_FN, CD_EXE_FN, CDM_DMG_FN):
      for i in A_RANGE:
          for j in BC_RANGE:
              for k in BC_RANGE:
                  cd_exe_info(n, i, j, k)
      print("----------")
  ```

</details>

---

## Windows 版破解

请在 [此处下载破解补丁](https://github.com/Z-H-Sun/MRN-ADF_Patch/releases/download/v2.22/COS_Win_Patch.exe)。

随后，运行破解程序。破解过程中，如下图所示，按窗口提示操作（一般而言，第一个问题按 <kbd>Y</kbd> 键，接下来按 <kbd>P</kbd> 键（或者等待 10 秒后自动以默认模式进行）。最后可以选填注册信息，不影响破解，只是可以在软件的“关于”对话框中显示这些用户自定义的信息。

然后就完成了！破解完成效果如下图。

![](/cos/260.png)

#### 疑难解答

* 运行补丁时，请确保在杀毒软件中放行。该补丁的代码开源于此处：[Patch.rb](https://github.com/Z-H-Sun/MRN-ADF_Patch/blob/tags/hidden/COS_for_Win/Patch.rb)。如果你对该补丁的安全性存在疑问，也可自己安装任意版本的 [Ruby 运行环境](https://rubyinstaller.org/) 并运行该脚本。
* 如果你不是系统管理员，可以 [下载这个无需管理员权限的破解补丁](https://github.com/Z-H-Sun/MRN-ADF_Patch/releases/download/v2.22/COS_Win_Patch_Non_Admin.exe)，但请注意这个补丁只能作用于为当前用户安装的程序，而无法进行任何需要权限的操作，否则，将出现 `Error occurred: #<Errno::EACCES: Permission denied - [文件名]>` 的红色失败信息。
* 破解过程中，如果有管理员权限却仍出现红色失败信息 `Error occurred: #<Errno::EACCES: Permission denied - [文件名]>`，则说明该文件正在被占用，无法写入。请关闭所有 ChemOffice 相关程序后重试。

  <details>
  
  但有时，"ChemDrawCtl.dll" 等文件仍然提示正在占用。这可能是由于 Windows 资源管理器的缩略图缓存 (Thumbnail Cache) 服务正在工作中。最简单的方法就是重启电脑。也可以在任务管理器中结束命令行为`dllhost.exe /ProcessiD:{ab8902b4-09ca-4bb6-b78d-a8f59079a8d5}`的进程，如下图所示。
  
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

## MacOS 版破解
* 官方安装过程结束后，必须先正常运行一遍 ChemDraw，系统验证过后再进行后续破解步骤 **（非常重要！）**
* 下载 [补丁程序](https://github.com/Z-H-Sun/MRN-ADF_Patch/releases/download/v2.22/CDM_Crack) 至任意位置
* 确保 “**终端 (Terminal)**” 程序具有 “**完全磁盘访问 (Full Disk Access)**” 权限 **（非常重要！）**
  * 进入 设置 (System Preferences) -> 隐私与安全性 (Security & Privacy) -> 完全磁盘访问权限 (Full Disk Access)，确认 终端 (Terminal) 在列表中，否则请单击 + 图标并添加、启用 实用工具 (Utilities) -> 终端 (Terminal)
* 通过 LauchPad 打开一个 “**终端 (Terminal)**” 窗口，输入 `ruby `，注意在字母y后**还有一个空格（非常重要！）**，然后将访达 (Finder) 中的补丁程序文件拖拽至终端窗口中（将会补全其路径），最后回车运行即可
  * 或者也可直接输入 `ruby "<path/to>/CDM_Crack"`
  * 如果出现错误，请确保“终端”拥有“完全磁盘访问权限”（见上条）；或者，可能是因为需要管理员权限，此时请运行 `sudo ruby "<path/to>/CDM_Crack"`
* 程序会自动检测 Mac 上安装的所有17及以上版本的 ChemDraw：

  * 对于未经破解的 ChemDraw 版本，程序将在用户按下<kbd>y</kbd>键后开始破解【Patch】
  * 对于已打过补丁的 ChemDraw 版本，程序将在用户按下<kbd>y</kbd>键后将软件回复至初始（未破解）状态【Restore】
  * 对于任一情况，若用户按下<kbd>n</kbd>键都将忽略这个版本

> [!note]
> 对于 25 版及以上的 ChemDraw，请特别注意破解程序最后显示的额外信息（见下图）。如果你使用的是搭载 Intel 芯片的老 Mac 电脑，那么恭喜你，你可以忽略这一段话并直接开始正常使用 ChemDraw 25。如果你不幸正在用 M1/M2/M3/M4/M5 芯片的新 Mac，那么请做以下步骤：

* 仅针对使用 Apple Silicon 芯片的新 Mac 用户：
    * 请安装 Rosetta，并在 ChemDraw 应用程序上点右键，选择“显示简介”，然后在“通用”部分勾选“使用Rosetta 打开 (Open using Rosetta)”选项。**这样就可以了。**
    * 如果你无法使用 Rosetta，那么必须在补丁程序最后按<kbd>y</kbd>键进行数字签名。
      * 这需要你拥有 `codesign`，如果没有的话请安装 Xcode Command Line Tools。

运行ChemDraw，点击Install按钮后，**即可正常激活**。在ChemDraw -> About窗口中，Licensed to后为空**是正常现象**。

![](/cos/261.png)

> [!note]
> 23 版及以上 ChemDraw 会弹窗询问选择何种注册模式，请选择第二种——Activation Code（见下图）。

<p align="center"><img width="60%" height="60%" src="/cos/232.png"></p>

以上安装破解过程在Mac OS 11-26 上测试通过。
