---
title: "Matplotlib: Sharing the Legend Box in Twin Axes"
subtitle: ""
date: 2021-09-10T17:08:41+08:00
draft: false
author: ""
authorLink: ""
description: ""

tags: [julia, python, visualization]
categories: [Python, Julia]

hiddenFromHomePage: false
hiddenFromSearch: false

featuredImage: ""
featuredImagePreview: ""

toc:
  enable: true
math:
  enable: false
lightgallery: false
---

- Capture line plot objects from both axes.
- Call `legend()` for both(all) line plot objects.

<!--more-->

```julia
x1 = 1:10

import PyPlot as plt

fig, ax1 = plt.subplots()

l1 = ax1.plot(x1, x1)

ax2 = ax1.twinx()
l2= ax2.plot(x1, exp.(x1))

ax1.legend([first(l1), first(l2)], ["x", "exp(x)"])
```
