---
title: "使用网格线做绘图调整"
date: 2018-07-14T11:10:00+08:00
lastmod: 2018-07-14T11:10:00+08:00
draft: false
tags: ["技巧"]
categories: ["GMT"]
author: 王亮
weight: 10
contentCopyright: '<a href="https://creativecommons.org/licenses/by-nc-sa/4.0/deed.zh" rel="noopener" target="_blank">CC 4.0</a>'
mathjax: false
slug: gmt-gridlines
---

绘制出网格线可以实现快速调整绘图元素的位置。

# 单一底图内的情形

如果绘图元素在单一底图内，可以加入如下命令绘出网格线，就可以知道地图上各个点的位置，就能快速移动目标了。

```bash
gmt psbasemap -R -J -Ba1g1 -BWSEN  -P -K -O >> $file
```

# 多个底图的情形

如果元素横跨多个底图，则需要引入辅助底图：

```bash
# 绘制辅助底图
gmt gmtset MAP_FRAME_TYPE=inside MAP_GRID_PEN_PRIMARY=1p,blue
gmt psbasemap -R0/21/0/29.7 -Jx1/1 -Ba1g1 -BWSEN -Xf0c -Yf0c -P -K -O >> $file;
```
