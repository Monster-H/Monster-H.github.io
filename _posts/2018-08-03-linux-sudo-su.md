---
title: "su-sudo-sudo-su-sudo-i的用法和区别"
categories:
  - Linux
tags:
  - Linux sudo
date: 2018-08-03
---

## sudo

暂时切换到超级用户模式以执行超级用户权限，提示输入密码时该密码为当前用户的密码。

```bash
sudo command
```

## su

切换到某某用户模式，提示输入密码时该密码为切换后账户的密码。

```bash
su username  # 切换到指定用户
su           # 切换到root用户
```

## sudo -i

为了频繁的执行某些只有超级用户才能执行的权限，用这个命令。

```bash
sudo -i
```

## sudo su

两者效果一样，都是 root 权限。

## 区别总结

| 命令 | 密码 | 切换用户 |
|------|------|----------|
| sudo | 当前用户密码 | 不切换 |
| su | 目标用户密码 | 切换到目标用户 |
| sudo -i | 当前用户密码 | 切换到root |
| sudo su | 当前用户密码 | 切换到root |

---

*本文原始发表于 CSDN，迁移至 GitHub Pages*
