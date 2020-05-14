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
- Other thoughts

---

These notes are mainly to keep track of where things are.

Most of the resources for technical skills sessions are on this site. Other resources which are too large to be housed on this site or incompatible with Ruby are listed here. They can be stored on a USB or an external hard drive and taken into prison by the instructor. Resources required for technical skills sessions but not on this site are listed here. Some ideas and thoughts are noted here too.

# Command line session

## Notes

It might be a nice idea to ask students to change the sudo (superuser) username on the laptops they are assigned. To change username:

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

Git can be used for version control of collaborative projects without the internet by initializing Git in a repository on a USB stick and using the USB stick to exchange and update local repositories. The idea is to use USB sticks as a sneakernet version of GitHub. I am really excited about this but I need to experiment with it some more before I can explain how to do it.

The basic steps are:

- Mount the USB stick on a pre-determined path (this is where I'm stuck right now)
- Setup a bare repository in the USB stick
- Add the repository in the USB stick as a remote

Students will be able to clone repositories from the USB stick and push and pull contributions to repositories on the USB stick. I would absolutely set up a remote repository on all the USB sticks (assuming that the students will be allowed to use USB sticks) before the course starts.

---

# Other thoughts

I want to see how a Flask App could work as a blog. I built a Flask App following Michael Grinburg's [Flask Mega-Tutorial](https://blog.miguelgrinberg.com/post/the-flask-mega-tutorial-part-i-hello-world) and had a really good time doing this, and I think it could work well. I hope to make time to experiment with this over the summer.

I also look forward to seeing how Alex Gil and Dennis Tenen's [No Connect](https://github.com/xpmethod/no-connect) could be used by students to build their own Jekyll sites.  

---
