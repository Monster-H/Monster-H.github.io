---
title: "Linux-pgrep命令-查找进程"
categories:
  - Linux
tags:
  - Linux pgrep
date: 2021-11-18
---

## 1) 使用场景

pgrep命令以名称为依据从运行进程队列中查找进程，并显示查找到的进程ID。

## 2) 常用参数

- `-o`：仅显示找到的最小（起始）进程号
- `-n`：仅显示找到的最大（最新）进程号
- `-l`：显示进程名称
- `-f`：匹配进程名和参数

## 3) 示例

```bash
# 查找python进程
pgrep python

# 显示进程名
pgrep -l python

# 查找最新启动的
pgrep -n python
```

---

*本文原始发表于 CSDN，迁移至 GitHub Pages*
