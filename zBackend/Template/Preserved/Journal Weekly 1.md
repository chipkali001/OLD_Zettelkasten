# <%moment(tp.file.title).startOf('isoWeek').format("MMM DD") %> - <%moment(tp.file.title).endOf('isoWeek').format("MMM DD") %>


[[Journal/Phase5 - Labours/Weekly/<%moment(tp.file.title).subtract(1,'week').format("gggg-[W]ww")%>| ↶  Previous Week]] | [[Journal/Phase5 - Labours/Weekly/<%moment(tp.file.title).add(1,'week').format("gggg-[W]ww")%>| ↷  Next Week]]


# Days

- [[Journal/Phase5 - Labours/Daily/<%moment(tp.file.title).startOf('isoWeek').add(0,'day').format("DD MMMM YYYY")%>|Monday]]
- [[Journal/Phase5 - Labours/Daily/<%moment(tp.file.title).startOf('isoWeek').add(1,'day').format("DD MMMM YYYY")%>|Tuesday]]
- [[Journal/Phase5 - Labours/Daily/<%moment(tp.file.title).startOf('isoWeek').add(2,'day').format("DD MMMM YYYY")%>|Wednesday]]
- [[Journal/Phase5 - Labours/Daily/<%moment(tp.file.title).startOf('isoWeek').add(3,'day').format("DD MMMM YYYY")%>|Thursday]]
- [[Journal/Phase5 - Labours/Daily/<%moment(tp.file.title).startOf('isoWeek').add(4,'day').format("DD MMMM YYYY")%>|Friday]]
- [[Journal/Phase5 - Labours/Daily/<%moment(tp.file.title).startOf('isoWeek').add(5,'day').format("DD MMMM YYYY")%>|Saturday]]
- [[Journal/Phase5 - Labours/Daily/<%moment(tp.file.title).startOf('isoWeek').add(6,'day').format("DD MMMM YYYY")%>|Sunday]]

# Reminders
- [ ]  VOICE Notes Record IN BULK - instead of using sticky notes 
- [ ]  ()
- [ ]  ()
- [ ]  ()
- [ ]  ()
- [ ]  ()
- [ ]  ()
- [ ]  ()
- [ ]  ()

# Quests
1. 

![[‎ Cycles Of The Day#Database - Cycle Of Day]]

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

