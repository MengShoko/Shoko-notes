---
title: 变分自编码器 VAE
created: 2026-08-22
updated: 2026-08-22
type: concept
tags: [deep-learning, generative-models, vae]
sources: []
confidence: medium
---

# 变分自编码器（VAE）

## 定义
变分自编码器（Variational Autoencoder, VAE）是一种基于变分推断的生成模型，通过学习数据的潜变量分布来生成新样本。

## 核心思想
- 将输入编码为潜变量的分布（而非点估计）
- 从潜变量分布中采样并解码生成
- 通过变分下界（ELBO）优化

## 模型结构

```
输入 → 编码器 → 潜变量分布 q(z|x) → 采样 z → 解码器 p(x|z) → 重构输出
```

### 编码器（Encoder）
输出潜变量的均值 $\mu$ 和对数方差 $\log \sigma^2$：
$$z \sim \mathcal{N}(\mu, \sigma^2 I)$$

### 解码器（Decoder）
从潜变量 $z$ 生成数据：
$$x \sim p_\theta(x|z)$$

## 损失函数
$$\mathcal{L} = \underbrace{-\mathbb{E}[\log p_\theta(x|z)]}_{\text{重构损失}} + \underbrace{D_{KL}(q(z|x) \| p(z))}_{\text{正则化项}}$$

## 重参数化技巧
$$z = \mu + \sigma \odot \epsilon, \quad \epsilon \sim \mathcal{N}(0, I)$$

使梯度可以通过采样节点反向传播。

## 与GAN对比

| 特性 | VAE | GAN |
|------|-----|-----|
| 训练稳定性 | 稳定 | 不稳定 |
| 生成质量 | 较低（模糊） | 较高 |
| 理论保证 | 有 | 无 |
| 推理速度 | 快 | 慢 |

## 相关概念
- [[生成模型]]
- [[扩散模型]]
- [[生成对抗网络 GAN]]
- [[香农熵]]
