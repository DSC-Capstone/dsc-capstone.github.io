---
layout: page
title: "Quarter 2, Lesson 5 – Websites"
nav_exclude: true
---

# Quarter 2, Lesson 5 – Websites
{:.no_toc}

To recap, you're required to present your project in several ways. 

- Your **report** describes the details of your project and its implementation. It justifies why your project is interesting and details the correctness of your work. Learn more in [Quarter 1's Lesson 3](../../q1/03).
- Your **public GitHub repository** contains all of your implementation details, in a reproducible way (in that someone should be able to download your repo and run your code immediately). Learn more in [Quarter 1's Lesson 2](../../q1/02), [5](../../q1/05), and [6](../../q1/06).
- Your **poster** is a visual aid that supports your **oral presentation** at the [in-person capstone showcase](https://hdsishowcase.com). Learn more in [Quarter 2's Lesson 4](../04).

In this lesson, we'll detail the role of your fourth deliverable, your project **website**.

Remember to refer to the [examples presented at the bottom of the project spec](../../../../assignments/projects/q2#examples) and the [archive of past capstone projects](../../../archive) for context.

---

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Overview

### Target Audience

Your website serves as an introduction to your project for _some_ target audience you choose.
- The person at Company X that messaged you on LinkedIn.
- A person browsing the internet after a Google search in your project area.
- An expert in the field vaguely interested in your results.
- Your friends and family from home.

The goal of your website is to get your target audience interested in your project – you want them to understand why your work is impactful and encourage them, if interested, to read further. Realistically, nobody is going to look through the code in your GitHub repo unless they have a good reason to.

{: .note }
Your website will be the most prominent and public-facing of all the deliverables you create. As such, you should strive to create a high-quality website that you and your mentor are proud of. Prior instructors tell us that **hiring managers for industry jobs are more likely to respond to candidates who include links to project websites on their resumes**!

### Content and Style

Before writing the content of your website, you should decide who your target audience is, as this will determine the level of technical detail you provide.

Regardless of your audience, your site will contain many of the same sections as your report – expect your site to contain an introduction, a methods section, a results section, and a conclusion section.

- The introduction section should motivate the problem being addressed and justify its relevance to the reader. It should also introduce the methods being used.
- The methods section should describe how you approached the problem. **The level of detail provided depends on the target audience.**
- The results and conclusion sections (perhaps even just one big section in the website) should talk about the impact of the work.

You can tailor your website for different audiences by hiding in-depth technical details behind links or dropdown menus, like the one below.

<details>
    <summary>Example dropdown</summary>
    <br>
    Here are some hairy, scary details.
</details>

Note that your website should be **simple and easy to navigate**! 
- Refrain from using complicated layouts and too many pages - readers like to scroll, not click. All you're trying to do is motivate your project.
- Pictures and plots should tell your whole story, just like in your poster – just by skimming your figures, readers should be able to get the main idea of what you've done.
- It's a good idea to review what you did in DSC 106.

You don't need to write everything from scratch – feel free to re-use material from your report. However, your website should feel more informal and welcoming than your report, and so you may need to tailor your language and explanations accordingly.

---

## Creating a Website

Now that we understand the purpose of a project website, let's take a look at _how_ you'll create your site.

### Requirements

While there exist a variety of no-code platforms for building websites, like Google Pages and Squarespace, you cannot use them for this project. 

**Instead, you must create your website using code, and you must be able to store that code in a public GitHub repository.** By owning your website's code yourself, you can choose the hosting service you'd like to deploy it on, and are protected in any sudden changes in access (for instance, you lose access to UCSD Google Pages after you graduate).

That is not to say that you must write every single line of HTML, CSS, and Javascript yourself – while you're certainly free to, you can instead use existing templates, or use frameworks that generate HTML from other formats that are easier to write. (We'll recommend you use Jekyll through GitHub Pages, which takes a set of Markdown files and creates a website – more on this soon.)

### Static vs. Dynamic Websites

There are two general types of websites – static websites and dynamic websites. Read [this page](https://davidwalsh.name/introduction-static-site-generators) for an excellent example that distinguishes the two.
- **Static websites** run all computation in the client (web browser). They are created using HTML (content), CSS (styling), and Javascript (interactivity), though remember that you can create HTML, CSS, and Javascript using Markdown through frameworks like Jekyll. Static websites are not only easier to get up and running, but are also free (e.g. through GitHub Pages) or very cheap to run.
- **Dynamic websites** require server-side computation. In summary, the client (web browser) sends a request to a server, which sends a response back to the client. To run a dynamic website, you must either run and maintain a server of your own or pay for a cloud hosting service; either way, as your website becomes more popular, your costs will increase. Examples of dynamic websites include websites that access information stored in databases and websites that allow users to upload datasets and return predictions from an ML model.

Unless your project involves creating a web-based product (e.g. a dashboard or marketplace), **your project website should be a static website** to minimize overhead. You'd be surprised at the level of interactivity that is possible with a static webpage (including model execution – look at [Tensorflow JS](https://www.tensorflow.org/js), for instance.)

For instance, here is an interactive map created with <a href="https://plotly.com/python/">plotly</a> that students in DSC 80 are creating this quarter. You can drag and zoom with it.

<center>
<iframe src="assets/example-map.html" width=800 height=600 frameBorder=0></iframe>
</center>

If you think you need a dynamic webpage, you likely have already looked into how to set one up, but feel free to contact methodology staff if you have any questions.

---

## GitHub Pages

GitHub Pages hosts static websites **for free**; I personally make heavy use of this feature, and we encourage you to as well, both for this project and in the future.

- Each GitHub user is allowed to create one personal website, published at `<username>.github.io`. 
    - For instance, the capstone course website, [dsc-capstone.github.io](https://dsc-capstone.github.io), is the personal website for the GitHub user [dsc-capstone](https://github.com/dsc-capstone); the code for the website is stored at [github.com/dsc-capstone/dsc-capstone.github.io](https://github.com/dsc-capstone/dsc-capstone.github.io). 
    - As another example, my personal website is at [surajrampure.github.io](https://surajrampure.github.io), and its source code is in [github.com/surajrampure/surajrampure.github.io](https://github.com/surajrampure/surajrampure.github.io). Since I have a custom domain setup, the link appears as [rampure.org](https://rampure.org), however.
- Each project you create can have a project website, published at `<username>.github.io/<reponame>`.
    - For instance, the site for the repository [github.com/dsc-capstone/projects-2021-2022](https://github.com/dsc-capstone/projects-2021-2022) is hosted at [dsc-capstone.github.io/projects-2021-2022](https://dsc-capstone.github.io/projects-2021-2022).

You may opt to host your site out of a separate branch in your existing public repository, like `gh-pages`, or create a separate repository solely for your website.

### Creating a Website from Scratch

To create the most basic possible page on GitHub Pages:

1. Create a repository (or branch in a repository) named `<project>`.
1. Add, commit, and push a basic `index.html` file.
1. Go to your repository's settings, then click "Pages" on the left, and select a source and branch. (See [Publishing from a branch](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site) for more details.)

We recommend you _don't_ do this, since it's likely more work than is necessary, but you're free to. If you want to go this route, you may find the [GitHub Pages landing page](https://pages.github.com) to be helpful.

### Creating a Website using Jekyll

Jekyll is a Ruby-based tool that takes a set of Markdown files and images and turns it into HTML automatically. It allows you to create a static website by mostly editing Markdown files. It's particularly useful for websites that have multiple pages, but it's also useful when you don't want to worry too much about formatting.

GitHub Pages has Jekyll installed on its servers; this means that all you have to do is push Markdown code and your assets to a repository, and GitHub will handle the deployment.

To create a Jekyll-based site using GitHub Pages, follow the instructions [here](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/about-github-pages-and-jekyll). In short, you'll have to:

1. Create a repository (or branch in a repository) named `<project>`.
2. Go to your repository's settings, then click "Pages" on the left, then select a source and branch.

[Here](https://surajrampure.github.io/capstone-test-repo) is a barebones example of a Jekyll site; you can view the source code [here](https://github.com/surajrampure/capstone-test-repo/).
- Note that the `_config.yml` file specifies that the site's theme is `cayman`. There are several existing themes; browse them [here](https://pages.github.com/themes/) and read more about changing themes [here](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/adding-a-theme-to-your-github-pages-site-using-jekyll).

To see the source code for a more complicated Jekyll site, in addition to looking at [past capstone project websites](../../../../archive), you can look at the [source code for dsc-capstone.github.io](https://github/com/dsc-capstone/dsc-capstone.github.io). 
- The `_layouts` folder contains templates for various kinds of pages.
- In most pages' source code, [like this one (meta!)](https://raw.githubusercontent.com/DSC-Capstone/dsc-capstone.github.io/master/lessons/q2/05/index.md), you will see **front matter**, delimited by `---`, at the top of the page. Front matter provides metadata for a particular page; for instance, it may specify which template in `_layouts` to use.

More examples are linked below.
- [Aaron Fraenkel's malware domain site](https://github.com/afraenkel/capstone-malware-domain); given the link to the site's repo, can you find the site itself?
- [GitHub Pages' gallery of sites](https://github.com/collections/github-pages-examples).

{: .note }
The instructions above only show you how to configure a Jekyll site directly on GitHub Pages. If you'd like to render your Jekyll site locally, you'll need to install Jekyll (which means you'll also need to install Ruby). Find those instructions [here](/).

### Tutorials

Here are a few additional resources for creating sites on GitHub Pages.

- The official [GitHub Pages documentation](https://docs.github.com/en/pages).
- Jonathon McGlone's [through, from the start, tutorial with demo code](https://jmcglone.com/guides/github-pages/).
- [Jekyll documentation](https://jekyllrb.com/docs), mentioned above.
- [More examples of visualization tools](https://hackmd.io/2CEWS9T3Qxyk4DNPUBpn3w) by TA Kengchi Chang.

---

## Grading

In most cases, your project website will be your group's [**secondary deliverable**](../../../../syllabus#assignments-and-grades). In that case, the rubric we'll use to grade your website is as follows:

| Grade | Description |
| A | Well thought-out visual presentation for a specific target audience. Includes some content for a general audience. The code for the website is publicly available on GitHub. |
| B | The website is almost identical to the project report. The code for the website is publicly available on GitHub. |
| C | The website contains some content about the project, but is incomplete. A website builder service may have been used. |
| F| The website contains little to no content, and its code is not on GitHub. |

If your primary deliverable is a web-based application, then in addition to the above standards, your mentor will grade the content of your website itself.

Remember that the checkpoint for your website is due on **February 26th**. See the [Quarter 2 Project spec](../../../../assignments/projects/q2#website) for details on what is expected of you for the website checkpoint.