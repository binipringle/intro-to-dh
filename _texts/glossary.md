---
layout: narrative
title: Glossary of Technical Terms
author:
editor: Sabina Pringle
source:
toc:
- Command line
- Git
- HTML and CSS
- Jekyll
- Python

---

*Derived from the [Graduate Center Digital Research Institute (DRI)](https://gcdri.commons.gc.cuny.edu/) [January 2020 Curricula](https://gcdri.commons.gc.cuny.edu/curricula/january-2020-workshops/). Copyright GCDI with [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/legalcode). Edited by Sabina Pringle for this course.*

---

# Command Line

## Commands

`pwd` - show the current (or "working") directory. Stands for "print working directory"

`man <command>` — show manual for the command you are interested in learning more about; it will show all the flags the command will take as well

`ls` - show the files and folders in the working directory. I think of it as standing for "list stuff," but it's probably just short for "list."

`ls -1` — show the files and folders in a nice vertical column.

`ls -l` — show a detailed list of all the files and folders

`ls -a` — show all the files (including hidden files)

`ls -al`, `ls -a1` — the two commands above can be combined like this, to both (a) include all files, and (b) show the list in a nice vertical column.

`cd` - move to a directory, i.e. `cd Desktop` will move to the "Desktop" folder. Some special cases:

`cd ..` - go to the directory above

`cd ~` go to your "home" directory, i.e. /Users/<yourname>

`cd` (by itself) also goes to the home directory

`cd -` go to the last directory you were in before the current

`cd ../..` travel two directories up

`cd Documents/thesis-drafts` move two directories, from the home folder to (for example) "thesis-drafts," skipping "Documents"

`touch <filename>` - Create an empty text file named <filename> in your current directory.

`code <filename>` - Open file in VS Code (and create it, if it does not already exist).

`mkdir <folder name>` - Create a directory named `<folder name>` in the current working directory.

`echo <some text>` - Print out any text you give it. Often used with a redirect to add text to a file.

`cat <filename>` - Print the contents of a file to the screen, in this case the contents of `<filename>`

`>` - Redirects printed output to a text file, as in `echo "this is some text" > hello.txt`

`>>` - Redirect and append. If there's already a file with text in it, this command will add that text to the file without destroying and recreating it.

`|` - Pipe symbol. Takes output from one command and uses it as input for another command.

`less <filename>` - Print out the contents of a file in a paginated form. Use `<Control-v>` and `<Alt-v>` (or `<Command-v` and `<Option-v>`) to move up and down. Press `q` to quit.

`head <filename>` - Print the first section of a file

`tail <filename>` - Print the last section of a file

`wc -l` - Takes input and returns the number of lines in that input, as in `cat <filename> | wc -l`

`sort` - Arrange lines in a file in numeric and alphabetical order.

`uniq` - Remove duplicate lines from input, as in `cat <filename> | uniq`. To show the duplicate files, use `uniq -d`. Often most useful after using `sort`, since it only removed duplicates that are next to one another.

`mv` - Move or rename a file. For example, `mv file1 file2` will rename `file` to `file2`. You can also specify another destination, so that `mv file1 ~` will move file1 to the home folder without renaming it.

`rm <filename>` - Permanently remove a file from your computer.

## Definitions

### Synonyms for the command line

*bash* - the programming language used in the command line. (Yes, we tricked you, you're already programming!) Short for "Born Again SHell," for reasons people on the internet will happily tell you about.

*terminal* - Particularly used to refer to the command line on OSX. This term made more sense when universities used mainframes and every computer was only a terminal.

*shell* - The part of an operating system that interacts with a human. Technically, anything you do in a graphical interface is also in a shell, but in practice this is just another synonym for the command line.

*cli* - "Command Language Interpreter," this is a super technical term for the command line used to impress everyone around you.

### Other Terms

*GUI* - "Graphical User Interface." Pronounced "gooey," like delicious gooey chocolate. Basically, anything on a computer that isn't in the command line. All familiar elements of day-to-day computer tasks such as images, windows, prompts, buttons, and progress bars are part of the GUI. The way most people interact with computers. Some tasks can only be done in a GUI, while others can only be done in the command line.

*root* - A word for the administrative user on a system. You often need administrative privileges to install programs or access certain system folders using the command line. You can tell you're root when your `$` prompt turns into a `#` prompt. To become root, type `su` and enter the password you use to log in. (No characters or asterisks will appear, just type your password and press enter.) You can also run a single command as root by typing `sudo` before the command.

*UNIX* - A family of operating systems that have a multi-user model and a particular design philosophy. Both OSX and Linux are UNIXes. Windows is not.

*REPL* - "Read Eval Print Loop" The process of typing something in to the command line and getting something back out. Like most things to do with the command line, not as complicated (or scary) as it sounds.

*Text editor* - A program for creating and editing plain text files. Unlike word processors such as LibreOffice and Word, which create complex documents in the form of archives that include formatting information and other metadata, a plain text editor creates a single file. Programmers tend to use plain text files because computers can work with them easily. Sublime Text, Nano, and VI are examples of text editors.

*path* - A list of folders on your system that are checked for programs to generate the list of commands available on the command line. For example, since the folder `/bin` is typically on the path, putting an executable program in that folder will make it available as a command.

---

# Git

## Definitions

*branch* - A branch is an alternative timeline of commits, usually used to add a new feature or some other substantive change to a repository. Once the feature or change is complete, the branch can be reintegrated with the main timeline, which is usually called "master."  

*git* - Git is a version control tool. It lives on your local computer and can be accessed through the command line.   

*local* - An adjective describing the machine you're sitting in front of. "Your local machine" usually translates to "your laptop." In Git, a local repository is a repository on your machine.  

*markdown* - Markdown is a specific markup language designed to be readable as code, not just when it's displayed. That makes it fun to write in, at least compared to HTML. Markdown is provides a readable syntax for a subset of HTML, such as headings, lists, and links. These tutorials are written in markdown.  

*markup* - Markup languages allow you to format things, whether they're documents, posters, or websites. HTML is a markup language, as is LaTeX.  

*master* - The default branch, and typically the primary branch of a project. When a new repository is created with `git init`, it has one branch, and that branch is called "master."

*merge conflict* - If, when attempting to merge, there is a line that has been changed by both parties, you will experience a merge conflict. This means that Git needs your manual intervention to decide which of the two changes will be the canonical or accepted change. A merge conflict is resolved by editing the conflicting files with a text editor, then adding and committing to resolve the merge.  

*merge* - If you've advanced the timeline of a repository by making commits, and someone else has advanced the timeline of a remote version of the repository, when you attempt to pull in the remote changes you will be prompted to merge the two timelines. In most cases this is an automatic process that reconciles the two timelines.  

*origin* - In Git, the default remote repository. When you clone a remote repository—that is, make a local reposotry based on it—the remote repository is automatically added as "origin."

*pull* - Accepting and taking changes that were made to a remote repository, possibly by someone else, and updating your local repository to match.  

*pull request* - A pull request is a set of proposed changes to a repository. If you wish to contribute to an open-source project, the most common method is by proposing changes through pull requests.  

*push* - Pushing means sharing local changes with a remote repository. When you push local commits, the history of the remote repository is updated to match your local timeline.

*remote* - An adjective describing a computer that is somewhere else. A "remote machine" is a machine you do not have physical access to, but might have access through a means such as the internet. In Git, a remote is a repository that is not on your computer, but is connected to your local repository. You can add new remotes with the `git remote add` command, and change them with the `gitremote set-url` command.

*repo* - Short for repository.  

*repository* - A folder that is currently being tracked by Git. The folder could be on your local machine or it could be on a service such as GitHub. The tracking information that makes a normal folder into a Git repository is contained in a hidden folder, called `.git`, that lives in the repository.

*version control system (VCS)* - A tool for keeping track of versions of files in a project. They allow for collaboration in a team, storing work in multiple locations, and reverting back to a previous state of the project.

---

# HTML and CSS

Forthcoming.

---

# Jekyll

## Running Jekyll

These Jekyll-related commands can be entered in bash. (That's the prompt with the `$`.)

`jekyll new site_name` - This command will create a jekyll instance inside the directory you are currently in.

`jekyll serve` - This command will start the jekyll server in the directory you are currently in.

---

# Python

## Python from the Terminal

These Python-related commands can be entered in bash. (That's the prompt with the `$`.) They won't work inside Python. (Python uses the `>>>` prompt.)

`python --version` - Prints out version information for Python, and will tell you if you're using Anaconda or the default Python. Useful for figuring out if Python has successfully installed on your computer, and whether it's accessible from the command line.

`python` - Typing Python by itself brings up the Python interpreter, also known as the Python shell or the Python REPL (which stands for "read–eval–print loop"). Lines you type after this will be sent directly to Python and evaluated. Any result will be printed back to you. A standard interaction might look like this:

```
Python 3.6.4 (default, Jan 15 2018, 23:11:13)
[GCC 4.8.4] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> 2 + 2
4
```

`python <filename>` - Typing `python` and following it with a filename will feed that file into Python. This is how you run scripts from the command line.

# Python Syntax and Commands

These commands and syntax are used in the Python interpreter (the `>>>`) or when writing a Python text file. They will not work in the bash shell (the `$` prompt).

## Operators

Python accepts these operators:

- `+` - Plus. Add two things.
- `-` - Minus. Subtract one thing from another.
- `*` - Multiply. Multiply one thing by another.
- `/` - Divide. Divide one thing by another.
- `%` - Modulo or "mod." Divide and return the remainder..

Operators work on integers and floats, but can also be used to, for example, add strings together with plus or make them repeat with multiply.

## Data Types

Data types are classifications of what a variable represents and what kind of operators can be performed on it. For example, you can subtract one integer from another, but you're not allowed to subtract one string from another.

The data types we use in this lesson are:

- *integer* - A whole number, a number without a decimal point. `1` is an integer.
- *float* - A floating point number, a number with a decimal point. `1.0` is a float.
- *string* - A series of arbitrary text characters, including letters, numbers, and symbols. Basically, some text. Strings are denoted by double quotes, single quotes, triple double quotes, or triple single quotes. `"Hello, world!"` is a string. `'''Hello, world!'''` is also a string.
- *list* - A list is a collection of items, which can be any other data type, including lists. Lists are denoted by a `[` at the beginning and a `]` at the end, with commas between items. `[1, 2, 3]` is a list. `["I", "have", 10, "mushrooms"]` is a list.
- *Boolean* - A binary choice between truthiness and falsiness. Boolean values are written with capital letters. `True` is a Boolean. `False` is a Boolean. The word "Boolean" is capitalized because it derives from a proper name.

## Functions

Functions take some input and either do something or return a value or both. The input goes inside the parentheses.

*print()* - Print to the screen whatever is put in the parentheses.

*type()* - Return a value that represents the type of whatever is in the parentheses.

## Variables

A variable is a name that is assigned to a value. Assignment looks like this:

```python
x = 3
name = "Patrick"
name2 = "Ignatz"
grocery_list = ["tomato", "limes", "chocolate"]
```

Variable assignment uses a single `=`. The name given is on the left of the `=`, the value is on the right of the `=`.

## Loops

A loop takes a list and moves through it one value at a time. For each of the values, it runs the code in the indented block. While running that code, the name after "for" can be used to refer to the current value.

```python
flowers = ['rose', 'violet', 'buttercup']
for flower in flowers:
    print("My favorite flower is the", flower)
```

```
for <name_given_on_each_loop> in <list>:
    print("This is the current list item:", <name_given_on_each_loop>>
```

Remember that loops need a semicolon at the end of the first line and need to indent the code in the block below.

## Comparison and Equality

Comparison operators check if an expression is true or false.

- `==` - Checks if a value is equal to another value. `3 == 3` returns `True`. `"love" == "love!"` returns `False`.
- `>` - Greater than. `10 > 2` returns `True`. `3 > 4` returns `False`.
- `<` - Less than. `3 < 4` returns `True`. `10 < 2` returns `False`.
- `!=` - Does not equal. `3 != 4` returns `True`. `10 != 10` returns `False`.

You can also use `>=` and `<=` (greater than or equal to and less than or equal to).

## Conditionals

Conditionals check whether a value or comparison is true or false. If it's true, some code is run. If it's false, different code is run.

```python
weather = "sunny"

if weather == "sunny":
    print("Bring your shades")
elif weather == "rainy":
	print("Bring your umbrella")
else:
    print("I don't know what you should bring! I'm just a little program...")
```

Like a loop, conditionals start a block with a colon at the end of the line.

Components of a conditional:

- *if statement* - Starts with `if` followed by a value that is either true or false. The block after the colon (`:`) is run if the statement is true.
- *elif statement* - Starts with `elif` followed by a value that is either true or false. Only used if the value after the initial `if` was false. If the value after `elif` is true, the code in the block underneath is run.
- *else statement* - A catchall. If the `if` statement was not true and none of the `elif` statements are true, run the code block under `else`.
- *case* - Each branch in the conditional, whether if, elif, or else, is called a **case**.

You can have multiple elif statements but only one if statement and only one else statement in a conditional. You don't need to have elif or else statements. If you don't have elif or else statements, if the if statment isn't true, nothing will happen.

## Input

`input()` is a function that prints the string in parentheses, then waits for the user to type. After the user types and presses enter, the `input()` function uses the value the user entered within the program.

This two-line program asks the user a question and uses their answer in a response.

```python
name = input("What's your name? ")
print(name + "? That's great. Not what I'd have chosen, but great.")
```

## Importing Libraries

A **library** is a set of code, including functions and objects, that can be brought into your program and used.

Import a library like this:

```python
import random
```

In this case, random is the name of our library, but we could also, for example, `import csv` if we wanted to work with CSVs.

To use a function from the random library, we use a special dot (`.`) syntax:

```python
random_number = random.randint(0, 100)
print("My random number is", random_number)
```

---

[Home](/intro-to-dh/index)
