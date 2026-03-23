---
title: "Pycharm设置自定义代码块LiveTemplate"
categories:
  - Python
tags:
  - Python Pycharm
date: 2018-07-16
---

## 前言

在Pycharm中设置自定义代码块，可以大幅提升编码效率。

## 设置步骤

### 第一步：打开设置

`File` → `Settings` → 搜索 `Live Templates`

### 第二步：添加模板

1. 点击右上角 `+` 选择 `Template Group`，创建自己的分组
2. 在分组中点击 `+` 选择 `Live Template`
3. 设置缩写（如 `main`）和描述
4. 填写模板内容
5. 点击 `Define` 选择适用的语言

## 示例

```
Template: main
Abbreviation: main
Template text:
if __name__ == '__main__':
    $END$
```

---

*本文原始发表于 CSDN，迁移至 GitHub Pages*
