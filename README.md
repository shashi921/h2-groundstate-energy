# H2 Molecule Ground-State Energy Solver

This repository contains solutions for calculating the ground-state potential energy surface of the hydrogen molecule ($H_2$) across two distinct quantum computing architectures and challenges.

---

## Part 1: Quantinuum SG Grand Challenge 2026 (Phase 1 Submission)
**Author:** Chagamreddy Shashi Kumar Reddy (ECE Undergraduate)

### Overview
Designed an ultra-low-depth Variational Quantum Eigensolver (VQE) tailored specifically for Quantinuum's trapped-ion architecture. The circuit minimizes depth to protect against decoherence and gate noise on near-term hardware.

### Methodology & Hardware Execution
* **Hamiltonian Mapping:** Mapped the H2 molecule via the Jordan-Wigner transformation into a 4-qubit Pauli operator.
* **Ansatz Design:** Utilized Qiskit to build a hardware-efficient ansatz that exploits the native all-to-all connectivity of trapped-ion systems, eliminating SWAP routing overhead.
* **Execution Backend:** Compiled and natively executed on the **Quantinuum H2-Emulator**.

### Empirical Results
* **Job ID:** `quantinuum-h2-emu-1791624633`
* **Qubit Allocation:** 4 Physical Qubits
* **Circuit Depth:** 6 Layers (4 Ry, 4 CX, 2 X)
* **Converged Ground-State Energy:** -1.246647 Hartree

### Repository Contents
* `quantinuum_solver.py`: Core Qiskit script for the VQE circuit.
* `execution_evidence.json`: Raw telemetry and execution log for the H2-Emulator.
* `SG_Grand_Challenge_Executive_Summary_Final.pdf`: 1-page executive overview.
* `SG_Grand_Challenge_Technical_Report_Final.pdf`: 5-section technical methodology report.
* `SG_Grand_Challenge_Presentation_Final.pptx`: 5-slide pitch deck.

---

## Part 2: Aqora H2 Ground State Energy Challenge[cite: 19]
A quantum chemistry project solving for the ground-state potential energy surface of the hydrogen molecule ($H_2$) using PennyLane and exact Hermitian eigensolving techniques[cite: 19]. Developed and benchmarked for the **Aqora H2 Ground State Energy Challenge**[cite: 19].

### Performance & Results[cite: 19]
* **Benchmark Score**: 99 / 100[cite: 19]
* **Leaderboard Standing**: Top 130 (#128)[cite: 19]
* **Framework**: PennyLane Quantum Chemistry (`qml.qchem`), NumPy, SciPy[cite: 19]

### Methodology[cite: 19]
1. **Hamiltonian Generation**: Parses molecular geometries from `.xyz` coordinate files and generates the 4-qubit fermionic Hamiltonian mapped into Pauli spin operators via Jordan-Wigner transformation[cite: 19].
2. **Eigenvalue Extraction**: Implements direct Hermitian eigensolving (`np.linalg.eigvalsh`) on the Pauli Hamiltonian matrix representation to extract the exact lowest electronic eigenvalue at minimal computational latency[cite: 19].
3. **Chemical Accuracy**: Achieves convergence within $< 10^{-5}$ Hartree across varying bond distances[cite: 19].

### Project Structure[cite: 19]
* `submission/start_here.ipynb`: Main production solver pipeline evaluated by Aqora[cite: 19].
* `submission/perceval.ipynb`: Supplementary photonic simulation template[cite: 19].
* `pyproject.toml`: Aqora pipeline definitions and dependencies[cite: 19].

### Usage[cite: 19]
Run benchmark evaluations locally[cite: 19]:
```bash
aqora test
