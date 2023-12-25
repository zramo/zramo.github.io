---
layout: post
title: "智能控制：模糊控制总结"
date: 2023-12-14 06:00:00 +0800
categories: intelligent_control
---


概念表
|概念|含义|
|:--:|:--:|
|模糊关系|自返性关系、对称性关系、传递性关系|
|$\vee$|取大（逻辑或），如$0.5\vee 0.8=0.8$|
|$\wedge$|取小（逻辑与），如$0.8\wedge 0.6=0.6$|
|||



|概念|表达式|含义|
|:--:|:--:|:--:|
|并|$C=A\cup B$|$C_{ij}=\vee[a_{ij},b_{ij}]=a_{ij}\vee b_{ij}$，即逐元素取大|
|交|$C=A\cap B$|$C_{ij}=\wedge[a_{ij},b_{ij}]=a_{ij}\wedge b_{ij}$，即逐元素取小|
|补|$A\rightarrow\bar A$|$\bar A = [1-a_{ij}]$，即逐元素取补|
|乘（合成）|$C=A\circ B$|$C_{ij}=\mathop\vee\limits_{k=1}^{n}\left[a_{ik}\wedge b_{kj}\right]$，即按照矩阵乘法运算顺序先取小后取大|

**给出模糊矩阵，计算模糊矩阵的交、并与合成**


> ### 例题
> $$
> A=\begin{bmatrix}0.8&0.7\\0.5&0.3\end{bmatrix},
> B=\begin{bmatrix}0.2&0.4\\0.6&0.9\end{bmatrix}
> $$
> 
> $$
> \begin{aligned}
> A\circ B&=\begin{bmatrix}
> (0.8\wedge0.2)\vee(0.7\wedge0.6)&(0.8\wedge0.4)\vee(0.7\wedge0.9)\\
> (0.5\wedge0.2)\vee(0.3\wedge0.6)&(0.5\wedge0.4)\vee(0.3\wedge0.9)
> \end{bmatrix}\\
> &=\begin{bmatrix}
> 0.2\vee0.6&0.4\vee0.7\\
> 0.2\vee0.3&0.4\vee0.3
> \end{bmatrix}
> =\begin{bmatrix}
> 0.6&0.7\\
> 0.3&0.4
> \end{bmatrix}
> \end{aligned}
> $$
> 




普通集合中的运算性质除互补律外同样适用于模糊集合

Zadeh模糊集合理论不能满足互补律，即有
$$
\bar{A}\cup A\neq \Omega\\
\bar{A}\cap A\neq \empty
$$

$A\circ B$类似于矩阵乘法运算，12取小，01取大

<img title="模糊控制器的各个部分含义" src="\assets\images\intelligent_control\fuzzy_controller.svg" alt="" data-align="center">

画**模糊控制器的结构框架**（模糊化 推理 反模糊）


**量化因子和比例因子的计算**

常见的推理方式填空（近似（假言）、条件、多输入、多输入多规则）

**给出模糊关系方程，求出解**

清晰化方法（最大隶属度方法、加权平均法（重心法））

连续的考过了，可能考离散的

给出量化表（即为离散的隶属度函数）、规则表U，要看明白

大题：模糊控制器的设计

模糊计算题：
    关系方程的解
    多输入多规则推理
    模糊集合的合成、取大取小、交并补计算

拓扑图和拉普拉斯连通性的计算
给出邻接矩阵判断连通性，阐述矩阵性质（可能给出联合连通图）

**消顶法的理论推导：不懂要问**

一阶系统的一致性问题和跟踪控制问题理论推导

