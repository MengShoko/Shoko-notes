---
title: Q-learning
created: 2026-08-22
updated: 2026-08-22
type: method
tags: [reinforcement-learning, deep-learning]
sources: []
confidence: high
---

# Q-learning

## 定义
Q-learning是一种经典的离策略（off-policy）强化学习算法，通过直接学习动作价值函数 $Q(s,a)$ 来找到最优策略。

## 核心思想
学习每个状态-动作对的Q值，然后根据最大Q值选择动作：
$$\pi^*(s) = \arg\max_a Q^*(s, a)$$

## 更新公式
$$Q(s, a) \leftarrow Q(s, a) + \alpha [r + \gamma \max_{a'} Q(s', a') - Q(s, a)]$$

| 符号 | 含义 |
|------|------|
| $\alpha$ | 学习率 |
| $r$ | 即时奖励 |
| $\gamma$ | 折扣因子 |
| $\max_{a'} Q(s', a')$ | 下一状态的最大Q值 |

## 算法流程
1. 初始化 $Q(s,a)$ 为任意值
2. 对于每个episode：
   - 选择动作 $a$（通常用 $\epsilon$-greedy）
   - 执行动作，观察 $(s', r)$
   - 更新Q值
   - $s \leftarrow s'$
3. 直到收敛

## $\epsilon$-greedy策略
- 以概率 $\epsilon$ 随机选择动作（探索）
- 以概率 $1-\epsilon$ 选择当前最佳动作（利用）

## 优缺点

| 优点 | 缺点 |
|------|------|
| 简单易懂 | 离散动作空间 |
| 收敛保证 | 表格法存不下大状态空间 |
| Off-policy | 需要探索 |

## 扩展
- **DQN**：用神经网络近似Q函数
- **Double DQN**：解决Q值高估
- **Dueling DQN**：分离状态价值和动作优势

## 相关概念
- [[强化学习]]
- [[马尔可夫决策过程 MDP]]
- [[经验回放]]
