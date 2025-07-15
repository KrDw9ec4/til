---
title: 图像处理的瑞士军刀 - ImageMagick
published: 2025-06-20T08:00:00
modified: 2025-07-15T21:06:00
tags:
  - cli
  - image
---

今天发现了图像处理领域的瑞士军刀 ImageMagick，原本需要找各种网站或者工具软件的功能，比如图片压缩、图片拼接、将多张图片合并成 PDF 等需求都可以使用 ImageMagick 满足。

## 安装

### Windows

使用 [Scoop](https://github.com/ScoopInstaller/Scoop) 安装，自动处理依赖和路径配置，方便后续更新。

```shell
scoop install imagemagick
```

### macOS

使用 [HomeBrew](https://brew.sh/) 安装，好处同 Scoop。

```shell
brew install imagemagick
```

## 使用

### 1. 格式转换

```shell
# jpg 转 png
magick input.jpg output.png
# 其他格式转换也是类似的，就是更改文件后缀名
```

### 2. 图片压缩

```shell
# 调整质量，数字越小，压缩程度越高
magick input.jpg -quality 80 output.jpg
```

### 3. 图片拼接

```shell
# 水平拼接
magick image1.jpg image2.jpg +append output.jpg
# 垂直拼接
magick image1.jpg image2.jpg -append output.jpg
```

#### 4. 合并为 PDF 文件

```shell
# 指定文件合并
magick image1.jpg image2.jpg output.pdf
# 批量合并当前目录下全部文件
magick *.jpg output.pdf
```

## References

- [ImageMagick](https://github.com/ImageMagick/ImageMagick)
