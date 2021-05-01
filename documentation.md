---
layout: page
title: Documentation
author: Sabina Pringle
editor: Sabina Pringle
rights: CC Attribution-ShareAlike 4.0 International License
source: DH in Prison
toc:
- Make a copy of this site
- Note on adding images
- Note on adding licenses
- Preparing student laptops for using Intro to DH
- Installing Ubuntu
- Installing Git
- Finding the Text Editor
- Installing Python
- Installing Jekyll

---

This is a static site built with Jekyll using [Ed](https://elotroalex.github.io/ed/).

## To make a copy of this site and run it on your computer:

You will need to use your terminal. If you don't remember much about how to use your terminal, I recommend "[Introduction to the Command Line](https://github.com/GC-DRI/command-line)."

## Once you are in your terminal, first try the "easy" or "lucky" way to install:

Go into your Desktop or wherever you want your copy of this site.

Now type or paste the following commands:

~~~ bash
$ git clone https://github.com/binipringle/intro-to-dh.git
$ cd intro-to-dh
$ gem install bundler
$ bundle install
~~~

Done! To see if Intro to DH is working properly, tell Jekyll to serve it by typing

~~~ bash
$ jekyll serve
~~~

If the site was rendered, copy the url from your terminal log and paste it into your browser (my preference is Firefox). This url usually looks something like this `http://127.0.0.1:4000/dh-in-prison`. Now you should be looking at your own working version of Intro to DH, served from your computer without relying on the internet.

## If the site did not render:

And you had errors you could not resolve, follow the installation instructions in the [Ed documentation](https://elotroalex.github.io/ed/documentation/), replacing "ed" with "intro-to-dh" wherever necessary. Ed is the Jekyll theme that I used to build Intro to DH, so once you have cloned Intro to DH onto your computer, if you run into issues when making changes to Intro to DH, I recommend looking to the [Ed documentation](https://elotroalex.github.io/ed/documentation/) for help.

## Note on adding images

In order to render images, I added the following code to the **_config.yml** file:

```
defaults:
  - scope:
      path: "assets/img"
    values:
      image: true
```

I enabled responsiveness on mobile devices in the following line in the **_ed.scss** file:

```
<meta name="viewport" content="width=device-width,initial-scale=1.0,shrink-to-fit=yes" />
```

## Note on adding licenses

Because the logo, illustrations and some texts on this site are distributed with different licenses, I created folders for collections and put a copy of the pertinent license in that folder in a LICENSE.md file. I added the text of this CC BY-NC-SA 4.0 license CC and the text of the CC BY-SA 4.0 which my work and the GCDRI and GC DHRI work are licensed with, to the MIT License which Ed is licensed with in the LICENSE.md folder at the top level of the repository.

---

# Preparing student laptops for using Intro to DH

Although the technical skills sessions should work on most operating systems such as Windows and Mac OS, they have been adapted to be used on Ubuntu, the free open source operating system. Ubuntu therefore needs to be installed on all student and instructor laptops. **When you install Ubuntu on a laptop you will erase the operating system that was there before**. When you are ready to set up student laptops, installing Ubuntu is the first thing you should do.

# Installing Ubuntu

To install Ubuntu, follow this [easy tutorial](https://ubuntu.com/tutorials/tutorial-install-ubuntu-desktop#1-overview) to replace the current operating system with Ubuntu. In **step 5**, choose **normal installation**. In **step 6**, choose **Erase disk and install Ubuntu**. You will need a USB stick.

---

# Installing Git

Ubuntu comes with Git. However, before you start using Git, you have to make it available on your computer.

First, use the apt package management tools to update your local package index. With the update complete, you can install Git:

~~~ bash
$ sudo apt update
$ sudo apt install git
~~~

You can confirm that Git is installed by typing

~~~ bash
$ git --version
~~~

Output should be

```
git version 2.20.1
```

You may want to update to the latest version. If so, see the [Ubuntu Documentation Community Help Wiki for Git](https://help.ubuntu.com/community/Git) for instructions on how to do this.

---

# Finding the Text Editor

Ubuntu comes with Visual Studio Code, or VS Code, so you will have installed it when you installed Ubuntu and should see it in your GUI. If you want to check which version you have, type

~~~ bash
$ code -v
~~~

You should see something like this:

```
1.45.0
d69a793808559a91206d73d7717ff5f798f23c
x64
```

If you need to reinstall or update VS Code follow the steps in [Downloading VS Code for Linux](https://code.visualstudio.com/docs/?dv=linux64_deb).

---

# Installing Python

I recommend that you install Python with Anaconda. To do this, navigate to the [Anaconda documentation for installing on Linux](https://docs.anaconda.com/anaconda/install/linux/).

Here, you will first be directed to install the following extended dependencies for Qt (you will probably have to write ```sudo``` before the command as I did):

~~~ bash
$ sudo apt-get install libgl1-mesa-glx libegl1-mesa libxrandr2 libxrandr2 libxss1 libxcursor1 libxcomposite1 libasound2 libxi6 libxtst6
~~~

Next, download the Anaconda installer for Linux. Click on **Download**, scroll to the bottom and choose the **Linux Python 3.7 64-bit (x86) Installer (522 MB)**.

Now it gets a bit confusing because instead of installing Python by double-clicking on the file you just downloaded or by dragging and dropping it into your Applications folder like we are used to doing on Mac OS or Windows, you have to install it from the command line.

Follow the steps in the Anaconda documentation very carefully. Anaconda recommends that before you install, you verify the data integrity of the Anaconda installer hash (Anaconda walks you through how to do this).

To install Python with Anaconda, I typed two commands. The first gave me an error but I executed the second command anyway and it worked.

First command (this gave me an error):

~~~ bash
$ sha256sum /Downloads/Anaconda3-2020.02-Linux-x86_64.sh
~~~

Second command (this worked like magic):

~~~ bash
$ bash ~/Downloads/Anaconda3-2020.02-Linux-x86_64.sh
~~~

If everything went well, you should now see Anaconda install Python 3.7 on your computer. When it has finished installing, type

~~~ bash
$ python --version
~~~

You should see this:

```
Python 3.7.6
```

Yippee (unless you got errors). If you got errors, see the [Anaconda troubleshooting guide](https://docs.anaconda.com/anaconda/user-guide/troubleshooting/).

---   

# Installing Jekyll

Jekyll is a static site generator written in Ruby. Ruby should already be installed because it is installed with Ubuntu. To check, type

~~~ bash
$ ruby -v
~~~

Output should be something like this:

```
ruby 2.6.3p62 (2019-04-16 revision 67580) [x86_64-linux]
```

If for some reason Ruby is not installed, type

~~~ bash
$ sudo apt-get install ruby-full
~~~

Now you should be good to go and ready to install Jekyll.

To install Jekyll, follow its clear and easy guide to [install Jekyll on Ubuntu](https://jekyllrb.com/docs/installation/ubuntu/). When this is done, to see that it is installed, type

~~~ bash
$ jekyll -v
~~~

Output should be something like

```
jekyll 4.0.0
```
Now that you have installed Ubuntu, Git, VS Code, Python and Jekyll, the laptops are ready to go! Have fun!

---
