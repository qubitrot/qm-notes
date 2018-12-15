---
title: Measure Theorey
nav-order: 5
---

$$
\newcommand{\R}{\mathbb{R}}
\newcommand{\C}{\mathbb{C}}
\newcommand{\N}{\mathbb{N}}
\newcommand{\H}{\mathcal{H}}
\newcommand{\inner}[1]{\langle#1\rangle}
\newcommand{\norm}[1]{\lVert#1\rVert}
\newcommand{\abs}[1]{\lvert#1\rvert}
\newcommand{\Tr}[1]{\text{Tr}#1}
\renewcommand{\diff}[1]{\mathop{}\!\mathrm{d}#1}
\newcommand{\spann}{\text{span}\,}
\newcommand{\slim}{\text{s-lim}}
\newcommand{\wlim}{\text{w-lim}}
\newcommand{\preim}{\text{preim}}
\newcommand{\cconj}[1]{\overline{#1}}
$$

# Measure Theory

### Definition
let $M$ be a non-empty set. Then a collection of subsets $\sigma \subseteq 
\mathcal{P}(M)$ is called a **$\sigma$-algebra** if

1. $M \in \sigma$,
2. If $A \in \sigma$, then $M \setminus A \in \sigma$, and
3. $\sigma$ is closed under countable unions.

A set $A\in\sigma$ is called a **measurable set** in $M$, and 
$(M,\sigma)$ is called a **measurable space**.

### Definition
A **measure** $\mu : \sigma \to \overline{\R}^+_0$ on a measurable space
$(M,\sigma)$ is a map satisfying

2. $\mu(\emptyset) = 0$,
1. If $A_1,A_2,...\in\sigma$ are pairwise disjoint, then 

   $$ \mu\left(\bigcup A_n\right) = \sum_n \mu(A_n).  $$      

A space $(M,\sigma,\mu)$ is called a **measure space**.

### Definition
let $M$ be a measure space. The measure $\mu$ is called **finite** if 
there exists a sequence $A_1,A_2,...\in \sigma$ with $\cup A_n = M$ such that 
for all $n$, $\mu(A_n)$ is finite.

## Borel $\sigma$-Algebras.

### Theorem
The "smallest" $\sigma$-algebra for a set $M$ that contains a collection of 
subsets $\mathcal{E} \subseteq \mathcal{P}(M)$ is

$$ \sigma(\mathcal{E}) := \bigcap_{\sigma \in \Sigma(\mathcal{E})} \sigma $$

where $\Sigma(\mathcal{E})$ is the set of all $\sigma$-algebras containing 
$\mathcal{E}$, and is called the **generating set**.

### Theorem
Every $\sigma$-algebra can be written as $\sigma = \sigma(\mathcal{E})$ for
some set $\mathcal{E}$.

### Definition
Let $(M,O)$ be a topological space. Then $\sigma(O)$ is called the **Borel 
$\sigma$-algebra** of $(M,O)$.

## The Lebesgue Measure.

### Defintion
Consider the measurable space $(\R^d, \sigma)$, with $\sigma = 
\sigma(O_{std})$. The **Lebesgue measure** is the unique map

$$
\begin{align*}
\lambda : \sigma &\to \overline{\R}_0^+ \\
          E &\mapsto \inf_I\sum_{k=1}^\infty(I_{kb}-I_{ka})
\end{align*}
$$

where $I$ is a sequence of open intervals such that

$$ E \subseteq \bigcup_{k=1}^\infty I_k.  $$

## Measurable Maps

### Definition
Let $M$ and $N$ be measurable spaces. A map $f : M \to N$ is called
**measurable* if for all $A\in\sigma_N$,

$$ \preim_f(A) \in \sigma_M.  $$

### Lemma
To show that $f$ is measurable, it is sufficient to check whether

$$ \forall A\in\mathcal{E} : \preim_f(A) \in \sigma_M, $$

where $\mathcal{E}$ is a generating set of $\sigma_N$.

### Corollary
The following is true:

1. Any continuous map is measuable w.r.t. the Borel $\sigma$-algebra.
2. Any monotonous map $f : \R \to \R$ is measurable.

### Theorem
The composition $f \circ g$ of two measurable maps is measurable.

## Push-forward of a Measure

### Definition
Let $(M,\sigma,\mu)$ be a measure space, and let $(N,\tau)$ be a measurable
space. Further, let $f : M \to N$ be a measurable map, then the **push-forward** 
$f_*\mu$ is a measure on $(N,\tau)$ defined by

$$
\begin{align*}
f_*\mu : \tau &\to \R_0^+ \\
A &\mapsto \mu(\preim_f(A)).
\end{align*}
$$

