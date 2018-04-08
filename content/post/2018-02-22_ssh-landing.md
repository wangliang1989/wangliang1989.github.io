---
title: "假期在家 SSH 登陆学校电脑"
date: 2018-02-22T21:30:00+08:00
lastmod: 2018-02-22T21:30:00+08:00
draft: false
tags: ["服务器"]
categories: ["计算机"]
author: 王亮
weight: 10
contentCopyright: '<a href="https://creativecommons.org/licenses/by-nc-sa/4.0/deed.zh" rel="noopener" target="_blank">CC 4.0</a>'
mathjax: false
---

假期在家想 SSH 登陆学校的电脑，有如下障碍：无公网 IP、学校断网和学校断电。

# 用端口转发解决没有公网 IP 的问题

互联网最基本的结构性质就是其非对称性。当你的服务器不具有公网 IP 的时候，服务端必须在同一个局域网内才能实现 SSH 登陆。
这就好比北京的电话相互拨打不需要输入区号的，但是如果要给上海打就需要区号了。公网 IP 在国内是非常稀缺的互联网资源，学校是不会给学生的（听说中科大给）。
可以使用「端口转发」来进行中转，以回避这个问题。

## 购买和配置 NATAPP 服务

我用的端口转发服务是 NATAPP，国内的，速度稳定性有保障，完全合法。我建议购买 VIP_1 型，实惠够用。

隧道本身的配置见 NATAPP 的官方文档即可（**配置时注意本地端口改为 22**）。
在 /etc/rc.local 中加入以下内容：

```bash
nohup /usr/local/natapp -authtoken=abc123 -log=stdout &# 开机启动 NATAPP
```

# 学校断网和断电

因为各种原因，学校可能会断网和断电，下面罗列了一些方法以便在网络和电力恢复后能重新登陆。

## 定时和来电开机

目前，多数 PC 计算机可以通过设置 BIOS 实现定时开机和断电后来电开机。

## 重新登陆校园网

断电后，断网后肯定是需要重新校园网登陆的。桂工和成理用的是 drcom 网页登陆。
首先需要抓取 HTTP POST 请求，看看认证过程中究竟给认证服务器发送了什么内容。
Chrome 浏览器打开认证页面，右键选择「检查」，打开开发者工具， 选择 network，勾选 Preserve log。
在登录页面填写帐号信息，点击登录， 即可看到相关的 HTTP 请求。
在 ALL 中找到 Request Method 为 POST 的那个，右键->Copy-> Copy as cURL，即可得到认证所需的 curl 命令。
使用该命令即可进行登录认证。

在 /etc/rc.local 中加入以下内容：

```bash
nohup /home/peterpan/ping -log=stdout &
# 开机启动脚 ping，千万别忘了文件 ping 要给予可执行权限，这条语句要在启动 NATAPP 那条之前
```
ping 的内容如下

```perl
#!/usr/bin/env perl
use strict;
use warnings;
while () {
    system "sh /home/peterpan/curl";# 登陆校园网，文件 curl 的内容是上面得到的 curl 命令
    for (my $i = 0;$i <= 20;$i++) {
        system "ping www.natapp.cn -c 5";# 间隔 300 秒 ping 5 次防止掉线
        sleep(300);
    }
    system "service networking restart";# 间隔 6000 秒无论怎样重启一次网络服务
}
```

# 参考

https://butui.me/post/use-curl-for-drcom-webauth/
