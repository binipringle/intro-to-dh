---
layout: page
title: Documentation
author: Alex Gil
---

This is a static site built with Jekyll using [Ed](https://elotroalex.github.io/ed/).

### To make a copy of this site and run it on your computer:

You will need to use your terminal. If you don't remember much about how to use your terminal, I recommend "[Introduction to the Command Line](https://github.com/GC-DRI/command-line)."

### Once you are in your terminal, first try the "easy" or "lucky" way to install:

Create a folder in your Desktop where you want your copy of this site. I would call my folder 'projects.' When you have created your folder (or directory), go into it with the cd (change directory) command, like this:


~~~ bash
$ cd Desktop
$ mkdir projects
$ cd projects
~~~

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

And you had errors you could not resolve, follow the installation instructions in the [documentation of Ed](https://elotroalex.github.io/ed/documentation/), replacing "ed" with "intro-to-dh" wherever necessary.

Ed is the Jekyll theme that I used to build Intro to DH, so if what you want to do is to completely change the content of Intro to DH and build your own site with its framework, I strongly recommend that you clone Ed instead and use Ed to build your site because Ed's documentation is way better than mine.

If, on the other hand, you are interested in talking about, contributing to or otherwise getting involved in Intro to DH, see its sibling site [DH in Prison](https://binipringle.github.io/dh-in-prison/) and write to me at springle@ccny.cuny.edu or [https://github.com/binipringle ](https://github.com/binipringle)

---
