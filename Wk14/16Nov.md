---
title: Probability and Statistics (MA6.101)
subtitle: |
          | Monsoon 2021, IIIT Hyderabad
          | 16 November, Tuesday (Lecture 22)
author: Taught by Prof. Pawan Kumar
header-includes: 
    - \usepackage{amsmath}
---

# Probability
## Joint Probability (contd.)
### Conditional PMF and CDF
The conditional PMF of a random variable is a function which gives the probability of each event given a certain constraint on the value.  

The conditional PMF of two variables is defined according to the joint probability. It is denoted as
$$P_{X \mid Y} (x_i, y_j) = \frac{P_{XY}(x_i, y_j)}{P_Y(y_j)}.$$

The law of total probability for joint distributions is
$$P(X \in A) = \sum_{y_j \in R_Y} P(X \in A \mid Y = y_j)P_Y(y_j).$$
