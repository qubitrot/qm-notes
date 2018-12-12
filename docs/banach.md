---
title: Banach Spaces
nav-order: 2
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
$$

# Banach Spaces

### Definition
A **Banach Space** $(V,+,\cdot, \norm{\cdot})$ is a vector space with a 
norm, and is complete with respect to that norm. The norm is a map

$$ \norm{\cdot} : V \rightarrow \R, $$

which satisfies

1. $\norm{\lambda f} = \abs{\lambda} \norm{f},\,\forall\lambda \in \C$,
2. The triangle inequality: $\norm{f + g} \le \norm{f} + \norm{g}$, and
3. $\norm{f} \ge 0$, with equality iff $f=0$,

and complete means that every Cauchy sequence converges.

### Definition
A map $A : V \to W$ between normed spaces is said to be 
**bounded** if

$$ \sup_{f \in V} \frac{\norm{Af}}{\norm{f}} < \infty.  $$

The **operator norm** can then be defined as 

$$ \norm{A} = \sup_{\norm{f} = 1} \norm{Af}.  $$

### Theorem
Bounded is equivalent to continuous.

### Proof
($\implies$) Let $A : V \to W$ be bounded and let $u,v \in V$. Then

$$ \norm{Av - Aw} \le \norm{A}\norm{v-w}, $$

by definition of the operator norm. $\norm{A}$ is finite and real, so $A$ 
satisfies Lipschitz continuity.

($\impliedby$) Let $A : V \to W$ be continuous. Continuity at 0 means that

$$
\begin{align*}
    \forall \epsilon > 0, \exists \delta > 0, &\forall f \in V : \\
    &\norm{f} < \delta \implies \norm{Af} < \epsilon.
\end{align*}
$$

We are free to choose $\epsilon = 1$. Define

$$ v = \delta\frac{f}{2\norm{f}} $$

Clearly $\norm{v} < \delta$ for all $\delta$, so

$$
\begin{align*}
    \forall f \in V : \norm{Av} < 1.
\end{align*}
$$

Then since $A$ is linear,

$$ \norm{Av} = \norm{A\left(\delta\frac{f}{2\norm{f}}\right)}
              = \frac{\delta}{2\norm{f}}\norm{Af} < 1 $$

which implies

$$ \norm{Af} < \frac{2}{\delta}\norm{f}, $$

and $A$ is bounded.

### Theorem
Let $V$ be a normed space and let $W$ be a Banach space. Then the set 

$$ \mathcal{L}(V,W) := \{ A : V \rightarrow W \,\,|\,\, 
                           A \text{ is linear and bounded } \} $$

is a Banach space with the operator norm.

### Proof
$\mathcal{L}(V,W)$ trivally forms a normed vector space. It
remains to show completeness. Let $A_n$ be a Cauchy sequence in 
$\mathcal{L}(V,W)$. That is,

$$ \forall \epsilon > 0 .\, \exists N .\, \forall m,n > N .\;
    \norm{A_m - A_n} < \epsilon.  $$

Choose an $f \in V$, then $A_nf$ forms a Cauchy sequence in $W$ because

$$ \norm{(A_m - A_n)f} \le \norm{A_m - A_n} \norm{f} < \epsilon \norm{f}, $$

where the first inquality follows from the definition of the operator norm.
Now we construct a candiate for the limiting map, $A$:

$$ Af = \lim_{n \rightarrow \infty} A_n f.  $$

Linearity follows from linearity of $A_n$ and from the continuity of $+$ and 
$\cdot$. Is $A$ bounded?

$$
\begin{align*}
    \norm{Af} &=   \norm{ \lim_{n \rightarrow \infty} A_n f }
               =   \lim_{n \rightarrow \infty} \norm{A_n f} \\
              &\le \lim_{n \rightarrow \infty} \norm{A_n} \norm{f}.
\end{align*}
$$

$A_n$ being Cauchy is equivalent to

$$ \forall \epsilon > 0 .\, \exists N .\, \forall n > N .\;
    \norm{A_n} - \norm{A_N} \le \norm{A_n - A_N} < \epsilon $$

by the triangle inequality. So

$$ \forall \epsilon > 0 .\, \exists N .\, \forall n > N .\;
    \norm{A_n} < \epsilon + \norm{A_N} $$

and we can conclude

$$ \norm{Af} \le \lim_{n \rightarrow \infty} \norm{A_n} \norm{f} < \infty.  $$

Therefore $A \in \mathcal{L}(V,W)$ and the space is
complete.

### Theorem
Let $V$ be a normed space and $W$ a Banach space. Consider the bounded linear 
map

$$A : \mathcal{D}_A \rightarrow W$$

where $\mathcal{D}_A$ is densely defined in $V$. Then there exists a unique 
extension of $A$ onto the whole domain $V$.

$$ \hat{A} : V \rightarrow W $$

such that

$$ \forall f \in \mathcal{D}_A : \hat{A} = A(f), $$

and

$$ \norm{\hat{A}} = \norm{A}.  $$

Because of this theorem, we will always extend any bounded map to the entire
normed space. This is done implicitly in the preceeding section.

### Proof
Consider a sequence $\{f_n\} \in \mathcal{D}_A$ with $\lim f_n = f$. Since 
$\{f_n\}$ is Cauchy on $V$, $\{Af_n\}$ is Cauchy on $W$, and since
$W$ is Banach, $Af_n$ converges. Define

$$
\begin{align*}
    \hat{A} : V &\rightarrow W \\
              f &\mapsto \hat{A}f := \lim_{n \rightarrow \infty}(Af_n).
\end{align*}
$$

We need to show that $\hat{A}$ has the required properties to be the extension
we seek:

1. Well Definition: Let $\{g_n\}$ be different sequence in $V$ that 
   converges to $f$. Then

   $$ \norm{Af_n - Ag_n} = \norm{A(f_n-g_n)} \le \norm{A}\norm{f_n-g_n}. $$

2. In the limit $n \rightarrow \infty$, $f_n-g_n \rightarrow 0$. So we
   can conclude that $\lim Af_n = \lim Ag_n$.
3. Boundedness: $\norm{\hat{A}f} = \lim \norm{Af_n} \le \lim \norm{A}\norm{f_n}$.   
4. Linearity: Follows from continuity of $\hat{A}$.
5. Extension: If $f \in \mathcal{D}_A$, then $f_n$ converges to $f$ and $\lim Af_n = Af$.
6. Uniqueness: Suppose $\hat{B}$ is a second extension of $A$ Then 
   $\hat{A} - \hat{B}$ is a bounded linear map, and

   $$ \norm{\hat{A} - \hat{B}} \ge \norm{A} - \norm{B} = 0.  $$

### Definition
Let $V$ be a normed space. The \defined{dual space} of $V$ is the set

$$ V^* := \mathcal{L}(V,\C) $$

equipted with the operator norm. $V^*$ is Banach.
\end{definition}

### Definition
Let $f_n$ be a sequence in $V$. Is is said to
1. **converge (strongly)** to $f \in V$ if 
   $$ \forall \epsilon > 0, \exists N \in \N, \forall n \ge N : 
      \norm{f_n - f} < \epsilon.  $$

   This is just the usual notion. We will write $\slim_{n\to\infty}f_n = f$ to 
   denote strong convergence.
2. **converge weakly** to $f \in V$ if for all $l \in V^*$, $l(f_n)$ converges 
   to $l(f)$. We will write $\wlim_{n\to\infty}f_n = f$ to denote weak convergence.

### Theorem
Strong convergence implies weak convergence.

### Definition
Let $V$ be a vector space. A subset $B \subseteq V$ is called a **(Hamel) basis** if
1. any finite subset $\{e_1,...,e_n\} \subseteq B$ is linearly independant, and
2. for any $v \in V$, there exists a finite subset $\{e_1,...,e_n\} \subseteq B$ and 
   complex numbers $v^1,...,v^n$ such that

   $$ v = \sum_{i=1}^n v^i e_i.  $$

If there exits a finite basis $B$ then $\dim V = \abs{B}$, else 
$\dim V = \infty$.

### Definition
Let $W$ be a Banach space. A subset $S \subseteq W$ is called a **(Schauder) basis** if
1. any finite subset $\{e_1,...,e_n\} \subseteq S$ is linearly independant, and
2. for any $\psi \in W$, there exists a unique countable subset $\{e_1,e_2,...\} 
   \subseteq S$ a sequence of complex numbers $\{\psi^1,\psi^2,...\}$ such that

   $$ \psi = \sum_{i=1}^\infty \psi^i e_i.  $$

We can refrase condition 2 as 

$$ \overline{\spann(S)} = \H.  $$

That is, the span is dense in $\H$. Note that $\spann(S)$ is defined to 
be the *finite* linear combinations of elements in $S$. The Schauder 
basis is often more convienent and will almost always be used implicitly.
