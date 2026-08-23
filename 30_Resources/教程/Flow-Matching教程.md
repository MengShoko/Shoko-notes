---
title: Flow-Matching教程
created: 2026-08-20
updated: 2026-08-22
type: reference
tags: [deep-learning, generative-models, flow-matching, tutorial]
sources: [https://zhuanlan.zhihu.com/p/685921518]
confidence: medium
---

# Flow-Matching 教程

> 来源：[深入解析Flow Matching技术 - 知乎](https://zhuanlan.zhihu.com/p/685921518)

---

## 概述

Flow Matching 是一种生成模型技术，通过学习从简单分布（如高斯分布）到目标数据分布的**连续变换**来生成数据。

## 核心思想

1. **连续流**：构建从噪声分布到数据分布的连续变换轨迹
2. **ODE求解**：通过常微分方程求解器沿流轨迹生成样本
3. **训练效率**：相比扩散模型，Flow Matching 训练更稳定、采样速度更快

## 与扩散模型对比

| 特性 | Flow Matching | Diffusion Model |
|------|---------------|-----------------|
| 生成方式 | 连续流 | 逐步去噪 |
| 训练效率 | 更高 | 较低 |
| 采样速度 | 快 | 慢（多步） |
| 稳定性 | 好 | 好 |

## 相关知识点

- [[Flow-Matching]] — Flow Matching概念笔记
- [[扩散模型]] — 前向/反向过程
- [[生成模型]] — 主要类型和应用
- [[神经网络]] — 基础结构