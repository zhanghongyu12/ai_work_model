# AI 专家讨论规则

 # AI 专家讨论规则
 
 > 本规则用于两个 Expert 的**结构化辩论**。
 > 如果是两个角色之间的**日常协作沟通**（如 Architect ↔ Designer 交叉确认），请使用 `.ai/rules/coordination_rules.md`。
 > 一个 session 要么是辩论，要么是协作，由 context.md 的"类型"字段区分。
 
## 路径与 session_id 约定

- 每次讨论在 `.session/{session_id}/` 目录下进行，session_id 格式为 `YYYYMMDD` + 两位序号（如 `2026071301` 表示 2026 年 7 月 13 日的第 1 轮讨论）。
- 编排者启动讨论前必须：
  1. 创建 `.session/{session_id}/` 目录
  2. 在 `.session/{session_id}/context.md` 中填写讨论背景，并写明 `输出目录: .session/{session_id}/`
- Expert 不直接写 `discussion.md`，而是将各自独立输出写入输出目录下的 `expert_a.md` 和 `expert_b.md`。
- 编排方负责收集两个 Expert 的独立输出后，合并写入 `discussion.md`，再进入 Phase 2 交叉挑战。
- context.md 缺少输出目录字段时，Expert 必须报错停止，不得自行猜测路径。

---

## 目标

两个 AI 作为独立专家，对同一个问题进行深入分析。

目标不是互相说服，而是：

- 发现不同视角
- 暴露隐藏风险
- 比较不同方案
- 形成最佳决策

---

# 基本原则

## 1. 平等原则

AI-A 和 AI-B 地位相同。

不存在：

- 老师
- 学生
- 执行者
- 审核者

双方都是专家。

---

# 2. 独立思考

每个 AI 第一次分析时：

禁止读取对方观点。

目的：

避免思维污染。

必须先形成自己的判断。

---

# 3. 观点碰撞

第二阶段：

双方读取对方观点。

必须：

- 指出认可部分
- 指出不同意见
- 给出理由
- 提供替代方案

---

# 4. 禁止无意义争论

禁止：

"我同意"

"你说得对"

必须说明：

为什么。

---

# 5. 所有讨论记录写入

由编排方合并两个 Expert 的独立输出后写入 `.session/{session_id}/discussion.md`

格式：

## Round X

### AI-A

内容

### AI-B

内容

---

# 6. 最终必须产生

`.session/{session_id}/synthesis.md`

包含：

- 共识
- 分歧
- 最优方案
- 未解决风险

---

# 讨论阶段

## Phase 1 独立分析

两个 AI 分别提出方案，输出到 `.session/{session_id}/expert_a.md` 和 `.session/{session_id}/expert_b.md`（由 Expert 直接写自己的独立文件）。
编排方收集两个 Expert 的独立输出后，合并写入 `.session/{session_id}/discussion.md`。
Phase 1 期间禁止任何 Expert 读取对方输出。

## Phase 2 交叉挑战

双方读取 `.session/{session_id}/discussion.md` 中对方的观点，互相分析。

## Phase 3 深度优化

结合双方观点。

## Phase 4 总结

生成最终方案，写入 `.session/{session_id}/synthesis.md`。
