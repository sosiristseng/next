---
title: "Matplotlib figures to tiff images"
subtitle: ""
date: 2021-09-10T17:05:44+08:00
draft: false
author: ""
authorLink: ""
description: ""

tags: [julia, python, visualization, tiff]
categories: [Julia, Python]

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

Exporting pyplot figures to TIFF images with custom dpi and  LZW compression.

```julia
fig.savefig("fig.tif", dpi=300, format="tiff", pil_kwargs=Dict("compression" => "tiff_lzw"))
```

```python
fig.savefig("fig1.tif", dpi=300, format="tiff", pil_kwargs={"compression" : "tiff_lzw"})
```

<!--more-->
