---
title: "用 JWEED 和 QQ 邮箱发送 BREQ_FAST 邮件"
date: 2015-10-30T16:18:08+08:00
lastmod: 2015-10-30T16:18:08+08:00
draft: false
tags: ["jweed"]
categories: ["数据获取"]
author: 王亮
weight: 10
contentCopyright: '<a href="https://creativecommons.org/licenses/by-nc-sa/4.0/deed.zh" rel="noopener" target="_blank">CC 4.0</a>'
mathjax: false
---

BREQ_FAST 是 通过发送特定格式的邮件到指定的邮箱来申请数据。JWEED 可以生成该特定格式的邮件。

本文将以我组申请01年和02年两年，在东经85度到89度，北纬25度到30度范围内宽频高增益地震仪的连续波形数据
为例子展示如何用 JWEED 生成邮件内容，然后用 QQ 邮箱向 IRIS 发信申请数据。

JWEED的安装：

<http://ds.iris.edu/pub/programs/install_anywhere/JWEED-current/Default_Configuration/Web_Installers/install.htm>

# 使用 JWEED 生成邮件内容

启动 JWEED，点击 Events/Stations 选项卡。窗口中，你可以看到一张世界地区。

点击 Query Options 菜单中的Start/End time，设定起止时间。

![pic](/media/2015102901.png)

点击 Station Query Options设定台站参数。

![pic](/media/2015102902.png)

点击 Map Options 菜单中的 Enter Lat/lon, Points
设定区域范围，然后点击Map it。

![pic](/media/2015102903.png)

至此，台站的时空约束等条件就设定完了。点击 Query for stations 按钮搜寻台站。如果没有台站可能是确实没有台站。

如果正常地找到了台站，就点击 Get data 菜单里的 Breq_fast。即可打开发信的 Email Request Pane选项卡。
选项卡由三部分组成： Enter Request Info 、Mail To 和 Messages.

![pic](/media/2015102904.png)

在 Enter Request Info 部分：

Name： IRIS 给你发数据时会用这个 Name 作为名字建立一个 ftp 目录。到时，你去这个 ftp 目录下载。
如果这个名字和别人的一样，那么你的数据就会和别人的放在一个目录。所以请取一个不会重复的名字。

Email： IRIS 会向这个 Email 发送回信，告知数据分发的进度(关于回信，后面还会有说明)。
请填写你能收信的正确 Email 地址。

seed label： 决定 seed 文件的名字。
图中所示意味着 seed 文件名会是 2001.9.17.iris.3839939.seed
(其中3839939是IRIS随即产生的数字，只有拿到数据后才会知道)。

Phone#：在此处留下你的电话号码。
现在就业这么困难，IRIS 看你是个勤勉的人，打电话叫你去上班也说不定啊。

Mail To 部分有两行：Net DC 和 breq_fast。我们只用 breq_fast 一行。

像图里一样，选中 IRIS：点击右边的 send 按钮，就会直接向 IRIS 发邮件，
不过绝大多数时候都不行，比如在做这次演示时，我运气就不好
(在 Messages 的文本框中显示了 Email error 报错信息)。
或者
点击 Save to disk(breq_fast) 保存邮件内容到文件，然后按下面的步骤用QQ邮箱发信。

# 用QQ邮箱发信

关键在于，发出去的邮件一定是纯文本格式，不要富文本格式:

![pic](/media/2015102905.png)

#. 收信地址是 breq_fast@iris.washington.edu 。
#. 主题随意。
#. 先把正文文本框下的其他选项中的纯文本复选框选中。再把邮件内容复制进去。

最后，发出邮件即可。

# 关于回信

无论数据申请是否成功，IRIS 会回两封信，第一封的主题是 IRIS received your data reques(s)……。

第二封的主题如果是 Your request for …… is ready to pick up 。这就说明数据已经申请成功，信中会有如何下载的说明。
如果主题是IRIS data request notify - no data……，那就是数据申请失败了。

回信的地址不是你发邮件的邮箱地址，而是你在 Enter Request Info 中填写的地址。

关于异常情况。
很久都收不到第一封邮件：IRIS网站可能发生了故障，等一两天。
JWEED找不到台站，但是按理应该是有的：JWEED 的 bug 很多，把 JWEED 关闭，重启再试。
