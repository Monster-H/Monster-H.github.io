---
title: "Linux-lsof命令-查看打开的文件"
categories:
  - Linux
tags:
  - Linux lsof
date: 2021-11-18
---

## 1) 使用场景

lsof (list open files) 是一个列出当前系统打开文件的工具。

在linux环境下，任何事物都以文件的形式存在，通过文件不仅仅可以访问常规数据，还可以访问网络连接和硬件。

## 2) 命令详解

### 常用参数

- `-a` 或 `--append` 追加模式
- `-c` 或 `--command` 显示 COMMAND 列中包含指定字符的进程
- `-d` 或 `--directory` 显示目录下被打开的文件
- `+d` 或 `+D` 递归搜索
- `-i` 或 `--internet` 显示符合条件的进程
- `-p` 或 `--process` 显示指定进程所打开的文件
- `-u` 或 `--user` 显示指定用户打开的文件

### 常用示例

```bash
# 查看端口占用
lsof -i:8080

# 查看所有网络连接
lsof -i

# 查看某个用户打开的所有文件
lsof -u username

# 查看某个进程打开的所有文件
lsof -p pid

# 查看目录下被打开的文件
lsof +D /path/to/directory
```

---

*本文原始发表于 CSDN，迁移至 GitHub Pages*
