![](https://csdnimg.cn/release/blogv2/dist/pc/img/original.png)

[IT云清](https://me.csdn.net/weixin_39800144) 2018-07-01 10:40:00 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/articleReadEyes.png) 27800 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/tobarCollect.png) 收藏  13 

最后发布:2018-07-01 10:40:00首次发布:2018-07-01 10:40:00

版权声明：本文为博主原创文章，遵循 [CC 4.0 BY-SA](http://creativecommons.org/licenses/by-sa/4.0/) 版权协议，转载请附上原文出处链接和本声明。

[先启动mysql服务](https://blog.csdn.net/weixin_39800144/article/details/78817278)，启动mysql后，如果想进入mysql的命令行，执行如下命令

    [root@izbp163wlhi02tcaxyuxb7z ~]# docker exec -it mysql1 bash 
    
    root@654c15160c66:/# mysql -uroot -p
    Enter password: 
    
    Welcome to the MySQL monitor.  Commands end with ; or \g.
    Your MySQL connection id is 9
    Server version: 8.0.11 MySQL Community Server - GPL
    
    Oracle is a registered trademark of Oracle Corporation and/or its
    affiliates. Other names may be trademarks of their respective
    owners.
    
    Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.
    
    mysql>