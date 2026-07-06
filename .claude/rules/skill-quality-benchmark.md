# Skill 质量对标规则（Skill Quality Benchmark）

> 优先级：高（与 skill-route-enforcement 同级）
> 创建：2026-07-06
> 根因：新创建 skill 只有 4 个文件，对标最优 skill 的 17 个文件，补齐花了 3 轮迭代

---

## 核心铁律

**新创建的 skill 必须对齐当前生态内最优 skill 的文件结构标准。**

---

## 一、对标标准（Benchmark Standard）

### 顶层必备文件（6个）

| 文件 | 必备 | 说明 |
|------|------|------|
| SKILL.md | REQUIRED | 主文件，含执行协议 + 配套文件清单 |
| _meta.json | REQUIRED | 元数据：版本/创建日期/触发词/依赖 |
| eval.json | REQUIRED | 质量门禁（>=20项断言） |
| golden_rules.md | REQUIRED | 黄金规则（>=9条） |
| DEPRECATED.md | CONDITIONAL | 仅在弃用时创建 |
| lifecycle-log.md | REQUIRED | 生命周期记录 |

### references/ 目录（>=5个文件）

| 文件类型 | 最低数量 | 示例 |
|----------|---------|------|
| 方法论/流程文件 | >=2 | methodology.md, workflow.md |
| 案例/模式库 | >=1 | case-studies.md, anti-patterns.md |
| 联动/生态文件 | >=1 | skill-linkage.md |
| 补充/边缘情况 | >=1 | supplementary.md |

### scripts/ 目录（>=1个可运行脚本）

自动化检查/扫描脚本，如 scan_xxx.py

---

## 二、质量门禁分级

### 创建门禁（24项）

| 类别 | 项目数 | 包含 |
|------|--------|------|
| 基础结构 | 6项 | SKILL.md存在、_meta.json完整、触发词>=15等 |
| 方法论完整 | 6项 | 执行协议完整、Phase流程清晰、references>=5等 |
| 对标检查 | 6项 | 顶层6文件齐全、eval.json>=20项、scripts>=1等 |
| 联动注册 | 6项 | 路由表已注册、联动链已配置、配套文件清单完整等 |

### 迭代门禁（每次迭代后检查）

- [ ] 配套文件清单已逐项检查
- [ ] references/ 文件是否需要更新
- [ ] scripts/ 是否需要修复
- [ ] 路由触发词是否需要扩展

---

## 三、对标参照物（生态内标杆）

| Skill | 文件数 | 作为什么场景的参照 |
|-------|--------|---------------------|
| li-research | 17+ | 深度研究类 |
| li-skillcreate | 20+ | 创建/管理类 |
| li-renhua | 13 | 内容处理类 |
| li-transcript | 15+ | 转录/处理类 |

---

## 四、防退化机制

退化信号：
- [ ] 迭代后 references/ 文件数减少
- [ ] golden_rules.md 被删除或清空
- [ ] lifecycle-log.md 超过 30 天未更新
- [ ] scripts/ 下的 .py 文件语法错误

---

## 五、三阶段学习闭环（道法术）

| 层 | 问题 | 修复 |
|---|------|------|
| 道 | 设计哲学只学外部方法，不学内部结构标准 | Phase 1 新增对标学习 |
| 法 | 门禁有标配但没指定对标谁 | 明确顶层6文件 + references>=5 + scripts>=1 |
| 术 | 落盘验证只检查 references/ | Phase 4 扩展验证到全部对标文件 |

---

> 创建日期：2026-07-06
> 来源：li-skillcreate v11.0 对标升级经验
> 关联：skill-route-enforcement.md, skill-execution-discipline.md
