---
layout: post
title: "系统辨识理论英文术语整理"
date: 2023-12-06 06:00:00 +0800
categories: system_identification
---

# 最小二乘

三条性质：无偏性、有效性、一致性

加权最小二乘法可以克服数据饱和问题

## 增广最小二乘法(Extended LS)

新息
$$
\hat{e}(i)=z(i)-\textbf{h}^T(i)\hat{\bold\theta}(i-1)
$$

//通过扩维的技巧

$$
\begin{cases}
\hat{\bold\theta}(k)=\hat{\bold\theta}(k-1)+\bold{K}(k)\left(z(k)-\textbf{h}^T(k)\hat{\bold\theta}(k-1)\right)\\
\bold{K}(k)
\end{cases}
$$

## 英文术语

增广最小二乘法 Extended LS



# 极大似然估计方法