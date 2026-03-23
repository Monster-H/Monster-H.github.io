---
title: "Pandas遇到DtypeWarning怎么办"
categories:
  - Python
tags:
  - Python Pandas
date: 2020-12-18
---

## 一、问题描述

在运行项目的过程中，做数据分析，会读取到csv文件，最后在运行代码的时候报了这样的错误：

```
DtypeWarning: Columns (0,9,13,20,24,26,32,33,36,41,55,60,61,63,64) have mixed types.Specify dtype option on import or set low_memory=False.
```

从警告的字面意思看是由于列中存在多种数据类型导致的。例如数值 3 被认为 是 int 类型，但是数值 3.4 可能被认为是 str 类型。

## 二、解决思路

### 方法1：关闭 low_memory 模式

```python
data = pd.read_csv(f, low_memory=False)
```

### 方法2：指定列的数据类型

```python
data = pd.read_csv(f, dtype={"Columns1": int, "Columns2": int})
```

## 三、low_memory 是什么?

Pandas 在读取 csv 文件时是按块读取的，并不会一次性读取，并且对于数据的类型"都靠猜"，所以就可能出现了 Pandas 在不同块对同一列的数据"猜"出了不同的数据类型。

- 关闭 low_memory 功能时，Pandas 会一次性读取 csv 中的所有数据，自然对列的数据类型也只会猜测一次
- 但是关闭 low_memory 时，一旦 csv 文件过大，就会内存溢出

**建议：** 采取指定类型的方式。

---

*本文原始发表于 CSDN，迁移至 GitHub Pages*
