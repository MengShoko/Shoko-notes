---
title: 生成对抗网络 GAN
created: 2026-08-22
updated: 2026-08-22
type: concept
tags: [deep-learning, generative-models, gan]
sources: []
confidence: medium
---

# 生成对抗网络（GAN）

## 定义
生成对抗网络（Generative Adversarial Network, GAN）由生成器和判别器两个网络组成，通过对抗训练学习数据分布。

## 核心架构

```
生成器 G：随机噪声 → 生成假样本
判别器 D：真实/假样本 → 判断真假
```

## 对抗训练

### 生成器目标
欺骗判别器，使 D(G(z)) 接近 1：
$$\min_G \mathbb{E}[\log(1 - D(G(z)))]$$

### 判别器目标
正确区分真实和生成样本：
$$\min_D \mathbb{E}[\log D(x)] + \mathbb{E}[\log(1 - D(G(z)))]$$

### 极小极大博弈
$$\min_G \max_D V(D, G) = \mathbb{E}_{x \sim p_{data}}[\log D(x)] + \mathbb{E}_{z \sim p_z}[\log(1 - D(G(z)))]$$

## 常见问题与解决

| 问题 | 表现 | 解决方案 |
|------|------|---------|
| 模式崩溃 | 生成多样性差 | WGAN、Mini-batch |
| 训练不稳定 | 震荡不收敛 | Gradient penalty |
| 消失梯度 | 生成器不学习 | Use non-saturating loss |

## 代表模型
- **DCGAN**：使用卷积结构
- **WGAN**：使用Wasserstein距离
- **StyleGAN**：高质量图像生成
- **CycleGAN**：图像风格迁移

## 与VAE对比
- VAE：训练稳定但生成模糊
- GAN：生成质量高但训练困难

## 相关概念
- [[生成模型]]
- [[变分自编码器 VAE]]
- [[神经网络]]
