# Changelog

## v4.0.0 (2026-06-22) — 从单体纪律到多Agent协作生态

### 结构性修复
- **修复 .gitignore 阻止规则分发**：`.claude/` 整目录排除 → `.claude/*` + `!.claude/rules/`
- **全量规则入库**：从实际工作区同步全部 29 条规则（v1.0 仅含 10 条）

### 新增规则（19条，自v1.0以来）
#### Agent管理与故障恢复
- `agent-concurrency-fallback.md` — Agent 并发降级协议（429限流零等待切换）
- `agent-prompt-ironclad.md` — Agent Prompt 三要素铁律（目标/格式/停止条件）
- `subagent-strategy.md` — Sub-Agent 策略（何时用/不用/模型选择/故障恢复）

#### 信息搜索与纪律
- `search-decision-tree.md` — 搜索决策树（何时搜/搜多深/用什么工具）
- `lesson-auto-update.md` — 教训闭环自动更新（用户纠正→工作流自动修改）

#### Skill管理与路由
- `skill-auto-activation.md` v2.0 — 技能自动激活（三层路由+联动链+自我学习闭环）
- `skill-execution-discipline.md` — Skill 执行纪律（必读执行协议，不可跳过）
- `skill-logging-enforcement.md` — Skill 调用日志强制记录
- `skill-route-enforcement.md` — Skill 路由注册强制规则

#### 安全与运维深化
- `chinese-path-safety.md` — Windows 中文路径安全（禁Bash heredoc）
- `powershell-safety.md` — PowerShell 安全规则
- `pre-action-check.md` — 动手前检查门禁
- `git-recovery.md` — Git 检查点与恢复（删前commit+30秒恢复）
- `mcp-config-protocol.md` — MCP 配置协议四铁律

#### 架构与治理
- `competition-workspace-architecture.md` — 竞赛项目工作区架构
- `dual-write-protocol.md` — 双写协议（经验教训根级+模块级同步）
- `no-root-rules-dir.md` — 禁止根目录 rules/（防回退）
- `_MIGRATED-TO-RULES.md` — 规则迁移说明

### 优化
- `anti-info-overload.md` — 补充数据筛选和折叠技巧
- `no-blind-overwrite.md` — 补充 .gitignore 安全策略
- `script-safety-check.md` — 细化路径白名单

### 移除（太个人化/信息密度低）
- `identity-consistency.md` — 太泛泛，具体规则已覆盖
- `preference-memory.md` — 信息密度不足
- `voice-dna-auto-inject.md` — 个人文风，不适合通用框架

---

## v1.0.0 (2026-05-26)

### Added
- 10 cross-cutting engineering laws
- 6-stage project lifecycle SOP
- 3-layer memory architecture (with confidence labels)
- Anti-illusion audit (five-question check)
- Negative result archiving mechanism
- Memory candidate confirmation protocol
- Script safety check protocol
- Anti-information overload rules
- Boundary declaration rules
- Claude Code / Codex / Cursor / Aider / Gemini CLI adapters
- Chinese and English memory templates
