---
title: Probability and Statistics (MA6.101)
subtitle: |
          | Monsoon 2021, IIIT Hyderabad
          | 22 October, Friday (Lecture 16)
author: Taught by Prof. Pawan Kumar
---

# Probability
## Cumulative Distribution Function
The cumulative distribution function (CDF) of a random variable $X$ is defined as
$$F_X(x) = P(X \leq x), x \in \mathcal{R}.$$
For a discrete variable $X$, $F_X$ is in the form of a staircase. We say that $F_X(-\infty) = 0$ and it jumps at every point in the range of $X$.

One result relating to CDFs is for all $a \leq b$, we can say that $P(a < X \leq b) = F_X(b) - F_X(a)$.

## Continuous Random Variables
A random variable $X$ with a CDF $F_X(x)$ is said to be continuous if $F_X(x)$ is continuous in $\mathcal{R}$.  

Note that the PMF may not be continuous, but the CMF always must be.  

The probability density function or PDF is defined as probability per unit length. It can be found by taking the limit of the ratio of $P(x < X \leq x + \Delta)$ with $\Delta$, *i.e.*, it is equivalent to $F_X'(x)$.
