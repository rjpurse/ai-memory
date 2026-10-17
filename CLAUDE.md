# Claude Code Boot

@AGENTS.md

This project uses the shared AI Memory Vault system defined in `AGENTS.md`.

## Claude-specific
- Place a copy of (or symlink) this file in the working directory where you launch Claude Code if it is not already the project root.
- Claude Code native memory (if used) should be redirected to the vault via the `templates/MEMORY.md` pointer.
- After any context compaction, re-read `VAULT-INDEX.md`.

Follow the startup sequence, checkpoint rule, and memory-on-demand behavior in `AGENTS.md`.