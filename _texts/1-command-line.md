---
layout: narrative
title: Command Line
author: Kelsey Chatlosh, Patrick Smyth, Mary Catherine McKinniburgh, and Jojo Karlin
editor: Sabina Pringle
rights: License (specify)
source: Graduate Center Digital Humanities Research Institute
toc:
- Introduction to the command line
- What is the command line?
- Letter from Wendell Phillips, Esq.
- Chapter I
- Chapter II
- Chapter III
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

This session was adapted from *Introduction to the Command LIne* session created by Kelsey Chatlosh for the Graduate Center Digital Research Institute in January 2020, and based on work by GC Digital Fellows Patrick Smyth, Mary Catherine McKinniburgh, and Jojo Karlin. The [Guttenberg file](http://www.gutenberg.org/) does not tell us which witness was used in making their digital edition. You will find the link to the GitHub repository in the [Documentation]({{ site.baseurl }}/documentation/). I might want to say in the bibliography or references.

---

## Introduction to the command line

Many of us have had some interaction with computers, and would be able to explain what a screen and a cursor are, and then show how to point and click on icons. When we do this, we are relying on a graphical user interface, or GUI (pronounced "gooey!").

In this session we are going to explore another way to make a computer do things: through the command line. Instead of pointing and clicking, we will be typing in the laptop's terminal to tell the computer directly what task to perform.

While this new technique can seem intimidating if you have not used text-based interfaces before, luckily, you can use 90% of the functionality of the command line by becoming comfortable with a very small set of the most common commands.

In this session, we will:

* learn common commands to create files (touch and echo)
* learn commands to create directories (mkdir)
* navigate our file structure using change directory (cd), print working directory (pwd), and list (ls)
* move content from one place to another using redirects (>) and pipes (|)
* explore a comma separated values (.csv) dataset using word and line counts, head and tail, and the concatenate command cat
* search text files using the grep command
* create and sort cheat sheets for the commands we learn

[Get started >>>]({{ site.baseurl }}{% link _texts/what-is-the-command-line.md %})

This tutorial is based on previous work by Kelsey Chatlosh, Patrick Smyth, Mary Catherine McKinniburgh, and Jojo Karlin for the CUNY Graduate Center Digital Humanities Research Institute

---

## What is the command line?

The command line is a text-based way of interacting with your computer. You may hear it called different names, such as the terminal, the shell, or bash. In practice, you can use these terms interchangeably. (If you're curious, though, you can read more about them in the glossary.) The shell we use (whether terminal, shell, or bash) is a program that accepts commands as text input and converts commands into appropriate operating system functions.

What does "text-based" mean?

For those of us comfortable reading and writing, the idea of "text-based" in the context of computers can seem a bit strange. As we start to get comfortable typing commands to the computer, it's important to distinguish "text" from word processed, desktop publishing (think Microsoft Word or Google Docs) in which we use software that displays what we want to produce without showing us the code the computer is reading to render the formatting. Plain text has the advantage of being manipulable in different contexts.

Let's take a quick moment to discuss text and text editors.

<<< Previous | Next >>>
