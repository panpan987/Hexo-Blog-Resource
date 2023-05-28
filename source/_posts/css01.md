---
title: css01
date: 2023-05-20 20:17:00
author: 小白学css
img: https://cdn.jsdelivr.net/gh/panpan987/CDN@master/cover_img/101035-16600110352f43.jpg
categories: css
tags:
  - css
  - Udemy排名第一的高级CSS课程
---
## title
### 图片
```html
<body>
    <header class="header">
        Some text...
    </header>  
</body>
```
```css
/*
COLORS:

Light green: #7ed56f
Medium green: #55c57a
Dark green: #28b485

*/

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: "Lato", sans-serif;
    font-weight: 400;
    font-size: 16px;
    line-height: 1.7;
    color: #777;
    padding: 30px;
}

.header {
    /* 占视窗高度的95% */
    height: 95vh;
    /* linear-gradient 从左上到右下颜色渐变 */
    background-image: linear-gradient(to right bottom,
            rgba(126, 213, 111, 0.8),
            rgba(40, 180, 131, 0.8)),
        url(../img/hero.jpg);
    /* 自适应 */
    background-size: cover;
    /* 改变视窗大小时，上部分不改变 */
    background-position: top;
    /* 切片，图片在特定形状里显示*/
    clip-path: polygon(0 0, 100% 0, 100% 75vh, 0 100%);
}
```
![](https://cdn.jsdelivr.net/gh/panpan987/CDN@master/img/Snipaste_2023-05-20_21-35-07.png)
### 文字及logo
```html
<body>
        <header class="header">
            <div class="logo-box">
                <img src="img/logo-white.png" alt="Logo" class="logo"/> 
            </div>

            <div class="text-box">
                <h1 class="heading-primary">
                    <span class="heading-primary-main">Outdoors</span>
                    <span class="heading-primary-sub">is where life happens</span>
                </h1>
            </div>
            
        </header>
        
    </body>
```
```css
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: "Lato", sans-serif;
    font-weight: 400;
    font-size: 16px;
    line-height: 1.7;
    color: #777;
    padding: 30px;
}

.header {
    /* 占视窗高度的95% */
    height: 95vh;
    /* linear-gradient 从左上到右下颜色渐变 */
    background-image: linear-gradient(to right bottom,
            rgba(126, 213, 111, 0.8),
            rgba(40, 180, 131, 0.8)),
        url(../img/hero.jpg);
    /* 自适应 */
    background-size: cover;
    /* 改变视窗大小时，上部分不改变 */
    background-position: top;
    position: relative;
    /* 切片，图片在特定形状里显示*/
    clip-path: polygon(0 0, 100% 0, 100% 75vh, 0 100%);
}

.logo-box {
    /* 绝对定位，它都父元素需要相对定位 */
    position: absolute;
    top: 40px;
    left: 40px;
}
.log {
    height: 35px;
}

.text-box {
    position: absolute;
    /* top、left是相对于父元素位置改变 */
    top: 40%;
    left: 50%;
    /* 相对于自身位置改变 */
    transform: translate(-50%,-50%);
    
}

.heading-primary {
    color: #fff;
    text-transform: uppercase;
}
.heading-primary-main {
    display: block;
    font-size: 60px;
    font-weight: 400;
    letter-spacing: 35px;
}
.heading-primary-sub {
    display: block;
    font-size: 20px;
    font-weight: 700;
    letter-spacing: 17.4px;

}
```
![](https://cdn.jsdelivr.net/gh/panpan987/CDN@master/img/Snipaste_2023-05-20_22-08-46.png)

### 动画
```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        
        <link href="https://fonts.googleapis.com/css?family=Lato:100,300,400,700,900" rel="stylesheet">

        <link rel="stylesheet" href="css/icon-font.css">
        <link rel="stylesheet" href="css/style.css">
        <link rel="shortcut icon" type="image/png" href="img/favicon.png">
        
        <title>Natours | Exciting tours for adventurous people</title>
    </head>
    <body>
        <header class="header">
            <div class="logo-box">
                <img src="img/logo-white.png" alt="Logo" class="logo"/> 
            </div>

            <div class="text-box">
                <h1 class="heading-primary">
                    <span class="heading-primary-main">Outdoors</span>
                    <span class="heading-primary-sub">is where life happens</span>
                </h1>
            </div>
            
        </header>
        
    </body>
</html>
```
```css
/*
COLORS:

Light green: #7ed56f
Medium green: #55c57a
Dark green: #28b485

*/

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: "Lato", sans-serif;
    font-weight: 400;
    font-size: 16px;
    line-height: 1.7;
    color: #777;
    padding: 30px;
}

.header {
    /* 占视窗高度的95% */
    height: 95vh;
    /* linear-gradient 从左上到右下颜色渐变 */
    background-image: linear-gradient(to right bottom,
            rgba(126, 213, 111, 0.8),
            rgba(40, 180, 131, 0.8)),
        url(../img/hero.jpg);
    /* 自适应 */
    background-size: cover;
    /* 改变视窗大小时，上部分不改变 */
    background-position: top;
    position: relative;
    /* 切片，图片在特定形状里显示*/
    clip-path: polygon(0 0, 100% 0, 100% 75vh, 0 100%);
}

.logo-box {
    /* 绝对定位，它都父元素需要相对定位 */
    position: absolute;
    top: 40px;
    left: 40px;
}

.log {
    height: 35px;
}

.text-box {
    position: absolute;
    /* top、left是相对于父元素位置改变 */
    top: 40%;
    left: 50%;
    /* 相对于自身位置改变 */
    transform: translate(-50%, -50%);

}

.heading-primary {
    color: #fff; 
    text-transform: uppercase;

    backface-visibility: hidden
}

.heading-primary-main {
    display: block;
    font-size: 60px;
    font-weight: 400;
    letter-spacing: 35px;

    animation-name: moveInLeft;
    animation-duration: 1s;
    animation-timing-function: ease-out;

    /* animation-iteration-count: 3; */
    /* animation-delay: 3s; */
}

.heading-primary-sub {
    display: block;
    font-size: 20px;
    font-weight: 700;
    letter-spacing: 17.4px;

    animation: moveInRight 1s ease-out;
}

/* 动画效果 */
@keyframes moveInLeft {
    0% {
        opacity: 0;
        /* 动画开始前，元素在x轴更靠左边一点 */
        transform: translateX(-100px);
    }

    /* 60% {
        transform: rotate(180deg);
    } */

    80% {
        transform: translateX(10px);
    }

    100% {
        opacity: 1;
        transform: translate(0);
    }
}

@keyframes moveInRight {
    0% {
        opacity: 0;
        /* 动画开始前，元素在x轴更靠右边一点 */
        transform: translateX(100px);
    }

    80% {
        transform: translateX(-10px);
    }

    100% {
        opacity: 1;
        transform: translate(0);
    }
}
```
