---
title: 每日必应图片
categories:
  - Python
tags:
  - 每日必应
  - 图片
mp3: 'https://link.hhtjim.com/163/5179544.mp3'
cover: 'https://cn.bing.com//th?id=OHR.Aldeyjarfoss_ZH-CN0106567013_1920x1080.jpg&rf=LaDigue_1920x1080.jpg'
date: 2021-09-14 17:36:45
---
### 每日必应图片API
`https://www.bing.com/HPImageArchive.aspx?format=js&idx=0&n=1`
提取返回的图片url设置为该文章cover

`format=js`表示格式为json，`idx=0`表示今天，`n=1`表示返回的数量

python代码
```python
#!/usr/bin/env python
# -*- coding: UTF-8 -*-
# @Time    : 2019/12/22 下午2:10
# @Author  : dawn
# @File    : bing.py

import requests

bing = 'https://www.bing.com'
url = 'https://www.bing.com/HPImageArchive.aspx?format=js&idx=0&n=1'
img = requests.get(url).json().get('images')[0]['url'].replace('&pid=hp', '')
print(bing + img)
```