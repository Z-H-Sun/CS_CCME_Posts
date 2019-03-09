# Mac 用户福音！ChemDraw 18 for Mac 无限试用
**<p align="center">Z.-H. Sun 1月30日</p>**

PerkinElmer在去年9月份高调宣布ChemOffice Suite 2018的发布，其中ChemDraw 18最受瞩目的新特性是**添加了Reaxys结构/反应式搜索的支持**（原先只支持SciFinder搜索），以及**添加了“插件”功能**（自带：ChemACX的CAS号/性质/价格查询功能）。

遗憾的是，目前网上尚无ChemDraw 18 for Mac破解版，而官网提供的试用版只提供10次试运行机会（*比17版少了10次emmm* ）。我通过一些反汇编手段强行改大了试运行次数，从而基本实现了无限次数试用（*20多亿次，即使每秒点一次也要68年……而且可以续回来*）。本文将和大家分享这个Mac版ChemDraw 18的破解程序，而Windows版本的ChemOffice Suite 18破解版可[点此](https://github.com/Z-H-Sun/CS_CCME_Posts/blob/master/cos/cow.md)访问。

*本试用版需要每次点击“试用”。如果觉得麻烦，本文还提供更旧版本的ChemDraw破解版下载，见[旧版下载安装](/cdm.md#旧版下载安装)一节，不过这样就无法使用新版本特性了。*

## 安装与运行
* 先下载官方程序包[ChemDraw18.dmg](https://github.com/Z-H-Sun/CDM_18/releases/download/v1/ChemDraw18.dmg)文件，然后双击打开，完成验证过程，正常安装。破解之前一定先**不要运行主程序（重要！虽然有补救方法）**

* 在应用程序文件夹 -> ChemDraw 18.0图标上右键，显示包内容，然后定位到Contents\Framworks\ChemDrawBase.framework\Versions\A文件夹

* 自己备份好ChemDrawBase，**并用[这个文件](https://github.com/Z-H-Sun/CDM_18/raw/master/ChemDrawBaseCrack)替换**（下载并重命名为ChemDrawBase，如下图所示），即可破解成功
<p align="center"><img width="80%" height="80%" src="https://github.com/Z-H-Sun/CS_CCME_Posts/raw/master/cos/1.webp"></p>

* 运行ChemDraw 18.0，跳出Activate ChemDraw窗口，点More options, Activate Later（试用次数2147483647，是signed int32的最大值，如下图所示），然后Activate。再点Install, Continue即可正常开启程序。麻烦之处在于每次启动都要点击试用，Install，Continue，**是正常现象**。
<p align="center"><img width="80%" height="80%" src="https://github.com/Z-H-Sun/CS_CCME_Posts/raw/master/cos/2.webp"></p>

* 补充说明：若试用次数小于10，则说明破解之前就已经（*不小心*）运行过ChemDraw 18.0，上述破解方法无效。此时的**补救措施为：用[这个文件](https://github.com/Z-H-Sun/CDM_18/raw/master/ChemDrawBaseRemedy)替换ChemDrawBase（下载并重命名为ChemDrawBase），按第4步Activate一遍**。此时试用次数被*续回2147483647*，但**不能正常跳出主程序**。不过我们的目的已经达到，此时，再**替换回之前的ChemDrawBase文件（程序自带的或Crack的都行）即可成功破解**

以上安装破解过程在Mac OS X 10.11 和 10.14 上测试通过。

## 运行效果
* 最新版ChemDraw的新特性：Reaxys搜索及Add-ins (ChemACX)。
<p align="center"><img width="80%" height="80%" src="https://github.com/Z-H-Sun/CS_CCME_Posts/raw/master/cos/3.webp"></p>

* ChemDraw for Mac（16版本以上）所特有的Unicode（甚至emoji）支持。*很遗憾，Windows版至今不支持插入Unicode字符（例如希腊字母、负号等），这一点我在推送[【ChemDraw】如何输入Unicode字符？](http://mp.weixin.qq.com/s?__biz=MzUzNDQ2MTE1Mw==&mid=2247483695&idx=1&sn=0b0a2683e8e7321330050c8a2563b169&chksm=fa952ea1cde2a7b7e370289a8b2ac060289d35d64a44264f2c26485e217cb6c7d4b123f82d71&scene=21) 中已论及。此外，即使是在Mac上存好的带Unicode字符的.cdx文件，Windows下ChemDraw打开也会有问题：Unicode字符会直接变为不可见。所以还是等哪天Windows版本的开发程序员哪天突然想到要解决这个问题再说吧……*
<p align="center"><img width="80%" height="80%" src="https://github.com/Z-H-Sun/CS_CCME_Posts/raw/master/cos/4.webp"></p>

# 正版试用
另外，如果觉得需要支持正版的同学，也可以从官网的[这个链接](http://scistore.cambridgesoft.com/ScistoreProductPage.aspx?ItemID=8900)申请试用，需要填写邮箱、身份等信息进行注册，大约一两天后会收到附有包含ChemDraw 18 for Mac和ChemOffice Suite 18 for Windows下载地址的邮件。上文中我所说的“官方程序包”就是来自这里（毕竟网上找了一圈没有/摊手）。有趣的是，虽然标明的是两周试用版，但其实并不限制时间，而是对试用次数进行了限制（10次免费试用）。

# 旧版下载安装
> [15.0版](https://github.com/Z-H-Sun/CDM_18/releases/download/v1/ChemDraw15.dmg)：运行CoreKeygen
> [16.0版](https://github.com/Z-H-Sun/CDM_18/releases/download/v1/ChemDraw16Professional.dmg)：**Name:** JKO；**Company:** CambridgeSoft；**SN:** 2；**Reg Code:** --JAKKO--

