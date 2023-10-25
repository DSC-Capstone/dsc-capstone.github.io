---
layout: page
title: "Lesson 3 – Software Organization"
nav_exclude: true
---

<script type="text/javascript" async
  src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.7/MathJax.js?config=TeX-MML-AM_CHTML">
</script>

# Lesson 3 – Software Organization
{:.no_toc}

All lectures will be delivered as readings that you complete on your own time. Post questions with the lesson [here](TODO).

<!-- There is no Methodology Assignment associated with this lesson. -->

---


## Test Data

### Overview

It would be a massive waste of time and resources to kick off a long-running job that runs for a few hours before terminating because of a bug in our code. In order to detect such bugs, we will create and run our code on _test data_.

Test data is _small_, made-up data that is realistic enough to _test_ the behavior of our code.
- It is not a sample of real data – it should be _created_ by the developer.
- It is designed to test the correctness of code.
- Developers should design each line/component of the test data to test different aspects of their code.

**Warning**{: .label .label-yellow } **In this context, test data is created for unit tests, _not_ data that results from a train/test split!**

Test data should only be a few lines long. You should be able to verify that your code works correctly on test data **by hand**. For instance, suppose your code takes in a dataset, uses [`sklearn.preprocessing.PolynomialFeatures`](https://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.PolynomialFeatures.html) to create a quadratic feature, and trains a regression model of the form $$H(x) = w_0 + w_1 x + w_2 x^2$$. A possible test dataset might be

```
x,y
-2,1
2,9
3,16
```
By hand, we can verify that the three points above satisfy $$y = (1 + x)^2 = 1 + 2x + x^2$$, so as a "test case" we can expect that our code outputs $$w_0 = 1, w_1 = 2, w_2 = 1$$ (with a loss of 0).

Note that since test data is synthetic, the resulting trained models will be meaningless. For instance, the weights $$w_0 = 1, w_1 = 2, w_2 = 1$$ mean nothing if our regression model aims to model car acceleration as a function of horsepower. This is expected – the sole purpose of test data is to ensure that code works correctly.

### Using Test Data

Run your project using test data until you can verify that your code and outputs are correct. Once you've done so, then you can initiate a long-running job on _real_ data, with the piece of mind that it should run correctly. (As an intermediate step you may also elect to run your code on a _sample_ of the full dataset, but remember, the test data is not merely a sample).

Recall, in [Lesson 5](../05#targets), we introduced the idea of _targets_. 

> A target specifies what to build. Specifically, a target is a string describing the desired output, and targets are used when calling build scripts from the Terminal.

You're **encouraged** to implement a `test-data` target, that runs the same code as the `data` target, but only on your test data. To train a model on your test data, you may run your build script with `test-data` as one of your many targets:

```py
python run.py test-data features model
```

For instance, the above call to `run.py` should featurize test data and use that featurized data to train a model.

While you're encouraged to implement a `test-data` target, you're **required** to implement a `test` target, both for your Quarter 1 Project and for your Quarter 2 Project. The `test` target should behave the same as the `all` target discussed in Lesson 5, just on your test data – that is, it should build your entire project from scratch, using test data.

We will use your `test` target to **grade** your project code in both quarters. Here are the specific commands we'll run on our personal DSMLP containers to grade your work:

1. `launch-scipy-ml.sh -i <your-docker-repo>`
2. `git clone <your-github-repo>`*
3. `python run.py test`
4. `<script that checks generated files>`

_*While your Quarter 2 Project repo is required to be public, your Quarter 1 Project repo can be private. As such, if your code is not accessible on GitHub, we'll download it directly from Gradescope._

This means that we (methodology staff) don't need access to your "real" data in order to evaluate your project. While your reports and deliverables will be a result of real data, your submitted code will not include it. As mentioned in Lesson 2, **your actual data should never included in Git/version control**, since it does not change. However, since test data is _created_ by the developer and may change as the project evolves, it **should** be included in version control. For instance, you may place it in the `test/testdata/` directory.

