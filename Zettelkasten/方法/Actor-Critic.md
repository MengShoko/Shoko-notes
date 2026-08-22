---
title: Actor-Critic
created: 2026-08-22
updated: 2026-08-22
type: method
tags: [reinforcement-learning, deep-learning]
sources: []
confidence: high
---

# Actor-Critic

## 定义
Actor-Critic方法结合了两类强化学习方法的优点：
- **Actor**：负责策略优化（类似策略梯度）
- **Critic**：负责评估策略价值（类似价值迭代）

## 架构
```
                    ┌─────────────┐
          状态 s ──▶│    Actor    │──▶ 动作 a
                    │  (策略 π)   │
                    └─────────────┘
                         │
                         ▼
                    ┌─────────────┐
          奖励 r ──▶│   Critic    │──▶ 价值评估
                    │  (价值 V/Q) │
                    └─────────────┘
```

## 更新规则
- **Critic更新**：最小化 TD误差
  $$L = \mathbb{E}[(r + \gamma V(s') - V(s))^2]$$

- **Actor更新**：沿优势函数方向更新策略
  $$\nabla_\theta J \approx \mathbb{E}[\nabla_\theta \log \pi(a|s) \cdot A(s,a)]$$
  
  其中优势函数 $A(s,a) = Q(s,a) - V(s)$

## 优势
- 比纯策略梯度方差更低
- 比纯价值方法更灵活
- 可处理连续动作空间

## 代表算法
- **A2C**：异步Actor-Critic
- **A3C**：异步优势Actor-Critic
- **PPO**：近端策略优化
- **SAC**：软Actor-Critic

## 相关概念
- [[策略梯度]]
- [[强化学习]]
- [[Soft Actor-Critic]]
- [[PPO]]
