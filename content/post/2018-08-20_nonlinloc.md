---
title: "Nonlinloc Viewer 安装教程"
date: 2018-08-20T16:56:00+08:00
lastmod: 2018-08-20T16:56:00+08:00
draft: false
tags: ["绘图"]
categories: ["地震学软件"]
author: 王亮
weight: 10
contentCopyright: '<a href="https://creativecommons.org/licenses/by-nc-sa/4.0/deed.zh" rel="noopener" target="_blank">CC 4.0</a>'
mathjax: false
slug: nonlinloc
---

Nonlinloc 是一个基于到时的绝对定位程序，配套了一个 3D 绘图软件 SeismicityViewer。
只可惜读入的文件必须是 hypo 格式，单纯用于绘图太复杂了。这里先说明 SeismicityViewer 如何安装。

# 下载文件

地址： http://alomax.net/seismicity/SeismicityViewer.html

SeismicityViewer31.jar - 程序本身
vinti.hyp - NonLinLoc Hypocenter-Phase file
vinti.hdr - NonLinLoc Grid Header file
vinti.cont.xyz - topography 3D line file
vinti.text - 3D text file

# 添加环境变量

```bash
export CLASSPATH=/to-path/SeismicityViewer50.jar
```

环境变量要加上程序文件本身，这是比较特殊的。

# 运行程序

在那堆 vinti 文件的地方执行：

```bash
java net.alomax.seismicity.Seismicity vinti.hyp
```
