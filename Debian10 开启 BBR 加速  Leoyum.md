Debian10 开启 BBR 加速

*   分类：Linux
*   发表：2020-02-27
*   围观(3,323)
*   [评论(0)](https://leoyum.com/501.html#comments)

TCP 拥塞控制算法 BBR (Bottleneck Bandwidth and RTT) 可以大限度地利用服务器带宽，减少排队的情况，提高网络质量。

Debian10 默认的内核就是 4.19 版本的内核而且编译了 TCP BBR 模块，所以可以直接通过参数开启。

![](http://tu.leoyum.com/IMG/vOud.png)

### 开启方法：

> echo net.core.default\_qdisc=fq >> /etc/sysctl.conf
> 
> echo net.ipv4.tcp\_congestion\_control=bbr >> /etc/sysctl.conf
> 
> sysctl -p

### 检查是否成功：

> sysctl net.ipv4.tcp\_available\_congestion\_control

显示：

> sysctl net.ipv4.tcp\_available\_congestion\_control  
> net.ipv4.tcp\_available\_congestion\_control = bbr cubic reno

表示开启成功。

或执行 lsmod | grep bbr ，检测 BBR 是否开启。