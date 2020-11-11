[![](https://upload.jianshu.io/users/upload_avatars/13169213/58cfec11-ef6d-4758-b721-54dc860aaad5?imageMogr2/auto-orient/strip|imageView2/1/w/96/h/96/format/webp)](https://www.jianshu.com/u/0e2387565a95)

0.1672019.03.09 17:45:44字数 1,109阅读 30,729

**总的来说，apt-get update就是访问服务器，更新可获取软件及其版本信息，但仅仅给出一个可更新的list，具体更新需要通过apt-get upgrade，apt-get upgrade可将软件进行更新，但是有文章指出不建议一次性全部更新，因为最新的不一定是最好的，有可能出现版本不兼容的情况。**

来源：http://www.baiyuxiong.com/?p=529

入门linux的同志，刚开始最迫切想知道的，大概一个是中文输入法，另一个就是怎么安装软件。本文主要讲一下LINUX安装软件方面的特点。

在windows下安装软件，我们只需要有EXE文件，然后双击，下一步直接OK就可以了。但在LINUX下，不是这样的。每个LINUX的发行版，比如UBUNTU，都会维护一个自己的软件仓库，我们常用的几乎所有软件都在这里面。这里面的软件绝对安全，而且绝对的能正常安装。

那我们要怎么安装呢？在UBUNTU下，我们维护一个源列表，源列表里面都是一些网址信息，这每一条网址就是一个源，这个地址指向的数据标识着这台源服务器上有哪些软件可以安装使用。

编辑源命令：

**sudo gedit /etc/apt/sources.list**

在这个文件里加入或者注释（加#）掉一些源后，保存。这时候，我们的源列表里指向的软件就会增加或减少一部分。

接一下要做的就是：

**sudo apt-get update**

这个命令，会访问源列表里的每个网址，并读取软件列表，然后保存在本地电脑。我们在新立得软件包管理器里看到的软件列表，都是通过update命令更新的。

update后，可能需要upgrade一下。

**sudo apt-get upgrade**

这个命令，会把本地已安装的软件，与刚下载的软件列表里对应软件进行对比，如果发现已安装的软件版本太低，就会提示你更新。如果你的软件都是最新版本，会提示：

**升级了0个软件包，新安装了0个软件包，要卸载0个软件包，有0个软件包未被升级。**

总而言之，update是更新软件列表，upgrade是更新软件。

***

来源：https://blog.csdn.net/csdn\_duomaomao/article/details/77802673

简要说明：

apt update：只检查，不更新（已安装的软件包是否有可用的更新，给出汇总报告）

用法：sudo apt update

apt upgrade：更新已安装的软件包

用法：sudo apt upgrade 软件包名

附图：

0、ubuntu16.04版本的更新提示，以及执行apt update的过程,有129个包可以升级。

![](https://upload-images.jianshu.io/upload_images/13169213-4a758bc7d6bc682f.png?imageMogr2/auto-orient/strip|imageView2/2/w/659/format/webp)

本机采用ubuntu16.04系统，已使用sudo apt update && sudo apt upgrade -y将系统更新到最新的ubuntu 16.04.03。再使用阿里源，单独安装Docker v1.12.3版本的软件，执行如下操作，对比两个命令的差别。

1、sudo apt update只检查是否有可用更新，给出汇总报告和提示信息

使用sudo apt list --upgradable查看可升级的软件信息

sudo apt list --upgradable -a查看可升级的软件的全部版本信息

![](https://upload-images.jianshu.io/upload_images/13169213-b3d2ea4d60501b2e.png)

2、使用apt upgrade将Docker从1.12.3升级到1.13.1的过程

![](https://upload-images.jianshu.io/upload_images/13169213-0f6211a9370ff46a.png)

3、重启Docker服务，再次查看可用的更新

![](https://upload-images.jianshu.io/upload_images/13169213-03e9ab7c3fd916e3.png)

注意事项：不能随意使用sudo apt upgrade -y命令

Ubuntu总是认为：最新的软件就是最好的软件，建议用户安装使用。直接使用sudo apt update && sudo apt -y upgrade，就会将本机已安装的软件全部更新到最新！

但是在实际工作中并不总是这样，K8S v1.6.6版本只支持Docker v1.12.3版本，即K8S依赖于某一特定版本的Docker，不支持最新版本的Docker。因此要想在Docker上部署K8S v1.6.6就不能ubuntu系统中随意使用sudo apt upgrade -y 命令。

"小礼物走一走，来简书关注我"

还没有人赞赏，支持一下

[![  ](https://upload.jianshu.io/users/upload_avatars/13169213/58cfec11-ef6d-4758-b721-54dc860aaad5?imageMogr2/auto-orient/strip|imageView2/1/w/100/h/100/format/webp)](https://www.jianshu.com/u/0e2387565a95)

总资产5 (约0.42元)共写了4.8W字获得57个赞共17个粉丝

### 推荐阅读[更多精彩内容](https://www.jianshu.com/)

*   http://blog.csdn.net/mathewsking/article/details/8211273 ...
    
*   一、文件/文件夹管理 ls 列出当前目录文件（不包括隐含文件） ls -a 列出当前目录文件（包括隐含文件） ls...
    
    [![](https://cdn2.jianshu.io/assets/default_avatar/5-33d2da32c552b8be9a0548c7a4576607.jpg)小杰的简书](https://www.jianshu.com/u/e51051c7ef07)阅读 1,503评论 0赞 45
    
*   https://linux.cn/article-8782-1.html Linux 包管理基础：apt、yum、...
    
    [![](https://upload.jianshu.io/users/upload_avatars/13548043/95d0b447-fa14-4fcc-8234-3669bdcd7348?imageMogr2/auto-orient/strip|imageView2/1/w/48/h/48/format/webp)是我拉叔](https://www.jianshu.com/u/5bc634ed43e2)阅读 246评论 0赞 0
    
*   一、文件/文件夹管理 ls 列出当前目录文件（不包括隐含文件）ls -a 列出当前目录文件（包括隐含文件）l...
    
    [![](https://upload.jianshu.io/users/upload_avatars/6422358/70c9438b-1248-49c2-be6f-5abb80ddef9f?imageMogr2/auto-orient/strip|imageView2/1/w/48/h/48/format/webp)路痴千行](https://www.jianshu.com/u/cf6a5996ab2d)阅读 1,533评论 0赞 4
    
*   《民主主义与教育》读书笔记（十一） ——第十一章：经验和思维 2017/8/12 一、经验的性质： 经验既包含有主...