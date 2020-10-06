---
layout: page
title: Methodology Assignments
doodle: /doodle.png
---

---
* TOC
{:toc}

---

## Assignment 0

Syllabus Quiz: See Gradescope.

---

## Assignment 1 -- Using the DSMLP Server

Follow the instructions in [Lecture
02](/resources/lecture-notes/Lecture02_Servers.pdf)
and the [documentation](/resources/computing/) to log onto a
configurable campus server (DSMLP).

Note, that in some cases, your username for logging-in may not be your
usual username:

> Students should login to the front-end nodes using either their UCSD
email username (e.g. ‘jsmith’), or in some cases, a “course specific”
account, e.g. “cs253wXX" for CSE253, Winter 2018. Consult the [ITS/ETS
Account Lookup
Tool](https://www.google.com/url?q=https://sdacs.ucsd.edu/~icc/index.php&sa=D&ust=1579049815630000)
for instructions on activating course specific accounts.

### Log-in to the Server

This is a multi-step process:
1. Log into your home directory on a "jump-box server" using `ssh`.
2. Use a launch script (e.g. `launch-scipy-ml.sh`) to start up a
   container (this is a similar to a DataHub instance).
3. Once you've launched you container, follow the URL on the
   container's startup screen to open a Jupyter Notebook. You must be
   on Campus VPN to open the URL (or alternatively, use an 'ssh-tunnel').
   
### To Turn In

1. Create a private repository called DSC180A-Methodology-0

2. Log into the jump-box server and git clone this repository. Then
   change directories into the repository (`cd DSC180A-Methodology-0`).

3. On the jumpbox-server, run the command `uname -a >
   uname-jumpbox.txt` (this gives server info and saves it to a file
   called `uname-jumpbox.txt`.
   
4. On the jump-box server, run the command `echo ~ > homdir.txt`.

5. Launch a container using the script `launch-scipy-ml.sh` and run
   the command `uname -a > uname-container.txt`.

6. Open a Jupyter Notebook from the URL given on the container's
   welcome screen. Copy this url [URL] and run the command `echo
   [URL] > notebook-url.txt`. This should create a file
   `notebook-url.txt` with the url inside it. You can test this by
   typing `cat notebook-url.txt` after you've created the file.
   
7. Commit and push your changes to GitHub; submit to Gradescope.
   

---

## Assignment 2

SW Dev: Organizing your files; templates

---

## Assignment 3

Writing: Analyzing the structure of a scientific paper

---

## Assignment 4

Envs: Dockerfiles

---

## Assignment 5

SW Dev: Code vs Configuration; parameterizing experimennts

---

## Assignment 6

Writing: Effective EDAs

---

## Assignment 7

Envs: Long-running jobs

---

## Assignment 8

Writing: Peer Reviewing Proposals

---

## Assignment 9

Writing: Peer Reviewing Project Schedules


