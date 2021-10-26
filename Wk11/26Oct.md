---
title: Probability and Statistics (MA6.101)
subtitle: |
          | Monsoon 2021, IIIT Hyderabad
          | 26 October, Tuesday (Lecture 17)
author: Taught by Prof. Pawan Kumar
---

# Probability
## Continuous Random Variables (contd.)
Note that when finding the probability, it does not matter whether we use $<$ or $\leq$, *i.e.* $P(X < a) = P(X \leq a)$ for any $a$.  

Since the PDF is the derivative of the CDF, we can also say
$$F_X(x) = \int_{-\infty}^x f_X(u)du$$
and
$$P(a < X \leq b) = F_X(b) - F_X(a) = \int_a^b f_X(u)du$$

The expectation of a continuous random variable is
$$E[X] = \int_{-\infty}^\infty xf_X(x)dx$$

The variance is defined in terms of expectation as $E[(X-\mu_X)^2]$.
