---
layout: post
title: 朴素贝叶斯
categories: Blog
description: some word here
keywords: keyword1, keyword2
---

### 朴素贝叶斯

#### 1. 介绍

朴素贝叶斯用于解决两个用来解决两个条件概率之间的关系问题。其应用于量化评估，预测和分类等问题。

#### 2.基本原理

用后验概率去验证先验概率以获得假设的准确性。

贝叶斯公式用来描述两个条件概率之间的关系
$$
P(A|B) = \frac{P(B|A)P(A)}{P(B)}
$$
也即
$$
P(A|B) = \frac{P(B\cap A)}{P(B)}
$$
其关系如下图表示

![image-20200417112632618](D:\文档\个人文件\复习markdown\image-20200417112632618.png)

#### 3. 例子

垃圾邮件分类例子。通过关键词来判断邮件是否是垃圾邮件。我们想知道的是，一封出现“中奖”关键词的邮件，多大程度上是一封垃圾邮件。

| 关键词“中奖” | 邮件类别 |
| ------------ | -------- |
| No           | Email    |
| Yes          | Spam     |
| Yes          | Spam     |
| No           | Email    |
| No           | Spam     |
| Yes          | Spam     |
| No           | Email    |
| Yes          | Email    |
| No           | Email    |
| No           | Email    |

整理原式子
$$
p(垃圾邮件)=\frac{垃圾邮件}{所有邮件}=\frac{2}{5}\\
p(出现“中奖”)=\frac{出现“中奖”的邮件}{所有邮件}=\frac{2}{5}\\
p(出现“中奖”|垃圾邮件)=\frac{出现“中奖”的邮件}{所有垃圾邮件}=\frac{3}{4}\\
p(垃圾邮件|出现“中奖”)=\frac{垃圾邮件}{出现“中奖”的邮件}=\frac{p(出现“中奖”|垃圾邮件)p(垃圾邮件)}{p(出现“中奖”)}=\frac{3}{4}
$$

#### 4.相关链接

[例子来源](http://bluewhale.cc/2016-04-01/naive-bayesian.html)

[简单分类器](https://blog.csdn.net/weixin_40799076/article/details/86375192)

