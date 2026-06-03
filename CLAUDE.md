# Obsidian Vault — Rules for Claude

This file defines how this vault is structured and how Claude should handle any content the user brings.

---

## Folder Rules

| Folder | What goes here |
|--------|---------------|
| `Notes/` | The user's own thoughts, ideas, evergreen notes, meeting notes, projects |
| `References/` | Notes about specific external things: people, books, movies, places, podcasts, games — and the user's writing *in response to* something someone else wrote |
| `Clippings/` | Saved content from outside: articles, quotes, web pages |
| `Daily/` | One note per day, named `YYYY-MM-DD.md` |
| `Attachments/` | Images and embedded files only |
| `Categories/` | Index pages — do not create or edit files here |
| `Templates/` | Templates only — do not create or edit files here |

---

## File Naming

- **Descriptive name** — always clear, no abbreviations
- **Evergreen notes** (`Notes/`): title is a complete sentence or clear claim that describes the idea, e.g. `Writing every day sharpens thinking.md`
- **References** (`References/`): name of the subject, e.g. `Yuval Noah Harari.md`, `Inception.md`, `Sapiens.md`
- **Daily** (`Daily/`): always `YYYY-MM-DD.md`
- **Meetings** (`Notes/`): `YYYY-MM-DD Meeting with [Name].md`

---

## Properties (Frontmatter)

Every new note gets these properties. Use only what's relevant — don't add empty fields.

```yaml
---
created: YYYY-MM-DD        # always include
category: "[[Books]]"      # link to the matching category page
rating: 6                  # 1–7, only for rateable things (books, movies, etc.)
people:
  - "[[Person Name]]"      # anyone mentioned or relevant
topics:
  - "[[Topic]]"            # key concepts as wiki-links
---
```

**Available category links:** `[[Books]]`, `[[Movies]]`, `[[Shows]]`, `[[Albums]]`, `[[Podcasts]]`, `[[Podcast episodes]]`, `[[Games]]`, `[[Board games]]`, `[[People]]`, `[[Places]]`, `[[Companies]]`, `[[Products]]`, `[[Recipes]]`, `[[Posts]]`, `[[Projects]]`, `[[Events]]`, `[[Trips]]`, `[[Meetings]]`, `[[Journal]]`, `[[Clippings]]`, `[[Evergreen]]`

---

## Adding to an Existing File

If a note about the same subject already exists, **add to it** rather than creating a new file. Mark the addition with a date header:

```markdown
## Added 2024-03-15

[new content here]
```

---

## Decision Rules

- **Confident about folder and filename** → create/edit the file and tell the user where it went
- **Not sure which folder or file** → ask the user before doing anything
- **Same subject, existing file** → add to the existing file with a date marker
- **Ambiguous note type** (could be Notes or References) → if it's primarily the user's own thinking, put it in `Notes/`; if it's primarily about an external thing, put it in `References/`

---

## Note Types Quick Reference

| Type | Folder | Template to use |
|------|--------|----------------|
| Daily note | `Daily/` | Daily Note Template |
| Evergreen idea | `Notes/` | Evergreen Template |
| Meeting | `Notes/` | Meeting Template |
| Project | `Notes/` | Project Template |
| Person | `References/` | People Template |
| Book | `References/` | Book Template |
| Movie | `References/` | Movie Template |
| Recipe | `References/` | Recipe Template |
| Place | `References/` | Place Template |
| Article/quote saved | `Clippings/` | Clipping Template |
| Podcast episode | `References/` | Podcast Episode Template |

---

## How Claude Should Behave as Organizer

The user brings content in any form — free text, ideas, summaries, links, voice note transcripts, anything. Claude's job:

1. Understand what the content is about
2. Decide the right folder, filename, and template
3. If confident → create or edit the file directly and confirm where it went
4. If unsure → ask one focused question, then act
5. Always include correct frontmatter properties
6. If adding to an existing note → append with a `## Added YYYY-MM-DD` section
7. After creating/editing → commit and push to GitHub so it syncs to the phone automatically
