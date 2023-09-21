# Advanced Quantum Algorithms

Grading: 
- Written Exam
- Not super mathematical
- Exercises every week
- Pass or fail for exercises

## Overview

- Quantum Advantage: Quantum computers can solve problems that classical computers cannot solve in a reasonable amount of time.

- Hardware: 
    - Digital
    - Gate Time ( Clock Frequency )
    - Analog 

- Quantum Software
    - Adiabatic Quantum Computing: Optimization
    - Hamiltonian Simulation: Chemistry and Physics
    - Variational Algorithms: Optimization, Chemistry, Physics
    - Search Algorithms: Optimization, Data Science, Finance
    - Quantum Machine Learning

All concepts are viewed from the perspective of complexity theory and practical implemenations.

### Quantum Computer

- Set of controllable qbits
- Quantum gates are operations that can be applied to qbits
- Qbits are much bigger in size than classical bits
- Clock frequency must be lower than the electronic components controlling the qbits
- Operations are noisy, meaning they do not always perform the desired computation
- Todays computers have a clock frequency of 100 MHz, where largers systems are projected tohave a frequency of 10 - 100 kHz.
- Error correction: Logical Qbit is encoded in multiple physical qbits to reduce noise. Maybe 20-50 physical qbits per logical qbit. Part of the reason why quantum computers are so slow.

### Quantum Advantage

- For many problems the runtime increases exponentially with the size of the problem. 
- Quantum computers have a scaling advantage over classical computers for certain problems.
- We want to understand weather the problems make sense to be solved on a quantum computer or not. This means we need to know the crossover point where the quantum computer is faster than the classical computer.

### Theory

$\ket{q} \in \mathbb{C}^n$ is a vector of complex numbers. 

$\ket{q} = \begin{bmatrix} 1 \\ 0 \end{bmatrix}$

$\ket{q} = \alpha \ket{0} + \beta \ket{1} = \alpha \begin{bmatrix} 1 \\ 0 \end{bmatrix} + \beta \begin{bmatrix} 0 \\ 1 \end{bmatrix}$

$|\alpha|^2 + |\beta|^2 = 1$

We can also state the probability of measuring a certain state:

$P(\ket{0}) = |\alpha|^2 = \braket{0|q}$

Multiple qbits:

$\alpha \ket{00} + \beta \ket{01} + \gamma \ket{10} + \delta \ket{11}$

Potential Product State:

$\ket{v} \otimes \ket{w} = \begin{bmatrix} v_0 \\ v_1 \end{bmatrix} \otimes \begin{bmatrix} w_0 \\ w_1 \end{bmatrix} = \begin{bmatrix} v_0 \begin{bmatrix} w_0 \\ w_1 \end{bmatrix} \\ v_1 \begin{bmatrix} w_0 \\ w_1 \end{bmatrix} \end{bmatrix} = \begin{bmatrix} v_0 w_0 \\ v_0 w_1 \\ v_1 w_0 \\ v_1 w_1 \end{bmatrix}$

$\ket{00} = \begin{bmatrix} 1 \\ 0 \end{bmatrix} \otimes \begin{bmatrix} 1 \\ 0 \end{bmatrix} = \begin{bmatrix} 1 \\ 0 \\ 0 \\ 0 \end{bmatrix}$

$\ket{01} = \begin{bmatrix} 1 \\ 0 \end{bmatrix} \otimes \begin{bmatrix} 0 \\ 1 \end{bmatrix} = \begin{bmatrix} 0 \\ 1 \\ 0 \\ 0 \end{bmatrix}$

Qiskit uses the convention of $\ket{q_1} \otimes \ket{q_0}$ (little endian)