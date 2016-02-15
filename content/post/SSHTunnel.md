+++
categories = ["Linux"]
date = "2016-02-05T08:16:41+08:00"
description = "how to use ssh tunnel"
keywords = ["SSH Tunnel"]
title = "SSH Tunnel"

+++


本地想要访问远端但是从本地建立连接
ssh -L 8000:remote_addr1:3000 username@remote_addr2

将本地的8000的所有数据通过remote_addr2发送到remote_addr1的3000端口，让访问本地8000端口和访问remote_addr1的3000是一样的

但是在这次实际应用中由于服务run在深圳深圳本地可以访问3000，我们的cache server并不能访问他们的3000端口所以第一步就是将他们的localhost的3000映射到cache server上

使用 ssh -R 9000:server_addr:3000 cachename@cacheip

这条命令是指将cache上的9000端口的所有数据经由运行本条命令的机器转发给server_addr的3000

因为当时的场景就是运行这条命令的机器就是运行服务的机器所以命令是 ssh -R 9000:localhost:3000 cachename@cacheip

如果在别的可以访问server的机器上运行就是 ssh -R 9000:server_ip:3000 cache@cacheip

本次场景也可以在cache上运行ssh -L 9000:localhost:3000 cachename@cacheip

转发的其他
-f 表示后台运行要停止只能kill

-N 表示不打开shell -T 表示不分配tty -NT 表示只是连接头并不在cache上操作

还有就是两端要修改 /etc/ssh/sshd_config 文件 将AllowTcpForwarding yes 写入

如果两端还是不通可以考虑两次tunnel，取一个中介server。
