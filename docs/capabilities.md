# Capabilities and boundaries

This page separates what the repository ships today from patterns that need implementation in your own environment. It is the source of truth for public capability claims.

**Last reviewed:** 2026-08-11  
**Current ruleset:** v5.0.0 / 34 Markdown rule files

| Capability | Public artifact | Status | What this means |
|---|---|---|---|
| Core engineering rules | `.claude/rules/` | Shipped | 34 Markdown rule files that can be copied or adapted into a project. |
| Claude Code setup | `.claude/rules/`, `CLAUDE.md` | Documented integration | The repository contains the rule directory and a root guide; test it in a disposable project before relying on it. |
| Codex setup | `adapters/codex.md`, `adapters/codex/AGENTS.md.example` | Documented integration | Copy selected rules into your project and reference them from `AGENTS.md`. |
| Cursor, Aider, Gemini CLI setup | `adapters/` | Documented integration | Instructions are provided, but compatibility is not continuously guaranteed. |
| Three-layer file protection | `21-git-archive-ironlaw.md` | Reference policy | The repository supplies the policy. Archive scripts, branch protection, scheduled backups, and retention must be implemented and operated by the adopter. |
| Knowledge Hub | `knowledge-hub-architecture.md` | Reference architecture | The directory model and synchronization protocol are documented; no general-purpose sync service is shipped here. |
| Dual scheduler | `scheduled-task-dual-redundancy.md` | Reference architecture | The redundancy design is documented; no portable scheduler configuration or executable jobs are shipped here. |
| Skill quality benchmark | `skill-quality-benchmark.md` | Maintainer workflow reference | The rule describes a benchmark learned from a specific ecosystem. Adopters should adapt its thresholds to their own public, reproducible baseline. |

## Verification scope

- Rule files are guidance, not enforcement code.
- The user and maintainer remain responsible for reviewing changes, configuring repository protection, and operating any backup or scheduling systems.
- Claims about support should use one of these terms: **Shipped**, **Documented integration**, or **Reference architecture**.
- Do not describe a reference architecture as an installed automation unless a linked public implementation exists.

## Reporting drift

If a README, adapter, rule, or release note contradicts this page, open a documentation Issue and include the file path and the exact conflicting statement.
