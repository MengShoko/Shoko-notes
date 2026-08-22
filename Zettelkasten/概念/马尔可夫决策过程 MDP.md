---
title: 马尔可夫决策过程 MDP
created: 2026-08-22
updated: 2026-08-22
type: concept
tags: [reinforcement-learning, fundamentals]
sources: []
confidence: high
---

# 马尔可夫决策过程（MDP）

## 定义
马尔可夫决策过程（Markov Decision Process, MDP）是强化学习的数学框架，用于建模序列决策问题。

## 五元组定义
$$MDP = (S, A, P, R, \gamma)$$

| 符号 | 含义 | 说明 |
|------|------|------|
| $S$ | 状态空间 | 所有可能状态的集合 |
| $A$ | 动作空间 | 所有可能动作的集合 |
| $P$ | 状态转移函数 | $P(s'|s,a)$：在状态 $s$ 执行动作 $a$ 后转移到 $s'$ 的概率 |
| $R$ | 奖励函数 | $R(s,a,s')$：转移获得的即时奖励 |
| $\gamma$ | 折扣因子 | $\gamma \in [0,1]$，衡量未来奖励的重要性 |

## 马尔可夫性质
未来状态只依赖当前状态和动作，与历史无关：
$$P(s_{t+1}|s_t, a_t, s_{t-1}, a_{t-1}, ...) = P(s_{t+1}|s_t, a_t)$$

## 策略
策略 $\pi(a|s)$ 表示在状态 $s$ 下选择动作 $a$ 的概率。

## 价值函数

### 状态价值函数
$$V^\pi(s) = \mathbb{E}_\pi\left[\sum_{t=0}^{\infty} \gamma^t R(s_t, a_t, s_{t+1}) \bigg| s_0 = s\right]$$

### 动作价值函数（Q函数）
$$Q^\pi(s, a) = \mathbb{E}_\pi\left[\sum_{t=0}^{\infty} \gamma^t R(s_t, a_t, s_{t+1}) \bigg| s_0 = s, a_0 = a\right]$$

## Bellman方程
$$V^\pi(s) = \sum_{a} \pi(a|s) \sum_{s'} P(s'|s,a)[R(s,a,s') + \gamma V^\pi(s')]$$

最优策略满足：
$$V^*(s) = \max_a Q^*(s, a)$$
$$Q^*(s, a) = R(s, a) + \gamma \sum_{s'} P(s'|s,a) V^*(s')$$

## 相关概念
- [[强化学习]]
- [[Q-learning]]
- [[策略梯度]]
