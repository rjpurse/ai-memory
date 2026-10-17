# AI Memory

Simple, local, Markdown-based memory system for AI coding agents.

Adapted from [jaredrhod/ai-memory-vault](https://github.com/jaredrhod/ai-memory-vault) (CC BY-SA 4.0). Credit to Jared Rhodenizer.

## What this is

Turns an Obsidian vault (or any Markdown folder) into the AI's external working memory.

- No vector database
- No embeddings required
- Unlimited size (lives on disk)
- Prevents context-window blowup via **memory on demand** (load only the relevant slice)
- Human-readable and editable
- Works with any AI that can read/write files (best with Claude Code; usable with Grok Build, Copilot, etc. with manual pointing)

## Daily workflow (summary)

1. Start session → AI reads boot file (`CLAUDE.md` or equivalent) + `VAULT-INDEX.md`
2. Work → AI primes itself by reading only the notes needed for the task (Jobs, project indexes, recent daily notes)
3. Capture → Important decisions/facts written into the vault as you go (checkpoint rule)
4. Signal done → AI offers to update today's daily note
5. Next session continues from the vault

## Files

- `templates/CLAUDE.md` — Boot config (identity + rules + startup sequence). Place in your working directory (outside the vault).
- `templates/VAULT-INDEX.md` — Operating manual + profile. Lives inside the vault root.
- `templates/DAILY-NOTE.md` — Template for daily logs.
- `templates/MEMORY.md` — Pointer for Claude Code native memory (redirects it to the vault).

## Quick start

1. Create an Obsidian vault (or Markdown folder).
2. Copy the templates into place and fill the `[FILL IN: ...]` markers (or have an AI interview you).
3. Point your AI at the vault path.
4. Work. The vault is the memory.

## License

Adapted from jaredrhod/ai-memory-vault under Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0).
Credit original author. Share adaptations under the same license.
