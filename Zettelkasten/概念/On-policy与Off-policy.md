---
title: 强化学习基础概念
created: 2026-08-22
updated: 2026-08-22
type: concept
tags: [reinforcement-learning, fundamentals]
sources: []
confidence: high
---

# On-policy 与 Off-policy

## 定义
On-policy 和 Off-policy 是强化学习中两种核心的学习策略，区别在于**学习使用的数据来自当前策略本身，还是来自于其他策略**。

## On-policy

### 定义
学习使用的数据必须来自**当前策略本身**。行为策略（生成数据的策略）和目标策略（学习的策略）是相同的。

### 代表算法
- SARSA (State-Action-Reward-Action-Next State)
- PPO (Proximal Policy Optimization)
- A2C (Advantage Actor-Critic)

### 特点
- 数据与策略紧耦合
- 样本利用率较低（新策略不能复用旧数据）
- 训练稳定，收敛性好

## Off-policy

### 定义
学习使用的数据可以来自**其他策略**。行为策略与目标策略不同，可以使用历史数据或其他策略生成的数据。

### 代表算法
- Q-learning
- DQN (Deep Q-Network)
- DDPG / TD3
- SAC (Soft Actor-Critic)

### 特点
- 数据可以反复使用（配合经验回放）
- 样本利用率高
- 训练灵活，可以分离采样和训练过程
- 容易产生偏差或不稳定

## 对比总结

| 特性 | On-policy | Off-policy |
|------|-----------|------------|
| 数据来源 | 当前策略 | 其他策略 |
| 样本效率 | 低 | 高 |
| 训练稳定性 | 高 | 较低 |
| 算法代表 | PPO, SARSA | Q-learning, DQN, SAC |

## 相关概念
- [[强化学习]]
- [[经验回放]]
- [[Actor-Critic]]
