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

### $\delta$函数的性质

筛选性

$$
\int^{+\infty}_{-\infty}\delta(t-t_0)f(t)dt=f(t_0)
$$

 
对称性$$
\delta(x-\xi)=\delta(\xi-x)$$

 
$\delta$函数与普通函数的乘积
$$f(x)\delta(x-\xi)=f(\xi)\delta(x-\xi)$$

设$ u(t) $是单位阶跃函数, 则$ u'(t) = δ(t)$.
 
$$
\int^{+\infty}_{-\infty}\delta'(t)f(t)dt=
-\int^{+\infty}_{-\infty}\delta(t)f'(t)dt
$$

$$
\int^{+\infty}_{-\infty}\delta^{(n)}(t)f(t)dt=
(-1)^n\int^{+\infty}_{-\infty}\delta(t)f^{(n)}(t)dt
$$

$$
\delta(at)=\frac{1}{\vert a\vert}\delta(t)
$$

$$
\delta^{(n)}(-t)=(-1)^n\delta^{(n)}(t)
$$

### 弱意义下相等

若对于任意的在$(-\infty,+\infty)$上连续的函数$f(t)$，恒有

$$
\int_{-\infty}^{+\infty}f(t)\varphi(t)dt=
\int_{-\infty}^{+\infty}f(t)\psi(t)dt
$$

则称函数$\varphi(t)$与$\psi(t)$在弱意义下是**相等**的，记作$\varphi(t)\overset{\text{弱}}{=}\psi(t)$，或简记为$\varphi(t)=\psi(t)$


> 注意换元时若变量换元前后反号则需交换积分上下限

## 定义

### 积分变换
 
对函数 $f(t)$做某种积分变换, 就是指对它进行如下形式的含参变量的积分运算

$$
F(\tau)=\int^b_af(t)k(t,\tau)dt$$


其中的二元函数$k(t, τ )$称为积分核,$ −∞ ≤ a < b ≤ +∞$.

$$
\begin{aligned}
f(t) & \rightarrow&F(\tau)\\

原像函数&&像函数
\end{aligned}
$$

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

实际应用中常利用欧拉公式将傅氏积分公式转化为三角形式，即

$$
\begin{aligned}
f(t)=&\frac{1}{\pi}\int_{0}^{+\infty}\left[\int_{-\infty}^{+\infty}f(\tau)\cos\omega (t-\tau) d\tau\right]e^{i\omega t}d\omega
\end{aligned}
$$

> 计算中常用分部积分法
> $$
> \int udv=uv-\int vdu
> $$
> 对于定积分则有
> $$
> \int_a^b udv=uv\vert^b_a-\int^b_a vdu
> $$
> 证明：$(uv)'=u'v+uv'$移项后求不定积分


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


## 广义傅里叶变换

### 需要记住的公式

#### 常用函数的傅里叶变换
 
|$f(t)$|$F[f(t)]$|
|------|---------|
|阶跃函数$u(t)$|$\frac{1}{i\omega}+\pi\delta(\omega)$|
|单位脉冲函数$\delta(t)$|$1$|
|$1$|$2\pi\delta(\omega)$|
|$F[\delta(t)]=1$ | $F^{-1}[1]=\delta(t)$ |
|$F[\delta(t-t_0)]=e^{-i\omega_0 t}$ | $F^{-1}[e^{-i\omega t_0}]=\delta(t-t_0)$|
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
$$

$$
F[f(t\pm t_0)]=e^{\pm i\omega t_0}F[f(t)]
$$

$$
F^{-1}[F(\omega\pm \omega_0)]=e^{\mp i\omega_0 t}f(t)
$$

#### 推论
 
$F[\sin \omega_0t f(t)]=\frac{1}{2j}[F(\omega-\omega_0)-F(\omega+\omega_0)]$
 
$F[\cos \omega_0t f(t)]=\frac{1}{2}[F(\omega-\omega_0)+F(\omega+\omega_0)]$

### 微分性（时域）
 
$$
F[f^{(n)}(t)]=(j\omega)^nF(\omega), \vert t\vert \rightarrow+\infty, f^{(n-1)}(t)\rightarrow0$$


### 微分性（频域）

$$
\bf{F^{-1}[F^{(n)}(\omega)]=(-it)^nf(t)}
$$

### 坐标缩放性质
 
设$a$是不等于$0$的实常数，若$F[f(t)]=F(\omega)$，则

$$

F[f(at)]=\frac{1}{\vert a\vert }F\left(\frac{\omega}{a}\right)
$$


### 乘积定理
 (see:帕塞瓦尔定理(能量积分/瑞利定理)) 

若记$F_1(\omega)=F[f_1(t)],F_2(\omega)=F[f_2(t)]$,则有

$$
\begin{aligned}
\int^{+\infty}_{-\infty} f_1(t)f_2(t)dt
&=\frac{1}{2\pi}\int^{+\infty}_{-\infty}\overline{F_1(\omega)}F_2(\omega)d\omega\\

&=\frac{1}{2\pi}\int^{+\infty}_{-\infty} F_1(\omega)\overline{F_2(\omega)}d\omega
\end{aligned}
$$

### 帕塞瓦尔定理(能量积分/瑞利定理)
 

若记$F(\omega)=F[f(t)]$,则有

$$
\int^{+\infty}_{-\infty}[f(t)]^2dt=\frac{1}{2\pi}\int^{+\infty}_{-\infty}\vert F(\omega)\vert^2 d\omega

$$

### 微分性质

### 积分性质

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
 
|常用函数的拉普拉斯变换|
|--|
|$L[e^{kt}]=\frac{1}{s-k}$|
|$L[t^m]=\frac{m!}{s^{m+1}}$(m是自然数)|
|$L[u(t)]=L[1]=\frac{1}{s}$|
|$L[\delta(t)]=1$|
|$L[\sin kt]=\frac{k}{s^2+k^2}$|
|$L[\cos kt]=\frac{s}{s^2+k^2}$|

 

**周期函数的拉氏变换公式：**

$$
设f(t+T)=f(t)，则

L[f(t)]=\frac{1}{1-e^{-sT}}\int^T_0f(t)e^{-st}dt$$


## 性质

### 线性性质

设$\alpha, \beta$是常数，$F_1(s)=L[f_1(t)]$，，$F_2(s)=L[f_2(t)]$，则

$$
L[\alpha f_1(t)+\beta f_2(t)]=\alpha L[f_1(t)]+\beta L[f_2(t)]
$$

$$
L^{-1}[\alpha F_1(s)+\beta F_2(s)]=\alpha L^{-1}[F_1(s)]+\beta L^{-1}[F_2(s)]
$$

### 微分性质（时域）

若$L[f(t)]=F(s)$，假设$f^{(n)}(t)$存在且连续，则

$$
\begin{aligned}
L[f'(t)]&=\int_0^{+\infty}f'(t)e^{-st}dt\\
&=\left.f(t)e^{-st}\right\vert^{+\infty}_{0}-\int_0^{+\infty}f(t)de^{-st}\\
&=\left.f(t)e^{-st}\right\vert^{+\infty}_{0}+s\int_0^{+\infty}f(t)e^{-st}dt\\
&\bf{=sL[f(t)]-f(0)=sF(s)-f(0)\quad(Res>c_0)}\\
\end{aligned}
$$

**推论：** 对自然数$n$,有

$$
L[f^{(n)}(t)]=s^nL[f(t)]-s^{n-1}f(0)-s^{n-2}f'(0)-\cdots -f^{(n-1)}(0)
$$


### 微分性质（s域）

有拉氏变换存在定理，可以得到像函数的微分性质：

若$L[f(t)]=F(s)$，则

$$
F'(s)=L[-tf(t)]\quad(Res>c_0)
$$

一般地，对自然数$n$，有

$$
F^{(n)}(s)=(-1)^nL[t^nf(t)]\quad(Res>c_0)
$$

### 积分性质（时域）

设$F(s)=L[f(t)]$，则

$$
L\left[\int_0^tf(\tau)d\tau \right]=\frac{1}{s}F(s)
$$

一般地，有

$$
L\left[
    \begin{gathered}
    \underbrace{\int_0^tdt\int_0^tdt\cdots\int_0^t}&f(t)dt\\
    n次&
    \end{gathered}
    \right]=\frac{1}{s^n}F(s)
$$

### 积分性质（s域）

由拉氏变换存在定理，可以得到像函数的积分性质：

设$\lim\limits_{t\rightarrow 0^+}\frac{f(t)}{t}$存在，且积分$\int_s^\infty F(u)du$收敛，则

$$
\int_s^\infty F(u)du=L\left[\frac{f(t)}{t}\right]
$$

一般地，若$\lim\limits_{t\rightarrow 0}\frac{f(t)}{t^n}$存在，有

$$

\begin{gathered}
    L\left[\frac{f(t)}{t^n}\right]=&
    \underbrace{
        \int_s^{+\infty} ds\int_s^{+\infty} ds\cdots\int_s^{+\infty}
    }&
    F(s) ds,\quad n=1,2,\cdots\\
    &n次&
\end{gathered}
$$

**推论**

由像函数的积分性质有
$$
\begin{aligned}
\int_s^\infty F(u)du&=L\left[\frac{f(t)}{t}\right]\\
&=\int^{+\infty}_{0}\frac{f(t)}{t}e^{-st}dt
\end{aligned}
$$
即

$$
\begin{aligned}
\int_0^\infty F(u)du=\int^{+\infty}_{0}\frac{f(t)}{t}dt
\end{aligned}
$$

### 位移性质

若$L[f(t)]=F(s)$，则有

$$
L[e^{at}f(t)]=F(s-a),\quad (Re(s-a)>c_0)
$$

**证明：**

$$
\begin{aligned}
L[e^{at}f(t)]&=\int_0^{+\infty}e^{at}f(t)e^{-st}dt\\
&=\int_0^{+\infty}f(t)e^{-(s-a)t}dt\\
&=F(s-a)
\end{aligned}
$$

### 延迟性质

若$L[f(t)]=F(s)$，又$t<0$时$f(t)=0$，则对于任一非负实数$\tau$，有

$$
\begin{cases}
L[f(t-\tau)]=e^{-s\tau}F(s)\\
L^{-1}[e^{-s\tau}F(s)]=f(t-\tau)
\end{cases}
$$

### 相似性质

设$L[f(t)]=F(s)$，则对$a>0$有

$$
L[f(at)]=\frac{1}{a}F\left(\frac{s}{a}\right),\quad(Res>ac_0)
$$

定义换元证明之

### 初值和终值定理

$$
f(0^+)=\lim_{s\rightarrow\infty}sF(s)
$$

$$
f(+\infty)=\lim_{s\rightarrow 0}sF(s)
$$

### 卷积定理


**拉氏变换的卷积：**

$$
f_1(t)*f_2(t)=\int_0^tf_1(\tau)f_2(t-\tau)d\tau
$$


**定理：**假设$f_1(t),f_2(t)$满足拉氏变换存在定理中的条件，且$L[f_1(t)]=F_1(s)$，$L[f_2(t)]=F_2(s)$，则$f_1(t)*f_2(t)$的拉氏变换一定存在，且

$$
\begin{cases}
L[f_1(t)*f_2(t)]=F_1(s)F_2(s)\\
L^{-1}[F_1(s)F_2(s)]=f_1(t)*f_2(t)
\end{cases}
$$

<!--
## 几个积分公式

$$
 \int_{0}^{+\infty}f(t)e^{-kt}dt=L[f(t)]\vert _{s=k}
$$

拉普拉斯变换考试时必出一个大题
-->