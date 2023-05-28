---
title: css02
date: 2023-05-21 18:05:00
author: 小白学css
img: https://cdn.jsdelivr.net/gh/panpan987/CDN@master/cover_img/235005-1682869805397f.jpg
categories: css
tags:
  - css
  - Udemy排名第一的高级CSS课程
---

## btn效果
```html
<a href="#" class="btn btn-white">Discover our tours</a>
```
```css
.btn:link,
.btn:visited {
    text-transform: uppercase;
    text-decoration: none;
    padding: 15px 40px;
    display: inline-block;
    border-radius: 100px;
    transition: all .2s;
}
.btn:hover { 

    transform:  translateY(-3px);
    box-shadow: 0 10px 20px rgba(0, 0, 0, .2);
}
.btn:active {
    transform:  translateY(-1px);
    box-shadow: 0 5px 10px rgba(0, 0, 0, .2);
}

.btn-white {
    background-color: #fff;
    color: #777;
}
```

