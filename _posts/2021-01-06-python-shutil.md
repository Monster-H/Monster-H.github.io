---
title: "Python标准库shutil模块-复制移动"
categories:
  - Python
tags:
  - Python shutil
date: 2021-01-06
---

## 引言

最近写的脚本需要将文件中的文件及信息进行复制和转移，因此找到了python中shutil模块，跟着学习了和操作了一下，现将分享如下

## 1.什么是Shutil?

- Shutil的全称 Shell utility （中文：Shell实用程序）
- shutil 是高级的文件，文件夹，压缩包处理模块

## 2.常用的函数及含义

### 1.shutil.copyfileobj(fsrc, fdst[, length])

将文件内容拷贝到另一个文件中

```python
import shutil
shutil.copyfileobj(open('old.xml','r'), open('new.xml', 'w'))
```

### 2.shutil.copyfile(src, dst)

拷贝文件

```python
shutil.copyfile('f1.log', 'f2.log')
```

### 3.shutil.copymode(src, dst)

仅拷贝权限。内容、组、用户均不变

```python
shutil.copymode('f1.log', 'f2.log')
```

### 4.shutil.copystat(src, dst)

仅拷贝状态的信息，包括：mode bits, atime, mtime, flags

```python
shutil.copystat('f1.log', 'f2.log')
```

### 5.shutil.copy(src, dst)

拷贝文件和权限

```python
shutil.copy('f1.log', 'f2.log')
```

### 6.shutil.copy2(src, dst)

拷贝文件和状态信息

```python
shutil.copy2('f1.log', 'f2.log')
```

### 7.shutil.copytree(src, dst, symlinks=False, ignore=None)

递归的去拷贝文件夹

```python
shutil.copytree('folder1', 'folder2', ignore=shutil.ignore_patterns('*.pyc', 'tmp*'))
```

### 8.shutil.rmtree(path[, ignore_errors[, onerror]])

递归的去删除文件

```python
shutil.rmtree('folder1')
```

### 9.shutil.move(src, dst)

递归的去移动文件，它类似mv命令，其实就是重命名。

```python
shutil.move('folder1', 'folder3')
```

### 10.shutil.make_archive(base_name, format,...)

创建压缩包并返回文件路径

```python
import shutil
ret = shutil.make_archive("wwwwwwwwww", 'gztar', root_dir='/Users/wupeiqi/Downloads/test')
```

## 压缩包处理

```python
import zipfile

# 压缩
z = zipfile.ZipFile('laxi.zip', 'w')
z.write('a.log')
z.write('data.data')
z.close()

# 解压
z = zipfile.ZipFile('laxi.zip', 'r')
z.extractall()
z.close()
```

---

*本文原始发表于 CSDN，迁移至 GitHub Pages*
