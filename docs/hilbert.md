---
title: Seperable Hilbert Spaces
nav-order: 3
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
\newcommand{\spann}{\text{span}}
\newcommand{\slim}{\text{s-lim}}
\newcommand{\wlim}{\text{w-lim}}
\newcommand{\cconj}[1]{\overline{#1}}
$$

# Seperable Hilbert Spaces

In quantum mechanics (but *not* QFT) we need only care about seperable
Hilbert spaces.

### Definition
A **(complex) Hilbert space** $\H$ is a Banach space equipted with a
sesquilinear inner product $\inner{,} : \H \times \H \to \C$ 
that induces the norm. These conditions are
1. $\inner{\phi,\psi} = \cconj{\inner{\psi,\phi}}$,
2. $\inner{,}$ is linear in its second argument,
3. $\inner{\psi,\psi} \ge 0 \; \forall\psi\in\H$ with equality 
   iff $\psi = 0$,
4. $\norm{\psi} = \sqrt{\inner{\psi,\psi}}$.

### Theorem
A norm $\norm{\cdot} : V \to \R$ is induced by a sesquilinear inner product
if and only if the parallelogram identity

$$ \norm{f+g}^2 + \norm{f-g}^2 = 2\norm{f}^2 + 2\norm{g}^2 
   \;\; \forall f,g \in V $$

holds. In this case, the inner product can be explicitly constructed as

$$ \inner{f,g} := \frac{1}{4}\left(\norm{f+g}^2+\norm{f-g}^2
                                   +i\norm{f-ig}^2-i\norm{f+ig}^2\right). $$

This is called the \defined{polarization identity}.

### Theorem: The Cauchy-Schwarz inequality

$$ \abs{\inner{\psi,\phi}} \le \norm{\psi}\norm{\phi}.  $$

### Definition
A Hilbert space is **seperable** if it has a Schauder basis $S$ which
is 
1. countable, and
2. orthonormal: $\inner{e_i,e_j} = \delta_{ij}$.

### Theorem
The space $l^2(\N)$ of all square-summable sequences in $\C$,

$$ l^2(\N) := \{ a : \N \to \C \;\Big|\; \sum_{i=1}^\infty\abs{a_i}^2 < \infty \}, $$

forms a seperable Hilbert space with the inner product

$$ \inner{a,b} := \sum_{i=1}^\infty \cconj{a_i} b_i.  $$

### Proof
$l^2(\N)$ trivally forms a vector space with pointwise operations, and the 
inner product is evidently sesquilinear. The induced norm is 

$$ \norm{\psi}^2 = \sum_{i=0}^\infty \abs{a_i}^2.  $$

We need to demonstrate that the space is complete with respect to this norm.
Let $\{\alpha_n\}$ be a Cauchy sequence in $l^2(\N)$. The candiate limit is
$\alpha := \lim_{n\to\infty} \alpha_n$.

$$
\begin{align*}
\norm{\alpha}^2 
    &= \lim_{N\to\infty}\sum_{i=1}^N\lim_{n\to\infty}\abs{\alpha_{ni}}^2 \\
    &= \lim_{n\to\infty}\lim_{N\to\infty}\sum_{i=1}^N\abs{\alpha_{ni}}^2 \\
    &= \lim_{n\to\infty}\norm{\alpha_n}^2.
\end{align*}
$$

Since $\alpha_n$ is Cauchy in $l^2(\N)$, $\norm{\alpha_n}^2$ is Cauchy in $\R$,
and therefore converges. It follows from the first line that $\alpha$
is square-summable and in $l^2(\N)$.

It remains to show the existance of a countable orthonormal basis. Behold:

$$ (e_i)_n := \delta_{in}.  $$

### Definition
Let $V$ and $W$ be Hilbert spaces. A map $U \in \mathcal{L}(V,W)$ is called 
**unitary** if

$$ \forall x,y \in V \;:\; \inner{Ux,Uy} = \inner{x,y}.  $$

If such a map exists, then $V$ and $W$ are called \defined{unitarily equivalent}
or **unitarily isomorphic** Unitary maps are the cononical isomorphisms
on Hilbert spaces.

### Theorem
There is a single infinite-dimensional seperable complex Hilbert space up to 
unitary equivalence. 

### Proof
Let $\H$ be a seperable infinite-dimentional complex Hilbert space. 
Let ${e_1,e_2,...}$ be a countable and orthonormal Shauder basis on $\H$.
Construct the map

$$
\begin{align*}
    U : \H&\to l^2(\N) \\
        \psi     &\mapsto \{\inner{e_n,\psi}\}_{n\in\N}
\end{align*}
$$

Note that

$$ \norm{U\psi}^2 = \sum_{n=1}^\infty\abs{\inner{e_n,\psi}}^2 $$

is finite because $\psi$ can be expanded in the othronormal basis. We now check
properties of $U$:

1. Linearity: follows from linearity of $\inner{,}$.
2. Unitarity: by continuity and the pythagorean theorem:
   
   $$
   \begin{align*}
     \norm{\psi}^2 
     &= \sum_{n=1}^\infty\norm{\inner{e_n,\psi}e_n}^2 \\
     &= \sum_{n=1}^\infty\abs{\inner{e_n,\psi}}^2\norm{e_n}^2,
   \end{align*}
   $$

   $\norm{e_n} = 1$, so $U$ preserves the norm:

   $$\norm{\psi}^2 = \sum_{n=1}^\infty\abs{\inner{e_n,\psi}}^2
                   = \norm{U\psi}^2. $$

3. Invertable: Every unitary map is invertable (proved later).
