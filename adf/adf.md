# ADF 2012.01 (Win x86/Linux x64) 安装及破解

**本破解方法对2014及更高版本ADF无效，切勿尝试！**

## 破解原理
[跳转](/adf/adfm.md)

## 安装破解方法
* 首先下载官方安装包：[Baidu Pan](https://pan.baidu.com/s/1U9aMcbzxK4tfADx824h29A)（提取码: zsun）；[Google Drive](https://drive.google.com/open?id=1l5BSEqnjJ3oy0nED_RWhio38qbxDaWKI)
* 安装方法：

  * Windows：双击adf2012.01a.pc_windows.platform_mpi.exe。默认安装在`C:\ADF2012.01`，下文以此为例。可更改安装路径，**但不能含空格**。
  * Linux: `cd`到adf2012.01a.pc64_linux.platform_mpi.bin.tgz所在目录，输入以下命令
  
```bash
tar -xzvf adf2012.01a.pc64_linux.platform_mpi.bin.tgz -C ~
mkdir ~/adftmp
cat << EOF >> ~/.bashrc

# ADF
export ADFHOME=~/adf2012.01
export SCMLICENSE=\$ADFHOME/license.txt
export SCM_TMPDIR=~/adftmp
export ADFBIN=\$ADFHOME/bin
export ADFRESOURCES=\$ADFHOME/atomicdata
export PATH=\$ADFBIN:\$PATH
EOF
source ~/.bashrc
```
* 将[许可文件](https://github.com/Z-H-Sun/MRN-ADF_Patch/raw/master/ADF_utils/license.txt)下载后放在`adf2012.01`（`C:\ADF2012.01`或`~/adf2012.01`）文件夹下

* 该许可文件早已过期，所以我们要对ADF的可执行文件进行一些修改。下载`patchADF`并运行

  * Windows：下载[patchADF.exe](https://github.com/Z-H-Sun/MRN-ADF_Patch/releases/download/v2.0/patchADF.exe)，双击运行。ADF若安装在系统盘，则请**右键->以管理员身份运行**
  * Linux：下载[patchADF_linux](https://github.com/Z-H-Sun/MRN-ADF_Patch/releases/download/v2.0/patchADF_linux)，首先`cd`到那个文件夹，然后`chmod +x patchADF_linux`设置运行权限，接着`./patchADF_linux`运行

* 按照提示，键入y并回车以对ADF的各个模块程序进行破解（下图），大约2分钟即可完成。之后可尝试运行`adfjobs`查看是否已可正常运行。
<p align="center"><img width="60%" height="60%" src="/adf/1.png"></p>

## 附加说明
本补丁只是破解了“过期”这一点。但是我们的许可文件还有两处限制：
* **没有GENNBO（自然键轨道）的许可**
* **限制并行核数上限为8**

另外，虽然到目前为止未发现破解有任何问题，但若“过期”还是不幸被触发，则还有另一个办法：调整系统时间为2012年之前。如果没有管理员权限无法更改系统时间，则Linux下还有`FakeTime`包可以利用，请自行搜索（例如，`export LD_PRELOAD=blahblah/libfaketime.so.1 FAKETIME=-20y`伪造时间为20年前）。对更高版本的ADF，**切勿尝试**！

## 疑难解答
~~待更新~~
