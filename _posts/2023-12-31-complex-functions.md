---
layout: post
title: "复变函数知识点整理"
date: 2023-12-01 06:00:00 +0800
categories: math
---
# 1 复数与复变函数

## 复数

### 运算

- 加法

- 减法

- 乘法
 
- 复数的模或绝对值记为$\vert z\vert=\sqrt{a^2+b^2}$

- 辐角
 
    - 辐角${\rm Arg}\, z = \arg z + 2k\pi , k = 0, \pm 1, \pm 2, \cdots$
    
    - 主辐角$\arg z$

## 复变函数及其极限与连续

### 复平面上的点集

|概念|写作|定义|
|:--:|:--:|:--:|
|$z_1,z_2$两点的**距离**|$\vert z_1-z_2\vert$|$\vert z_1-z_2\vert=\sqrt{(x_1-x_2)^2+(y_1-y_2)^2}$|
|$z_0$点的$\delta$**邻域**|$U_{\delta}(z_0)$|以$z_0$为心，$\delta>0$为半径的圆的内部，即$U_{\delta}(z_0)=\lbrace z \vert\vert z-z_0\vert<\delta \rbrace$|
|**内点**||属于平面点集$E$的点$z_0$，若它的某个邻域$U_{\delta}(z_0)\subset E$，则称$z_0$点为$E$的内点|
|集$E$的极限点(或**聚点**)||$z_0$点的任一邻域内都含有集$E$的无穷多个点|
|界点||$z_0$点的任一邻域内既有属于$E$的点，又有不属于$E$的点|
|**边界**|$\partial E$|$E$的所有界点组成的集合|
|开集||集合$E$的每个点都是内点|
|连通的||对集$E$中任意两点总存在一条属于E的折线连接这两点|
|**区域**|$D$|**非空**平面点集$D$，是**连通的开集**|
|闭区域|$\bar{D}$|$D\cup \partial D = \bar{D}$|
|连续曲线||设曲线$C$的参数方程$z=z(t)=x(t)+iy(t)\quad (a\le t \le b)$，若$x_t,y_t$在$a\le t \le b$上连续，称$C$为连续曲线|
|简单曲线||当$a < t_1 \neq t_2 < b$时，$z(t_1) \neq z(t_2)$，即曲线$C$无重点|
|简单闭曲线||$z(a)=z(b)$（头连尾）|
|光滑曲线||$x'(t),y'(t)$连续且$z'(t)=x'(t)+iy(t)\neq 0$|
|按(分)段光滑曲线||曲线$C$由有限条光滑曲线组成|
|**单连通区域**||区域$D$内任何一条简单闭曲线的内部的所有点仍属于$D$|
|**多(复)连通区域**||单连通区域条件不成立|

### 复变函数的定义

### 复变函数的极限与连续



# 2 解析函数

## 解析函数的概念

### 复变函数解析的概念
 
**定义**

##### 可导/可微
 
$$

\lim_{z\rightarrow z_0}\frac{f(z)-f(z_0)}{z-z_0}
$$


##### 函数在区域内解析与在区域内可导是等价的

##### 函数在一点处可导,不一定在该点处解析

## 函数解析的充要条件
 
### 函数解析性的判定

柯西黎曼条件
$$
\frac{\partial u}{\partial x}=\frac{\partial v}{\partial y},\frac{\partial u}{\partial y}=-\frac{\partial v}{\partial x}$$

 
**定理:** 设$f(z)=u(x,y)+iv(x,y)$是区域D上的复变函数,则函数$f(z)$在$D$内一点$z=x+iy$处可导的充要条件是:

$u(x,y)$和$v(x,y)$在此点$(x,y)$可微,而且满足C-R方程.

### 复变函数的导数形式

若函数$f(z)=u(x,y)+iv(x,y)$可导，则其导数

$$
\begin{aligned}
f'(z)&=
\frac{\partial u}{\partial x} + i\frac{\partial v}{\partial x}=
\frac{\partial v}{\partial y} + i\frac{\partial v}{\partial x}\\&=
\frac{\partial v}{\partial y} - i\frac{\partial u}{\partial y}=
\frac{\partial u}{\partial x} - i\frac{\partial u}{\partial y}
\end{aligned}
$$

## 调和函数

### 解析函数有任意阶导数(第三章证明)
 
拉普拉斯方程

$$
\frac{\partial^2u}{\partial x^2}+\frac{\partial^2u}{\partial y^2}=0,\frac{\partial^2v}{\partial x^2}+\frac{\partial^2v}{\partial y^2}=0$$

 
**定义:** 凡在区域D内有二阶连续偏导数且满足拉普拉斯方程的二元实函数$u(x,y)$,称为区域D内的**调和函数**
 
**定理:** 设函数$f(z)=u(x,y)+v(x,y)$在区域D内解析,

则$f(z)$的实部$u(x,y)$和虚部$v(x,y)$都是区域D内的**调和函数**
 
**定义:** 在区域D内满足C-R方程的两个调和函数$u,v$中,

$v$称为$u$的**共轭调和函数**

### 曲线簇
 
**推论:** 解析函数可以把它写成只关于$z$的表达式

(化简完成后的表达式不含$\overline{z}$)

## 初等函数

### 指数函数
 
$$
e^z=e^{x+i y}=e^x(\cos y + i \sin y)$$

 
$$
(e^z)'=e^z$$


### 三角函数
 
$$
\sin z = \frac{e^{iz}-e^{-iz}}{2i}, \cos z = \frac{e^{iz}+e^{-iz}}{2}$$


### 双曲正弦余弦

### 对数函数

# 3 复变函数的积分

## 概念
 
$$
\int_c f(z)dz=\lim_{n\rightarrow \infty}f(\xi_k)\Delta z_k$$

,c是光滑曲线

### 复变函数的积分实际上是复平面上的线积分

##  性质
 
$$
\int_c f(z)dz=-\int_{c^{-1}} f(z)dz
$$

($c^{-1}$与$c$的方向相反)
 
$$
\int_c [\alpha f(z) + \beta g(z)]dz=\alpha\int_c f(z)dz+\beta\int_c f(z)dz
$$

 ,$\alpha,\beta$ 是常数
 
若曲线$c$由$c_1$与$c_2$连接而成，则$$
\int_c f(z)dz=\int_{c_1} f(z)dz+\int_{c_2} f(z)dz$$


## 复变函数积分的一般计算法

### 化为线积分
 
$$
\int_c f(z)dz=\int_c udx-vdy+i \int_c vdx+udy$$
(常用于理论证明)

### 参数方法
 
设曲线$$
c:z=z(t)(\alpha \le t \le \beta)$$
,其中$\alpha$对应曲线c的起点, $\beta$对应曲线c的终点,则

$$
\int_c f(z)dz=\int^\beta_\alpha f[z(t)]z'(t)dt$$


## 关于复变函数积分的重要定理与结论
 
$$
\int_c \frac{dz}{(z-z_0)^n}=
\begin{cases}
2\pi i, n = 1\\
0, n \neq 0
\end{cases}
$$


### 柯西基本定理
 
设$f(z)$在单连通域$B$内解析,$c$为$B$内任意一条闭曲线,则$$
\oint_cf(z)dz=0$$

 (see:) 
$f(z)$是单连通域$D$内的一个解析函数，而$C_1$和$C_2$是连接$z$和$z_0$的任意两条逐段光滑曲线，
则$$
\int_{C_1}f(z)dz=\int_{C_2}f(z)dz$$


### 复合闭路定理
 
设f(z)在多连通域D内解析,c为D内任意一条简单闭曲线,

$ c_1, c_2, \cdots, c_n$是c内的简单闭曲线,它们互不包含互不相交，

并且以$ c_1, c_2, \cdots, c_n$为边界的区域全含于D内,则

①$
\oint_c f(z)dz=\sum^n_{k=1}\oint_{c_k}f(z)dz$
, 其中$c$与$c_k$均取正向;

②$
\oint_\Gamma f(z)dz = 0$，其中$\Gamma$是由$c$及$c^{-1}(k=1,2,\cdots, n)$所组成的复合闭路


### 闭路变形原理
 
一个在区域D内的解析函数f(z)沿闭曲线c的积分,

不因c在D内作连续变形而改变它的值，

只要在变形过程中c不经过使f(z)不解析的奇点

### 解析函数沿非闭曲线的积分

#### xx

# 4 级数

## 复变函数项级数

### 复数序列

#### 定义
 
复数序列$\{z_n\}$收敛于极限$z_0$，

记作$$
\lim_{n\rightarrow \infty}z_n=z_0$$
或$$
z_n\rightarrow z_0; n\rightarrow +\infty$$


#### 定理

##### 极限

##### 4.1.2

### 复数项级数

#### 定义

##### 复数项级数

##### 部分和

###### 收敛的

###### 发散的

###### 和

#### 定理
 
 - 复数项级数 $
   \sum^{\infty}_{n=1}z_n(z_n=a_n+i b_n,n=1,2,\cdots)$收敛的充分必要条件是

   - 实数项级数 $\sum^{\infty}_{n=1}a_n$ 和级数 $\sum^{\infty}_{n=1}b_n$ 同时收敛
 
 - 复数项级数 $\sum^{\infty}_{n=1}z_n$ 收敛的必要条件是 $\lim_{n\rightarrow \infty} z_n=0$ 

 
 - 给定复数项级数 $\sum^{\infty}_{n=1}z_n$ ,其中 $z_n=a_n+i b_n,n=1,2,\cdots$ .

   - 若正项级数 $\sum^{\infty}_{n=1}\vert z_n\vert $ 收敛,称级数 $\sum^{\infty}_{n=1}z_n$ 是绝对收敛的.

   - 若级数 $\sum^{\infty}_{n=1}z_n$ 收敛,而正项级数 $\sum^{\infty}_{n=1}\vert z_n\vert $ 发散,称级数 $\sum^{\infty}_{n=1}z_n$ 是条件收敛的.

##### 每个绝对收敛的复数项级数其本身一定是收敛的——该定理的逆不成立

### 复变函数项级数

#### 定义

##### 复变函数项级数

##### 收敛域

##### 和函数

#### 定理
 
若复变函数$f_n(z)(n=1,2,\cdots)$均定义在集合$E$上,且有不等式$\vert f_n(z)\vert  \le M_n(n = 1, 2, \cdots)$成立.

如果正项级数$\sum^{\infty}_{n=1}M_n$收敛,则复变函数项级数$\sum^{\infty}_{n=1}f_n(z)$在集合$E$上**一致收敛**
 
若复变函数$f_n(z)(n=1,2,\cdots)$均在区域$D$内连续,且级数$\sum^{\infty}_{n=1}f_n(z)$在$D$内一致收敛于和函数$s(z)$,则$s(z)$在$D$内处处连续

##### 4.1.8

###### 即若一致收敛,可先积分再求和

##### 4.1.9

## 幂级数

### 幂级数的概念

#### 阿贝尔(Abel)定理

### 幂级数的收敛圆与收敛半径

#### 定义

##### 收敛圆

##### 收敛半径

#### 定理

##### 达朗贝尔法则或检比法
 

对于幂级数

$$
\sum^{\infty}_{n=0}a_n(z-z_n)^n
$$

,若极限

$$
\lim_{n \rightarrow \infty} \left\vert  \frac{a_{n+1}}{a_n}\right\vert  =\lambda
$$

(包括$\lambda$ 为0或$+\infty$ 的情形)

,则它的收敛半径

$$
R=\begin{cases}
+\infty, &\text{$\lambda=0$}\\

\frac{1}{\lambda}, &\text{$0 < \lambda < +\infty$}\\

0, & \text{$\lambda=+\infty$}
\end{cases}
$$

##### 柯西法则或检根法
 

对于幂级数

$$
\sum^{\infty}_{n=0}a_n(z-z_n)^n
$$

,若极限

$$
\lim_{n \rightarrow \infty} \sqrt[n]{\vert a_n\vert }=\lambda
$$

(包括$\lambda$为0或$+\infty$的情形)

,则它的收敛半径

$$
R=\begin{cases}
+\infty, &\text{$\lambda=0$}\\

\frac{1}{\lambda}, &\text{$0 < \lambda < +\infty$}\\

0, & \text{$\lambda=+\infty$}
\end{cases}
$$

### 幂级数的运算
 
$$
f(z)\pm g(z)=\sum_{n=0}^\infty a_nz_n\pm \sum_{n=0}^\infty b_nz_n=\sum^\infty_{n=0}(a_n\pm b_n)z^n,\ \ \vert z\vert <R=min\left\{R_1,R_2\right\}$$

 
$$

\begin{aligned}
f(z)g(z)&=\left(\sum^\infty_{n=0}a_nz^n\right)\left(\sum_{n=0}^\infty b_nz^n\right)=\sum^\infty_{n=0}\left(\sum^\infty_{k=0}a_kz_k\cdot b_{n-k}z^{n-k}\right)

&=\sum^\infty_{n=0}c_nz^n,\ \ c_n=\sum^\infty_{k=0}a_kb_{n-k}

&=\sum^\infty_{n=0}\left(\sum^\infty_{k=0}a_kb_{n-k}\right)z^n

&,R\ge min\{R_1,R_2\}

\end{aligned}
$$

 
$$
f[g(z)]=\sum_{n=0}^\infty a_n[g(z)]^n,\ \ \vert g(z)\vert <R_1$$


## 泰勒级数

### 泰勒展开
 
设函数$f(z)$在圆域$\vert z-z_0\vert <R$内解析,

则在此圆域内$f(z)$可以展开成幂级数

$$
f(z)=\sum^{\infty}_{n=0}\frac{f^{(n)}(z_0)}{n!}(z-z_0)^n$$
,

并且此展开式是唯一的
 
若$f(z)$在$z_0$解析，则$f(z)$在$z_0$的泰勒展开式成立的圆域的收敛半径$R=\vert z_0-a\vert $;

其中$R$为从$z_0$到$f(z)$的距$z_0$最近一个奇点$a$之间的距离
 
常用函数在$z_0=0$的泰勒展开式
 
$$
e^z=\sum^\infty_{n=0}\frac{1}{n!}z^n=1+z+\frac{z^2}{2!}+\frac{z^3}{3!}+\cdots+\frac{z^n}{n!}+\cdots$$
, $$
\vert z\vert <\infty$$

 
$$
\frac{1}{1-z}=\sum^\infty_{n=0}z^n=1+z+z^2+\cdots+z^n+\cdots$$
, $$
\vert z\vert <1$$

 
$$
\sin z=\sum^\infty_{n=0}\frac{(-1)^n}{(2n+1)!}z^{2n+1}=z-\frac{z^3}{3!}+\frac{z^5}{5!}-\cdots+\frac{(-1)^n}{(2n+1)!}z^{2n+1}+\cdots$$
, $$
\vert z\vert <\infty$$

 
$$
\cos z=\sum^\infty_{n=0}\frac{(-1)^n}{(2n)!}z^{2n}=z-\frac{z^2}{2!}+\frac{z^4}{4!}-\cdots+\frac{(-1)^n}{(2n)!}z^{2n}+\cdots$$
, $$
\vert z\vert <\infty$$


### 解析函数展开成泰勒级数的方法

#### 直接法
 
直接求出$$
c_n=\frac{f^{(n)}(z_0)}{n!}$$
,于是$$
f(z)=\sum^{\infty}_{n=0}c_n(z-z_0)^n$$


#### 间接法

##### 利用已知函数的泰勒展开式及幂级数的代数运算、复合运算和逐项求导、逐项求积等方法将函数展开

## 洛朗级数

### 洛朗级数的概念
 
$$
\sum^{\infty}_{n=-\infty}c_n(z-z_0)^n$$
，含正幂项和负幂项

### 洛朗展开定理
 
$$

设函数f(z)在圆环域R_1<\vert z-z_0\vert <R_2内处处解析，c为圆环域内绕z_0的任意一条正向简单闭曲线，

则在此圆环域内，有f(z)=\sum^\infty_{n=-\infty}c_n(z-z_0)^n，且展开式唯一
$$


### 解析函数的洛朗展开法

#### 洛朗级数一般只能用间接法展开

### 利用洛朗级数求围线积分
 
$$

设f(z)在r<\vert z-z_0\vert <R内解析，c为r<\vert z-z_0\vert <R内的任何一条正向简单闭曲线，

则\oint_cf(z)dz=2\pi ic_{-1}。其中c_{-1}为f(z)在r<\vert z-z_0\vert <R
内洛朗展开式中\frac{1}{z-z_0}的系数

$$

 
即围线积分可转化为求被积函数的洛朗展开式中$$
(z-z_0)^{-1}$$
的系数

# 5 留数

## 奇点

### 非孤立奇点

### 孤立奇点

#### 孤立奇点的定义
 
$$

f(z)在z_0点不解析，但在z_0的0<\vert z-z_0\vert <\delta内解析
$$


#### 孤立奇点D内一定有洛朗展式

#### 分类

##### 分类依据：洛朗展式主要部分项数
 
1）没有负幂次项，则称该孤立奇点为可去奇点。

 
2）只有有限项负幂次项，则称该孤立奇点为极点。

 
3）有无穷多项负幂次项，则称该孤立奇点为本性奇点。


##### 可去奇点
 
$$

洛朗展式中不含z-z_0的负幂项：
f(z)=c_0+c_1(z-z_0)+c_2(z-z_0)^2+\cdots
$$


##### (m阶)极点
 


展开式中含有限项$z-z_0$的负幂项
$$
f(z)=c_{-m}(z-z_0)^{-m}+c_{-(m-1)}(z-z_0)^{-(m-1)}+\cdots+c_{-1}(z-z_0)^{-1}+c_0+c_1(z-z_0)+c_2(z-z_0)^2+\cdots
=\frac{g(z)}{(z-z_0)^m},
$$
$$
其中g(z)=c_{-m}+c_{-(m-1)}(z-z_0)+\cdots+c_{-1}(z-z_0)^{m-1}+c_{0}(z-z_0)^{m}+\cdots在z_0解析，$$


且
$$g(z_0)\neq 0, m \ge 1, c_{-m}\neq 0$$


##### 本性极点
 
展开式中含无穷多项$z-z_0$的负幂项

$$
f(z)=\cdots+c_{-m}(z-z_0)^{-m}+c_{-(m-1)}(z-z_0)^{-(m-1)}+\cdots+c_{-1}(z-z_0)^{-1}+c_0+c_1(z-z_0)+c_2(z-z_0)^2+\cdots
$$


#### 孤立奇点的判别方法
 
$$
可去奇点：
\lim_{z\rightarrow z_0}f(z)=c_0常数
$$

 
$$
极点：
\lim_{z\rightarrow z_0}f(z)=\infty
$$

 
$$
本性奇点：
\lim_{z\rightarrow z_0}f(z)不存在
$$


##### 零点与极点的关系

###### 零点的概念
 
$$

不恒为零的解析函数f(z)，如果能表示成f(z)=(z-z_0)^m\varphi(z),

其中\varphi(z)在z_0解析，\varphi(z_0)\neq 0, m为正整数，称z_0为f(z)的m级零点
$$


###### 零点级数判别的充要条件
 
$$

z_0是f(z)的m级零点\Leftrightarrow
\begin{cases}
f^{(n)}(z_0)=0, &n=0, 1, 2, \cdots, m-1\\
f^{(m)}(z_0) \neq 0&
\end{cases}
$$


###### 零点与极点的关系
 
$$
z_0是f(z)的m级零点\Leftrightarrow z_0是\frac{1}{f(z)}的m级极点$$


###### 重要结论
 
$$

若z=a分别是\varphi(z)与\psi(z)的
m级与n级零点，则
$$

 
$$
当m>n时，z=a是\frac{\varphi(z)}{\psi(z)}的m-n级零点$$

 
$$
当m<n时，z=a是\frac{\varphi(z)}{\psi(z)}的n-m级极点$$

 
$$
当m=n时，z=a是\frac{\varphi(z)}{\psi(z)}的可去奇点$$

 
$$
当m\neq n时，z=a是\varphi(z)+\psi(z)的min(m,n)级零点$$

 
$$
当m=n时，z=a是\varphi(z)+\psi(z)的l级零点，其中l\ge m(n)$$


## 留数

### 留数的定义
 

设$z_0$为$f(z)$的**孤立奇点**，$f(z)$在$z_0$的去心邻域$0<\vert z-z_0\vert <\delta$内解析，$c$为该域内包含$z_0$的任一正向简单闭曲线，
则称积分$\frac{1}{2\pi i}\oint_cf(z)dz$为$f(z)$在$z_0$的留数(或残留)，记作$Res[f(z), z_0]=\frac{1}{2\pi i}\oint_cf(z)dz$


### 留数的计算方法

若$z_0$是$f(z)$的孤立奇点，则$Res[f(z), z_0]=c_{-1}$，其中$c_{-1}$为$f(z)$在$z_0$的去心邻域内洛朗展开式中$(z-z_0)^{-1}$的系数

#### 可去奇点处的留数
 
若$z_0$是$f(z)$的可去奇点，则$Res[f(z), z_0]=0$

#### n阶极点处的留数

若$z_0$是$f(z)$的$n$阶极点，则

$$
Res[f(z),z_0]=\frac{1}{(n-1)!}
\lim_{z\rightarrow z_0}
\frac{d^{n-1}}{dz^{n-1}}\left[
    \left(z-z_0\right)^{n}f(z)
\right]
$$

##### 证明：

$$
(z-z_0)^nf(z)=c_{-n}+c_{-(n-1)}(z-z_0)^1+\cdots+c_{-1}(z-z_0)^{m-1}+c_0(z-z_0)^n+\cdots
$$

$$
\frac{d^{n-1}}{dz^{n-1}}\left[(z-z_0)^nf(z)\right]=
c_{-1}(m-1)!+c_0 m(m-1)2(z-z_0)+\cdots
$$

即

$$
\lim_{z\rightarrow z_0}
\frac{d^{n-1}}{dz^{n-1}}\left[
    \left(z-z_0\right)^{n}f(z)
\right]
=c_{-1}(n-1)!
$$

整理得

$$
Res[f(z),z_0]=c_{-1}=\frac{1}{(n-1)!}
\lim_{z\rightarrow z_0}
\frac{d^{n-1}}{dz^{n-1}}\left[
    \left(z-z_0\right)^{n}f(z)
\right]
$$

##### 推论1

$f(z)=\frac{P(z)}{Q(z)}$，其中$P(z)$，$Q(z)$均在点$z_0$处解析，且$P(z_0)\neq 0, Q(z_0)=0, Q'(z_0)\neq 0$，则点$z_0$是$f(z)$的一阶极点，且

$$
Res\left[\frac{P(z)}{Q(z)},z_0\right]
=\frac{P(z_0)}{Q'(z_0)}
$$

证明：

$$
f(z)=\frac{P(z)}{Q(z)}=\frac{1}{z-z_0}\frac{P(z)}{\varphi(z)}
$$

$$
Res[f(z),z_0]=
\lim_{z\rightarrow z_0}
\left(z-z_0\right)f(z)
=\lim_{z\rightarrow z_0}\frac{P(z)}{\varphi(z)}
$$

$$
\lim_{z\rightarrow z_0}\varphi(z)
=\lim_{z\rightarrow z_0}\left[
    \frac{Q(z)-0}{z-z_0}
\right]
=\lim_{z\rightarrow z_0}\left[
    \frac{Q(z)-Q(z_0)}{z-z_0}
\right]
=Q'(z_0)
$$

即

$$
Res\left[\frac{P(z)}{Q(z)},z_0\right]
=\lim_{z\rightarrow z_0}\frac{P(z)}{\varphi(z)}
=\frac{P(z_0)}{Q'(z_0)}
$$


##### 推论2(考试常用)

$$
Res[f(z), \infty]=-Res\left[f(\frac{1}{z})\frac{1}{z^2},0\right]
$$

常见情况：z=0为可去奇点，留数为0

> ###### 例题：求$Res[\frac{e^{\frac{1}{z}}}{1-z}, 0]$
> 
> $$
> \begin{aligned}
> \frac{e^{\frac{1}{z}}}{1-z} =& 
> \left(\sum^\infty_{n=0}\frac{1}{n!}\frac{1}{z_n}\right)\left(\sum^\infty_{n=0}z^n\right)\\
> =& \left(1+\frac{1}{z}+\frac{1}{2!}\frac{1}{z^2}+\cdots\right)\left(1+z+z^2+\cdots\right)\\
> =& \cdots + \left(\sum^\infty_{n=1}\frac{1}{n!}\right)\frac{1}{z}+\cdots
> \end{aligned}
> $$
> 
> 即
> 
> $$
> Res\left[\frac{e^{\frac{1}{z}}}{1-z},0\right]=c_{-1}=\sum^\infty_{n=1}\frac{1}{n!}=\sum^\infty_{n=0}\frac{1}{n!}-1=e-1
> $$



### 留数基本定理


$$
\oint_cf(z)dz = 2\pi i\sum^{n}_{k=1}Res\left[f(z), z_k\right]
$$

#### 留数基本定理的推广

$f(z)$ 在扩充复平面内只有有限个孤立奇点，那么在各个孤立奇点（包括$\infty$）的留数之和为0，即

$$
\sum^{n}_{k=1}Res\left[f(z), z_k\right] + Res\left[f(z), \infty\right] = 0
$$

##### 证明：

$$
\sum^{n}_{k=1}Res\left[f(z), z_k\right] = \frac{1}{2\pi i}\oint_cf(z)dz
$$

$$
Res[f(z), \infty] = \frac{1}{2\pi i}\oint_{c^{-}}f(z)dz = - \frac{1}{2\pi i}\oint_{c}f(z)dz
$$

即

$$
\sum^{n}_{k=1}Res\left[f(z), z_k\right] + Res\left[f(z), \infty\right] = 0
$$



## 利用留数求解实积分

### 形如$\int_0^{2\pi}R(\sin\theta, \cos\theta)d\theta$

$$
\cos\theta=\frac{e^{i\theta}+e^{-i\theta}}{2}
=\frac{z+z^{-1}}{2}
$$

$$
\sin\theta=\frac{e^{i\theta}-e^{-i\theta}}{2i}
=\frac{z-z^{-1}}{2i}
$$

$$
d\theta=\frac{1}{ie^{i\theta}}de^{i\theta}=\frac{1}{iz}dz
$$

即可变换为$\vert z\vert=1$沿正向积分如下

$$
\int_0^{2\pi}R(\sin\theta, \cos\theta)d\theta=\int_{|z|=1}R\left[\frac{z-z^{-1}}{2i}, \frac{z+z^{-1}}{2}\right]\frac{1}{iz}dz
$$

## 形如$\int_{-\infty}^{\infty}R(x)dx$

$$
R(x)=\frac{P(x)}{Q(x)}=\frac{x^n+a_1x^{n-1}+\cdots+a_n}{x_m+b_1x^{m-1}+\cdots+b_m},\quad m-n\ge 2
$$

$$
\int_{-\infty}^{\infty}R(x) dx=
2\pi i\sum^n_{k=1}Res\left[R(z),z_k\right]
$$

其中$z_k(k=1,\cdots,n)$为$R(z)$在上半平面内（$Im z > 0$）的全部孤立奇点

## 形如$\int_{-\infty}^{\infty}R(x)e^{i\alpha x} dx\ (\alpha>0)$，$R(x)$在实轴上无奇点

$$
R(x)=\frac{P(x)}{Q(x)}=\frac{x^n+a_1x^{n-1}+\cdots+a_n}{x_m+b_1x^{m-1}+\cdots+b_m},\quad m-n\ge 1
$$

$$
\int_{-\infty}^{\infty}R(x)e^{i\alpha x} dx=
2\pi i\sum^n_{k=1}Res\left[R(z)e^{i\alpha z},z_k\right]
$$

其中$z_k(k=1,\cdots,n)$为$R(z)$在上半平面内（$Im z > 0$）的全部孤立奇点

> $$
> \int_{-\infty}^{\infty}R(x)\cos(\alpha x) dx=
> Re\left[
> \int_{-\infty}^{\infty}R(x)e^{i\alpha x} dx
> \right]
> $$
> 
> $$
> \int_{-\infty}^{\infty}R(x)\sin(\alpha x) dx=
> Im\left[
> \int_{-\infty}^{\infty}R(x)e^{i\alpha x} dx
> \right]
> $$

$\int_0^{+\infty}$及$\int_{-\infty}^0$情形下考虑变换为$\frac{1}{2}\int_{-\infty}^{+\infty}$

## 形如$\int_{-\infty}^{\infty}R(x)e^{i\alpha x} dx\ (\alpha>0)$，$R(x)$在实轴上只有有限个一阶极点

$$
R(x)=\frac{P(x)}{Q(x)}=\frac{x^n+a_1x^{n-1}+\cdots+a_n}{x_m+b_1x^{m-1}+\cdots+b_m},\quad m-n\ge 1
$$

$$
\int_{-\infty}^{\infty}R(x)e^{i\alpha x} dx=
\pi i\sum^p_{k=1}Res\left[R(z)e^{i\alpha z},x_k\right]+2\pi i\sum^q_{k=1}Res\left[R(z)e^{i\alpha z},z_k\right]
$$

其中$x_k(k=1,\cdots,p)$为$R(z)$在实轴上的一阶极点，$z_k(k=1,\cdots,q)$为$R(z)$在上半平面内（$Im z > 0$）的孤立奇点


#### 典型三种例题

##### sin
 
$$
\int^\pi_0\frac{dx}{a+\sin^2x}$$

 
$$
\int^{2\pi}_0\frac{dx}{(2+\sqrt{3}\cos x)^2}$$


##### 奇偶性
 
$$
\int^{+\infty}_{0}\frac{x^2}{x^4+1}dx$$


##### sin mx
 
$$
\int^{+\infty}_{0}\frac{x\sin mx}{(x^2+a^2)^2}dx$$

#### Tips

最终结果如果出现虚部，则必有错误

在期末考试中必出1-2个大题

# 6 保形映射
 
称$Arg f'(z_0)$为映射$\omega = f(z)$在点$z_0$的旋转角
 
称$\vert f′(z_0)\vert $为映射$\omega=f(z)$在点$z_0$的伸缩率.

## 具有保角性和伸缩率不变的连续映射称为保形映射
 
若函数$\omega=f(z)$在点$z_0$处解析,且$f'(z_0)\neq 0$,则数$\omega=f(z)$在点$z_0$附近为保形映射
