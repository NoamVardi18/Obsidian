---
tags:
---
## Notes

![[Daily.base]]# Obsidian Vault

A personal knowledge base for iPhone, built on [Steph Ango's kepano-obsidian vault](https://github.com/kepano/kepano-obsidian) and synced via Git — no PC required.

---

## Guides

| Guide | What it covers |
|-------|---------------|
| [SETUP-PHONE.md](SETUP-PHONE.md) | How to clone this vault onto your iPhone using only Obsidian + Obsidian Git (no PC, no extra apps). Covers GitHub token creation, plugin setup, auto-sync, and merge conflict resolution. |
| [HOW-TO-USE.md](HOW-TO-USE.md) | Beginner guide to the "File Over App" philosophy: folder layout, organizing with properties, Bases (live tables), note types, and the daily → evergreen → monthly rhythm. Includes a 5-minute Templater setup so auto-dates work. |

---

## What's in This Vault

This vault is a faithful copy of [kepano/kepano-obsidian](https://github.com/kepano/kepano-obsidian), with one fix applied:

- **Auto-date fix:** All `{{date}}` placeholders in the Templates folder have been converted to `<% tp.date.now("YYYY-MM-DD") %>` (Templater syntax), so dates fill in automatically when you create a note — no manual entry needed.

### Folder layout

```
Attachments/   ← embedded images and files
Categories/    ← index pages (Books, Movies, People, etc.)
Clippings/     ← saved articles and web clippings
Daily/         ← daily notes
Notes/         ← evergreen notes, meetings, projects
References/    ← notes about specific things (books, films, people, places)
Templates/     ← 52 note templates + 30 Bases (live table views)
.obsidian/     ← Obsidian app settings
```

---

## Credits

- **Vault design:** [kepano/kepano-obsidian](https://github.com/kepano/kepano-obsidian) by [Steph Ango](https://stephango.com) — MIT License
- **iPhone sync method:** Based on the [Obsidian Git](https://github.com/Vinzent03/obsidian-git) community plugin by Vinzent03, inspired by the [proflead/obsidian-sync](https://github.com/proflead/obsidian-sync) approach

---

## License

The vault contents (templates, example notes, configuration) are licensed under the [MIT License](LICENSE) from the original kepano-obsidian project. The guides (SETUP-PHONE.md, HOW-TO-USE.md) and README are in the public domain — do whatever you like with them.
