---
title: "Compressio"
date: 2023-03-22T15:24:13Z
draft: false
---

## About

Compressio was originally my final college project. 

Сompressio is a Python-based program that uses the PyQt framework for it's GUI. I also used **multithreading** and **Pillow** libraries It is pretty simple: 
1. Select a folder containing images you need to compress
2. Select where to save all the images after compressing
3. Choose level of compression using a slider. This is applicable only to JPEG, as PNG is a lossless format. 

The coolest thing I'm proud of is compressio's speed. Hundreads of images can be compressed in 10-20 seconds. Furthermore, you will not spot any significant difference in quality. 

## Compression methods

Compressio compresses JPEG images using JPEG's own compressing algorithm. Pillow library handles the compression. PNGs are harder, so I came up with a solution to lower a colour palette of images. Our eyes hardly notice difference, but the image has MILLIONS less colours, making the file size much smaller.

## Installation

I use Poetry to manage my dependencies, so installing it is necessary.

#### Using Poetry (Linux, macOS, WSL)

```shell
# Installing Poetry 
curl -sSL https://install.python-poetry.org | python3 -

# Cloning the repo
git clone https://github.com/knikolaeff/img-compressio.git

cd img-compressio

# Installing dependencies
poetry install

# Running the script
python3 compressio.py
```

#### Using Poetry (Windows **(Powershell)**)

```shell
# Installing Poetry 
(Invoke-WebRequest -Uri https://install.python-poetry.org -UseBasicParsing).Content | py -

# Cloning the repo
git clone https://github.com/knikolaeff/img-compressio.git

cd img-compressio

# Installing dependencies
poetry install

# Running the script
python compressio.py
```