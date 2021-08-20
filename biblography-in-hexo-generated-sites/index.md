# Biblography in Hexo-generated sites


Using `citeproc` in `pandoc` to generate citation (biblography) entries in Hexo static site generator.

<!--more-->

## Setup a hexo blog site

Please see the [user guide](https://theme-next.js.org) for details.

## Switch markdown renderer to pandoc

A [pandoc](https://pandoc.org/) installation is required.

And replace the default Hexo `marked` render:

```bash
npm un hexo-renderer-marked
npm i hexo-renderer-pandoc
```

## Pandoc renderer config

In `_config.yml`

```yml
# markdown-renderer-pandoc config: https://github.com/wzpan/hexo-renderer-pandoc
pandoc:
  extra:
  - citeproc:
  - bibliography: "xxx.bib"
  - csl: "xxx.csl"
  template:
  meta:
  mathEngine:
```

