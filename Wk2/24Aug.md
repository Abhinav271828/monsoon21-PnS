---
title: Probability and Statistics (MA6.101)
subtitle: |
          | Monsoon 2021, IIIT Hyderabad
          | 24 August, Tuesday (Lecture 3)
author: Taught by Prof. Pawan Kumar
---

# Probability
Probability is a measure of how likely an event or outcome is.  

## Important Terms
A _random experiment_ is a process by which we observe something uncertain.  
An _outcome_ is a result of a random experiment.  
The _sample space_ is the set of all possible outcomes.  
An _event_ is a subset of the sample space.

## Finite Probability Space
The characteristics of a finite probability space are:
* The number of outcomes is finite.
* Each outcome $i$ has probability $p_i /geq 0$.
* $\sum_i p_i = 1$.

In a finite probability space with equally likely outcomes, each outcome has probability $\frac{1}{N}$, where $N$ is the cardinality of the sample space.

## Axioms of Probability
We assign a _probability measure_ $P(A)$ or $\Pr (A)$ to an event $A$, which is a value between 0 and 1. This value shows how likely the event is.

The axioms of probability are:

* For any event $A$, $P(A) \geq 0$.
* Probability of the sample space $S$ is $P(S) = 1$.
* If $A_1, A_2, \dots$ are disjoint events, then $P(A_1 \cup A_2 \cup A_3 \cup \dots) = P(A_1) + P(A_2) + P(A_3) + \dots$.

From these axioms, we can derive other results:

* $P(A^c) = 1 - P(A)$
* $P(\phi) = 0$
* For any event $A$, $P(A) \leq 1$
* $A \subseteq B \implies P(A) \leq P(B)$
* $P(A - B) = P(A) - P(A \cap B)$
