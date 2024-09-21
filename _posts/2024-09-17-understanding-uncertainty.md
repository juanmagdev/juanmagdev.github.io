---
layout: post
title: A friendly guide to understanding uncertainty. (In progress)
date: 2024-09-17 16:15:00
description: In this post, I’ll give you a simple, easy-to-follow summary of the key ideas from two important probability courses. No need to worry about complicated proofs—just clear explanations of the essentials. While some basic math knowledge will be helpful, this guide is all about making the main concepts relatable. 
tag: math
thumbnail: 
---
## 1. Introduction

Before diving into the deep world of probability, we should define the spaces we are working with. The following definitions might be confusing to inexperienced readers, but they are essential for the correct understanding of probability functions and random variables. Let’s define a $$ \sigma $$-algebra: 

**Definition 1.0.1.** A set $$ \mathcal{A} $$ of subsets of $$ \Omega $$ is a $$ \sigma $$-algebra if it satisfies:
- $$ \Omega \in \mathcal{A} $$.
- If $$ A \in \mathcal{A} $$, then $$ A^c \in \mathcal{A} $$.
- If $$ \{A_n\}, A_n \in \mathcal{A} $$, then $$ \bigcup_n A_n \in \mathcal{A} $$.

Immediate consequences:
- $$ \emptyset \in \mathcal{A} $$.
- If $$ A_n \in \mathcal{A} $$, then $$ \bigcap_n A_n \in \mathcal{A} $$.
- If $$ A_1, \dots, A_n \in \mathcal{A} $$, then $$ \bigcup_{i=1}^{n} A_i \in \mathcal{A} $$ and $$ \bigcap_{i=1}^{n} A_i \in \mathcal{A} $$.

Now, we introduce the Borel $$\sigma$$-algebra, which is important for understanding measurable sets in real analysis. We then define what it means for a function to be a probability measure and outline some of its immediate consequences. 

**Definition 1.0.2**
Let $$\mathcal{I}$$ be the collection of all intervals. Then $$\sigma(\mathcal{I})$$ defines the Borel $$\sigma$$-algebra. It is denoted by $$\mathcal{B}_{\mathbb{R}}$$ on $$\mathbb{R}$$.

**Definition 1.0.3**
Let $$(\Omega, \mathcal{A})$$ be a measurable space. A probability is a measure $$P: \mathcal{A} \rightarrow [0, +\infty)$$ such that
1. $$P(\Omega) = 1$$.
2. If $$\{A_n\}_{n \in \mathbb{N}} \subset \mathcal{A}$$ with $$A_n \cap A_m = \emptyset$$ for $$n \neq m$$, then
   $$P\left(\bigcup_{n=1}^{\infty} A_n\right) = \sum_{n=1}^{\infty} P(A_n)$$.

Immediate consequences:
- $$P(A^c) = 1 - P(A)$$, $$\forall A \in \mathcal{A}$$.
- $$P(\emptyset) = 0$$.
- If $$A, B \in \mathcal{A}$$, then $$P(A \setminus B) = P(A) - P(A \cap B)$$.
- If $$A, B \in \mathcal{A}$$ and $$A \subset B$$, then $$P(A) \leq P(B)$$.

**Theorem 1.0.4**
Let $$(\Omega, \mathcal{A})$$ be a measurable space. A function $$P: \mathcal{A} \rightarrow [0, +\infty)$$ is a probability measure if it satisfies:
1. $$ P(\Omega) = 1$$.
2. For any sequence $$\{A_n\}_{n \in \mathbb{N}} \subset \mathcal{A}$$ with $$A_n \cap A_m = \emptyset$$ if $$n \neq m$$, then
   $$P\left(\bigcup_{i=1}^{n}A_{i}\right)=\sum_{i=1}^{n}P(A_{i}).$$
3. If $$\{A_n\}_{n \in \mathbb{N}} \subset \mathcal{A}$$ and $$\lim_{n \to \infty} A_n = \emptyset$$, then $$\lim_{n \to \infty} P(A_n) = 0$$.


Independence is a fundamental concept in probability theory, which describes a situation where the occurrence of one event does not affect the probability of another event.

**Definition 1.0.5**
Let $$(\Omega, \mathcal{A}, P)$$ be a probability space. Two events $$A, B \in \mathcal{A}$$ are independent if 
$$P(A|B) = P(A)$$ and $$P(B) > 0.$$
Recall that 
$$P(A|B) = \frac{P(A \cap B)}{P(B)}$$
provided that $$P(B) > 0.$$

‎
‎ 

## 2. Aleatories Variables
**Definition 2.1.1.** Let $$(\Omega, \mathcal{A})$$ be a probabilizable space. A function $$X : \Omega \longrightarrow \mathbb{R}$$ is called a random variable if $$X^{-1}(B) \in \mathcal{A}$$ for every $$B \in \mathcal{B}_1$$.

**Definition 2.1.2.** Let $$(\Omega, \mathcal{A})$$ be a probabilizable space. A function $$X : \Omega \longrightarrow \mathbb{R}$$ is called a random variable if $$X^{-1}((-\infty, a]) \in \mathcal{A}$$ for every $$a \in \mathbb{R}$$.

**Theorem 2.2.1.** Let $$X$$ and $$Y$$ be random variables defined on $$(\Omega, \mathcal{A})$. Then
1. $$A = \{\omega \in \Omega : X(\omega) < Y(\omega)\} \in \mathcal{A}$$.
2. $$B = \{\omega \in \Omega : X(\omega) \leq Y(\omega)\} \in \mathcal{A}$$.
3. $$C = \{\omega \in \Omega : X(\omega) = Y(\omega)\} \in \mathcal{A}$$.


**Proposition 2.2.2.** Let $$X$$ and $$Y$$ be random variables defined on $$(\Omega, \mathcal{A})$$. Then:
1. Given $$a \in \mathbb{R}$$, we have that $$Z = aX$$ is a random variable.
2. $$X + Y$$ is a random variable.
3. $$X^2$$ is a random variable.
4. $$|X|$$ is a random variable.
5. $$X \cdot Y$$ is a random variable.

**Theorem 2.2.3.** Let $$X$$ be a random variable defined on $$(\Omega, \mathcal{A})$$. Let $$g: \mathbb{R} \longrightarrow \mathbb{R}$$ be a function such that $$g^{-1}(B) \in \mathbb{B}_1$$ for all $$B \in \mathbb{B}_1$$. Then $$Y = g(X)$$ is also a random variable defined on $$(\Omega, \mathcal{A})$$.


‎
‎ 

## 3. Probability Distribuition Function
**Definition 3.1.1.** A function $$F: \mathbb{R} \longrightarrow [0,1]$$ is called a distribution function if it satisfies:
1. $$F$$ is non-decreasing.
2. $$F$$ is right-continuous, that is,
    $$
    \lim_{x \rightarrow a^{+}} F(x) = F(a) \text{ for all } a \in \mathbb{R}
    $$.
3. 
    $$
    \lim_{x \rightarrow -\infty} F(x) = 0 \quad \text{and} \quad \lim_{x \rightarrow +\infty} F(x) = 1
    $$.


**Proposition 3.1.2.** Let $$P$$ be a probability measure defined on $$\left(\mathbb{R}, \mathbb{B}_1\right)$$. The function $$F: \mathbb{R} \longrightarrow [0,1]$$ given by $$F(x) = P((-\infty, x])$$ for all $$x \in \mathbb{R}$$ is a probability distribution.


**Definition 3.2.1.** Let $$X$$ be a random variable defined on $$(\Omega, \mathcal{A}, P)$$, let $$P_X$$ be the probability induced by $$X$$ on $$\left(\mathbb{R}, \mathbb{B}_1\right)$$, and let $$F_X$$ be the probability distribution function associated with $$P_X$$. We define:
- The set of jump points of $$F_X$$ as
$$
D_X = \left\{ x \in \mathbb{R} : P_X(\{x\}) > 0 \right\}
$$
- The support of $$X$$ (or the support of the distribution) as
$$
S_X = \{ x \in \mathbb{R} : F(x + \varepsilon) - F(x - \varepsilon) > 0 \}
$$
for all $$\varepsilon > 0$$.

**Theorem 3.2.2.** The set $$D_X$$ is at most countably infinite.


## 4. Aleatories Variables Classification
