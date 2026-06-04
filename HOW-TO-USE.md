# How to Use This Vault (Beginner Guide)

This vault is built around Steph Ango's "File Over App" philosophy. Here's everything you need to understand it and start using it well.

---

## Do This First: 5-Minute Setup That Makes Auto-Dates Work

> **Why:** The templates in this vault use Templater syntax (`<% tp.date.now("YYYY-MM-DD") %>`). Without this plugin, dates won't fill in automatically when you create a note.

> **Important:** Plugins are not synced through Git — only note files are. You must install this plugin manually on each device.

### Install Templater

1. Open Obsidian → **Settings → Community plugins → Browse**.
2. Search for **Templater** → install and enable it.
3. In Templater's settings, set **Template folder location** to: `Templates`
4. Turn on **Trigger Templater on new file creation** — this is the key toggle. It makes Templater run automatically whenever you create a new note, filling in the date without any extra steps.
5. Close Settings.

That's it. Now any note you create using a template will have the correct date filled in automatically.

---

## The Philosophy: Files Over App

The central idea is that **your notes are plain text files** (Markdown) that live on your device and in your Git repo. They don't live inside a proprietary database that you can't open without a specific app.

- Notes are `.md` files you can open in any text editor, now or in 20 years.
- The app (Obsidian) is a lens on your files, not a prison for them.
- If Obsidian disappears tomorrow, all your notes are still there, readable.

This also means syncing via Git is natural — you're just syncing plain files.

---

## The Folder Layout

```
/
├── Attachments/     ← images and files embedded in notes
├── Categories/      ← index pages, one per note type (Books, Movies, etc.)
├── Clippings/       ← saved articles, quotes, web clippings
├── Daily/           ← one note per day
├── Notes/           ← evergreen notes, meeting notes, projects
├── References/      ← notes about specific things (books, films, people, places)
├── Templates/       ← templates for creating new notes
│   └── Bases/       ← live table views embedded in category pages
└── Templates/       ← all the template files
```

There are very few folders by design. The structure comes from **properties and links**, not from nested folders.

---

## Organizing with Properties Instead of Folders

Each note has a **properties block** (YAML frontmatter) at the top. This is where you put metadata:

```yaml
---
categories:
  - "[[Books]]"
author:
  - "[[Cormac McCarthy]]"
genre:
  - "[[Western]]"
year: 1985
rating: 6
topics:
  - "[[Violence]]"
  - "[[American Southwest]]"
created: 2024-03-15
tags:
  - read
---
```

### Key properties to know

| Property | What it does |
|----------|-------------|
| `created` | Date the note was created (filled automatically by Templater) |
| `categories` | Links this note to a category index (a **list**), e.g. `[[Books]]`. This is what the Bases filter on |
| `rating` | A number 1–7 (or 1–5, your choice) for things you want to rate |
| `author` | Links to the author/person note, e.g. `[[Cormac McCarthy]]` |
| `topics` | Links to concept notes, tags as wiki-links |

> ⚠️ The field is `categories` (plural, a list) — **not** `category`. The Bases query `categories`, so a note with the wrong field name won't show up in any table.

Using `[[wiki-links]]` in properties means Obsidian builds a graph of connections automatically. Click any linked name and you jump to that note.

---

## What Are Bases?

**Bases** are live tables embedded directly in your notes. They look like this inside a category page:

```
![[Books.base]]
```

When Obsidian renders this, it becomes a sortable, filterable table of all your book notes — their titles, ratings, authors, dates — without you doing anything. The `.base` files in `Templates/Bases/` define the columns and filters for each table.

Open `Categories/Books.md` to see an example: it embeds `![[Books.base]]`, which pulls in every note where `categories` contains `[[Books]]`.

---

## The Main Note Types

| Type | Template | What it's for |
|------|----------|---------------|
| **Daily note** | Daily Note Template | Log of the day, tasks, quick thoughts |
| **Evergreen note** | Evergreen Template | A single idea developed over time |
| **Monthly note** | Monthly Note Template | Reflection and review of the month |
| **Reference** | Book/Movie/etc. Template | Facts about a specific thing |
| **Meeting** | Meeting Template | Notes from a meeting |
| **Clipping** | Clipping Template | Saved article or quote |
| **Project** | Project Template | Notes for an ongoing project |

---

## The Daily → Evergreen → Monthly Rhythm

### Daily (every day)
- Create a daily note from **Daily Note Template**.
- Capture anything: tasks, ideas, links, what happened.
- Don't worry about structure — daily notes are raw input.

### Evergreen (when an idea matures)
- When a thought from your daily notes is worth keeping, create an **Evergreen note**.
- Name it as a complete sentence or clear concept: *"Writing daily sharpens thinking over time"*.
- Develop it over weeks and months by linking it to related notes.
- Evergreen notes are the long-term value of a personal knowledge base.

### Monthly (end of each month)
- Create a **Monthly note** from Monthly Note Template.
- Review: what did you read, watch, do? What ideas kept coming up?
- Link to the daily notes and evergreen notes from that month.
- This is your retrospective layer.

---

## Creating a New Note with a Template

1. Tap the **new note** icon (or Command Palette → "Create new note").
2. Open Command Palette → run **Templater: Open Insert Template Modal**.
3. Choose the template for your note type (e.g., Book Template).
4. Templater runs immediately, fills in the date, and sets up the properties block.
5. Fill in the properties and start writing.

> If you turned on **Trigger Templater on new file creation** in the 5-minute setup above, some templates apply automatically without the extra step.

---

## Tips for Getting Started

- **Don't over-organize.** Resist the urge to create new folders. Put everything in the right existing folder and let properties do the work.
- **Link liberally.** When you mention a person, book, or concept, make it a `[[link]]`. The graph emerges from links, not folders.
- **Rate things.** The `rating` property on a 1–7 scale makes Bases much more useful — you can sort your books or movies by how much you loved them.
- **Start with daily notes.** If you don't know where to start, just open today's daily note and write something. The rest of the system grows naturally.
