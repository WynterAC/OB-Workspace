---
type: daily
description: A basic structure for a daily note that evolves over the day
---
%%
Status:: #in-progress
%%

---
**Tags**:: #daily-note
**Links**:: <!-- Add any additional links here -->

---
<% tp.user.generate_periodic_link_markdown(tp, "D") %>

![[../../../../Resources Vaults/obsidian-garden copy/Snippets/Good Day]]

# Today's Plan
<!-- What is the plan for today? Is there anything left over from yesterday? -->

# What Did I Learn Today?
<!-- Put any new ideas or topics to found out today, can any of them be new links? -->

# New Items Created

```dataview
table file.ctime as "Planted at",
file.mtime as "Last tended to",
length(file.inlinks) as "In Links", 
length(file.outlinks) as "Out Links"
where date(file.cday) <= (date(this.file.cday) + dur(1 day))
and date(file.cday) >= date(this.file.cday)
and this.file.name != "🗓 Daily Note"
```
---

<!-- Put links to new items created here -->

# Questions Raised
<!-- Did you have any unanswered questions from today?  Do you have anything you need to follow up? -->

# Other Notes
<!-- Put other notes here, like the weather for the day, any thoughts you had, other quick notes to expand on -->

#💡
🔗:  [[Notes]]

# Daily Note


 📅 [[2021-W22]]  current week
 
## Work Log:
---
### Tasks
#### ToDo 
 - [ ] open to do 
#### Working on 
- [ ]  working on
#### Done 
- [x] finished task
---

## Meeting Notes
---
#### Daily


--- 
## Notes





##### a word on tasks
Obsidian as a feature to search for tasks, open or done, see in  [[../../../00 Inbox/001 ✔️ToDo]].
I don´t want the moved tasks to show up there, but for journaling / logging reasons I still want to see what was done / on the ToDo list that day. So unfinished tasks don´t get deleted from the daily notes, they get moved to the next day and marked with an M so the search for open tasks don´t shows them in all the old notes multiple times.

- [ ] Open Task
- [x]  Done Tasks
- [M]  Task moved to next day
- [C]  canceled task