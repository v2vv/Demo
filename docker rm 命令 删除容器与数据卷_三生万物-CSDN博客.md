![](https://csdnimg.cn/release/blogv2/dist/pc/img/original.png)

[唯重](https://me.csdn.net/GMingZhou) 2017-12-05 09:27:12 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/articleReadEyes.png) 12210 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/tobarCollect.png) 收藏  1 

最后发布:2017-12-05 09:27:12首次发布:2017-12-05 09:27:12

版权声明：本文为博主原创文章，遵循 [CC 4.0 BY-SA](http://creativecommons.org/licenses/by-sa/4.0/) 版权协议，转载请附上原文出处链接和本声明。

###### 宽为限 紧用功 功夫到 滞塞通

**删除前必须先停止容器**

    docker stop XXX
    docker rm XXX

_XXX可以是容器的NAMES 也可以是CONTAINER ID_

**当然也可以加参数 -f 不停止，强行删除！**

**数据删除有风险！**

    docker rm $(docker ps -aq)

**加参数 -n 可以匹配前n个创建的容器，参数 -l 删除指定的链接**

数据卷是被设计用来持久化数据的，它的生命周期独立于容器，**Docker不会在容器被删除后自动删除数据卷，并且也不存在垃圾回收这样的机制来处理没有任何容器引用的数据卷。**如果需要在删除容器的同时移除数据卷。

可以在删除容器的时候使用 **docker rm -v** 这个参数。

删除容器与数据卷
--------

**停止容器**

    docker stop XXX

**\-v 参数用于删除数据卷**

    docker rm -v XXX

    docker rm --help
    Usage:    docker rm [OPTIONS] CONTAINER [CONTAINER...] 
    
    Remove one or more containers 
      -f, --force        Force the removal of a running container (uses SIGKILL) 
      --help             Print usage 
      -l, --link         Remove the specified link 
      -v, --volumes      Remove the volumes associated with the container