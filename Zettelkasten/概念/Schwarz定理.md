---
title: Schwarz定理
created: 2026-09-10
type: concept
tags: [微积分, 偏微分方程, 数学分析]
sources: [NJU课程, 复变函数]
confidence: high
---

# Schwarz定理（混合偏导数相等定理）

**Schwarz定理**（也称 Clairaut 定理）指出：若二元实函数两阶混合偏导数在一点连续，则在该点混合偏导数相等。

## 一、定理表述

设函数 $f(x, y)$ 在点 $(x_0, y_0)$ 的某邻域内存在，且二阶混合偏导数 $f_{xy}$ 和 $f_{yx}$ 在该点连续，则：

$$\frac{\partial^2 f}{\partial x \partial y} = \frac{\partial^2 f}{\partial y \partial x}$$

## 二、重要推论

### 1. 梯度场的旋度为零

对于任意标量场 $f$，有 $\nabla \times (\nabla f) = \mathbf{0}$。这是因为旋度的每个分量都涉及混合偏导数的差，而 Schwarz 定理保证这些差为零。

### 2. 无旋场的保守性

若矢量场 $\mathbf{F}$ 满足 $\nabla \times \mathbf{F} = \mathbf{0}$，且在单连通区域内各分量具有连续偏导数，则 $\mathbf{F}$ 是某个势函数 $f$ 的梯度：$\mathbf{F} = \nabla f$。

### 3. 无源场的矢量势表示

若矢量场 $\mathbf{F}$ 满足 $\nabla \cdot \mathbf{F} = \mathbf{0}$，则可存在矢量势 $\mathbf{A}$ 使得 $\mathbf{F} = \nabla \times \mathbf{A}$。

## 三、在物理中的应用

- **电磁学**：静电场是无旋场，可引入电势 $\phi$（$E = -\nabla \phi$）；磁场是无源场，可引入矢量势 $\mathbf{A}$（$B = \nabla \times \mathbf{A}$）
- **流体力学**：不可压缩流体的速度场满足 $\nabla \cdot \mathbf{v} = 0$

## 四、相关知识点

- [[Nabla算子]] — 梯度、散度、旋度的定义
- [[泊松方程]] — 拉普拉斯算子与泊松方程
- [[单位冲激信号]] — 狄拉克δ函数与广义函数
- [[LTI 线性时不变系统]] — 线性系统中的偏微分方程模型
