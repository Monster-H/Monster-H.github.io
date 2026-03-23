---
title: "Python-format-格式化函数详解"
categories:
  - Python
tags:
  - Python format
date: 2020-12-08
---

## 前言

由于最近使用Python format较为频繁，且太久回顾源码，又容易遗忘，就将format格式化函数做一点整理。

## 1. 作用

Python2.6 开始，新增了一种格式化字符串的函数 str.format()，它增强了字符串格式化的功能。

基本语法是通过 {} 和 : 来代替以前的 % 。

format 函数可以接受不限个参数，位置可以不按顺序。

## 2. 基本用法

```python
# 不设置指定位置，按默认顺序
>>>"{} {}".format("hello", "world")
'hello world'

# 设置指定位置
>>> "{0} {1}".format("hello", "world")
'hello world'

# 重复使用
>>> "{1} {0} {1}".format("hello", "world")
'world hello world'
```

## 3. 设置参数

```python
# 通过字典设置参数
site = {"name": "菜鸟教程", "url": "www.runoob.com"}
print("网站名：{name}, 地址 {url}".format(**site))

# 通过列表索引设置参数
my_list = ['菜鸟教程', 'www.runoob.com']
print("网站名：{0[0]}, 地址 {0[1]}".format(my_list))
```

## 4. 数字格式化

```python
>>> print("{:.2f}".format(3.1415926));
3.14

>>> print("{:+.2f}".format(3.14));
+3.14

>>> print("{:0>5d}".format(3));
00003
```

## 5. 格式化参考

| 格式 | 含义 |
|------|------|
| `{:.2f}` | 保留2位小数 |
| `{:+}` | 显示正负号 |
| `{:>10}` | 右对齐，宽度10 |
| `{:<10}` | 左对齐，宽度10 |
| `{:^10}` | 居中，宽度10 |

---

*本文原始发表于 CSDN，迁移至 GitHub Pages*
