---
title: "闪存盘的修复"
date: 2016-03-11T15:40:44+08:00
lastmod: 2016-03-11T15:40:44+08:00
draft: false
tags: ["硬件"]
categories: ["计算机"]
author: 王亮
weight: 10
contentCopyright: '<a href="https://creativecommons.org/licenses/by-nc-sa/4.0/deed.zh" rel="noopener" target="_blank">CC 4.0</a>'
mathjax: false
---

可能是没有安全卸载造成的。症状是说文件系统是只读文件系统，而且不管怎么加权限都是加不了的。修复命令是

```
sudo fsck -fy /dev/sdb1
```

注意使用前要确保 sdb1 是要修复的闪存盘。
