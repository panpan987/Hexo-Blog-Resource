---
title: Python07
date: 2023-06-07 07:47:00
author: Anduin
img: https://cdn.jsdelivr.net/gh/panpan987/CDN@master/cover_img/001818-16826122981a31.jpg
categories: Python
tags:
  - Python
  - 基础
---
## 函数
函数是组织好的，可重复使用，用来实现特定功能的代码段。
```python
name = "Hello"
length = len(name)
print(length)
```
```bash
5
```
为什么随时都可以使用len()统计长度？
因为，len()是Python内置的函数：
- 是提前写好的
- 可以重复使用
- 实现统计长度这一特定功能的代码段  

我们使用过的input()、print()、int()等都是Python的内置函数。

需求：不使用系统内置函数，统计字符串长度。
```python
str1 = "Python"
str2 = "Number one"

count = 0
for i in str1:
    count += 1
print(f"字符串{str1}的长度是：{count}")

count = 0
for i in str2:
    count += 1
print(f"字符串{str2}的长度是：{count}")
```
```bash
字符串Python的长度是：6
字符串Number one的长度是：10
```
但是这样的代码重复严重，所以可以使用函数优化代码，如：
```python
str1 = "Python"
str2 = "Number one"

def my_len(data):
    count = 0
    for i in data:
        count += 1
    print(f"字符串{data}的长度是{count}")

my_len(str1)
my_len(str2)
```
```bash
字符串Python的长度是6
字符串Number one的长度是10
```
为什么要学习、使用函数呢？  
为了得到一个针对特定需求、可供重复利用的代码段，提高程序的复用性，减少重复性代码，提高开发效率。

函数的定义：
```python
def 函数名(传入参数):
    函数体
    return 返回值
```
无参案例
```python
def say_hi():
    print("欢迎光临\n这边请！")

say_hi()
```
```bash
欢迎光临
这边请
```
有参案例
```python
def add(x, y):
    result = x + y
    print(f"{x} + {y}的计算结果是：{result}")

add(5,6)
```
```bash
5 + 6的计算结果是：11
```
在函数定义中，提供的x和y,称之为：形式参数（形参），表示函数声明将要使用2个参数。函数调用中，提供的5和6，称之为：实际参数（实参），表示函数执行时真正使用的参数值，传入时，按照顺序传入数据，使用逗号分隔。

```python
def check(num):
    print("请配合测量体温！")
    if num <= 37.5:
        print(f"体温测量中，您的体温是：{num}度，体温正常请进！")
    else:
        print(f"体温测量中，您的体温是：{num}度，需要隔离！")
        
check(37.3)
```
```bash
请配合测量体温！
体温测量中，您的体温是：37.3度，体温正常请进！
```

函数的返回值
```
def 函数(参数...):
    函数体
    return 返回值

变量 = 函数(参数...)
```
```python
def add(a, b):
    result = a + b
    return result

r = add(1,2)
print(r)
```
```bash
3
```
什么是函数的嵌套调用
所谓函数的嵌套调用是指在一个函数里面又调用了另外一个函数。
```python
def func_b():
    print("---2---")

def func_a():
    print("---1---")

    func_b()

    print("---3---")

func_a()
```
```bash
---1---
---2---
---3---
```
执行流程：函数A中执行到调用函数B的语句，会将函数B全部执行完成后，继续执行函数A的剩余内容

变量作用域指的是变量的作用范围（变量在哪里可用，在哪里不可用）
主要分为两类：局部变量和全局变量
```python
def testA():
    num = 100
    print(num)

testA()     # 100
print(num)  # 报错：name 'num' is not defined.
```
局部变量的作用：在函数体内部，临时保存数据，即当函数调用完成后，则销毁局部变量。

所谓全局变量，指的是在函数体内、外都能生效的变量。
```python
num = 100

def testA():
    print(num)

def testB():
    print(num)

testA()     # 100
testB()     # 100
```

在函数体内可以修改全局变量吗？
```python
num = 200

def test_a():
    print(num)

def test_b():
    num = 500 # 变成了局部变量，和外部的没有任何联系
    print(num)

test_a()     # 100
test_b()     # 100
print(num)
```
可以使用global关键字
```python
num = 200

def test_a():
    print(num)

def test_b():
    # global 关键字，在函数内声明变量为全局变量
    global num
    num = 500
    print(num)

test_a()     # 100
test_b()     # 100
print(num)
```
```bash
200
500
500
```
