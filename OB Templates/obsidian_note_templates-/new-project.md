<%_
tR += "---"
// create a title for the project
let title = tp.file.title
if(title.startsWith("Untitled")) {
title = await tp.system.prompt("Project Title");
}
await tp.file.rename(title)
let type = "Project"
let display_title = "Project - "
display_title += title
// set the tags
let tags = "#Project"
let project_tag = await tp.system.prompt("Project Tag")
tags += " "
tags += project_tag
// set date variables
let dt = tp.date.now("YYYY-MM-DD")
let df = tp.date.now("DD MMM YYYY")
let project_status = "open"
%>
<%_ tR %>title: "<% display_title %>"
type: "<% type %>"
tags: "<% tags %>"
date-created: "<% dt %>"
project-status: "<% project_status %>"

---

# <% title %>
