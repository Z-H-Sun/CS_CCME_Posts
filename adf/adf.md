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
### 如何计算有效载流子耦合

* 这个版本的ADF没有自动计算电子/空穴耦合（有效转移积分）*V*的功能（~~2014以上版本才支持这个功能，但可惜网上找不到可用安装包~~）。因此作者编写了`CTIout`这个程序（源码：[CTIout.rb](https://github.com/Z-H-Sun/MRN-ADF_Patch/tree/master/ADF_utils/CTIout)；下载地址：[Windows](https://github.com/Z-H-Sun/MRN-ADF_Patch/releases/download/v2.02/CTIout.exe)、[Linux](https://github.com/Z-H-Sun/MRN-ADF_Patch/releases/download/v2.02/CTIout_Linux)）以实现这个功能。其中有效转移积分*V*和原始转移积分*J*<sub>ab</sub>之间的关系为

<p align="center"><i>V</i> = [<i>J</i><sub>ab</sub> − ½<i>S</i><sub>ab</sub>(<i>H</i><sub>aa</sub> + <i>H</i><sub>bb</sub>)] / (1 − <i>S</i><sub>ab</sub><sup>2</sup>)</p>

* 该版本的ADF只会在计算结束后记录*J*和位点能*H*、重叠积分*S*，你可以在输出文件中找到这些数值并按上公式手动计算；而`CTIout`自动化了整个流程。

* 一般来说，你会计算若干个dimer之间的转移积分，最后得到若干个.out输出文件，请最好将所有这些.out文件收集到同一个文件夹下。然后在终端中`cd`到这个目录下并执行`CTIout`命令。Linux平台下请注意大小写。请注意将可执行文件`CTIout`或`CTIout.exe`置于`PATH`环境变量包含的目录下。或者，假若你对终端操作不熟悉，可以将`CTIout`复制到这些.out文件所在的目录下，然后双击运行即可。

* 运行后，程序会先列出当前目录下的所有.out文件。若要计算某一个输出文件对应的有效转移积分*V*，则输入相应编号后回车；若要计算所有文件中的*V*，则直接回车即可。输出结果中`J_12^h`代表空穴转移积分，`|V_e|`代表有效电子转移积分的绝对值，其余符号含义以此类推。此外，程序还会在当前目录下生成一个表格文件`outSummary.csv`，可用Excel等程序打开。

### 如何快速添加转移积分运算任务

* 尽管ADF是一个强大的量子计算软件，但它相对来说对初学者不太友好，（特别是早期版本的）程序预设做得较差，有许多需要用户注意和自己更改的设置项，否则将会**无法运行**或**得到毫无意义的错误数值**。

* 转移积分运算本质上是 **单点能 (Single Point)** 计算，但在`ADFInput`中编辑时需要在`Single Point`预设的基础上改很多参数，容易忙中出错。因此作者增设了`CTI`预设，[CTI.tpl](https://github.com/Z-H-Sun/MRN-ADF_Patch/raw/master/ADF_utils/CTI.tpl)。请将此文件置于相应文件夹下，便可在`ADFInput`的“预设”选择框中读取：

  * Windows: `$ADFHOME/../ADF_DATA/Templates`
  * Linux: `~/.scm_gui/Tpl`

### 修正Linux平台GUI程序远程显示崩溃问题

* 使用X11转发显示远程GUI程序时，对OpenGL的渲染有两种模式：Direct和Indirect。后者麻烦频出，已被当前主流所抛弃，但ADF的GUI外壳脚本却强行设置了indirect rendering (`export LIBGL_ALWAYS_INDIRECT=1`)，导致窗口在远程显示器上显示时崩溃（无论是远程显示器是Windows系统还是Linux系统）

* 请将`$ADFHOME/bin/startvtk`中的第18–22行注释掉，以修正该问题

### 修正Linux平台并行运算的MPI支持问题

* 在某些高性能计算平台上运行并行计算时，会报错：multiple full-membership pkey found in partition key table

* 请在`~/.bashrc`中追加写入环境变量`export MPI_IB_PKEY=0xffff`以解决

### 修正SLURM支持问题

* 作者发现提交SLURM作业时，无论环境变量`NSCM`（并行运算核数）设为多少，都永远只有一个核在运行（在.logfile中第一行会显示`Nodes: n1, Procs: n2`），速度很慢

* 请在`$ADFHOME/bin/start`中第235行，`mpirun.mpich`多加一个`-np $NSCM`参数以解决

### 自动设定NSCM以免触及许可并行核数上限

* 本破解版仍有一定限制，并行核数上限为8。如果不加设置，而当机器超过8核时（例如在32核节点上跑程序），会抛出“LICENSE INVALID”异常

* 请在`~/.bashrc`中追加写入环境变量`export NSCM=8`

* 即使已经设置了`NSCM`环境变量，`ADFJobs`会默认无视该设置，使用所有CPU核来进行运算。因此，请在`ADFJobs`中更改默认的两个Run Command（`Sequential`和`Interactive`），将`sh "$job" "NSCM=$options ; export NSCM"`中的`$option`改为`8`

### 免责声明

* 以上“疑难解答”中的问题无法在网络上找到解决方案，以上修改均为作者自行试验觉得操作可行的方法，无法预计是否会产生其他不良后果。如果出现问题，请开启一个[Issue](https://github.com/Z-H-Sun/CS_CCME_Posts/issues)。
