# Design Philosophy (v5.0)

## From Discipline Framework to Ecosystem

v1.0 was a solo discipline: one person, one AI, 10 rules to stop accidents.

v4.0 became a team sport: 29 rules covering multi-agent coordination, skill routing, and cross-workspace sync.

**v5.0 is an ecosystem.** It governs not just one AI agent, but the entire system of agents, workspaces, scheduled tasks, skills, and knowledge that form the backbone of AI-assisted work.

---

## The Three Paradigm Shifts

### Shift 1: From Tool to Architecture

v4.0 treated each workspace as an independent unit. Rules were copied between workspaces. Knowledge stayed local.

v5.0 introduces the **Knowledge Hub** as a single source of truth:
- Shared rules live in one place, projected to all workspaces
- Cross-tool lessons are dual-written: local + hub
- A dedicated guardian (li-zhongshu) enforces synchronization

### Shift 2: From Single Layer to Defense in Depth

v4.0 had individual safety rules (no-blind-overwrite, script-safety-check, git-recovery).

v5.0 layers them into a **three-layer protection system (R21)**:
- L1: Archive before every modification
- L2: Git branch isolation (agent/{date}, auto-merge after 3 days)
- L3: Daily zip snapshots with retention policy

Each layer can fail independently. Data loss requires all three layers to fail simultaneously.

### Shift 3: From "Good Enough" to "Benchmarked"

v4.0's skill creation guidance was: "Read 5 reference skills, then build."

v5.0 adds a **quality benchmark**: every new skill must match the file structure of the ecosystem's best skills (6 top-level files + 5+ references + 1+ script + 24 quality gates).

This came from a real incident: a skill was created with 4 files, while the benchmark skill had 17. It took 3 rounds of iteration to catch up. Now the benchmark enforces this from the start.

---

## What v5.0 Governs

| Layer | What | Primary Rules |
|-------|------|---------------|
| File Safety | Prevent data loss from AI mistakes | 21-git-archive-ironlaw, no-blind-overwrite, git-recovery |
| Agent Coordination | Multiple agents working without conflict | agent-prompt-ironclad, subagent-strategy, agent-concurrency-fallback |
| Knowledge Flow | Lessons and rules shared across workspaces | knowledge-hub-architecture, lesson-auto-update, dual-write-protocol |
| Skill Quality | Skills that actually meet production standards | skill-quality-benchmark, skill-route-enforcement, skill-execution-discipline |
| Task Reliability | Scheduled tasks that don't silently fail | scheduled-task-dual-redundancy |
| Engineering Discipline | How individual tasks are executed | 10-engineering-laws, lifecycle-sop, think-before-act |

---

## Principles That Survive All Versions

1. **Rules grow from real accidents.** Every rule in this repo blocked a confirmed failure pattern. No rule was designed in isolation.

2. **Negative results are first-class citizens.** Dead ends are documented, shared across workspaces via the Knowledge Hub, so no conversation repeats the same mistake.

3. **Evidence over claims.** Every pass/complete/done statement carries a calibration label. Numbers without source are suspicion, not information.

4. **The framework is alive.** It updates as new failure patterns are recognized in production. You are reading a snapshot, not a final answer.

---

> v5.0, July 2026
> 33 rules, 5 workspaces, 128+ skills, 6 scheduled tasks
> From discipline to ecosystem.
