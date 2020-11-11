![](https://csdnimg.cn/release/blogv2/dist/pc/img/original.png)

[zihui\_xu](https://me.csdn.net/bronzehammer) 2019-02-14 09:34:27 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/articleReadEyes.png) 14255 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/tobarCollect.png) 收藏  9 

最后发布:2019-02-14 09:34:27首次发布:2019-02-14 09:34:27

> Ubuntu 16.04环境

查看Linux所有服务的运行状态可输入命令

    service --status-all
    

> 注意：-all要紧跟在–status后面，中间不要有空格

结果

![在这里插入图片描述](https://img-blog.csdnimg.cn/20190214092815179.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2Jyb256ZWhhbW1lcg==,size_16,color_FFFFFF,t_70)

那么，服务名称前面的加减号 \[+\] \[-\] 是什么意思呢？

\[+\] 代表服务是在启动运行的状态  
\[-\] 代表服务是在关闭停止的状态

我们来做个验证，以apache2服务为例。

现在的 apache2 是 \[+\] 的状态，即正在启动运行中，我们来停止这个服务

    service apache2 stop
    

我们再次查看所有服务的运行状态发现，apache2 的状态变为 \[-\]

![在这里插入图片描述](https://img-blog.csdnimg.cn/20190214093332437.png)