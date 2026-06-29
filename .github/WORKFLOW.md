# AI-CS 团队协作工作流程

## 📋 概述

本项目使用 **GitHub Projects v2** 进行团队协作管理，采用看板（Kanban）式工作流。

- **项目板**: https://github.com/users/decardlabs/projects/3
- **仓库**: https://github.com/decardlabs/AI-CS

---

## 🎯 工作流阶段

| 阶段 | 说明 | 谁负责 |
|------|------|--------|
| 📋 **Backlog** | 待处理的 Idea / 需求池，还没排期 | PM / 任何人 |
| 🎯 **Ready** | 经过评审、已排期，可以认领 | PM |
| 👨‍💻 **In Progress** | 正在开发中 | 开发者 |
| 👀 **Review** | 开发完成，等待 Code Review 或测试 | 开发者 |
| ✅ **Done** | 已完成并合并到主分支 | — |
| 🗑️ **Cancelled** | 已取消或不会实现 | — |

---

## 🏷️ 标签体系

### 类型标签
| 标签 | 含义 |
|------|------|
| `bug` | 缺陷报告 |
| `feature` | 新功能需求 |
| `enhancement` | 现有功能改进 |
| `refactor` | 代码重构 |
| `documentation` | 文档相关 |
| `urgent` | 紧急修复（热修复） |

### 状态标签
| 标签 | 含义 |
|------|------|
| `blocked` | 被外部依赖阻塞 |
| `duplicate` | 重复 Issue |
| `wontfix` | 暂不修复 |
| `question` | 需进一步讨论 |
| `good first issue` | 适合新手 |

### 优先级标签
| 标签 | 含义 |
|------|------|
| `p1-critical` | 🔴 关键问题，必须立即处理 |
| `p2-high` | 🟠 高优先级，尽快处理 |
| `p3-medium` | 🟡 中等优先级 |
| `p4-low` | 🟢 低优先级，可延后 |

---

## ⚡ 优先级与工作量

### 优先级（Project 字段）
| 等级 | 说明 | 响应时间 |
|------|------|---------|
| 🔥 Urgent | 阻塞发布 / 生产故障 | 当天 |
| ⭐ High | 重要功能 / 核心改进 | 本周 |
| 📌 Medium | 常规任务 | 本 sprint |
| ⏳ Low | 可延后的优化 | 待定 |

### 工作量（Project 字段）
| 大小 | 预估时间 | 说明 |
|------|---------|------|
| 🐤 Small | 1-2 天 | 简单改动 |
| 🐔 Medium | 3-5 天 | 一般功能 |
| 🐂 Large | 1-2 周 | 大型功能 |
| 🐘 Epic | 2 周以上 | 需要拆分 |

---

## 🔄 Sprint 迭代

- 周期：**2 周**（周一至下下周一）
- 规划日：每周一上午
- 回顾日：每 Sprint 最后一天下午

### Sprint 流程
1. **周一上午**：PM 将 Backlog 中的任务评估后移入 Ready
2. **开发者**从 Ready 中认领任务，拖入 In Progress
3. **每日更新**：更新 Status 字段状态
4. **完成时**：拖入 Review，创建 PR
5. **Review 通过**：合并 PR，拖入 Done
6. **Sprint 结束**：回顾、复盘

---

## 👨‍💻 日常操作指南

### 认领任务
1. 打开项目板：https://github.com/users/decardlabs/projects/3
2. 切换到 **Board 视图**
3. 从 `🎯 Ready` 列中找一个任务
4. 点击任务卡片 → Assign yourself
5. 将 Status 改为 `👨‍💻 In Progress`

### 提交代码
```
git checkout -b feat/xxx     # 从 master 创建功能分支
# ... 开发代码 ...
git add .
git commit -m "feat: xxx"    # 遵循 Conventional Commits
git push origin feat/xxx
```
然后创建 Pull Request，关联对应 Issue（在 PR 描述中输入 `Closes #123`）。

### Code Review
1. 提交 PR 后，将项目板 Status 改为 `👀 Review`
2. 至少 1 人 Review 通过后才能合并
3. Review 通过后，由 PR 作者合并到 master

### 完成任务
1. PR 合并后，Status 自动或手动改为 `✅ Done`
2. 确认无误后关闭 Issue

---

## 📊 项目板视图说明

| 视图 | 用途 | 分组方式 |
|------|------|---------|
| **Board** | 日常看板，拖拽更新状态 | 按 Status |
| **Table** | 完整任务列表，可多维度筛选 | — |
| **Roadmap** | 按 Sprint 和时间线查看进度 | 按 Sprint |
| **My Work** | 个人任务视图 | 过滤器：Assignee: @me |

---

## 📐 编码规范

- 使用 **Conventional Commits** 规范提交信息
  - `feat:` 新功能
  - `fix:` 修复 Bug
  - `refactor:` 重构
  - `docs:` 文档
  - `chore:` 杂项
- PR 标题与对应 Issue 标题保持一致
- 每个 PR 关联一个 Issue
