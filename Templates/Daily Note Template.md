---
tags:
  - daily
created: <% tp.date.now("YYYY-MM-DD") %>
---
<%*
const week = tp.date.now("gggg-[W]ww");
const month = tp.date.now("YYYY-MM");
const isSunday = tp.date.now("d") === "0";

// Weekly note — create if it doesn't exist yet
if (!(await tp.file.exists(`Daily/${week}.md`))) {
  const wt = tp.file.find_tfile("Weekly Note Template");
  if (wt) await tp.file.create_new(wt, week, false, "Daily");
}

// Monthly note — only once a week (Sunday), create if missing
if (isSunday && !(await tp.file.exists(`Daily/${month}.md`))) {
  const mt = tp.file.find_tfile("Monthly Note Template");
  if (mt) await tp.file.create_new(mt, month, false, "Daily");
}

let nav = `> [!info]+ ניווט\n> 📅 [[${week}|השבוע]]`;
if (isSunday) nav += ` · 🗓️ [[${month}|החודש]]`;
nav += ` · 😴 [[מעקב שינה]] · ⚖️ [[מעקב משקל]]`;
tR += nav;
%>

## Notes

![[Daily.base]]
