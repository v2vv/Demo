![](https://csdnimg.cn/release/blogv2/dist/pc/img/original.png)

[情話微甜](https://me.csdn.net/qq_41157588) 2020-09-30 19:55:12 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/articleReadEyes.png) 216 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/tobarCollect.png) 收藏 

最后发布:2020-09-30 19:55:12首次发布:2020-09-30 19:55:12

版权声明：本文为博主原创文章，遵循 [CC 4.0 BY-SA](http://creativecommons.org/licenses/by-sa/4.0/) 版权协议，转载请附上原文出处链接和本声明。

错误问题
----

今天我在linux系统使用docker启动mysql服务时，突然报如下的错误，翻译过来大致意思就是 端口被占用。  
在出现问题时在网上也是翻阅了资料，说是重启docker即可，但是反复重启，仍不见解决问题，通过查看占用端口、杀死进程方案得以解决问题。  
**错误问题如下**  
docker: Error response from daemon: driver failed programming external connectivity on endpoint mysql5.6.46 (8c10cf68a1196a3a4b62faf37e36a4823bcfe2b353d9881a78c06314c1487fc6): Error starting userland proxy: listen tcp 0.0.0.0:3306: bind: address already in use.  
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200930194813679.png#pic_center)

解决方案
----

查看当前占用端口命令

    netstat -tanlp
    

杀死进程(注意不是杀死端口，而是pid的端口)，如下图参考

    kill xxx进程 
    

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200930194913373.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxMTU3NTg4,size_16,color_FFFFFF,t_70#pic_center)

至此，再次运行图1的命令，问题得以解决，不在报错。  
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200930195230832.png#pic_center)

如帮助到您的问题，请点个赞支持一下作者哦，感谢~