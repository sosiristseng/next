---
title: "Tilix"
subtitle: ""
date: 2021-08-20T23:43:36+08:00
draft: false
author: ""
authorLink: ""
description: ""

tags: ["linux", "command line"]
categories: ["Linux", "Applications"]

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

[Tilix](https://gnunn1.github.io/tilix-web/) is an advanced GTK3 tiling terminal emulator.

<!--more-->

## Installation

- apt
  ```bash
  sudo apt install tilix
  [[ -x $(command -v nautilus) ]] && sudo apt install python-nautilus
  ```
- pacman
  ```bash
  sudo pacman -S tilix
  [[ -x $(command -v nautilus) ]] && sudo pacman -S python-nautilus
  ```

## Set `tilix` as the default GUI terminal emulator

- Ubuntu: `sudo update-alternatives --config x-terminal-emulator`
- Arch and derivatives:  Select `tilix` in `Prefered applications`.
