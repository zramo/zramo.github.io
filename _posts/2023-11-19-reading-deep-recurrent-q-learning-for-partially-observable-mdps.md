---
layout: post
title: "论文阅读：Deep Recurrent Q-Learning for Partially Observable MDPs"
date: 2023-11-19 06:00:00 +0800
categories: DRL
---

## 论文简介

本文针对深度强化学习实现的控制器记忆性有限和决策时需要获取当前系统状态完整信息（如完整Atari游戏屏幕）等局限性，研究了利用将卷积层后第一层全连接层替换为循环的LSTM以向DQN引入记忆性的方法，并将其称作DRQN（Deep Recurrent Q-Network）。其在通过对Atari游戏画面进行闪烁处理以人为构建的等价部分可观测情形下得到了与DQN相仿的性能。

实践中，常使用包含4个历史状态的输入训练DQN，若其面对的游戏逻辑需要多于4个状态的信息，则其便不是马尔可夫决策过程（MDP， Markov Decision Process），而是部分可观测马尔可夫决策过程（POMDP， Partially Observable MDP），这更符合实际世界中的问题性质。

## 理论分析

强化学习是学习智能体与未知环境交互的控制策略的过程。其中的环境常被形式化地表达为可被四元组$(S,A,P,R)$完全描述的MDP。在每个时间步长为$t$的决策过程中，一个与MDP交互的智能体观测当前状态$s_t\in S$并选择一个相应动作$a_t\in A$，其决定了当前奖励$r_t\sim R(s_t, a_t)$和下一个状态$s_{t+1}\sim P(s_t, a_t)$。

Q学习（Watkins and Dayan 1992）估计从一个给定状态执行一个动作的映射值，即状态动作值，简记作Q值。在Q值迭代学习的过程中，其根据观测到的奖励和结果状态的效用估计对当前Q值估计进行迭代更新，如下式所示

$$
Q(s,a)=Q(s,a)+\alpha\left(r+\gamma \underset{a'}{\max} Q(s',a')-Q(s,a)\right)
$$

在如Atari游戏等较难领域的应用中，对于每个$S\times A$则有太多状态需要分别估计，此时可使用模型近似Q值 (Mnih et al. 2015)。对于深度Q学习来说，这个模型是一个由统称为$\theta$的权重和偏移参数化的神经网络。Q值由网络输入状态后进行正向传播后的的输出节点值估计，可表示为$Q(s,a\vert\theta)$。对其的更新是为最小化损失函数而对参数的更新：

$$
L(s,a\vert\theta_i)\approx 
\left(
r
+\gamma \underset{a}{\max} Q(s',a\vert\theta_i)
-Q(s,a\vert\theta_i)
\right)^2
$$

$$
\theta_{i+1}=\theta_i+\alpha\nabla_\theta L(\theta_i)
$$

由于$\vert\theta\vert\ll \vert S\times A\vert$，神经网络模型比状态和动作更加具有一般性

$$
L_i(\theta_i)=E_{(s,a,r,s')\sim D}\left[\left(y_i-Q\left(s,a;\theta_i\right)\right)^2\right]
$$

### 部分可观测

而物理世界中MDP是近乎不可实现的，即POMDP更能描述实际系统。一个POMDP可以被描述为六元组$(S,A,P,R,\Omega, O)$，其中$S,A,P,R$与MDP相同，分别是状态、动作，转移，和奖励集合。但不同之处在于，智能体不再能获知系统实际状态，而只能获取到观测$o \in \Omega$。此时的观测则是由背后的系统状态根据概率分布$o\sim O(s)$生成.

原生的深度Q学习没有明确的机制用来挖掘POMDP隐藏的状态，故仅在观测能够反映系统隐含状态时性能较好。而由于$Q(o,a\vert\theta)\neq Q(s, a\vert\theta)$，其从观测估计Q值的策略在更一般化的场景中可能效果极差。

## DRQN网络设计

<img title="Figure 2: DRQN convolves three times over a single-channel image of the game screen. The resulting activations are processed through time by an LSTM layer. The last two timesteps are shown here. LSTM outputs become Q-Values after passing through a fully-connected layer. Convolutional filters are depicted by rectangular sub-boxes with pointed tops." src="\assets\images\2023-11-18-fig2.png" alt="" data-align="center">


## 文献来源：

[[1]Hausknecht M, Stone P. Deep Recurrent Q-learning for Partially Observable MDPs[C]//2015 AAAI Fall Symposium Series. 2015: 29-37](https://aaai.org/papers/11673-11673-deep-recurrent-q-learning-for-partially-observable-mdps/)
