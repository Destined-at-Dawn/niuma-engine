# niuma-engine v5.0

**不是"又一个 AI 规则集"。是从 6 次事故长出来的工程纪律框架，现已进化到跨工具生态系统。**

[English](README.en.md) | 中文

---

## v5.0 的核心跳跃

| 维度 | v4.0 (2026-06) | v5.0 (2026-07) |
|------|---------------|---------------|
| 治理范围 | 单工具（Claude Code） | 跨工具（AI + OS 定时任务 + 知识中枢） |
| 规则数 | 29 条 | **34 条** |
| 文件保护 | 单层规则（no-blind-overwrite） | **三层体系**（归档 + Git分支隔离 + 每日Zip） |
| Skill 质量 | "读5个参考再建" | **对标标准**（6顶层文件 + 5+ refs + 1+ script + 24项门禁） |
| 知识管理 | 工作区各自独立 | **知识中枢**（单一真相源 + 一改全改 + 跨区教训共享） |
| 定时任务 | 单套调度 | **双冗余**（AI + OS 独立调度，互相兜底） |
| 多Agent | Agent 三要素 + 隔离契约 | **+ Workflow 编排**（pipeline/parallel + 阶段门禁） |

---

## 这不是什么

[CRITICAL] 不是"又一个提示词模板"
[CRITICAL] 不是"让 AI 变聪明"的魔法
[CRITICAL] 不是闭着眼装上就能用的插件

**这是一个纪律框架。** 它不会让 AI 变聪明，但它会让 AI 少犯错，犯了错能被抓住，同样的错不犯第二次。

---

## 三层文件保护（v5.0 核心新增）

```
L1 操作前归档 ---> 修改/删除任何文件前先复制到归档目录
L2 Git分支隔离 --> 所有AI修改走 agent/{date} 分支，3天自动合并，禁止直推main
L3 每日Zip快照 -> 每天23:59全量打包，7天内全保留
```

每一层都可以独立失效。数据丢失需要三层同时失效。

---

## 知识中枢架构（v5.0 核心新增）

```
知识中枢（单一真相源）
├── 共享规则 --> 一改全改，li-sync 自动同步到所有工作区
├── 跨区教训 --> 一次踩坑，所有工作区可见（禁止只写本地）
├── SOP库    --> 无SOP的任务先查中枢再动手
└── 全局注册表 --> 工作区/Skill/规则的元数据索引
```

五个工作区，一个大脑。

---

## 10 条核心工程法则（v1.0 保留至今）

| 法则 | 一句话 |
|------|--------|
| 1 证据分层 | 任何"通过"必须带口径标签（粗筛/中级/全签核） |
| 2 防假象审计 | 异常好数字先假设是假象，五连问验证 |
| 3 实测优先 | 优化方向必须扫描验证，不凭直觉 |
| 4 工具自由度 | 给成熟工具空间，克制人工 hint |
| 5 跨边界校验 | 系统接缝处先校验格式/编码/单位 |
| 6 隔离契约 | 多Agent写入区严格隔离 |
| 7 负结果归档 | 死路必须入档，防止重复踩坑 |
| 8 门禁不可跳过 | "完成"= 过全部门禁 |
| 9 识别结构墙 | 平台期换角度，天花板就停 |
| 10 规则结晶 | 经验 -> 规则 -> Skill，复利沉淀 |

---

## 快速开始

### 按痛点安装

| 你的核心痛点 | 只需装这几条规则 |
|---------|---------|
| 担心 AI 搞乱/搞丢文件 | `21-git-archive-ironlaw.md` + `no-blind-overwrite.md` |
| AI 给的数字不可信 | `anti-illusion-audit.md` |
| 多个工作区管理混乱 | `knowledge-hub-architecture.md` |
| 定时任务静默失败 | `scheduled-task-dual-redundancy.md` |
| 新建 skill 质量参差不齐 | `skill-quality-benchmark.md` |
| AI 说"做完了"但质量不行 | `10-engineering-laws.md` + `lifecycle-sop.md` |
| 同一个坑反复踩 | `negative-results.md` |
| 多 Agent 互相覆盖/冲突 | `agent-prompt-ironclad.md` + `subagent-strategy.md` |
| 想从零搭建完整纪律体系 | 全装 `.claude/rules/`（共34条） |
| 报了 AI 课，不知道怎么持续进阶 | `docs/student-pathway/`（六层成长路线图 L0-L5） |

### 安装

```bash
git clone https://github.com/Destined-at-Dawn/niuma-engine.git
cd niuma-engine
```

然后让你的 AI 代理自己读 `docs/agent-install.md`。**让 AI 自己装自己。**

支持的代理：
- Claude Code（`.claude/rules/` 自动加载）<-- 主要目标
- Codex / Cursor / Aider / Gemini CLI（通过 adapter 桥接）

---

## 仓库结构

```
niuma-engine/
├── README.md                     <-- 你在这
├── CHANGELOG.md                  <-- 版本历史
├── .claude/rules/                <-- 核心规则（Claude Code 自动加载，共 34 条）
│   ├── 10-engineering-laws.md            十条贯穿性工程法则
│   ├── 21-git-archive-ironlaw.md         三层文件保护铁律（v5.0 NEW）
│   ├── knowledge-hub-architecture.md     知识中枢架构规则（v5.0 NEW）
│   ├── scheduled-task-dual-redundancy.md 定时任务双冗余规则（v5.0 NEW）
│   ├── skill-quality-benchmark.md        Skill质量对标规则（v5.0 NEW）
│   ├── student-onboarding.md             学员引导铁律，自门控（v5.0 NEW）
│   ├── (其余 28 条规则...)
├── docs/student-pathway/         <-- 学员六层成长路线图（v5.0 NEW，L0-L5）
├── templates/                    <-- 记忆模板（中/英）
├── adapters/                     <-- 各 Agent 适配器
└── docs/                         <-- 设计哲学 + 安装指南
```

---

## 版本进化

| 版本 | 日期 | 核心变化 |
|------|------|---------|
| v1.0 | 2026-05 | 10条工程法则 + 6阶段SOP，单工具纪律 |
| v4.0 | 2026-06 | 29条规则，多Agent协作 + Skill路由 + 搜索决策树 |
| **v5.0** | **2026-07** | **34条规则，知识中枢 + 三层保护 + 质量对标 + 双冗余 + 学员成长路线图** |

---

## 协议

MIT -- 用，改，发，随你。

---

## 致谢

- 数字生命卡兹克（Khazix）的 storage-analyzer -- 让我意识到「开源一个 AI skill」可以帮到多少人
- comemo 的记忆架构 -- 给我三层分层的灵感
- 副教授的「可复用 AI 工程方法论」-- 10 条法则的理论地基
- 5 个真实工作区 + 多次事故 -- 所有规则的真实验证场

---

> **让 AI 像工程师一样工作，而不是像实习生一样自信。**
>
> v5.0: 从单工具纪律到跨工具生态系统。34 条规则，每一块都是一次事故的墓碑。
