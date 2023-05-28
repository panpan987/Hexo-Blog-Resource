---
title: Python04
date: 2023-05-16 18:18:00
author: Anduin
img: https://cdn.jsdelivr.net/gh/panpan987/CDN@master/cover_img/230111-1683730871344e.jpg
categories: Python
tags:
  - Python
  - 基础
---

## if语句的基本格式
```python
age = 30

if age >= 18:
    print("我已经成年了")
    print("即将步入大学生活")
print("时间过得真快")
```
运行结果：
```bash
我已经成年了
即将步入大学生活
时间过得真快
```
说明：判断语句的结果，必须是布尔类型True或False，
True会执行if内的代码语句，False则不会执行
```python
age = 17

if age >= 18:
    print("我已经成年了")
else:
    print("你还没成年")
```
运行结果：
```bash
你还没成年
```
## 猜数字小游戏



