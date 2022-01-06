---
layout: page
title: Project Checkpoints
doodle: /assets/images/doodle.png
---

---
* TOC
{:toc}

---

## Mandatory Check-in

This is a mandatory meeting with a TA during week 3. 

Deadlines:
* You must agree on an appointment time with your TA by the end of
  week 2.
* You must submit the write-up for the meeting 24 hours before the
  meeting itself.

Given that you have been working on the project for 3 weeks now, this
check-in is to make sure you that you are making progress in the right
direction, are not stuck anywhere, and on track for your
project checkpoint. Make an appointment with your TA and
discuss the following:

1. A short summary of, and current status of your project
2. Any challenges you might be facing and any questions you have regarding organizing your code.

This is different from your weekly section meetings in the sense that this is more about making sure that your ideas and code are coming together cogently.

Please submit a brief write-up on Canvas:
* Project Github repo link (should be public).
* An abstract of your problem statement (revised proposal)
  1. This can be copied from your proposal.
  2. Idea is to capture things that have changed from what you proposed, which tends to happen once you actually start working on a problem statement.
* Tasks completed till now.
* Current tasks and concerns/issue if any.

## Project Report Checkpoint

The project report checkpoint is an opportunity to get feedback from
your domain mentor. Please check with your mentor on what is required
of the checkpoint for the report.

Requirements for submission:
* The report should be in PDF format (and will likely include all
  sections prior to the results and conclusion).
* The figures in the reports should *not* be created from screenshots:
  - Tables should be imported from csv.
  - Plots should be saved programmatically and imported (or converted
    from a notebook/Rmarkdown).
* Include a copy of your project proposal for reference in the
  appendix of your report (at the end).
* In a comment on the Canvas submission, include the tasks for which
  each group member was responsible.

This assignment is due at the end of week 5 and is graded by your
domain mentor.

## Code Artifact Checkpoint

The code artifact checkpoint will be an initial code review of your
project code artifact at the end of week 5. You will also be required
to meet with a methodology instructor/TA during weeks 3-4 to review
the requirements for this assignment, for a 'mid-checkpoint check-in'.

This checkpoint will check that the code:
1. is well documented and build instructions are found in a
   README.
2. is structured with best-practices in your domain (and in quarter-1
   methodology, where applicable).
3. contains a test target that tests the pipeline on test data, where applicable.
4. runs in a Docker Image on DSMLP, via `python run.py test`.

You will **not** submit your repository. Rather, you will submit a
`submission.json` file to gradescope that includes a link to your
*public GitHub repository* and a link to your *public Dockerhub
repository*.

```
{
    "GitHub Repository": "<github repo url>",
    "DockerHub Repository": "<dockerhub repo url>"
}
```

This is graded by the methodology instructor.

## Visual Presentation Checkpoint

The visual presentation checkpoint requires you to write the technical
scaffolding for your visual output.

You must:
1. Create a live static webpage that contains a skeleton/outline of your
   project webpage. It should contain titles and headers, but does not
   need to contain content (i.e. you should put thought into how your
   webpage is organized).
1. Turn in the code repository URL for the webpage (this is *not* your
   project GitHub repository). It is recommended that you use
   GitHub-Pages as covered in lecture.
1. The `README.md` in the code repository should contain the URL to
   your webpage, which the grader can use to visit your webpage.

This is graded by the methodology instructor and is graded P/NP. To
pass this assignment, you must make reasonable effort at each of the
items listed above.

*Note:* If you are planning on creating a website with a backend, you
still must create a static website explaining your project. This is
the way most people will acquaint themselves with your project. You
should include a prominent link to your interactive webpage from your
static page.

## Presentation Checkpoint

Each group will:
* turn in initial slides for their presentation
* do a dry-run of their presentation with TAs.

This is graded by the methodology instructor against the rubric laid
out in the 'oral presentations' lecture.
