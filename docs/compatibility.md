# Agent Compatibility

| Agent | Integration Method | Auto Load | Rule Count | Status |
|-------|-------------------|-----------|------------|--------|
| Claude Code | `.claude/rules/` | Automatic | 29 rules | Primary Target |
| Codex | `AGENTS.md` bridge | Automatic | Configurable | Supported |
| Cursor | `.cursor/rules` | Automatic | 29 rules (symlink) | Supported |
| Aider | `.aider.conf.yml` | Manual | Configurable | Supported |
| Gemini CLI | `GEMINI.md` | Automatic | Configurable | Supported |

## Rule Loading Priority

Universal across all agents:
1. User direct instructions (highest priority)
2. Project root guide (CLAUDE.md / AGENTS.md / GEMINI.md)
3. Rule files (.claude/rules/) — 29 files, ~124KB
4. Agent default behavior (lowest priority)

## Rule Categories

| Category | Count | Key Files |
|----------|-------|-----------|
| Core Engineering Laws | 2 | 10-engineering-laws, lifecycle-sop |
| Agent Management | 3 | agent-prompt-ironclad, subagent-strategy, agent-concurrency-fallback |
| Search & Info Discipline | 3 | search-decision-tree, lesson-auto-update, anti-info-overload |
| Safety & Operations | 7 | script-safety-check, no-blind-overwrite, chinese-path-safety, powershell-safety, pre-action-check, git-recovery, mcp-config-protocol |
| Memory & Quality | 5 | memory-candidate-protocol, memory-confidence, negative-results, anti-illusion-audit, boundary-declaration |
| Architecture & Governance | 5 | competition-workspace-architecture, dual-write-protocol, no-root-rules-dir, _MIGRATED-TO-RULES |
| Skill Ecosystem | 4 | skill-auto-activation, skill-route-enforcement, skill-execution-discipline, skill-logging-enforcement |

## Memory System Compatibility

niuma-engine's memory system is based on Markdown files. All agents can read/write `.md` files under `memory/`.
