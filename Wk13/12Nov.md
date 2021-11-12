---
title: Probability and Statistics (MA6.101)
subtitle: |
          | Monsoon 2021, IIIT Hyderabad
          | 11 November, Friday (Lecture 21)
author: Taught by Prof. Pawan Kumar
header-includes: 
    - \usepackage{amsmath}
---

# Probability
## Joint Probability
### Joint Probability Mass Function
The joint PMF of two discrete random variables $X$ and $Y$ is denoted $P_{XY}(x,y)$ and defined $P(X = x, Y = y)$.  

The joint range for $X$ and $Y$ is $R_{XY} = \{(x,y) \mid P_{XY} > 0 \}$, *i.e.*, $R_{XY} \subset R_X \times R_Y$.  

The sum of joint probabilities must sum to 1.  

To compute the probability of some event set $A \subset \mathbb{R}^2$, we take the sum:
$$P((X,Y) \in A) = \sum_{(x_i, y_j) \in A \cap R_{XY}} P_{XY}(x_i, y_j).$$

We can also obtain the PMF of $X$ from its joint PMF with $Y$ as
$$P_X(x) = \sum_{y_j \in R_Y} P_{XY}(x,y_j).$$
We call the PMF obtained in this way the marginal PMF of $X$.

### Joint Cumulative Distribution Function
Analogously, we have
$$F_{XY}(x,y) = P(X \leq x, Y \leq y).$$
This applies to both discrete and continuous variables.  

Note that we have the property $F_{XY}(\infty, \infty) = 1$, and $F_{XY}(-\infty, y) = 0$.

For the marginal CDF, we can find
$$F_X(x) = F_{XY}(x, \infty).$$

For the probability of ranges, we can use the following result:
$$P(x_1 < X \leq x_2, y_1 < Y \leq y_2) = F_{XY}(x_1,y_1) + F_{XY}(x_2, y_2) - F_{XY}(x_1, y_2) - F_{XY}(x_2, y_1).$$

## Independent Random Variables
If $X, Y$ are two RVs, they are independent if
$$\forall x, y : P_{XY}(x,y) = P_X(x)P_Y(y).$$

Note that if $X$ and $Y$ are independent, then
$$P(x_i | y_j) = P_X(x_i).$$
