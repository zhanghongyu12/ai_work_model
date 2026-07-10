# Git Rules (Git 协作规则)

## 分支策略

### 分支模型

```
main          ← 稳定发布分支，始终可运行
develop       ← 开发集成分支
feature/*     ← 功能分支，如 feature/user-auth
fix/*         ← 修复分支，如 fix/login-redirect
hotfix/*      ← 紧急修复分支，从 main 拉出
```

### 规则

- `main` 分支禁止直接提交，必须通过合并
- 功能开发在 `feature/*` 分支进行
- 合并到 `main` 前必须通过 Review
- 合并后删除功能分支

---

## 提交规范

### Commit Message

遵循 coding_rules.md 中的 Commit Message 格式。

### 提交粒度

- 一个提交只做一件事
- 提交前确保代码可编译/可运行
- 不要提交调试代码（console.log, print 调试等）
- 不要提交敏感信息（密钥、密码、配置中的真实凭据）

---

## 合并规则

- 合并前确保分支与目标分支同步
- 合并前必须通过测试
- 使用 `--no-ff` 合并，保留分支历史
- 合并信息包含关联的 Task ID

---

## Tag / Release

### 版本号

遵循语义化版本 (Semantic Versioning)：

```
MAJOR.MINOR.PATCH
```

- MAJOR：不兼容的 API 修改
- MINOR：向下兼容的功能新增
- PATCH：向下兼容的问题修复

### Release 流程

1. 确认所有测试通过
2. 更新 docs/CHANGELOG.md
3. 打 Tag：`v1.0.0`
4. 合并 develop → main

---

## .gitignore 原则

- 忽略所有依赖目录（node_modules/, venv/, __pycache__/ 等）
- 忽略构建产物（dist/, build/, *.pyc 等）
- 忽略环境配置（.env, .env.local 等）
- 忽略编辑器配置（.vscode/, .idea/ 等，除非团队共享配置）
- 不忽略文档文件
