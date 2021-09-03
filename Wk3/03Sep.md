---
title: Probability and Statistics (MA6.101)
subtitle: |
          | Monsoon 2021, IIIT Hyderabad
          | 03 September, Friday (Lecture 6)
author: Taught by Prof. Pawan Kumar
---

# Probability
## Bayes' Theorem
For any events $E$ and $F$ with nonzero probabilities, we have
$$P(F|E) = \frac{P(E|F)P(F)}{P(E)}.$$
This theorem is provable from the relation between conditional probability and probability of intersection.

P(D|P) = P(P|D)P(D)/P(P) = 0.98*0.005/P(P)
P(P) = P(P|D)P(D) + P(P|D')P(D') = 0.98*0.005 + 0.01*0.995

## The Monty Hall Problem
There are three doors, one of which has a car and the other two have goats. A participant picks a door without opening it; a host then opens another door, revealing a car. Should the participant switch?  

Yes, because  
* if they picked a car first (which had a probability of $\frac{1}{3}$), they will lose (probability of getting car 0)
* if they picked a goat first (which had a probability of $\frac{2}{3}$), they will win (probability of getting car 1)
Therefore the probability of winning if the participant switches is $\frac{1}{3} \cdot 0 + \frac{2}{3} \cdot 1 = \frac{2}{3}$.  

Alternatively, suppose the participant walks away after the host reveals a goat and a new participant comes in. For the new participant, the chance is 50-50; the question is, did the old participant have any information that made one door more likely? Yes, because they knew that the door they picked had only a $\frac{1}{3}$ chance of having a car. Therefore the other door is more likely to have a car.
