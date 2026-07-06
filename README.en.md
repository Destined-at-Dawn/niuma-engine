# niuma-engine v5.0

**From single-tool discipline to cross-tool ecosystem. 33 rules grown from real accidents.**

English | [中文](README.md)

---

## The v5.0 Leap

| Dimension | v4.0 (2026-06) | v5.0 (2026-07) |
|-----------|---------------|---------------|
| Governance Scope | Single tool (Claude Code) | Cross-tool (AI + OS scheduled tasks + Knowledge Hub) |
| Rules | 29 | **33** |
| File Protection | Single-layer rules | **Three-layer system** (archive + git branch + daily zip) |
| Skill Quality | "Read 5 references" | **Benchmark standard** (6 top files + 5+ refs + 1+ script + 24 gates) |
| Knowledge | Per-workspace independent | **Knowledge Hub** (single truth source + sync-all + cross-workspace lessons) |
| Scheduled Tasks | Single scheduler | **Dual redundancy** (AI + OS independent scheduling, mutual fallback) |
| Multi-Agent | Agent 3-elements + isolation | **+ Workflow orchestration** (pipeline/parallel + phase gates) |

---

## What This Is NOT

[CRITICAL] NOT another prompt template
[CRITICAL] NOT magic to make AI smarter
[CRITICAL] NOT a plug-and-play plugin

**This is a discipline framework.** It won't make AI smarter, but it will make AI make fewer mistakes, catch mistakes when they happen, and never repeat the same mistake twice.

---

## Three-Layer File Protection (v5.0 Core Addition)

```
L1 Pre-modification Archive --> Copy original to archive directory before any file change
L2 Git Branch Isolation ----> All AI changes go through agent/{date} branch, 3-day auto-merge, no direct main push
L3 Daily Zip Snapshot -------> Full backup at 23:59 daily, full retention for 7 days
```

Each layer can fail independently. Data loss requires all three layers to fail simultaneously.

---

## Knowledge Hub Architecture (v5.0 Core Addition)

```
Knowledge Hub (single source of truth)
├── Shared Rules --> Edit once, li-sync auto-syncs to all workspaces
├── Cross-Workspace Lessons --> One mistake, visible to all workspaces
├── SOP Library --> No SOP? Check the Hub first
└── Global Registry --> Metadata index for workspaces/skills/rules
```

Five workspaces, one brain.

---

## 10 Core Engineering Laws (since v1.0)

| Law | One-liner |
|-----|-----------|
| 1. Evidence Layering | Every "pass" carries a calibration label |
| 2. Anti-Illusion Audit | High scores first audit how they were produced |
| 3. Empirical Testing First | Scan and verify, don't assume monotonicity |
| 4. Tool Freedom | Restrain manual hints, let tools work |
| 5. Cross-Boundary Validation | Validate format/encoding/units at system seams |
| 6. Isolation Contracts | Strict write-zone isolation for multi-agent work |
| 7. Negative Result Archiving | Dead ends must be documented |
| 8. Gate Culture | "Done" = passed all gates |
| 9. Recognize Structural Walls | Plateau = change angle, ceiling = stop |
| 10. Rule Crystallization | Experience -> Rule -> Skill, compound interest |

---

## Quick Start

### Install by Pain Point

| Your Pain Point | What to Install |
|----------------|----------------|
| Worried AI will mess up / lose files | `21-git-archive-ironlaw.md` + `no-blind-overwrite.md` |
| AI's numbers aren't trustworthy | `anti-illusion-audit.md` |
| Multiple workspaces are chaotic | `knowledge-hub-architecture.md` |
| Scheduled tasks silently fail | `scheduled-task-dual-redundancy.md` |
| New skills have inconsistent quality | `skill-quality-benchmark.md` |
| AI says "done" but quality is poor | `10-engineering-laws.md` + `lifecycle-sop.md` |
| Same pitfall keeps recurring | `negative-results.md` |
| Multiple agents overwrite each other | `agent-prompt-ironclad.md` + `subagent-strategy.md` |
| Full discipline system from scratch | Install all `.claude/rules/` (33 rules) |

### Install

```bash
git clone https://github.com/Destined-at-Dawn/niuma-engine.git
cd niuma-engine
```

Let your AI agent read `docs/agent-install.md`. **Let AI install itself.**

Supported agents: Claude Code (primary) / Codex / Cursor / Aider / Gemini CLI

---

## Repository Structure

```
niuma-engine/
├── README.md                     <-- You are here
├── CHANGELOG.md                  <-- Version history
├── .claude/rules/                <-- Core rules (33 files, auto-loaded)
│   ├── 10-engineering-laws.md            Ten cross-cutting engineering laws
│   ├── 21-git-archive-ironlaw.md         Three-layer file protection (v5.0 NEW)
│   ├── knowledge-hub-architecture.md     Knowledge Hub architecture (v5.0 NEW)
│   ├── scheduled-task-dual-redundancy.md Dual redundancy for tasks (v5.0 NEW)
│   ├── skill-quality-benchmark.md        Skill quality benchmark (v5.0 NEW)
│   ├── (remaining 29 rules...)
├── templates/                    <-- Memory templates (zh-CN / en)
├── adapters/                     <-- Agent adapters
└── docs/                         <-- Design philosophy + install guide
```

---

## Version History

| Version | Date | Core Change |
|---------|------|-------------|
| v1.0 | 2026-05 | 10 engineering laws + 6-stage SOP, single-tool discipline |
| v4.0 | 2026-06 | 29 rules, multi-agent + skill routing + search decision trees |
| **v5.0** | **2026-07** | **33 rules, Knowledge Hub + 3-layer protection + quality benchmark + dual redundancy** |

---

## License

MIT -- use freely, modify freely, distribute freely.

---

> **Making AI work like an engineer, not like a confident intern.**
>
> v5.0: From single-tool discipline to cross-tool ecosystem. 33 rules. Each one is a tombstone of a real accident.
