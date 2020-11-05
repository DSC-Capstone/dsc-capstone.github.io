---
layout: page
title: Effective Communication
doodle: /assets/images/doodle.png
---

---
* TOC
{:toc}

---

* This page collects some principles and resources on data science communication that you might find useful throughout this and next quarter. It will be updated constantly.
* Data scientists often have to communicate their findings with different stakeholders--from engineers, managers, to customers. As a result, these are also highly-transferable skills for your professional development.

## Principles

* Know your audience: Envision what they already know and what you are passing along. For this course, you will face different scenarios: Writing scientific reports for curious readers, generate visualization blogposts to general public, and present findings in front of industry partners.
* Be as specific as possible: Vagueness causes confusion. Use concrete and testable terms. Refrain from using adjectives and adverbs. 
* Avoid jargons and [curse of knowledge](https://en.wikipedia.org/wiki/Curse_of_knowledge): Define and explain concepts in plain English that other data science majors outside of your domain or HRs in your dream company can get the main idea. After writing a report / blog post / presentation draft, step aside and try to unlearn the things you already know. Then approach the draft again with a fresh pair of eyes--more often than not you will find blindspots of your earlier self.
* Try to tell a story: Regardless of platform, you are telling a story about your data. Stories are easier to follow if you have a main argument. Decide what is the [central dramatic argument](http://jtleek.com/ads2020/week-9.html#story-telling-in-data-analysis) of your delivery. Have a strand of arguments that lead to the main point if it is complicated. Spend more time on the parts of your analyses that are interesting and true; quickly go over the parts that are true but uninteresting (but still report them). 

## Reports (applies to final replication / project)

* Target audience: Imagine an upper-undergraduate data science major outside of your domain is reading your report. They should be able to understand what you are working on by simply reading your report. 
* Report should be written in the form of a scientific paper. Please see [Lecture Notes on Scientific Writing](https://dsc-capstone.github.io/resources/lecture-notes/Lecture04_Scientific_Writing.pdf) for more detailed anatomy.
* The report itself should be self-contained. This means that you should explain things (procedures, results, etc) in itself in forms of words or equations and referencing the relevant tables or figures in the main text, not just printing your results. A report also should not just describe the findings without showing the actual result.
* A good report should be readable, welcoming to a curious reader, and provides context when necessary. Providing too many details, on the other hand, can also be distracting. Decide whether they need this specific information at this point or not for the audience.

## Blog Posts / Visualization Demos

* Target audience: General public, non data science majors
* Main idea: 
    * Have one or two main figures that deliver the main idea of your project, along with a few sentences that reinforces the reader's understanding.
    * The reader should be able to get the idea by simply reading the figure (without reading the sentences). So make the figure intuitive and label the axes clearly. Add titles and legends. Add annotations on figures when necessary.
* Some examples: 
    * [The New York Times Intergenerational Mobility](https://www.nytimes.com/interactive/2018/03/19/upshot/race-class-white-and-black-men.html)
    * [The Economist: Tracking Covid-19 Excess Deaths](https://www.economist.com/graphic-detail/2020/04/16/tracking-covid-19-excess-deaths-across-countries)
    * [Election Forecast Correlations](https://roadtolarissa.com/forecast-correlation/)
    * [How to Win an Oscar](https://observablehq.com/@bartok32/how-to-win-an-oscar)
    * [The Universe of Miles Davis](https://pudding.cool/2017/03/miles/index.html)
* Some libraries for interactive plots: You can use in conjunction with Jupyter Notebook
    * [Plotly](https://plotly.com/python/): Easy to use but a bit clumsy
    * [mpld3](https://mpld3.github.io/): Based on D3.js and matplotlib
    * [Altair](https://altair-viz.github.io/): Based on Vega-Lite
    * [Bokeh](https://docs.bokeh.org/en/latest/index.html): Extensive plotting capabilities, explore their example gallery.
* Ways to deploy:
    * You can create a Github repo for visualization and host static website on [Github pages](https://lab.github.com/githubtraining/github-pages) (or add [Github Actions](https://lab.github.com/githubtraining/github-actions:-continuous-integration) to the repo to host dynamic website)
    * You can render an interactive notebook through [nbviewer](https://nbviewer.jupyter.org/), see [Working with Jupyter Notebook files on GitHub](https://help.github.jp/enterprise/2.11/user/articles/working-with-jupyter-notebook-files-on-github/)
    * There are also some new (free) services such as [Observable](https://observablehq.com/). Here is one example on [Connection between song's features and popularity](https://observablehq.com/@bartok32/connection-between-songs-features-and-popularity)

## Presentations

* Target audience: You will likely deliver talks of your project (separately) to both classmates and industry partners
* (more to come)

## General References

* [Advanced Data Science 2020](http://jtleek.com/ads2020/) by Jeff Leek and Roger D. Peng
* [Ten simple rules for structuring papers](https://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1005619) by Brett Mensh and Konrad Kording 
* [Data Visualization](https://socviz.co/lookatdata.html#what-makes-bad-figures-bad) by Kieran Healy

