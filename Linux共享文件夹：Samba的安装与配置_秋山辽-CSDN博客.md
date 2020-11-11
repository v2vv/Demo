![](https://csdnimg.cn/release/blogv2/dist/pc/img/original.png)

[Macrocell](https://me.csdn.net/sinat_37367944) 2019-03-27 17:11:18 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/articleReadEyes.png) 1030 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/tobarCollect.png) 收藏  3 

最后发布:2019-03-27 17:11:18首次发布:2019-03-27 17:11:18

版权声明：本文为博主原创文章，遵循 [CC 4.0 BY-SA](http://creativecommons.org/licenses/by-sa/4.0/) 版权协议，转载请附上原文出处链接和本声明。

我们知道Windows系统之间可以通过共享文件夹实现文件共享访问。那么Linux系统如何共享文件给Windows系统？比较常用的就是通过Samba软件包实现。  
如何在Linux系统上安装和配置Samba？网上有很多版本，试了很多次就是不成功，以下给出的方法亲测有效，在此把每一步写清楚，方便以后自己查看。

(1) 安装Samba软件包

    sudo apt-get install samba samba-common
    

(2) 修改Samba配置文件: `/etc/samba/smb.conf`

    sudo gedit /etc/samba/smb.conf			
    

在文件的结尾加上一段配置：

    [Share]						
    	comment = Shared Folder			
    	path = /home/yhw			
    	public = yes				
    	writable = yes				
    	available = yes				
    	browseable = yes			
    

(3) 创建要分享的目录，并设置目录权限

    mkdir /home/yhw					
    chmod 777 /home/yhw
    

(4) 将系统中已有的系统用户添加为Samba用户，并设置Samba访问密码

    sudo useradd username		  		
    sudo smbpasswd -a username			
    

(5) 重启Samba服务

    sudo service smbd restart			
    

(6) Windows访问设置好的共享文件夹

在Windows资源管理器地址栏输入Linux主机的IP：`\\192.168.1.13` 就可以看到刚刚在Linux系统设置的Share共享文件夹，如下图：  
![在这里插入图片描述](https://img-blog.csdnimg.cn/20181031204755284.gif)