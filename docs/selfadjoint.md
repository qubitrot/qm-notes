---
title: Self-Adjoint Operators
nav-order: 7
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
\newcommand{\range}{\text{range}}
\newcommand{\cconj}[1]{\overline{#1}}
$$

# Self-Adjoint Operators

### Definition
Let $A : D_A \to \H$ be a (possibly unbounded) operator densely defined 
on a subset $\overline{D}_A \subseteq \H$. Then the **adjoint** of 
$A$ is

$$ A^* : D_{A^*} \to \H $$

where

$$ D_{A^*} := \left\{ \psi \in \H\;|\; \exists \eta \in \H: 
\forall\alpha\in D_A : \inner{\psi,A\alpha} = \inner{\eta,\alpha} \right\} $$

and

$$ A^*\psi := \eta.  $$

If $A = A^*$ then $A$ is called **self-adjoint**.

### Lemma

$$ \ker(A^*) = A(D_A)^\bot $$

### Proof

$$
\begin{align*}
\psi \in \ker(A^*) &\iff \forall \alpha \in D_A : \inner{\psi,A\alpha} = 0 \\
&\iff \psi \in A(D_A).
\end{align*}
$$

### Lemma
Let $A$ and $B$ be operators, with $A \subseteq B$ ($B$ is an extension of 
$A$). Then $B^* \subseteq A^*$.

### Proof

$$ D_{A^*} := \left\{ \psi \in \H\;|\; \exists \eta \in \H : 
\forall\alpha\in D_A : \inner{\psi,A\alpha} = \inner{\eta,\alpha} \right\} $$

$$ D_{B^*} := \left\{ \psi \in \H\;|\; \exists \eta \in \H : 
\forall\beta\in D_B : \inner{\psi,B\beta} = \inner{\eta,\beta} \right\} $$

Since $D_A \subseteq D_B$, it follows that $D_{B^\*} \subseteq D_{A^\*}$.

### Definition
An operator $A$ is **symmetric** (sometimes **Hermitian**) if

$$ \inner{A\psi,\phi} = \inner{\psi,A\phi}.  $$

### Lemma
If $A$ is symmetric, then $A \subseteq A^*$.

### Theorem
A self-adjoint operator cannot be extended to another self-adjoint operator
(or even a symmetric one).

### Proof
Assume $B$ is a self-ajoint extension of $A$, $A \subseteq B$. Then 

$$A \subseteq B \subseteq B* \subseteq A* = A,$$

so $B \subseteq A$ and thus $B = A$. 

### Definition
A densely defined operator $A$ is called **closable** if its adjoint
$A^*$ is also densely defined. The **closure** of closable operator
is defined as $\overline{A} = A^{\*\*}$. A **closed** operator is one 
for which $A = A^{\*\*}$.

### Theorem
A symmetric operator is closable.

### Proof
If $A$ is symmetric, then $A \subseteq A^\*$, and $D_A \subseteq D_{A^\*}$. \\
Then, $\H = \overline{D}\_A \subseteq \overline{D}\_{A^\*} \subseteq \H$, and 
$\overline{D}\_{A^\*} = \H.$

### Lemma
If $A$ is symmetric, then $A^{\*\*} \subseteq A^\*$.

### Lemma
If $A$ is closable, then $A \subseteq A^{\*\*}$.

### Corollary
If $A$ is symmetric, then $A \subseteq \overline{A} \subseteq A^*$.

### Theorem
Let $A$ be a densely defined operator, then

1. $A^*$ is closed,
2. $A$ is bijective ($\ker(A) = \{0\}$ and $\overline{A(D_A)} = \H$),
3. $(A^{-1})^* = (A^*)^{-1}$, and
4. If $A$ is bijective and closable and $\overline{A}$ is injective, then
   $\overline{A^{-1}} = (\overline{A})^{-1}$.

## Essentially self-adjoint operators

### Definition
A symmetric operator $A$ is called **essentially self-ajoint** if it's 
closure $\overline{A}$ is self-adjoint.

### Theorem
For an essentially self-ajoint operator $A$, there exists a unique self-adjoint
extension, namely $\overline{A}$.

### Proof
Since $A$ is symmetric, it is closable. Then since $A \subseteq \overline{A}$,
$\overline{A}$ is indeed an extension. It remains to show unquieness. Let $B$
be another self-adjoint extension of $A$, then 

$$ A \subseteq B = B^* \implies B^{**} \subseteq A^* \implies 
A^{**} \subseteq B^{***} = B.  $$

Since $A$ is essientially self-adjoint, $\overline{A}$ is self-adjoint, and it
follows that $\overline{A}$ is an extension of $B$. Then from the eariler 
theorem, $\overline{A} = B$.

### Theorem
A symmetric operator has a self-adjoint extension if it's \defined{defect 
indices},

$$
\begin{align*}
d_+ &:= \dim(\ker(A^* - i)) \\
d_- &:= \dim(\ker(A^* + i)),
\end{align*}
$$

conincide. Otherwise there is no self-adjoint extension.

### Corollary
If $d_+ = d_- = 0$, then $A$ is essentially self-adjoint.

### Theorem
A symmetric operator $A$ is self-adjoint if there exists a $z\in\C$ such that

$$ \range(A + z) = \H = \range(A + \cconj{z}). $$

### Proof
Since $A$ is symmetric, $A \subseteq A^\*$. For the other direction, let $\psi
\in D_{A^\*}$. Since $\range(A+\cconj{z}) = \H$, then

$$ \exists \rho \in D_A : A^*\psi + \cconj{z}\psi = (A + \cconj{z})\rho.  $$

By symmetry of $A$, for any $\phi \in D_A$,

$$
\begin{align*}
\inner{\psi,(A+z)\phi} &= \inner{A^*\psi + \cconj{z}\psi, \phi} \\
&= \inner{(A+\cconj{z})\rho,\phi} \\
&= \inner{\rho,(A+z)\phi}.
\end{align*}
$$

Since $\range(A+z) = \H$, we can conclude that $\psi = \rho
\in D_A$ and $D_{A\*} \subseteq D_A$. Thus $A^\* \subseteq A$

### Theorem
A symmetric operator $A$ is essentially self-adjoint if and only if there
exists a $z \in \C \setminus \R$ such that that

$$ \overline{\range(A + z)} = \H = \overline{\range(A + \cconj{z})}.  $$

### Corollary
A symmetric operator $A$ is essentially self-adjoint if and only if for all
$z \in \C \setminus \R$,

$$ \ker(A^* + \overline{z}) = \{0\} = \ker(A^* + z).  $$

