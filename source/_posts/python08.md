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
 ### 一、列表（list）   
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

#### 列表的常用操作（方法）
1. 查找某元素的下标  
功能：查找指定元素再列表的小标，如果找不到，报错ValueError.
语法：列表.index(元素)
```python
list4 = ["小A","大S","迷你"]
# 1.查看元素下标：index
index = list4.index("大S")
print(f"1.大S在列表中的下标索引是：{index}")
# 2.在数组指定位置插入元素：insert
list4.insert(1,"雷欧克")
print(f"2.执行insert方法，新数组为{list4}")
# 3.在数组末尾插入元素：append 方法
list4.append("田七")
print(f"3.执行append方法，新数组为{list4}")
# 4.在数组末尾追加新的数组：extend
list5 = [1,2,3]
list4.extend(list5)
print(f"4.列表在追加元素之后的结果是：{list4}")

# 5.删除指定下标索引的元素（2种方式）
newList = ["小磊","Java","Python","CSS"]
# 5.1 方式1：del 数组[下标]
del newList[3]
print(f"5.1.使用del删除元素后为{newList}")
# 5.2 方式2：列表.pop(下标)
newList = ["小磊","Java","Python","CSS"]
element = newList.pop(0)
print(f"5.2.使用pop删除{element}后新数组为{newList}")
# 6.删除某元素在列表中的第一个匹配项：列表.remove(元素)
newList = ["小磊","Java","Python","Java","CSS"]
newList.remove("Java")
print(f"6.通过remove移除元素后结果为{newList}")
# 7.清空整个列表：clear
newList = ["小磊","Java","Python","CSS"]
newList.clear()
print(f"7.清空后的列表为{newList}")
# 8.统计某列表内某元素的数量:count
newList = ["Java","Java","Python","Java","Python"]
count = newList.count("Java")
print(f"8.列表中Java的数量为{count}")
# 9.统计列表中总共有多少个元素:len(数组名)
newList = ["Java","Java","Python","Java","Python"]
count = len(newList)
print(f"9.列表的元素数量总共有{count}个")
```
```bash
1.大S在列表中的下标索引是：1
2.执行insert方法，新数组为['小A', '雷欧克', '大S', '迷你']
3.执行append方法，新数组为['小A', '雷欧克', '大S', '迷你', '田七']
4.列表在追加元素之后的结果是：['小A', '雷欧克', '大S', '迷你', '田七', 1, 2, 3]
5.1.使用del删除元素后为['小磊', 'Java', 'Python']
5.2.使用pop删除小磊后新数组为['Java', 'Python', 'CSS']
6.通过remove移除元素后结果为['小磊', 'Python', 'Java', 'CSS']
7.清空后的列表为[]
8.列表中Java的数量为3
9.列表的元素数量总共有5个
```
学习编程，大多数方法是记忆不下来的，一般不需要刻意去记忆。我们要做的是，有一个模糊的印象，知晓有这样的用法即可。需要的时候，随时查阅资料即可。

经过上述的列表的学习，我们可以总结出列表有如下特点：  
1. 可以容纳多个元素（上限为2**63-1、9223372036854775807个）
2. 可以容纳不同类型的元素
3. 数据是有序存储的（有下标序号）
4. 允许重复元素存在
5. 可以修改（增加或删除元素等）  

练习：
![](https://cdn.jsdelivr.net/gh/panpan987/CDN@master/img/Snipaste_2023-07-29_21-00-01.png)  

#### 列表的循环遍历
```python
"""
演示对list列表的循环，使用while和for循环2种方式
"""

def list_while_func():
    newList = ["草稚京","雅典娜","菲欧娜"]
    index = 0
    while index < len(newList):
        element = newList[index]
        print(f"列表的元素：{element}")
        index = index + 1


def list_for_func():
    newList = ["早川秋","欧阳修","电次"]
    for element in newList:
        print(f"列表的元素有：{element}")


list_while_func()
list_for_func()
```
```bash
列表的元素：草稚京
列表的元素：雅典娜
列表的元素：菲欧娜
列表的元素有：早川秋
列表的元素有：欧阳修
列表的元素有：电次
```
练习： 
![](https://cdn.jsdelivr.net/gh/panpan987/CDN@master/img/Snipaste_2023-07-29_21-26-17.png)  

### 二、元组
列表是可以修改的。如果想要传递的信息，不被修改，列表就不合适了。   
元组同列表一样，都是可以封装多个、不同类型的元素在内。但最大的不同点在于：元组一旦定义完成，就不可以修改。
```python
# 定义元组
t1 = (1,"hello",True)
t2 = ()
t3 = tuple()

print(f"t1的类型是：{type(t1)}，内容是：{t1}")
print(f"t2的类型是：{type(t2)}，内容是：{t2}")
print(f"t3的类型是：{type(t3)}，内容是：{t3}")

# 定义单个元素的元组,注意后面加个逗号，否则是str类型
t4 = ("hello",)
print(f"t4的类型是：{type(t4)}，内容是：{t4}")
# 元组也可以嵌套的

# 元组可以通过下标索引定位具体元素

# 元组内如果有list，list内的内容是可以修改的
t9 = (1,2,["AA","BB"])
print(f"t9的内容是：{t9}")
t9[2][0] = "蔡文姬"
t9[2][1] = "马可波罗"
print(f"t9的内容是：{t9}")
```
```bash
t1的类型是：<class 'tuple'>，内容是：(1, 'hello', True)
t2的类型是：<class 'tuple'>，内容是：()
t3的类型是：<class 'tuple'>，内容是：()
t4的类型是：<class 'tuple'>，内容是：('hello',)
t9的内容是：(1, 2, ['AA', 'BB'])
t9的内容是：(1, 2, ['蔡文姬', '马可波罗'])
```  
练习：
![](https://cdn.jsdelivr.net/gh/panpan987/CDN@master/img/Snipaste_2023-07-29_21-54-13.png) 

### 三、字符串
```python
# 1.字符串下标索引
newStr = "Devil May Cry"
value1 = newStr[2]
value2 = newStr[-11]
print(f"1.从字符串{newStr}取下标为2的元素值为{value1}，下标-16的元素值为{value2}")
# 同元组一样，字符串是一个：无法修改的数据容器

# 2.index方法
value = newStr.index("May")
print(f"2.在字符串{newStr}中查找May,其起始下标是：{value}")

# 3.replace方法，将字符串里内容进行替换，得到一个新字符串
newNewStr = newStr.replace("May", "Must")
print(f"3.将字符串{newStr}替换后得到{newNewStr}")

# 4.split 字符串的分割，将字符串划分多个字符串，并存入列表对象中
newList = newStr.split(" ")
print(f"4.将字符串{newStr}进行切割后得到{newList}")

# 5.strip() 可以去除字符串前后空格
newStr1 = "    Devil May Cry     "
newNewStr1 = newStr1.strip()
print(f"5.1.字符串{newStr1}进行split切分后得到{newNewStr1}")

newStr2 = "123Devil May Cry321"
newNewStr2 = newStr2.strip("123")
print(f"5.2.字符串{newStr2}进行split切分后得到{newNewStr2}")

# 6.统计字符串中某个字符出现的次数
newStr = "Devil May Cry"
count = newStr.count("y")
print(f"6.字母y在{newStr}里出现了{count}次")

# 7.统计字符串的长度
newStr = "Devil May Cry"
cd = len(newStr)
print(f"7.字符串{newStr}的长度为{cd}")

```
```bash
1.从字符串Devil May Cry取下标为2的元素值为v，下标-16的元素值为v
2.在字符串Devil May Cry中查找May,其起始下标是：6
3.将字符串Devil May Cry替换后得到Devil Must Cry
4.将字符串Devil May Cry进行切割后得到['Devil', 'May', 'Cry']
5.1.字符串    Devil May Cry     进行split切分后得到Devil May Cry
5.2.字符串123Devil May Cry321进行split切分后得到Devil May Cry
6.字母y在Devil May Cry里出现了2次
7.字符串Devil May Cry加的长度为14
```

### 三-5序列
序列是指：内容连续、有序，可使用下标索引的一类数据容器。
列表、元组、字符串，均可以视为序列。
![](https://cdn.jsdelivr.net/gh/panpan987/CDN@master/img/Snipaste_2023-07-29_22-39-08.png)   
序列的常用操作：切片，即从一个序列中，取出一个子序列。
```python
# 对list进行切片，从1开始，4结束，步长1
my_list = [0,1,2,3,4,5,6]
result1 = my_list[1:4] # 默认步长1，所以可以省略不写
print(f"结果1：{result1}")


# 对tuple（元组）进行切片，从头开始，步长1可以省略
my_tuple = (0,1,2,3,4,5,6)
result2 = my_tuple[:]
print(f"结果2：{result2}")

# 对str进行切片，从头开始，到最后结束，步长2
my_str = "01234567"
result3 = my_str[::2]
print(f"结果3：{result3}")

# 对str进行切片，从头开始，到最后结束，步长-1
my_str = "01234567"
result4 = my_str[::-1]
print(f"结果4：{result4}")
```
```bash
结果1：[1, 2, 3]
结果2：(0, 1, 2, 3, 4, 5, 6)
结果3：0246
结果4：76543210
```

### 四、集合
不支持元素的重复，无序。使用{元素1，元素2，...}定义.
不支持下标索引访问，但可以修改元素。
```python
# 定义集合
my_set = {"Python","Java","Go","Go","Go","Html"}
my_set_empty = set()
print(f"my_set的内容是{my_set}")
print(f"my_set_empty的内容是{my_set_empty}")

# 添加新元素
my_set.add("C++")
my_set.add("Java")
print(f"my_set添加匀速后的结果是：{my_set}")

# 移除元素
my_set.remove("Html")
print(f"my_set移除Html结果是：{my_set}")

# 随机取出一个元素
my_set = {"Python","Java","Go","Go","Go","Html"}
element = my_set.pop()
print(f"集合被取出元素是：{element}，取出元素后集合是：{my_set}")

# 2个集合合并
set1 = {1,2,3}
set2 = {1,5,6}
set3 = set1.union(set2)
print(f"2个集合合并结果：{set3}")
print(f"2个集合合并后集合1结果：{set1}")
print(f"2个集合合并后集合2结果：{set2}")

# 集合的遍历。
# 集合不支持下标索引，索引不能用while循环
# 可以用for循环
set1 = {1, 2, 3, 5, 6}
for item in set1:
    print(f"集合的元素有：{item}")

```
```bash
my_set的内容是{'Java', 'Html', 'Go', 'Python'}
my_set_empty的内容是set()
my_set添加匀速后的结果是：{'Go', 'Java', 'C++', 'Html', 'Python'}
my_set移除Html结果是：{'Go', 'Java', 'C++', 'Python'}
集合被取出元素是：Java，取出元素后集合是：{'Html', 'Go', 'Python'}
2个集合合并结果：{1, 2, 3, 5, 6}
2个集合合并后集合1结果：{1, 2, 3}
2个集合合并后集合2结果：{1, 5, 6}
集合的元素有：1
集合的元素有：2
集合的元素有：3
集合的元素有：5
集合的元素有：6
```

### 五、字典
```python
# 定义字典   {key1: value1,key2:value2,...}
my_dict1 = {"大门":99,"猪猪":88,"八神":77}
# 定义空字典
my_dict2 = {}
print(f"字典1的内容是：{my_dict1}")
print(f"字典2的内容是：{my_dict2}")

# 字典中key不能重复，相同key的最后一个value会覆盖前面的value

# 从字典中基于key获取value
my_dict1 = {"大门":99,"猪猪":88,"八神":77}
score = my_dict1["猪猪"]
print(f"猪猪的考试成绩是：{score}")

# 字典可以嵌套的,如何表示下面数据
#  ——————————————————————————————
#  |  姓名  | 语文 | 数学  | 英语 |
#  | 叶湘伦 |  127 | 130  |  59  |
#  | 祝英台 |  105 | 140  |  116 |
#  | 罗密欧 |  96  | 146  |  89  |
#  ——————————————————————————————
stu_score_dict = {
    "叶湘伦": {
        "语文": 127,
        "数学": 130,
        "英语": 59
    }, "祝英台": {
        "语文": 105,
        "数学": 140,
        "英语": 116
    }, "罗密欧": {
        "语文": 96,
        "数学": 146,
        "英语": 89
    }
}
print(f"学生的考试信息是：{stu_score_dict}")

# 从嵌套字典中获取数据
# 查看罗密欧的数学成绩
lmo_sx = stu_score_dict["罗密欧"]["数学"]
print(f"罗密欧的数学成绩是：{lmo_sx}")
```
```bash
字典1的内容是：{'大门': 99, '猪猪': 88, '八神': 77} 
字典2的内容是：{}
猪猪的考试成绩是：88
学生的考试信息是：{'叶湘伦': {'语文': 127, '数学': 130, '英语': 59}, '祝英台': {'语文': 105, '数学': 140, '英语': 116}, '罗密欧': {'语文': 96, '数学': 146, '英语': 89}}
罗密欧的数学成绩是：146
```

```python
my_dict = {"小红": 99, "小美": 66, "小刚": 77}

# 新增元素
my_dict["小智"] = 55
print(f"字典经过新增元素后，结果是：{my_dict}")

# 更新元素
my_dict["小美"] = 99
print(f"字典经过更新元素后，结果是：{my_dict}")

# 删除元素
score = my_dict.pop("小美")
print(f"字典中被移除了一个元素，结果：{my_dict},小美的考试成绩是：{score}")

# 清空元素， clear
my_dict.clear()
print(f"字典被清空了，内容是：{my_dict}")

# 获取全部的key
my_dict = {"小红": 99, "小美": 66, "小刚": 77}
keys = my_dict.keys()
print(f"字典的全部key是{keys}")

# 遍历字典
# 方式1：通过获取全部的key来完成遍历
for key in keys:
    print(f"1.字典的key是：{key}")
    print(f"1.字典的value是：{my_dict[key]}")

# 方式2：直接对字典进行for循环，每一次循环都是直接得到key
for key in my_dict:
    print(f"2.字典的key是：{key}")
    print(f"2.字典的value是：{my_dict[key]}")

# 字典不可以使用while循环，因为字典不支持下标索引

# len(字典)计算字典内的元素数量
```
```bash
字典1的内容是：{'大门': 99, '猪猪': 88, '八神': 77}
字典2的内容是：{}
猪猪的考试成绩是：88
学生的考试信息是：{'叶湘伦': {'语文': 127, '数学': 130, '英语': 59}, '祝英台': {'语文': 105, '数学': 140, '英语': 116}, '罗密欧': {'语文': 96, '数学': 146, '英语': 89}}
罗密欧的数学成绩是：146
字典经过新增元素后，结果是：{'小红': 99, '小美': 66, '小刚': 77, '小智': 55}
字典经过更新元素后，结果是：{'小红': 99, '小美': 99, '小刚': 77, '小智': 55}
字典中被移除了一个元素，结果：{'小红': 99, '小刚': 77, '小智': 55},小美的考试成绩是：99
字典被清空了，内容是：{}
字典的全部key是dict_keys(['小红', '小美', '小刚'])
1.字典的key是：小红
1.字典的value是：99
1.字典的key是：小美
1.字典的value是：66
1.字典的key是：小刚
1.字典的value是：77
2.字典的key是：小红
2.字典的value是：99
2.字典的key是：小美
2.字典的value是：66
2.字典的key是：小刚
2.字典的value是：77
```
练习：
![](https://cdn.jsdelivr.net/gh/panpan987/CDN@master/img/Snipaste_2023-08-02_20-48-51.png)   



练习答案：
```python
# 组织字典记录数据
info_dict = {
    "王力鸿":{
        "部门": "科技部",
        "工资": 3000,
        "级别": 1
    },
    "周杰轮":{
        "部门": "市场部",
        "工资": 5000,
        "级别": 2
    },
    "林俊节":{
        "部门": "市场部",
        "工资": 7000,
        "级别": 3
    },
    "张学油":{
        "部门": "科技部",
        "工资": 4000,
        "级别": 1
    },
    "刘德滑":{
        "部门": "市场部",
        "工资": 6000,
        "级别": 2
    }
}
print(f"员工在升级加薪前的结果是：{info_dict}")

# for循环遍历字典
for name in info_dict:
    # if条件判断符合条件的员工
    if info_dict[name]["级别"] == 1:
        # 升职加薪
        # 获取员工的信息几点
        employee_info_dict = info_dict[name]
        # 修改员工信息
        employee_info_dict["级别"] = 2    # 级别+1
        employee_info_dict["工资"] += 1000    # 工资+1000
        # 将员工的信息更新回info_dict
        info_dict[name] = employee_info_dict

# 输出结果
print(f"对员工进行升级加薪后的结果是：{info_dict}")

```
```bash
员工在升级加薪前的结果是：{'王力鸿': {'部门': '科技部', '工资': 3000, '级别': 1}, '周杰轮': {'部门': '市场部', '工资': 5000, '级别': 2}, '林俊节': {'部门': '市场部', '工资': 7000, '级别': 3}, '张学油': {'部门': '科技部', '工资': 4000, '级别': 1}, '刘德滑': {'部门': '市场部', '工资': 6000, '级别': 2}}
对员工进行升级加薪后的结果是：{'王力鸿': {'部门': '科技部', '工资': 4000, '级别': 2}, '周杰轮': {'部门': '市场部', '工资': 5000, '级别': 2}, '林俊节': {'部门': '市场部', '工资': 7000, '级别': 3}, '张学油': {'部门': '科技部', '工资': 5000, '级别': 2}, '刘德滑': {'部门': '市场部', '工资': 6000, '级别': 2}}
```


## 总结
![](https://cdn.jsdelivr.net/gh/panpan987/CDN@master/img/Snipaste_2023-08-02_21-08-19.png) 

![](https://cdn.jsdelivr.net/gh/panpan987/CDN@master/img/Snipaste_2023-08-02_21-10-01.png) 

![](https://cdn.jsdelivr.net/gh/panpan987/CDN@master/img/Snipaste_2023-08-02_21-14-08.png) 


附录：
字符串比较是一位位按照ASCII码表进行比较的。