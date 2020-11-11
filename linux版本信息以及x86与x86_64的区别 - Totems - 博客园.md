一 x86、x86\_64、AMD64
-------------------

x86是指intel的开发的一种32位指令集，从386开始时代开始的，一直沿用至今，是一种cisc指令集，所有intel早期的cpu，amd早期的cpu都支持这种指令集，ntel官方文档里面称为“IA-32”

x84\_64是x86 CPU开始迈向64位的时候，有2选择：1、向下兼容x86。2、完全重新设计指令集，不兼容x86。AMD抢跑了，比Intel率先制造出了商用的兼容x86的CPU，AMD称之为AMD64，抢了64位PC的第一桶金，得到了用户的认同。而Intel选择了设计一种不兼容x86的全新64为指令集，称之为IA-64（这玩意似乎就是安腾），但是比amd晚了一步，而且IA-64也挺惨淡的，因为是全新设计的CPU，没有编译器，也不支持windows（微软把intel给忽悠了，承诺了会出安腾版windows server版，但是迟迟拿不出东西）。。。后来不得不在时机落后的情况下也开始支持AMD64的指令集，但是换了个名字，叫x86\_64，表示是x86指令集的64扩展，大概是不愿意承认这玩意是AMD设计出来的。

也就是说实际上，x86\_64,x64,AMD64基本上是同一个东西，我们现在用的intel/amd的桌面级CPU基本上都是x86\_64，与之相对的arm,ppc等都不是x86\_64。

x86、x86\_64主要的区别就是32位和64位的问题，x86中只有8个32位通用寄存器，eax,ebx,ecx，edx, ebp, esp, esi, edi。x86\_64把这8个通用寄存器扩展成了64位的，并且比x86增加了若干个寄存器（好像增加了8个，变成了总共16个通用寄存器）。同样的MMX的寄存器的位数和数量也进行了扩展。此外cpu扩展到64位后也能支持更多的内存了，等等许多好处。

对于普通程序来说，CPU位数的扩展、寄存器数量的增加不会带来明显的性能提升，比如IE浏览器、Office办公这类的软件。特定的程序很能够充分利用64位CPU、更多的寄存器带来的优势，比如MMX除了能提升多媒体程序的性能，对矩阵、多项式、向量计算都能带来提升，更多的MMX寄存器、更大的寄存器字长都有利于SIMD指令的执行，能够提升CPU对数据的吞吐量（RISC指令集的CPU动不动就有数百个寄存器，可以有效的缓存中间计算结果，不需要把中间结果写入内存，从而减少内存访问次数，显著提升性能）

二 查看linux系统版本命令
---------------

**一。查看内核版本命令：**

1） \[root@SOR\_SYS ~\]# cat /proc/version  
Linux version 2.6.18-238.el5 ([mockbuild@x86-012.build.bos.redhat.com](mailto:mockbuild@x86-012.build.bos.redhat.com)) (gcc version 4.1.2 20080704 (Red Hat 4.1.2-50)) #1 SMP Sun Dec 19 14:22:44 EST 2010  
\[root@SOR\_SYS ~\]#

2）\[root@SOR\_SYS ~\]# uname -r  
2.6.18-238.el5  
3）\[root@SOR\_SYS ~\]# uname -a  
Linux SOR\_SYS.99bill.com 2.6.18-238.el5 #1 SMP Sun Dec 19 14:22:44 EST 2010 x86\_64 x86\_64 x86\_64 GNU/Linux  
\[root@SOR\_SYS ~\]#

**二。查看linux版本：**

1) 登录到服务器执行 lsb\_release -a ,即可列出所有版本信息,例如:

\[root@SOR\_SYS ~\]# lsb\_release -a  
LSB Version:    :core-4.0-amd64:core-4.0-ia32:core-4.0-noarch:graphics-4.0-amd64:graphics-4.0-ia32:graphics-4.0-noarch:printing-4.0-amd64:printing-4.0-ia32:printing-4.0-noarch  
Distributor ID: RedHatEnterpriseAS  
Description:    Red Hat Enterprise Linux AS release 4 (Nahant Update 4)  
Release:        4  
Codename:       NahantUpdate4  
\[root@SOR\_SYS ~\]#

注:这个命令适用于所有的linux，包括Redhat、SuSE、Debian等发行版。

2) 登录到linux执行cat /etc/issue,例如如下:

\[root@SOR\_SYS ~\]# cat /etc/issue  
Red Hat Enterprise Linux Server release 5.6 (Tikanga)  
Kernel \\r on an \\m

\[root@SOR\_SYS ~\]#

3) 登录到linux执行cat /etc/redhat-release ,例如如下:

\[root@SOR\_SYS ~\]# cat /etc/redhat-release  
Red Hat Enterprise Linux AS release 4 (Nahant Update 4)  
\[root@SOR\_SYS ~\]#

注:这种方式下可以直接看到具体的版本号，比如 AS4 Update 1

4)登录到linux执行rpm -q redhat-release ,例如如下:

\[root@SOR\_SYS ~\]# rpm -q redhat-release  
redhat-release-5Server-5.6.0.3  
\[root@SOR\_SYS ~\]#

注:这种方式下可看到一个所谓的release号，比如上边的例子是5

这个release号和实际的版本之间存在一定的对应关系，如下：

 redhat-release-3AS-1 -> Redhat Enterprise Linux AS 3

 redhat-release-3AS-7.4 -> Redhat Enterprise Linux AS 3 Update 4

 redhat-release-4AS-2 -> Redhat Enterprise Linux AS 4

 redhat-release-4AS-2.4 -> Redhat Enterprise Linux AS 4 Update 1

 redhat-release-4AS-3 -> Redhat Enterprise Linux AS 4 Update 2

 redhat-release-4AS-4.1 -> Redhat Enterprise Linux AS 4 Update 3

 redhat-release-4AS-5.5 -> Redhat Enterprise Linux AS 4 Update 4

**另:第3)、4)两种方法只对Redhat Linux有效**

5) \[root@SOR\_SYS ~\]# file /bin/bash  
/bin/bash: ELF 64-bit LSB executable, AMD x86-64, version 1 (SYSV), for GNU/Linux 2.6.9, dynamically linked (uses shared libs), for GNU/Linux 2.6.9, stripped  
\[root@SOR\_SYS ~\]#

6) \[root@SOR\_SYS ~\]# file /bin/cat  
/bin/cat: ELF 64-bit LSB executable, AMD x86-64, version 1 (SYSV), for GNU/Linux 2.6.9, dynamically linked (uses shared libs), for GNU/Linux 2.6.9, stripped  
\[root@SOR\_SYS ~\]#

三 linux版本信息说明
-------------

Linux内核版本有两种：稳定版和开发版 ，Linux内核版本号由3个数字组成：r.x.y

  r：目前发布的内核主版本。  
  x：偶数表示稳定版本；奇数表示开发中版本。  
  y：错误修补的次数。

内核版本号每位都代表什么 ?

    以版本号为例： 2.6.18-128.ELsmp ,

    r:   2 , 主版本号

    x:  6 , 次版本号，表示稳定版本

    y:  18 , 修订版本号 ， 表示修改的次数，头两个数字合在一齐可以描述内核系列。如稳定版的2.6.0，它是2.6版内核系列。

    128:  表示这个当前版本的第5次微调patch ， 而ELsmp指出了当前内核是为ELsmp特别调校的

    EL :   Enterprise Linux   ； smp : 表示支持多处理器 ， 表示该内核版本支持多处理器

其它方面：

    一般的有三种  
     1  smp  
     2  bigmem  
     3  一般的内核

      Red Hat Linux开机的时候，GRUB的启动菜单会有两个选项，分别是  
　　   Red Hat Enterprise Linux ES (版本号.ELsmp)  
　　   Red Hat Enterprise Linux ES-up (版本号.EL)  
　　其实这个就是系统开机时由GRUB引导启动 － 单处理器与对称多处理器启动核心文件的区别。  
　　Red Hat Enterprise Linux ES (版本号.ELsmp)  multiple processor (symmetric multiprocessing )  
　　Red Hat Enterprise Linux ES-up (版本号.EL)   uniprocessor