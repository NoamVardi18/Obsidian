---
name: organize-vault
description: Audit and reorganize Noam's Obsidian vault — fix frontmatter schema, file misplaced notes into the right folders, tighten titles, and add missing links/connections, following the vault's own CLAUDE.md rules. Use when Noam asks to organize, clean up, sort, or tidy his Obsidian notes/vault.
---

# Organize Obsidian vault

1. **Find the vault.** If the current directory's `CLAUDE.md` starts with "Obsidian Vault — Claude Organizer", you're already there. Otherwise check `~/Obsidian` (default clone location). If neither works, ask Noam for the path.

2. **Read `CLAUDE.md` and `_context.md`** in the vault root first — they define the folder structure, frontmatter schemas, naming rules, the note pipeline, and what was done in recent sessions. Follow them exactly.

3. **Scope the audit.** Default to files touched/added since the last `_context.md` entry, plus anything Noam points at. Don't re-scan the whole vault unless asked — keep it cheap.

4. **Fix, per `CLAUDE.md`:**
   - Frontmatter schema (`categories` plural list vs `tags`, wikilink fields, no empty fields, evergreen = `tags: [0🌲]` with no `categories`)
   - Misplaced files (root = inbox → move into `Notes/`, `References/`, `Daily/`, or `Clippings/`)
   - Vague evergreen titles → rewrite as complete-sentence claims
   - Missing `[[links]]` to related notes — add 1-3 per note, create stub notes for new people/concepts
   - Duplicate notes → merge into the better-schema version, then delete the weaker copy

5. **Touch as few files as possible.** Only edit what's actually wrong — don't reformat correct notes. For large batches, split work across parallel sub-agents on non-overlapping files to save context.

6. **Update `_context.md`** with a new dated entry (Created / Edited / Deleted / Key links added), matching the format already used in the file.

7. **Commit and push:**
   ```bash
   git add -A
   git commit -m "<short description of what was organized>"
   git push
   ```
   If push fails with "no upstream branch", run `git push -u origin <current-branch>`.

8. **Report back** — short and specific, per `CLAUDE.md`'s confirmation format (file → one-sentence summary). No fluff.
