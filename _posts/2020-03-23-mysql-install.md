---
title: "Windows免安装版MySQL配置教程"
categories:
  - Python
tags:
  - MySQL Python
date: 2020-03-23
---

## 一、下载

1. 打开 https://www.mysql.com/downloads
2. 选择 Community Edition
3. 下载地址：https://dev.mysql.com/downloads/mysql/
4. 选择 Windows (Architecture Independent), ZIP Archive

## 二、解压

解压到指定目录，如 `D:\mysql`

## 三、配置

创建配置文件 `my.ini`：

```ini
[mysqld]
basedir=D:\mysql
datadir=D:\mysql\data
port=3306
```

## 四、环境变量

```
MYSQL_HOME=D:\mysql
PATH=%MYSQL_HOME%\bin
```

## 五、安装服务

以管理员身份运行命令提示符：

```bash
cd D:\mysql\bin
mysqld --install
```

## 六、启动服务

```bash
net start mysql
net stop mysql
```

---

*本文原始发表于 CSDN，迁移至 GitHub Pages*
