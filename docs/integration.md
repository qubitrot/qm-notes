---
title: The Lebesgue Integral
nav-order: 6
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

# The Lebesgue Integral

### Definition
An **indicator function** or a **characteristic function** is a special map:

$$
\begin{align*}
1_S : M &\to \{1,0\} \\
m &\mapsto 1_S(m) := \begin{cases}
                     1 \; \text{ if $m \in S$} \\
                     0 \; \text{ otherwise}
                     \end{cases}
\end{align*}
$$

### Definition
A measurable function $ s : M \to \R_0^+$ is called a **simple function**
if it is a finite linear combination of indicator functions, who's sets $S_k$ 
are measurable.

### Definition
The **integral** of a simple function $s$ is

$$ \int s \diff{\mu} := \sum_k a_k \int 1_{S_k} \diff{\mu} = \sum_k a_k \mu(S_k).  $$

## Integration of non-negative functions

### Definition
Let $(M,\sigma,\mu)$ be a measure space. Let $f$ be a non-negative measurable
function from $M$ to $\overline{\R}$. Then the \defined{integral} of $f$ is the 
(extended) real number

$$ \int f \diff{\mu} := \sup \left\{ \int s \diff{\mu} \;\Big|\; 
0 \le s \le f, \text{ s simple }\right\}.  $$

### Definition
let $A$ be a measurable set. Then

$$ \int_A f \diff{\mu} := \int f \cdot 1_A \diff{\mu}.  $$

It is often convienent to write

$$ \int f(x) \mu(\diff{x}) := \int f \diff{\mu}.  $$

### The Monotone Convergence Theorem
Let $0 \le f_1 \le f_2 \le ...$ be a sequence of non-negative measurable 
functions $f_n : M \to \overline{\R}$. Provided there exists a

$$ f := \sup_{n \ge 1} f_n \;\;\; \text{(pointwise)}, $$

then 

$$ \lim_{n \to \infty} \int f_n \diff{\mu} = \int f \diff{\mu}.  $$

## Integration of general functions

### Definition
A measurable function $f : M \to \overline{\R}$ is called **intergrable**
if $\int \abs{f} \diff{\mu} < \infty$.

### Definition
The **integral** of an integrable function is

$$ \int f \diff{\mu} = \int f^+ \diff{\mu} - \int f^- \diff{\mu}, $$

where $f^+ = \max(f,0)$ and $f^- = \max(-f,0)$.

### Theorem
The Lebesgue integral is linear and even

$$ \int \sum_{n=1}^\infty a_n f_n \diff{\mu} = 
\sum_{n=1}^\infty a_n \int f_n \diff{\mu} $$

for functions $f_n : M \to \overline{\R}_0^+$.

### The Dominated Convergence Theorem
Let $f_1,f_2,...$ be a sequence of measurable functions that converge 
pointwise (almost everywhere) to $f$. Let $g$ be a non-negative measurable
function with a finite integral (aka integrable), such that 

$$ \forall n \in \N : \abs{f_n} \le_{\text{a.e.}} g.  $$

Then

1. $f$ and $f_1,f_2,...$ are all integrable,
2. $\lim_{n\to\infty}\int\abs{f_n-f}\diff{\mu} = 0$, and
3. $\lim_{n\to\infty}\int f_n \diff{\mu} = \int f \diff{\mu}$.

## The Function Spaces $L^p$

### Definition
The set of measurable functions,

$$ \mathcal{L}^p := \left\{ f : M \to \C \;\Big|\; 
\int\abs{f}^p\diff{\mu} < \infty\right\}, $$

equipted with pointwise multiplication and addition, is a $\C$ vector space.

### Theorem
The map $p : \mathcal{L}^p \to \R$, defined by

$$ p(f) := \left( \int \abs{f}^p \diff{\mu} \right)^{\frac{1}{p}}, $$

is a **semi-norm**. That is

1. $\forall \alpha \in \C : p(\alpha f) = \abs{\alpha} p(f)$,
2. $p(f+g) \le p(f) + p(g)$, and
3. $p(f) \ge 0$.

But it does not form a norm because $p(f) = 0$ does not imply $f = 0$,
because functions may differ on a set of measure 0.

### Definition
Let $f,g \in \mathcal{L}^p$ be equivalent, $f \sim g$, iff $f(x) = g(x)$
almost everywhere. Under this equivalence relation, we have the quotient space

$$ L^p := \mathcal{L}^p/\sim \;\; = 
\left\{ [f]_\sim \;|\; f \in \mathcal{L}^p \right\}, $$

where $[f]_\sim := \{ \overline{f} \;|\; \overline{f} \sim f \}$. Again, this 
forms a vector space. In fact, it forms a Banach space with the norm

$$ \norm{[f]} := \left( \int \abs{f}^p \diff{\mu} \right)^\frac{1}{p}.  $$

### Theorem: The Holder Inequality
Let $1 \le p,q \le \infty$, and $\frac{1}{p} + \frac{1}{q} = 1.$ Then

$$
\abs{\int \cconj{f} g \diff{\mu}} \le 
\left( \int \abs{f}^p \diff{\mu} \right)^\frac{1}{p} + 
\left( \int \abs{g}^q \diff{\mu} \right)^\frac{1}{p}.
$$

### Theorem
$L^2$, when equipted with the inner product

$$ \inner{[f],[g]} := \int \cconj{f} g \diff{\mu} $$

forms a seperable Hilbert space. For $p \neq 2$, $L^p$ does not form a Hilbert
space because it cannot satisfy the Cauchy-Schwarz inequality. $L^2$ forms the
so-called **square-integrable "functions"**.

