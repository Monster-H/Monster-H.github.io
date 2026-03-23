---
title: "systemctl命令管理systemd服务"
categories:
  - Linux
tags:
  - Linux systemctl
date: 2021-09-09
---

## 前言

当Linux中有许多系统服务，无法通过外部管理工具或者接口开启/关闭时，需要手动管理。

Systemd 是基于Linux的操作系统的系统和服务管理器。

## 常用命令

### 启动/停止服务

```bash
systemctl start 服务名
systemctl stop 服务名
# 例如
systemctl start ssh.service
systemctl stop ssh.service
```

### 查看服务状态

```bash
systemctl status 服务名
```

### 开机自启

```bash
systemctl enable 服务名
systemctl disable 服务名
```

### 重启服务

```bash
systemctl restart 服务名
```

### 查看所有服务

```bash
systemctl list-units --type=service
```

---

*本文原始发表于 CSDN，迁移至 GitHub Pages*
