---
title: "Python爬虫-Selenium与PhantomJS"
categories:
  - Python
tags:
  - Python Selenium 爬虫
date: 2019-05-08
---

> 转自：cnblogs.com/miqi1992

## Selenium

Selenium是一个Web的自动化测试工具，最初是为网站自动化测试而开发的。它可以像按键精灵一样自动化操作浏览器，支持所有主流的浏览器。

Selenium可以根据指令让浏览器自动加载页面，获取需要的页面，甚至页面截屏。

### 安装

```bash
pip install selenium
```

## PhantomJS

PhantomJS是一个基于Webkit的"无界面"(headless)浏览器，它会把网站加载到内存并执行页面上的JavaScript，因为不会展示图形界面，所以运行起来比完整的浏览器更高效。

把Selenium和PhantomJS结合在一起，就可以运行一个非常强大的网络爬虫了。

### 快速入门

```python
# -*- coding:utf-8 -*-
from selenium import webdriver
import time
from selenium.webdriver.common.keys import Keys

# 创建浏览器对象
driver = webdriver.PhantomJS()
driver.set_window_size(1366, 768)

# 打开百度
driver.get("http://www.baidu.com/")

# 获取页面内容
data = driver.find_element_by_id('wrapper').text
print(data)

# 页面截图
driver.save_screenshot("baidu.png")

# 搜索
driver.find_element_by_id('kw').send_keys('长城')
driver.find_element_by_id('su').click()

driver.quit()
```

## 页面操作

### 定位元素

```python
# 通过ID
element = driver.find_element_by_id("passwd-id")

# 通过Name
element = driver.find_element_by_name("user-name")

# 通过XPath
element = driver.find_element_by_xpath("//input[@id='passwd-id']")

# 通过CSS选择器
element = driver.find_element_by_css_selector("#passwd-id")
```

### 键盘操作

```python
# 全选
driver.find_element_by_id('kw').send_keys(Keys.CONTROL, 'a')

# 复制
driver.find_element_by_id('kw').send_keys(Keys.CONTROL, 'x')

# 粘贴
driver.find_element_by_id('kw').send_keys(Keys.CONTROL, 'v')

# 回车
driver.find_element_by_id('su').send_keys(Keys.RETURN)
```

---

*本文原始发表于 CSDN，迁移至 GitHub Pages*
