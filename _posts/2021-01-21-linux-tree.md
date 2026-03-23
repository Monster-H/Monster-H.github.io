---
title: "Linux-Tree命令-树状图显示目录"
categories:
  - Linux
tags:
  - Linux tree
date: 2021-01-21
---

## 简介

Linux tree命令用于以树状图列出目录的内容。执行tree指令，它会列出指定目录下的所有文件，包括子目录里的文件。

## 安装

```bash
# Ubuntu/Debian
sudo apt install tree

# CentOS/RHEL
sudo yum install tree
```

## 常用参数

- `-a` 显示所有文件和目录
- `-d` 只显示目录
- `-L n` 显示层级深度
- `-f` 显示完整路径
- `-I pattern` 忽略匹配的文件

## 示例

```bash
# 显示当前目录
tree

# 显示2层
tree -L 2

# 只显示目录
tree -d

# 忽略node_modules
tree -I 'node_modules|dist'
```

---

*本文原始发表于 CSDN，迁移至 GitHub Pages*
