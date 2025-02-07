+++ 
draft = false
date = 2023-03-09T14:53:02Z
title = "How to fix Hugo on AWS Amplify"
slug = "hugo-version-amplify"
tags = ["AWS", "Hugo", "Amplify"]
categories = [ "WebDev" ]
+++

When I was building this site, I saw several warnings in the AWS console during deployment saying that my theme was not supported by this version of Hugo. I found this odd as the site built fine on my local machine, but didn't go in-depth, as everything worked anyway. But after I moved to a new theme, AWS was failing to build it. Logs have been still pointing at Hugo version. 

As I was unfamiliar with AWS and Amplify in particular, I went to Google (or to [SearX](https://knikolaev.me/projects/searx/), to be precise) and stumbled upon [this](https://michaux.co/posts/specifying-hugo-version-on-aws-amplify/) article. Apparently, AWS has its own repository and they don't feel like updating it often. 
As in the author's article, Hugo version on my host was extremely old: 
```
2023-03-08T15:34:24.150Z [INFO]: Hugo Static Site Generator v0.75.1-A4A7BAB7 linux/amd64
BuildDate: 2020-09-15T06:46:04Z
```
For comparison: the latest version is **0.111.2**. 

Although the author did a great job with their fix, I needed newer and extended version of hugo, so I edited their build settings to suit my needs. Here are two options for extended and normal versions of Hugo:

### Latest Hugo extended:

```yaml
version: 1
frontend:
  phases:
    build:
      commands:
        - echo $(hugo version)
        - wget https://github.com/gohugoio/hugo/releases/download/v0.111.2/hugo_extended_0.111.2_Linux-64bit.tar.gz
        - tar -xf hugo_extended_0.111.2_Linux-64bit.tar.gz hugo
        - mv hugo /usr/bin/hugo
        - rm -rf hugo_extended_0.111.2_Linux-64bit.tar.gz
        - hugo
  artifacts:
    baseDirectory: public
    files:
      - '**/*'
  cache:
    paths: []
```

### Latest Hugo standard:
```yaml
version: 1
frontend:
  phases:
    build:
      commands:
        - echo $(hugo version)
        - wget https://github.com/gohugoio/hugo/releases/download/v0.111.2/hugo_0.111.2_Linux-64bit.tar.gz
        - tar -xf hugo_0.111.2_Linux-64bit.tar.gz hugo
        - mv hugo /usr/bin/hugo
        - rm -rf hugo_extended_Linux-64bit.tar.gz
        - hugo
  artifacts:
    baseDirectory: public
    files:
      - '**/*'
  cache:
    paths: []

```
