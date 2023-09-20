# [[Article - Automating Obsidian Workflows with Templates]]
**Created:** [[2023-07-06]]


# Part 1 - Using Templates and Templater in Obsidian to Automate Your Workflows
Templates are powerful tools for automating workflow and helping you get more done with more ease in any application. They are especially powerful as a workflow support in Obsidian.

In this series of articles, we'll be looking at the two most commonly used Template tools - the Templates Core plugin and the Templater Community plugin and digging into a myriad of ways that you can use them - focusing most heavily on the Templater Community plugin. 

## What's the difference between Templates and Templater?
The Templates Core plugin in Obsidian will allow you to build templates and you can insert dates and times automatically into them, along with the note's title. The Templates Core plugin integrates well with the Daily Notes Core plug-in and the Unique Note Creator Core plugin. The Templates Core plugin allows you to keep your vault in Restricted Mode if that is important to you. I'm going to write about the Templates Core Plugin assuming that you are using it predominantly because you wish to leave your vault in Restricted Mode and not add any Community plugins. I recognize that might not be the case for you and if so, you can certainly make use of Templates with other Community Plugins.  

The Templater Community plugin is, [according to its creator](https://silentvoid13.github.io/Templater/introduction.html), "a template language that lets you insert **variables** and **functions** results into your notes. It will also let you execute JavaScript code manipulating those variables and functions." Templater is a Community plugin so it does require that you leave Obsidian's restricted mode to use it. That said, it includes many more features than the basic Templates Core plugin and it is, as I write this, the sixth most highly used Community plug-in with over 230,000 installs.

## Which should I use?
My advice is generally to start with the "lowest" level of any tool that you can and then work up from there as you get more comfortable. That said,  there are some pretty distinct functionality differences that would cause you to have to rework your templates if you switch so I actually recommend you start with Templater - but I will walk through how you can get the most out of the Templates Core plug-in before we get there.

## What should I create templates for?
I get a lot of value out of looking at other people's templates and so I will provide you with several examples of templates here - and in upcoming posts - for things you might want to include in your templates. That said, I think what you put in a template - and particularly how you arrange it in a template - is very much about who you are as a person and so I don't see much value in simply copying and pasting someone else's templates and using them for yourself. 

So, that means you have to create a lot of your own templates. By all means, do a quick google search and find links to starting points - but you will get more value if you customize these templates to the way you think. 

Here are several examples of templates you could create in Obsidian (or really in any Tool for Thought):

### Logs & Reviews
- Daily Note
- Weekly Note
- Weekly Review
- Monthly Note
- Monthly Review
- Quarterly Note
- Quarterly Review
- Yearly Note
- Yearly Review/Annual Planning

### Life Admin
- Recipe Template
- Weekly, Monthly, or Quarterly Financial Processes
- A list of monthly bills you pay (so you can check them off each month) - or this could go in your monthly note/review template
- Project Template
- Meeting Notes Templates (you can make one generic one or make specific ones for each meeting)

### Streamlining Writing Process
Any text that I might use over and over again, I'll create a template for.

- Affiliate links
- definitions I use all the time (e.g. I write all the time about learning projects and so I created my own definition for this and that is a template named def-Learning Project)
- Journaling and Writing Prompts - I have several templates that include lists of prompts. If I'm feeling uninspired, I'll just randomly select one and insert it into the file I'm working in to try to get me writing
- Templates for the things you want to include in any kind of content you publish: tweets, articles, videos, and these could differ by platform and content type on the platform (e.g. one for tweets and one for threads)

### Checklists
EVERY checklist you use makes for a good template. Here are a few of my favorites:
- Packing Lists
- Trip Planning Checklists
- Article Editing/Publishing Checklist
- Video Editing/Publishing Checklist

### Obsidian Focused Templates
- If you use Obsidian for Task Management, various Task Queries
- Any sort of inline query

### Personal Knowledge Management
- Book Notes Template
- Literature Note Template
- Atomic Note/Zettelkasten Template
- Reference Note Template

So, now that you've gotten a few ideas of templates that you might use - and again, I urge you to comment with any other templates you think of - let's dig in first to the Templates Core plugin.

## Series Overview
I wrote this series as a way to pull together my own knowledge about templates into a single place and to really refine my own core processes around template use. As an example, one of the things that has come out of this process is that I'm developing a new syntax for how I name templates and whether they are designed to be used in an existing file (they get the letter f at the front of their name) or they are designed to be used in a new file (they get the letter n in front of their name). While for some templates it really doesn't matter, for others it does and so this exercise of writing this and thinking in depth about Templates has allowed me to get really serious about making my templates as automated as possible for my specific use cases.

The article got SUPER long though so I decided I'd split it into parts. In the spirit of fairness, I'm releasing the entire series at one time - although I will hopefully come back through soon and update the series with some videos to enhance the content. Here is an overview of the series - you'll find this same list at the end of each article in the series so you can easily navigate your way through from any part.

- Part 1: Using Templates and Templater in Obsidian 
- Part 2: Maximizing the Templates Core Plugin
- Part 3: Getting Started with the Templater Community Plugin
- Part 4: Other Things You Can Automate Using Templater Commands and Functions and Other Resources for More Inspiration

# Part 2: Maximizing the Templates Core plugin
## Introduction
This is the second article in my series on automating your workflow with templates. Use these links to navigate through the series:
- Part 1: Using Templates and Templater in Obsidian 
- Part 2: Maximizing the Templates Core Plugin
- Part 3: Getting Started with the Templater Community Plugin
- Part 4: Other Things You Can Automate Using Templater Commands and Functions and Other Resources for More Inspiration


## Enable and Set Up to Use the Templates Core plugin
To get started with the Templates Core plugin you need to make sure it is enabled in your vault. 
1. Open your vault and go to settings.
![[obs-options.png]]
2. Select Core plugins on the left
![[obs-coreplug.png]]

3. Scroll down in the right hand portion of the Core plugins box until you see Templates. Make sure its toggle button is pushed to the right to indicate that it is on. 
![[obs-templatescoreplug.png]]
From here you can actually go ahead and also set your options for the Templates plug in. The one you must set is a folder for all of your Templates.

To do that from here, just click the cog button right by the toggle switch. If you want to access that page at any time, you can also do so by scrolling down on the left and locating Templates under the Core plugins section.

So, clicking this cog wheel
![[obs-templatesoptionscog.png]]

or scrolling down under Core plugins to Templates both give you the Templates option screen
![[obs-templatesoptionsmenu.png]]

4. Let's go ahead and say our templates will be in a top level folder called Templates (again, so creative, I know). Just type Templates in the Template folder location box and then close that window using the X just above where you typed Templates.
![[obs-templatesfolderlocate.png]]
5. And, finally, we need to create our Templates Folder. Click the New Folder button.
![[Obs - Automating Obsidian Workflows with Templates - New Folder.png]]
And then type Templates
![[obs-templatesfoldercreated.png]]

## Create Your First Template

We're going to use a Meeting Notes Template as our first template. You can watch how I did it, and then you can follow along step by step below.

[Watch the video]

1. In the templates folder, create a new note and name it Meeting Notes. You can do this by right clicking the templates folder and selecting New Note or by making sure the templates folder is selected in the file explorer and then pressing Ctrl+N on the keyboard.
![[obs-createnotetemplate.png]]

2. We're going to use a little piece of code to indicate that we want the title we give our note to be included as a header in the note. So, type # {{title}} on the first line and then press enter.
![[obs-meetingnotestemplatetitle.png]]
Now, when you run this template you'll enter a title and it will automatically get added to this spot in the template when you accept the title. Don't worry if that doesn't make sense - we'll walk through it again in a moment.

3. We're also going to add the date to the file. The date will be in the format of YYYY-MM-DD because that was the format we set in the Template options screen. If you include this little date script inside of a pair of double brackets you will automatically create a backlink between your daily notes for this day and the meeting notes you take.
![[obs-meetingnotestemplatetitledate.png]]

4. Now that we've got our tiny bit of scripting out of the way, you can add your remaining headers. I'm going to add # Agenda, three dashes to make a horizontal row, # Attendees, # Notes, and # Action Items as my main sections.
![[obs-meetingnotestemplatefinal.png]]
The image above shows the template in Source Mode. As you can see, I also added a single check box under action items so that is already there for me to start adding action items. This is what it looks like in Reading Mode (if you're not sure how to toggle between those modes, click the three dots on the top right side of any note and you'll see these toggles in that menu.)

![[obs-meetingnotespreview.png]]

 ## Using Your Meeting Notes Template
 Now that you've made your template, it's time to use it. Let's create a note for today's Team Meeting. I personally include the date in the note meeting title - how you name your notes is up to you.

1. Open a new note. Name your note Team Meeting Date (so mine will look like Team Meeting 2022-08-30).
2. Hit enter. This will save the note with that name and will put your cursor at the top of your note. 
3. To run your template, press Ctrl-P (to bring up the command palette) and then start typing Te for Template. Once you see "Templates: Insert template" is highlighted just press enter. For now, because you only have one template created, that template will run. 
![[Pasted image 20220830154010.png]]
4. You should now see your Template on the screen - already pre-filled for you.
![[obs-teammeetingnote.png]]

As an alternative to the Templates command in the command palette, you can also use the Templates button on the left to add a template to a page.
![[obs-inserttemplatebutton.png]]

## Using Templates Plugin to insert Time and Date
You can also use the Templates Plugin to insert the time and date into any note. We'll demonstrate this with time. 

To do this, place your cursor where you want the time inserted.

Using Ctrl+P again, bring up the command palette. Start typing te for Template. This time, select Template: Insert Time
![[obs-inserttime.png]]
As soon as you hit enter on that line, the current time will be inserted into your file where your cursor was.

![[obs-insertedtime.png]]

You can also set this up as a Hotkey to make it a little faster to apply. Let's walk through that process. 

1. Open up the Settings panel using the cog wheel.
![[obs-Settings-Cog.png]]

2. Select "Hotkeys" from the left hand menu. Scroll down to Templates or type tem in the Search box to locate templates.
![[obs-hotkeys-templates.png]]

3. Click the "Customize this command" button on Templates: Insert current time
![[obs-time-hotkey-button.png]]

4. Press the keyboard command of your choice using some combination of command, shift, and alt as well as letters, numbers, and symbols. I used Ctrl+Shift+t for the Insert current time command. 
![[obs-time-hotkey-set.png]]


5. Once set, close the hotkey window and try it out. Place your cursor somewhere in a note that you want the time inserted and select Ctrl+Shift+t (or whatever key combination you chose) to insert the time. 

## Using Other Date Formats In Your Notes
There are many different types of notes that you could use a template for. Among these are the very commonly used daily, weekly, monthly, quarterly, and yearly notes. Lets use these common note types to look at other ways you can use date and time formatting within your templates to streamline note creation.

### Creating a Daily Notes Template and Setting up the Daily Notes Core Plugin

A Daily Note is used by many in the Tools for Thought page as their daily log file to record all of their thoughts, tasks, and information for that day. We're going to start by creating a simple template that uses a few of the alternative date formats for our daily note.

1. To begin, create a new file in the Templates folder called Daily Template
2. In this file, enter all the text you want your daily note to start with each day. Here is a walk through of what I included:
	I wanted each note's top header to read Day of Week, Month, Day Year Daily Note so I used the {{date}} script and customized the output for the script so it wouldn't return the standard YYYY-DD-MM format and instead generated my custom format.
	On the next line, I wanted the text Day Number in bold and then I wanted the year's day number.
	Then, to conclude the date section, I added the Week number, again using a custom format for the date.
	Note: in the image shown, I needed top put another line of space between the week number and the three dashes for the horizontal rule - that's why week number looks so much larger than everything else. I didn't see it when I took the screen shot.
	I then added the four sections I want to have in every daily note, each as level 1 headers. 
![[obs-dailytemplate.png]]

Now, to give it a full test drive, let's set up the Daily Notes Core Plugin.

This will let us see how the Daily Notes template can be called by another plugin and automatically filed where we want it.

1. Open Settings
![[obs-Settings-Cog.png]]

2. Make sure the Daily Notes Core Plugin is enabled from the Core Plugins Screen.
![[obs-dailynoteson.png]]

3. Now, under the Core Plugins section, select Daily Notes so we can set its options. We need to first confirm the date format. I like the format of YYYY-MM-DD so I'm going to leave it as is. If you'd prefer a different format, you can click format reference on the window to see the key for how to format various date formats. I'll be showing you several examples of this in the screens that follow. Now, we're going to choose where all of our daily notes get stored. I like to keep all of my time based notes in a folder called Logs and then divide them into separate folders by note type. As you can see, I entered Logs/Daily Notes in the New file location box. We'll create this file location right after we finish the settings. And, then, select the location To your Daily note Template. Finally, I turned on the toggle so that when I start up Obsidian, my Daily Note will open on startup just because I prefer that option. 

![[obs-dailynoteoptions.png]]

4. Finally, let's go add the Logs folder and the Daily Notes folder inside of it.
![[obs-logs-dailynotes.png]]

5. You're now ready to test your first daily note. You can create the daily note using the Command Palette (Ctrl+P and then Da for Daily) or by clicking the Open Daily Note button on the menu bar.

![[obs-opendailynote.png]]

This is what my first daily note looks like. If you used my template, you should get something similar but with the correct dates filled in.
![[obs-dailynotereadmode.png]]

You're now ready to start using your daily note. 

You can do a lot of additional customization with the date and time scripts if you want to. Full documentation for that is located [on the moment page](https://momentjs.com/docs/#/displaying/). 

## One More Plugin with Templates
If you want to push the Templates Core Plugin to its limits without adding any Community plugins then you may also want to use the Note Composer Plugin.

Note: You might also want to use the Unique Note Creator Plugin which  lets you create a template for Zettelkasten style notes. That said, I personally can't make sense of a Zettelkasten file structure based on date codes so with the information you already have you'll be able to use this plugin and I hope some day you'll help me see how a Zettelkasten based on date and time codes can make sense to someone.

The Note Composer Plugin allows you to specify a few additional pieces of data in your template using your script. Let's create that template first and then we'll give the Note Composer Core plugin a run for its money.

1. Create a new note in your template folder. Call it Extracted Note.
2. In your Extracted Note, you can use commands like {{fromTitle}} {{newTitle}} {{content}} and, of course, date and time. This is the simple template I set up for an Extracted Note
![[obs-extractednotetemplate.png]]
Notes that I used double brackets outside of the double curly braces for fromTitle and date in order to create automated links back to the original file and to the daily note.

Now, you need to turn on the Note Composer plug in and set its template location. Again, this is just as we've done before so this time I'll just show you what the options screen for Note Composer looks like when you're done.

![[obs-notecomposersettings.png]]

Now, to use this new functionality, you need two files. 

The first is the file that has all the text. I used a short extract of the text of this article and created that note. 
![[obs-beforeextract.png]]

Then, you need to create a new note that uses the Extracted Note template. I named that file Zettlekasten Plugin.

Now that you have both of those files created, you can go back to the One More Plugin File and select the text in that middle paragraph, then right click the text, and select Extract current selection....
![[obs-rightclicktoextract.png]]
A file window will open and ask you what file you want to put this text into. Choose your Zettelkasten Plugin file.

Your One More Plugin file will now have a link to Zettelkasten Plugin where that text was and your Zettelkasten Plugin file will include the link to the original file, the date formatted as a link, and the extracted text.

These two images show what that looks like in its final form.
![[obs-onemorepluginwithlink.png]]

![[obs-zettlekastenplugin.png]]

You can create a sea of additional templates with the Templates plugin, but I think time is better spent learning more about the Templater plugin and really focusing on ways we can automate routine tasks with our notes.

## Conclusion & Navigating The Article Series
This is the second article in my series on automating your workflow with templates. Use these links to navigate through the series:
- Part 1: Using Templates and Templater in Obsidian 
- Part 2: Maximizing the Templates Core Plugin
- Part 3: Getting Started with the Templater Community Plugin
- Part 4: Other Things You Can Automate Using Templater Commands and Functions and Other Resources for More Inspiration

# Part 3: Getting Started with the The Templater Community Plugin

## Introduction
This is the third article in my series on automating your workflow with templates. Use these links to navigate through the series:
- Part 1: Using Templates and Templater in Obsidian 
- Part 2: Maximizing the Templates Core Plugin
- Part 3: Getting Started with the Templater Community Plugin
- Part 4: Other Things You Can Automate Using Templater Commands and Functions and Other Resources for More Inspiration


To begin using the Templater Community Plugin, you must leave Restricted Mode in your vault.

To do this, go to Settings > Community Plugins > and click "Turn on Community Plugins"

Now, it's time to install the Templater Plugin. On the Community Plugins screen, click Browse and search for Templater.
![[obs-installtemplater.png]]

![[obs-enabletemplater.png]]
![[obs-templateroptions.png]]

On the options screen, if you take a moment to scroll through it you can see there is a LOT more we can do here. We won't cover all of it, but we'll get some of the most important things covered. 

Go ahead and set your location for your templates. I would actually go ahead and set it to the Templates folder you already have set up, even if you have a LOT of other templates already created. It's easier to just edit all of these files as you need them to use all the new features we get with templater. 

**Note:** If you decide to read on with the Templater instructions, you will, at some point soon, want to disable The Templates and Daily Notes Core Plugins so that you can use only Templater and likely the Periodic Notes Community Plugins. I won't provide instructions for that specifically but simply remind you that you will need to make sure you do that. 

## The Meeting Notes Template
Let's go ahead and open up our meeting notes template and see some of the new things that we can do with it now that we're using Templater. 

This is what our Meeting Notes Template looked like when we last saw it:
![[obs-meetingnotespreview.png]]

We're going to change the name of this template to Team Meeting Template. We're doing this because we're going to make the text of this meeting template much more specific to only our team meeting to allow us to automate these agendas in a flash.

Let's begin by changing the title and date at the top to use the format language called for by Templater.

## Templater's Language
To be very clear, I am not a coder. What I figure out, I learn through a lot of reading and trial and errors. So, if I mix up my Java Script and my something else, please feel free to correct me with kindness - I will be happy to learn from my mistake - just remember to be kind.

According to the [Templater website](https://silentvoid13.github.io/Templater/syntax.html), it uses the Eta templating syntax. 

Each command in Templater begins with a <% and ends with a %>
Inside of the command, you place the functions.

Functions begin with tp followed by a dot

Functions come from one of seven modules (for internal functions which is the bulk of what we'll cover here). You need to tell templater which module you're going to use. The modules are:
- config
- date
- file
- frontmatter
- obsidian
- system
- web

After the module, you put another dot.

And finally, you're ready for the function. Functions often contain some sort of argument which is included in either parenthesis or brackets. 

## We trade simplicity for functionality
So, while it was easy in the Templates Core Plugin to just say {{date}}, we have to use a little more complicated format to get the date in Templater. Don't worry, very soon I'm going to show you how beneficial that functionality can be. 

![[obs-TeamMeetingWithTemplaterFileandDate.png]]

We now have to get the file's title using the tp.file.title command. Notice that we've put it inside of double brackets again so that it will update as we update the name of the file. We did the same thing with the Date - putting it inside of double brackets. The date function also requires a set of empty parenthesis since there is an argument needed for that command.

Here's the really fun part though.

At the very end of our file, we're going to add a command that will move this file to the folder where we want it to ultimately end up. Don't worry - we're going to look at an alternative way to do this from within the Templater plugin, but I think knowing both methods has a lot of value. We do this using the file module and the move function. The move function needs an argument that essentially tells it where to put this file. While you don't have to, the documentation indicates putting an await command at the beginning of this command. [According to Stephen Millard](https://www.thoughtasylum.com/2021/07/10/automation-with-templater-for-obsidian/), this extra javascript command, while not necessary now, could keep things from "piling up" in computer processing as you add on more and more complexity.

I decided I wanted my files to be sorted by type under a generic "Meetings" folder so this meeting will go into my Team Meetings folder.

`<% await tp.file.move("/Meetings/Staff Meetings/" + "/" + tp.file.title) %>`

Before we do the big reveal, let's go back to this file and make it much more specific to our actual Team meetings by adding the regular attendees. I added check boxes in front of their names so that I could easily check who was there and who wasn't. I also added a set of standing agenda items and then finally, I added a task to distribute notes. 

![[obs-teammeetingtemplatefinal.png]]

Depending on how you organize your files, you could create a template for each primary folder location (e.g. if you have /Meetings/1-on-1/ and /Meetings/Executive Council/ these would be two different templates with two different move statements at the end of each.) In my sample vault that you can download (details below) you'll see a few different examples of meeting note templates being directed to different folders. In the vault, I'm doing it using the built in feature of the Templater Community Plugin so let's look at that next.

## Using Templater to Put Notes Where You Want Them

If you open up the Templater Community Plugin settings, you'll see an option to "Trigger Templater on new file creation". This option is turned off by default. Let's turn it on and see what happens. 

Anti-climactic - right! It looks like nothing happens. However, if you scroll down on the Templater options screen a little bit, you'll notice a new section labeled Folder Templates got added. Automation opportunities await!
![[obs-foldertemplatessectionadded.png]]

We already know that we want our team meeting template to automatically get put into our Team Meetings Folder so let's set the Team Meetings folder to be our folder in the left hand box and our Team Meetings template to be the template that fires in our right hand box.
![[obs-usingfoldertemplatestoinsertteammeetingtemplateinfolder.png]]

Now, just to make sure there is no funny business here, let's make sure that we've deleted that last line of code from our Team Meetings template - the line that looks like:
`<% await tp.file.move("/Meetings/Staff Meetings/" + "/" + tp.file.title) %>`

Now, let's test this out and see what happens.

We trigger the Folder Templates function by creating a new blank file in a folder that has a template tied to it. So, right click the Team Meetings folder and select New Note.
![[obs-rtclicknewnoteonteammeetingsfolder.png]]

A new meeting notes file will be created using your template - just give it a name and you're ready to go.

So, which is the best way to go? That's entirely up to you. 

I personally prefer the method of putting the code snippet into the file for two reasons:
1) This can be entirely fired via keyboard (I'll even show you how to bind a template to a keyboard shortcut in a moment)
2) If I ever reorganize my folder structure or want to start directing notes to a new folder, everything is included in the template. I don't have to edit the template AND the templater plugin (assuming that in a case where I'm directing a note to a new folder it might mean this is now a fundamentally different meeting.)

## Bind a Template to a Keyboard Shortcut
For templates you use regularly, you can speed up your processing even more if you're a keyboard-centric person by assigning specific keyboard shortcuts to specific templates. When you combine this with the fact that the template itself creates the file in the folder where you want it, then you've created a pretty slick system for making sure files go where you want them in just a couple of keyboard commands. 

Let's demonstrate that with a Project Template. 

## Create a Project Template
I want a folder called Projects that I'm going to put all my Project files in. 
1. Create a folder called Projects.
2. Create a new file in the Templates folder called Project Template.
3. I started with a very simple project template that includes the file name, date we created the file and then six sections as level 1 headings I also included the title of the file as a header and the date it was created as a page reference.
![[obs-ProjectTemplate.png]]

**Note:** I have a base template for templates (yes - it's called Template Template). The problem with it is that as soon as I run it on a new file the file.move command has run and is deleted from the file. So, when I create the new template, it gets automatically created in the Templates folder, but I need to add that line of code again to place the new template file where I want it. This is a place where I use TextExpander in combination with templates to streamline this work. I have just that last line of code saved in TextExpander so I can add it again quickly if I need to.

## Connect The Projects Template to a Hotkey


1. Go to the Templater Settings (Settings  > Templater) and find Template Hotkeys (it's just above Folder Templates).
5. Select Templates/Project Template.md from the list of templates in the box on the left and then click the Configure Hotkey Button
6. This will take you to the Hotkeys screen with this specific template selected. Click the "Customize This Command" button on the right

![[obs-projecttemplatehotkey.png]]

7. I chose Alt + Shift + P - you can choose what you want.
8. Close the Settings window to return to Obsidian.

Let's try it out.
1. Create a new note (Ctrl +N) and give it the name of your Project. I named mine Project A
2. Now, use your keyboard command to run your template (again, I chose Alt + Shift + P)
3. Your template should have run AND the Project A file should now be in your Projects folder

## Conclusion and Navigating the Series
This is the third article in my series on automating your workflow with templates. Use these links to navigate through the series:
- Part 1: Using Templates and Templater in Obsidian 
- Part 2: Maximizing the Templates Core Plugin
- Part 3: Getting Started with the Templater Community Plugin
- Part 4: Other Things You Can Automate Using Templater Commands and Functions and Other Resources for More Inspiration

# Part 4: Other Things You Can Automate Using Templater Commands and Functions and Other Resources for More Inspiration

## Introduction
This is the fourth - and for now final - article in my series on automating your workflow with templates. Use these links to navigate through the series:
- Part 1: Using Templates and Templater in Obsidian 
- Part 2: Maximizing the Templates Core Plugin
- Part 3: Getting Started with the Templater Community Plugin
- Part 4: Other Things You Can Automate Using Templater Commands and Functions and Other Resources for More Inspiration

As I wrap up this article, I thought I'd run few several templater commands and functions and then you can let your mind run through with those. If you find this useful, I hope you'll post comments with your own examples or let me know how you put these together to build templates that let you automate different tasks in your life.

- [[<% (await tp.file.create_new(tp.file.find_tfile("Template Name"), tp.date.now("YYYY-MM-DD") + " Name of New File", false)).basename %>]] - If you use a Daily Note as a log, having this command saved as a template (or even several different templates - all point to different templates - you can call it from within your daily note and immediately create a new link to a properly named new file in the right location.
-  [[<% tp.date.yesterday("YYYY-MM-DD") %>]] |[[<% tp.date.tomorrow("YYYY-MM-DD") %>]] - Add links to yesterday and tomorrow somewhere in your daily note template to have easy access to these options. 
- <% tp.date.now("YYYY-MM-DD", 1, tp.file.title, "YYYY-MM-DD") %> - This is the same command as above, but it bases the date off of the file title rather than off of today. This will generate the next date after the file's title. Put in a -1 for the 1 and you get the date before the file's title date.
- You can also combine a command with existing text. [Bryan Jenks suggested this](https://youtu.be/2234DXKbNgM?t=2193) as a method to create an "On this Day" section linking to the same date from previous years. I haven't been using Obsidian quite long enough for this to come in handy for me yet but I'm almost there. For anyone that uses their daily notes as a journal this might be of interest. The command looks like [[2020-<% tp.date.now("MM-DD") %>]]. I want to try using this with Transclusion and actually inserting my Highlight section from my notes right into my daily notes for the next year. 
- <% tp.file.creation_date() %> - Gives you the date a file was created. I like to include this in the Frontmatter for a lot of my documents.
- <% tp.system.clipboard() %> - When I'm reading an online document and I want to annotate a piece of text from the web, I'll copy it to my Clipboard, come to Obsidian and run the "Paste Text" template in a new note. That template contains only this command. It pastes the text I have on my system clipboard into the note. This is very useful for research and could be used in a Literature or Reference note for Zettelkasten makers.
- This one is a bit longer but has a LOAD of functionality options for it because it prompts you for a file name when it runs. I've combined it with the clipboard contents in this template and changed the frontmatter tag to include inbox so that it will come up in my inbox search each day and I can properly process the note into my PKM. The code for the prompt is from an [article by MacDrifter](http://www.macdrifter.com/2021/08/obsidian-templater-fun.html):
![[obs-promptforfilename.png]]





## Using Templater with Other Community Plugins - What's Coming Next in This Series

Templater compliments many other Community Plugins. Just a couple of those are:
- Periodic Notes (which I think works best with the Calendar Community Plugin and which I'll cover in depth in another future post coming shortly - all about building Daily Notes Templates), 
- Quick Add (which will be the subject of a future post like this one)
- Buttons (I don't have this one on my list to do a big dive into but if there is interest, I'll be happy to put a post together.)
- Dataview - basically any dataview query that I write immediately gets put into a template so that I never have to figure it out again. (I don't have this one on my list, but would add it if there is interest)


## Other Great Resources on Templater
In pulling together all my thoughts and notes for this article, I found a large number of really great resources about Templater and thought I'd close out with those. Where one was directly used in an example above, I tried to make sure I credited it in line above so that you see clearly that this is in no way all my work. 
- Stephen Millard - [His Obsidian Directory](https://www.thoughtasylum.com/obsidian/) - His articles were some of the first I read about Templater and they inspired me to keep playing and get better at using the tool despite the documentation being a little clunky.
- Red Gregory - [15 Templater Commands for Obsidian](https://www.redgregory.com/obsidian-content/2021/11/17/15-templater-commands-for-obsidian) - Red is fantastic! I hadn't thought of repeating tags in my document that are listed in the YAML front matter but I can see where that one might have value.
- Shabegom - [How to use Templater JS Scripts](https://shbgm.ca/obsidian/docs/how-to-use-templater-js-scripts) - I've read this and played around with it. While I am in no way prepared to show it to anyone else, if you're interested in learning more about this functionality in Obsidian, this resource has been helpful to me. 
- Macdrifter - [Obsidian Templater Fun](http://www.macdrifter.com/2021/08/obsidian-templater-fun.html) - One of the reasons this article was of interest to me to write, besides pulling together my knowledge about templates and templater into a single place in my own vault is that my template naming had gotten a little unwieldy. Macdrifter has some good thoughts on that
- Choumann - [Templater Templates Samples](https://github.com/chhoumann/Templater_Templates) - Some of the Readwise commands listed here might be useful in my workflows but they aren't necessities for me. That said, there is a TON of great stuff here and definitely something you should check out to see if there are things here you can grab for your templates. 
- Bryan Jenks - [Three Plugins Video](https://www.youtube.com/watch?v=2234DXKbNgM&t=1944s) - Templater is the last plug in he covers. Check out the time stamps in the description. I'm not interested in geeking out quite this much and replacing Periodic Notes plugin. It could be done but I like the simplicity of the Periodic Notes plugin. Bryan's video does contain a really good example of how to use IF statements with templater. 
- Nicole van der Hoeven - [Templater Video](https://www.youtube.com/watch?v=5j9fAvJCaig) - Nicole is incredible. Her video is what got me started using Templater. As I mentioned somewhere above, Nicole is the one who shared the idea to include the title as a linked reference in the file itself so that any time you change the file name your heading gets updated as well.
- Pamela Wang - [Create a Meta Templater](https://www.youtube.com/watch?v=5zcdG6ZWja4) - I have to admit, Pamela's version is NEXT LEVEL but watching her video gave me some ideas - particularly for all the content I create and the various templates for that.


## Conclusion
This is the fourth - and for now final - article in my series on automating your workflow with templates. I would truly love to know what you thought. What did I get wrong? How could I make this better? What else would you like to learn about?

Use these links to navigate through the series:
- Part 1: Using Templates and Templater in Obsidian 
- Part 2: Maximizing the Templates Core Plugin
- Part 3: Getting Started with the Templater Community Plugin
- Part 4: Other Things You Can Automate Using Templater Commands and Functions and Other Resources for More Inspiration