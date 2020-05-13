---
layout: narrative
title: Teaching notes
author:
editor: Sabina Pringle
rights: Sabina Pringle with a CC Attribution-ShareAlike 4.0 International License.
source:
toc:
- Command line session
- Intro to git session
- Intro to HTML and CSS session
- Intro to Jekyll session
- Intro to Python session
- Accessibility session
- Glossary of technical terms
- Course readings

---

These notes are mainly to keep track of where things are. Some resources will be

Most of the resources for technical skills sessions are on those pages. Other resources which are too large or incompatible with Ruby to be housed on this site are listed here. They can be stored on a USB or an external hard drive and taken to class by the instructor. Resources required for technical skills sessions but not on this site are listed here. Some ideas and thoughts about the course sessions are noted here too.

# Command line session

## Notes

At some point towards the end of the first session (or in a later session), it might be a nice idea to ask students to change the sudo username on the laptops they were assigned. To change username:

~~~ bash
$ sudo usermod -l newUsername oldUsername
~~~

This however, doesn't rename the home folder. To change home-folder, use

~~~ bash
$ sudo usermod -d /home/newHomeDir -m newUsername
~~~

after you changed the username.

# Resources for command line session

On student USB (and in GitHub repo)

- nypl_items.csv

# Intro to Git session

Git can be used for version control of collaborative projects without the internet by initializing Git in a repository on a USB stick and using the USB stick to exchange and update local repositories. The idea is to use USB sticks as a sneakernet version of GitHub.

The basic steps are:

- Mount the USB stick on a pre-determined path
- Setup a bare repository in the USB stick
- Add the repository in the USB stick as a remote

Students will be able to clone repositories from the USB stick and push and pull contributions to repositories on the USB stick. I would absolutely set up a remote repository on the USB stick before the course starts, because doing this is fiddly. To mount a USB stick and set it up to act as a remote, I followed this Wikibooks step-by=step guide: <a href="https://en.wikibooks.org/wiki/Git/Repository_on_a_USB_stick">Git/Repository on a USB stick</a>

---
