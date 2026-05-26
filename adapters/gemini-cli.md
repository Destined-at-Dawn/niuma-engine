# Gemini CLI Adapter

## Integration Method

Gemini CLI uses `GEMINI.md` or context files in the project root directory.

### Quick Integration

1. Create `GEMINI.md` in the project root directory (if it does not exist)
2. Reference niuma-engine rules in `GEMINI.md`:
   ```markdown
   > Engineering framework: This project uses niuma-engine.
   > Rule files are in the .claude/rules/ directory.
   > See CLAUDE.md for detailed guidelines.
   ```

3. Gemini CLI automatically discovers `.md` files in the project root directory as context.

### Notes
- Gemini CLI's context discovery mechanism is relatively loose
- It is recommended to inline the most critical rules in `GEMINI.md`
- Memory file paths remain unchanged
