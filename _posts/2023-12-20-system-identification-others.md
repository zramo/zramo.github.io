---
layout: post
title: "系统辨识：其他知识点整理"
date: 2023-12-20 06:00:00 +0800
categories: system_identification
---

# 系统阶次的辨识

## 多变量线性系统参数辨识

## 线性系统的结构辨识（定阶）

### Hankel矩阵定阶

$$
H(l,k)=\begin{bmatrix}
g(k) & g(k+1) & \cdots & g(k+l-1)\\
g(k+1) & g(k+2) & \cdots & g(k+l)\\
\vdots & \vdots & & \vdots\\
g(k+l-1) & g(k+l) & \cdots & g(k+2l-2)\\
\end{bmatrix}
$$

### 最小信息准则（AIC准则）

AIC准则定义为

$$
AIC(n)=N\log\hat\sigma^2_v(n)+4n
$$
使得上式达到最小值的$n$便被取为模型的阶次

AIC准则法虽然给时间序列模型的定阶带来了方便，但一般
不能保证在数据长度$N\rightarrow\infty$时，阶估计值以概率1收敛到真实
模型阶数。为了克服这种缺陷，又相继提出了BIC准则。

$$
BIC(n)=N\log\hat\sigma^2_v(n)+2n\log n
$$

了解BIC准则如何构造

## 模型检验

最后检验模型的标准应该是模型的实际应用效果。

## *系统辨识在自适应控制中的应用

# 智能辨识方法

## 神经网络

### 基本概念

### BP神经网络辨识

### Hopfield神经网络

## 遗传算法