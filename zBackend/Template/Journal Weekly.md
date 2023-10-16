# <%moment(tp.file.title).startOf('isoWeek').format("MMM DD") %> - <%moment(tp.file.title).endOf('isoWeek').format("MMM DD") %>


[[Heart Beat/Second Cycle/Phase5 - Labours/Weekly/<%moment(tp.file.title).subtract(1,'week').format("gggg-[W]ww")%>| ↶  Previous Week]] | [[Heart Beat/Second Cycle/Phase5 - Labours/Weekly/<%moment(tp.file.title).add(1,'week').format("gggg-[W]ww")%>| ↷  Next Week]]
`= date(2023-11-05) - date(today)`
`= date(today) - date(2004-10-05)`

![[‎ Cycles Of The Day#Database - Cycle Of Day]]




# Quests
1. 



# Schedule


# Overview

```dataview
table without id
	file.link AS "Day",
	Title,
	Work AS "📝",
	Places AS "🧳",
	Creatures AS "🦍",
	Breakfast AS "🍳",
	Lunch AS "🍛",
	Dinner AS "🍖",
	Snack AS "🍕",
	Fruit AS "🍇",
	Exercise AS "💪",
	Reading AS "👓",
	Entertainment AS "📺",
	Encylcopedia AS "📚"
from "Journal/Second Cycle"
where week = "<% moment(tp.file.title).format("gggg-[W]ww") %>"
sort file.name ASC
```

# Reminders
- [ ]  VOICE Notes Record IN BULK - instead of using sticky notes 
- [ ] 