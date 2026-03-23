---
title: "Linux-iotop命令-监控磁盘IO"
categories:
  - Linux
tags:
  - Linux iotop
date: 2021-11-16
---

## 1) 使用场景

iotop 是一个用来监视磁盘I/O使用状况的 top 类工具，可监测到哪一个程序使用的磁盘IO的信息。

## 2) 常用参数

- `-o` 只显示正在使用I/O的进程
- `-b` 非交互模式
- `-n num` 设置显示的次数
- `-d sec` 设置刷新间隔
- `-p PID` 只显示指定PID

## 3) 使用示例

```bash
# 安装
sudo apt install iotop

# 运行
sudo iotop
```

---

*本文原始发表于 CSDN，迁移至 GitHub Pages*
