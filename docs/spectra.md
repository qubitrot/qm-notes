---
title: Spectra and Perturbation Theorey
nav-order: 8
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

# Spectra and Perturbation Thoery

### Definition
The **resolvent set** of a closed operator $A$ is

$$ \rho(A) := \{ z \in \C \;|\; (A-z)^{-1} \in \mathcal{L}(\H,\H) \}.  $$

The **resolvent map** of $A$ is

$$
\begin{align*}
R_A : \rho(A) &\to \mathcal{L}(\H,\H)  \\
z &\to (A - z)^{-1},
\end{align*}
$$

### The Closed Graph Theorem
A map $A$ is closed if and only if $(A-z)$ is bijective.

### Definition
The **spectrum** $\sigma(A)$ is the set of complex numbers which do not
belong in $\rho(A)$.

### Corollary
If $\lambda \in \C$ is an eigenvalue of an operator $A : D_A \to \H$, 
then $\lambda \in \sigma(A)$.

### Proof

$$
\begin{align*}
0 \neq \psi \in \ker(A-\lambda) &\implies \ker(A-\lambda) \{0\} \\
&\implies (A-\lambda) \text{ not injective } \\
&\implies \lambda \notin \rho(A) \\
&\implies \lambda \in \sigma(A).
\end{align*}
$$

## Spectrum of a self-adjoint operator

### Definition
If $A$ is a self-adjoint operator, then we define

$$
\begin{align*}
\sigma_{\text{p-pure}}(A) &= \{ z \in \C \;|\; 
    \range(A-z) = \overline{\range(A-z)} \neq \H \} \\
\sigma_{\text{p-embedded}}(A) &= \{ z \in \C \;|\; 
    \range(A-z) \neq \overline{\range(A-z)} \neq \H \} \\
\sigma_{\text{c-pure}}(A) &= \{ z \in \C \;|\; 
    \range(A-z) \neq \overline{\range(A-z)} = \H \} \\
\sigma_{\text{p}}(A) &= \sigma_{\text{p-pure}} \cup \sigma_{\text{p-embedded}} \\
\sigma_{\text{c}}(A) &= \sigma_{\text{c-pure}} \cup \sigma_{\text{p-embedded}}.
\end{align*}
$$

$\sigma_p(A)$ is called the **point spectra** of $A$, and $\sigma_c(A)$
is called the **continuous spectra**.

### Lemma
If $\lambda$ is an eigenvalue of a self-adjoint map $A$, then $\lambda \in \R$.

### Proof
Let $\psi$ be an eigenvector of $A$ with eigenvalue $\lambda$. Then

$$ \inner{\psi,A\psi} = \lambda\inner{\psi,\psi} = 
\cconj{\lambda}\inner{\psi,\psi} = \cconj{\inner{A\psi,\psi}}.  $$

### Theorem
Let $A$ be a self-adjoint operator. The elements of the point spectrum,

$$ \sigma_p(A) = \{ z \in \C \;|\; \overline{\range(A-z)} \neq \H \} $$

are the eigenvalues of $A$.

## Perturbation theory for the point spectra of self-adjoint operators

Let $H$ and $W$ be self-adjoint operators. Let $H_\lambda := H_0 + \lambda W$,
where $\lambda \in (a,b) \ni 0$. Assume that $H_0$ has countably many 
eigenvectors and eigenvalues and that they are known:

$$ H_0 e_{n\delta} = h_n e_{n\delta}, $$

where the index $\delta$ is used to distinguise degenerate eigenvectors, and
there are as many as the dimension of the eigenspace.
