# Home
Welcome to the Adventure Log! This is a record of the travels of [[rulkorf-alpensinger|Rulkorf Alpensinger]], [[kleb-fumpton|Kleb Fumpton]], and [[rowan-chokrotsk|Rowan Chokrotsk]] in the Forgotten Realms.

---
# Open Quests
```dataview
TASK FROM ""
WHERE !completed
GROUP BY "" as "Open Quests"
```
---
# Recent Events
```dataview
TABLE WITHOUT ID	
	("[[" + file.name + "|" + title + "]]") AS Name,
	dur(date(today) - file.cday) AS Age
FROM #new_adventure AND !"templates"
LIMIT 3
SORT file.cday DESC
```
---
# Quote Board
- *Nothing here yet...*
---
# Historical Archive
```dataview
TABLE WITHOUT ID
	arc AS "Story Arc",
	link(rows.file.name, rows.title) AS Name,
	date(rows.published) AS Date
FROM "sessions"
SORT file.cday ASC
GROUP BY story_arc AS arc
SORT arc DESC
```
---