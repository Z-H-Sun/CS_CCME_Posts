# ChemOffice 20\~22 for Windows / ChemDraw 20\~22 for Mac 一键破解
**<p align="center">Z.-H. Sun 20年11月27日<br>更新于 22年11月18日</p>**

## 更早的版本
* [ChemOffice for Win 19 / 18 / 17](/cos/cow2.md)
* [ChemDraw for Mac 19 / 18 / 17](/cos/cdm2.md)

## [跳过 新版本特性 一节](#本方法优点)

## 新版本特性
### 22.0
* 终于把给`Chem3D`整成 64 位的了……从此版本起，无需再把 32 位、64 位的 ChemOffice 重复装两遍了。如果你是 64 位系统，建议只装 64 位即可（除非你要用到`ChemFinder`，99% 用户都不需要）
  * 有 64 位`Chem3D`后就可以在 64 位`ChemDraw`里查看`Chem3D HotLink Window`了（在顶端`View`菜单中打开）
* 鉴于`ChemDraw`的 3D 显示功能日渐完善，现已支持直接打开单晶`.cif`文件，以三维形式显示（见下图）
  * 其实很鸡肋，二维画布显示三维结构显得特别拥挤，而且也不能较好地更改原子的三维位置（只能在面内平移）
* 虽然之前就有虚线键可以用来表示氢键，但现在新增了一个“氢键”类型（中间不是虚线而是点线），更加规范化了（见下图）
* “导出分子的三维结构”功能中，之前只支持高亮`键/原子`，现在新增对`环`高亮的支持（见下图）
  * 在这种没啥乱用的功能上挤牙膏……~~这种行为我们一般称之为不务正业……~~
* 画寡聚核酸、多肽等生物大分子时，若选用`Sequence Graphic Monomers`样式，则会以更美观的流式图形式显示（`File -> Apply document settings from`菜单中选择，见下图）
  * 咱不搞生物，但也没觉得美观到哪里去~
* `ChemScript`大部分人都用不到，不过有一个说大不大说小不小的更新，就是把几百年前就开始依赖的`python 3.4`（Python 官方早就不维护了）更新成`3.9`了，可喜可贺

新功能展示及破解效果图（上：Win；下：Mac）：

<p align="center">
<img width="60%" height="60%" src="/cos/220.png">
<img width="60%" height="60%" src="/cos/221.png">
</p>

### 21.0
* （自20.1版本起）[解决了](https://informatics-support.perkinelmer.com/hc/en-us/articles/4408274326932)一个因 Win10 更新导致的[软件卡顿问题](https://www.zhihu.com/question/444922651/answer/1979751680)
* 支持导出球棍模型为 3MF 格式，在 Win10 下可以很方便地用 `PowerPoint`、`3D Builder`、以及自带的`画图3D`、`Print 3D`查看（或编辑）。也支持复制到剪贴板，这样可以（省下导出的这步操作）直接粘到 `PPT` 或 `3D Builder` 里。

  * 注意需要先运行结构式3D清理功能（见下文），不然所有原子仍然是处于同一平面内的
  * 默认是不会画出氢原子的，除非手动、明确地画出 C–H（或 N–H、O–H）键
  * ~~一点吐槽：越来越像玩具了……反正不做构象分析的我是用不到这功能的~~
* 声称是优化了结构式的3D清理功能和添加了快捷键，但反正我是没感受到差异
* 开始强推 `ChemOffice+`，之前版本是可以另外单独下载，这个版本则是直接集成进安装包了（所以可以看到安装包体积肉眼可见地增加了）
  * 主要功能类似于云实验笔记，有一个个人觉得很赞的功能是提取某个 Word 文档或 PPT 里的所有化学结构式和反应式，方便下次要用时直接拷。但目前做的还不是很完善。
  * 其次，这是一个云应用，所以是不可能破解的（~~除非把 PerkinElmer 的数据库黑了……~~）。**如果没有许可的话，是完全用不了的，安装的时候就直接别选这个组件了**

新功能展示及破解效果图（上：Win；下：Mac）：

<p align="center">
<img width="60%" height="60%" src="/cos/210.png">
<img width="60%" height="60%" src="/cos/211.png">
</p>

### 20.0
* 添加新快捷键，例如<kbd>Enter</kbd>编辑当前分子，离开鼠标，仅用键盘即可快速画出反应式。新增快捷键一览表，各种快捷操作一目了然。
* 继19版新增给环着色功能后，本版又增加给键/原子/标签增加颜色高亮功能
* 新增结构式3D清理功能，画出平面键线式可自动生成三维构型（包含透视效果及远处虚化效果），结合“Structure Perspective”工具使用，搞天然产物合成的同志们一定非常喜欢

新功能展示及破解效果图（上：Win；下：Mac）：

<p align="center">
<img width="60%" height="60%" src="/cos/200.png">
<img width="60%" height="60%" src="/cos/201.png">
</p>

## 本方法优点
* 本法为通用破解补丁，预计之后再出新版也能轻松解决，无需满网找资源（还找不到）
* 便捷，一键解决，无需一个个手动替换
* 破解更完全，具备网传破解版没有的功能（如Office内嵌对象编辑，Chem3D hotlink等，见更早版本的推送）

## 使用方法
### Windows
* 只需直接下载运行单文件版安装破解程序`cos22.0_Crack.exe`或`cos21.0_Crack.exe`或`cos20.0_Crack.exe`，即可正常使用。正常安装结束后，自动跳出破解补丁窗口。

  * [Google Drive](https://drive.google.com/open?id=1FT3l0msiLPsarmT78JQ8_sgbdJLMY4_X)
  * [百度网盘](https://pan.baidu.com/s/1smDXW8GNTPErq_yjilDhLg?pwd=csme)
  
* **若已经安装了未破解版或网传不完全破解版**，则可单独下载使用[破解补丁](https://github.com/Z-H-Sun/MRN-ADF_Patch/releases/download/v2.15/COS_Win_Patch.exe)

  * 注意请下载上方链接中的最新补丁程序。早先的补丁无法正确破解 22.0/21.0 版本，已在最新版中修复该 Bug。因为这是通用破解补丁，预计之后再出新版也能正常破解
  * 如果已经下载运行了上面的单文件版安装破解程序，因其本身就会自动运行该破解补丁程序，**故无需再另行下载此补丁**
* 破解过程中，按窗口提示操作，或者直接等一会（以默认模式进行）即可。最后可以选填注册信息，不影响破解，只是会将这些信息显示在软件的“关于”对话框中（见第一张图）。（和之前的破解补丁不同，最后不会弹出新的注册信息对话框，因为已经整合到主程序中了。）

<p align="center"><img width="60%" height="60%" src="/cos/202.png"></p>

---

#### Windows 下的替代破解法
* 虽然上述破解方法几乎完美，但若多个Windows ChemDraw用户在同一局域网内，可能出现弹窗提示（详见 [Issue #5](https://github.com/Z-H-Sun/CS_CCME_Posts/issues/5)）。这是由那个序列号本身的限制所致。此时可尝试另一种不完全破解方法（与网传破解补丁原理相同）。**注意，采用本方法将不能正常使用ChemDraw for Excel、ChemDraw内的Chem3D hotlink等功能（详见之前推送），因此，除非不得已（多个Windows ChemDraw用户在同一局域网内），不推荐采用本方法。**

  * 在安装完 ChemOffice 后（**无论是不是破解版均可**），下载并运行[此破解补丁](https://github.com/Z-H-Sun/MRN-ADF_Patch/releases/download/v2.13/COS_Win_Patch.Deprecated.exe)，使用方法与上面类似。
  * 该补丁对 ChemOffice 17~21 通用。
  * 若仍有弹窗提示（暂未发现），请尝试卸载之前的完全破解补丁（下载上一节中的补丁，按<kbd>R</kbd>进入`Restore`模式）。
---

### Mac
* 和之前的方法一样。以下仅为（替换了部分链接的）复制粘贴。
* **最好先在另一台Windows电脑上下载下述安装包和替换补丁，用U盘拷贝至此Mac电脑**

  * 先下载官方程序包`ChemDraw22.dmg`或`ChemDraw21.dmg`或`ChemDraw20.dmg`，然后双击打开，正常安装。

    * [Google Drive](https://drive.google.com/open?id=1GRwysPQhOYnrriZTKSRc05Mf_Q7xd5DC)
    * [百度网盘](https://pan.baidu.com/s/1PDgXv4qrZHybyqf_niM2eA?pwd=csme)
  * 下载[补丁程序](https://github.com/Z-H-Sun/MRN-ADF_Patch/releases/download/v2.15/CDM_Crack)至任意位置，以“终端 (Terminal)”方式打开补丁文件

    * 上面的网盘文件夹里也有这个文件 `CDM_Crack`，择一方式下载即可
  * 详情/若发生错误：请见[一般操作流程及疑难解答](/MAC.md)
  * 程序会自动检测PC上安装的所有17及以上版本的ChemDraw（如下图所示）：

    * 对于未经破解的ChemDraw版本，程序将在用户按下<kbd>y</kbd>键后开始破解【Patch】
    * 对于已打过补丁的ChemDraw版本，程序将在用户按下<kbd>y</kbd>键后将软件回复至初始（未破解）状态【Restore】
    * 对于任一情况，若用户按下<kbd>n</kbd>键都将忽略这个版本
<p align="center"><img width="60%" height="60%" src="/cos/203.png"></p>

* 运行ChemDraw，点击Install按钮后，**即可正常激活**。在ChemDraw -> About窗口中，Licensed to后为空**是正常现象**。

以上安装破解过程在Mac OS X 10.14、10.16及最新版 11.0 上测试通过。
