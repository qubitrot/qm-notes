---
title: Projectors
nav-order: 4 
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
\newcommand{\cconj}[1]{\overline{#1}}
$$

# Projectors

### Definition
let $\H$ be a seperable Hilbert space. Given $\psi \in \H$ and
a unit vector $e \in \H$, then

$$ \psi_\parallel := \inner{e,\psi}e $$

is called the **projection** of $\psi$ to $e$, and

$$ \psi_\bot := \psi - \psi_\parallel $$

### Theorem
Let $\psi \in \H$ and $\{e_i\}_{i\in I}$ be an orthonormal set in 
$\H$ for at most countable $I$. Then

1. $\psi$ can be decomposed:
   
   $$ \psi = \psi_\bot + \psi_\parallel, $$
   
   where
   
   $$ \psi_\parallel = \sum_{i=I}\inner{e_i,\psi}e_i, $$
   
   and 
   
   $$ \inner{\psi_\bot,e_j} = 0 \;\;\;\; \forall j \in I $$

2. Pythagoras holds:

   $$ \norm{\psi}^2 = \norm{\psi_\bot}^2 + 
      \sum_{i \in I}\abs{\inner{e_i,\psi}}^2 $$

3. For any $\gamma \in \spann\{e_i\}$,

   $$ \norm{\psi - \gamma} \ge \norm{\psi_\parallel} $$

   with equality iff $\gamma = \psi_\parallel$.

### Proof
At first, assume $I$ is finite with max index $N$. Then
1. The sum exists because $I$ is finite. We need only check

   $$
   \begin{align*}
   \inner{\psi_\bot,e_j} 
   &= \inner{\psi - \sum_{i=1}^N\inner{e_i,\psi}e_i, e_j} \\
   &= \inner{\psi,e_j} - \sum_{i=1}^N\cconj{\inner{e_i,\psi}}\delta_{ij} \\
   &= \inner{\psi,e_j} - \cconj{\inner{e_j,\psi}} = 0.
   \end{align*}
   $$

2. Trivial for finite $I$.
3. $$
   \begin{align*}
   \norm{\psi - \gamma}^2
   &= \norm{\psi_\bot + \psi_\parallel  - \gamma}^2 \\
   &= \norm{\psi_\bot + \sum_{i=1}^N\left( 
      \inner{e_i,\psi}e_i - \gamma_ie_i \right)}^2 \\
   &= \norm{\psi_\bot} + \sum_{i=1}^N\abs{\inner{e_i,\psi} - \gamma_i}^2
   \end{align*}
   $$

We need to extend this to countable $I$. That is, we need to show that this
limit exists:

$$ \psi_\parallel = \lim_{N\to\infty}\sum_{i=1}^N\inner{e_i,\psi}e_i $$

It is sufficient to show that the sequence of partial sums is Cauchy.
Consider

$$ \norm{\sum_{i=n}^N\inner{e_i,\psi}e_i}^2 
= \sum_{i=n}^N\abs{\inner{e_i,\psi}}^2
\le \norm{\psi}^2.  $$

Since the sequence is bounded and monotonically increasing, it converges, and
is therefore Cauchy. Thus $\psi_\parallel \in \H$.

### Lemma
A closed subset $M \subseteq \H$ of a complete space is complete.

### Proof
Consider a Cauchy sequence $\{\psi_n\} \in M$. Since $M \subseteq \H$, 
$\{\psi_n\}$ converges in $\H$. Then since $M$ is closed, $\H
\setminus M$ is open. Suppose $\psi := \lim\psi_n \notin M$, then there exists 
an open neighborhood $U \subseteq \H \setminus M$ of $\psi$. But then

$$ \exists N \in \N, \forall n \ge N : \psi_n \in U. $$

This is a contradiction since $U \cap M = \emptyset$.

### Corollary
A closed linear subset $M$ of a Hilbert space $\H$ is a sub-Hilbert space. 
If $\H$ is seperable then $M$ is too.

## Orthogonal projections

Let $M \subseteq \H$ be a linear subspace of $\H$. Then the set 

$$ M^\bot := \{ \psi \in \H\;|\; 
   \forall \mu \in M : \inner{\mu,\psi} = 0 \} $$

is called the **orthogonal complement** of $M$ in $\H$. 

### Theorem
$M^\bot$ is a closed linear subspace of $\H$ (and therefore a sub-Hilbert Space).

### Definition
Let $M$ be a closed linear subspace of $\H$. The map

$$
\begin{align*}
P : \H&\to M \\
    \psi &\mapsto \psi_\parallel
\end{align*}
$$

is called the **orthogonal projector** to the sub-Hilbert space $M$.
Properties:

1. $P^2 = P$,
2. $\forall \psi, \phi \in \H: 
    \inner{P\psi,\phi} = \inner{\psi,P\phi}$,
3. $P \in \mathcal{L}(\H,M)$.

### Theorem
Let $P \in \mathcal{L}(\H,\H)$ have the properties

1. $P^2 = P$,
2. $\forall \psi, \phi \in \H : 
    \inner{P\psi,\phi} = \inner{\psi,P\phi}$,

then $P$ is the orthogonal projector onto $P(\H)$, which is
a sub-Hilbert space.

### Theorem: Riesz Representation Theorem
Consider $\lambda \in \H$. Define the bounded linear map

$$
\begin{align*}
l_\lambda : \H     &\to \C \\
            \alpha &\mapsto \inner{\lambda,\alpha}
\end{align*}
$$

Any $l \in \H^*$ can be uniquely represented by some $l_\lambda$.

