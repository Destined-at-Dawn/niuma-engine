# Aider Adapter

## Integration Method

Aider uses `.aider.conf.yml` or command-line arguments to load context.

### Quick Integration (Recommended)

Add the entire rules directory as read-only context:

```yaml
# .aider.conf.yml
read:
  - CLAUDE.md
  - .claude/rules/10-engineering-laws.md
  - .claude/rules/lifecycle-sop.md
  - .claude/rules/think-before-act.md
  - .claude/rules/anti-illusion-audit.md
  - .claude/rules/negative-results.md
  - .claude/rules/no-blind-overwrite.md
  - .claude/rules/script-safety-check.md
  - .claude/rules/anti-info-overload.md
  - .claude/rules/boundary-declaration.md
  - .claude/rules/memory-candidate-protocol.md
  - .claude/rules/memory-confidence.md
  - .claude/rules/agent-prompt-ironclad.md
  - .claude/rules/agent-concurrency-fallback.md
  - .claude/rules/subagent-strategy.md
  - .claude/rules/search-decision-tree.md
  - .claude/rules/lesson-auto-update.md
  - .claude/rules/git-recovery.md
  - .claude/rules/chinese-path-safety.md
  - .claude/rules/powershell-safety.md
  - .claude/rules/pre-action-check.md
  - .claude/rules/mcp-config-protocol.md
```

### Minimal Install (pick by pain point)

```yaml
# Core only
read:
  - CLAUDE.md
  - .claude/rules/10-engineering-laws.md
  - .claude/rules/lifecycle-sop.md
  - .claude/rules/think-before-act.md
  - .claude/rules/no-blind-overwrite.md
  - .claude/rules/script-safety-check.md
```

### Notes
- Aider's `--read` files are read-only context
- Memory files (memory/) are managed separately
- Full rule list: 29 files in `.claude/rules/`
