---
title: "Pyplot.jl Tips"
subtitle: ""
date: 2021-06-19T13:07:26+08:00
draft: false
author: ""
authorLink: ""
description: ""

tags: [julia, visualization, tiff]
categories: [Julia]

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

Some tips about [PyPlot.jl](http://juliaplots.org), the `matplotlib` (Python) visulization library for Julia.

<!--more-->

## Dealing with installation errors

Since `PyPlot.jl` depends on the Python package `matplotlib`, sometimes simply `]add` the package will not work due to some quirks in the installation process.

It is recommended to have a clean [Conda environment inside Julia](https://github.com/JuliaPy/Conda.jl) to minimize installation issues.

To enforce a local miniconda environment inside Julia, set the `PYTHON` environment variable to an empty string.

`.julia/config/startup/.jl`

```julia
ENV["PYTHON"]=""
```

Rebuild related packages.

```julia
import Pkg
Pkg.build(["PyCall", "Conda", "PyPlot"])

# Test
using PyPlot
```

## Tweaking default options

Changing [mplstyle and rcparams](https://matplotlib.org/stable/tutorials/introductory/customizing.html) in `matplotlib`.

### Python

```py
import matplotlib as mpl
mpl.rcParams['font.sans-serif'] = "Arial"
mpl.rcParams['font.family'] = "sans-serif"
mpl.rcParams['font.size'] = 12
```

### Julia

For `PyPlot.jl`

```julia
import PyPlot as plt
rcParams = plt.PyDict(plt.matplotlib."rcParams")
rcParams['font.sans-serif'] = "Arial"
rcParams['font.family'] = "sans-serif"
rcParams["font.size"] = 12
```

For `Plots.jl`, there is an internal `pyrcparams` dictionary for `pyplot`(`matplotlib`) backend.

```julia
using Plots
Plots.pyplot()
Plots.pyrcparams["font.size"] = 12
Plots.pyrcparams["font.sans-serif"] = "Arial"
Plots.pyrcparams["font.family"] = "sans-serif"
```

### Source

1. [Yasser Khan's post](https://web.stanford.edu/~ymkhan/blog/2015/matplotlib_change_default_font/)
1. [mplstyle and rcparams](https://matplotlib.org/stable/tutorials/introductory/customizing.html) for matplotlib
2. [PyPlot.jl](https://github.com/JuliaPy/PyPlot.jl) readme
3. [mplstyle and rcparams](https://matplotlib.org/stable/tutorials/introductory/customizing.html) in `matplotlib` docs.
