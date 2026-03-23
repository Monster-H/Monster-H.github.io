---
title: "Ubuntu查看隐藏文件的方法"
categories:
  - Linux
tags:
  - Linux Ubuntu
date: 2018-07-14
---

## 方案一：桌面可视化窗口

进入待显示的文件路径，按 `Ctrl + h` 即可显示隐藏文件。

## 方案二：命令行

使用 `ls -a` 命令显示所有文件，包括隐藏文件：

```bash
ls -a
ls -la  # 显示详细信息
```

## 补充

使用 git 命令初始化后，会自动生成 `.git` 的隐藏文件夹，该文件是 git 系统跟踪管理的核心。

---

*本文原始发表于 CSDN，迁移至 GitHub Pages*
