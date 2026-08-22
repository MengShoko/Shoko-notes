# Wiki Log

> Chronological record of all wiki actions.

## [2026-08-22] fix | Cron jobs repaired
- Pinned both jobs to model 'agnes-2.5-flash' (provider: custom)
- Started Hermes gateway (PID: 34692) — was previously not running
- Jobs will now fire automatically:
  - NJU工科资讯日报: daily at 22:00
  - RA学习知识库每日整理: daily at 23:00

## [2026-08-22] organize | Manual cleanup of missed files
- Moved 7 unsorted files to Zettelkasten/未分类/
- Files moved:
  - On-policy与Off-policy的区别与统一.md
  - Soft Actor-Critic 软演员-评论家算法.md
  - 机器学习的分支.md
  - 泛化能力.md
  - 过拟合.md
  - 香农熵.md
  - 深度学习中Epoch、Batch以及Batch size的设定.md
- Further classified:
  - 方法: Soft Actor-Critic, Epoch/Batch设定
  - 概念: On-policy/Off-policy, 香农熵
  - 删除空文件: 泛化能力、过拟合、机器学习的分支
- Note: 昨日(8/21) cron job failed due to drift skip + gateway not running

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
