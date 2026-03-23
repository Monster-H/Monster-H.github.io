---
title: "Keras-截取ResNet50网络层"
categories:
  - Python
tags:
  - Python Keras 深度学习
date: 2019-11-25
---

## 概述

截取主要是使用 `get_layer()` 方法来设置截取网络的起点与终点！

## 实现方法

```python
from keras.models import Model
from keras.applications import ResNet50

# 加载完整ResNet50
base_model = ResNet50(weights='imagenet')

# 获取中间层
# 例如：截取到 avg_pool 层
model = Model(
    inputs=base_model.input,
    outputs=base_model.get_layer('avg_pool').output
)

# 使用
features = model.predict(image)
print(features.shape)
```

## 常用层名称

- `conv1_conv`
- `conv2_block3_out`
- `conv3_block4_out`
- `conv4_block6_out`
- `conv5_block3_out`
- `avg_pool`

---

*本文原始发表于 CSDN，迁移至 GitHub Pages*
