---
title: Probability and Statistics (MA6.101)
subtitle: |
          | Monsoon 2021, IIIT Hyderabad
          | Assignment 1
author: Abhinav S Menon
---

# Problem 1
Two fair dice are rolled. The events defined are
$$A = \text{sum of the two dice equals 3},$$  
$$B = \text{sum of the two dice equals 8},$$  
$$C = \text{at least one of the two dice shows a 2}.$$

All events have $36 = 6 \times 6$ possible outcomes.  

$A$ has 2 favourable outcomes ($\{(1,2), (2,1)\}$) $\implies P(A) = \frac{1}{18}$.  

$B$ has 5 favourable outcomes ($\{(2,6), (3,5), (4,4), (5,3), (6,2)\}$) $\implies P(B) = \frac{5}{36}$.  

$C$ has 11 favourable outcomes ($\{(2,i) | 1 \leq i \leq 6\} \cup \{(j,2) | 1 \leq j \leq 6\}$) $\implies P(C) = \frac{11}{36}$.

## Question 1
By Bayes' Law,
$$P(A \mid C) = \frac{P(A \cap C)}{P(C)}.$$

Now, $A \subset C$, and therefore $P(A \cap C) = P(A) = \frac{1}{18}$. From this we get
$$P(A \mid C) = \frac{\frac{1}{18}}{\frac{11}{36}} = \frac{2}{11}.$$

## Question 2
As above,
$$P(B \mid C) = \frac{P(B \cap C)}{P(C)}.$$

We see that $B \cap C$ has as its favourable outcomes $\{(2,6), (6,2)\}$. This means that $P(B \cap C) = \frac{1}{18}$. Thus,
$$P(B \mid C) = \frac{\frac{1}{18}}{\frac{11}{36}} = \frac{2}{11}.$$

## Question 3
We saw above that $P(A \cap C) = \frac{1}{18}$, which is not the same as $P(A) \cdot P(C) = \frac{1}{18} \cdot \frac{11}{36} = \frac{11}{648}$. Therefore $A$ and $C$ are not independent.  

We saw above that $P(B \cap C) = \frac{1}{18}$, which is not the same as $P(B) \cdot P(C) = \frac{5}{36} \cdot \frac{11}{36} = \frac{55}{1296}$. Therefore $B$ and $C$ are not independent.

# Problem 2
Alex is one of two children, and may be a girl or a boy. We assume that the probability of a child being a girl or a boy is 50-50. Let Alex's sibling be called Bobby.  

Therefore, we have $P(\text{Alex is a girl}) = P(\text{Alex is a boy}) = \frac{1}{2}$, and $P(\text{Bobby is a girl}) = P(\text{Bobby is a boy}) = \frac{1}{2}$.  

Similarly, the set of equiprobable outcomes is $\{\text{Alex and Bobby are both boys}$, $\text{Alex is a boy and Bobby is a girl}$, $\text{Alex is a girl and Bobby is a boy}$,  
$\text{Alex and Bobby are both boys}\}$.

## Question 1
As in Problem 1,
$$P(\text{Bobby is a girl} \mid \text{Alex is a girl}) = \frac{P(\text{Alex and Bobby are both girls)}}{P(\text{Alex is a girl})}.$$

We have the probabilities of both the events, so we can compute
$$P(\text{Bobby is a girl} \mid \text{Alex is a girl}) = \frac{\frac{1}{4}}{\frac{1}{2}} = \frac{1}{2}.$$

## Question 2
As above,
$$P(\text{Bobby is a girl} \mid \text{Alex is a boy}) = \frac{P(\text{Alex is a boy and Bobby is a girl)}}{P(\text{Alex is a boy})}.$$

Again, we have the probabilities of both the events, so we can compute
$$P(\text{Bobby is a girl} \mid \text{Alex is a boy}) = \frac{\frac{1}{4}}{\frac{1}{2}} = \frac{1}{2}.$$

# Problem 3
We have 100 red and 100 blue candies, and 2 jars. We must fill the candies in the jars and pick a candy randomly from a randomly selected jar.  

To maximise the probability of drawing a blue candy, we can place 1 blue candy in one of the jars (jar 1) and fill the other one (jar 2) with the remaining 199 candies.  

Let $B$ be the event of picking a blue candy, and let $J_i$ be the event of picking jar $i$.  

By the law of total probability,
$$P(B) = P(B \mid J_1) \cdot P(J_1) + P(B \mid J_2) \cdot P(J_2).$$

From this, we get $P(B) = \frac{1}{1} \cdot \frac{1}{2} + \frac{99}{199} \cdot \frac{1}{2} \approx 0.749$. This is the maximum value.

# Problem 4
We have three coins whose probabilities of heads are 0.2, 0.4 and 0.6 respectively. One is chosen (we assume randomly) and tossed for times.  

Let $C_1$ be the event that the coin with probability 0.2 is chosen.  
Let $C_2$ be the event that the coin with probability 0.6 is chosen.  
Let $C_3$ be the event that the coin with probability 0.4 is chosen.

## Question 1
By the law of total probability,
$$P(\text{HTHT}) = P(\text{HTHT} \mid C_1) \cdot P(C_1) + P(\text{HTHT} \mid C_2) \cdot P(C_2) + P(\text{HTHT} \mid C_3) \cdot P(C_3).$$

We know that $P(C_i) = \frac{1}{3}$.  

Now, we can say that
$$P(\text{HTHT} \mid C_1) = 0.2 \times 0.8 \times 0.2 \times 0.8 = 0.0256,$$
$$P(\text{HTHT} \mid C_2) = 0.6 \times 0.4 \times 0.6 \times 0.4 = 0.0576,$$
and
$$P(\text{HTHT} \mid C_1) = 0.4 \times 0.6 \times 0.4 \times 0.6 = 0.0576.$$

Substituting, we get
$$P(\text{HTHT}) = \frac{1}{3} \times (0.0256 + 0.0576 + 0.0576) = \frac{0.1408}{3} \approx 0.0469.$$

## Question 2
From Bayes' Law, we know that
$$P(C_1 \mid \text{HTHT}) = \frac{P(C_1 \cap \text{HTHT})}{P(\text{HTHT})} = \frac{P(\text{HTHT} \mid C_1) \cdot P(C_1)}{P(\text{HTHT})}.$$

In this expression, we can substitute all values from Question 1 to obtain
$$P(C_1 \mid \text{HTHT}) = \frac{0.0256 \times \frac{1}{3}}{0.1408 \times \frac{1}{3}} = \frac{0.0256}{0.1408} = 0.\overline{18}.$$

# Problem 5
We know that $P(A) = 0.45$, $P(A \cap B) = 0.15$, and $P(A^c \cap B^c) = 0.45$.  

By the Inclusion-Exclusion Principle, we have
$$P(A \cup B) = P(A) + P(B) - P(A \cap B).$$

Further, we know by de Morgan's Law that $P(A^c \cap B^c) = 1 - P((A^c \cap B^c)^c) = 1 - P(A \cup B)$. This gives us $P(A \cup B) = 1 - 0.45 = 0.55$.  

Rearranging and substituting, we get
$$P(B) = P(A \cup B) + P(A \cap B) - P(A) = 0.55 + 0.15 - 0.45 = 0.25.$$

# Problem 6
We know that $A$ and $C$ are independent, $B$ and $C$ are independent and $A$ and $B$ are disjoint.  
Further, we know that $P(A \cup C) = \frac{2}{3}$, $P(B \cup C) = \frac{3}{4}$, and $P(A \cup B \cup C) = \frac{11}{12}$.  

Using the Principle of Inclusion-Exclusion, we know that
$$P(A \cup B \cup C) = P(A) + P(B) + P(C) - P(A \cap B) - P(B \cap C) - P(C \cap A) + P(A \cap B \cap C),$$
in which we know that $P(A \cap B) = P(A \cap B \cap C) = 0$ (since $A \cap B = \phi$). Therefore,
$$P(A \cup B \cup C) = P(A) + P(B) + P(C) - P(B \cap C) - P(C \cap A).$$

Now, the independence conditions allow us to conclude that
$$P(A \cup B \cup C) = P(A) + P(B) + P(C) - P(B)P(C) - P(C)P(A),$$
which we can substitute to get
$$\frac{11}{12} = P(A) + P(B) + P(C) - P(B)P(C) - P(C)P(A).$$

Further, we know that $P(A \cup C) = \frac{2}{3} = P(A) + P(C) - P(A)P(C)$. Subtracting these two equations,
$$\frac{11}{12} - \frac{2}{3} = P(B) - P(B)P(C).$$

We also know that $P(B \cup C) = \frac{3}{4} = P(B) + P(C) - P(B)P(C)$. Subtracting again,
$$\frac{11}{12} - \frac{2}{3} - \frac{3}{4} = -P(C).$$

From this we have $P(C) = \frac{1}{2}$, using which we can get $P(A) = \frac{1}{3}$ and $P(B) = \frac{1}{2}$.

# Problem 7
A biased coin has a probability of $p$ of coming up heads. Let $H_n$ be the event of a head coming up on the $n^\text{th}$ toss (similarly $T_n$). Let $E$ be the event that the first head comes up at an even-numbered toss.  

Clearly, $P(H_i) = p$, and $P(T_i) = 1-p$ for all $i$.  

By the total probability theorem,
$$P(E) = P(T_1)P(H_2) + P(T_1)P(T_2)P(T_3)P(H_4) + \cdots$$
which is equal to
$$(1-p) \cdot p + (1-p)^3 \cdot p + \cdots.$$

This is a geometric series with first term $p(1-p)$ and common ratio $(1-p)^2$. Its infinite sum, therefore, is
$$\frac{p(1-p)}{1 - (1-p)^2} = \frac{1-p}{2-p}.$$
which is the desired probability.

# Problem 8
We know that $A$ and $B$ are conditionally independent given each $C_i$, where the $C_i$ form a mutually exclusive and exhaustive partition of $S$. Further, $B$ is independent of each $C_i$.  

From the total probability theorem,
$$\begin{split}
P(A \cap B) &= \sum_{i = 1}^M P(A \cap B  \mid  C_i)P(C_i) \\
&= \sum_{i=1}^M P(A \mid C_i)P(B \mid C_i)P(C_i) \text{    [conditional independence]} \\
&= \sum_{i=1}^M P(A \mid C_i)P(B \cap C_i) \text{    [Bayes' Theorem]} \\
&= \sum_{i=1}^M P(A \mid C_i)P(C_i)P(B) \text{    [independence]} \\
&= P(B) \cdot \sum_{i=1}^M P(A \mid C_i)P(C_i) \\
&= P(B) \cdot P(A) \text{    [total probability theorem]} \end{split}.$$

Thus, $A$ and $B$ are independent, QED.

# Problem 9
Let $D$ be the event that a person has the disease, and $+$ the event that they test positive.  

We are given that $P(D) = \frac{1}{1000}$, $P(+ \mid D) = \frac{99}{100}$, and $P(+ \mid D^c) = \frac{5}{1000}$.  

We need to find how likely a person is to have the disease given that they test positive, *i.e.*, $P(D \mid +)$. By Bayes' Theorem,
$$P(D \mid +) = \frac{P(+ \mid D) \cdot P(D)}{P(+)} = \frac{P(+ \mid D) \cdot P(D)}{P(+ \mid D) \cdot P(D) + P(+ \mid D^c) \cdot P(D^c)}.$$
Substituting, we get
$$\begin{split}
P(D \mid +) &= \frac{\frac{99}{100} \cdot \frac{1}{1000}}{\frac{99}{100} \cdot \frac{1}{1000} + \frac{5}{1000} \cdot \frac{999}{1000}} \\
&= \frac{990}{990 + 4995} \\
&\approx 0.165 .\end{split}$$

# Problem 10
We know that the man is reporting a two. Further, we know that he speaks the truth with a probability of $\frac{3}{5}$.  

Therefore, the probability that the dice returned a two is the same as that of him telling the truth, *i.e.* $\frac{3}{5}$.
