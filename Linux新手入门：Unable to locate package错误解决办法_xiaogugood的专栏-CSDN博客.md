![](https://csdnimg.cn/release/blogv2/dist/pc/img/reprint.png)

[xiaogugood](https://me.csdn.net/xiaogugood) 2014-01-17 09:56:26 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/articleReadEyes.png) 307591 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/tobarCollect.png) 收藏  32 

最后发布:2014-01-17 09:56:26首次发布:2014-01-17 09:56:26

原文地址：[http://www.cppblog.com/colorful/archive/2012/04/29/173122.html](http://www.cppblog.com/colorful/archive/2012/04/29/173122.html)

最近刚开始接触[Linux](http://www.letuknowit.com/topics/linux "关于Linux的学习心得")，在虚拟机中装了个[Ubuntu](http://www.letuknowit.com/topics/tag/ubuntu "关于ubuntu的学习心得")，当前的版本是[Ubuntu 11.10](http://www.letuknowit.com/topics/tag/ubuntu-11-10)，装好后自然少不了安装一些软件，在设置了软件的源后，就开始了 sudo apt-get install，结果出现了下面的Unable to locate package错误：

1.  letuknowit@ubuntu:~$ sudo apt-get install mysql-server mysql-client
2.  \[sudo\] password for letuknowit:
3.  Reading package lists… Done
4.  Building dependency tree    
5.  Reading state information… Done
6.  E: Unable to locate package mysql-server
7.  E: Unable to locate package mysql-client
8.  letuknowit@ubuntu:~$

　　这叫一个郁闷啊，出师不利，不带这么吓唬刚玩Ubuntu的小朋友吧~于是赶紧找资料，又回顾下前面的操作，最后发现问题出**在执行sudo apt-get install之前更换了软件源，但是却忘了update下**了，于是执行下面的命令：

等上面命令执行完后，再执行sudo apt-get install就可以了！其实错误信息已经很明确了，Unable to locate packet就是无法找到包嘛，那还不赶紧sudo apt-get update下！

附另一篇文章：

原文地址：[http://blog.chinaunix.net/uid-22002627-id-3475650.html](http://blog.chinaunix.net/uid-22002627-id-3475650.html)  

碰到这个问题后找到这个帖子就转了过来 当用apt-get更新软件包时常出现错误提示Unable to locate package update, 尤其是在ubuntu server上,解决方法是： 先更新apt-get #sudo apt-get update 执行完后，问题就解决了。 继续更新： #sudo apt-get upgrade 然后就可以安装apache: #sudo apt-get install apache2 等就可以了 安装mysql命令：sudo apt-get install mysql-server mysql-client