---
layout: post
title: "The five element ninjas approach to teaching design matrices"
date: 2016-04-25 23:50
comments: true
---

Design matrices unite seemingly disparate statistical methods, including linear regression, ANOVA, multiple regression, ANCOVA, and generalized linear modeling.
As part of a hierarchical Bayesian modeling course that we offered this semester, we wanted our students to learn about design matrices to facilitate model specification and parameter interpretation.
Naively, I thought that I could spend a few minutes in class reviewing matrix multiplication and a design matrix for simple linear regression, and  if students wanted more, they might end up on [Wikipedia's Design matrix page](https://en.wikipedia.org/wiki/Design_matrix).

It quickly became clear that this approach was not effective, so I started to think about how students could construct their own understanding of design matrices.
About the same time, I watched a pretty incredible kung fu movie called [Five Element Ninjas](http://www.imdb.com/title/tt0084921/), and it occurred to me that the "five elements" concept could be an effective device for getting my students to think about model specification and design matrices.

![](/images/Five-Element-Ninjas-001.jpg)

# Learning goals

Students should be able to specify design matrices for many different types of models (e.g., linear models and generalized linear models), and they should be able to interpret the parameters.

# Approach

The broad idea was to get the students to think about model specification from five perspectives:

1. Model specification via a design matrix
2. Model specification via R syntax (e.g., the `formula` argument to `lm`)
3. Model specification via "long form" equations
4. Graphical model specification
5. Verbal model specification (along with an interpretation of each of the parameter estimates)

This leverages what students already know, and encourages them to connect new concepts to their existing knowledge.
In our case, the students were all students in CU Boulder's Ecology and Evolutionary Biology graduate program.
Most of them had a strong grasp of perspective 2 (model specification in R syntax), but relatively weak understanding of the remaining perspectives.

# Getting the students started

Before we asked them to do anything, I demonstrated this five elements approach on a simple model: the model of the mean.

### 1. Design matrix specification

$$y \sim N(\mu, \sigma_y)$$

$$\mu = X \beta$$

$$X = \begin{bmatrix} 1 \\ 1 \\ \vdots \\ 1 \\ 1 \end{bmatrix}$$

### 2. R syntax

The formula for a model of the mean is `y ~ 1`

### 3. Long form equations

$$y_1 = \beta + \epsilon_1$$

$$y_2 = \beta + \epsilon_2$$

$$ \vdots $$

$$y_n = \beta + \epsilon_n$$

### 4. Graphical interpretation

![](/images/x1.png)

### 5. Verbal description

I asked for a student to take a stab at a verbal description of the model specification, and also to explain the interpretation of the parameter $\beta$.
If they're having a hard time understanding the task, you can tell them to pretend that they are talking to a classmate on the phone and trying to describe the model.

# The activity

We provided students with a very simple data set that does not include the "response" variable.
This was printed ahead of time, so that each student had a paper copy that they could also use as scratch paper.

| Covariate 1 | Covariate 2 |
|-------------|-------------|
| 1.0         | A           |
| 2.0         | B           |
| 3.0         | A           |
| 4.0         | B           |

The omission of the response variable is deliberate, reinforcing the idea that one can construct a design matrix without knowing the outcome variable (this is useful later in our class for prior and posterior predictive simulations).

We organized the students into groups of three or four and had each group come up to the blackboard, which we partitioned ahead of time to have a space for each group to work.
Then, *we proceeded to work through incrementally more complex models with our five-pronged approach*:

1. A model that includes an effect of covariate 1.
2. A model that includes an effect of covariate 2.
3. A model that includes additive effects of covariate 1 and 2 (no interactions).
4. A model that includes additive effects and an interaction between covariate 1 and 2.

Each of these exercises took about 15 minutes, and once all the groups were done we checked in with each group as a class to see what they came up with.
Some groups opted for effects parameterizations, while others opted for means parameterizations, which lead to a useful discussion of the default treatment of intercepts in R model formulas and the manual suppression of intercepts (e.g., `y ~ 0 + x`).

# The outcome

This in-class activity was surprisingly well-received, and it seemed to provide the context and practice necessary for the students to understand design matrices on a deeper level.
Throughout the rest of the semester, model matrices were preferred over other specifications by many of the students - a far cry from the widespread confusion at the beginning of the semester.
