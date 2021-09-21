---
title: Probability and Statistics (MA6.101)
subtitle: |
          | Monsoon 2021, IIIT Hyderabad
          | 14 September, Tuesday (Lecture 8)
author: Taught by Prof. Pawan Kumar
---

# Quantum Computing
## Bits and Qubits
A classical bit is either
$$0 = \begin{bmatrix} 1 \\ 0 \end{bmatrix} = | 0 \rangle \text{ or }
1 = \begin{bmatrix} 0 \\ 1 \end{bmatrix} = | 1 \rangle.$$

Even if we don't know the value, we can identify probabilities $p_0$ and $p_1$ s.t. $p_0 + p_1 = 1$.  

In contrast, a qubit can be in a superposition of the states:
$$| \psi \rangle = \alpha | 0 \rangle + \beta | 1 \rangle$$
where $\alpha$ and $\beta$ are complex numbers s.t. $|\alpha|^2 + |\beta|^2 = 1$.  
Any attempt to measure the state results in $| 0 \rangle$ with probability $|\alpha|^2$ and $| 1 \rangle$ with probability $|\beta|^2$. After measurement, the system will be in the measured state
$$| \psi' \rangle = 0 \text{ or } 1.$$
Any subsequent measurement will yield the same value.

The state of a qubit is more than a probability mass function. For example,
$$\frac{1}{\sqrt{2}}(| 0 \rangle + | 1 \rangle ),$$
$$\frac{1}{\sqrt{2}}(| 0 \rangle - | 1 \rangle ),$$
$$\frac{1}{\sqrt{2}}(| 0 \rangle + i| 1 \rangle ),$$
$$\frac{1}{\sqrt{2}}(| 0 \rangle - i| 1 \rangle ),$$
are all equally likely to be $| 0 \rangle$ or $| 1 \rangle$, but correspond to different superpositions.  

The Hadamard gate $H$ behaves in the following way:
$$H| + \rangle = H \left[ \frac{1}{\sqrt{2}}( | 0 \rangle + | 1 \rangle) \right] \to | 0 \rangle$$
$$H| - \rangle = H \left[ \frac{1}{\sqrt{2}}( | 0 \rangle - | 1 \rangle) \right] \to | 1 \rangle$$

The two-qubit Bell state $| \phi^+ \rangle$ is defined as
$$| \phi^+ \rangle = \frac{1}{\sqrt{2}}| 0 0 \rangle + | 1 1 \rangle.$$

Quantum phenomena are described in linear algebra terms. We need to define a new form of multiplication on matrices called tensor multiplication:
$$A \otimes B = \begin{bmatrix} a_{11}B & \cdots & a_{1m}B \\
\vdots & \ddots & \vdots \\
a_{n1}B & \cdots & a_{nm}B \end{bmatrix}.$$
We also define the conjugate transpose $A^\dagger = (A^*)^T$.  

If we have two vectors $| u \rangle, | v \rangle$, we define the inner product $\langle u | v \rangle$ as $\langle u | \times | v \rangle = u^\dagger v$. Similarly, the outer product is $| u \rangle \langle v |$, which is a matrix. If $| u \rangle$ is a unit vector then $| u \rangle \langle u|$ is known as a projector; it projects an arbitrary vector $| v \rangle$ onto the subspace $| u \rangle$.
$$(| u \rangle \langle u|) | v \rangle = | u \rangle (\langle u | v \rangle) = (\langle u | v \rangle) | u \rangle$$

A matrix $A$ is normal if $A A^\dagger = A^\dagger A$. It is hermitian if $A = A^\dagger$. It is unitary if $A A^\dagger = A^\dagger A = I$.  

## Postulates of QM
### State space
Associated to any isolated physical system is a copmlex vector space with an inner product (a Hilbert space). The state is completely described by its state vector (which is a unit vector).  

Qubits are quantum states in the space $\mathbb{C}^2$. An example of a physical realisations of qubits is electron spin.

### Evolution
The time evolution of the state of a closed system is described by the Schrodinger equation
$$ i \hbar \frac{d | \psi \rangle}{dt} = H | \psi \rangle,$$
where $H$ is a fixed Hermitian operator called the Hamiltonian of the system.  

We can say that
$$| \psi_{t_1} \rangle = \exp \left( \frac{i H (t_1 - t_0)} {\hbar} \right) | \psi_{t_0} \rangle.$$


The Pauli matrices are important single-qubit unitary matrices
$$X = \begin{bmatrix} 0 & 1 \\ 1 & 0 \end{bmatrix},$$
$$Y = \begin{bmatrix} 0 & -i \\ i & 0 \end{bmatrix},$$
$$Z = \begin{bmatrix} 1 & 0 \\ 0 & -1 \end{bmatrix};$$

and the Hadamard matrix is
$$H = \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\ 1 & -1 \end{bmatrix}.$$
We can check that $H | + \rangle = | 0 \rangle$ and $H | - \rangle = | 1 \rangle$.

### Measurement
Quantum measurements are described by a collection $\{M_m\}$ of measurement operators. They ar on the state space of the system. The index $m$ refers to the outcomes that may occur.  

If the state is $| \psi \rangle$ before measurement, the probability of the $m^\text{th}$ outcome is
$$p(m) = \langle \psi | M_m^\dagger M_m | \psi \rangle$$
and the state of the system after the measurement is
$$\frac{M_m | \psi \rangle}{\sqrt{\langle \psi | M_m^\dagger M_m | \psi \rangle}}.$$

The measurement operators must satisfy
$$\sum_m M_m^\dagger M_m = I.$$
This property is called completeness.  

We can write a one-qubit state as
$$| \psi \rangle = e^{i \theta} (\alpha |0 \rangle + \beta e^{i \phi} | 1 \rangle ) = e^{i \theta} | \psi' \rangle,$$
where $\alpha, \beta$ are positive real numbers. $\theta$ is known as the global phase and has no observable consequences.

### Composition
The state space of a composite system is the tensor product of the state space of the component physical systems. More generally, if the systems are numbered 1 to $n$, where system $i$ is in state $| \psi_i \rangle$, then the state of the composite system is $| \psi_1 \rangle \otimes \cdots \otimes | \psi_n \rangle$.
