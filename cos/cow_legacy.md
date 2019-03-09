# ChemOffice 2018/2017 for Windows一键破解版

**注意：该方法已不被推荐。更好的激活方法请参见[此文](/cos/cow.md)**。另请参见：[Mac版ChemDraw 18资源](/cos/cdm.md)。

## 新版本特性
> [跳转](/cos/cow.md#新版本特性)

## 官方包下载安装
> [跳转](/cos/cow.md#官方包下载安装)

## 下载与使用
安装完官方试用版之后，破解的过程其实很简单，只需下载运行[ChemOfficePatch.exe](https://github.com/Z-H-Sun/COPatch/releases/download/v1.5/ChemOfficePatch.exe)即可（见下图）。因为网传的17版破解补丁中找文件的过程比较麻烦，所以除了18版，我也**同时整合了17版ChemOffice的破解功能**。一般来说，如果你是默认安装路径，点“破解”便可一键完成，之后所有ChemOffice模块就能正常运行了。

更细节的使用方法和程序源码见[此仓库](https://github.com/Z-H-Sun/COPatch/)。
<p align="center"><img width="60%" height="60%" src="/cos/-1.webp"></p>

## 特色与缺点
目前网上流传的ChemOffice 2018破解版有以下几个缺陷：
* 第一个最为致命，没有破解64位版本ChemDraw，导致装好ChemOffice 64-bit Support之后根本无法打开存好的.cdx文件和Office中内嵌的ChemDraw对象（要不其实干脆就别装64-bit Support，其实问题也不大）
* 第二是完全没有破解ChemDraw For Excel插件
* 另外，操作起来也不是很方便。

我经过反编译修改，解决了这几个问题（前者的破解方式与32位的以及2017版的ChemDraw类似；后者在网上无破解的原因是程序更改了验证机制，导致之前的破解方法失效，但我通过修改其他指令能成功激活）。

目前为止，本破解版的缺陷在于虽然能激活启用ChemDraw for Excel，但其中部分高级功能仍然无法使用，这是网上流传的2017版破解也存在的问题，不过一般也不会影响大家的日常使用，就暂时不去考虑了。提示原因为“ChemDraw for Excel requires a higher activation level”（已知的等级有Viewer、Prime、Ultra、Professional，试用版是不支持这些功能的。主要是验证机制复杂，导致ChemDrawCtl18.dll无法破解。我在尝试一番后不得不放弃。
