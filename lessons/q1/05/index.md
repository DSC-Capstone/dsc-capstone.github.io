---
layout: page
title: "Lesson 5 – Software Development"
nav_exclude: true
---

<script type="text/javascript" async
  src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.7/MathJax.js?config=TeX-MML-AM_CHTML">
</script>

# Lesson 5 – Software Development
{:.no_toc}

All lectures will be delivered as readings that you complete on your own time. Post questions with the lesson [here](TODO).

There is no Methodology Assignment associated with this lesson. However, it builds on the software development principles introduced in [Lesson 2](../02), and your projects will be graded according to how closely they follow these principles.

**Reminders:** 
- The [Quarter 1 Project Checkpoint](../../../assignments/projects/q1) is due **this Sunday!**
- Take a look at the new [Resources](../../../resources) tab of the course website.


---

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Overview

Recall, in [Lesson 2](../02), we introduced a template for data science projects by [Cookie Cutter Data Science](https://drivendata.github.io/cookiecutter-data-science):

```
Project
├── .gitignore         <- Files to keep out of version control (e.g. data/binaries).
├── run.py             <- run.py with calls to functions in src.
├── README.md          <- The top-level README for developers using this project.
├── data
│   ├── temp           <- Intermediate data that has been transformed.
│   ├── out            <- The final, canonical data sets for modeling.
│   └── raw            <- The original, immutable data dump.
├── notebooks          <- Jupyter notebooks (presentation only).
├── references         <- Data dictionaries, explanatory materials.
├── requirements.txt   <- For reproducing the analysis environment, e.g.
│                         generated with `pip freeze > requirements.txt`
├── src                <- Source code for use in this project.
    ├── data           <- Scripts to download or generate data.
    │   └── make_dataset.py
    ├── features       <- Scripts to turn raw data into features for modeling.
    │   └── build_features.py
    ├── models         <- Scripts to train models and make predictions.
    │   ├── predict_model.py
    │   └── train_model.py
    └── visualization  <- Scripts to create exploratory and results-oriented viz.
        └── visualize.py
```

This template was chosen out of a need to develop data science projects that are:
1. Flexibly written, to adapt to changing questions.
1. Clearly documented, so that is clear – both to you and others using your code – what each piece does.
1. Reproducible, meaning that others should be able to run it themselves.

While the focus in Lesson 2 was on how to _develop_ projects, the focus in this lesson will be on how projects are used _after_ they are completed. To do this, we need to understand how data science projects are used in practice.

The goal of a data science project is often to 


### Examples



---

## Build Scripts

A build script enables others to clone and "run" your project, without needing to sift through your code.

There are several ways to create build scripts.

Run just the targets that are necessary, don't re-run everything everytime a small thing is changed. remember to regularly move stuff out of notebooks.

targets:
- all
- test data
- clean

python argparse for instance

---

## Configuration Files

parameterize what is likely to change. if the project is and always will be only about california, leave it in your code. but if you might want to run this analysis for different states, maybe parameterize it and put it in a configuration file.

show pre-splitting it up and post splitting it up

maybe do a quick demo video on how we'd actually live code this

---

## Example Projects

In [this repo](#), 
