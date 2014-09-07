---
title: A POETIC INTRODUCTION TO GIT
files: []
editable: true
layout: 2-panels-tree

---
#'Forking' this module
If you check the url address bar of your browser, if it starts with `https://codio.com/anon/....` then this means it is an anonymous project and any changes you make will be lost when you close down the browser tab. This will be the case if you access the module from the Codio Courses screen.

To avoid losing changes, you can 'fork' the module into your own Codio account where it will appear in your projects list. To do this, select the **'Project->Fork'** menu item and choose a suitable name for the project.

#A few words about the Codio Guide
Before we start with this module here are a few pointers about using this Codio Guide.

If you've already read this in another Guide then skip to the next section.

![](.guides/img/guides-helper.jpg)

#The File Tree
The left most panel is the File Tree **(1)**. This is where your project's files are stored. You can open up files you see listed there by clicking on them.

#About the Codio Guide
The Codio Guide **(2)** is the content you are reading right now. It's worth knowing the following

- if you ever close the Guide tab by mistake, simply open in from the View menu **(3)**.
- you can expand and collapse the Guide's Table of Contents **(4)** with the Hamburger icon **(5)**
- you move from one section of the Guide to the next using either the Table of Contents or the Navigation Buttons (6)

#The Rocket Menu
The Rocket menu **(7)** is a dropdown menu that lets you load code into your file tree when you click it as different sections might want to show different bits of code.

You are usually encouraged to mess around with the live code. It is perfectly likely that you can wreck the code so pressing the Rocket menu button will restore the code again to its original state.

#Previewing
The Preview button **(8)** lets you run your web application. When you press it, it will open up a preview window so you can play with your app.

#Code Tabs
When you open some code from the file tree or the Codio Guide opens a file for you automatically, they will appear within a tab **(9)** in one of the panels. You can have several of these open at one time so you may need to click on the respective tab to get to see the file you want.


---
title: Overview
files: []
editable: true
layout: ""

---
#Module 1 - The Basics
In this module we will cover the basic and most commonly used Git operations.

You can navigate from one section to the next using the buttons at the bottom right or by opening up the table of contents (hamburger icon top right of this window). 

##Who this course is for
This is a beginner level Course for people who have never used Git or Source Control Management systems before. The purpose is to get anyone to a level where they feel completely comfortable using Git for all common use cases. 

Total mastery of Git, which is really not necessary by the way, can then be gradually achieved using reference materials as you work with Git on a daily basis.

If you are already familiar with source control management systems then you can skip this section. 

##A fully interactive course
The great thing about this course is that it is interactive. Using Codio, you can follow the course and actually use Git at the same time. You can edit files and use the command line for Git commands with complete freedom. 

As with most things, practice makes perfect and using Codio let’s you do just that - practice as you learn. Each module has starting points with data and commits already in place so you don’t have to tediously create them yourself. 

##Video Overview
To get an overview of what Git does, watch the video below. We’ll then move immediately into using Git.

![640x480](http://www.youtube.com/watch?v=kDUSoOubyGU&feature=youtu.be)

##Graphical Software Tools
Git is a command line tool, so you enter commands in a terminal window rather than using a pretty desktop application.

You will come across products that have a Graphical User Interface for Git. If you watched the overview video, you will have seen me using Ungit, a GUI tool that you can install on your Codio Box.

**But** - *please, please, please* don’t use them until you are comfortable with the command line. There are a few reasons for this.

- If you can use the command line, you will find GUI products much more obvious although you may decide to never use one.
- Git is a command line tool, so any Git GUI will be both an approximation and a dilution
- To get the full power of Git, the command line is as powerful as it gets
- If you find (and you will) that your GUI tool cannot do something you need to do, you will struggle as you will not be familiar with the command line
- Working with the command line is faster and more streamlined than a GUI, especially if you set up helper scripts for common commands

So - use a GUI tool later by all means - and I can recommend Ungit as a free and powerful tool - but first you must get completely comfortable with Git on the command line.
---
title: "Installation & Setup"
files: []
editable: true
layout: ""

---
This tutorial is running on the Codio coding platform. There’s nothing to set up, so once you are in your project, you will find Git already installed. 

If you’re NOT running this tutorial on Codio, then installing Git itself is [described here](http://git-scm.com/book/en/Getting-Started-Installing-Git).

---
title: Using the command line
files: []
editable: true
layout: ""

---
When you are prompted to use the command line, you should open up a Codio terminal window as follows

- From the Codio menu, select **Tools->Terminal**
- Shortcut key is **Shift+Alt+T** (all platforms)

Go ahead and open up a terminal window now.

---
title: What is a Git repository
files: []
editable: false
layout: ""

---
The good news is that you don’t need to know where Git stores its files and data. If you are not interested in knowing more, then skip to the next section.

#Yes, I am interested
You can think of your Git repository as a database that contains multiple snapshots in time of your code. Nothing gets added to the repository until you explicitly tell Git.

When Git is initialised in a project, a hidden directory called `.git` is created beneath your workspace folder (which is why you don’t see it in the Codio file tree but you can if you use the command line). 

So you should now be aware that the Git repo is actually a part of your project, albeit a hidden one, and is not (yet) on any external system like BitBucket or GitHub. We’ll be doing this in the next module in fact.

If you want to see the Git repo (remember, it is just a database contained within the hidden `.git` directory), type the following from the command line (**Tools=>Terminal** menu item)

```bash
ls -al .git
```

It is not at all necessary to ever look in this folder but you can Google it for more details if you really feel the urge.

---
title: The Working Directory
files: []
editable: false
layout: ""

---
The Working Directory is easy to understand as it is the directory and all its sub-directories where the code you are working on lives. It’s what you see in the file tree. 

Codio projects always have a folder called ‘workspace’ and this is the base location for your code. In the file tree, your workspace folder is the top most folder.

![](.guides/img/working-dir.png)

The above image shows our file tree with a couple of files.
---
title: Your First Git Command
files: []
editable: false
layout: ""

---
Run `git status` from the terminal and you will see

```bash
# On branch master
nothing to commit, working directory clean
```

This tells you that Git cannot find anything to do.

Once you start adding or editing files in your working directory, nothing is actually added to your Git repo until you tell Git to do so. 
---
title: Adding a file
files: []
editable: false
layout: ""

---
So, let's do something

1. Add a new file `mary.txt`to the your working directory (right click the root folder in the file tree and select New File from the pop-up menu)
2. Copy and paste the following text into your new file

```bash
Mary had a little lamb,
His fleece was white as snow,
And everywhere that Mary went,
The lamb was sure to go.
```
3. Enter `git status` in the terminal

You should now see this

```bash
# On branch master
# Untracked files
#   (use "git add <file>..." to include in what will be committed)                                           
#
#   mary.txt
#
nothing added to commit but untracked files present (use "git
 add" to track) 
```

This tells you the following

- you are on the `master` branch (more on that later)
- Git has detected that `mary.txt` in the working directory is not yet tracked by Git, which we'll deal with in the next section.


---
title: Staging Files
files: []
editable: false
layout: ""

---
You can think of the Staging Area as a current and temporary snapshot of files and changes that you are ready to add to your Git repo.

Take a look at the file tree. The only file in it (the working directory) is `mary.txt`. This is how things currently look to Git.

![](.guides/img/track-stage-1.png)

As soon as you run `git add`, which we'll do next, your file is ...

- *Tracked* - Git will know about this file from now on
- *Staged* - Git takes a snapshot of the **current state** of the file and adds it to the *Staging Area*

So let's enter these commands in the terminal

- `git add mary.txt` to stage and track `mary.txt`
- `git status` again and this time you’ll see

```bash
# On branch master
#
# Initial commit
#
# Changes to be committed:
#   (use "git rm --cached <file>..." to unstage)
#
#       new file:   mary.txt
#
```

Notice that it no longer mentions that `mary.txt` is not being tracked. It tells us that it is ready to be committed. In other words, `mary.txt` is now staged.

Now go and modify `mary.txt` again and then check the status. This time you’ll see

```bash
# On branch master
# Changes to be committed:
#   (use "git reset HEAD <file>..." to unstage)
#
#       new file:   mary.txt
#
# Changes not staged for commit: 
#   (use "git add <file>..." to update what will be committed)
#   (use "git checkout -- <file>..." to discard changes in working directory)
# 
#       modified:   mary.txt 
# 
```

This tells you that although `mary.txt` is being tracked and is staged, it has been modified since the last time you staged it with `git add mary.txt`. 

If you now commit these changes to your Git repo (coming up soon) then any changes *after* `git add mary.txt` would *not* be committed until you run 'git add mary.txt' again.

---
title: Add some more files
files: []
editable: false
layout: ""

---
#Add some more files
Let’s make some more changes.

- add another 2 files (maybe call them `shakespeare.txt` and `limerick.txt`) and add a short bit of content to each file. 
- make a small change to the contents of mary.txt (anything at all)
- run `git status` from the command line

```bash
# On branch master
# Changes to be committed:
#   (use "git reset HEAD <file>..." to unstage)
#
#       new file:   mary.txt
#
# Changes not staged for commit:
#   (use "git checkout -- <file>..." to discard changes in working directory)  
#
#       modified:   mary.txt
#
# Untracked files: 
#   (use "git add <file>..." to include in what will be committed) 
# 
#       limerick.txt
#       shakespeare.txt
#  
```

Git tells you that the new files are **not** being tracked. So things look like this now.

![](.guides/img/track-stage-3.png)

If we want to add these new files to our repo, we will need to stage them.

Luckily, there is a quick way to add all untracked files (and all unstaged edits in all tracked files) to the staging area. Just enter the following

```
git add -A
```

Run `git status` again

```
# On branch master
# Changes to be committed:
#   (use "git reset HEAD <file>..." to unstage)
#
#       new file:   limerick.txt
#       new file:   mary.txt
#       new file:   shakespeare.txt
#  
```

You can see how everything is nicely staged, ready to commit to our Git repository.

So we finally have this

![](.guides/img/track-stage-4.png)

**IMPORTANT** : If you have made any further edits to the files,  be sure to stage them with `git add` first.
---
title: Committing changes to the repo
files: []
editable: false
layout: ""

---
Now we are ready to *commit* files to our repo.  This will finally add all **staged** files to the repo.

With each commit, we provide a message to help us identify the commit later.

Let's commit now

```bash
git commit -m 'my first commit'
```

You’ll be rewarded with something like this

```bash
[master 16c6a81] my first commit
 3 files changed, 5 insertions(+)
 create mode 100644 mary.txt
 create mode 100644 shakepseare.txt
 create mode 100644 limericks.txt
```

Your files are now safely stored in the Git repo and you would have to try very hard to lose that code, which is exactly what we’ll try to do next.

---
title: Delete everything
files: []
editable: false
layout: ""

---
Yes - we are now going to delete all of our files in the Working Directory. Select them in the file tree and right click to delete or, if you prefer, enter the following in the terminal window

```bash
rm *.*
```

All your files are gone. Imagine this was a complete mistake and the panic that would ensue.

It feels a bit uncomfortable doesn’t it? However, Git let’s you recover from any earlier commit in various ways. 

We’ll recover using the simple sledgehammer approach. We’ll explain the dangers of `git reset` in a later module.

```bash
git reset --hard HEAD
```

Now take a look at your project and the files will have been restored exactly as they were in the previous commit.

We’ll cover what this command does in more detail later on, but what it is basically saying is ‘reset the Working Directory to most recent commit (known as HEAD).
---
title: Finally
files: []
editable: false
layout: ""

---
There are a couple of extra things worth knowing about.

##Unstaging files
What happens if you have staged a file (using `git add`) and then change your mind and want to remove it or changes to it from the staging area?

You can unstage any file using the following command

```bash
git checkout -- file.txt
```
There are other ways we can accomplish this and similar things, which are discussed in Module 5.

##Committing and Staging simultaneously
If you Stage files and then make more edits to those files in the Working Directory and then run `git commit -m`, any changes you may have made after staging will not have been added to the commit.

There is a way simple was around this. You can commit all current changes to all *tracked* files without having to use `git add` at all. 

```bash
git commit -am 'commit message'
```

This will automatically stage any changes to all currently tracked files. However, this will not commit new files that are not yet tracked.

So, the fast and lazy way to get track/stage and commit everything is to use the following commands one after the other

```bash
git add -A
git commit -m 'commit message'
```

In the next Section, you should experiment lots so you can see exactly what Git is doing with your changes and feel completely comfortable with the entire process.
---
title: Play Time
files: []
editable: false
layout: ""

---
Now it’s time to play around and get used to the `git status`, `git add` and `git commit` commands. 

**IMPORTANT** : have absolutely no fear, just add files, add text to them, delete them and in between use `git status`. 

Check out what we were talking about in the previous section where we changed staged files that had not yet been committed. 

- If you want to return to your previous commit at any stage, just enter `git reset —hard HEAD`. 
If you want to go back 3 commits, use `git reset —hard HEAD~2`.
- If you want to restore everything to the initial state as of the start of this module, enter `git reset --hard HEAD@{0}` or pres the 'Restore' button in the menu at the top of the Codio IDE.

Once you feel you have completely absorbed what is going on, move onto the next Module and play with remote repositories.