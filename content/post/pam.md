+++
categories = ["Linux"]
date = "2016-02-05T08:13:09+08:00"
description = "How to use pam with busybox in boot2docker"
keywords = ["busybox","pam"]
title = "change busybox login with pam in boot2docker"

+++

* install pam

  * 使用tcz安装pam包 linux-pam.tcz即可

    * so使用的是/usr/local/lib/security/

    * pam.d使用的是/etc/pam.d/other

  * 所以需要装两次即cd两次后复制到/下面和直接复制到/下面

* 配置 pam 编辑 /etc/pam.d/other

  *   auth            sufficient      pam_unix.so

  *   auth            sufficient      mypam.so

* 自定义so

  * 编译自己的so 即mypam.so

  * 将so放置到相应的位置，即/usr/local/lib/security/

* 编译自己的busybox，打开pam支持

* 重置login链接到新的busybox

##### 注意事项

* 自定义的逻辑如果有涉及用户，则需要该用户存在。
