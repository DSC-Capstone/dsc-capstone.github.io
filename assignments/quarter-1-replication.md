---
layout: page
title: Result Replication
doodle: /assets/images/doodle.png
---

---
* TOC
{:toc}

---

## Introduction

*This assignment is worked on in pairs*.

This quarter, each domain works through a central problem that
introduces you to the area. Depending on the domain, you will produce
either:
1. a replication of a known result in a (published) paper, or
2. a survey paper, with a hands-on, data driven inquiry
   into a relevant question in the area.

By the end of the quarter, you will summarize the results of
your work in a well-organized report that follows the norms of
research papers in your domain.

Your work will go beyond mere paraprhasing of the existing work that
you study:
* Your domain may be taking a broader or narrower view than the work
  of any one paper. Your report will reflect the work *you* are doing,
  not the broader research that may be found in the work being
  studied.
* You will likely be using data that differs from that used in the
  work you are studying.
* Your conclusions may be different than the work you are
  studying. You should present the conclusions drawn from *your*
  data/methods and address any discrepancies with the work being
  studied.
* The code supporting your work will conform to best practices in data
  science software development.
  
## What is being turned in?

Work on the report comprises of:
1. A pdf submission of the report (w/feedback given by domain mentor),
2. The code that generates the contents of the report (w/feedback
   given by head instructor/TAs).
  
## Objectives for the Q1 report

* Carefully explaining work in your area study ensures you understand
  the area you'll be working in *very well*, details and
  all. In particular you will understand how to draw a rigorous
  conclusion in your area.
* Emulating finished work in your domain of inquiry encourages you to
  carefully consider how to effectively communicate technical ideas in
  your area.
* Critically view existing methodologies and conclusions in a way that
  raise possible improvements to existing approaches (e.g. possible
  work in Q2).
* Certain sections of your report (e.g. the literature review) will
  serve as a foundation for your writing in quarter 2.
* You will get practice using tools for producing such reports.
* Develop a library of useful code and the foundations
  of a code pipeline for further work in the area.

## Checkpoints

You will work on the report in three parts (two checkpoints and a final):
1. Checkpoint #1: Introduction (Part-1)
2. Checkpoint #2: Introduction (Part-2) / Methods
3. Final: Results and Conclusions

Each successive checkpoint should be cumulative (containing the
previous checkpoints) with a marker signifying where the current work
begins.

You must make the suggested changes to your previous checkpoint before
submitting the following assignment. If a mentor sees suggestions on a
previous section being ignored, that may *continue to affect your
grade*.

### Checkpoint #1

Report portion:

Write an introduction, as laid out in lecture. This includes:
1. An explanation of the problem being investigated.
2. A brief explanation of the context of the problem and why it's
   interesting.
3. A description of either:
   * the data generation process and its relationship to the problem
     (i.e. for domain problems)
   * the type of data for which the method is appropriate
     (i.e. for methods problems)
4. Basic description of observed data used in the investigation and
   why it's appropriate for addressing the problem.
   

This introduction should be turned in as a PDF and conform to
standards set in both lecture and your domain.

Code Portion:

Your code should be turned in via GitHub. It should:
* conform to the template structure discussed in lecture,
* contain a rudimentary data ingestion pipeline,
* include documentation both in your README.md, describing the purpose
  of the code, its contents, and how to run it.
* be runnable runnable via the command `python run.py data`. Include a
  `data-params.json` file in the `config` directory, which specifies
  any data-input locations. If your data-ingestion requires data that
  is on your local computer, include a copy of the data in your
  domain's `/teams` directory on the DSMLP server and include that
  location in your `data-params.json`.

For both the Report and Code Portion, **write in a Canvas comment
listing what tasks each group member was responsible for**.

### Checkpoint #2

In this checkpoint you will be writing the more completing your
introduction and describing your methods. You should continue add this
work into a narrative form according to the 'scientific writing'
lecture.

Report Portion:

* Write a description of of the methods used in the investigation.

If you have a data-modeling focused domain:
* Write an EDA that gives a data-driven argument for why the data that
you use is appropriate for answering the question in the problem laid
out in your introduction. You should also address and justify and data
cleaning or manipulation.

If you have a methods focused domain:
* Describe the implementation of your method in detail, discussing
  relevant decisions that had to be made in writing your code (and
  their implications).


Code (which bullet takes more time/code will depend on your domain):
* Incorporate data cleaning code into your pipeline, if relevant.
* Develop code that generates analysis/figures for EDA.
* Implement the methods that generate results.

*Note:* If you like, You can write your report in a jupyter notebook and strip out
the code using `jupyter nbconvert`:
```
jupyter nbconvert --no-input --to pdf --output notebook.pdf notebook.ipynb
```

You can also save figures you've generated from scripts to files using
`plt.savefig` and incorporate those into your report.


### Final Report

TODO

Report:
* Write results and conclusion

Code:
* Develop code for generating results
* Develop code that generates analysis/figures for results
