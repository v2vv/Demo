![](https://csdnimg.cn/release/blogv2/dist/pc/img/original.png)

[qin江](https://me.csdn.net/yangqinjiang) 2018-06-24 16:50:09 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/articleReadEyes.png) 8407 ![](https://csdnimg.cn/release/blogv2/dist/pc/img/tobarCollect.png) 收藏  5 

最后发布:2018-06-24 16:50:09首次发布:2018-06-24 16:50:09

版权声明：本文为博主原创文章，遵循 [CC 4.0 BY-SA](http://creativecommons.org/licenses/by-sa/4.0/) 版权协议，转载请附上原文出处链接和本声明。

1,下载 https://download.docker.com/linux/static/stable/x86\_64/docker-18.03.1-ce.tgz

2,解压, tar xzvf docker-18.03.1-ce.tgz

3,复制二进制文件到/usr/bin目录下

cp docker/\* /usr/bin/  

4,检查是否安装

    docker version

    Client:
     Version:      18.03.1-ce
     API version:  1.37
     Go version:   go1.9.2
     Git commit:   9ee9f40
     Built:        Thu Apr 26 07:12:25 2018
     OS/Arch:      linux/amd64
     Experimental: false
     Orchestrator: swarm
    
    
    Server:
     Engine:
      Version:      18.03.1-ce
      API version:  1.37 (minimum version 1.12)
      Go version:   go1.9.5
      Git commit:   9ee9f40
      Built:        Thu Apr 26 07:23:03 2018
      OS/Arch:      linux/amd64
      Experimental: false

5,配置 docker.service文件

vi /usr/lib/systemd/system/docker.service  

    [Unit]
    Description=Docker Application Container Engine
    Documentation=https://docs.docker.com
    After=network-online.target firewalld.service
    Wants=network-online.target
    
    [Service]
    Type=notify
    ExecStart=/usr/bin/dockerd
    ExecReload=/bin/kill -s HUP $MAINPID
    LimitNOFILE=infinity
    LimitNPROC=infinity
    TimeoutStartSec=0
    Delegate=yes
    KillMode=process
    Restart=on-failure
    StartLimitBurst=3
    StartLimitInterval=60s
    
    [Install]
    WantedBy=multi-user.target
    

6,启动dockerd服务进程

    systemctl daemon-reload
    systemctl start docker.service

7,检验

    
    root      2262  0.1  4.4 472948 44944 ?        Ssl  16:38   0:00 /usr/bin/dockerd
    root      2266  0.2  1.3 277032 13540 ?        Ssl  16:38   0:01 docker-containerd --config /var/run/docker/containerd/containerd.toml
    root      2895  0.0  0.0 112660   972 pts/0    S+   16:48   0:00 grep --color=auto docker
    

    # docker run hello-world
    
    Hello from Docker!
    This message shows that your installation appears to be working correctly.
    
    To generate this message, Docker took the following steps:
     1. The Docker client contacted the Docker daemon.
     2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
        (amd64)
     3. The Docker daemon created a new container from that image which runs the
        executable that produces the output you are currently reading.
     4. The Docker daemon streamed that output to the Docker client, which sent it
        to your terminal.
    
    To try something more ambitious, you can run an Ubuntu container with:
     $ docker run -it ubuntu bash
    
    Share images, automate workflows, and more with a free Docker ID:
     https:
    
    For more examples and ideas, visit:
     https: