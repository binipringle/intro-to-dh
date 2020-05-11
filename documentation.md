---
layout: page
title: Documentation
author: Alex Gil
---

This is a static site built with Jekyll using [Ed](https://elotroalex.github.io/ed/).

### To make a copy of this site and run it on your computer:

You will need to use your terminal. If you don't remember much about how to use your terminal, I recommend "[Introduction to the Command Line](https://github.com/GC-DRI/command-line)."

### Once you are in your terminal, first try the "easy" or "lucky" way to install:

Go into your Desktop or wherever you want your copy of this site.

Now type or paste the following commands:

~~~ bash
$ git clone https://github.com/binipringle/intro-to-dh.git
$ cd intro-to-dh
$ gem install bundler
$ bundle install
~~~

Done! To see if Intro to DH is working properly, tell Jekyll to serve by typing

~~~ bash
$ jekyll serve
~~~

If the site was rendered, copy the url from your terminal log and paste it into your browser (my preference is Firefox). This url usually looks something like this `http://127.0.0.1:4000/dh-in-prison`. Now you should be looking at your own working version of Intro to DH, served from your computer without relying on the internet.

### If the site did not render:

And you had errors you could not resolve, follow the installation instructions in the [Ed documentation](https://elotroalex.github.io/ed/documentation/), replacing "ed" with "intro-to-dh" wherever necessary. Ed is the Jekyll theme that I used to build Intro to DH, so if you run into issues when making changes to Intro to DH, see the [Ed documentation](https://elotroalex.github.io/ed/documentation/).

---

## Setting up laptops so that students can access this course without an internet connection

# Operating system

On each laptop,

1. Install Ubuntu

Follow this [easy tutorial](https://ubuntu.com/tutorials/tutorial-install-ubuntu-desktop#1-overview) to replace the current operating system with Ubuntu. In step 5, choose **normal installation**. In step 6, choose **Erase disk and install Ubuntu**.

---

# Git

2. Install Git

Ubuntu’s default repositories provide you with a fast method to install Git.

First, use the apt package management tools to update your local package index. With the update complete, you can download and install Git:

~~~ bash
$ sudo apt update
$ sudo apt install git
~~~

You can confirm that you have installed Git correctly by running the following command:

~~~ bash
$ git --version
~~~

Output should be

```
git version 2.20.1
```

If you need to update to the latest version of Git, do this:

~~~ bash
$ sudo add-apt-repository -y ppa:git-core/ppa
$ sudo apt-get update
$ sudo apt-get install git -y
~~~
---

# Text Editor

Ubuntu comes with Visual Studio Code, so you will have installed it in step 1 and should see it in your GUI. If you want to check what version you have from the command line, type

~~~ bash
$ code --version
~~~

You should see something like this:

```
1.45.0
d69a793808559a91206d73d7717ff5f798f23c
x64
```

If you need to reinstall or update VS Code follow the steps in [Downloading VS Code for Linux](https://code.visualstudio.com/docs/?dv=linux64_deb).

---

# Python

Go to the Anaconda site.

To install Anaconda on Linux you will first be directed to install the following extended dependencies for Qt (you will probably have to write ```sudo``` before the command):

sudo apt-get install libgl1-mesa-glx libegl1-mesa libxrandr2 libxrandr2 libxss1 libxcursor1 libxcomposite1 libasound2 libxi6 libxtst6

Download the Linux Python 3.7 64-bit (x86) Installer (522 MB).

Now it gets a bit confusing because instead of installing Python by double-clicking on the file you just downloaded or by dragging and dropping it into your Applications folder like I am used to doing on Mac OS or Windows, you have to install it from the command line. Follow the next steps in the instructions in the Anaconda documentation very carefully. Anaconda recommends that before you install, you verify the data integrity of the Anaconda installer hash (Anaconda walks you through how to do this). To install Python with Anaconda, I typed two commands. The first gave me an error but I gave the second command anyway and it worked.

First command (this one gave me an error):

~~~ bash
$ sha256sum /Downloads/Anaconda3-2020.02-Linux-x86_64.sh
~~~

Second command (this one worked like magic):

~~~ bash
$ bash ~/Downloads/Anaconda3-2020.02-Linux-x86_64.sh
~~~

If everything went well, you should now see Anaconda install Python 3.7 on your computer. When it has finished installing, type

~~~ bash
$ python -- version
~~~

You should see this:

```
Python 3.7.6
```

Yippee (unless you got errors). If you got errors, see the Anaconda troubleshooting guide.

---   

# Jekyll
