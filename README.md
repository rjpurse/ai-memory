# AI Memory

Simple, local, Markdown-based memory system for AI coding agents.

Adapted from [jaredrhod/ai-memory-vault](https://github.com/jaredrhod/ai-memory-vault) (CC BY-SA 4.0). Credit to Jared Rhodenizer.

Works across **Claude Code**, **Grok Build**, and **GitHub Copilot** via a shared instruction file plus thin tool-specific bootstraps.

## What this is

Turns an Obsidian vault (or any Markdown folder) into the AI's external working memory.

- No vector database
- No embeddings required
- Unlimited size (lives on disk)
- Prevents context-window blowup via **memory on demand** (load only the relevant slice)
- Human-readable and editable

## Multi-tool bootstrap

| Tool | What it reads | File in this repo |
|------|---------------|-------------------|
| Claude Code | `CLAUDE.md` (or `AGENTS.md` if none) | `CLAUDE.md` (imports `@AGENTS.md`) |
| Grok Build | `AGENTS.md`, `CLAUDE.md`, `.grok/rules/` | `AGENTS.md` (read natively) |
| GitHub Copilot | `.github/copilot-instructions.md` (and AGENTS.md on some surfaces) | `.github/copilot-instructions.md` |

**Common source of truth:** `AGENTS.md`

Fill the vault path in `AGENTS.md` (and the Copilot file). Each tool then follows the same startup sequence, checkpoint rule, and memory-on-demand behavior.

## Daily workflow (summary)

1. Start session → AI reads the shared instructions + `VAULT-INDEX.md`
2. Work → AI primes itself by reading only the notes needed for the task
3. Capture → Important decisions/facts written into the vault as you go (checkpoint rule)
4. Signal done → AI offers to update today's daily note
5. Next session (any tool) continues from the vault

## Files

- `AGENTS.md` — Common instructions (startup, rules, vault path)
- `CLAUDE.md` — Thin Claude Code bootstrap that imports `AGENTS.md`
- `.github/copilot-instructions.md` — Thin Copilot bootstrap
- `templates/` — Vault templates (`VAULT-INDEX.md`, `DAILY-NOTE.md`, etc.)

## Quick start

1. Create an Obsidian vault (or Markdown folder).
2. Fill the vault path in `AGENTS.md` and `.github/copilot-instructions.md`.
3. Copy templates into the vault and fill the remaining `[FILL IN]` markers (or have an AI interview you).
4. Launch any of the three tools from a directory that can see these files (or copy/symlink the relevant bootstrap into the working directory).
5. Work. The vault is the shared memory.

## License

Adapted from jaredrhod/ai-memory-vault under Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0).
Credit original author. Share adaptations under the same license.
