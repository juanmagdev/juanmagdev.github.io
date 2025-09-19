---
layout: page
title: Mathematics Thesis: Henstock–Kurzweil Integral
description: My Bachelor Thesis (TFG) for the Mathematics degree at Universidad de Málaga, focused on the Henstock–Kurzweil integral.
importance: 2
category: academics
---

  <p style="text-align: center; font-style: italic;">
  📄 <a href="/assets/pdf/Garcia_Delgado_Juan_Manuel_Grado_en_Matematicas.pdf" target="_blank">
  Download the full thesis (PDF)
  </a>
  </p>

---

## About this work

This page presents my **Bachelor Thesis (Trabajo de Fin de Grado** for the **Mathematics degree** at the [Universidad de Málaga](https://www.uma.es), Spain.  
The thesis, written in Spanish, is titled:

> **“La integral de Henstock–Kurzweil”**

It received a final grade of _9.8/10_ and was awarded _Matrícula de Honor_ (highest distinction).

Here I provide an English version of the Introduction and the foundational definitions and concepts used in the construction of the Henstock–Kurzweil integral. The full text (in Spanish) can be downloaded above.

The complete thesis is structured as follows:

- **Chapter 1: The Henstock–Kurzweil Integral**  
  Motivation and formal construction of the Henstock Kurzweil integral using tagged partitions and gauges. Proof of basic properties and a version of the Fundamental Theorem of Calculus.

- **Chapter 2: Henstock vs. Lebesgue Integration**  
  Comparison with Lebesgue’s theory. Saks–Henstock Lemma, properties of Henstock Kurzweil primitives, measure theory preliminaries, Lusin’s theorem, and improper integrals.

- **Chapter 3: Convergence Theorems**  
  Study of uniform, monotone, and dominated convergence theorems. Introduction of $$\mathcal{P}$$-Cauchy sequences of functions and their use as a convergence criterion.

- **Chapter 4: The classes** $$AC\delta$$ **and** $$ACG\delta$$
  Definition of the function classes $$AC*\delta$$ (absolutely continuous on $$\delta$$-fine partitions) and $$ACG*\delta$$ (generalized $$\delta$$-absolute continuity), and their characterization as primitives of Henstock–Kurzweil integrable functions.

---

## Introduction

At the beginning of the 20th century, the French mathematician Henri Léon Lebesgue introduced a new theory of integration that responded to the growing needs of mathematical analysis, greatly extending the scope of the Riemann integral.  
 The Lebesgue integral made it possible to integrate much more general functions—such as the well-known Dirichlet function—and facilitated the formulation and proof of powerful theorems, especially those concerning the interchange of limit and integral. Throughout the 20th century, the Lebesgue integral became a central tool, largely replacing the Riemann integral in advanced analysis.

However, the construction of the Lebesgue integral is considerably more involved than that of Riemann: it requires first building measure theory on the Borel sets of the real line, and only then defining the integral. Although powerful, this approach is technically demanding and less direct than the definition of the Riemann integral.

Despite its many advantages, the Lebesgue integral has certain limitations. It is absolutely integrable: a function $$f$$ is Lebesgue integrable if and only if $$|f|$$ is also integrable. This condition excludes some interesting functions. Moreover, the connection with differentiation is less natural: to apply the Fundamental Theorem of Calculus one needs monotone, bounded variation, or otherwise restricted functions.

To overcome these limitations, other integration theories arose—such as the Denjoy and Perron integrals—but their constructions are technically more complicated and less intuitive.

Within this context, Henstock and Kurzweil developed an integral that surpasses some of the limitations of the Lebesgue integral while retaining a simple, elegant, Riemann-like definition. The Henstock–Kurzweil integral recovers the intuitive idea of Riemann sums while extending its scope considerably.

<div class="row mt-3">
  <div class="col-12 d-flex justify-content-center">
    {% include figure.liquid loading="eager" path="assets/img/thesis-mathematics/HK.jpeg" class="img-fluid rounded z-depth-1" %}
  </div>
</div>

---

## Motivation

Traditionally, the two major constructions of the concept of integral in real analysis have been the Riemann and Lebesgue integrals.  
The former relies on a clear geometric intuition—the sum of the areas under the curve—but fails for functions with unbounded discontinuities or strong oscillations.  
The latter greatly extends the class of integrable functions by using measure theory, ensuring excellent convergence properties, but at the cost of a more technical and less intuitive construction.

For example, there are differentiable functions whose derivative is **not** Lebesgue integrable. Consider:

$$
F(x)=
\begin{cases}
x^2\sin\!\left(\frac{1}{x^2}\right), & x\ne 0, \\
0, & x = 0.
\end{cases}
$$

Then $$F$$ is differentiable on $$\mathbb{R}$$ but

$$
F'(x)=
\begin{cases}
2x\sin\!\left(\frac{1}{x^2}\right)-\frac{2}{x}\cos\!\left(\frac{1}{x^2}\right), & x\ne 0, \\
0, & x = 0,
\end{cases}
$$

and $$F'\notin L^1([a,b])$$ for any interval containing $$0$$.  
This seems paradoxical, as derivatives are the “natural” integrands for the Fundamental Theorem of Calculus.

Another example is $$f(x)=\frac{\sin x}{x}$$: its improper Riemann integral over $$\mathbb{R}$$ converges (and equals $$\pi$$ using complex analysis), but its absolute value is not Lebesgue integrable:

$$
\int_{\mathbb{R}}\left|\frac{\sin x}{x}\right|\,dx = \infty.
$$

Such examples show that the Lebesgue integral, although very powerful, fails to integrate some “natural” functions. Moreover, classical rules like substitution or integration by parts—easy under Riemann—become more intricate under Lebesgue.

The **Henstock–Kurzweil integral** solves these issues without using measure theory. It refines the notion of Riemann partition by introducing **gauge functions** $$\delta$$ that adapt the size of subintervals to the local behavior of the integrand.  
This allows integrating every derivative (even those not Lebesgue integrable) and some improper integrals not classically defined. Thus, the Henstock–Kurzweil integral is both more general than Lebesgue’s and closer in spirit to the original ideas of calculus.

---

## Construction of the Henstock–Kurzweil Integral

We now present the basic definitions, following mainly _The integrals of Lebesgue, Denjoy, Perron, and Henstock_ by Gordon [1994].

**Definition (Gauge):**  
Let $$I=[a,b]$$. A **gauge** is a positive function $$\delta:I\to (0,\infty)$$.

---

**Definition (Tagged interval subordinated to a gauge):**  
A **tagged interval** is a pair $$(\xi,[c,d])$$ with $$[c,d]\subseteq[a,b]$$ and $$\xi\in[c,d]$$.  
It is said to be **$$\delta$$-fine** if
\[
[c,d]\subseteq (\xi-\delta(\xi),\ \xi+\delta(\xi)).
\]

---

**Definition (Tagged partition):**  
A **tagged partition** $$\mathcal{P}=\{(\xi*i,[t_i,t*{i+1}]):0\le i\le n\}$$ of $$I=[a,b]$$ is a finite collection of pairwise disjoint subintervals covering $$I$$.  
It is **$$\delta$$-fine** if each tagged interval is $$\delta$$-fine.

---

**Lemma (Cousin):**  
For every gauge $$\delta$$ on $$I=[a,b]$$ there exists a $$\delta$$-fine tagged partition $$\mathcal{P}$$ of $$I$$.

---

**Definition (Riemann sum):**  
Given $$f:I\to\mathbb{R}$$ and a tagged partition $$\mathcal{P}=\{(\xi*i,[t_i,t*{i+1}])\}$$:
\[
\mathcal{S}(f,\mathcal{P}) = \sum*{i=0}^n f(\xi_i)(t*{i+1}-t_i).
\]

---

**Definition (Henstock–Kurzweil integral):**  
We say that $$f:I\to\mathbb{R}$$ is **Henstock–Kurzweil integrable** on $$I$$ with integral $$L$$ if for every $$\varepsilon>0$$ there exists a gauge $$\delta$$ such that for every $$\delta$$-fine tagged partition $$\mathcal{P}$$:
\[
\big|\mathcal{S}(f,\mathcal{P}) - L\big| < \varepsilon.
\]

We write
\[
(H)\int_a^b f = L.
\]

Every Riemann integrable function is also Henstock–Kurzweil integrable with the same value, so the Henstock Kurzweil integral strictly extends the Riemann one.

---

## Academics

- **Degree:** Mathematics (Double Degree in Mathematics and Computer Engineering)
- **Institution:** [Universidad de Málaga](https://www.uma.es)
- **Year:** 2025
- **Department:** Departamento de Análisis Matemático, Estadística e Investigación Operativa, y Matemática Aplicada
- **Area:** Mathematical Analysis
- **Type:** Bibliographic
- **Modality:** Individual
- **Pages (main content):** 56
- **Author:** Juan Manuel García Delgado
