---
title: "pyspider爬虫教程-HTML和CSS选择器"
categories:
  - Python
tags:
  - Python 爬虫 pyspider
date: 2019-04-30
---

> 转自：binux.blog

## 开始之前

由于教程是基于 pyspider 的，你可以安装一个 pyspider，或者直接使用 pyspider 的 demo 环境。

万维网是一个由许多互相链接的超文本页面组成的系统：
- 网页使用网址（URL）定位，并链接彼此
- 网页使用 HTTP 协议传输
- 网页使用 HTML 描述外观和语义

所以，爬网页实际上就是：
1. 找到包含我们需要的信息的网址列表
2. 通过 HTTP 协议把页面下载回来
3. 从页面的 HTML 中解析出需要的信息
4. 找到更多URL，回到2继续

## 选取开始网址

我们要爬所有的电影，通过抓取分类下的所有的标签列表页来遍历所有的电影。

## 创建项目

在 pyspider 的 dashboard 的右下角，点击 "Create" 按钮

```python
@every(minutes=24 * 60)
def on_start(self):
    self.crawl('http://movie.douban.com/tag/', callback=self.index_page)
```

- self.crawl 告诉 pyspider 抓取指定页面，然后使用 callback 函数对结果进行解析
- @every 修饰器，表示每天会执行一次

## CSS选择器

CSS选择器，是CSS用来定位需要设置样式的元素所使用的表达式。我们也可以通过它定位需要的元素。

在 pyspider 中，内置了 response.doc 的 PyQuery 对象，让你可以使用类似 jQuery 的语法操作 DOM 元素。

### 常用CSS选择器

```python
# 选择所有a标签
response.doc('a')

# 选择id为wrapper的元素
response.doc('#wrapper')

# 选择class为content的元素
response.doc('.content')

# 选择div下的p标签
response.doc('div p')

# 选择有href属性的a标签
response.doc('a[href]')
```

### 电影详情页示例

```python
def detail_page(self, response):
    return {
        "url": response.url,
        "title": response.doc('title').text(),
        "rating": response.doc('#interest_sectl .rating_num').text(),
        "导演": [x.text() for x in response.doc('a[rel="v:directedBy"]').items()],
    }
```

---

*本文原始发表于 CSDN，迁移至 GitHub Pages*
