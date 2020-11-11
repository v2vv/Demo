计算机的体系结构从指令集的复杂度上可以分两类，一是复杂指令集CISC，主要是X86架构。另一类是精简指令集RISC，这个比较多，主要是ARM、MIPS、PowerPC等。  
拿到一块开发板，有时候想快速的知道它的体系结构或者叫系统架构，linux上提供了比较多的方法来判断。下面列几种相对常见一些的

uname命令  
uname -a

不是最直观的，但是也是一个不错的命令。

nvidia@tegra-ubuntu:~$ uname -a  
Linux tegra-ubuntu 4.4.38-tegra #1 SMP PREEMPT Fri Jul 28 09:55:22 PDT 2017 aarch64 aarch64 aarch64 GNU/Linux

aarch64就是ARM架构

openwrt@ubuntu:~$ uname -a  
Linux ubuntu 4.4.0-21-generic #37-Ubuntu SMP Mon Apr 18 18:33:37 UTC 2016 x86\_64 x86\_64 x86\_64 GNU/Linux

X86架构

root@IceCreamBox:~# uname -a  
Linux DrogooBox 3.3.8 #33 Tue Mar 22 15:02:01 CST 2016 mips GNU/Linux

MIPS架构

file命令  
file看一下本地的可执行程序，比如/bin/bash，随便找个可执行程序就可以。

nvidia@tegra-ubuntu:~$ file /bin/bash  
/bin/bash: ELF 64-bit LSB executable, ARM aarch64, version 1 (SYSV), dynamically linked, interpreter /lib/ld-, for GNU/Linux 3.7.0, BuildID\[sha1\]=64c27467ad7a6c507c8f79464fea872fed5dd044, stripped

里面有个ARM，显然是ARM架构。

openwrt@ubuntu:~$ file /bin/bash  
/bin/bash: ELF 64-bit LSB executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/l, for GNU/Linux 2.6.32, BuildID\[sha1\]=04eca96c5bf3e9a300952a29ef3218f00487d37b, stripped

显然是X86架构

arch命令  
arch命令给出的结果比较简洁

nvidia@tegra-ubuntu:~$ arch  
aarch64

ARM架构

openwrt@ubuntu:~$ arch  
x86\_64

X86架构

另外，还有一种方式，直接去看cpuinfo信息，然后自己再简单分析一下即可。

cat /proc/cpuinfo

————————————————  
版权声明：本文为CSDN博主「奔狼的春晓」的原创文章，遵循 CC 4.0 BY-SA 版权协议，转载请附上原文出处链接及本声明。  
原文链接：https://blog.csdn.net/lixuande19871015/java/article/details/90485929