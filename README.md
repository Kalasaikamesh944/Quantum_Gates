# Quantum Gates and Their Formulas

Quantum gates are the building blocks of quantum circuits. They operate on qubits, the fundamental units of quantum information, and manipulate their states using unitary transformations. This document provides an overview of common quantum gates and their Python implementations using `NumPy`.

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

**Python Implementation:**
```python
import numpy as np

def identity():
    return np.array([[1, 0], [0, 1]])
```

---

### Pauli Gates (X, Y, Z)
1. **Pauli-X (NOT Gate):** Flips the qubit state \(|0\rangle \leftrightarrow |1\rangle\).

   **Python Implementation:**
   ```python
   def pauli_x():
       return np.array([[0, 1], [1, 0]])
   ```

2. **Pauli-Y:** Combines bit and phase flip.

   **Python Implementation:**
   ```python
   def pauli_y():
       return np.array([[0, -1j], [1j, 0]])
   ```

3. **Pauli-Z:** Flips the phase of \(|1\rangle\).

   **Python Implementation:**
   ```python
   def pauli_z():
       return np.array([[1, 0], [0, -1]])
   ```

---

### Hadamard Gate (H)
Creates a superposition state.

**Python Implementation:**
```python
def hadamard():
    return np.array([[1, 1], [1, -1]]) / np.sqrt(2)
```

---

### Phase Gate (S)
Applies a phase of \(\pi/2\) to \(|1\rangle\).

**Python Implementation:**
```python
def phase_s():
    return np.array([[1, 0], [0, 1j]])
```

---

### T Gate
Applies a phase of \(\pi/4\) to \(|1\rangle\).

**Python Implementation:**
```python
def t_gate():
    return np.array([[1, 0], [0, np.exp(1j * np.pi / 4)]])
```

---

## Multi-Qubit Gates

### CNOT Gate
Flips the target qubit if the control qubit is \(|1\rangle\).

**Python Implementation:**
```python
def cnot():
    return np.array([
        [1, 0, 0, 0],
        [0, 1, 0, 0],
        [0, 0, 0, 1],
        [0, 0, 1, 0]
    ])
```

---

### SWAP Gate
Swaps the states of two qubits.

**Python Implementation:**
```python
def swap():
    return np.array([
        [1, 0, 0, 0],
        [0, 0, 1, 0],
        [0, 1, 0, 0],
        [0, 0, 0, 1]
    ])
```

---

### Toffoli Gate (CCNOT)
Flips the target qubit if both control qubits are \(|1\rangle\).

**Python Implementation:**
```python
def toffoli():
    return np.eye(8)
    matrix[6, 6], matrix[6, 7] = 0, 1
    matrix[7, 6], matrix[7, 7] = 1, 0
    return matrix
```

---

### Fredkin Gate (CSWAP)
Swaps two target qubits if the control qubit is \(|1\rangle\).

**Python Implementation:**
```python
def fredkin():
    matrix = np.eye(8)
    matrix[5, 5], matrix[5, 6] = 0, 1
    matrix[6, 5], matrix[6, 6] = 1, 0
    return matrix
```

---

## Parameterized Gates

### Rotation Gates (Rx, Ry, Rz)
1. **Rx Gate:** Rotates around the X-axis by an angle \(\theta\).

   **Python Implementation:**
   ```python
   def rx(theta):
       return np.array([
           [np.cos(theta / 2), -1j * np.sin(theta / 2)],
           [-1j * np.sin(theta / 2), np.cos(theta / 2)]
       ])
   ```

2. **Ry Gate:** Rotates around the Y-axis by an angle \(\theta\).

   **Python Implementation:**
   ```python
   def ry(theta):
       return np.array([
           [np.cos(theta / 2), -np.sin(theta / 2)],
           [np.sin(theta / 2), np.cos(theta / 2)]
       ])
   ```

3. **Rz Gate:** Rotates around the Z-axis by an angle \(\theta\).

   **Python Implementation:**
   ```python
   def rz(theta):
       return np.array([
           [np.exp(-1j * theta / 2), 0],
           [0, np.exp(1j * theta / 2)]
       ])
   ```

---

## Measurement

Measurement collapses a qubit's state into one of the basis states \(|0\rangle\) or \(|1\rangle\) with probabilities determined by the squared amplitudes of the state vector.

**Python Implementation:**
```python
def measure(state):
    probabilities = np.abs(state) ** 2
    outcome = np.random.choice(len(state), p=probabilities)
    return outcome
```

---

This document serves as a reference for quantum gates and their Python implementations. For more details or practical usage, explore quantum programming libraries like [Qiskit](https://qiskit.org) or [Cirq](https://quantumai.google/cirq).

