---
title: Python08
date: 2023-06-09 20:00:00
author: 小白学Python
img: https://cdn.jsdelivr.net/gh/panpan987/CDN@master/cover_img/123916-1635741556813b.jpg
categories: Python
tags:
  - Python
  - 基础
---

 ## 数据容器
 一种可以容纳多份数据的数据类型，容纳的每一份数据称之为1个元素。每一个元素，可以是任意类型的数据，如字符串、数据、布尔等。  
 数据容器根据特点的不同，如：
 - 是否支持重复元素
 - 是否可以修改
 - 是否有序，等
 分为5类，分别是：
 列表（list）、元组（tuple）、字符串（str）、集合（set）、字典（dict）    
一层列表
```python
list1 = ['python', 'Java', 'html', 666, True]
print(list1)
```
```bash
['python', 'Java', 'html', 666, True]
```
嵌套列表
```python
list2 = [[1, 2, 3], [4, 5, 6]]
print(list2)
```
```bash
[[1, 2, 3], [4, 5, 6]]
```

如何从列表中取出特定位置的数据呢？  
我们可以使用：下标索引  
![](https://cdn.jsdelivr.net/gh/panpan987/CDN@master/img/Snipaste_2023-06-09_20-30-12.png)
如图：列表中的每一个元素，都有其位置下标索引，从前向后的方向，从0开始，依次递增，我们只需要按照下标索引，即可取得对应位置的元素。
```python
list3 = ['Python','Java','C++']
print(list3[0])
print(list3[1])
print(list3[2])
```
```bash
Python
Java
C++
```
列表的下标（索引）- 反向

![](https://cdn.jsdelivr.net/gh/panpan987/CDN@master/img/Snipaste_2023-06-11_17-47-26.png)
嵌套列表的下标（索引）
![](https://cdn.jsdelivr.net/gh/panpan987/CDN@master/img/Snipaste_2023-06-11_17-49-28.png)
```python
list4 = [[1,2,3],[4,5,6]]
print(list4[1][1])
```
```bash
5
```

### 列表的常用操作（方法）
  
