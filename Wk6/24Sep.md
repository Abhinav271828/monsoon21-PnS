---
title: Probability and Statistics (MA6.101)
subtitle: |
          | Monsoon 2021, IIIT Hyderabad
          | 24 September, Friday (Lecture 9)
author: Taught by Prof. Pawan Kumar
header-includes: \usepackage{physics}
---

# Quantum Computing (contd.)
## States
if we have two orthogonal states $\ket{\psi_0} = \alpha \ket{0} + \beta \ket{1}$, and $\ket{\psi_1} = \beta^* \ket{0} - \alpha \ket{1}$, they can be distinguished by a transformation that takes $\ket{\psi_0}$ to $\ket{0}$ and $\ket{\psi_1}$ to $\ket{1}$.  

If Alice and Bob are on opposite ends of the universe, each having one qubit of a two-qubit system in the Bell state, then Alice's measurement immediately collapses both qubits. However, Bob has no way to know that Alice has made a measurement; in the absence of this knowledge, his probability remains 50-50 for measuring $\ket{0}$ or $\ket{1}$, as before. This is the no-signalling principle.  

There does not exist a unitary operator $U$ such that $U(\ket{\psi} \ket{0}) = \ket{\psi} \ket{\psi}$. This is the no-cloning principle. Conversely, the no-deleting principle tells us that there does not exist a unitary operator $\hat{U}$ such that $\hat{U}(\ket{\psi} \ket{\psi} ) = \ket{\psi} \ket{0}$.

## Circuits
In a quantum circuit, wires represent qubits and gates represent operators. One example of an operator (on two qubits) is
$$ \text{CNOT} = 
\begin{bmatrix}
1 & 0 & 0 & 0 \\
0 & 1 & 0 & 0 \\
0 & 0 & 0 & 1 \\
0 & 0 & 1 & 0 \end{bmatrix}.$$

The entire quantum circuit can be seen as a matrix, formed by the tensor product of the component gates.

## Teleportation and Superdense Coding
Alice and Bob can transfer 1 qubit using 2 classical bits (teleportation) or 1 qubit having information equal to 2 classical bits (superdense coding).  

Teleportation can be done if Alice and Bob each have one qubit of an EPR pair. Alice must apply the CNOT gate to the qubit to be transferred and her qubit, and then the Hadamard gate on the former. She must then measure the two qubits and send the measurement $M_1M_2$ to Bob.  
Then, Bob must apply the transformation $Z^{M_1}X^{M_2}$ on his qubit to obtain the qubit Alice wished to teleport.
