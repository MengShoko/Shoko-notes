---
title: Nabla算子
created: 2026-09-10
type: concept
tags: [微积分, 矢量分析, 复变函数]
sources: [NJU课程, 复变函数]
confidence: high
---

# Nabla算子（哈密顿算子）

**哈密顿算子（Hamilton operator）**，又称矢量微分算子，记为 $\nabla$：

$$\nabla = \left(\frac{\partial}{\partial x}, \frac{\partial}{\partial y}, \frac{\partial}{\partial z}\right)$$

它既有微分性质，又遵循矢量代数法则。

## 一、核心算子的数学定义

### 梯度（Gradient）

- **作用对象**：标量场（如温度场、高度场）
- **数学定义**：$\nabla f = \frac{\partial f}{\partial x}\mathbf{i} + \frac{\partial f}{\partial y}\mathbf{j} + \frac{\partial f}{\partial z}\mathbf{k}$
- **物理意义**：梯度是一个向量，指向标量场在该点增长最快的方向，其大小等于该方向的最大变化率

### 散度（Divergence）

- **作用对象**：矢量场（如水流速度场、电场）
- **数学定义**：$\nabla \cdot \mathbf{F} = \frac{\partial F_x}{\partial x} + \frac{\partial F_y}{\partial y} + \frac{\partial F_z}{\partial z}$
- **物理意义**：散度是标量，衡量矢量场在某一点的发散程度，即单位体积中的净通量（源强度）
  - 大于0为**源**（流体向外流出）
  - 小于0为**汇**（流体向内流入）
  - 等于0为进出平衡

### 旋度（Curl）

- **作用对象**：矢量场
- **数学定义**：$\nabla \times \mathbf{F}$
- **物理意义**：衡量矢量场在某一点的旋转趋势，方向遵循右手定则，大小表示旋转的强度

## 二、算子之间的运算关系

### 梯度的旋度恒为零

- **数学本质**：由混合偏导数可交换次序直接推导（参见 [[Schwarz定理]]）
- **物理意义**：任何由标量势函数梯度产生的场必然是**无旋场（保守场）**，解释了为什么在保守力场中做功与路径无关

### 旋度的散度恒为零

- **物理意义**：任何旋度场必然是**无源场**
- **经典例子**：磁场满足 $\nabla \cdot \mathbf{B} = 0$，意味着磁力线总是闭合的，自然界中不存在磁单极子

### 拉普拉斯算子

- **定义**：$\nabla^2 f = \nabla \cdot (\nabla f)$，即梯度的散度
- **物理意义**：描述物理量在空间中的扩散、波动或平衡状态
- 参见 [[泊松方程]]

## 三、积分定理

### 高斯散度定理

$$\oiint_{\partial V} \mathbf{F} \cdot d\mathbf{S} = \iiint_V (\nabla \cdot \mathbf{F}) \, dV$$

穿过一个闭合曲面的总通量，等于该曲面所保卫体积内所有源和汇的总和，建立了体积分与面积分的关系。

### 斯托克斯定理

$$\oint_{\partial S} \mathbf{F} \cdot d\mathbf{l} = \iint_S (\nabla \times \mathbf{F}) \cdot d\mathbf{S}$$

沿一条闭合曲线的环量，等于该曲线所围曲面上所有微小漩涡的综合，建立了面积分与线积分的关系。

## 四、相关知识点

- [[拉普拉斯算子]] — 梯度的散度，常见于泊松方程
- [[Schwarz定理]] — 混合偏导数相等，保证旋度梯度和散度旋度为零
- [[泊松方程]] — $\nabla^2 \phi = f$，椭圆型偏微分方程
- [[LTI 线性时不变系统]] — 矢量场在线性系统中的描述
