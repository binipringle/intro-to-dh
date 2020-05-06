---
layout: narrative
title: Teaching notes
author:
editor: Sabina Pringle
rights:
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

These notes are mainly to keep track of where things are. Some resources will be on the external hard drive, others in student USB flash drives, and others will be printed on paper and physically given to students.

If I were teaching this course I would assign one laptop and one USB flash drive per student for the duration of the whole course. USB flash drives will need to be kept securely with the laptops. No students should take their USB flash drives out of the classroom. I would have students sign a document acknowledging receipt of their assigned USB flash drive and their assigned laptop at the beginning of the course, so as to give them ownership over the devices and hold them accountable for any damage or loss that might occur to these. It is a good idea to have a few unassigned USB flash drives in case any become damaged or get erased.

Most of the resources for technical skills sessions are on this course site in each tutorial session. These are not listed here. Other resources which are too large or too fiddly to put on the course site will be in clearly named folders on all the USB flash drives, or maybe on an external hard drive. The resources on USB flash drives or an external hard drive are listed here.

# Command line session

## Notes

At some point towards the end of this session (or in a later session), it could be a nice idea to ask students to change the sudo username on the laptops they were assigned. To change username:

  sudo usermod -l newUsername oldUsername

This however, doesn't rename the home folder. To change home-folder, use

  sudo usermod -d /home/newHomeDir -m newUsername

after you changed the username.

# Resources for command line session

On student USB:

- nypl_items.csv

# Intro to git session

This course is designed to be taught in a prison with no internet connection. Therefore, students will not be able to house repositories on GitHub or push and pull their work to and from there. However, they can still use Git for version control when working on collaborative projects by putting using a USB stick to exchange and update local repositories.

The basic steps are:

- Mount the USB stick on a pre-determined path
- Setup a bare repository in the USB stick
- Add the repository in the USB stick as a remote

Students will be able to clone repositories from the USB stick and push and pull contributions to repositories on the USB stick. I would absolutely set up a remote repository on the USB stick before the course starts, because it's a bit fiddly. To mount a USB stick and set it up to act as a remote, I followed this Wikibooks step-by=step guide: <a href="https://en.wikibooks.org/wiki/Git/Repository_on_a_USB_stick">Git/Repository on a USB stick</a>
