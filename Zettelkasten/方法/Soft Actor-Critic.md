---
title: Soft Actor-Critic
created: 2026-08-22
updated: 2026-08-22
type: method
tags: [reinforcement-learning, deep-learning]
sources: []
confidence: high
---

# Soft Actor-Critic (SAC)

## 概述
SAC是一种适用于**连续动作空间**的强化学习算法，同时优化策略质量和熵（探索性）。

## 适用场景
- 机器人控制
- 移动机器人导航
- 无人车控制
- 机械臂控制
- 自动驾驶

## 核心组件

### 1. Actor（演员网络）
根据状态 $s$ 输出动作分布：
$$a \sim \pi_\phi(a|s)$$

Actor输出动作均值 $\mu$ 和标准差 $\sigma$，从分布中采样：
```
v ~ Normal(0.08, 0.03)
ω ~ Normal(0.20, 0.10)
```

### 2. Critic（评论家网络）
- 使用**两个Critic**（Twin Critic）
- 计算目标时取两者较小值
- 降低Q值高估问题

$$Q(s, a) = r + \gamma \min(Q_1^{target}, Q_2^{target}) - \alpha \log \pi(a'|s')$$

## 训练流程

1. **与环境交互**：读取状态 $s_t$，Actor采样动作 $a_t$，获得 $(s_{t+1}, r_t, done)$
2. **存储经验**：存入 Replay Buffer（容量50万）
3. **随机采样**：从Buffer中抽取一个batch
4. **更新Critic**：最小化均方误差
5. **更新Actor**：最大化Q值同时保留熵
6. **自动调节α**：自适应调整熵系数
7. **软更新目标网络**：$\theta_{target} \leftarrow \tau\theta + (1-\tau)\theta_{target}$

## 关键特性
- **Off-policy**：可使用历史经验
- **最大熵**：鼓励探索，避免早熟收敛
- **样本效率高**：适合实际机器人应用

## 相关概念
- [[强化学习]]
- [[On-policy与Off-policy]]
- [[经验回放]]
- [[香农熵]]
