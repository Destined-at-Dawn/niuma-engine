# Security Policy

## Reporting Security Issues

If you discover a security issue, please report it via GitHub Issues.

## Security Design

niuma-engine's security mechanisms include:
- Script safety checks (preventing accidental deletion of system files)
- Dual-archive iron law (must back up before deletion)
- No blind overwriting (must read before modifying)
- Memory write confirmation (preventing unconfirmed writes)
