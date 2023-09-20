<%*
let qcFileName = await tp.system.prompt("Note Title")
titleName = qcFileName + " " + tp.date.now("YYYY-MM-DD")
await tp.file.rename(titleName)
await tp.file.move("/Snippets/" + titleName);
-%>
---
title: <% qcFileName %>
date: <% tp.file.creation_date("YYYY-MM-DD HH:mm:ss") %>
tags: #inbox
---
---


<% tp.system.clipboard() %>

