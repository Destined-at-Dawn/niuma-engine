# Codex Adapter

## Integration Method

Codex uses `AGENTS.md` as its root guide.

### Quick Integration

1. Create `AGENTS.md` in the project root, referencing the full rule set:

```markdown
> Engineering framework: This project uses niuma-engine v4.0 (29 rules).
> All rule files are in the .claude/rules/ directory.
> See CLAUDE.md for the startup sequence and core principles.
```

2. Append rule references to `AGENTS.md`:

```markdown
## Engineering Rules (niuma-engine v4.0)
- Core: .claude/rules/10-engineering-laws.md (10 cross-cutting laws)
- Lifecycle: .claude/rules/lifecycle-sop.md (6-stage project lifecycle)
- Audit: .claude/rules/anti-illusion-audit.md (anti-illusion five questions)
- Archive: .claude/rules/negative-results.md (dead end archiving)
- Safety: .claude/rules/script-safety-check.md + no-blind-overwrite.md
- Agents: .claude/rules/agent-prompt-ironclad.md + subagent-strategy.md + agent-concurrency-fallback.md
- Search: .claude/rules/search-decision-tree.md + lesson-auto-update.md
- Full set: 29 rules in .claude/rules/
```

### Notes
- Codex does not auto-load `.claude/rules/` — must be referenced in `AGENTS.md`
- All critical rules should have references in `AGENTS.md`
- Total: 29 rule files, ~124KB of engineering discipline
