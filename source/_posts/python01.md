---
title: Python01
date: 2023-05-14 13:59:00
author: Anduin
coverImg: /images/1.jpg
categories: Python
tags:
  - Python
  - 基础
---
## Python中常用6种数据类型
| 类型 | 描述 | 说明 |
| ---- | ---- | ---- |
| 数字（Number）| `支持：` <br> 整数（int）<br> 浮点数（float）<br> 复数（complex）<br> 布尔（bool）  | <br> 整数(int), 如：10、-3 <br> 浮点数(float), 如13.14，-3.15 <br> 复数，如4+3j <br> 布尔，True为真，False为假|
| 字符串(String) | 描述文本的一种数据类型 | 字符串(String)由任意数量的字符组成 |
| 列表（list）| 有序的可变序列 | Python里面使用最频繁的数据类型，可有序记录一堆数据 |
| 元组（Tuple） | 有序不可变序列 ||
|集合（set）| 无序不重复集合||
|字典（Dictionary）| 无序key-value集合||

## 变量
变量：在程序运行时，能存储计算结果或能表示值的抽象概念。简单来说，变量就是在程序运行时，记录数据用的。

```python
money = 20
print("钱包还有：",money)

money = money - 10
print("买了冰淇淋花费10元，还剩余：", money,"元")
```

## 字符串、数字转换
|语句（函数）|说明|
|----|----|
|int(x)| 将x转化为一个整数|
|float(x)| 将x转换为一个浮点数|
|str(x)|将对象x转换为字符串|

说明：万物皆可转字符串，因为万物带上双引号就是字符串，但是想将字符串转为数字，需要确保字符串的内容都是数字才可以。特别：整数也会转为浮点数，如 a = float（11），结果a=11.0; 浮点数也会转为整数，如b = int(3.1415), 结果b=3, 会丢失精度，即丢失掉小数的部分。

## 标识符
在Python中，我们可以给很多东西起名字，比如：
- 变量的名字
- 方法的名字
- 类的名字
- 函数的名字，等等

这些名字，我们统一称之为标识符，用来做内容的标识。

标识符的命名中，只允许出现：
- 英文
- 中文
- 数字
- 下划线 _

这四类元素，其余内容不被允许。
规则：1.不推荐使用中文；2.不可以用数字开头；3.大小写敏感；4.不可以使用关键字。
关键字在Python中都有特定的用途：
```html
False   True    None    and     as      assert   break    class
contine def     del     elif    else    except   finally  for 
from    global  if      import  in      is       lambda   nonlocal
not     or      pass    raise   return  try      while    with     yield

```

## 运算符
| 运算符|描述|实例|
|----|----|----|
| + | 加 | a + b |
| - | 减 | a - b |
| * | 乘 | a * b |
| / | 除 | a / b，如a=10,b=3,c=a/b,则c=3.3333333333333335 |
| // | 取整 | a//b，返回整数部分 |
| % | 取余 | a%b，返回余数部分 |
| ** | 指数 | a**b,如a=10,b=2,则10的平方为100 |

## 字符串的三种定义方式
- 单引号定义法：name = '张三'
- 双引号定义法：name = "张三"
- 三引号定义法：name = """张三"""

三引号定义法，和多行注释写法一样，同时支持换行操作。
使用变量接收它，它就是字符串，不使用变量接收它，就可以作为多行注释使用。
```python
# 使用 \ 这个转义字符可以把第二、三个引号的效力取消，使他们不再有定义字符串的效果，转为普通的字符串
name = "\"魂斗罗天下第一\""
```

## 字符串的拼接
字符串和字符串间的拼接
```python
print("PHP" + "是世界上最好的语言")
```
运行结果：
```bash
PHP是世界上最好的语言
```
字符串和变量之间的拼接
```python
name = "Java"
effect = "可以做网站后端"
print("我是" + name + "," + effect)
```
运行结果：
```bash
我是Java,可以做网站后端
```
如果变量是数字呢
```python
name = "小王"
address = "人民东路108号"
tel = 4006188080
print("我是" + name + ",我的地址是：" + address + ",我的电话是：" + tel)
```
运行结果：
```bash
print("我是" + name + ",我的地址是：" + address + ",我的电话是：" + tel)
TypeError: can only concatenate str (not "int") to str
```
字符串没有办法和数字完成拼接的，需要转化


## 字符串格式化
```python
anyu = "宝塔镇河妖"
message = "天王盖地虎, %s" % anyu
print(message)
```
运行结果：
```bash
天王盖地虎, 宝塔镇河妖
```
其中，%s
- % 表示：我要占位
- s 表示：将变量变成字符串放入占位的地方 

那，数字类型呢？可以用占位？
那必须可以的
```python
nf = 2023
zy = "计算机专业"
avg_salary = 17000
message = "根据大数据显示，%s年%s毕业的学生平均月薪为%s" % (nf, zy, avg_salary)
print(message)
```
```bash
根据大数据显示，2023年计算机专业毕业的学生平均月薪为17000
```
在Python中，其实支持很多的数据类型占位
最常用的是如下三类
|格式符号|转化|
|----|----|
|%s|将内容转化成字符串，放入占位位置|
|%d|将内容转换成整数，放入占位位置|
|%f|将内容转换成浮点型，放入占位位置|

```python
name = "panda电竞鼠标"
year = 2023
price = 19.99
message = "根据大数据显示,%d年这一款名为%s的产品售价仅仅需要%f元" % (year, name, price)
print(message)
```
```bash
根据大数据显示,2023年这一款名为panda电竞鼠标的产品售价仅仅需要19.990000元
```
