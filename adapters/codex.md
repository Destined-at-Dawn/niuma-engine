# Codex Adapter

## Integration Method

Codex uses `AGENTS.md` as its root guide. niuma-engine's `CLAUDE.md` needs to be bridged to `AGENTS.md`.

### Quick Integration

1. Create `AGENTS.md` in the project root directory (if it does not exist)
2. Add the following at the top of `AGENTS.md`:

```markdown
> Engineering framework: This project uses niuma-engine.
> Rule files are in the .claude/rules/ directory.
> See CLAUDE.md for detailed guidelines.
```

3. Append the contents of rule files in `.claude/rules/` to `AGENTS.md`, or keep them as independent files with references.

### Rule Loading

Codex automatically reads the `AGENTS.md` file in the project root directory. If rule files are kept independent, they must be explicitly referenced in `AGENTS.md`:
```
## Engineering Rules
- See .claude/rules/10-engineering-laws.md for details
- See .claude/rules/lifecycle-sop.md for details
```

### Notes
- Codex does not automatically load the `.claude/rules/` directory
- All critical rules must have references or be inlined in `AGENTS.md`
- Memory file paths (memory/) remain unchanged
