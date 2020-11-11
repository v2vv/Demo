![](https://csdnimg.cn/release/blogv2/dist/pc/img/original.png)

[奔奔尚](https://me.csdn.net/qq_29753285) 2019-07-08 20:24:37 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/articleReadEyes.png) 2066 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/tobarCollect.png) 收藏  4 

最后发布:2019-07-08 20:24:37首次发布:2019-07-08 20:24:37

版权声明：本文为博主原创文章，遵循 [CC 4.0 BY-SA](http://creativecommons.org/licenses/by-sa/4.0/) 版权协议，转载请附上原文出处链接和本声明。

一、安装docker
----------

下面是使用阿里云的源进行安装的方法，如果在其他系统上安装，比如ubuntu，把debian换成ubuntu就可以了。

    
    sudo apt-get update
    sudo apt-get -y install apt-transport-https ca-certificates curl software-properties-common
    
    curl -fsSL http://mirrors.aliyun.com/docker-ce/linux/debian/gpg | sudo apt-key add -
    
    sudo add-apt-repository "deb [arch=amd64] http://mirrors.aliyun.com/docker-ce/linux/debian $(lsb_release -cs) stable"
    
    sudo apt-get -y update
    sudo apt-get -y install docker-ce
    
    
    
    
    
    
    
    
    

二、使用国内镜像
--------

修改/etc/docker/daemon.json，添加如下配置：

    {
       "registry-mirrors": ["https://registry.docker-cn.com","http://hub-mirror.c.163.com"]
    }
    

然后执行命令`systemctl restart docker`重启docker

三、测试
----

###### 1.输出version：

    docker --version
    

![在这里插入图片描述](https://img-blog.csdnimg.cn/20190708204047823.png)

###### 2.运行hello-world镜像

    docker run hello-world
    

![在这里插入图片描述](https://img-blog.csdnimg.cn/20190708204240987.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzI5NzUzMjg1,size_16,color_FFFFFF,t_70)

四、参考资料
------

[阿里云：docker安装帮助](https://help.aliyun.com/document_detail/60742.html?spm=5176.11065259.1996646101.searchclickresult.568873406tmss7)  
[docker官方：debian下的docker安装](https://docs.docker.com/install/linux/docker-ce/debian/)