---
title: Flow Matching
created: 2026-08-20
updated: 2026-08-22
type: concept
tags: [deep-learning, generative-models, flow-matching]
sources: [30_Resources/教程/Flow-Matching教程.md]
confidence: medium
---

# Flow Matching

## 概述
Flow Matching 是一种生成模型技术，通过学习从简单分布（如高斯分布）到目标数据分布的连续变换来生成数据。

## 核心思想
- 构建从噪声分布到数据分布的**连续流**
- 通过ODE求解器沿流轨迹生成样本
- 比扩散模型更高效、训练更稳定

## 与扩散模型对比

| 特性 | Flow Matching | Diffusion Model |
|------|---------------|-----------------|
| 生成方式 | 连续流 | 逐步去噪 |
| 训练效率 | 更高 | 较低 |
| 采样速度 | 快 | 慢（多步） |
| 稳定性 | 好 | 好 |

## 相关概念
- [[生成模型]]
- [[扩散模型]]
- [[神经网络]]

## 参考资源
- [深入解析Flow Matching技术 - 知乎](https://zhuanlan.zhihu.com/p/685921518)
