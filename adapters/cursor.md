# Cursor Adapter

## Integration Method

Cursor uses `.cursor/rules` or rule files in the project root directory.

### Quick Integration

1. Create symbolic links or copy rule files under the `.cursor/rules/` directory:
   ```bash
   # Symbolic links (recommended, stays in sync)
   ln -s ../.claude/rules/* .cursor/rules/

   # Or copy directly
   cp .claude/rules/* .cursor/rules/
   ```

2. Create a `niuma-engine.md` file under `.cursor/rules/` that references the root CLAUDE.md.

### Rule Loading

Cursor loads all `.md` files under the `.cursor/rules/` directory as project rules.

### Notes
- Cursor's rule loading mechanism differs from Claude Code
- If using symbolic links, changes to `.claude/rules/` will automatically sync
- Memory file paths remain unchanged
