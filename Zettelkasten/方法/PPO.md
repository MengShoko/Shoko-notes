---
title: PPO
created: 2026-08-22
updated: 2026-08-22
type: method
tags: [reinforcement-learning, deep-learning]
sources: []
confidence: high
---

# 近端策略优化（PPO）

## 定义
PPO（Proximal Policy Optimization）是一种on-policy策略梯度算法，通过裁剪损失函数限制策略更新幅度，提高训练稳定性。

## 核心思想
避免策略一次更新太大导致性能骤降，引入裁剪机制：
$$L^{CLIP}(\theta) = \mathbb{E}_t[\min(r_t(\theta)\hat{A}_t, \text{clip}(r_t(\theta), 1-\epsilon, 1+\epsilon)\hat{A}_t)]$$

其中 $r_t(\theta) = \frac{\pi_\theta(a_t|s_t)}{\pi_{\theta_{old}}(a_t|s_t)}$

## 参数说明
- $\epsilon$：裁剪范围，通常取 0.1 或 0.2
- $\hat{A}_t$：优势函数估计

## 算法流程
1. 用旧策略收集轨迹
2. 计算优势函数
3. 多次epoch更新策略（每次重新计算比值）
4. 重复

## 优势
- 比TRPO更简单实现
- 比DQN更稳定
- 样本效率较高
- 工业界广泛应用

## 相关变体
- **PPO-Clip**：原始版本
- **PPO-Penalty**：使用惩罚项替代裁剪

## 相关概念
- [[Actor-Critic]]
- [[策略梯度]]
- [[On-policy与Off-policy]]
- [[强化学习]]
