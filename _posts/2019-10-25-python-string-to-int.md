---
title: "Python-列表字符串转数字"
categories:
  - Python
tags:
  - Python 列表
date: 2019-10-25
---

## 方法一：循环

```python
numbers = ['2', '5', '130', '8']
new_numbers = []
for n in numbers:
    new_numbers.append(int(n))
print(new_numbers)  # [2, 5, 130, 8]
```

## 方法二：列表推导式

```python
numbers = ['2', '5', '130', '8']
new_numbers = [int(n) for n in numbers]
print(new_numbers)  # [2, 5, 130, 8]
```

## 方法三：map函数

```python
numbers = ['2', '5', '130', '8']
new_numbers = list(map(int, numbers))
print(new_numbers)  # [2, 5, 130, 8]
```

## Pandas Series 转 Numpy

```python
import pandas as pd

s = pd.Series([1, 2, 3])
arr = s.to_numpy()  # 或 s.values
```

---

*本文原始发表于 CSDN，迁移至 GitHub Pages*
