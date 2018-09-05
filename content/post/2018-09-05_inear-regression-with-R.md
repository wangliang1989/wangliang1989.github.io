---
title: "用 R 语言进行线性回归"
date: 2018-09-06T00:37:00+08:00
lastmod: 2018-09-06T00:37:00+08:00
draft: false
tags: ["数理统计"]
categories: ["地震学软件"]
author: 王亮
weight: 10
contentCopyright: '<a href="https://creativecommons.org/licenses/by-nc-sa/4.0/deed.zh" rel="noopener" target="_blank">CC 4.0</a>'
mathjax: false
slug: inear-regression-with-R
---

R 语言是知名的统计软件，也可以做一些其他事情。
R 因为高度适应统计，所以是一门很高的语言，比 Matlab 还要高，比如有称为数据框的数据形式。

# 安装

https://www.r-project.org/

# 例子

数据是这样：

````text
M lgN
5 1.398
5.1 1.322
5.2 1.204
5.3 1.146
5.4 1.114
5.5 0.778
5.6 0.699
5.7 0.699
5.8 0.477
5.9 0.000
6.0 0.000
6.1 0.000
````

代码：
````bash
#! /usr/bin/env Rscript
grdata <- read.table("gr.txt", header=TRUE)
m <- lm(lgN~M,data=grdata)
plot(grdata)
abline(m)
m
summary(m)
````

第一行是读入数据，read.table 就是表示读入一个数据框，括弧内依次是指出文件名和表示有 header。
header 就是数据里的 M 和 lgN。没错！R 语言中的所谓的数据框中两列数据，每列数据可以指定它的名字，这就是高度适配统计的一个体现。

第二行是进行线性回归，回归的结果保存到 m 中。

第三行是把输入的数据框数据画图，画散点图。

第四行是画最佳拟合回归线。

第五行是输出回归结果。

第六行是给出重要的统计量（比如残差标准差）。
