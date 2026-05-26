# Agent Compatibility

| Agent | Integration Method | Auto Load | Memory System | Status |
|-------|-------------------|-----------|---------------|--------|
| Claude Code | `.claude/rules/` | Automatic | Native | Primary Target |
| Codex | `AGENTS.md` bridge | Automatic | Requires config | Supported |
| Cursor | `.cursor/rules` | Automatic | Requires config | Supported |
| Aider | `.aider.conf.yml` | Manual | Manual management | Supported |
| Gemini CLI | `GEMINI.md` | Automatic | Requires config | Supported |

## Rule Loading Priority

Universal across all agents:
1. User direct instructions (highest priority)
2. Project root guide (CLAUDE.md / AGENTS.md / GEMINI.md)
3. Rule files (.claude/rules/)
4. Agent default behavior (lowest priority)

## Memory System Compatibility

niuma-engine's memory system is based on Markdown files and does not depend on any platform-specific features.
All agents can read and write `.md` files under the `memory/` directory.
