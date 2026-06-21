# niuma-engine

**Not just a memory system -- it's engineering discipline for AI collaboration.**

English | [中文](README.md)

---

## What Is This

niuma-engine is an **engineering-grade collaboration framework** for AI coding agents (Claude Code, Codex, Cursor, Gemini CLI, Aider).

It transforms the work disciplines of human engineers -- evidence layering, anti-illusion audits, negative result archiving, gate culture -- into rules that AI agents can understand and execute.

**Comparison with comemo**:

| Dimension | comemo | niuma-engine |
|-----------|--------|-------------|
| Memory architecture | 3-layer (global/project/personal) | 3-layer + confidence labels + expiration conditions |
| Rule system | Basic collaboration rules | 29 engineering rules + 6-stage lifecycle |
| Error prevention | None | Anti-illusion audit (five questions) + negative result archiving |
| Security mechanisms | None | Script safety checks + dual-archive + no blind overwriting |
| Self-improvement | None | Experience -> Rule -> Skill automatic crystallization |
| Information control | None | Anti-information overload + boundary declarations |

**In one sentence**: comemo teaches AI to remember your preferences; niuma-engine teaches AI to **work like an engineer**.

---

## Who Is This For

- People using AI coding agents for real projects (not toy demos)
- People who have been burned by AI "confidently giving wrong good results"
- People who want AI to remember "which paths don't work" -- not just "which paths work"
- People who need consistent AI collaboration standards across multiple projects
- People who don't want to start from scratch with every new conversation

---

## Core Modules

### 10 Engineering Laws (Horizontal Axis -- Always Active)

| Law | One-liner | When You Need It |
|-----|-----------|-----------------|
| 1. Evidence Layering | Any "pass" must carry a calibration label | AI says "test passed" but you're unsure of its credibility |
| 2. Anti-Illusion Audit | High scores first audit how they were produced | AI gives an abnormally good number |
| 3. Empirical Testing First | Scan and verify, don't assume monotonicity | AI says "bigger is better" when tuning parameters |
| 4. Tool Freedom | Restrain manual hints | You can't resist using hard constraints to help the tool |
| 5. Cross-Boundary Validation | Format/encoding/units/naming | Data passes between two systems |
| 6. Isolation Contracts | Multi-agent write zone isolation | Multiple AIs modifying code simultaneously |
| 7. Negative Result Archiving | Dead ends must be archived | You took a detour and don't want to take it again |
| 8. Gate Culture | Done = passed all gates | AI says "it's done" but you're not sure |
| 9. Recognize Structural Walls | Plateau = change angle | The same problem keeps failing |
| 10. Rule Crystallization | Experience -> Rule -> Skill | Summarize lessons to prevent recurrence |

### 6-Stage Lifecycle (Vertical Axis -- Over Time)

```
Project Scoping -> Solution Exploration -> Parallel攻坚 -> Layered Verification -> Retrospective Crystallization -> Delivery Declaration
```

Each stage has **target deliverables, standard actions, exit gates, and anti-patterns**.

### 3-Layer Memory System

```
Global Rules (always active)
  └── Project Memory (loaded per project)
       └── Personal Memory (loaded on demand)
```

Each memory entry carries a **confidence label** (high/medium/pending) and **expiration conditions**.

---

## Quick Start

### Method 1: Automatic Installation (Recommended)

```bash
# Clone the repository
git clone https://github.com/Destined-at-Dawn/niuma-engine.git
cd niuma-engine

# Give the repository to your AI agent and have it read the installation guide
# Claude Code: read docs/agent-install.md
# Codex: read docs/agent-install.md
# Others: read docs/agent-install.md
```

### Method 2: Manual Installation

1. Copy `.claude/rules/` to your project root directory
2. Copy `CLAUDE.md` to your project root directory (merge content if it already exists)
3. Copy memory templates from `templates/` to `memory/` as needed

### Method 3: Pick and Choose

No need to install everything. Choose based on your pain points:

| Your Pain Point | What to Install |
|----------------|----------------|
| AI's numbers aren't trustworthy | `.claude/rules/anti-illusion-audit.md` |
| AI says "done" but quality is poor | `.claude/rules/10-engineering-laws.md` + `lifecycle-sop.md` |
| Same pitfall keeps recurring | `.claude/rules/negative-results.md` |
| AI output is too long and verbose | `.claude/rules/anti-info-overload.md` |
| AI is different every conversation | Create your own style guide + `10-engineering-laws.md` (method consistency) |
| Script almost deleted the wrong thing | `.claude/rules/script-safety-check.md` |
| AI silently overwrites files | `.claude/rules/no-blind-overwrite.md` |

---

## Repository Structure

```
niuma-engine/
├── README.md                     # You are here
├── CHANGELOG.md                  # Version history
├── .claude/rules/                # Core rules (auto-loaded, 29 files)
│   ├── 10-engineering-laws.md         # 10 cross-cutting engineering laws
│   ├── lifecycle-sop.md              # 6-stage project lifecycle
│   ├── anti-illusion-audit.md        # Anti-illusion audit
│   ├── think-before-act.md           # Think before acting
│   ├── agent-concurrency-fallback.md # Agent concurrency fallback protocol
│   ├── agent-prompt-ironclad.md      # Agent prompt iron law
│   ├── subagent-strategy.md          # Sub-agent strategy
│   ├── search-decision-tree.md       # Search decision tree
│   ├── lesson-auto-update.md         # Lesson auto-update loop
│   ├── skill-auto-activation.md      # Skill auto-activation v2.0
│   ├── skill-route-enforcement.md    # Skill route enforcement
│   ├── skill-execution-discipline.md # Skill execution discipline
│   ├── skill-logging-enforcement.md  # Skill logging enforcement
│   ├── chinese-path-safety.md        # Chinese path safety (Windows)
│   ├── powershell-safety.md          # PowerShell safety
│   ├── pre-action-check.md           # Pre-action checklist
│   ├── git-recovery.md               # Git checkpoint & recovery
│   ├── mcp-config-protocol.md        # MCP config protocol
│   ├── competition-workspace-architecture.md  # Competition workspace arch
│   ├── dual-write-protocol.md        # Dual-write protocol
│   ├── no-root-rules-dir.md          # No root rules/ directory
│   ├── negative-results.md           # Negative result archiving
│   ├── memory-candidate-protocol.md  # Memory write confirmation
│   ├── memory-confidence.md          # Memory confidence & expiration
│   ├── anti-info-overload.md         # Anti-information overload
│   ├── no-blind-overwrite.md         # No blind overwriting
│   ├── script-safety-check.md        # Script safety check
│   ├── boundary-declaration.md       # Boundary declaration
│   └── _MIGRATED-TO-RULES.md         # Migration documentation
├── templates/                    # Memory templates (zh-CN / en)
├── adapters/                     # Agent adapters
└── docs/                         # Design philosophy + install guide
```

---

## Relationship with comemo

comemo and niuma-engine are not in conflict -- they can coexist:

- **comemo**: Lightweight memory management, 3-layer architecture, cross-agent compatible
- **niuma-engine**: Engineering-grade discipline framework, 10 laws, error prevention mechanisms

If you only use comemo: AI will remember your preferences.
If you add niuma-engine: AI will also **audit its own output, archive dead ends, and遵守 engineering discipline**.

Recommendation: Install comemo first for memory, then add niuma-engine for discipline.

---

## Design Philosophy

### 1. Honesty Determines Value

A high score with a false calibration is a negative asset. Always ask first: "How was this number produced?"

### 2. Efficiency Comes from Parallelism and Non-Repetition

An unrecorded dead end will be retried by every subsequent conversation. Archive once = all future sessions save that cost.

### 3. Boundary Awareness

A mature delivery = accurately knowing what was achieved and what cannot be claimed.

---

## Supported Agents

| Agent | Integration Method | Status |
|-------|-------------------|--------|
| Claude Code | `.claude/rules/` auto-load | Primary Target |
| Codex | `AGENTS.md` bridge | Supported |
| Cursor | Project rule sharing | Supported |
| Aider | Read-only context | Supported |
| Gemini CLI | Context discovery | Supported |

---

## License

MIT License -- use freely, modify freely, distribute freely.

---

## Acknowledgments

- [comemo](https://github.com/zhang-chenhao-creator/comemo-agent-memory) -- inspiration for memory architecture
- Associate Professor's "Reusable AI Engineering Methodology" -- theoretical foundation for the 10 engineering laws
- Niuma AI Community -- real-world validation in production projects

---

> **niuma-engine** -- Making AI work like an engineer, not like a confident intern.
