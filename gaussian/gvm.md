# 面向Mac用户—GaussView 5 for Mac and Gaussian 09M
**<p align="center">Z.-H. Sun / 2月1日</p>**

在[创刊推送](http://mp.weixin.qq.com/s?__biz=MzUzNDQ2MTE1Mw==&mid=2247483661&idx=2&sn=0f5ca623978826356c0a10cf51b0a44c&chksm=fa952e83cde2a795cb22baa2e346c2cd2dde447e4c9ad9886f3ae1c3f75e12f5e4a01f289dd0&scene=21#wechat_redirect)中，我提供了Windows和Linux平台的（*所能搞到的*）最新版本GaussView和Gaussian程序下载，但是唯独没有找到Mac版本的。感谢[清化科协](https://thuchemst.github.io/2016/08/01/gaussian-download/index.html#download)和清华化工系小伙伴的友情帮助，现在Mac版的资源也已经移到**之前分享的百度云链接**中了（如果不记得了可点击[此处](https://pan.baidu.com/s/1xr7lDuXzpFiu21xodvPCPg)，密码: zsun），欢迎Mac用户下载安装。

清化科协所提供的程序包含了GaussView的激活密钥gv5.key，但这有可能包含购买者信息，不知道用户太多会不会被Gaussian, Inc.发现而造成麻烦（*不过其实之前提供的Windows/Linux版都含gv6.key，好像也没啥关系…*）。所以在此次发布的版本中，我清空了gv5.key中的所有字符，并通过[这篇文章](https://blog.csdn.net/communix/article/details/9298571)中所介绍的方法修改了GaussView主程序，使其在没有激活密钥信息的情况下也能正常启动。至于Gaussian09主程序，则不需要任何注册信息就能运行，而网上绝少有下载的原因我猜也只是Gaussian, Inc.的保密工作做得太好了……

## 下载安装方法
* GaussView: 下载[网盘](https://pan.baidu.com/s/1xr7lDuXzpFiu21xodvPCPg)中zip压缩文件，拖到应用程序文件夹，解压进入gv文件夹，**直接双击GaussView即可运行**。
* Gaussian的安装方法比较麻烦，和Linux版一样没有图形用户界面（Windows版是有的），需要设置环境变量后在命令行用户界面下运行，具体方法参见压缩包中的官方说明。不过我猜大部分用户都用不到这个，毕竟很少会在个人PC上跑吧。

## 关于GaussView 5 for mac的附加说明
* 完全可以不装Gaussian只装gv，这样的话打开gv时会有两个警告窗口，确定即可。这在任何平台上都是如此，属正常现象。
* 拿gv 5（而不是最新版的gv 6）去打开超算平台的Gaussian 16跑完的输出文件，官方提示有较小概率可能报错，但解决方法很简单，自行搜索即可。

*虽然不是最新版的Mac平台GaussView和Gaussian，但是能用就行……最近在CSDN上还看到有Windows平台下的Gaussian 16 的安装包下载，但是运行之后发现并不是完整的程序，缺少很多计算相关的可执行文件。不过想了想，反正用Windows跑Gaussian的情形本身少之又少，又还有G09W，就懒得费心去找了。*
