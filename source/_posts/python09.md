---
title: Python09
date: 2023-08-04 20:44:00
author: 小白学Python
img: https://cdn.jsdelivr.net/gh/panpan987/CDN@master/cover_img/small235848rbKch1690732728.jpg
categories: Python
tags:
  - Python
  - 基础
---

## 函数补充

### 函数的多返回值
```python
# 按照返回值的顺序，写对应顺序的多个变量接收即可
# 变量之间使用逗号隔开
# 支持不同类型的数据return
def test_return():
    return 1,"hello",True

x, y, z= test_return()
print(x)
print(y)
print(z)
```
```bash
1
hello
True
```
### 函数的多种传参方式
1. 位置参数：调用函数时根据函数定义的参数位置来传递参数 
```python
def user_info(name,age,gender):
    print(f'您的名字是{name}, 年龄是{age}, 性别是{gender}')

user_info('Tom', 17, '男')
```
```bash
您的名字是Tom, 年龄是17, 性别是男
```
2. 关键字参数：函数调用时通过“键=值”形式传递参数。
```python
def user_info(name,age,gender):
    print(f'您的名字是{name}, 年龄是{age}, 性别是{gender}')

# 关键字传参
user_info(name='Tom', age=17, gender='男')
# 可以不按照固定顺序
user_info(age=20,gender="男",name="小明")
# 可以和位置参数混用，位置参数必须在前，且匹配参数顺序
user_info('Tom', 17, gender='男')
```
```bash
您的名字是Tom, 年龄是17, 性别是男
您的名字是小明, 年龄是20, 性别是男
您的名字是Tom, 年龄是17, 性别是男
```
3. 缺省参数：缺省参数也叫默认参数，用于定义函数，为参数提供默认值，调用函数时可不传该默认参数的值（注意：所有位置参数必须出现在默认参数前，包括函数定义和调用）
```python
def user_info(name,age,gender='男'):
    print(f'您的名字是{name}, 年龄是{age}, 性别是{gender}')
# 不传就用默认值，传就使用传的值
user_info(name='小爱', age=13)
user_info(name='小李', age=15,gender='女')
```
```bash
您的名字是小爱, 年龄是13, 性别是男
您的名字是小李, 年龄是15, 性别是女
```
4. 不定长参数：不定长参数也叫可变参数，用于不确定调用的时候会传递多少个参数（不传参也可以）。当嗲用函数时不确定参数个数时，可以使用不定长参数。
```python
# 1. 位置不定长, *
# 传进的所有参数都会被args变量收集，它会根据传进参数的位置合并为一个元组，args是元组类型
def user_info1(*args):
    print(f"args参数的类型是：{type(args)}, 内容是：{args}")

user_info1(1,2,3,"小美","女孩")

# 2.关键字不定长, **
# 参数是"键=值"形式的，会根据"键-值"组成字典
def user_info2(**kwargs):
    print(f"kwargs参数的类型是：{type(kwargs)}, 内容是：{kwargs}")

user_info2(name="小王",age=11, gender='男',addr='安道尔')
```
```bash
args参数的类型是：<class 'tuple'>, 内容是：(1, 2, 3, '小美', '女孩')
kwargs参数的类型是：<class 'dict'>, 内容是：{'name': '小王', 'age': 11, 'gender': '男', 'addr': '安道尔'}
```

5. 函数作为参数传递。传入计算逻辑，而非传入数据。
```python
# 定义一个函数，接收另一个函数作为传入参数
def test_func(compute):
    result = compute(1, 2)
    print(f"compute参数的类型是：{type(compute)}")
    print(f"计算结果：{result}")

# 定义一个函数，准备作为参数传入另一个函数
def compute(x, y):
    return x+y
# 调用，并传入函数
test_func(compute)
```
```bash
compute参数的类型是：<class 'function'>
计算结果：3
```

### lambda匿名函数
函数的定义中
- def关键字，可以定义带有名称的函数
- lambda关键字，可以定义匿名函数（无名称）  
有名称的函数，可以基于名称重复使用。  
无名称的匿名函数，只可临时使用一次。
```python
# 定义一个函数，接受其它函数输入
def test_func(compute):
    result = compute(1,2)
    print(f"结果是：{result}")

# 通过lambda匿名函数的形式，将匿名函数作为参数传入
# lambda语法:
# lambda 传入参数：函数体（一行代码）
test_func(lambda x,y: x+y)
```
```bash
结果是：3
```




