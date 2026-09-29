# H2 Molecule Ground-State Energy Solver

A quantum chemistry project solving for the ground-state potential energy surface of the hydrogen molecule ($H_2$) using PennyLane and exact Hermitian eigensolving techniques. Developed and benchmarked for the **Aqora H2 Ground State Energy Challenge**.

## Performance & Results
- **Benchmark Score**: 99 / 100
- **Leaderboard Standing**: Top 130 (#128)
- **Framework**: PennyLane Quantum Chemistry (`qml.qchem`), NumPy, SciPy

## Methodology
1. **Hamiltonian Generation**: Parses molecular geometries from `.xyz` coordinate files and generates the 4-qubit fermionic Hamiltonian mapped into Pauli spin operators via Jordan-Wigner transformation.
2. **Eigenvalue Extraction**: Implements direct Hermitian eigensolving (`np.linalg.eigvalsh`) on the Pauli Hamiltonian matrix representation to extract the exact lowest electronic eigenvalue at minimal computational latency.
3. **Chemical Accuracy**: Achieves convergence within $< 10^{-5}$ Hartree across varying bond distances.

## Project Structure
- `submission/start_here.ipynb`: Main production solver pipeline evaluated by Aqora.
- `submission/perceval.ipynb`: Supplementary photonic simulation template.
- `pyproject.toml`: Aqora pipeline definitions and dependencies.

## Usage
Run benchmark evaluations locally:
```bash
aqora test
```

Submit updated models:
```bash
aqora upload
```
