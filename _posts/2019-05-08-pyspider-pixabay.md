---
title: "pyspider爬取Pixabay免费正版图片"
categories:
  - Python
tags:
  - Python 爬虫 pyspider Pixabay
date: 2019-05-08
---

## 前言

许多网友贡献了不少爬取妹子图片、豆瓣电影的教程。这次来分享爬取国外比较大的图片网站 Pixabay。

选择 Pixabay 的原因：
- 可以在任何地方使用的免费正版图片和视频
- 无需为创作者署名
- 资源丰富，便于爬取大量数据

官网：https://pixabay.com/zh/

## 1. 安装 PhantomJS

pyspider 的安装不过多赘述，为了爬取含JS的页面，需要使用 PhantomJS。

```bash
sudo apt-get install phantomjs
phantomjs --version
```

## 2. 使用 PhantomJS

当 pyspider 连上 PhantomJS 代理后，通过在 self.crawl 中添加 `fetch_type='js'` 参数开启。

```python
self.crawl(url, callback=self.index_page, fetch_type='js')
```

## 3. 完整代码

```python
from pyspider.libs.base_handler import *

class Handler(BaseHandler):
    crawl_config = {}
    
    def __init__(self):
        self.base_url = 'https://pixabay.com/zh/images/search/?pagi='
        self.page_num = 1
        self.total_num = 30
    
    @every(minutes=24 * 60)
    def on_start(self):
        while self.page_num <= self.total_num:
            url = self.base_url + str(self.page_num)
            self.crawl(url, callback=self.index_page, fetch_type='js')
            self.page_num += 1
    
    @config(age=10 * 24 * 60 * 60)
    def index_page(self, response):
        for each in response.doc('a[href^="https://pixabay.com/zh/photos/"]').items():
            self.crawl(each.attr.href, callback=self.detail_page, fetch_type='js')
    
    @config(priority=2)
    def detail_page(self, response):
        return {
            "title": response.doc('h1').text(),
            "img": response.doc('div > img').attr('src')
        }
```

然后设置 running，点击 run 运行即可。

---

*本文原始发表于 CSDN，迁移至 GitHub Pages*
