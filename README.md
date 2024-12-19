# Quantum Gates and Their Formulas

Quantum gates are the building blocks of quantum circuits. They operate on qubits, the fundamental units of quantum information, and manipulate their states using unitary transformations. This document provides an overview of common quantum gates and their mathematical representations.

## Table of Contents
1. [Single-Qubit Gates](#single-qubit-gates)
    - [Identity Gate (I)](#identity-gate-i)
    - [Pauli Gates (X, Y, Z)](#pauli-gates-x-y-z)
    - [Hadamard Gate (H)](#hadamard-gate-h)
    - [Phase Gate (S)](#phase-gate-s)
    - [T Gate](#t-gate)
2. [Multi-Qubit Gates](#multi-qubit-gates)
    - [CNOT Gate](#cnot-gate)
    - [SWAP Gate](#swap-gate)
    - [Toffoli Gate (CCNOT)](#toffoli-gate-ccnot)
    - [Fredkin Gate (CSWAP)](#fredkin-gate-cswap)
3. [Parameterized Gates](#parameterized-gates)
    - [Rotation Gates (Rx, Ry, Rz)](#rotation-gates-rx-ry-rz)
4. [Measurement](#measurement)

---

## Single-Qubit Gates

### Identity Gate (I)
The Identity gate leaves the qubit state unchanged.

**Matrix Representation:**
\[
I = \begin{bmatrix} 1 & 0 \\
0 & 1 \end{bmatrix}
\]

---

### Pauli Gates (X, Y, Z)
1. **Pauli-X (NOT Gate):** Flips the qubit state \(|0\rangle \leftrightarrow |1\rangle\).

   **Matrix Representation:**
   \[
   X = \begin{bmatrix} 0 & 1 \\
   1 & 0 \end{bmatrix}
   \]

2. **Pauli-Y:** Combines bit and phase flip.

   **Matrix Representation:**
   \[
   Y = \begin{bmatrix} 0 & -i \\
   i & 0 \end{bmatrix}
   \]

3. **Pauli-Z:** Flips the phase of \(|1\rangle\).

   **Matrix Representation:**
   \[
   Z = \begin{bmatrix} 1 & 0 \\
   0 & -1 \end{bmatrix}
   \]

---

### Hadamard Gate (H)
Creates a superposition state.

**Matrix Representation:**
\[
H = \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\
1 & -1 \end{bmatrix}
\]

---

### Phase Gate (S)
Applies a phase of \(\pi/2\) to \(|1\rangle\).

**Matrix Representation:**
\[
S = \begin{bmatrix} 1 & 0 \\
0 & i \end{bmatrix}
\]

---

### T Gate
Applies a phase of \(\pi/4\) to \(|1\rangle\).

**Matrix Representation:**
\[
T = \begin{bmatrix} 1 & 0 \\
0 & e^{i\pi/4} \end{bmatrix}
\]

---

## Multi-Qubit Gates

### CNOT Gate
Flips the target qubit if the control qubit is \(|1\rangle\).

**Matrix Representation:**
\[
CNOT = \begin{bmatrix} 1 & 0 & 0 & 0 \\
0 & 1 & 0 & 0 \\
0 & 0 & 0 & 1 \\
0 & 0 & 1 & 0 \end{bmatrix}
\]

---

### SWAP Gate
Swaps the states of two qubits.

**Matrix Representation:**
\[
SWAP = \begin{bmatrix} 1 & 0 & 0 & 0 \\
0 & 0 & 1 & 0 \\
0 & 1 & 0 & 0 \\
0 & 0 & 0 & 1 \end{bmatrix}
\]

---

### Toffoli Gate (CCNOT)
Flips the target qubit if both control qubits are \(|1\rangle\).

**Matrix Representation:**
\[
Toffoli = \begin{bmatrix}
1 & 0 & 0 & 0 & 0 & 0 & 0 & 0 \\
0 & 1 & 0 & 0 & 0 & 0 & 0 & 0 \\
0 & 0 & 1 & 0 & 0 & 0 & 0 & 0 \\
0 & 0 & 0 & 1 & 0 & 0 & 0 & 0 \\
0 & 0 & 0 & 0 & 1 & 0 & 0 & 0 \\
0 & 0 & 0 & 0 & 0 & 1 & 0 & 0 \\
0 & 0 & 0 & 0 & 0 & 0 & 0 & 1 \\
0 & 0 & 0 & 0 & 0 & 0 & 1 & 0
\end{bmatrix}
\]

---

### Fredkin Gate (CSWAP)
Swaps two target qubits if the control qubit is \(|1\rangle\).

**Matrix Representation:**
\[
Fredkin = \begin{bmatrix}
1 & 0 & 0 & 0 & 0 & 0 & 0 & 0 \\
0 & 1 & 0 & 0 & 0 & 0 & 0 & 0 \\
0 & 0 & 1 & 0 & 0 & 0 & 0 & 0 \\
0 & 0 & 0 & 1 & 0 & 0 & 0 & 0 \\
0 & 0 & 0 & 0 & 1 & 0 & 0 & 0 \\
0 & 0 & 0 & 0 & 0 & 0 & 1 & 0 \\
0 & 0 & 0 & 0 & 0 & 1 & 0 & 0 \\
0 & 0 & 0 & 0 & 0 & 0 & 0 & 1
\end{bmatrix}
\]

---

## Parameterized Gates

### Rotation Gates (Rx, Ry, Rz)
1. **Rx Gate:** Rotates around the X-axis by an angle \(\theta\).

   **Matrix Representation:**
   \[
   Rx(\theta) = \begin{bmatrix}
   \cos(\theta/2) & -i\sin(\theta/2) \\
   -i\sin(\theta/2) & \cos(\theta/2)
   \end{bmatrix}
   \]

2. **Ry Gate:** Rotates around the Y-axis by an angle \(\theta\).

   **Matrix Representation:**
   \[
   Ry(\theta) = \begin{bmatrix}
   \cos(\theta/2) & -\sin(\theta/2) \\
   \sin(\theta/2) & \cos(\theta/2)
   \end{bmatrix}
   \]

3. **Rz Gate:** Rotates around the Z-axis by an angle \(\theta\).

   **Matrix Representation:**
   \[
   Rz(\theta) = \begin{bmatrix}
   e^{-i\theta/2} & 0 \\
   0 & e^{i\theta/2}
   \end{bmatrix}
   \]

---

## Measurement

Measurement collapses a qubit's state into one of the basis states \(|0\rangle\) or \(|1\rangle\) with probabilities determined by the squared amplitudes of the state vector.

**Probability Formula:**
\[
P(\text{outcome } |0\rangle) = |\alpha|^2, \quad P(\text{outcome } |1\rangle) = |\beta|^2
\]
where the qubit state is \(|\psi\rangle = \alpha|0\rangle + \beta|1\rangle\).

---

This document serves as a reference for quantum gates and their mathematical foundations. For more details or implementation examples, explore quantum programming libraries like [Qiskit](https://qiskit.org) or [Cirq](https://quantumai.google/cirq).

