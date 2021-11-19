---
title: Probability and Statistics (MA6.101)
subtitle: |
          | Monsoon 2021, IIIT Hyderabad
          | 19 November, Friday (Lecture 23)
author: Taught by Prof. Pawan Kumar
header-includes: 
    - \usepackage{amsmath}
---

# Probability
## Some Properties of Expectation
If $X, Y$ are two RVs and $g, h$ are functions of $X$ and $Y$, then
$$E[g(X)h(Y) \mid X] = g(X) E[h(Y) \mid X].$$

The Law of Iterated Expectations states that if $X, Y$ are two RVs, then
$$E[X] = E[E[X\mid Y]].$$

If $X, Y$ are two independent RVs, then

* $E[X\mid Y] = E[X]$
* $E[g(X) \mid Y] = E[g(X)]$
* $E[XY] = E[X]E[Y]$
* $E[g(X)h(Y)] = E[g(X)]E[h(Y)]$

## Conditional Variance
If $X, Y$ are two RVs, then the conditional variance of $X$ given $Y = y$, is
$$\text{Var}(X \mid Y = y) = E[X^2 \mid Y] = \mu_{X \mid Y}(x^2).$$

The Law of Total Variance states that if $X, Y$ are two random variables, then
$$\text{Var}(X) = E[\text{Var}(X \mid Y)] + \text{Var}(X \mid Y).$$

## Joint Probability Density Function
Two RVs $X, Y$ are jointly continuous if there exists a nonnegative function $f_{XY} : \mathbb{R}^2 \to \mathbb{R^2}$ such that for any $A \subseteq \mathbb{R}^2$, we have
$$P((X,Y) \in A) = \int \int_A f_{XY}(x,y)dxdy.$$

The function $f_{XY}$ is the joint probability density function.

The marginal continuous PDF is analogously defined as
$$f_X(x) = \int_{-\infty}^\infty f_{XY}(x,y)dy.$$

## Conditional PDF
The conditional PDF of $X$ given $Y = y$ is
$f_{X \mid Y}(X \mid y) = \frac{f_{XY}(x,y)}{f_Y(y)}.$$

This can be integrated to find the conditional CDF and the conditional probability of any range $A$.
