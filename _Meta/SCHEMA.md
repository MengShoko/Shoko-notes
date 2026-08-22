---
title: Wiki Schema
created: 2026-08-20
updated: 2026-08-22
type: meta
tags: [meta]
---

# Wiki Schema

## Domain
南京大学本科/研究生学习知识库，覆盖自动化、计算机、AI 等领域。

## Structure Overview

本知识库采用 **PARA + Zettelkasten** 混合结构，分为两大类笔记：

### 1. 课程教材笔记 (10_Courses/)
- 各门课程的学习笔记，系统性较强
- 与特定课程关联，与其他课程关联较少
- 按课程分类存放

### 2. 知识点网络 (Zettelkasten/)
- 原子化的知识点笔记
- 跨课程、跨领域共享
- 形成强关联的知识网络

## Conventions
- File names: lowercase, hyphens, no spaces
- Use `[[wikilinks]]` to link between pages (minimum 2 outbound links)
- Tags must come from taxonomy below
- Language: Chinese primary, English technical terms in brackets
- All notes must have frontmatter: title, created, updated, type, tags, sources, confidence

## Tag Taxonomy

### Course Tags
- `#course/ml-fundamentals` — 机器学习基础
- `#course/deep-learning` — 深度学习
- `#course/robotics` — 机器人学
- `#course/control` — 自动控制
- `#course/embedded` — 嵌入式系统

### Concept Tags
- `#concept` — 概念类笔记
- `#method` — 方法类笔记
- `#book-note` — 书籍笔记
- `#paper-note` — 论文笔记

### Domain Tags
- `#machine-learning` — 机器学习
- `#deep-learning` — 深度学习
- `#reinforcement-learning` — 强化学习
- `#generative-models` — 生成模型
- `#neural-network` — 神经网络
- `#optimization` — 优化算法
- `#information-theory` — 信息论

### Status Tags
- `#to-review` — 待复习
- `#in-progress` — 进行中
- `#completed` — 已完成

## Page Types
- `concept`: 单个概念的原子笔记（Zettelkasten/概念/）
- `method`: 算法、技术方法（Zettelkasten/方法/）
- `book-note`: 教材/书籍系统笔记（Zettelkasten/书籍/）
- `paper-note`: 论文笔记（30_Resources/论文/）
- `course-note`: 课程教材笔记（10_Courses/）
- `meta`: 元数据文件（_Meta/）
