# AI Work Model

> AI 原生个人开发模板

一种不依赖聊天记录、通过项目文件驱动的多 AI 协作开发模式。

## 这是什么

这是一个项目模板，定义了多个 AI 角色（产品经理、架构师、开发、审查、测试）的职责边界、协作规则和文档体系。
任何 AI 工具（ChatGPT、Claude Code、Codex、Qoder、DeepSeek 等）都可以基于这套文件体系无缝接手工作。

## 快速开始

### 作为新项目使用

1. 复制本模板目录作为新项目根目录
2. 在 `docs/00_idea.md` 中写下你的产品想法
3. 让 AI 以 PM 角色接手，阅读 `.ai/roles/pm.md` 后开始工作
4. AI 会按工作流程自动推进，每步输出对应文档

### 作为 AI 接手现有项目

1. 阅读 `README.md`（本文件）了解项目背景与状态
3. 阅读 `.ai/workflow.md` 了解工作流程
4. 确认你的角色，阅读 `.ai/roles/<角色>.md`
5. 阅读相关 `.ai/rules/` 规则文件
6. 阅读 `docs/06_tasks.md` 确认当前任务
7. 开始工作，完成后更新对应文档

## 目录结构

```
.
├── README.md              ← 项目说明（本文件）
├── .ai/                   ← AI 协作配置
│   ├── roles/             ← 角色定义
│   │   ├── pm.md
│   │   ├── architect.md
│   │   ├── developer.md
│   │   ├── reviewer.md
│   │   └── tester.md
│   ├── rules/             ← 工作规则
│   │   ├── coding_rules.md
│   │   ├── git_rules.md
│   │   └── document_rules.md
│   └── workflow.md        ← 工作流程
├── docs/                  ← 项目文档
│   ├── 00_idea.md         ← 产品想法
│   ├── 01_prd.md          ← 产品需求文档
│   ├── 02_architecture.md ← 系统架构设计
│   ├── 03_database.md     ← 数据库设计
│   ├── 04_api.md          ← API 设计
│   ├── 05_ui.md           ← UI 设计
│   ├── 06_tasks.md        ← 任务清单
│   ├── 07_decisions.md    ← 决策记录
│   ├── 08_review.md       ← 审查报告
│   └── CHANGELOG.md       ← 变更日志
├── src/                   ← 源代码
├── tests/                 ← 测试代码
└── .gitignore
```

## 角色体系

| 角色 | 职责 | 主要输出 |
|------|------|---------|
| PM (产品经理) | 需求分析、PRD | 00_idea.md, 01_prd.md |
| Architect (架构师) | 技术方案、系统设计 | 02_architecture.md, 03_database.md, 04_api.md |
| Developer (开发) | 编码、测试、修 Bug | src/, tests/, 06_tasks.md |
| Reviewer (审查) | 代码质量审查 | 08_review.md |
| Tester (测试) | 测试方案、用例 | tests/, 08_review.md |

## 工作流程

```
想法 → PRD → 架构设计 → 数据库设计 → API设计 → UI设计 → 任务拆分 → 编码 → 测试 → Review → 发布
``+
详见 `.ai/workflow.md`。

## 支持的 AI 工具

| 工具 | 适合角色 | 说明 |
|------|---------|------|
| ChatGPT | PM / Architect | 产品设计、方案讨论、技术评审 |
| Claude Code | Developer | 主要编码和工程实现 |
| Codex | Developer | 代码开发和自动化任务 |
| Qoder | Developer | IDE 集成开发 |
| DeepSeek / GLM | Reviewer / Tester | 低成本分析、Review、第二意见 |

## 核心原则

- **文档驱动**：所有工作基于文档，不基于聊天记录
- **角色分明**：每个 AI 明确自己的角色和权限边界
- **不可跳过**：设计阶段不可跳过直接编码
- **决策留痕**：重要决策记录在 07_decisions.md，避免重复讨论
- **冲突上报**：AI 发现需求冲突不上自作主张，记录后等待人工确认
