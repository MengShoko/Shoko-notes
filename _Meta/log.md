# Wiki Log

> Chronological record of all wiki actions.

## [2026-08-22] refactor | Knowledge base structure optimization
### 问题分析
用户反馈现有结构不够清晰，需要区分：
1. **课程教材笔记** — 各课程独立，关联较少
2. **机器学习知识点** — 跨课程共享，形成知识网络

### 新结构方案
```
RA学习/
├── 00_Inbox/           # 临时收件箱
├── 10_Courses/         # 【新增】课程教材笔记（各课程独立）
│   ├── 机器学习基础/
│   │   └── 机器学习-周志华.md
│   ├── 深度学习/
│   ├── 机器人学/
│   └── 自动控制原理/
├── 20_Areas/           # 持续关注领域
├── 30_Resources/       # 参考资料原文
├── 40_Archive/         # 已完成归档
├── Zettelkasten/       # 【核心】原子化知识点网络
│   ├── 概念/   (16个)
│   ├── 方法/   (7个)
│   └── 索引.md
├── Assets/             # 图片、PDF附件
└── _Meta/              # 管理文件
```

### 执行内容
1. 创建 `10_Courses/` 目录结构
2. 将书籍笔记 `机器学习-周志华.md` 复制到 `10_Courses/机器学习基础/`
3. 更新 `README.md` — 详细说明新结构和存放规则
4. 更新 `_Meta/SCHEMA.md` — 添加课程相关标签
5. 更新 `Zettelkasten/索引.md` — 区分课程笔记和知识点

### 设计理念
- **课程笔记** → `10_Courses/` → 系统性、详细、与课程绑定
- **知识点** → `Zettelkasten/` → 原子化、精炼、跨课程共享
- **关联方式** → 课程笔记用 `[[知识点名]]` 引用知识点

## [2026-08-22] organize | Systematic knowledge base refactoring (Part 2)
### 新增概念笔记（补全知识网络）
| 笔记 | 内容概要 |
|------|---------|
| 变分自编码器 VAE | ELBO、重参数化技巧、与GAN对比 |
| 生成对抗网络 GAN | 对抗训练、损失函数、常见问题 |
| 马尔可夫决策过程 MDP | 五元组定义、Bellman方程、价值函数 |
| 激活函数 | ReLU、Sigmoid、Tanh、Softmax等 |
| 损失函数 | MSE、交叉熵、Huber损失 |
| 梯度下降 | BGD/SGD/Mini-batch、Adam优化器 |

### 新增方法笔记
| 笔记 | 内容概要 |
|------|---------|
| Q-learning | 经典off-policy算法、更新公式 |
| 策略梯度 | REINFORCE算法、梯度公式 |
| Actor-Critic | 架构原理、优势函数 |
| PPO | 裁剪损失、超参数说明 |

### 更新现有笔记
- 更新 Zettelkasten/索引.md — 添加完整知识网络图
- 更新 Zettelkasten/概念/Flow-Matching.md — 补充frontmatter和链接
- 更新 Zettelkasten/书籍/机器学习-周志华.md — 添加更多wikilink
- 更新 Zettelkasten/方法/k折交叉验证.md — 添加相关概念链接

### 当前状态
- 概念笔记：16个
- 方法笔记：7个
- 书籍笔记：1个（已迁移到课程目录）
- 总计：24个原子笔记
- 每个笔记均包含：frontmatter + ≥2个wikilink

## [2026-08-22] organize | Manual cleanup of missed files (Part 1)
- Moved 7 unsorted files to Zettelkasten/未分类/
- Further classified into 概念/ and 方法/
- Deleted 3 empty files
- Note: 昨日(8/21) cron job failed due to drift skip + gateway not running

## [2026-08-22] fix | Cron jobs repaired
- Pinned both jobs to model 'agnes-2.5-flash' (provider: custom)
- Started Hermes gateway (PID: 1908)

## [2026-08-20] create | Wiki pages
- Created Zettelkasten/书籍/机器学习-周志华.md
- Created Zettelkasten/方法/k折交叉验证.md
- Created Zettelkasten/概念/Flow-Matching.md
- Total: 3 new atomic notes created

## [2026-08-20] cleanup | Remove redundant files
- Removed empty directories
- Fixed image references in resource files
- Streamlined structure

## [2026-08-20] organize | Library restructuring
- Created PARA + Zettelkasten hybrid structure
- Moved images to Assets/Images/
- Moved PDF to Assets/PDFs/
- Created README.md with structure guide

## [2026-08-20] create | Wiki initialized
- Domain: Machine Learning & AI notes
- Structure created with SCHEMA.md, index.md, log.md

## [2026-08-20] setup | Daily auto-organize cron job
- Created cron job to run daily at 23:00
- Job ID: 86988f913b4b
