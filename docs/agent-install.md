# Agent Installation Guide

## Automatic Installation (Recommended)

Clone the repo, then tell your AI agent:

```
Read CLAUDE.md and the .claude/rules/ directory.
Help me integrate niuma-engine into this project.
Show me the installation plan. Do not overwrite anything without my approval.
```

The AI will:
1. Read the startup sequence in CLAUDE.md
2. Load all 29 rules from .claude/rules/
3. Check for existing memory files
4. Propose an integration plan

## Manual Installation

### Claude Code (Primary Target)
```bash
git clone https://github.com/Destined-at-Dawn/niuma-engine.git
cp -r niuma-engine/.claude/rules/ your-project/.claude/rules/
cp niuma-engine/CLAUDE.md your-project/CLAUDE.md
cp -r niuma-engine/templates/zh-CN/ your-project/memory/
```

### Other Agents
See the corresponding adapter file:
- Codex: `adapters/codex.md`
- Cursor: `adapters/cursor.md`
- Aider: `adapters/aider.md`
- Gemini CLI: `adapters/gemini-cli.md`

## Pick by Pain Point

You don't need all 29 rules. Copy only what matches your problems:

| Pain Point | Install These |
|------------|--------------|
| AI numbers untrustworthy | anti-illusion-audit.md |
| AI says "done" but quality poor | 10-engineering-laws.md + lifecycle-sop.md |
| Same pitfall keeps recurring | negative-results.md |
| AI output too verbose | anti-info-overload.md |
| Script almost deleted wrong thing | script-safety-check.md |
| AI silently overwrites files | no-blind-overwrite.md |
| Multi-agent coordination chaos | agent-prompt-ironclad + subagent-strategy + agent-concurrency-fallback |
| Full discipline system | All 29 rules in .claude/rules/ |

## Post-Installation Verification

1. Start a new conversation
2. Ask: "What is evidence layering?" — AI should reference Law 1
3. Give the AI an abnormally good number — it should trigger an anti-illusion audit
4. Ask: "What rules are active?" — it should list rules from .claude/rules/
