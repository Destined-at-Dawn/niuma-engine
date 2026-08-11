# Agent compatibility

**Document review date:** 2026-08-11  
**Ruleset:** v5.0.0 / 34 Markdown rule files

| Agent | Integration method | Status | Verification scope |
|---|---|---|---|
| Claude Code | `.claude/rules/` and optional `CLAUDE.md` | Primary target | Rule directory and root guide are shipped; verify in a clean project. |
| Codex | `AGENTS.md` that references copied rule files | Documented integration | A minimal example is in `adapters/codex/AGENTS.md.example`. |
| Cursor | `.cursor/rules` | Documented integration | Follow `adapters/cursor.md`; validate against your Cursor version. |
| Aider | `.aider.conf.yml` | Documented integration | Follow `adapters/aider.md`; rule loading is configuration-dependent. |
| Gemini CLI | `GEMINI.md` | Documented integration | Follow `adapters/gemini-cli.md`; validate against your Gemini CLI version. |

## Loading precedence

Agent-specific precedence can change. In general, direct user instructions override project instructions, which override referenced rule files. Treat this table as integration guidance rather than a guarantee of identical behavior across tools.

## Rule categories

| Category | Examples |
|---|---|
| Engineering discipline | `10-engineering-laws.md`, `lifecycle-sop.md`, `think-before-act.md` |
| File and script safety | `no-blind-overwrite.md`, `script-safety-check.md`, `git-recovery.md` |
| Evidence and quality | `anti-illusion-audit.md`, `boundary-declaration.md`, `negative-results.md` |
| Agent coordination | `agent-prompt-ironclad.md`, `subagent-strategy.md` |
| Reference architectures | `21-git-archive-ironlaw.md`, `knowledge-hub-architecture.md`, `scheduled-task-dual-redundancy.md` |

See [Capabilities](capabilities.md) for the distinction between shipped rules, documented integrations, and reference architectures.
