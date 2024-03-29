---
layout: post
title: "系统辨识：其他知识点整理"
date: 2024-01-08 20:00:00 +0800
categories: system_identification
---

# 数学基础

## 1 随机过程的数学描述

基本概念
时间过程分类
在现实世界中，人们可见到各种事物的随时间变化的过程，
其中主要有两类：
① 确定性过程：变化过程具有明确的规律性（如自由落体运
动、行星运行轨迹）
② 随机过程：变化过程具有偶然性，人们无法肯定地预料下一
时刻的变化情况（如风浪中的海面起伏高度、电子放大器零
点漂移），但该过程具有统计意义上的规律性（统计规律，
如同随机变量那样）


2、数学表达
$$
\{X(t),t\in T\}\quad(\leftrightarrow X(\omega,t)\in(\Omega, F, P))
$$

t 为时间，$\omega$为样本点（事件），$\omega\in\Omega$

说明：

①在每一固定时刻 t ，X（t）是随机变量

②当样本点ω固定时，X（ω，t）是一个确定的时间函数，称为此过程的一次实现（样本曲线），即 { X ( t ) } 可认为是一个随机函数，每时刻取值为随机变量的函数 。

例:$X(t)=a+\xi t$

③随机过程与随机变量的区别：后者与时间无关；但 X ( t ) = ξ
可以看成特别的随机过程，即不随时间变化的随机过程。

几种竞争性随机过程:
一群鸟的飞行轨迹;
股市的变化;
人的心理活动过程;
社会系统中的竞争性过程;


3、随机过程的概率分布

在研究随机现象时，曾引入了随机变量的概念，其统计规律由分布函数（或分布密度）表示：
$$
\xi:P(\xi<x)=F(x)=\int_{-\infty}^{x}f(t)dt\quad f(x)=F'(x)
$$
同理，在研究随机过程时，亦引进分布函数簇（密度函数簇）的概念

① 一维分布函数簇

② 二维分布函数簇

1维高斯分布
$$
f(x)=\frac{1}{\sigma\sqrt{2\pi}}e^{\frac{-(x-\mu)^2}{2\sigma^2}}
$$

2维高斯分布
$$
f(X)=\frac{1}{\vert\Sigma\vert2\pi}e^{-\frac{1}{2}(x-\mu)^T\Sigma^{-1}(X-\mu)}
$$


二、随机过程的数字特征
从实用角度，只介绍最基本的数字特征，只与$f(t:x),f(t_1,t_2;x_1,x_2)$有关的数字特征。
设随机过程 为$\textbf{X(t)}$，分布密度函数簇为$f(t:x),f(t_1,t_2;x_1,x_2)$

1、与$f(t:x)$有关的数字特征

均值函数 ： （ 中心曲线）
均方函数 ：
方差函数 ：
（表示偏离中心曲线的程度）
又记作

$$自相关函数R_x(t_1,t_2)=E\{X(t_1)X(t_2)\}=\int_{-\infty}^{+\infty}\int_{-\infty}^{+\infty}x_1x_2f(t_1,t_2;x_1,x_2)dx_1dx_2$$

三、平稳随机过程（随机过程中重要的一类）

## 2 白噪声过程

一、基本概念

1、直观定义：没有“记忆性”的随机过程。t 时刻取值与前后各个时刻的情况统计上不相关。

2、数学定义：均值为零，谱密度为非零常数的平稳随机过程。

二、白噪声序列（白噪声过程的离散形式）

1、定义：零均值、互不相关的平稳序列，即对于
有
则称
为白噪声序列。

2、谱密度
由离散的Fourier变换
为常数。

三、由白噪声生成的有色噪声

1、有色噪声的定义

即非白噪声，噪声在不同时刻可能是相关的。

2、有色噪声的一种生成方法

$$
e(k)=C(z^{-1})W(k)
$$

其中$\{W(k)\}$为白噪声，$C(z^{-1})=1+C_1z^{-1}+\cdots+C_nz^{-n}$

四、白噪声的产生方法

1、目的

对所建立的模型进行检验的一种重要方法是计算机仿真，这时随机噪声序列信号要由计算机产生，仿真结果的准确性要求产生的（伪）随机序列是较为准确的。

2、产生任意随机数的步骤

① 先产生在区间（0，1）上的均匀分布的随机数。计算机高级语言中有专用的函数和子程序，可直接调用。

② 由（0，1）均匀分布的随机数可以产生满足任意其他分布的随机数。


定理：若 为（0，1）上均匀分布的随机变量，F (x) 为任
意一种给定的连续分布函数，且 F (x) 有反函数 ，
则
是服从 F (x) 分布的随机变量。

3、正态随机变量
随机变量 ，其中
若 的分布密度为
称 为正态随机变量，记 为 满足分布

2
E Var , { }  
     
2


4、正态白噪声的计算机产生
产生 ：
设 为一串（0，1）区间上均匀分布的随机数，则
进一步说明：

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

AIC准则法虽然给时间序列模型的定阶带来了方便，但一般不能保证在数据长度$N\rightarrow\infty$时，阶估计值以概率1收敛到真实模型阶数。为了克服这种缺陷，又相继提出了BIC准则。

$$
BIC(n)=N\log\hat\sigma^2_v(n)+2n\log n
$$

*了解BIC准则如何构造*

## 模型检验

- 检验的标准
  - **最后检验模型的标准应该是模型的实际应用效果。**
  - 由于辨识得到的模型只能是近似的，期望会找到一个和实际系统完全一致的模型是不现实的。因此，只要辨识得到的模型其特性和实际系统基本一致，那么就应该认为该模型是可以接受的

- 检验方法
  - 利用在不同时间区段内采集的数据，分别建立模型。如果模型的特点（如零极点分布等）基本相符，则模型是可靠的。
  - 利用两组不同的数据，独立辨识出模型，并分别计算他们的损失函数，然后将两组数据交叉使用，再计算各自的损失函数。如果对应的损失函数没有明显变化，则模型是可靠的。
  - 增加辨识中使用的数据长度，如果损失函数不再显著下降，则模型是可靠的。
  - 检验模型与系统输出残差序列的白色性。如果残差序列可以视作零均值的白噪声序列，则认为模型是可靠的。

## *系统辨识在自适应控制中的应用

实现自适应控制是以系统辨识为基础的，获取被控对象的数学模型是自适应控制的关键之一


## 传递函数辨识的时域方法


# 智能辨识方法

## 神经网络

### 基本概念

### BP神经网络辨识

- 应用领域：

  - 基于神经网络的系统辨识

  - 神经网络控制器

  - 神经网络与其他算法（专家系统，模糊逻辑，遗传算法等）相结合

### Hopfield神经网络

旅行商问题

## 遗传算法

---

# 重点

## 绪论

最小二乘格式

辨识的步骤：阶次辨识->参数辨识->辨识的验证

## 数学基础

高斯白噪声均值为零方差为$\sigma^2$

脉冲传递函数 时域无限窄，频域无限宽

无法产生真正的高斯白噪声均值，故使用M序列

一般为了简化用M2序列

均值、方差、相关函数、均方值

**白噪声及其产生方法**

白噪声的统计特性

## 辨识的输入信号

**好的输入信号应该具有的特征**

**伪随机序列：M序列的产生**

最大长度2^n-1

最末一位必须参与运算（摩尔累加运算）

## 最小二乘法

加权最小二乘

递推最小二乘

遗忘因子法

克服野值的影响

克服饱和

克服有色噪声：增广最小二乘、广义最小二乘

**LS估计**

**LS估计的统计性质**

无偏，一致，有效

**WLS**

克服野值问题提出加权最小二乘WLS

**RLS**

**数据递推的饱和及解决方法**

抗饱和的措施：WRLS，**FF遗忘因子法（加权最小二乘法特例，即加权最小二乘也能克服数据饱和）**，限定记忆法，震荡记忆法（数据长度震荡，如在100~200之间波动）

**广义LS（GLS、GRLS，Generalized）**


**增广LS（ELS、ERLS）**：向量扩维，加入有色噪声参数进行最小二乘估计，包括系统模型和噪声模型


广义LS和增广LS克服有色噪声

广义LS和增广LS均存在误差累积问题

**最小二乘类辨识算法的比较**

## 传函辨识

时域方法会一种即可

e^{-1}

时域法
一阶惯性滞后环节的辨识
$K,\tau,T$

目测法知道$\tau$

稳态与输入之比为$K$（拉氏变换终值定理）

取0.632点求$T$

## 极大似然

给出均值求方差

## 阶次辨识(有)

三种准则原理公式

根据Hankel矩阵判定模型阶次

AIC准则

一开始不准，误差项占主导，之后后面阶次项占主导

BIC准则

## 智能辨识方法(有)

**重点掌握2种，根据关键公式讲清楚原理和应用实例**

**BP神经网络（Back Propagation）**

误差量

梯度下降反向传播


离散分类 

连续拟合回归

**Hopfield神经网络（课本）**

原理、如何装载数据，如何调整

**遗传算法**

编码

遗传交叉编译

## 基础

几种常见的数学模型，主要是线性模型

关键：化成最小二乘格式

获取数据->阶次辨识->参数辨识->辨识的验证


# 重重重点：

给一组数据用最小二乘算参数

## 不定项选择，基本概念的理解

系统阶次辨识三种方法

抗饱和的措施有哪些：遗忘因子法，限定记忆法，震荡记忆法，加权最小二乘法也能做到

优良估计具有的性质：无偏、有效、一致

最小二乘自成体系体现解决问题的xxx思维

极大似然函数写对 **极大化->求导数**

智能辨识：掌握1-2种

递推最小二乘考讲课过程中理解 残差新息 递推最小二乘缺点

## 计算

#### 几种方法的综合计算

先化成最小二乘格式提出$\theta$

## 简答

需要理解写公式

选择5
简答4
计算3个问

方法用英语缩写