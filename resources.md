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

    - By default, you can only request 1 GPU (with `-g 1`). To request more, in addition to using `-g n` (where `n` is some integer between `2` and `8`), use `-p low` to specify that your request is _low priority_. For instance, `launch-scipy-ml.sh -g 4 -p low`.
    - Visit [here](https://datahub.ucsd.edu/hub/status) to see which pods and GPUs are currently free.