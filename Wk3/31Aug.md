---
title: Probability and Statistics (MA6.101)
subtitle: |
          | Monsoon 2021, IIIT Hyderabad
          | 31 August, Tuesday (Lecture 5)
author: Taught by Prof. Pawan Kumar
---

# Probability
## Random Walks
### 1D
A walk is called a simple random walk in 1D if there is an equal probability of going left or right.  

Consider the probability that a person ends up at $x = 0$ at the $i^\text{th}$ step of a simple random walk.  
The choice tree for this process resembles a Galton board; we see that the probability is $^i C _\frac{i}{2} \frac{1}{2^i}$ (for even $i$) for a simple walk.  

If the probability of going to the right is, say, $q$, then the probability becomes
$${^i C _\frac{i}{2}} \cdot q^{\frac{i}{2}} (1-q)^{\frac{i}{2}}$$

### 2D
Let Alice start at the bottom left corner of a 5 $\times$ 5 lattice and Bob at the top right. Alice walks one edge right or up every second; Bob walks left or down. Consider the probability that they meet.  

It is clear that they cannot meet anywhere except along the non-principal diagonal, and only after each has taken 5 steps. Thus the total number of ways Alice and Bob can reach the same vertex on the diagonal is given by $1^2 + 5^2 + 10^2 + 5^2 + 1^2 = 252$, out of 1024 total paths. Thus the probability is $\frac{252}{1024} = \frac{63}{256}$.

## Conditional Probability
Consider the probability that for two unbiased dice $D1$ and $D_2$, the probability that $D_1$ is even given that $D_2$ is odd. We restrict our sample space to the events where $D_2$ is odd, and calculate the probability as before. It comes out to be $\frac{1}{2}$.  

Similarly, consider the probability that $D_1 = 2$, given that $D_1 + D_2 = 4$. This has a probability of $\frac{1}{3}$, since the sample space is only $(D_1, D_2) \in \{(1, 3), (2, 2), (3, 1)\}$.  

The confitional probability of an event $E$ given that an event $F$ occurs is denoted $P(E | F)$. It can be calculated as
$$P(E|F) = \frac{P(E \cap F)}{P(F)}.$$

The law of total probability states that $P(E) = P(E|F)P(F) + P(E|F^c)P(F^c)$. This can be proved by noting that $U = F \cup F^c$, and therefore $P(E) = P((E \cap F) \cup (E \cap F^c)) = P(E \cap F) + P(E \cap F^c)$. From this the law follows directly.
