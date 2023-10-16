table without id
	file.link AS "Day",
	breakfast AS "🍳",
	lunch AS "🥪",
	dinner AS "🍽",
	choice(sleep,"✔","❌") AS "😴",
	choice(gym, "✔", "❌") AS "🏋️‍♀️",
	choice(wellbeing, "✔", "❌") AS "👨‍⚕️",
	choice(study, "✔", "❌") AS "📚",
	choice(reading, "✔", "❌") AS "👓"
from "Journal/Phase5 - Labours/Daily"
where week = "<% moment(tp.file.title).format("gggg-[W]ww") %>"
sort file.name ASC

# List All Files
dataview
	LIST
or 
dataview
	TABLE
	
# YAML are CASE SENSITIVE
==breakfast & Breakfast different YAML ==

   dataview
TABLE breakfast, Breakfast, Lunch, Dinner

==You can also write it as==

   dataview
TABLE 
breakfast, 
Breakfast, 
Lunch, 
Dinner

# from “()” AND/OR “()” AND/OR ()

> [!Attention] You don’t want for obsidian to pull file from whole OBSIDIAN PORJHECT

   dataview
TABLE breakfast, Breakfast, Lunch, Dinner
==from "Journal/Phase5 - Labours/Daily"==

<center>---------------------------------------------------------------------------------------------------—</center> 

   dataview
TABLE breakfast, Breakfast, Lunch, Dinner
==from "Journal/Phase5 - Labours/Daily" AND #Conflict/War OR #Space-Time== 


# where (Conditon1) AND/OR (Condtion2) AND/OR (Condition3)
where file.name = "Journal Weekly" 
where file.name != "Journal Weekly" 
where file.size > 2000
where contains(item,“(Value)”)
where file.name != "Journal Weekly" AND contains(sleep, "8") OR contains(breakfast,"ruiche")
where week = "<% moment(tp.file.title).format("gggg-[W]ww") %>"

> [!Attention] 
> = Equals  
> != Not Equals

# ==SORT== in ==Asc==ending & ==Desc==ending ORDER of ==XYZ==
==ASC== & ==DESC==
1. ==<span style="background:#fff88f">sort file.size asc</span>==   Most useful cuz most PACKED files will have HIGHEST SIZE
2. ==<span style="background:#fff88f">sort file.size desc</span>==   Most useful cuz most PACKED files will have HIGHEST SIZE
3. sort DateExpected desc

# (ITEM) AS ()
breakfast AS "🍳",

# choice(ITEM,"(Choice1)","(Choice2)",(“Choice3”)) 

# choice(() ,"()","()") ==AS "()",==

# Table ==without Id== vs ==with Id==

```dataview
table without id
	breakfast AS "🍳",
	lunch AS "🥪",
	dinner AS "🍽",
	choice(sleep,"✔","❌") AS "😴",
	choice(gym, "✔", "❌") AS "🏋️‍♀️",
	choice(wellbeing, "✔", "❌") AS "👨‍⚕️",
	choice(study, "✔", "❌") AS "📚",
	choice(reading, "✔", "❌") AS "👓"
from "Journal/Phase5 - Labours/Daily"
```


```dataview
table 
	breakfast AS "🍳",
	lunch AS "🥪",
	dinner AS "🍽",
	choice(sleep,"✔","❌") AS "😴",
	choice(gym, "✔", "❌") AS "🏋️‍♀️",
	choice(wellbeing, "✔", "❌") AS "👨‍⚕️",
	choice(study, "✔", "❌") AS "📚",
	choice(reading, "✔", "❌") AS "👓"
from "Journal/Phase5 - Labours/Daily"
```

# file.link as XYZ
```dataview
table 
	file.link AS "XYZZ",
	breakfast AS "🍳",
	lunch AS "🥪",
	dinner AS "🍽",
	choice(sleep,"✔","❌") AS "😴",
	choice(gym, "✔", "❌") AS "🏋️‍♀️",
	choice(wellbeing, "✔", "❌") AS "👨‍⚕️",
	choice(study, "✔", "❌") AS "📚",
	choice(reading, "✔", "❌") AS "👓"
from "Journal/Phase5 - Labours/Daily"
```


# DON’T DO - Last Column shouldn’t end with comma will result in error
table without id
	file.link AS "Day",
	breakfast AS "🍳"
	lunch AS "🥪",
	dinner AS "🍽",
	choice(sleep,"✔","❌") AS "😴"==,==
from "Journal/Phase5 - Labours/Daily"


table without id
	file.link AS "Day",
	breakfast AS "🍳"
	lunch AS "🥪",
	dinner AS "🍽",
	choice(sleep,"✔","❌") AS "😴"
from "Journal/Phase5 - Labours/Daily"

