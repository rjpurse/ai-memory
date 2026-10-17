# Copilot Instructions — AI Memory Vault

The shared agent rules and memory system live in the repository root `AGENTS.md` and in the local vault.

## Required at session start
1. Read the vault index at the path listed in `AGENTS.md` (`VAULT-INDEX.md`).
2. Check the most recent daily note.
3. Follow the checkpoint and memory-on-demand rules from `AGENTS.md`.

Vault path (copy from AGENTS.md): `[FILL IN: full path to your vault]`

Do not load the entire vault into context. Load only the notes relevant to the current task.

When the user indicates they are finished, offer to update today's daily note.

For full rules, standing identity, and detailed startup sequence, consult `AGENTS.md` and the vault files.