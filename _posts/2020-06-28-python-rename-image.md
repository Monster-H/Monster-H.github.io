---
title: "Python-批量修改图像文件名"
categories:
  - Python
tags:
  - Python 图像处理
date: 2020-06-28
---

## 简介

万能图像命名修改模板，可举一反三。

## 代码实现

```python
import os
import re
import sys

path = r"D:\test\photo"

def renameall(path):
    fileList = os.listdir(path)
    print("修改前：" + str(fileList))
    
    i = 0
    for file in fileList:
        olddir = os.path.join(path, file)
        
        # 获取文件扩展名
        filename = os.path.splitext(file)[0]
        filetype = os.path.splitext(file)[1]
        
        # 新文件名
        newname = f"image_{i:04d}{filetype}"
        newdir = os.path.join(path, newname)
        
        os.rename(olddir, newdir)
        i += i
    
    print("修改完成")

if __name__ == "__main__":
    renameall(path)
```

---

*本文原始发表于 CSDN，迁移至 GitHub Pages*
