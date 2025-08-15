## BASICS OF QUANTUM INFORMATION

![Qiskit](./images/demo.jpg)

# Quantum Computer
A quantum computer is a type of computer that uses the strange rules of quantum mechanics to process information.  
Unlike a regular computer, which stores data in bits that are either 0 or 1, a quantum computer uses quantum bits, or **qubits**, which can be both 0 and 1 at the same time (this is called **superposition**).

Two key principles that make quantum computers special are:

- **Superposition** — A qubit can exist in multiple states at once (not just 0 or 1, but a blend of both).  
- **Entanglement** — Qubits can become linked so that the state of one affects the other, no matter how far apart they are.

# Quantum Information
A quantum state of a system is represented by a column vector, similar to a probabilistic state.  
As before, the indices of the vector label the classical states of the system.  
Vectors representing quantum states are characterized by these two properties:

1. The entries of a quantum state vector are complex numbers.  
2. The sum of the absolute values squared of the entries of a quantum state vector is 1.

# Quantum Information: One System vs Multiple Systems

## 1. Quantum Information for One System (Single Qubit)

**What it means**:  
Quantum information for a single system is encoded in a **pure quantum state**, typically represented as a unit vector \( |\psi\rangle \) in a two-dimensional complex Hilbert space.  
Operations on this system are **unitary transformations**, and measurements extract classical outcomes **probabilistically** per the Born rule.

**Example**:  
A single qubit prepared in:
\[
|\psi\rangle = \alpha |0\rangle + \beta |1\rangle, \quad |\alpha|^2 + |\beta|^2 = 1
\]  
Measuring it in the computational basis yields:  
- "0" with probability \( |\alpha|^2 \)  
- "1" with probability \( |\beta|^2 \)

---

## 2. Quantum Information for Multiple Systems (Multi-Qubit)

**What it means**:  
When considering multiple quantum systems (qubits), the **joint system** lives in the **tensor-product Hilbert space** of its parts.  
Its state can be:
- **Separable** (simple product state)  
- **Entangled** (cannot be factored into individual system states)

Entanglement enables **correlations beyond classical possibilities**.

**Example**:  

**Bell State**:  
\[
|\Phi^+\rangle = \frac{1}{\sqrt{2}} \left( |00\rangle + |11\rangle \right)
\]  
- Neither qubit has a definite state on its own—only their joint state is defined.  
- If one is measured as "0", the other is guaranteed to be "0" (and likewise for "1").  

**GHZ State**:  
\[
|\mathrm{GHZ}\rangle = \frac{1}{\sqrt{2}} \left( |000\rangle + |111\rangle \right)
\]  
- Shows **multipartite entanglement**, where the joint system’s properties can’t be described by parts alone.

---

## Summary Table

| **System**           | **Quantum Information Description**                                                                 | **Illustrative Example**                                                          |
|----------------------|-----------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------|
| **Single System**    | A lone qubit in state \( |\psi\rangle \), measured probabilistically.                               | \( |\psi\rangle = \alpha|0\rangle + \beta|1\rangle \), outcomes: \(|\alpha|^2\) or \(|\beta|^2\). |
| **Multiple Systems** | Joint systems described via tensor-product space; may be entangled—non-separable and correlated.    | Bell state \( \frac{1}{\sqrt{2}}(|00\rangle + |11\rangle) \), GHZ state.           |

---

## **Pauli Operations**
The Pauli matrices are four fundamental unitary operations:

\[
I =
\begin{pmatrix}
1 & 0 \\
0 & 1
\end{pmatrix},
\quad
X =
\begin{pmatrix}
0 & 1 \\
1 & 0
\end{pmatrix},
\quad
Y =
\begin{pmatrix}
0 & i \\
-i & 0
\end{pmatrix},
\quad
Z =
\begin{pmatrix}
1 & 0 \\
0 & -1
\end{pmatrix}
\]

- **X gate:** Flips qubits (bit-flip), turning \( |0\rangle \) into \( |1\rangle \) and vice versa.  
- **Z gate:** Flips the phase of \( |1\rangle \) (adds a minus sign), known as a phase flip.

---

## **Hadamard Operation (H)**
The Hadamard gate:

\[
H = \frac{1}{\sqrt{2}}
\begin{pmatrix}
1 & 1 \\
1 & -1
\end{pmatrix}
\]

Creates superpositions, turning basis states into equal mixtures.

---

## **Phase Operations (\(P_\theta\))**
The **Phase gate** \( P_\theta \) adds a phase shift to the state \( |1\rangle \):

\[
P_\theta =
\begin{pmatrix}
1 & 0 \\
0 & e^{i\theta}
\end{pmatrix}
\]

**Special cases:**

- **S gate:**  
\[
P_{\pi/2} =
\begin{pmatrix}
1 & 0 \\
0 & i
\end{pmatrix}
\]

- **T gate:**  
\[
P_{\pi/4} =
\begin{pmatrix}
1 & 0 \\
0 & \frac{1+i}{\sqrt{2}}
\end{pmatrix}
\]

- **Z gate:**  
\[
P_{\pi} =
\begin{pmatrix}
1 & 0 \\
0 & -1
\end{pmatrix}
\]

These unitary gates form the building blocks for manipulating qubits in quantum circuits.
