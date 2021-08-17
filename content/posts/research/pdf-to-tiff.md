---
title: "Convert PDF files to TIFF image"
subtitle: ""
date: 2021-06-19T13:35:47+08:00
draft: false
author: ""
authorLink: ""
description: ""

tags: [research, pdf, tiff]
categories: [Research]

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

Convert `pdf` files to `tiff` images.

<!--more-->

## Use pdftoppm (recommended)

`pdftoppm` (included in `poppler-utils`) requires less setup than `ghostscript` + `imagemagick` do. [^2][^3]

[^2]: https://www.linuxuprising.com/2019/03/how-to-convert-pdf-to-image-png-jpeg.html
[^3]: https://jdhao.github.io/2019/11/14/convert_pdf_to_images_pdftoppm/

### Install

**Ubuntu-based**
```bash
sudo apt install poppler-utils
```

**Arch-based**
```bash
sudo pacman -S poppler-utils
```

**Conda** (Also available in Windows systems)
```bash
conda install -c conda-forge poppler
```

### Usage

[Documentation](https://www.mankier.com/1/pdftoppm)

To convert the pdf file to a 300-DPI TIFF image with lzw compression.

```bash
pdftoppm -tiff -tiffcompression lzw -r 300 in.pdf outname
```

## Use GhostScript and ImageMagick

### Install

```bash Ubuntu
sudo apt install ghostscript imagemagick
```

### Enable pdf permission

For security reasons, PDF read/write are disable by default. You could change the settings file to fix that.[^1]

[^1]: <https://stackoverflow.com/questions/52998331/imagemagick-security-policy-pdf-blocking-conversion>

`/etc/ImageMagick-7/policy.xml`

```xml /etc/ImageMagick-7/policy.xml
<policy domain="coder" rights="read | write" pattern="PDF" />
```

### Convert pdf to tiff

```bash
convert -density 300 \
        -compress lzw \
        -background white \
        -alpha remove \
        -trim \
        "image.pdf" "image_%d.tiff"
```

---

## Reference
