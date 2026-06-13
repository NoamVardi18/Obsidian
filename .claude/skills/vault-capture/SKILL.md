---
name: vault-capture
description: Take a raw thought, voice transcript, draft, or list Noam pastes in and turn it into properly organized note(s) in his Obsidian vault — classify the pipeline stage (fleeting/literature/evergreen), create or update notes with correct frontmatter and links, then commit and push. Use whenever Noam shares a thought, idea, transcript, or draft to save to Obsidian.
---

# Capture into Obsidian vault

1. **Find the vault.** If the current directory's `CLAUDE.md` starts with "Obsidian Vault — Claude Organizer", you're already there. Otherwise check `~/Obsidian` (default clone location). If neither works, ask Noam for the path.

2. **Read `CLAUDE.md` and `_context.md`** in the vault root first — they define folders, frontmatter schemas, naming rules, and the note pipeline (Fleeting → Literature → Evergreen).

3. **Read the input fully**, then decide:
   - How many distinct ideas/notes does this become?
   - What pipeline stage is each at — fleeting bullet in today's `Daily/`, literature response in `References/`, or mature evergreen in `Notes/`?
   - Does a note on this subject already exist? Search by likely filename/keywords before creating anything new.

4. **Create or update notes**, following `CLAUDE.md` exactly:
   - Correct folder and frontmatter schema for the type (evergreen = `tags: [0🌲]`, no `categories`; books/people/projects/etc. per their own schema)
   - Evergreen titles = complete-sentence claims, not topics
   - Add 1-3 `[[links]]` to related existing notes; create stub notes for any new person/concept mentioned
   - If appending to an existing note, use the `## Added YYYY-MM-DD` pattern

5. **Update `_context.md`** with a new dated entry (Created / Edited / Key links added).

6. **Commit and push:**
   ```bash
   git add -A
   git commit -m "<short description>"
   git push
   ```
   If push fails with "no upstream branch", run `git push -u origin <current-branch>`.

7. **Confirm back to Noam** — short, per `CLAUDE.md`'s confirmation format. If something is genuinely ambiguous, ask ONE focused question before acting, per the execution protocol.
