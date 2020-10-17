---
layout: page
title: Domain Mentor Guide
doodle: /assets/images/doodle.png
permalink: /instructor/current/
---

---
* TOC
{:toc}

---

## Preparing for Quarter 1 (Intro to Domain)

The objectives for the first quarter of the Capstone are:
* Introduce students to the area in which they will do their
  project through replicating a known result.
* Create written material and code that serves as a foundation for
  work in quarter-2's projects.
* Closely read 1-2 example papers in the domain to learn
  best-practices for communication in the chosen field.

The most straightfoward way to achieve these objectives is to choose a
result/paper in your field and lightly guide students through that
result. Students then propose projects close to this result.

### Materials needed for preparation

The recommended approach to Quarter 1 requires:
1. Choosing a paper/result around which to structure students'
   introduction to the domain. (While not strictly necessary, having
   known results to replicate helps students know they are on the
   right track).
2. Creating a weekly schedule for the domain to structure student
   learning. Each week should consist of three parts:
   - A list of 1-3 topics they are working on for the week.
   - A reading/task for the week. This is typically "read section XX"
     from the paper and replicate their analysis on your data".
   - A list of 1-3 questions they should answer before
     discussion. These may be conceptual (to test their understanding)
     or a detailed computation of a key figure (to make sure students
     are staying honest). These may be formulated the week before,
     given your current understanding of student progress.

For an example schedule, see the [Malware
Domain](https://afraenkel.github.io/capstone-malware-domain)

### Structuring the Quarter

The schedule follows a reasonable cadence for Quarter 1:

|Topic|Number of Weeks|
|---|---|
|Intro + Data|2-3|
|Methods|2-3|
|Results|2-3|
|Possible Extensions|2-3|
|Elevator Pitch|1|

---

## Running Quarter 1 (Intro to Domain)

For a week-by-week reference of what students will be doing in
lecture and in their assignments, and how this relates to running a
domain, see the [week-by-week guide](/instructor/week-by-week).

### Weekly Discussions

Weekly discussions are not lectures, but rather a time that students
can ask clarifying questions about their weekly reading/tasks. You may
begin by asking students how they approached the questions in the
weekly schedule. Some mentors find it useful to have students submit
their answers to the weekly questions on Canvas *before* discussion,
to help direct discussion.

One piece of advice to encourage participation in discussion is to let
students know that orienting oneself in a new area of research is
difficult and that *it's totally normal to get lost and misunderstand
the material*. Students may be quiet because they're not confident in
the work they've attempted. 

Try to reinforce to students that the purpose of discussion is to get
feedback and guidance from domain mentors. The weekly schedule tries
to facilitate that.

### Office Hours

Office hours should be mandatory for students every ~3 weeks. The main
purpose of office hours are:
1. to provide students with help and guidance on their current work,
2. to provide a meeting time for feedback on submitted work.

You may find it useful to have students make appointments for office hours.

### Assignments

All assignments in the course are "default assignments", suitably
generic for any domain. However, if any assignment does not fit with
your plans for your domain, feel free to adapt the default assignment
for your students.

**Large Assignments:** Quarter 1 consists of two primary assignments
that are largely fixed across all domains:
1. A [result replication](/student/assignments#result-replication), and
2. A [capstone project proposal](/student/assignments#project-proposal)

Each is submitted multiple times (rough drafts). If either of the
assignments doesn't fit with your domain, you can add additional
domain-specific criteria; let staff and students know of these
criteria.

**Small Assignments:** 

1. Students must participate in discussion; it is part of their
   grade. To encourage well thought out discussion, students must also
   submit their thoughts, in writing, on Canvas 24 hours before
   discussion. You might find it useful to read student submissions
   before section to structure discussion. You may also supply more
   specific questions for students to answer. See
   [Particpation](/student/assignments#Participation) for more detail.
2. Students complete small, [weekly
   assignments](/student/assignments#methodology-assignments)
   related to data science methodologies (software development; compute
   environments; effective communication). These weekly assignments
   independent of your domain, though you may find it useful to know what
   student's are learning parallel to their work in their domain.

### Grading

Regular feedback on student work is important for their progress
toward a successful capstone project. Grading in the Capstone Sequence
attempts this frequent feedback with minimal overhead for the mentor.

Below are summaries of grading responsibilities for each assignment,
as well as a description of the course grading schema.

**Assignments:**

* Weekly Discussion Questions: Answers to these questions in your
  domain schedule are part of student participation grades. Student's
  submissions on Canvas are graded for completion by course
  TAs. Feedback on student responses are student-driven and given by
  mentors in class.
* Weekly Methodology Assignments: These assignments are graded by
  course TAs.
* Result Replication (+ checkpoints): The result replication
  assignment consists of code and a written report. Domain mentors
  have no responsibility to grade student code. Feedback on the
  written reports can either be given on Canvas (written) or in
  mandatory office hours.
* Capstone Project Proposal: Feedback on the project proposal can
  either be given on Canvas (written) or in mandatory office hours.
* Elevator Pitch: The elevator pitch for project proposals take place
  in section during week 10. Grading for the pitch will be done in
  class, while feedback is given in writing or office hours.

**Grading Schemes**

Implementing a consistent grading scheme for work in such a diverse
collection of areas is helped by both a clear rubric and a coarse
grading scheme.

* Each assignment will have a (generally applicable) grading rubric
  that will help guide your grading. 
* Each assignment will be graded using a coarse schema that reflects
  broad checkpoints that students met. This schema helps maintain
  focus on *large, impactful* things that students can improve on and
  should reduce grading disaggreements.
  
The grading scheme for assignments in the course are given on an
A/B/C/F scale (without plus/minus). Generally, these grades reflect
the following criteria (credit: Shannon Ellis),

|Grade|Criteria|
|---|---|
|A (4.0) |Accomplishes the task accurately, completely, and clearly. Code is clear, effective, and efficient. Written component is concise, at the appropriate level, and correct. Oral component (when applicable) is effective both visually and explanation; is within the time limit. |
|B (3.0) |Accomplishes the task well, but lacks some completeness or clarity. Code runs but lacks some aspect of clarity, effectiveness, and or efficiency. Written component is logical and generally correct, but lacks either clarity or accuracy. Oral component (when applicable) is moderately effective and/or slightly outside the time window. |
|C (2.0) |The task is somewhat accomplished, but lacks significantly when it comes to completeness and clarity. Code present but does not accomplish the task up to the standards of a data science graduating senior. Written component lacks substantial clarity/correctness. Oral component (when applicable) significantly lacks effectiveness/clarity. |
|F (0.0) |The task largely remains unaccomplished. Code lacks completeness, structure, and is unclear. Written component lacking required information to understand what you did and/or your results. Oral component (when applicable) is nonsensical/unclear. |


Final grades will be computed using the grade-points above, using the
proportions given in the course components table. Letter grades will
be assigned using the standard university cutoffs.

### Student Compute Resources

Alongside personal laptops, students will use the campus ITS [DSMLP
Cluster](https://blink.ucsd.edu/faculty/instruction/tech-guide/dsmlp/index.html). This
is a Kubernetes cluster where students can specify their compute
resources and a data science environment in which to work.

Later in the first quarter, students will create and use a Dockerfile
for deploying their data science environment on the DSMLP cluster.

---

## Preparing for Quarter 2 (Project Mentoring)

TBA

---

## Running Quarter 2 (Project Mentoring)

TBA
