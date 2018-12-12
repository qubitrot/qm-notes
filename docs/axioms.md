---
title: Axioms of Quantum Mechanics
nav-order: 1
---

$$
\newcommand{\R}{\mathbb{R}}
\newcommand{\C}{\mathbb{C}}
\newcommand{\N}{\mathbb{N}}
\newcommand{\H}{\mathcal{H}}
\newcommand{\inner}[1]{\langle#1\rangle}
\newcommand{\Tr}[1]{\text{Tr}#1}
\renewcommand{\diff}[1]{\mathop{}\!\mathrm{d}#1}
$$

# Axioms of Quantum Mechanics

## Axiom 1
With every quantum system there is an associated seperable complex Hilbert 
space $(\H, +, \cdot, \inner{,})$.

The states of a the system are all positive trace-class linear maps 
$\rho : \H \to \H$ for which $\Tr{\rho} = 1$. 

Terminology: A state is called *pure* if there exists a 
$\Psi \in \mathcal{H}$ such that

$$
\begin{align*}
    \rho : &\H \to \H, \\
           &\alpha \mapsto \rho(\alpha) = \frac{\inner{\Psi,\alpha}}
                                               {\inner{\Psi,\Psi}}  \Psi.
\end{align*}
$$

It is called *mixed* otherwise.

## Axiom 2

The observables of a quantum system are the self-adjoint linear maps 
$A : \mathcal{D}_A \to \H$, where $\mathcal{D}_A$ is a dense subset of $\H$.

## Axiom 3

The probability that a measurement of an observable $A$ on a system that is in
the state $\rho$ yields a result in the Borel set $E \subseteq \R$ is given by

$$
    \mu^A_\rho (E) := \Tr( P_A(E) \circ \rho ),
$$

where $P_A : \text{Borel}(\R) \rightarrow \mathcal{L}(\H)$ is the 
*unique* projection-valued measure associated with a self-adjoint map
$A$ according to the spectral theorem:

$$
    A = \int^{\infty}_{-\infty} \lambda \diff{P_A}(\lambda).
$$

## Axiom 4: Unitary Dynamics

Let $(t_1,t_2)$ be a time interval for which no measurement takes place. The
states $\rho(t_1)$ and $\rho(t_1)$ are related by

$$
    \rho(t_2) = U(t_2 - t_1) \rho(t_1) U^{-1}(t_2 - t_1),
$$

where

$$
    U(t) := \exp\left( -\frac{i}{\hbar} H t \right)
$$

and $H$ is the energy observable.

## Axiom 5: Projective Dynamics

When a measurement is made using an obversable $A$ on a state $\rho_0$, the 
new state $\rho$ is given by

$$
    \rho := \frac { P_A(E) \rho_0 P_A(E) }
                  { \Tr\left(P_A(E) \rho_0 P_A(E)\right) },
$$

where $E$ is the smallest Borel set in which the outcome of the measurement 
happened to lie.
