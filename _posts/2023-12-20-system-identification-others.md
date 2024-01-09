---
layout: post
title: "系统辨识：其他知识点整理"
date: 2024-01-08 20:00:00 +0800
categories: system_identification
---

# 数学基础

---
# 辨识的输入信号

最低要求：在辨识时间内，系统的动态必须被输入信号持续激励

常用输入信号：白噪声信号、伪随机信号

## 伪随机序列

M序列

对于r级移位寄存器，只要适当地选择反馈逻辑，就能产生最大长度为$2^r-1$的二位式周期序列，即M序列

本原多项式

---



# 系统阶次的辨识


## 多变量线性系统参数辨识

## 线性系统的结构辨识（定阶）

### Hankel矩阵定阶

过程的脉冲响应序列记作$g(1).g(2),\dots, g(L)$，

$$
H(l,k)=\begin{bmatrix}
g(k) & g(k+1) & \cdots & g(k+l-1)\\
g(k+1) & g(k+2) & \cdots & g(k+l)\\
\vdots & \vdots & & \vdots\\
g(k+l-1) & g(k+l) & \cdots & g(k+2l-2)\\
\end{bmatrix}
$$

$g(*)$为系统的脉冲响应值，$l$决定Hankel矩阵的维数，k可以在1至L-2l+2间任意选择

如果$l\ge n_0$（过程的真实阶次），则Hankel矩阵的秩等于过程的真实阶次$n_0$，即

$$
rank\left[H(l,k)\right]=n_0,l\ge n_0, \forall k \in [1, \dots , L-2l+2]
$$


### 最小信息准则（AIC准则）


设系统模型为

$$
y(k)=\sum^n_{i=1}a_iy(k-i)+\sum^n_{j=1}b_j u(k-j)+v(k)
$$

其中，$y(k),u(k)$分别为系统输出和输入量，$v(k)\sim N(0,\sigma^2_v)$是正态白噪声

对于N组观测值，上式的矩阵方程表达为

$$\begin{aligned}
&Y_N=H_N(n)\theta_n+V_N\\
&\theta_n=\left(a_1\quad\cdots\quad a_n\quad b_1\quad \cdots \quad b_n\right)^T
\end{aligned}
$$

AIC准则法中对参数向量$\theta_n$的辨识采用了极大似然估计（记为$\hat\theta_{ML}$），但在零均值高斯白噪声条件下，$\hat\theta_{ML}$与最小二乘估计$\hat\theta_{LS}$是一致的，即

$$
\hat\theta_{ML}=\hat\theta_{LS}=(H_N^T(n)H_N(n))^{-1}H^T_N(n)Y_N
$$

有噪声方差$\hat\sigma_v^2$的估计值为

$$
\hat\sigma_v^2(n)=\frac{1}{n}\left({Y}_N-{H}_N(n){\hat\theta}_{LS}\right)^T\left({Y}_N-{H}_N(n){\hat\theta}_{LS}\right)
$$

**AIC准则**定义为

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

*了解BIC准则如何构造*

## 模型检验

最后检验模型的标准应该是模型的实际应用效果。

## *系统辨识在自适应控制中的应用

# 智能辨识方法

## 神经网络

### 基本概念

### BP神经网络辨识

### Hopfield神经网络

## 遗传算法