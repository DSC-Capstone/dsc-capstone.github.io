---
layout: page
title: "Lesson 8 – Examples"
nav_exclude: true
---

<script type="text/javascript" async
  src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.7/MathJax.js?config=TeX-MML-AM_CHTML">
</script>

# Lesson 8 – Examples
{:.no_toc}

All lectures will be delivered as readings that you complete on your own time. Post questions with the lesson [here](https://edstem.org/us/courses/28947/discussion/2153809).

Make sure to read this article before moving on to [Methodology Assignment 5](../../../assignments/methodology/q1/05).

---

There's not much _new_ content for this week. Instead, as you start to put together your Quarter 1 Project's codebase, we wanted to remind you of [this repository](https://github.com/DSC-Capstone/project-templates). The repo contains several examples of data science projects that follow best practices; each example is in a different branch.

One example you should look at is [Titanic Prediction](https://github.com/DSC-Capstone/project-templates/tree/titanic). In particular:
- The script `run.py` shows how to implement various targets. In MA 5 and your final Quarter 1 Project submission, you'll need to implement the `test` target, which this particular example does not.
- The data is pulled [from an API](https://github.com/DSC-Capstone/project-templates/blob/titanic/src/etl.py) that requires an API key. You'll note that the API key **is not** pushed to Git, and that's because API keys generally are _secrets_ that should not be shared with anyone else. For others to run the project from end-to-end, they'll need to generate their own API key and store it in a particular location. (If this applies to your project, you'll also implement a `test` target that will allow others to run your entire project without needing to create an API key.)