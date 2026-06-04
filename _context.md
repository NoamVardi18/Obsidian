## 2026-06-03 (session 2 — schema fix)

תוקן ה-frontmatter של כל הפתקים שיצרתי כך שיתאים לתבניות kepano וה-Bases יזהו אותם:
- `category` (יחיד) → `categories` (רשימה) — זה מה שכל ה-Bases מתשאלים
- פתקי **Evergreen** → `tags: [0🌲]` (זה התנאי היחיד ב-Evergreen.base), הוסר category
- **Books** (7 Habits, Deep Work, Can't Hurt Me, Power of Habit) → `author`/`genre`/`year`/`rating`/`tags: read`
- **Trips** (אירופה, ארה"ב) → `start`/`end`/`loc`
- **Projects** → `type`/`status`/`year`
- **Authors** (Goggins, Covey, Newport, Duhigg) → `categories: [[People]]` + `type: [[Authors]]`
- נוצר stub `References/Charles Duhigg.md`
- נמחק artifact `inbox.md_`

עכשיו כל פתק מופיע ב-Base המתאים: Books, Projects, Trips, People, Evergreen.

---

## 2026-06-03

### Created

**Notes/**
- `נועם — פרופיל פיטנס.md` — גיל, מדדים, פיצול A/B/C, ריצה, תזונה, HRV
- `טיול אירופה נובמבר 2024.md` — אופציה 1 (יוון+אלבניה+מקדוניה) vs אופציה 2 (יוון עומק)
- `ערך עצמי מוכח בהתנהגות, לא נדרש מבחוץ.md` — evergreen: ערך עצמי דרך עשייה, לא הצהרה
- `דחיית סיפוקים באימון ובכסף היא אותה מיומנות.md` — evergreen: אימון וכסף = אותה לוגיקה
- `ה-Stack שלי — כלים וטכנולוגיה.md` — AI stack + dev stack + תשלומים + וידאו
- `MSTR — הפסד לא ממומש ואסטרטגיית tax loss harvesting.md` — tax loss harvesting
- `קיזוז הפסדי מס בישראל — אין כלל wash sale על קריפטו.md` — evergreen: מיסוי קריפטו ישראל
- `הפסד מועבר בישראל דורש הגשת טופס 1301 כל שנה ללא הפסקה.md` — evergreen
- `מבנה הפרומפט המושלם.md` — AIM Framework + 7 שלבים + טבלת פרומפטים
- `שיטת הלמידה שלי.md` — פייפליין: שמע → קול → קלוד → NotebookLM → ריצה → חידון
- `מטרות ותוכניות אחרי הצבא.md` — 3 מסלולי הכנסה, חזון בגיל 25/35, יעד $200k
- `פרויקט לקוח חנות פרחים.md` — עץ היביסקוס + אתר + Google Business, $350 + $45/חודש
- `טיול ארה"ב 2026–2027.md` — NYC+DC, דצמבר 2026–ינואר 2027, 3 תקציבים
- `פרויקט יוצר תוכן.md` — אתגר 6 וידאו, מבנה: הוק → סיפור → משפט
- `השקעות לאבא — 3 מסלולים עם 60,000 ₪.md` — סימולציית 3 מסלולים על החזר מס
- `לולאות פתוחות.md` — כל המשימות הפתוחות: עסקי, למידה, כספי, אישי
- `ריצה — רוטציה ויעדים.md` — stub: יעדי ריצה

**References/**
- `7 Habits of Highly Effective People.md` — קובי, עברית, 7 הרגלים עם דוגמאות אישיות
- `Deep Work.md` — ניופורט, עברית, מערכת ריתמית + כללים אישיים
- `רשות המסים — גילוי מרצון קריפטו.md` — הליך גילוי מרצון
- `David Goggins.md` — stub
- `Can't Hurt Me.md` — stub + קישורים
- `Stephen Covey.md` — stub
- `Cal Newport.md` — stub
- `The Power of Habit.md` — stub

**Root/**
- `CLAUDE.md` — חוקי המאורגן: פייפליין, מבנה תיקיות, קישורים, פרוטוקול ביצוע
- `_inbox.md` — קלט עתידי
- `_context.md` — זה הקובץ

### Edited

- `Templates/Daily Note Template.md` — נוסף `created: <% tp.date.now("YYYY-MM-DD") %>`
- כל 31 תבניות בלי `created` — נוסף bulk
- כל 28 תבניות עם `{{date}}` — הומר ל-Templater syntax

### Deleted (raw source files, content extracted)

- `noam vault extract.md`, `noam conversation extract.md`
- כל הקבצים עם prefix Unicode (נועם-פרופיל-פיטנס, טיול-אירופה, תובנות משיחה, כל קבצי המס)
- `7 Habits of Highly Effective People.md`, `Deep Work.md`, `MSTR...md` (root originals)

### Key links added

- `ערך עצמי` ↔ `דחיית סיפוקים` ↔ `נועם — פרופיל פיטנס` ↔ `Deep Work`
- `מבנה הפרומפט המושלם` ↔ `שיטת הלמידה שלי` ↔ `ה-Stack`
- `מטרות ותוכניות` ↔ `פרויקט לקוח` ↔ `טיול ארה"ב` ↔ `פרויקט יוצר תוכן`
- `MSTR` ↔ `קיזוז הפסדי מס` ↔ `השקעות לאבא`
- כל ספרים → מחברים שלהם: `7 Habits` → `Stephen Covey`, `Deep Work` → `Cal Newport`, `Can't Hurt Me` → `David Goggins`
