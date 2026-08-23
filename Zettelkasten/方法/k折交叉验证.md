---
title: k折交叉验证
created: 2026-08-22
updated: 2026-08-22
type: method
tags: [machine-learning, evaluation]
sources: [30_Resources/书籍/周志华-机器学习/模型评估原文笔记.md]
confidence: high
---

# k折交叉验证（k-fold Cross Validation）

## 定义
将数据集 $D$ 分成 **k个大小相似、互斥** 的子集 $D_i$：
- 每次用 $k-1$ 个子集训练，剩下一子集测试
- 重复 $k$ 次，取平均值

$$D = D_1 \\cup D_2 \\cup \\cdots \\cup D_k, \\quad D_i \\cap D_j = \\emptyset \\ (i \\neq j)$$

## 标准设定
通常取 $k = 10$

## 留一法（LOO）
- 当 $k = m$（样本数）时的特例
- **优点**：训练集只少一个样例，模型与原始数据集差异最小
- **缺点**：计算开销大，且根据NFL原则未必更准确

## 相关方法
- [[留出法]] — 简单划分训练/测试集
- [[自助法]] — 有放回抽样

## 相关概念
- [[泛化能力]]
- [[过拟合]]
- [[模型评估]]