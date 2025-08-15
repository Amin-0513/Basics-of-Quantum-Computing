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
Quantum information for a single system is encoded in a **pure quantum state**, typically represented as a unit vector ![equation](https://latex.codecogs.com/svg.image?%7C%5Cpsi%5Crangle) in a two-dimensional complex Hilbert space.  
Operations on this system are **unitary transformations**, and measurements extract classical outcomes **probabilistically** per the Born rule.

**Example**:  
A single qubit prepared in:  
![equation](https://latex.codecogs.com/svg.image?%7C%5Cpsi%5Crangle%20%3D%20%5Calpha%20%7C0%5Crangle%20%2B%20%5Cbeta%20%7C1%5Crangle%2C%20%5Cquad%20%7C%5Calpha%7C%5E2%20%2B%20%7C%5Cbeta%7C%5E2%20%3D%201)  

Measuring it in the computational basis yields:  
- "0" with probability ![equation](https://latex.codecogs.com/svg.image?%7C%5Calpha%7C%5E2)  
- "1" with probability ![equation](https://latex.codecogs.com/svg.image?%7C%5Cbeta%7C%5E2)  

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
![equation](https://latex.codecogs.com/svg.image?%7C%5CPhi%5E%2B%5Crangle%20%3D%20%5Cfrac%7B1%7D%7B%5Csqrt%7B2%7D%7D%20%28%20%7C00%5Crangle%20%2B%20%7C11%5Crangle%20%29)  
- Neither qubit has a definite state on its own—only their joint state is defined.  
- If one is measured as "0", the other is guaranteed to be "0" (and likewise for "1").  

**GHZ State**:  
![equation](https://latex.codecogs.com/svg.image?%7C%5Cmathrm%7BGHZ%7D%5Crangle%20%3D%20%5Cfrac%7B1%7D%7B%5Csqrt%7B2%7D%7D%20%28%20%7C000%5Crangle%20%2B%20%7C111%5Crangle%20%29)  
- Shows **multipartite entanglement**, where the joint system’s properties can’t be described by parts alone.

---

## Summary Table

| **System**           | **Quantum Information Description**                                                                 | **Illustrative Example**                                                          |
|----------------------|-----------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------|
| **Single System**    | A lone qubit in state ![equation](https://latex.codecogs.com/svg.image?%7C%5Cpsi%5Crangle), measured probabilistically.                               | ![equation](https://latex.codecogs.com/svg.image?%7C%5Cpsi%5Crangle%20%3D%20%5Calpha%7C0%5Crangle%20%2B%20%5Cbeta%7C1%5Crangle), outcomes: ![equation](https://latex.codecogs.com/svg.image?%7C%5Calpha%7C%5E2) or ![equation](https://latex.codecogs.com/svg.image?%7C%5Cbeta%7C%5E2). |
| **Multiple Systems** | Joint systems described via tensor-product space; may be entangled—non-separable and correlated.    | Bell state ![equation](https://latex.codecogs.com/svg.image?%5Cfrac%7B1%7D%7B%5Csqrt%7B2%7D%7D%28%7C00%5Crangle%20%2B%20%7C11%5Crangle%29), GHZ state.           |

---

## **Pauli Operations**
The Pauli matrices are four fundamental unitary operations:

![equation](https://latex.codecogs.com/svg.image?I%20%3D%20%5Cbegin%7Bpmatrix%7D1%20%26%200%5C%5C0%20%26%201%5Cend%7Bpmatrix%7D%2C%20%5Cquad%20X%20%3D%20%5Cbegin%7Bpmatrix%7D0%20%26%201%5C%5C1%20%26%200%5Cend%7Bpmatrix%7D%2C%20%5Cquad%20Y%20%3D%20%5Cbegin%7Bpmatrix%7D0%20%26%20i%5C%5C-i%20%26%200%5Cend%7Bpmatrix%7D%2C%20%5Cquad%20Z%20%3D%20%5Cbegin%7Bpmatrix%7D1%20%26%200%5C%5C0%20%26%20-1%5Cend%7Bpmatrix%7D)

- **X gate:** Flips qubits (bit-flip), turning ![equation](https://latex.codecogs.com/svg.image?%7C0%5Crangle) into ![equation](https://latex.codecogs.com/svg.image?%7C1%5Crangle) and vice versa.  
- **Z gate:** Flips the phase of ![equation](https://latex.codecogs.com/svg.image?%7C1%5Crangle) (adds a minus sign), known as a phase flip.

---

## **Hadamard Operation (H)**
The Hadamard gate:  

![equation](https://latex.codecogs.com/svg.image?H%20%3D%20%5Cfrac%7B1%7D%7B%5Csqrt%7B2%7D%7D%20%5Cbegin%7Bpmatrix%7D1%20%26%201%5C%5C1%20%26%20-1%5Cend%7Bpmatrix%7D)

Creates superpositions, turning basis states into equal mixtures.

---

## **Phase Operations** ![equation](https://latex.codecogs.com/svg.image?P_%5Ctheta)
The **Phase gate** ![equation](https://latex.codecogs.com/svg.image?P_%5Ctheta) adds a phase shift to the state ![equation](https://latex.codecogs.com/svg.image?%7C1%5Crangle):

![equation](https://latex.codecogs.com/svg.image?P_%5Ctheta%20%3D%20%5Cbegin%7Bpmatrix%7D1%20%26%200%5C%5C0%20%26%20e%5E%7Bi%5Ctheta%7D%5Cend%7Bpmatrix%7D)

**Special cases:**

- **S gate:**  
![equation](https://latex.codecogs.com/svg.image?P_%7B%5Cpi/2%7D%20%3D%20%5Cbegin%7Bpmatrix%7D1%20%26%200%5C%5C0%20%26%20i%5Cend%7Bpmatrix%7D)

- **T gate:**  
![equation](https://latex.codecogs.com/svg.image?P_%7B%5Cpi/4%7D%20%3D%20%5Cbegin%7Bpmatrix%7D1%20%26%200%5C%5C0%20%26%20%5Cfrac%7B1%2Bi%7D%7B%5Csqrt%7B2%7D%7D%5Cend%7Bpmatrix%7D)

- **Z gate:**  
![equation](https://latex.codecogs.com/svg.image?P_%7B%5Cpi%7D%20%3D%20%5Cbegin%7Bpmatrix%7D1%20%26%200%5C%5C0%20%26%20-1%5Cend%7Bpmatrix%7D)

These unitary gates form the building blocks for manipulating qubits in quantum circuits.
