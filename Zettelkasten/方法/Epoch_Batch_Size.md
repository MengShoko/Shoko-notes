---
title: Epoch、Batch与Batch Size
created: 2026-08-22
updated: 2026-08-22
type: method
tags: [deep-learning, training]
sources: []
confidence: high
---

# 深度学习中Epoch、Batch以及Batch Size的设定

## 基本概念

### Epoch（时期）
一个完整的数据集通过神经网络一次并返回一次的过程。

### Batch（批）
由于数据集过大，将数据分成多个小块进行训练。

### Batch Size（批大小）
每次迭代使用的样本数量。

### Iteration（迭代）
训练一个Batch就是一次Iteration。

## 关系公式
$$\text{Iterations per Epoch} = \lceil \frac{\text{样本总数}}{\text{Batch Size}} \rceil$$

## 为什么需要多于一个Epoch？
- 数据集有限，训练太少会**欠拟合**
- 训练太多会**过拟合**
- 需要找到最佳平衡点

## 选择建议

| Batch Size | 优点 | 缺点 |
|-----------|------|------|
| 小（16-64） | 泛化好，内存占用低 | 训练慢，梯度噪声大 |
| 中（128-256） | 平衡性能和效果 | 适中 |
| 大（512-1024+） | 训练快，利用GPU并行 | 可能泛化差，内存需求高 |

## 相关概念
- [[过拟合]]
- [[泛化能力]]
- [[神经网络]]
