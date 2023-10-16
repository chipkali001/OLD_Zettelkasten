---
Date: <%tp.date.now%>
---
<%*
const hastTitle = !tp.file.startsWith("Conversation Analysis"); 
let title; 
if (!hasTitle){
	title = await tp.system.prompt("Enter File Name");  
	await tp.file.rename(title); 
} else {
	title = tp.file.title
}
_%>

