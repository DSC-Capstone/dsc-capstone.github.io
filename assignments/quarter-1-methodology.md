---
layout: page
title: Methodology Assignments
doodle: /assets/images/doodle.png
---

---
* TOC
{:toc}

---

## Assignment 1

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
4. On the jump-box server, run the command `echo ~ > homedir.txt`.
5. Launch a container using the script `launch-scipy-ml.sh`. Change
   directories back into your repository and run
   the command `uname -a > uname-container.txt`.
6. Open a Jupyter Notebook from the URL given on the container's
   welcome screen. Copy this url [URL] and run the command `echo
   [URL] > notebook-url.txt`. This should create a file
   `notebook-url.txt` with the url inside it. You can test this by
   typing `cat notebook-url.txt` after you've created the file.
7. Commit and push your changes to GitHub; submit to Gradescope.
   

---

## Assignment 2

Review the last portion of Lecture 3 on 'Structuring a Project' and
create the project structure for your result replication project.

* create a private GitHub repository with the directories/files
  discussed in lecture: `src`, `notebooks`, `config`, `references`,
  `run.py`, `.gitignore`, `README.md`. 
* Create 'stub files' in the directories as placeholders, as
  well. Stub files can be empty, but should have the correct
  extensions. For example, if a directory will inevitibly have python
  source code, place an empty file in the directory called `stub.py`.
* Your `.gitignore` file should have appropriate content.

You may find [this
repository](https://github.com/DSC-Capstone/project-templates) useful,
as an example.

---

## Assignment 3

### Docker

What is Docker? Go check the lecture slides for a formal definition
and details as you work through this assignment.

But to put in very easy to understand terms, Docker is the solution to
the following problem: "Incompatible library version: whoops.so
requires version a.b.c or later, but you currently have version x.y.z"
And when you fix that something some other application breaks! Now,
[virtualenv](https://docs.python.org/3/library/venv.html) does solve
this problem for python packages but docker takes to the next level.

Docker provides you a sandbox (separate environment for running your
applications without breaking other stuff) and not just python
applications.

Now that we understand why we need docker, let's see how to use it!

The sandbox I just mentioned is nothing but a 'container'. Using
docker you spin up a container which has all the dependencies that you
require for your application. Every container is ephemeral, meaning as
soon as you close the container, you lose the changes. So how do we
retain the changes?

You can take a snapshot of the container and commit that, which saves all
the changes that you made to the container. This snapshot is called an
image.  This snapshot is generally several GBs depending on the
software installed.

How do you spin-up a container? Using an image.

How do you create an image? This can be done in two ways:
* Using Dockerfile
* By saving the changes to an already created container.

Both of these are covered in detail (with references) in lecture.

### Dockerfiles
What is a Dockerfile? It is a text file containing specifications
which tells docker what software to include to build the
image.  As you can understand, it is easier to share a dockerfile
from which anyone can build an image than share the image itself.

After completing this assignment, you should be able to:
1. Create a dockerfile with required specifications.
2. Use that dockerfile to build an image.

### Creating a Dockerfile
Generally, you don't need to create every dockerfile from
scratch. Instead, you build on existing images and add stuff that you
need.  In this assignment, we will use `ucsdets/datascience-notebook:2021.2-stable` as our base
image and add a couple of software libraries that we need on top of that.

So, let's start with an image from datahub/dsmlp and see what is
already there in this image. Create an account on
[Dockerhub](https://hub.docker.com) and open
[this](https://hub.docker.com/r/ucsdets/datahub-base-notebook). If you see
the overview you will see a very long list of stuff that is already
present in this image. Now, to the `Dockerfile` tab and give that a
read. You will see that only a very small subset of the libraries are
installed in the image. That is because this image is build on top of
another image, `jupyter/datascience-notebook:python-3.7.6` which already has
most the dependencies.

We are going to create our own Dockerfile, inspired from this one, and
add a couple of libraries.

### Task 1: Write a Dockerfile
Create a Dockerfile using `ucsdets/datascience-notebook:2021.2-stable` as your base image and
then add the following libraries using linux's package manager
`apt-get`:
* [aria2](https://aria2.github.io/)
* [nmap](https://nmap.org/)
* [traceroute](https://en.wikipedia.org/wiki/Traceroute)

And add the following libraries with `conda` or `pip`:
* [geopandas](https://geopandas.org/)
* [babypandas](https://github.com/babypandas-dev/babypandas)

Note 1: There is nothing special about these libraries; we merely need
you to download something!

Note 2: The examples of Dockerfiles on the last few slides of lecture,
along with [this
tutorial](https://github.com/ucsd-ets/datahub-example-notebook)
referred to in lecture, should get you through these steps!

### Task 2: Build a Docker Image

Create an image and launch a container using the Dockerfile and verify
if all the softwares are present.

Note: testing locally on your laptop will involve pulling ~5GB of
data (an entire OS) the first time you build the image. Subsequent
times will be much faster! If you cannot install Docker on your
laptop, you can skip to step 3; however, debugging may be more difficult.

### Task 3: Pull a Docker Image 

Push the image to DockerHub and launch a pod on dsmlp server using
this image.  Test out your environment on the pod (can you start
python and import `babypandas`?)

### Turn in your work

* ~~Launch a pod using your Docker Image (as in step 3) and run the
  following command: `bash /datasets/dsc180-fa20-grading-tmp/method4-grader.sh`~~
* Go to gradescope and turn in both the image name and the Dockerfile. We will pull the image and test if requirements are met.

---

## Assignment 4

In this assignment, you will start thinking of ideas for your Capstone
project proposal. Please write a few sentence on each of the prompts below:

1. The most interesting topic covered in your domain this quarter?
2. Describe a potential investigation you would like to do for a
   project proposal?
3. What is a potential change you would like to make to the approach
   taken in your current Q1 project?
4. What other techniques/methods would you be interested in using in
   your project?

Answers to these questions will be circulated among your domain
(anonymously); reading others work will be helpful in thinking about
possible project.

**Note:** If you are in a domain where the projects are already
determined, this will still be a useful exercise. Do not just answer
with the project you think you are doing; give the questions thought
and respond with possible related project (e.g. if you get to go
further than expected with your current project, or if your currrent
project doesn't pan out). 

Developing your own topic of investigation is an important skill that
Data Scientist's must have!

---

## Assignment 5

In this assignment, you will get your Q1-project code working with
test data and implement a the standard target `test`.

1. Create test data, in `<projectdir>/test/testdata/`, according to
   the lecture. For this assignment, you only need to create the bare
   minimum of data so that your code builds the project
   successfully. Your test data should be in the format that most
   closely resembles "raw" data that your project may use (if you use
   an API to access data, copy the format of the data queried from the
   API).
2. Implement the target `test` in `run.py` that runs all your targets
   on the test data you created. (Since your project isn't finished,
   it should build the output your project creates, as it currently
   exists).

Turn in your code to gradescope (this will be your project
repository. In this submission, include a `submission.json`
file in the root directory of your repository that contains your
dockerhub repository (The format should be `<user>/<image>:<tag>`. The
default `<tag>` is `:latest` if you don't supply it).

```
{
    "dockerhub-id": "<user>/<image>:<tag>",
    "build-script": "<command>
}
```

Your submission will be run on DSMLP: 
* A container will be started using the command `launch.sh -i
<user>/<image>:<tag>` using the docker image information in
`submission-methodology.json`.
* Once in the container, the 'build-script' command will be run.

For example, a `submission-methodology.json` file might look like:
```
{
    "dockerhub-id": "amfraenkel/fair-policing-project",
    "build-script": "python run.py"
}
```

And the following commands would be run on DSMLP:
* `launch.sh -i amfraenkel/fair-policing-project`
* `python run.py test`


As this assignment encourages you to get your project-build in order
early, there will be tests that don't depend on your build to run.

*Note:* This assignment should readily apply to all domains. 
* Data-centered domains start with collected data (that you will model
  your test data after).
* Methods domains are building algorithms that take data as input. You
  should choose a data type that your algorithm may input and use that
  to model your test data.

*Note:* As with every methodology assignment, you should work on this
individually (discuss with your partner, but code the solution
separately). Once the assignment is turned in, you can use both your
test data.
