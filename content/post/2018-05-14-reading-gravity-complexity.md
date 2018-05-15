---
title: "复杂的地球重力场——重力学扫盲学习笔记一"
date: 2018-05-14T20:21:00+08:00
draft: false
tags: ["重力"]
categories: ["文献阅读"]
author: 王亮
weight: 10
contentCopyright: '<a href="https://creativecommons.org/licenses/by-nc-sa/4.0/deed.zh" rel="noopener" target="_blank">CC 4.0</a>'
mathjax: true
slug: reading-gravity-complexity
---

从这个星期开始，文献阅读板块将连载重力学和固体潮的一些基础知识。我的重力学学得很不好。
现在读博士，遇到了上课很认真的老师，学到了一些知识，对重力学梗概有了一定了解。

# 牛顿力学中的非惯性系

考虑到一些同学可能把牛顿忘了，所以复习一下高中牛顿力学。
牛顿力学原本只能用于惯性系，即参考系必须做匀速直线运动或者静止。
如果参考系不是做匀速直线运动或者静止，即非惯性系，所有物体在进行牛顿力学分析时必须加上一个惯性力：

$$F=-ma$$

非惯性系是牛顿力学的漏洞，用不存在的惯性力把这个洞临时补上。相对论最终解决了这个问题。

# 重力和重力场

在中学阶段，地球上物体所受的重力的公式是这样的：

$$mg = G\frac{m_1m_2}{r^2} - m\frac{v^2}{r}$$

这个公式忽略掉了太阳、月球的万有引力，并且认为地球是静止不动的，地球上的物体的运动仅仅是随着地球自转。
如果在重力学中，继续承认这些假设，那固体潮什么的就不存在了。
所以我们得出重力学中重力的严格定义:
重力是地球表面观察者受到的所有天体引力之和，去除维持观察者在宇宙中做变加速运动所需分力以后剩余的部分：

$$\overrightarrow{G}(\overrightarrow{r},t) = \overrightarrow{F_S}(\overrightarrow{r},t) + \overrightarrow{F_L}(\overrightarrow{r},t) + \overrightarrow{F_E}(\overrightarrow{r},t) - \overrightarrow{C}(\overrightarrow{r},t)$$

$\overrightarrow{F_S}(\overrightarrow{r},t))$ 是太阳引力，
$\overrightarrow{F_L}(\overrightarrow{r},t)$ 是月球引力，
$\overrightarrow{F_E}(\overrightarrow{r},t))$ 是地球引力，
$\overrightarrow{C}(\overrightarrow{r},t)$ 是向心力。

地球上的物体所做的运动是非常复杂的。首先，地球上的物体随着地球在自转，和围绕太阳公转。
然后，还因为固体潮的原因，地球的表面还会有起伏。
不过，在刚刚开始的时候，使用简化定义。
简化定义为：忽略地外天体的作用，地球重力场可以定义为地球引力和观察者围绕地球做自由圆周运动所需向心力（惯性离心力）之差（之和）。
此时，重力仅仅是空间的函数。

重力场是单位质量受到的重力。重力单位是加速度单位。在 SI 单位制中是 $m/s^2$。在厘米克秒 cgs 单位制中是 $cm/s^2$，称为伽利略 $Gal$。
另外，$1mGal = 10^{-5} m/s^2$。国际重力单位为 $gu=10^{-6}m/s^2$。
