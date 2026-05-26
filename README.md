# niuma-engine

**不只是记忆系统，是 AI 协作的工程纪律。**

[English](README.en.md) | 中文

---

## 这是什么

niuma-engine 是一套面向 AI 编码代理（Claude Code、Codex、Cursor、Gemini CLI、Aider）的**工程级协作框架**。

它把人类工程师的工作纪律——证据分层、防假象审计、负结果归档、门禁文化——变成 AI 代理能理解和执行的规则。

**对比 comemo**：

| 维度 | comemo | niuma-engine |
|------|--------|-------------|
| 记忆架构 | 3层（全局/项目/个人） | 3层 + 置信度标签 + 失效条件 |
| 规则体系 | 基础协作规则 | 10条工程法则 + 6阶段生命周期 |
| 防错机制 | 无 | 防假象审计（五连问）+ 负结果归档 |
| 安全机制 | 无 | 脚本安全检查 + 双归档 + 盲写禁止 |
| 自我改进 | 无 | 经验→规则→Skill 自动结晶 |
| 信息控制 | 无 | 防信息过载 + 边界声明 |

**一句话**：comemo 教 AI 记住你的偏好，niuma-engine 教 AI **像工程师一样工作**。

---

## 适用人群

- 用 AI 编码代理做真实项目（不是玩具 demo）的人
- 被 AI「自信地给出错误的好结果」坑过的人
- 想让 AI 记住「什么路走不通」而不只是「什么路走得通」的人
- 需要跨多个项目保持一致的 AI 协作标准的人
- 不想每次新对话都从零开始的人

---

## 核心模块

### 10 条工程法则（横轴——始终生效）

| 法则 | 一句话 | 你什么时候需要它 |
|------|--------|----------------|
| 1. 证据分层 | 任何「通过」必须带口径标签 | AI 说"测试通过了"但你不确定可信度 |
| 2. 防假象审计 | 高分先审产生方式 | AI 给了一个异常好的数字 |
| 3. 实测优先 | 扫描验证，不假定单调 | 调参数时 AI 说"越大越好" |
| 4. 工具自由度 | 克制人工 hint | 你忍不住想用硬约束帮工具 |
| 5. 跨边界校验 | 格式/编码/单位/命名 | 数据在两个系统间传递 |
| 6. 隔离契约 | 多 Agent 写入区隔离 | 多个 AI 同时改代码 |
| 7. 负结果归档 | 死路必须归档 | 走了弯路，不想下次再走 |
| 8. 门禁文化 | 完成=过全部门禁 | AI 说"做完了"但你不确定 |
| 9. 识别结构墙 | 平台期换角度 | 同一个问题反复失败 |
| 10. 规则结晶 | 经验→规则→Skill | 总结教训，防止再犯 |

### 6 阶段生命周期（纵轴——按时间）

```
立项调研 → 方案探索 → 并行攻坚 → 分层验证 → 复盘结晶 → 交付声明
```

每个阶段有**目标产出、标准动作、出口门禁、反模式**。

### 3 层记忆系统

```
全局规则（始终生效）
  └── 项目记忆（按项目加载）
       └── 个人记忆（按需加载）
```

每条记忆带**置信度标签**（高/中/待确认）和**失效条件**。

---

## 快速开始

### 方式 1：自动安装（推荐）

```bash
# 克隆仓库
git clone https://github.com/Destined-at-Dawn/niuma-engine.git
cd niuma-engine

# 把仓库交给你的 AI 代理，让它读安装指南
# Claude Code: 读 docs/agent-install.md
# Codex: 读 docs/agent-install.md
# 其他: 读 docs/agent-install.md
```

### 方式 2：手动安装

1. 复制 `.claude/rules/` 到你的项目根目录
2. 复制 `CLAUDE.md` 到你的项目根目录（如果已有，合并内容）
3. 根据需要复制 `templates/` 中的记忆模板到 `memory/`

### 方式 3：按需挑选

不需要全部安装。按你的痛点选：

| 你的痛点 | 安装什么 |
|---------|---------|
| AI 给的数字不可信 | `.claude/rules/anti-illusion-audit.md` |
| AI 说"做完了"但质量不行 | `.claude/rules/10-engineering-laws.md` + `lifecycle-sop.md` |
| 同一个坑反复踩 | `.claude/rules/negative-results.md` |
| AI 输出太长太啰嗦 | `.claude/rules/anti-info-overload.md` |
| AI 每次对话都不一样 | `.claude/rules/identity-consistency.md` + `preference-memory.md` |
| 脚本差点删错东西 | `.claude/rules/script-safety-check.md` |
| AI 偷偷覆写文件 | `.claude/rules/no-blind-overwrite.md` |

---

## 仓库结构

```
niuma-engine/
├── CLAUDE.md                    # 根指南（Claude Code 自动加载）
├── .claude/
│   └── rules/                   # 工程法则与规则（自动加载）
│       ├── 10-engineering-laws.md      # 10 条贯穿性工程法则
│       ├── lifecycle-sop.md            # 6 阶段项目生命周期
│       ├── anti-illusion-audit.md      # 防假象审计（五连问）
│       ├── negative-results.md         # 负结果归档
│       ├── think-before-act.md         # 动手前必先思考
│       ├── identity-consistency.md     # 身份一致性
│       ├── preference-memory.md        # 偏好记忆
│       ├── boundary-declaration.md     # 边界声明
│       ├── memory-confidence.md        # 记忆置信度与失效
│       ├── memory-candidate-protocol.md # 记忆写入确认机制
│       ├── anti-info-overload.md       # 防信息过载
│       ├── no-blind-overwrite.md       # 禁止盲目覆写
│       ├── script-safety-check.md      # 脚本安全检查
│       └── mcp-config-protocol.md      # MCP 配置协议
├── templates/
│   ├── en/                      # 英文记忆模板
│   │   ├── MEMORY.md
│   │   ├── goals.md
│   │   └── identity.md
│   └── zh-CN/                   # 中文记忆模板
│       ├── MEMORY.md
│       ├── goals.md
│       └── identity.md
├── adapters/                    # 各代理适配器
│   ├── codex.md
│   ├── cursor.md
│   ├── aider.md
│   └── gemini-cli.md
├── docs/
│   ├── agent-install.md         # 代理安装指南
│   ├── compatibility.md         # 代理兼容性
│   └── philosophy.md            # 设计哲学
├── LICENSE                      # MIT
├── CONTRIBUTING.md
├── SECURITY.md
└── CHANGELOG.md
```

---

## 与 comemo 的关系

comemo 和 niuma-engine 不冲突，可以共存：

- **comemo**：轻量级记忆管理，3层架构，跨代理兼容
- **niuma-engine**：工程级纪律框架，10条法则，防错机制

如果你只用 comemo：AI 会记住你的偏好。
如果你加上 niuma-engine：AI 还会**审计自己的输出、归档死路、遵守工程纪律**。

建议：先装 comemo 管记忆，再装 niuma-engine 管纪律。

---

## 设计哲学

### 1. 诚实决定价值

口径不实的高分是负资产。永远先问「这个数字是怎么来的」。

### 2. 效率来自并行与不重复

一条没被记录的死路，会被每个后续对话重新踩一遍。归档一次 = 所有未来省去这个成本。

### 3. 边界自觉

成熟的交付 = 准确知道做到了哪、什么不能声称。

---

## 适用代理

| 代理 | 集成方式 | 状态 |
|------|---------|------|
| Claude Code | `.claude/rules/` 自动加载 | ✅ 主要目标 |
| Codex | `AGENTS.md` 桥接 | ✅ 支持 |
| Cursor | 项目规则共享 | ✅ 支持 |
| Aider | 只读上下文 | ✅ 支持 |
| Gemini CLI | 上下文发现 | ✅ 支持 |

---

## 许可证

MIT License — 随便用，随便改，随便分发。

---

## 致谢

- [comemo](https://github.com/zhang-chenhao-creator/comemo-agent-memory) — 记忆架构的灵感来源
- 副教授的「可复用 AI 工程方法论」— 10 条工程法则的理论基础
- 牛马 AI 社区 — 真实项目中的实战验证

---

> **niuma-engine** — 让 AI 像工程师一样工作，而不是像实习生一样自信。
