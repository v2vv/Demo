![](https://csdnimg.cn/release/blogv2/dist/pc/img/original.png)

[土豆赛叩](https://me.csdn.net/Vblegend_2013) 2019-01-03 10:41:36 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/articleReadEyes.png) 2586 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/tobarCollect.png) 收藏  1 

最后发布:2019-01-03 10:41:36首次发布:2019-01-03 10:41:36

版权声明：本文为博主原创文章，遵循 [CC 4.0 BY-SA](http://creativecommons.org/licenses/by-sa/4.0/) 版权协议，转载请附上原文出处链接和本声明。

1.运行 **lsb\_release -cs 查看发行版名称**

**我这是 stretch**

![](https://img-blog.csdnimg.cn/20190103103503587.png)

**进入到下载包页面 [https://download.docker.com/linux/](https://download.docker.com/linux/)**

**依次进入**/[debian/dists/**stretch**/pool/stable/**amd64**/](https://download.docker.com/linux/debian/dists/stretch/pool/stable/amd64/) 加粗部分根据你的系统选择

注意：这里有三个包 docker-ce 18.09.0 是程序安装包，但是安装它需要上面两个依赖包，一块下载了

![](https://img-blog.csdnimg.cn/20190103103735524.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1ZibGVnZW5kXzIwMTM=,size_16,color_FFFFFF,t_70)

wget 下载到root目录 或者用sftp上传到root目录

cd进入root目录

然后 dpkg -i  containerd.io.此处省略1000字.deb

然后 dpkg -i  docker-ce-cli.此处省略1000字.deb

然后 dpkg -i  docker-ce.此处省略1000字.deb

docker -version

![](https://img-blog.csdnimg.cn/20190103104120277.png)