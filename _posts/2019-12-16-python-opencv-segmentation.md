---
title: "Python-OpenCV图像分割-提取特定目标区域"
categories:
  - Python
tags:
  - Python OpenCV 图像处理
date: 2019-12-16
---

## 概述

在OpenCV中，一般转换图像格式为HSV格式（默认格式为BGR），再进行指定颜色的提取。

## HSV格式介绍

HSV 为色相，饱和度，明度。

## 实现步骤

### 1. 转换为HSV格式

```python
import cv2

hsv = cv2.cvtColor(rgb_image, cv2.COLOR_BGR2HSV)
```

### 2. 提取指定颜色区域

```python
import cv2
import numpy as np

# 读取图像
img = cv2.imread('image.jpg')
hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)

# 定义蓝色范围
lower_blue = np.array([100, 50, 50])
upper_blue = np.array([130, 255, 255])

# 创建掩码
mask = cv2.inRange(hsv, lower_blue, upper_blue)

# 提取目标区域
result = cv2.bitwise_and(img, img, mask=mask)
```

---

*本文原始发表于 CSDN，迁移至 GitHub Pages*
