# Aider Adapter

## Integration Method

Aider uses `.aider.conf.yml` or command-line arguments to load context.

### Quick Integration

1. Add rule files as read-only context in `.aider.conf.yml`:
   ```yaml
   read:
     - .claude/rules/10-engineering-laws.md
     - .claude/rules/lifecycle-sop.md
     - .claude/rules/anti-illusion-audit.md
     - .claude/rules/negative-results.md
     - CLAUDE.md
   ```

2. Or specify at startup:
   ```bash
   aider --read .claude/rules/10-engineering-laws.md \
         --read .claude/rules/lifecycle-sop.md \
         --read CLAUDE.md
   ```

### Notes
- Aider's `--read` files are read-only context and will not be modified
- Memory files need to be managed manually (Aider has no built-in memory system)
- It is recommended to add MEMORY.md to the read list
