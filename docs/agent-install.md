# Agent Installation Guide

## Automatic Installation (Recommended)

Give this repository to your AI agent and have it execute the following instruction:

```
Read the CLAUDE.md file and all files in .claude/rules/ directory.
Then help me integrate niuma-engine into this project.
Check for existing memory files, show me the installation plan,
and do not overwrite anything without my approval.
```

## Manual Installation

### Claude Code
1. Copy `.claude/rules/` to your project root directory
2. Copy `CLAUDE.md` to your project root directory (merge if it already exists)
3. Copy `templates/zh-CN/` or `templates/en/` to `memory/`

### Codex
1. Refer to `adapters/codex.md`

### Cursor
1. Refer to `adapters/cursor.md`

### Aider
1. Refer to `adapters/aider.md`

### Gemini CLI
1. Refer to `adapters/gemini-cli.md`

## Post-Installation Verification

1. In a new conversation, the AI should be able to read the rules in `.claude/rules/`
2. Test: Ask the AI "What is evidence layering?" -- it should reference Law 1
3. Test: Give the AI an abnormally good number -- it should trigger an anti-illusion audit
