# Home
Welcome to the Adventure Log! This is a record of the travels of [[rulkorf-alpensinger|Rulkorf Alpensinger]], [[kleb-fumpton|Kleb Fumpton]], and [[rowan-chokrotsk|Rowan Chokrotsk]] in the Forgotten Realms.

The sections below utilize the Obsidian Dataview plugin to dynamically populate tables with information from the log. Unfortunately the results of the queries are visible only in Obsidian proper, not online. Check the sidebar for more information about particular people, places, items, and events!

Please see the GitHub repo for instructions on how to download ObsidianMD and view this repository locally!

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