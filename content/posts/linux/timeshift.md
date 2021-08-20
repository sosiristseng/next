---
title: "Timeshift"
subtitle: ""
date: 2021-06-18T23:41:56+08:00
draft: false
author: ""
authorLink: ""
description: ""

tags: [linux, apps, timeshift]
categories: [Linux, Applications]

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

[Timeshift](https://github.com/teejee2008/timeshift) is a system backup and restore manager using `rsync` or `btrfs` snapshots.
<!--more-->

## Installation

- Via `apt`
  ```bash
  sudo apt install timeshift
  ```
- Via [AUR](https://aur.archlinux.org/packages/timeshift/)
  ```bash
  paru -S timeshift cronie
  # You may need this to enable scheduled backup
  sudo systemctl enable --now cronie.service
  ```
