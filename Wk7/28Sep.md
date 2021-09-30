---
title: Probability and Statistics (MA6.101)
subtitle: |
          | Monsoon 2021, IIIT Hyderabad
          | 28 September, Tuesday (Lecture 10)
author: Taught by Prof. Pawan Kumar
header-includes: \usepackage{physics}
---

# Probability (contd.)
## Properties of Conditional Probabilities
For any events $A, B, E$, we have

* $0 \leq P(A \cap E) \leq 1,$
* $P(A \mid E) = 1 - P(A^c \mid E),$
* $P(A \cap B \mid E) = P(B \mid E) P(A \mid B \cap E),$
* $P(A \mid B \cap E) = \frac{P(B \mid A \cap E) P(A \mid E)}{P(B \mid E)}.$

## Conditional Independence
Two events $A, B$ are conditionally independent if
$$P(A \cap B \mid E) = P(A \mid E)P(B \mid E).$$

Note that independence does not imply conditional independence.

## Random Variables
A random variable $X$ is a function from the sample space to real numbers:
$$X : S \to \mathcal{R}.$$

The range of a random variable is the set of possible values it takes. For example, the number of heads in 10 tosses of a fair coin is a random variable.  

A random variable may be discrete (having countable range), continuous, or mixed.
