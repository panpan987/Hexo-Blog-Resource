---
title: Python02
date: 2023-05-14 23:15:00
author: Anduin
coverImg: /images/2.jpg
categories: Python
tags:
  - Python
  - 基础
---

## 字符格式化 - 数字精度控制
我们可以使用辅助符号 m.n 来控制数据的宽度和精度
- m, 控制宽度，要求是数字，设置的宽度小于数字自身，不生效
- n, 控制小数点精度，要求是数字，会进行四舍五入
示例
- %5d: 表示将整数的宽度控制在5位，如数字11，被设置为5d，就会变成：【空格】【空格】【空格】11，用三个空格补足宽度
- %5.2f: 表示宽度为5，小数点精度为2  
小数点和小数部分也算入宽度计算，如11.345设置了%7.2f后，结果是【空格】【空格】11.35。2个空格补足宽度，小数部分限制2位精度后，四舍五入为.35
- %.2f: 表示不限制宽度，只设置小数点精度为2，如11.345设置%.2f后，结果是11.35

## 字符串的格式化2
之前使用 % 占位，还可以使用f"内容{变量}"进行快速格式化
```python
name = "苹果17"
year = 2023
month = 6
price = 6999.99
print(f"一个叫做{name}的手机,{year}年{month}月上市，价格为：{price}")
```
运行结果：
```bash
一个叫做苹果17的手机,2023年6月上市，价格为：6999.99
```
股票练习题
```python
name = "无忧旅馆"
stock_price = 19.99
stock_code = "003032"
stock_price_daily_growth_factor = 1.2
growth_days = 7

finally_stock_price = stock_price * stock_price_daily_growth_factor ** growth_days

print(f"公司：{name},股票代码：{stock_code},当前股价：{stock_price}")
print("每日增长系数：%.1f,经过%d天的增长后，股价达到了：%.2f" % (stock_price_daily_growth_factor,growth_days,finally_stock_price))
```
运行结果：
```bash
公司：无忧旅馆,股票代码：003032,当前股价：19.99
每日增长系数：1.2,经过7天的增长后，股价达到了：71.63
```

## input语句
获取键盘输入
```python
print("请告诉我你是谁?")
name = input()
print("我知道了，你是：%s" % name)
```
运行结果：
```bash
请告诉我你是谁?
安度因
我知道了，你是：安度因
```


