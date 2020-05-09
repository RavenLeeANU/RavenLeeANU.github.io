---
layout: post
title: 最小二乘法
categories: Blog
description: some word here
keywords: keyword1, keyword2
---

### 最小二乘法

#### 1.作用及问题描述

普通最小二乘法（ordinary least squares, OLS）是解决线性回归问题的一种有效方法，可应用于线性系统数据估计、预测等问题，推荐系统等方面。一元最小二乘法中设拟合直线为


![](http://latex.codecogs.com/gif.latex?y=ax+b)


已知观测点数据表示为

![](http://latex.codecogs.com/gif.latex?\{ x_i,y_i\})

i=1...n

#### 2.公式推导

构建平方关系的代价函数为

![](http://latex.codecogs.com/gif.latex?\epsilon=\sum_{i=1}^n(y_i-y'_i)^2)
且

![](http://latex.codecogs.com/gif.latex?\y'_i=ax_i+b)

根据构造关系可知，代价函数为凸，极值点在导数为0时存在极值（代价函数的判定方法为二阶Hessian矩阵半正定）。

因此令代价函数求一阶偏导为0

![](http://latex.codecogs.com/gif.latex?\frac {\partial \epsilon} {\partial a}=2\sum_{i=1}^n({-x_iy_i+ax_i^2+bx_i})=0)


![](http://latex.codecogs.com/gif.latex?\frac {\frac {\partial \epsilon} {\partial b}=2\sum_{i=1}^n({-y_i+ax_i)+nb}=0)

整理得到

![](http://latex.codecogs.com/gif.latex?\frac {\sum_{i=1}^n{x_iy_i =a\sum_{i=1}^n x_i^2 +b \sum_{i=1}^nx_i})


![](http://latex.codecogs.com/gif.latex?\frac {\sum_{i=1}^n{y_i}-a\sum_{i=1}^nx_i=nb)


令

![](http://latex.codecogs.com/gif.latex?\sum_{i=1}^n{x_i}= n\overline{x})


![](http://latex.codecogs.com/gif.latex?\sum_{i=1}^n{y_i}= n\overline{y})


则代入有

![](http://latex.codecogs.com/gif.latex?a = \frac {\sum_{i=1}^nx_iy_i - \overline{y}\sum_{i=1}^nx_i} {\sum_{i=1}^n x_i^2-\overline{x}\sum_{i=1}^n x_i})


![](http://latex.codecogs.com/gif.latex?b = \overline{y}-a\overline{x})


应用求和性质得到

![](http://latex.codecogs.com/gif.latex?a = \frac {\sum_{i=1}^nx_iy_i - n\overline{x} \overline{y}} {\sum_{i=1}^n x_i^2-n\overline{x}^2}=\frac{\overline{xy}-\overline{x} \cdot\overline{y}}{\overline{x^2}-\overline{x}^2})

#### 3.应用

通过当地气温预测粮食产量。

假设气温和粮食产量在某个区间呈现线性关系，此时可对往年数据进行线性拟合。

存在数据为

| 当地气温（°C） | 粮食产量（kg） |
| -------------- | -------------- |
| 25             | Content Cell   |
| 27             | 115            |
| 31             | 155            |
| 33             | 160            |
| 35             | 180            |



最终拟合结果为
![](http://latex.codecogs.com/gif.latex?\begin{array}{c}
a \approx 7.2  \\
b \approx -73
\end{array})


![](/images/posts/image-20200417104802318.png)

#### 4.相关链接

[最小二乘公式推导](https://blog.csdn.net/winone361/article/details/50713088)

[应用实例](https://blog.csdn.net/ccnt_2012/article/details/81127117?depth_1-utm_source=distribute.pc_relevant.none-task-blog-BlogCommendFromMachineLearnPai2-4&utm_source=distribute.pc_relevant.none-task-blog-BlogCommendFromMachineLearnPai2-4)



