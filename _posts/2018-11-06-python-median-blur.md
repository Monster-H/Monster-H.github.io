---
title: "Python-图像平滑处理-中值滤波"
categories:
  - Python
tags:
  - Python OpenCV 图像处理
date: 2018-11-06
---

## 1. 什么是滤波？

图像滤波：即在尽量保留图像细节特征的条件下对目标图像的噪声进行抑制，是图像预处理中不可缺少的操作。

## 2. 中值滤波

中值滤波是一种非线性滤波，常用于去除椒盐噪声。

## 3. 代码实现

```python
import cv2
import numpy as np

# 读取图像
img = cv2.imread('noisy_image.jpg')

# 中值滤波
# kernel_size 必须是奇数
result = cv2.medianBlur(img, 5)

# 显示
cv2.imshow('Original', img)
cv2.imshow('Median Blur', result)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

## 4. 参数说明

- `src`：输入图像
- `ksize`：核大小，必须是奇数（如 3, 5, 7）

---

*本文原始发表于 CSDN，迁移至 GitHub Pages*
