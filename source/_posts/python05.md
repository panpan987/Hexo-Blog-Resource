---
title: Python05
date: 2023-05-16 20:25:00
author: Anduin
coverImg: /images/3.jpg
categories: Python
tags:
  - Python
  - 基础
---

## 循环
```python
sum = 0
i = 1
while i <= 100:
    sum += i
    i += 1
print(f"1-100累加的和是：{sum}")
```
运行结果：
```bash
1-100累加的和是：5050
```
```python
import random
num = random.randint(1,100)
count = 0

flag = True
while flag:
    guess_num = int(input("请输入你猜测的数字："))
    count += 1
    if guess_num == num:
        print("猜中了")
        flag = False
    else:
        if guess_num >  :
            print("你猜的大了")
        else:
            print("你猜的小了")

print(f"你总共猜测了{count}次")
```
运行结果(结果不唯一)：
```bash
请输入你猜测的数字：50
你猜的小了
请输入你猜测的数字：70
你猜的大了
请输入你猜测的数字：65
你猜的小了
请输入你猜测的数字：62
你猜的小了
请输入你猜测的数字：50
你猜的小了
请输入你猜测的数字：70
你猜的大了
请输入你猜测的数字：69
猜中了
你总共猜测了7次
```