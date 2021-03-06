---
title: CSS-三大特性
top: false
cover: false
toc: true
mathjax: true
date: 2020-04-15 16:03:49
password:
summary:
tags: CSS基础
categories: CSS
---

# css三大特性

> 重叠性、继承性和权重选择

## 重叠性

> 对于同一个标签使用的样式，后面的样式会覆盖前面的样式

![](Snipaste_2020-04-13_10-13-24.png)

## 继承性

> 子标签会继承父标签的样式，主要是文字样式

![](Snipaste_2020-04-13_10-15-19.png)

![Snipaste_2020-04-13_10-18-06](Snipaste_2020-04-13_10-18-06.png)

## 权重

> 不同类型的选择器选择了相同的标签，会根据权重进行选择使用

| 选择器类型           | 权重    |
| -------------------- | ------- |
| 继承 或 通配符选择器 | 0,0,0,0 |
| 标签选择器           | 0,0,0,1 |
| 类选择器             | 0,0,1,0 |
| ID选择器             | 0,1,0,0 |
| 行内样式             | 1,0,0,0 |
| import               | 无穷大  |

![](Snipaste_2020-04-13_10-32-15.png)

![Snipaste_2020-04-13_10-32-34](Snipaste_2020-04-13_10-32-34.png)

**范围越小，权重越大**

## 注意

+ 继承的权重为0

![](/Snipaste_2020-04-14_09-43-14.png)

虽然span的父级的类选择器的权重比span标签选择器的权重高，但是span标签是继承父类选择器的权重为0

+ 关于a标签的继承

![](Snipaste_2020-04-14_09-48-03.png)

虽然a标签直接继承父级选折起的样式，但是颜色却没有变红，是应为浏览器默认给a标签加了一个样式(蓝色字体+下划线)

+ 权重叠加

![](Snipaste_2020-04-14_09-55-56.png)

虽然都选择了a标签，一个是`类选择器+标签选择器` ，另一个是`标签选择器` ,但是呈现的效果第一个选择器，是因为选择器权重的叠加(0,0,1,0) + (0,0,01) > (0,0,0,1), **请注意权重叠加不会产生进位，也就是六个标签选择器叠加也没有一个类选择器权重大，量变无法引起质变**