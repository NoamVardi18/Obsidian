---
tags:
  - index
created: 2026-06-07
---
# 🏠 בית

## בוקר טוב ☀️

```button
name 📅 יומן היום
type command
action Daily notes: Open today's daily note
color blue
```

```button
name 🗓️ השבוע
type note(Daily, false)
action <% tp.date.now("gggg-[W]ww") %>
templater true
template Weekly Note Template
color green
```

```button
name 🌲 פתק חדש
type command
action Templater: Create new note from template
```

```button
name 🔄 משיכה (Pull)
type command
action Obsidian Git: Pull
```

## מעקב יומי
😴 [[מעקב שינה]] · ⚖️ [[מעקב משקל]] · 💪 [[פיטנס]]

## לולאות פתוחות

![[לולאות פתוחות]]

## פרויקטים
![[Projects.base]]

## רעיונות (Evergreen)
![[Evergreen.base]]

## ספרים
![[Books.base]]
