---
title: "GitLab CICD"
subtitle: ""
date: 2021-06-18T21:32:39+08:00
draft: false
author: ""
authorLink: ""
description: ""

tags: ["devops", "gitlab"]
categories: ["DevOps"]

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

[GitLab CI/CD](https://docs.gitlab.com/ee/ci/) is a tool built into GitLab for software development for
- Continuous Integration (CI)
- Continuous Delivery (CD) and Deployment

<!--more-->

## Parallel Matrix build of Gitlab CI/CD

Test and build in parallel with matrix build in Gitlab CI/CD. An example `.gitlab-ci.yml`

```yml
test:
  image: $IMAGE
  script:
    - python -V
  parallel:
    matrix:
      - IMAGE: ['python:3.6-alpine', 'python:3.7-alpine']
```

## Run Gitlab CI/CD on Github repositories

In GitLab, `Create a new project running CI/CD` for external repo, and enter the GitHub repo you want to mirror.

And then Gitlab will automatically mirror and run CI/CD piepelines when the Github repo updates.
