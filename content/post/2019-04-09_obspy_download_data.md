---
title: "Obspy 下载数据"
date: 2019-04-09T12:44:00+08:00
lastmod: 2019-04-09T12:44:00+08:00
draft: false
tags: ["波形数据"]
categories: ["数据获取"]
author: 王亮
weight: 10
contentCopyright: '<a href="https://creativecommons.org/licenses/by-nc-sa/4.0/deed.zh" rel="noopener" target="_blank">CC 4.0</a>'
mathjax: true
slug: obspy_download_data
---

Obspy 可以用于下载波形数据，主要优势在于自动支持「所有」数据中心。

# 准备安装环境

首先，需要安装 anaconda，可以参考

https://blog.seisman.info/anaconda/

# 开始安装

```bash
conda config --add channels conda-forge
conda create -n obspy python=3.7   # 为 obspy 配置专门的 python 环境
conda activate obspy
conda install obspy
```
正确情况下，这就安装好了。

# 下载数据

参照官方例子：

https://docs.obspy.org/packages/autogen/obspy.clients.fdsn.mass_downloader.html
