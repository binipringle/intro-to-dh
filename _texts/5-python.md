---
layout: narrative
title: Introduction to Python
author:
editor: Sabina Pringle
source: CUNY Graduate Center Digital Research Institute
rights: Digital Research Institute (DRI) Curriculum by Graduate Center Digital Initiatives (GCDI) with CC Attribution-ShareAlike 4.0 International License.
source: Graduate Center Digital Research Institute
toc:
- Overview and learning goals
- Interacting with Python
- Types
- Variables
- Running scripts
- Errors in Python
- Lists and Loops
- Conditionals
- Input
- Case sensitivity
- A little motivation
- Objects in python
- Python resources

---

*By Patrick Smyth for Digital Research Institute (DRI) Curriculum by Graduate Center Digital Initiatives (GCDI). Copyright GCDI with CC BY-SA 4.0. Edited by Sabina Pringle for this edition.*

---

# Overview and learning goals

Python is a general-purpose programming language that is suitable for a wide variety of core tasks in the digital humanities. Learning Python fundamentals is a gateway to analyzing data, creating visualizations, composing interactive websites, scraping the internet, and engaging in distant reading of texts.

By the end of this workshop, participants will:

- Understand what Python is and, in general terms, what it can do.
- Run Python programs, both by interacting directly with the interpreter and by preparing and running scripts.
- Distinguish among five core data types—integers, floats, strings, booleans, and lists.
- Become familiar with core programming concepts, including variables, loops, and conditionals.
- Engage with error output and use the internet and documentation to independently research language features.
- Learn how to find and import code from external sources to solve more complex problems.

---
# Interacting with Python

![ilian1](/intro-to-dh/assets/img/ilian/ilian1.png)

*Illustration by Ilian Sanchez, 2020. Copyright Ilian Sanchez with CC BY-NC-SA 4.0.*

---

To start an interactive session with Python, open your terminal and type

```console
$ python
```

at the prompt. You should see something like this

```pycon
Python 3.6.3 |Anaconda, Inc.| (default, Oct 13 2017, 12:02:49)
[GCC 7.2.0] on Linux
Type "help", "copyright", "credits" or "license" for more information.
>>>
```

Unlike the normal `$` terminal prompt, the Python prompt looks like this:

```pycon
>>>
```

Keep an eye on this, as a common early source of confusion is entering terminal commands into the Python prompt or entering Python commands into the terminal.

---

## A Little Math

Let's try a little math at the Python prompt. In the example below, type the text that appears after the Python prompt (the `>>>`). The line below is the output that is returned. This will be a standard convention when giving examples using the Python prompt.

```pycon
>>> 2 + 3
5
>>> 14 - 10
4
>>> 10 * 10
100
>>> 6 / 3
2
>>> 21 % 4
1
```

The first four operations above are addition, subtraction, multiplication, and division, respectively. The last operation is modulo, or mod, which returns the remainder after division.

Note the way you interact with Python at the prompt. After entering an expression such as `2 + 3`, Python "evaluates" it to a simpler form, `5`, and then prints out the answer for you. **This process is called the Read Eval Print Loop, or REPL**. Reading takes commands from you, the input is evaluated or run, the result is printed out, and the prompt is shown again to wait for more input. The normal terminal (the one with the `$`) is another example of a REPL.

The REPL is useful for quick tests and, later, can be used for exploring and debugging your programs interactively.

## Challenge

1. For a few minutes, practice moving in and out of Python's interactive mode (also known as the REPL). You can get out of Python by hitting `Control-d` (or `Control-z` if you're using Git Bash) or by typing `exit()`, and you can get back in by typing `python` at the `$` prompt. Remember that you're in the REPL when you see `>>>`, and you're in bash when you see the `$`.

---


# Types

**Types are classifications that let the computer know how a programmer intends to use a piece of data**. You can just think of them as, well, types of data.

We've already seen one type in the last section: the integer. In this section, we'll learn four more: the floating point number, the string, the boolean, and the list.

Enter these lines as you see them below:

```pycon
>>> type(1)
<class 'int'>
>>> type(1.0)
<class 'float'>
>>> type("Hello there!")
<class 'str'>
>>> type(True)
<class 'bool'>
>>> type([1, 2, 3])
<class 'list'>
```

Each of these represents a different type:

**Integer**: `1`

Integers are whole numbers.

**Float**: `1.0`

Floats are numbers with decimals, and are treated a little differently than integers.

**String**: `"Hello there!"`

Strings are arbitrary sets of characters, such as letters and numbers. You can think of them as a way to store text.

**Boolean**: `True` and `False`

Boolean is a fancy term for values representing "true" and "false," or "truthiness" and "falsiness."

**List**: `[1, 2, 3]`

A list is an ordered collection of values. You can put any type in a list: `["rose", "daisy", "buttercup"]` is also a valid list.

Don't worry about trying to actively remember these types. We'll be working with each in turn in the following sections.

## What's the deal with type()?

`type()` is a function. You can think of functions in Python in a few different ways:

1. A way of doing something in Python.
2. A way of saving some code for reuse.
3. A way of taking an input, transforming that input, and returning an output. The input goes in the parentheses `()`.

These are all valid ways of thinking about functions. We'll be learning more about functions in later sections.

---

# Variables

A variable is **a symbol that refers to an object**, such as a string, integer, or list. If you're not already at the Python prompt, open your terminal and type `python` at the `$`. You're in the right place when you see `>>>`.

Try these commands in order:

```pycon
>>> x = 5
>>> x
5
>>> x + 10
15
>>> y = "hello"
>>> y
'hello'
>>> y + " and goodbye"
'hello and goodbye'
```

As you can see above, the `=` sign lets you assign symbols like `x` and `y` to data.

Variables can be longer words as well:

```pycon
>>> breakfast = ['ham', 'eggs', 'toast']
>>> breakfast
['ham', 'eggs', 'toast']
>>> type(breakfast)
<class 'list'>
```

Variables can have letters, numbers, and underscores, **but should start with a letter**.

## Challenge

So I just told you that variables shouldn't start with a number or an underscore. What does that even mean? Will your computer explode if you write `3_flower = "buttercup"`?

Only one way to find out. Try giving weird names to variables and see if you can learn a bit about the rules.

---

# Running scripts

So far, you've interacted with Python one line at a time in the REPL. For the rest of this session, we're going to write and execute longer programs.

## Your first script

Open your text editor of choice (such as VS Code) and create a new file with this line:

```python
print("Hello world!")
```

Save it with the name `hello.py` to a known location, such as your desktop. Open your terminal and move to the desktop directory:

```console
$ cd Desktop
```

Once you're in the folder with your `hello.py` file, run it with:

```console
$ python hello.py
Hello world!
```

As above, you should see the text `Hello world!` appear as output. We needed the `print()` function here because, unlike in the REPL, things aren't automatically printed out when writing scripts.

Congratulations! You've written your first script. That's kind of a big deal.

## Challenges

1. Rewrite your program so that you assign the message to a variable, then print the variable. This will make your program two lines instead of one. There's a fancy programmer word for rewriting your code without changing its behavior—"refactoring."

2. (optional) Are you already getting sick of typing `python hello.py` again and again? Try typing `!!` in the command line (the `$`). This will run your last line of code again.


## A Note on Text

Fundamentally, Python programs are just text files. You can write them in any text editor, like VS Code or gedit on Ubuntu. When you pass the text file to Python, it runs the code in the file one line at a time. There's nothing special about `.py` files—they're just regular text files. This makes them work well with command line tools like Git. The tools you've learned so far—the command line, Git, markdown, grep—are all designed to work well together, and the medium through which they all work is plain text.

---

# Errors in Python

Our usual response when seeing an error on a computer screen is a stress response. Our heart rate elevates and, if we cannot do what we were asking the computer to do, our frustration mounts. This is because many errors when interacting with programs are not useful or informative, and because we often have no capability to fix the program in front of us.

In Python, errors are our friends. This might be hard to accept initially, but the errors you see when running Python scripts generally do a good job of pointing you to what's going wrong in your program. When you see an error in Python, therefore, try not to fall into the stress response you may be used to when interacting with your computer normally.

## Two kinds of errors

In Python, there are two kinds of errors you will encounter frequently. One appears before the program runs, and the other appears during the execution of a program.

**syntax errors** - When you ask Python to run a program or execute a line in the REPL, it will first check to see if the program is valid Python code—that is, that it follows the grammatical or syntactical rules of Python. If it doesn't, before the program even runs, you'll see a syntax error printed out to the screen.

In this below example, the syntax error is a common one—mismatched single and double quotes, which is not allowed in Python. You can replicate the below error by opening the REPL (type `python` in the command line) and entering the line after the `>>>` prompt.

```pycon
>>> print('This string has mismatched quotes. But Python will help us figure out this bug.")
  File "<stdin>", line 1
    print('This string has mismatched quotes. But Python will help us figure out this bug.")
                                                                                           ^
SyntaxError: EOL while scanning string literal
```

Note the caret (`^`) underneath the mismatched quote, helpfully pointing out where the error lies. Similarly, if this error happened when running a script, Python would tell us the filename and the line number for the line on which the error occurs.

**Traceback errors** - These errors occur during the execution of a Python program when the program finds itself in an untenable state and must stop. Traceback errors are often logical inconsistencies in a program that is valid Python code. A common traceback error is referring to a variable that hasn't been defined, as below.

```pycon
>>> print(not_a_variable)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name 'not_a_variable' is not defined
```

Traceback errors try to tell you a little about what happened in the program that caused the problem, including the category of error, such as `NameError` or `TypeError`.

## Debugging

Debugging is a fancy word for fixing problems with a program. Here are some common strategies for debugging a program when first learning Python:

- If the error is a syntax error, look at where the caret is pointing.
- If the error is a syntax error, pay attention to grammatical features such as quotes, parentheses, and indentation.
- If the error is a syntax error, consider reading the program, or the offending line, backward. It's surprising, but this often helps to detect the issue.
- If the error is a traceback error, first look at the line where the error occured, then consider the general category of error. What could have gone wrong?
- If the error is a name error (NameError), check your spelling.
- If the error is a traceback error and you have an internet connection, try copying the last line of the error and pasting it into Google. You'll often find a quick solution this way.
- If you changed the program and expect a different output, but are getting old output, you may not have saved the file. Go back and make sure the file has been correctly saved.

## Challenge

Try to create as many errors as you can in the next few minutes. After getting your first two syntax errors, try instead to get traceback errors. Some areas to try include mathematical impossibilities and using math operations on types that do not support them.

---

# Lists and Loops

## Lists

Remember lists? They look like this:

```python
flowers = ['rose', 'violet', 'buttercup']
```

For now, let's just create a list and print it out. In a text editor, our script will look like this:

```python
flowers = ['rose', 'violet', 'buttercup']
print(flowers)
```

Save this to a new file called `loop.py` and run it with `python loop.py`. You should see the list printed out in the terminal.

So far, we've only learned one function: `type()`. Let's try out another:

```python
flowers = ['rose', 'violet', 'buttercup']
# print(flowers)

list_length = len(flowers)

print(list_length)
```

The `len()` function returns the number of items in a list or the number of characters in a string.

Notice that, if you run the code above, you won't see the `flowers` list printed out. That's because that line has become a comment. If you put a `#` (hash or pound) at the beginning of a line, that line will be ignored.

# List Indexing

A useful property of a list is the list index. This allows you to pick out an item from within the list by a number starting from zero:

```python
print(flowers[0]) # rose
print(flowers[1]) # violet
```

Note that the first item in the list is item [0]. The second item is item [1]. That's because counting in Python, and in almost all programming languages, starts from 0.

You can print out the last item in a list using negative numbers:

```python
print(flowers[-1]) # buttercup
```

## Loops

What if we want to print out each item in the list separately? For that, we'll need something called a loop:

```python
flowers = ['rose', 'violet', 'buttercup']
# print(flowers)

for flower in flowers:
    print("My favorite flower is the " + flower)
```

What's happening here? This kind of loop is called a "for" loop, and tells Python: "for each item in the list, do something." Let's break it down:

```
for <variable name> in <list name>:
	<do something>
```

Indented code like this is known as a "code block." Python will run the `<do something>` code in the code block once for each item in the list. You can also refer to `<variable name>` in the `<do something>` block.

You can also perform more complicated operations. Let's tackle one in a challenge.

## Challenge

Here's a list of numbers:

```python
prime_numbers = [2, 3, 5, 7, 11]
```

Write some code to print out the square of each of these numbers. Remember that the square of a number is that number times itself. The solution is in the footnote[^1], but you're not allowed to look at it until you've tried to solve it yourself for 3.5 minutes. (Seriously! That's 210 seconds.)

[^1]: prime_numbers = [2, 3, 5, 7, 11]
  for num in prime_numbers:
  print(num * num)


## A Note on Variable Names

In this section, we've discussed flowers in the context of a list. But would a variable by any other name smell as sweet?

Why do we use the variable name `flowers` in this section for our list of flower names? Why not just use the variable name `x`, or perhaps `f`?

While the computer might not care if our list of flowers is called `x`, giving variables meaningful names makes a program considerably easier to read than it would be otherwise. Consider this for loop:

```python
y = ['rose', 'violet', 'buttercup']

for x in y:
    print(x)
```

Which is easier to read, this for loop or the one used in the example?

When variable names accurately reflect what they represent, and are therefore meaningful, we call them "semantic." Always try to create semantic variable names whenever possible.

---


# Conditionals

Conditionals allow programs to change their behavior based on whether some statement is true or false. Let's try this out by writing a script that will give different outputs based on the weather:

```python
weather = "sunny"

if weather == "sunny":
    print("Bring your shades")
else:
    print("I don't know what you should bring! I'm just a little program...")
```

In our first line, we set a variable `weather`  to the string "sunny," representing what the weather is like outside. The `if` statement checks whether the variable weather is set to "sunny." If it is, the code in the block beneath is executed, so the text "Bring your shades" will be printed.

The `else` statement handles any inputs that aren't "sunny"—the program merely prints out that it doesn't know what you should bring. Try this script out both with the variable set to "sunny" and the variable set to some other value.

What if we want our program to handle other kinds of weather, giving different messages for each one? Other cases after the first `if` statement are handled with `elif`:

```python
weather = "sunny"

if weather == "sunny":
    print("Bring your shades")
elif weather == "rainy":
    print("Bring your umbrella")
elif weather == "snowy":
    print("Bring your wooly muffler")
else:
    print("I don't know what you should bring! I'm just a little program...")
```

You can add as many `elif` statements as you need, meaning that conditionals in Python have one `if` statement, any number of `elif` statements, and one `else` statement that catches any input not covered by `if` or `elif`. Over the next sections, we'll work on improving this little application, making it able to handle user input directly.

## Challenge

Add two more `elif` statements to this program to make it better able to handle different kinds of weather.

---

# Input

Python allows you to take input directly from the user using the `input` function. Let's use it to improve our weather application by asking for the weather before displaying the output.

```python
weather = input("What is the weather like today? ")

if weather == "sunny":
    print("Bring your shades")
elif weather == "rainy":
    print("Bring your umbrella")
elif weather == "snowy":
    print("Bring your wooly muffler")
else:
    print("I don't know what you should bring! I'm just a little program...")
```

When you run this program, Python should ask you for some input with the prompt `What is the weather like today?` (The space before the second `"` makes the prompt look more tidy in the console.) It will then return some advice based on the input. Try running it now.

## Asking repeatedly

What if we want Python to keep asking for input instead of exiting after the first question is answered? For that, we can use something called a while loop.

Remember our for loop? Instead of iterating through a list like the for loop, our while loop will continue to execute as long as a certain condition is true. Here's a very simple while loop that will run forever until you quit it manually.

```python
while True:
    print("Oh no! I'm stuck...")
```

In the terminal, you can escape from this endless loop by pressing `Control-c` on your keyboard.

Let's apply the while loop to our weather app:

```python
while True:
    weather = input("What is the weather like today? ")

    if weather == "sunny":
        print("Bring your shades")
    elif weather == "rainy":
        print("Bring your umbrella")
    elif weather == "snowy":
        print("Bring your wooly muffler")
    else:
        print("I don't know what you should bring! I'm just a little program...")
```

Notice that we had to shift everything over one tab to fit it in the `while` block. Now our program will ask us for input again and again, and give us different answers each time.

Let's add one more feature: an `elif` statement that will break us out of the loop and end the program:

```python
while True:
    weather = input("What is the weather like today? ")

    if weather == "sunny":
        print("Bring your shades")
    elif weather == "quit":
        break
    elif weather == "rainy":
        print("Bring your umbrella")
    elif weather == "snowy":
        print("Bring your wooly muffler")
    else:
        print("I don't know what you should bring! I'm just a little program...")
```

The `break` command ends the current loop early, ending the program when "quit" is given as input.

## Challenge

How much of the code above do you understand? Even if you do kind of understand it, do you *really* understand it?

Open up your REPL (type `python` at the `$` prompt). Play around with `input()` a bit until you understand it's behavior really well. Write a two-line program in the REPL or in a script that takes some input and echoes it back to the user.

Alternatively, mess around with `while`. Try using things other than `True` and see if the code in the loop runs. If you can, write a while loop that prints out the numbers from 1 to 10 and stops.

---

# Case sensitivity

Our weather app is working pretty well, but you may have noticed that it's case sensitive:

```
What is the weather like today? snowy
Bring your wooly muffler
What is the weather like today? SNOWY
I don't know what you should bring! I'm just a little program...
```

How could we fix our program to handle cases like this? We could add a bunch of new `elif` statements, like this:

```python
...
elif weather == "snowy":
    print("Bring your wooly muffler")
elif weather == "SNOWY":
    print("Bring your wooly muffler")
...
```

This is a lot of work, and it's a pretty ugly solution. If we wanted to add more cases to our program, we would have to write them in twice every time, and it still wouldn't fix inputs like `Snowy`. The best way to improve our program would be to convert the input to lower case before we send it to our `if/else` block.

Try to figure it out for yourself for two minutes without looking at the answer.

Now look at the answer[^2].

[^2]: s = "Kilometer"
  print(s.lower())

---

## Implementing our answer

According to this answer, we can make a string lowercase by adding `.lower()` to the end of it, like this:

```pycon
>>> "SNOWY".lower()
'snowy'
```

OK, that seems to work, even if we don't really know what's going on with that dot. Let's incorporate this transformation into our weather app:

```python
while True:
    weather = input("What is the weather like today? ")
    weather = weather.lower()

    if weather == "sunny":
        print("Bring your shades")
    elif weather == "quit":
        break
    elif weather == "rainy":
        print("Bring your umbrella")
    elif weather == "snowy":
        print("Bring your wooly muffler")
    else:
        print("I don't know what you should bring! I'm just a little program...")
```

This new script should handle any combination of upper or lowercase characters. The new second line sets the weather variable to a new value, `weather.lower()`, which is a lowercase version of the original input.

---

# A Little Motivation

Early on, we learned a bit about lists, which look like this:

```python
['rose', 'violet', 'buttercup']
```

We're going to create a small application that will print a random motivational saying every time a user presses `Enter`. Our first step will be to create a list of positive sayings:

```python
motivational_phrases = [
        "Importing modules is easy!",
        "Programming! Yay!",
        "You write lists like a pro!",
    ]
```

Lists open with a square bracket `[`, have items seperated with commas, and end with a square bracket `]`, like this:

```python
[1, 2, 3, 4, 5]
```

Our positivity list above spreads the list out over multiple lines for greater readability, which is allowed in Python. Remember that you can change the strings in the list to whatever phrases you choose.

## Importing a module

Now that we have our sayings, let's use it in conjunction with some functionality from a module that's built into Python: the `random` module.

```python
import random

motivational_phrases = [
        "Importing modules is easy!",
        "Programming! Yay!",
        "You write lists like a pro!",
    ]

print(random.choice(motivational_phrases))
```

The `random.choice` function chooses a random item from a list and returns it. The `.` syntax indicates that the function is coming from the `random` library.

The real point of this section is to learn `import`, which is where Python really starts to get interesting. Python comes with many libraries (importable collections of code), and you can install many more. Think of something you're interested in doing (statistics, text analysis, web scraping, quantitative analysis, processing Excel/PDF/image files) and ask the instructor to search google for the "\<thing you're interested in> python library" and tell you in the next class what they found. You're almost certain to find some useful results.


---


# Objects in Python

Objects in Python (and other programming languages) are basically containers that can hold data and/or functions inside them. When a function is inside an object, we usually call the function a "method." When data is inside an object, we usually call it an "attribute." The terminology isn't that important, though. What we do need to know is that you can access these "methods" and "attributes" with a `.` (a dot or period).

When we added lower case to our weather program, we briefly saw a method contained inside all string objects in Python—`lower()`, which makes the string lower case.

```pycon
>>> loud_greeting = "HELLO!"
>>> loud_greeting.lower()
'hello!'
```

Many, or most, objects in Python have methods that allow you to use them in different ways. As you move into using more advanced libraries, you'll find that understanding what methods are available becomes more important.

## Examining Objects

When you encounter an object, how can you learn its methods and atributes so you can use them? There are two main ways. The first, and likely the most practical, is to read the documentation of the library you're using.

However, you can also use the `dir()` function, which will tell you which methods and attributes are available in an object.

Let's use the REPL for a moment—open it by typing `python` at the command line.

```pycon
>>> s = 'Hello, world!'
>>> dir(s)
['__add__', '__class__', '__contains__', '__delattr__', '__dir__', '__doc__',
...
'startswith', 'strip', 'swapcase', 'title', 'translate', 'upper', 'zfill']
```

The above output shows all the methods and attributes available to Python strings that can be accessed using the dot (`.`) syntax. When using `dir()`, you'll mostly want to ignore the methods and attributes that have underscores around them. They mainly have to do with the internals of the Python language.

## Challenge

1. You can also use `dir()` to see what functions are available from Python libraries that you import. Try importing the random library again and see what you get when you enter `dir(random)`.

2. Try entering other objects based on Python types we've already learned to the `dir()` function. For example, you might try `dir([1, 2, 3])` to see what methods are available when using lists.

---

# Python resources

If you want to read a book about Python ask the instructor to bring in one of these:

[Learn Python the Hard Way](http://learnpythonthehardway.org/book/) - An example-driven introduction to Python.

[How to Think Like a Computer Scientist - Python Edition](https://runestone.academy/runestone/static/thinkcspy/index.html) - A good intro if you're also interested in learning basic computer science concepts.

[Automate the Boring Stuff with Python](https://automatetheboringstuff.com/) - A fun book that teaches Python while automating some common (and annoying) tasks.

---

## Endnote

Well done! You have completed all the technical skills sessions. You learned how to use the command line, use Git for version control, HTML and CSS, Jekyll and Python. What an achievement. Now you are ready to hack!

---

[Home](/intro-to-dh/index)

---

**Answers**
