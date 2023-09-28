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

All lectures will be delivered as readings that you complete on your own time. Post questions with the lesson [here](https://edstem.org/us/courses/28947/discussion/2027764).

There is no Methodology Assignment associated with this lesson. However, it builds on the software development principles introduced in [Lesson 2](../02), and your final project deliverables will be graded according to how closely they follow these principles.

**Reminders:** 
- The [Quarter 1 Project Checkpoint](../../../assignments/projects/q1) is due **this Sunday!** Your checkpoint code does _not_ need to follow these standards.
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

While working on a project, your primary goal is to conduct a data-driven exploration of some problem, either using existing methods or new methods that are developed as part of your project. However, once your project is complete, it will still live on:
- If you structured your code well, bits and pieces of it can be extracted for other tasks that involve similar datasets, e.g. your [ETL](https://www.talend.com/resources/what-is-etl/) logic for data acquisition and cleaning.
- Your modeling code can be used to deploy models in production.
- More generally, your analysis will be used for decision-making.

In fact, when working on your project, it may be reasonable to create a separate repository for "general use libraries" that you develop, and import those libraries into your main project. That way, others can more easily adopt the general code that you've produced.

Let's look at some examples of projects and their artifacts.

| Project | Primary Output | Usage | Other Artifacts |
| --- | --- | --- | --- |
| Develop and train a recommender system. | A trained model. | The trained model (output) is executed on a website to give recommendations.<br><br>The model architecture code may become its own general purpose library, particularly if you built something novel.<br><br> (These will live in different repositories.) | A data analysis section that evaluates the model, to justify the project's worth. **If you are in a methods-focused domain, you must do this!**<br><br>A reproducible build, which automates updates to the model (e.g. with new training data). |
| Develop tools to measure engagement on websites. | A set of Javascript functions. | The Javascript functions developed will be run on a website to track and analyze user behavior. | A data analysis section that shows _why_ these functions and features were chosen. |
| Determine how many people to hire at a company. | A report with recommendations on how many people to hire. | Analyses are collected into a report for decision-making about business. | A data analysis section that demonstrates _how_ you arrived at your recommendations.<br><br>A reproducible build, for those who want to re-run your analysis (e.g. with new training data). |

For others to be able to use your project in the future, it needs be:
1. Easily buildable: It should be easy for someone else to load your Docker image, `git clone` your repo, and run your code.
  - If it's a hassle to get your project running, then others are unlikely to use it.
2. Flexible: It should be easy for someone else to re-use large pieces of your project while changing just the details that are necessary for their use case.

In the remainder of the lesson, we will look closely at two project components – build scripts and configuration files – that address the above two requirements directly.

---

## Build Scripts

### What is a Build Script?

As mentioned above, it's desirable for your project to be easy to run – ideally, future users can run `run project` in their Terminal and see the output of your work. That's precisely what build scripts enable!

Specifically, a build script runs the code in a project to "build" desired output. A build script _does not_ contain the implementation details of a project – that belongs in library code. Instead, a build script _calls_ library code, and thus should not be very complicated.

Build scripts are important for ensuring that your work is reproducible, as all science should be. While they are still not very common in data science projects, build scripts have been around for decades in other contexts. Examples include:
- [Makefiles](https://makefiletutorial.com), which are used to coordinate the compilation of C/C++ code and, more generally, to run general Bash (Terminal) commands.
  - These are extremely powerful for projects that involve multiple languages. You can use them in your data science projects too!
- [Ant, Maven, and Gradle](https://www.baeldung.com/ant-maven-gradle), which all coordinate the building of Java projects.
- [`setup.py`](https://www.educative.io/answers/what-is-setuppy) files in Python packages, which are used to install packages on others' systems. For instance, see the `setup.py` file for pandas [here](https://github.com/pandas-dev/pandas/blob/master/setup.py).
- While not "build scripts", _workflow managers_ like [Luigi](https://github.com/spotify/luigi) and [Airflow](https://airflow.apache.org/docs/apache-airflow/stable/python-api-ref.html) are similar in spirit, in that they allow you to build pipelines that "move data from point A to point B quickly" ([source](https://www.integrate.io/blog/airflow-vs-luigi/)).

To keep things simple, you will create a barebones build script from scratch, called `run.py`. Note that you can do this even if your project doesn't involve Python code; within your Python build script, you can import the `os` and `sys` libraries to call other Bash commands. If you'd like, you can write a build script in another language, e.g. `run.R` for R projects, or `run.sh` in Bash.

### Targets

A _target_ specifies what to build. Specifically, a target is a string describing the desired output, and targets are used when calling build scripts from the Terminal.

You should create targets for all major "steps" in your project pipeline, particular for steps that it would make sense to run in isolation of other steps. For instance: 
- You may have a target called `data` that prepares the data for your project by downloading data and running your ETL code. To use this target, users would run `python run.py data` in the Terminal.
- You may also have a target called `features` that builds the features for your project, from the already-processed data. To use this target, users would run `python run.py features` in the Terminal.

**As a reminder**, in [Lesson 2](../02#runpy), we looked at how to use command-line arguments in Python.

Above, we kept referring to "users", i.e. people using your project after you've finished building it. However, build scripts also make your life easier while working on your project. Here's an example workflow:
- Write ETL logic in `src/etl.py`.
- Import `etl` in `run.py`. Create a target called `data` that, when run via `python run.py data`, calls the relevant functions in `etl` to "build" the data.
- Work in notebooks to develop features, and, once no longer experimental, transfer feature creation code to `src/features.py`.
  - As we looked at in Lesson 2, notebooks are for experimenting and presenting, **not** for storing library code (e.g. functions) that you'll use repeatedly.
- Add a feature creation call to `run.py` under the target `features`, so `python run.py features` "builds" the features in your project.
  - This should be done without rebuilding the data, if possible!

By following this workflow, it'll make it easy to update different parts of your project when, say, your datasets change.

While the intermediate target names, like `features` and `data`, are up to you, there are a few standard target names that are almost always implemented:
- `all` runs `all` targets from scratch (`python run.py all`).
- `test` runs `all` targets on test data (`python run.py test`).
  - More on test data in Lesson 6.
- `clean` deletes all built files, so that you can build your project from scratch (`python run.py clean`).
  - It reverts to a _clean_ repository.

### Features of a Build Script

As a bare minimum, build scripts must piece together library code to create the output for your project. But, ideally, build scripts:
- (basic) Define targets that both clarify the overarching logic of the project and build intermediate states of the project (for debugging and for users who want to adapt your project from the middle).
- (intermediate) Do not do unnecessary intermediate computation.
  - If steps 1, 2, 3, ..., $k$ have already been completed and saved to files, then start at step $k+1$.
- (advanced) Run tasks in parallel, when possible.
  - Makefiles do this!

For further reading:
- [Using `argparse` instead of `sys.argv` to manage targets](https://docs.python.org/3/howto/argparse.html).
- Makefiles for Data Science: [bost.ocks.org/mike/make](https://bost.ocks.org/mike/make), [zmjones.com/make](http://zmjones.com/make).

---

## Configuration Files

So far, we've established that build scripts lay out the "big picture" logic of a project, and that library code contains implementation details.

If the implementation details of your project are likely to change, then it's rather inconvenient to have to go and repeatedly change library code. Instead, as introduced in Lesson 2, you should:
- Parameterize the details that are likely to change – i.e., make them inputs to your library functions, rather than hard-coded in the bodies of functions.
- Save the inputs that you'd like to call your functions on in **configuration files**.
- Read configuration files in build scripts to quickly change the input.

There's no exact science to determining what is "configuration" (detail) and what is "code" (logic), since it depends on the context of your project. The overarching question to ask, though, is **is this value likely to change as the project evolves?** If so, it belongs in configuration.


### Example: Parameterizing a Function

Below, we provide an example of how we might take code that doesn't involve configuration and generalize it. The example is similar, though not quite the same, as the one introduced in Lesson 2. Hopefully, it gets you to think about what role configuration files will play in your project.


```python
def get_data():
  data = pd.read_csv('data/raw/salaries_us_2012_2022.csv')
  data = (data
          .loc[df['year'] == 2015]
          .loc[df['state'] == 'CA])
```

The function above takes in no inputs, and quite a few pieces are hard-coded. Could some of these pieces change?
- File path (`'data/raw/salaries_us_2012_2022.csv'`): Is it likely that you'll receive new data and want to run your code on that new data at some point? If so, then perhaps the file path should be stored in a configuration file. **Then, when the path to your data changes, all you need to change is the configuration file!**
- Year (`2015`): Is your project specific to 2015, or may you want to expand the timeframe that you're interested in? If so, you may want to store a list of years in a configuration file.
- State: Is something about your project specific to California (for instance, are the datasets all California-specific)? If not, you may want to store the state(s) that you're interested in in a configuration file.

What is unlikely to change is the structure of the code itself – in this case, you will always need to load in a dataset as a DataFrame and query for only the years and states that are relevant. This _logic_ certainly belongs in a Python file. A parameterized version of the function above may look like this:

```python
def get_data(fp, years, states):
    data = pd.read_csv(fp)
    data = (data
            .loc[df['year'].isin(years)]
			  .loc[df['loc'].isin(states)])
    return data
```

### Configuration and Build Scripts

Let's tie everything together, in the context of the previous example. Where should everything live?

<table>
<th><code>src/etl.py</code></th>
<th><code>config/etl.json</code></th>
<th><code>run.py</code></th>
<tr>
<td><br><pre>
def get_data(fp, years, states):
    ....
    return data
</pre></td>
<td><pre>
{
  "fp": "data/raw",
  "years": [2020, 2021, 2022],
  "states": ["CA"]
}
</pre></td>
<td><pre>
...
config = json.loads(open(...))
get_data(**config)
</pre></td>
</tr>
</table>

This structure has several advantages:
- It it easy to track your "experiments" – you can create multiple config files, each of which corresponds to a different experiment.
  - Here, you might make 5 config files, each of which corresponds to a different set of years and states.
- It makes it easy to change the scope of your project, as all that needs to change are the inputs, not the code itself.
- It makes it clear to others what the main variables in your project are.

As a reminder, you should try and have the names of the keys in your configuration JSON files match the parameter names of your functions. This will allow you to use [dictionary unpacking](https://www.educative.io/answers/what-is-unpacking-keyword-arguments-with-dictionaries-in-python) when calling your functions. Also, as you'll see in the examples below, it's typical to have multiple configuration files, each of which corresponds to a different stage of your project.

---

## Example Projects

[This repository](https://github.com/DSC-Capstone/project-templates) contains several example data science projects of different flavors; each project is stored in a different branch. You can use these templates to structure your projects.
