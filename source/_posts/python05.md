---
title: Python05
date: 2023-05-16 20:25:00
author: Anduin
img: https://cdn.jsdelivr.net/gh/panpan987/CDN@master/cover_img/194258-16842373781c8b.jpg
categories: Python
tags:
  - Python
  - 基础
---

## while循环
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
        if guess_num > num:
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

### 嵌套循环
向小美表白100天，每天送10朵玫瑰花。
```python
# 外层：表白100天
# 内层：每天表白都送10只玫瑰花

i = 1
while i <= 100:
    print(f"今天是第{i}天,准备表白......")

    # 内层循环
    j = 1
    while j <= 10:
        print(f"送给小美第{j}只玫瑰花")
        j += 1

    print("小美，我喜欢你")
    i += 1

print(f"坚持到第{i-1}天，表白成功")
```
运行结果：
```bash
D:\PycharmProjects\pythonProject1_pachong\day03.py 
今天是第1天,准备表白......
送给小美第1只玫瑰花
送给小美第2只玫瑰花
送给小美第3只玫瑰花
送给小美第4只玫瑰花
送给小美第5只玫瑰花
送给小美第6只玫瑰花
送给小美第7只玫瑰花
送给小美第8只玫瑰花
送给小美第9只玫瑰花
送给小美第10只玫瑰花
小美，我喜欢你
...
...
...
今天是第100天,准备表白......
送给小美第1只玫瑰花
送给小美第2只玫瑰花
送给小美第3只玫瑰花
送给小美第4只玫瑰花
送给小美第5只玫瑰花
送给小美第6只玫瑰花
送给小美第7只玫瑰花
送给小美第8只玫瑰花
送给小美第9只玫瑰花
送给小美第10只玫瑰花
小美，我喜欢你
坚持到第100天，表白成功
```

打印99乘法表  
默认print语句输出内容会自动换行，如下图：
```python
print("hello")
print("world")
```
运行结果:
```bash
hello
world
```
若想不换行，则：
```python
print("hello", end='')
print("world", end='')
```
运行结果：
```bash
helloworld
```
\t 语句的使用，相当于制表符，可以实现文字对齐效果，如下代码
```python
print("Hello\tWorld")
print("你好\t世界")
```
```bash
Hello	World
你好	世界
```
打印99乘法表，如果不使用循环：
```python
print("1*1=1")
print("1*2=2	2*2=4")
print("1*3=3	2*3=6	3*3=9")
print("1*4=4	2*4=8	3*4=12	4*4=16")
print("1*5=5	2*5=10	3*5=15	4*5=20	5*5=25")
print("1*6=6	2*6=12	3*6=18	4*6=24	5*6=30	6*6=36")
print("1*7=7	2*7=14	3*7=21	4*7=28	5*7=35	6*7=42	7*7=49")
print("1*8=8	2*8=16	3*8=24	4*8=32	5*8=40	6*8=48	7*8=56	8*8=64")
print("1*9=9	2*9=18	3*9=27	4*9=36	5*9=45	6*9=54	7*9=63	8*9=72	9*9=81")
```
使用循环：
```python
i = 1
while i <= 9:
    j = 1
    while j <= i:
        print(f"{j}*{i}={j*i}\t", end='')
        j += 1
    print()
    i += 1
```

