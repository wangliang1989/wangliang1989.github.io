---
title: "重力位——重力学扫盲学习笔记二"
date: 2018-05-25T15:58:00+08:00
draft: false
tags: ["重力"]
categories: ["文献阅读"]
author: 王亮
weight: 10
contentCopyright: '<a href="https://creativecommons.org/licenses/by-nc-sa/4.0/deed.zh" rel="noopener" target="_blank">CC 4.0</a>'
mathjax: true
slug: reading-gravity-normal-gravity-formula
---

# 点质量的引力场和引力位

## 点质量的引力场

点质量 $m_1$ 受到的来自点质量 $m_2$ 的引力为

$$\overrightarrow{f_{12}} = G \frac{m_1m_2}{\left|\overrightarrow{r_1} - \overrightarrow{r_2}\right|^2} \frac{\overrightarrow{r_2} - \overrightarrow{r_1}}{\left|\overrightarrow{r_2} - \overrightarrow{r_1}\right|} = G \frac{m_1m_2}{\left|\overrightarrow{r_2} - \overrightarrow{r_1}\right|^3} (\overrightarrow{r_2} - \overrightarrow{r_1})$$

而引力场为

$$ \overrightarrow{F} = \frac{\overrightarrow{f_{12}}}{m_1}$$

两个式子联立

$$\overrightarrow{F}  = G \frac{m_2}{\left|\overrightarrow{r_2} - \overrightarrow{r_1}\right|^3} (\overrightarrow{r_2} - \overrightarrow{r_1})$$

发现角标m2没有意义：

$$\vec{F}(\vec{r}) = G \frac{m}{\left|\overrightarrow{r_s} - \overrightarrow{r}\right|^3} (\overrightarrow{r_s} - \overrightarrow{r})$$

## 点质量的引力位

单位点质量在点质量 $m$ 的引力场中从A移动到B的过程中，点质量 $m$ 的引力做的功为$W_A^B$：

$$W_A^B = \int_L\overrightarrow{F}d\vec{l} = \int_L\left|\overrightarrow{F}\right|\left|d\vec{l}\right|cos(\overrightarrow{F},d\vec{l}) = \int_L\frac{GM}{r^2}\left|d\vec{l}\right| = \frac{GM}{\left|\overrightarrow{r_B}\right|} -  \frac{GM}{\left|\overrightarrow{r_A}\right|} = GM(\frac{1}{\left|\overrightarrow{r_B}\right|} -  \frac{1}{\left|\overrightarrow{r_A}\right|})$$

所以，引力位函数就是

$$W_\infty^B = \frac{GM}{\left|\overrightarrow{r_B}\right|} = V(\overrightarrow{r_B})$$

由此得到引力位的定义：单位点质量从无穷远处运动到观察点上的过程中引力场所做的功:

$$V(\overrightarrow{r}) = \frac{GM}{\left|\overrightarrow{r_s} - \overrightarrow{r}\right|}$$

# 离心力位

重力位是重力场的位，离心力位就是离心力场的位：

$$\overrightarrow{Q} = -r\omega^2$$

# 重力位

重力位是地球引力位与惯性离心力位之和。

$$W = V + Q$$

重力等位面：令 $W=常数$，可以得到一个封闭的曲面，该曲面就是一个重力等位面。

大地水准面：与平均海平面重合的地球重力场等位面。在陆地区域，大地水准面是平均海平面的顺势延伸。
一般说，大地水准面就是固体地球的物理形状。
