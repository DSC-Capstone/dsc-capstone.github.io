---
layout: page
title: 📖 Resources
nav_order: 4
nav_exclude: true
---

# 📖 Resources
{:.no_toc}

---

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Computing Resources

- [Command-line cheat sheet](../command-line)
    - Bash cheat sheets: [educative.io](https://www.educative.io/blog/bash-shell-command-cheat-sheet), [devhints.io](https://devhints.io/bash). 
- [DSMLP documentation](https://support.ucsd.edu/services?id=kb_category&kb_category=368cc80fdb5c68d0d4781c79139619e2)
    - [Accessing section-specific data](../section-specific)
    - [Launching containers](https://support.ucsd.edu/services?id=kb_article_view&sys_kb_id=899d64931b6c991048e9cae5604bcb6e)
    - To view the amount of disk space you have left, navigate [here](https://datahub.ucsd.edu/hub/spawn). At the `/hub/spawn` page, select the Services Tab > "disk-quota-service".
    - Use `launch-scipy-ml.sh -h` to see all launch options.
    - By default, you can only request 1 GPU (with `-g 1`). To request more, in addition to using `-g n` (where `n` is some integer between `2` and `8`), use `-p low` to specify that your request is _low priority_. For instance, `launch-scipy-ml.sh -g 4 -p low`.
    - Visit [here](https://datahub.ucsd.edu/hub/status) to see which pods and GPUs are currently free.
- [Setting up SSH keys](https://www.digitalocean.com/community/tutorials/how-to-set-up-ssh-keys-2)
- [Git on the command line](https://docs.github.com/en/get-started/quickstart/set-up-git)
    - [Personal access tokens](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token)
        - You may also want to read [this guide](https://docs.google.com/document/d/1Sb6tQwUVBhzcmBGWw4UnhGlYcMDdyUy3gaRKcQzYur4/edit) written by current student and DSC 30 tutor Scott Yang
    - [SSH Keys for GitHub](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/about-ssh)
- [UCSD VPN](https://blink.ucsd.edu/technology/network/connections/off-campus/VPN/)

Have a resource that we should add to this page? Let us know!