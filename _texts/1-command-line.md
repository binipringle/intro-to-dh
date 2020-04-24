---
layout: narrative
title: Command Line
author:
editor: Sabina Pringle
rights: License (specify)
source: Graduate Center Digital Humanities Research Institute
toc:
- Introduction to the command line
- What is the command line?
- Text editors
- Why is the command line useful?
- Getting to the command line
- Navigation
- Chapter IV
- Chapter V
- Chapter VI
- Chapter VII
- Chapter VIII
- Chapter IX
- Chapter X
- Chapter XI
- Appendix
- A Parody
---

---

## Editor's note

This session was adapted from *Introduction to the Command LIne* session created by Kelsey Chatlosh for the Graduate Center Digital Research Institute (GCDHI) in January 2020, and based on work by GC Digital Fellows Patrick Smyth, Mary Catherine McKinniburgh, and Jojo Karlin. Links to the GC website and GitHub repositories are in the [Documentation]({{ site.baseurl }}/documentation/). I want to say in the bibliography or references but I have to get this together.

---

# Introduction to the command line

Many of us have had some interaction with computers, and would be able to explain what a screen and a cursor are, and then show how to point and click on icons. When we do this, we are relying on a graphical user interface, or GUI (pronounced "gooey!").

In this session we are going to explore another way to make a computer do things: through the command line. Instead of pointing and clicking, we will be typing in the laptop's terminal to tell the computer directly what task to perform.

While this new technique can seem intimidating if you have not used text-based interfaces before, luckily, you can use 90% of the functionality of the command line by becoming comfortable with a very small set of the most common commands.

In this session, we will:

- learn common commands to create files (touch and echo)
- learn commands to create directories (mkdir)
- navigate our file structure using change directory (cd), print working directory (pwd), -and list (ls)
- move content from one place to another using redirects (>) and pipes
- explore a comma separated values (.csv) dataset using word and line counts, head and tail, and the concatenate command cat
- search text files using the grep command
- create and sort cheat sheets for the commands we learn

---

# What is the command line?

The command line is a text-based way of interacting with your computer. You may hear it called different names, such as the terminal, the shell, or bash. In practice, you can use these terms interchangeably. (If you're curious, though, you can read more about them in the glossary.) The shell we use (whether terminal, shell, or bash) is a program that accepts commands as text input and converts commands into appropriate operating system functions.

What does "text-based" mean?

For those of us comfortable reading and writing, the idea of "text-based" in the context of computers can seem a bit strange. As we start to get comfortable typing commands to the computer, it's important to distinguish "text" from word processed, desktop publishing (think Microsoft Word or Google Docs) in which we use software that displays what we want to produce without showing us the code the computer is reading to render the formatting. Plain text has the advantage of being manipulable in different contexts.

Let's take a quick moment to discuss text and text editors.

---

# Text editors

## What is text?

Before we explain which program we will use for editing text, we want to give a general sense of this "text" we keep mentioning. For those of us in the humanities, whether we follow literary theorists who read any object as a "text" or we dive into philology, paleography, codicology or any of the fields David Greetham lays out in Textual Scholarship (I could maybe add this to the resources page - see also the text referred to in the introduction - Kelshey's not my adaptation), "text" has its specific meanings. As scholars working with computers, we need to be aware of the ways plain text and formatted text differ. Words on a screen may have hidden formatting. If you are familiar with HTML and making websites, you might know that in order to display even the simplest text on your website, you need specific codes. Many of us grew up using Microsoft Word and don't realize how much is going on behind the words shown on the screen. For the purposes of communicating with the computer and for easier movement between different programs, we need to use text without hidden formatting.

![first]({{https://github.com/binipringle}}/assets/img/command-line-1-worddoc.jpg)

![second]({{intro-to-dh}}/assets/img/command-line-1-worddoc.jpg)


or this is the html

<img src="/assets/img/command-line-1-worddoc.jpg" alt="" >


If you ask the command line to read that file, this Word .docx file will look something like this

INSERT command-line-2-catworddoc.png

Word documents which look like "just words!" are actually comprised of an archive of extensible markup language (XML) instructions that only Microsoft Word can read. Plain text files can be opened in a number of different editors and can be read within the command line.

## Plain Text

For the purposes of communicating with machines and between machines, we need characters to be as flexible as possible. Plain text includes characters of readable material but not graphical representation.

According to the Unicode Standard,[^1].

[^1]: There is a definition of Unicode in the glossary in case you are wondering what Unicode is and want to look it up.

> Plain text is a pure sequence of character codes; plain Unicode-encoded text is therefore a sequence of Unicode character codes.

Plain text has two main properties with regard to rich text:

> Plain text is the underlying content stream to which formatting can be applied. Plain text is public, standardized, and universally readable.

Plain text shows its cards-- if it is marked up, the markup will be human readable. Plain text can be moved between programs more fluidly and can respond to programmatic manipulations. Because it is not tied to a particular font or color or placement, plain text can be styled externally.

A counterpoint to plain text is rich text (sometimes denoted by the Microsoft rich text format ".rtf" file extension) or "enriched text" (sometimes seen as an option in email programs). In rich text files, plain text is elaborated with formatting specific to the program in which they are made.

## Text editors

An important tool for programming and working in the command line is a text editor. A text editor is a program that allows you to edit plain text files, such as .txt, .csv, or .md. Text editors are not used to edit rich text documents, such as .docx or .rtf, and rich text editors should not be used to edit plain text files. This is because rich text editors will add many invisible special characters that will prevent programs from running and configuration files from being read correctly.

While it doesn't really matter which text editor you choose, you should try to become comfortable with at least one text editor.

## Default text editor for this course

Choosing a text editor has as much to do with personality as it does with functionality. Graphical user interfaces (GUIs), user options, and "hackability" vary from program to program. For our workshops, we will be using Visual Studio Code (VS Code). Not only is VS Code free and open source, but it is also consistent across OSX, Windows, and Linux systems.

Visual Studio Code has been preinstalled on your laptop. We won't be using the editor a lot in this tutorial, so don't worry about getting to know the editor now. In later workshops we will discuss syntax highlighting and version control, which VS Code supports. For now we will get back to working in the command line itself.

---

# Why is the command line useful?

Initially, for some of us, the command line can feel a bit unfamiliar. Why step away from a point-and-click workflow? By using the command line, we move into an environment where we have more minute control over each task we'd like the computer to perform. Instead of ordering your food in a restaurant, you're stepping into the kitchen. It's more work, but there are also more possibilities.

The command line allows you to...

* Easily automate tasks such as creating, copying, and converting files.
* Set up your programming environment.
* Run programs you create.
* Access the (many) programs and utilities that do not have graphical equivalents.
* Control other computers remotely.

In addition to being a useful tool in itself, the command line gives you access to a second set of programs and utilities and is a complement to learning programming.

What if all these cool possibilities seem a bit abstract to you right now? That's all right! On a very basic level, most uses of the command line are about showing information that the computer has, or modifying or making things (files, programs, etc.) on the computer.

In the next section, we'll make this a little more clear by getting started with the command line.

---

# Getting to the command line

## Ubuntu

The operating system you are using is Ubuntu[^2].There are two ways to get to the command line in Ubuntu.

[^2]:  Ubuntu (pronounced "uh-BUN-two") is a free and open-source Linux distribution based on Debian. Debian, also known as Debian GNU/Linux, is a Linux distribution composed of free and open-source software, developed by the community-supported Debian Project, which was established by Ian Murdock on August 16, 1993. A Linux distribution (often abbreviated as distro) is an operating system made from a software collection that is based upon the Linux kernel and, often, a package management system (all definitions from Wikipedia).

First way:

Double-click on the terminal icon on the left hand side of your screen. The terminal icon looks like this:

INSERT command-line-3-terminal-icon.png

Second way:

1. Double-click on the word "Activities" in the top left corner of your screen.
2. Type "terminal" into the bar that appears.
3. Select the first item that appears in the list.

The terminal will look like this:

INSERT command-line-4-terminal.png

When you see the `$`, you're in the right place. We call the `$` the command prompt; the `$` lets us know the computer is ready to receive a command. The command prompt is the place you type commands you wish the computer to execute. We will now learn some of the most common commands.

In the next section, we'll learn how to navigate the filesystem in the command line.

---

# Navigation

## Prefatory pro tips

Go slow at first and check your spelling!

One of the biggest things you can do to make sure your code runs correctly and you can use the command line successfully is to make sure you check your spelling! Keep this in mind today, this week, and your whole life. If at first something doesn't work, check your spelling! Unlike in human reading, where letters can simultaneously have different uses and meanings, in coding, each character has a discrete function including (especially!) spaces.

Keep in mind that the command line and file systems are usually pre-configured as cAsE-pReSeRvInG -- so capitalizations also matter when typing commands and file and folder names.

Also, while copying and pasting from this handy tutorial may be tempting to avoid spelling errors and other things, we encourage you not to! Typing out each command will help you remember them and how they work.

## Getting started: know thyself

You may also see your username to the left of the command prompt `$`. Let's try our first command. Type the following and press the enter key:

    $ whoami

The `whoami` command should print out your username. Congrats, you've executed your first command! This is a basic pattern of use in the command line: type a command, press enter on your keyboard, and receive output.

## Orienting yourself in the command line: folders

OK, we're going to try another command. But first, let's make sure we understand some things about how your computer's filesystem works.

Your computer's files are organized in what's known as a hierarchical filesystem. That means there's a top level or "root" folder on your system. That folder has other folders in it, and those folders have folders in them, and so on. You can draw these relationships in a tree:

    Users
    |
    -- binipringle
      |
      -- Applications
      -- Desktop
      -- Documents

The root or highest-level folder on Linux is just called `/`. We won't need to go in there, though, since it mostly just contains files for the operating system.

Note that we are using the word "directory" interchangeably with "folder"--they both refer to the same thing.

OK, let's try a command that tells us where we are in the filesystem:

    $ pwd

You should get output like `bini`. That means you're in the `bini` directory in the `Users` folder inside the `/` or root directory. The folder you're in is called the working directory, and `pwd` stands for "print working directory."

The command `pwd` won't actually print anything except on your screen. This command is easier to grasp when we interpret "print" as "display."

OK, we know where we are. But what if we want to know what files and folders are in the `bini` directory, a.k.a. the working directory?

Try entering:

    $ ls

You should see a number of folders, probably including Documents, Desktop, and so on. You may also see some files. These are the contents of the current working directory. `ls` will "list" the contents of the directory you are in.

Wonder what's in the Desktop folder? Let's try navigating to it with the following command:

    $ cd Desktop

The `cd` command lets us "change directory." (Make sure the "D" in "Desktop" is capitalized.) If the command was successful, you won't see any output. This is normal —- often, the command line will succeed silently.

So how do we know it worked? That's right, let's use our `pwd` command again. We should get:

    $ pwd
    /Users/bini/Desktop

Now try `ls` again to see what's on your desktop. These three commands — `pwd`, `ls`, and `cd` — are the most commonly used in the terminal. Between them, you can orient yourself and move around.

Before we move on, let's take a minute to navigate through our computer's file system using the command line.

---

## Challenge

Use the three commands you've just learned — `pwd`, `ls` and `cd` — eight (8) times each. Go poking around your Pictures folder, or see what's so special about that root `/` directory. When you're done, come back to the home folder with

    cd ~

(That's a tilde, on the top left of your keyboard.) One more command you might find useful is

    cd ..

which will move you one directory up in the filesystem. That's a `cd` with two periods after it.

---

## Compare with the GUI

It's important to note that this is the same old information you can get by pointing and clicking displayed to you in a different way.

Go ahead and use pointing and clicking to navigate to your working directory--you can get there a few ways, but try starting from "Files" and clicking down from there. You'll notice that the folder names should match the ones that the command line spits out for you, since it's the same information! We're just using a different mode of navigation around your computer to see it.

---
