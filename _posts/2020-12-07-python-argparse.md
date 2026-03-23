---
title: "Python-argparse命令行参数解析"
categories:
  - Python
tags:
  - Python argparse
date: 2020-12-07
---

## 什么是argparse?

argparse 是 Python 模块：命令行选项、参数和子命令解析器。

argparse 模块可以让人轻松编写用户友好的命令行接口。程序定义它需要的参数，然后 argparse 将弄清如何从 sys.argv 解析出那些参数。

## 基本用法

```python
import argparse

parser = argparse.ArgumentParser(description='描述程序')
parser.add_argument('echo', help='echo参数的帮助信息')
args = parser.parse_args()
print(args.echo)
```

## 常用参数

- `name` 或 `flags`：命令行参数名
- `action`：参数为true时的操作
- `nargs`：应该使用的命令行参数数量
- `const`：某些参数被定义时需要的常量值
- `default`：参数未提供时使用的默认值
- `type`：命令行参数应该被转换成的类型
- `choices`：命令行参数的可能值容器
- `required`：命令行参数是否可选
- `help`：参数的简短描述
- `metavar`：用法消息中参数的显示方式
- `dest`：用于在程序中访问该命令行参数时使用的属性名

## 示例

```python
import argparse

parser = argparse.ArgumentParser()
parser.add_argument('-n', '--name', type=str, required=True, help='Your name')
parser.add_argument('-a', '--age', type=int, default=20, help='Your age')
args = parser.parse_args()

print(f"Name: {args.name}, Age: {args.age}")
```

---

*本文原始发表于 CSDN，迁移至 GitHub Pages*
