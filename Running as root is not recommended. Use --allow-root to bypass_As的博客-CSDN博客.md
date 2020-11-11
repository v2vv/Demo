![](https://csdnimg.cn/release/blogv2/dist/pc/img/original.png)

[小小蒲公英](https://me.csdn.net/weixin_39777626) 2018-05-19 09:33:47 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/articleReadEyes.png) 11803 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/tobarCollect.png) 收藏  6 

版权声明：本文为博主原创文章，遵循 [CC 4.0 BY-SA](http://creativecommons.org/licenses/by-sa/4.0/) 版权协议，转载请附上原文出处链接和本声明。

首先输入，查看配置文件位置

    [as-pc as]
    
    Overwrite /root/.jupyter/jupyter_notebook_config.py with default config? [y/N]y
    Writing default config to: /root/.jupyter/jupyter_notebook_config.py

接下来打开配置文件

    gedit /root/.jupyter/jupyter_notebook_config.py

找到这一行

    #c.NotebookApp.allow_root = False  

去掉#，并修改成True即可解决root权限运行的问题

    c.NotebookApp.allow_root =True

保存，重新运行程序

    jupyter notebook

**设置访问密码**  
打开 ipython 输入

    from notebook.auth import passwd
    passwd()

然后根据提示输入2次密码  
Enter password: ········  
Verify password: ········  
![这里写图片描述](https://img-blog.csdn.net/20180808161818638?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zOTc3NzYyNg==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)  
然后复制 **‘sha1:f5643\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\***’ 粘贴至配置文件（记得去掉 **#**）

    c.NotebookApp.password = u'sha1:f5*****************************'

更多设置如下

    c.NotebookApp.ip = 'localhost'
    c.NotebookApp.open_browser = True（True：启动时自动打开浏览器，False：需手动打开浏览器访问http:
    c.NotebookApp.port = 8888（端口设置）