---
title: "Telegram"
subtitle: ""
date: 2021-08-20T22:53:01+08:00
draft: false
author: ""
authorLink: ""
description: ""

tags: ["linux", "telegram"]
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

Install the official desktop client for the [Telegram messenger](https://telegram.org).

<!--more-->

- [official binaries](https://telegram.org)
- [snap](https://snapcraft.io/telegram-desktop)
  ```bash
  sudo snap install telegram-desktop
  ```
- [chocolatey](https://community.chocolatey.org/packages/telegram)
  ```bash
  choco install telegram
  ```
- [PPA for Ubuntu](https://launchpad.net/~atareao/+archive/ubuntu/telegram)
  ```bash
  sudo add-apt-repository -y ppa:atareao/telegram
  sudo apt update && sudo apt install telegram
  ```
- `pacman`
  ```bash
  sudo pacman -S telegram-desktop
  ```
