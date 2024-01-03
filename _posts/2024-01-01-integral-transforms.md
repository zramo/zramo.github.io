---
layout: post
title: "积分变换知识点整理"
date: 2024-01-03 06:00:00 +0800
categories: math
---

# 7 傅里叶变换

## 单位脉冲函数($\delta$函数)

### 定义

称一个函数为$\delta$函数，并记之为$\delta(t)$，如果其满足

$$
\delta(t)=\begin{cases}
0, & t\neq 0\\
\infty, & t=0
\end{cases}
$$

$$
\int_{-\infty}^{+\infty}\delta(t)dt=1
$$

## 定义

### 积分变换
 
对函数 $f(t)$做某种积分变换, 就是指对它进行如下形式的含参变量的积分运算

$$
F(\tau)=\int^b_af(t)k(t,\tau)dt$$


其中的二元函数$k(t, τ )$称为积分核,$ −∞ ≤ a < b ≤ +∞$.

\begin{aligned}
$f(t)$ & \rightarrow&$F(\tau)$

原像函数&&像函数
\end{aligned}

积分核$k(t, τ )$的不同取法决定了不同的积分变换.

### 狄利克雷条件

 - 除去有限个第一类间断点外，处处连续

 - 分段单调，单调区间的个数有限

### 傅立叶级数
 
如果一个以T为周期的函数$f_T(t)$在$[-\frac{T}{2},\frac{T}{2}]$上满足狄利克雷条件,则$f_T(t)$的傅里叶级数

$$
f_T(t)\sim\frac{a_0}{2}+\sum^\infty_{n=1}[a_n\cos(n\omega t)+ b_n\sin(n\omega t)]$$

> t为连续点时$\sim$可改为$=$，参见泰勒展开

在$[-\frac{T}{2},\frac{T}{2}]$上处处收敛，且在$f_T(t)$的连续点处极数收敛于$f_T(t)$,其中

$$
\omega=\frac{2\pi}{T}\\
$$

$$
a_0=\frac{2}{T}\int^{\frac{T}{2}}_{-\frac{T}{2}}f_T(t)dt
$$

$$
a_n=\frac{2}{T}\int^{\frac{T}{2}}_{-\frac{T}{2}}f_T(t)\cos(n\omega t)dt (n = 1,2,3,\cdots)
$$

$$
b_n=\frac{2}{T}\int^{\frac{T}{2}}_{-\frac{T}{2}}f_T(t)\sin(n\omega t)dt (n = 1,2,3,\cdots)
$$

> 非周期函数计算傅立叶级数
> - 延拓
> - $T\rightarrow\infty$


### 傅氏积分定理


如果定义在$(-\infty, +\infty)$的函数$f(t)$满足下列条件


(1) $f(t)$在任一有限区间上满足狄利克雷条件


(2) $f(t)$在$(-\infty, +\infty)$上绝对可积，即

$$\int^{+\infty}_{-\infty}\vert f(t)\vert dt<+\infty$$

则$f(t)$的傅里叶积分公式收敛，且

$$
\frac{1}{2\pi}\int_{-\infty}^{+\infty}\left[\int_{-\infty}^{+\infty}f(t)e^{-i\omega t}dt\right]e^{i\omega t}d\omega=
\begin{cases}
f(t), & t是f(t)的连续点\\

\frac{f(t+0)+f(t-0)}{2}, &t是f(t)的第一类间断点
\end{cases}
$$


### 傅里叶变换

如果定义在$(-\infty, +\infty)$的函数$f(t)$的傅里叶积分公式成立,则称表达式

$$
F(\omega)=\int^{+\infty}_{-\infty}f(t)e^{-i\omega t}dt
$$

为$f(t)$的傅氏变换式,记作$F(\omega)=F[f(t)]$,称函数$F(\omega)$为$f(t)$的傅里叶变换;

称表达式

$$
f(t)=\frac{1}{2\pi}\int^{+\infty}_{-\infty}F(\omega)e^{i\omega t}d\omega
$$
为$F(\omega)$的傅氏逆变换式,记作$f(t)=F^{-1}F(\omega)$,称函数$f(t)$为$F(\omega)$的傅里叶逆变换

#### Tips

傅里叶变换公式(7.2.1)和逆变换公式(7.2.2)中的积分均应理解为柯西主值意义下的广义积分

在一些工程学科中, 例如电工学中, 为避免符号上的冲突, 傅里叶变换和逆变换定义式中的虚数单位 i 常改用符号 j 代替
 
在不同的教材上对傅里叶变换的定义在形式上常常有一些差别, 因为傅里叶变换公式(7.2.1)和逆变换公式(7.2.2)是从傅里叶积分公式

$$
f (t)=\frac{1}{2\pi}\int_{-\infty}^{+\infty}\left[\int_{-\infty}^{+\infty}f(\tau)e^{-i\omega \tau}d\tau\right]e^{i\omega t}d\omega$$


中拆分出来的, 只要把它们合在一起是傅里叶积分公式就行.
 
从几何的角度看, 求一个函数的傅里叶变换就是求它在坐标系 $\{e^{iωx}\}_{x∈R}$ 下的坐标,而逆变换就是由坐标还原函数的过程.

#### 常用函数的傅里叶变换
 
(阶跃函数)$$
F[u(t)]=\frac{1}{j\omega}+\pi\delta(\omega)$$

 
(单位脉冲函数)$$
F[\delta(t)]=1$$

 
$$
F[1]=2\pi\delta(\omega)$$

 
单位脉冲函数\delta(x)

#### 性质
 
筛选性$$
\int^{+\infty}_{-\infty}\delta(x-\xi)\varphi(x)dx=\varphi(\xi)$$

 
对称性$$
\delta(x-\xi)=\delta(\xi-x)$$

 
$\delta$函数与普通函数的乘积$$
f(x)\delta(x-\xi)=f(\xi)\delta(x-\xi)$$

 

设$ u(t) $是单位阶跃函数, 则$ u'(t) = δ(t)$.

 
$\delta(at)=\frac{1}{\vert a\vert }\delta(t)$, $a$为非零实数

## 广义傅里叶变换

### 需要记住的公式

|$F[\delta(t)]=1$ | $F^{-1}[1]=\delta(t)$ |
|:--:|:--:|
|$F[\delta(t-t_0)]=e^{-i\omega_0 t}$ | $F^{-1}[e^{-i\omega t_0}]=\delta(t-t_0)$|
| $F[1]=2\pi\delta(\omega)$ | $F^{-1}[2\pi\delta(\omega)]=1$ |
| $F[e^{i\omega_0 t}]=2\pi\delta(\omega-\omega_0)$ | $F^{-1}[2\pi\delta(\omega-\omega_0)]=e^{i\omega t_0}$ |

## 傅里叶变换的性质

### 线性性质

### 对称性质
 
$$
若已知F(\omega)=F[f(t)],则有

F[F(t)]=2\pi f(-\omega)$$


### 位移性质
 
$$
设F[f(t)]=F(\omega),则

F[f(t\pm t_0)]=e^{\pm i\omega t_0}F[f(t)]

F^{-1}[F(\omega\pm \omega_0)]=e^{\mp i\omega_0 t}f(t)$$


#### 推论
 
$F[\sin \omega_0t f(t)]=\frac{1}{2j}[F(\omega-\omega_0)-F(\omega+\omega_0)]$
 
$F[\cos \omega_0t f(t)]=\frac{1}{2}[F(\omega-\omega_0)+F(\omega+\omega_0)]$

### 微分性（时域）
 
$$
F[f^{(n)}(t)]=(j\omega)^nF(\omega), \vert t\vert \rightarrow+\infty, f^{(n-1)}(t)\rightarrow0$$


### 坐标缩放性质
 
设$a$是不等于$0$的实常数，若$F[f(t)]=F(\omega)$，则

$$

F[f(at)]=\frac{1}{\vert a\vert }F\left(\frac{\omega}{a}\right)
$$


### 乘积定理
 (see:帕塞瓦尔定理(能量积分/瑞利定理)) 
$$
若记F_1(\omega)=F[f_1(t)],F_2(\omega)=F[f_2(t)],则有

\begin{aligned}
\int^{+\infty}_{-\infty} f_1(t)f_2(t)dt
&=\frac{1}{2\pi}\int^{+\infty}_{-\infty}\overline{F_1(\omega)}F_2(\omega)d\omega

&=\frac{1}{2\pi}\int^{+\infty}_{-\infty} F_1(\omega)\overline{F_2(\omega)}d\omega
\end{aligned}
$$


### 帕塞瓦尔定理(能量积分/瑞利定理)
 

若记$F(\omega)=F[f(t)]$,则有

$$
\int^{+\infty}_{-\infty}[f(t)]^2dt=\frac{1}{2\pi}\int^{+\infty}_{-\infty}\vert F(\omega)\vert d\omega

$$


## 卷积

### 概念
 
定义:设函数$ f_1(t) $和$ f_2(t) $在$ (−∞, +∞) $上有定义,
 则称由下面的含参变量$ t $的广义积
分所确定的函数

$$
g(t)=\int^{+\infty}_{-\infty}f_1(\tau)f_2(t-\tau)d\tau$$


为函数$ f_1(t) 与 f_2(t) $的卷积, 记为

$$
g(t) = f_1(t)*f_2(t).$$


### 性质

#### 交换性质

#### 结合性质

#### 线性性质

#### 平移不变性质

#### 坐标缩放性质

#### 卷积定理

### 卷积在傅氏变换中的应用

#### 傅氏变换的微分定理

#### 傅氏变换的积分定理(卷积性质的推论)

# 8 拉普拉斯变换

## 概念
 
$$

L[f(t)]=\int
^{+\infty}_0f(t)e^{-st}dt=F(s)$$


## 常用函数的拉普拉斯变换
 
$$
L[e^{kt}]=\frac{1}{s-k}$$

 
$$
L[t^m]=\frac{m!}{s^{m+1}}$$
(m是自然数)
 
$$
L[u(t)]=L[1]=\frac{1}{s}$$

 
$$
L[\delta(t)]=1$$

 
$$
L[\sin kt]=\frac{k}{s^2+k^2}$$


$$
L[\cos kt]=\frac{s}{s^2+k^2}$$

 
$$

设f(t+T)=f(t)，则

L[f(t)]=\frac{1}{1-e^{-Ts}}\int^T_0f(t)dt$$


## 性质

### 微分性（时域）

### 积分性（时域）

### 位移性（时域）

### 位移性（频域）

## 几个积分公式
 
$$

 \int_{-\infty}^{+\infty}f(t)\delta(t)dt=f(0)
$$

 
$$

 \int_{-\infty}^{+\infty}f(t)\delta(t-t_0)dt=f(t_0)
$$

 
$$

 \int_{0}^{+\infty}f(t)e^{-kt}dt=L[f(t)]\vert _{s=k}
$$
