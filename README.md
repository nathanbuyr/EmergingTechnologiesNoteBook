# Emerging Technologies Assignment
This repository contains solutions to the Emerging Technologies assessment. The primary deliverable is `problems.ipynb`, a Jupyter notebook that explores quantum algorithms and their advantages over classical computation, with a focus on the Deutsch-Jozsa algorithm implemented in Qiskit.

The notebook is organized into problems with explanations, Python implementations, tests, and demonstrations. It covers core quantum computing ideas such as superposition, quantum oracles, quantum circuits, and the reasoning behind quantum speedups.

## Target audience
This submission is written for an informed computing professional (for example, a prospective employer). It assumes general programming knowledge, but not prior experience with quantum computing, so the notebook includes detailed context, references, and explanations.

## Setup instructions
1. Clone the repository:
	```bash
	git clone https://github.com/ianmcloughlin/emerging-technologies.git
	cd emerging-technologies-assignment
	```
2. Create and activate a virtual environment:
	```bash
	python3 -m venv venv
	source venv/bin/activate
	```
	On Windows:
	```bash
	venv\Scripts\activate
	```
3. Install dependencies (Python 3.8+ recommended):
	```bash
	python -m pip install --upgrade pip
	pip install -r requirements.txt
	```
4. Run the notebook:
	```bash
	jupyter notebook problems.ipynb
	```
	Or use JupyterLab:
	```bash
	jupyter lab problems.ipynb
	```

## Repository structure
- `problems.ipynb`: Main notebook with solutions and explanations.
- `requirements.txt`: Python package dependencies.
- `README.md`: This file.

## Problems overview
### Problem 1: Generating random Boolean functions
Implements `random_constant_balanced()` to generate a callable `f(a, b, c, d) -> bool` that is guaranteed to be constant or balanced. The notebook explains the balanced count $\binom{16}{8} = 12{,}870$ and uses `random.sample` to enforce the 8-of-16 constraint. A helper `classify_constant_or_balanced()` exhaustively validates generated functions and includes seeded tests and truth-table demonstrations.

### Problem 2: Classical testing for function type
Implements `determine_constant_balanced(f)` with an early-exit strategy and a counted variant that proves the $2^{n-1} + 1$ bound for $n = 4$, giving a 9-query worst case. The notebook includes best-case and worst-case targeted tests plus a 1000-function random trial that confirms the 9-call maximum.

### Problem 3: Quantum oracles
Builds Qiskit oracles for the four single-input Boolean functions (constant 0/1, identity, and NOT) using the standard reversible construction $|x\rangle|y\rangle \to |x\rangle|y \oplus f(x)\rangle$. The oracles are grouped with their truth tables, circuit diagrams are drawn side by side, and basis-state behavior is described to show how each oracle flips the ancilla.

### Problem 4: Deutsch's algorithm with Qiskit
Implements `deutsch_circuit(oracle)` to classify single-bit functions using one oracle query, then runs all four oracles through the circuit. Results are deterministic across multiple shot counts (1, 10, 100, 1024), and a comparison table highlights the 1-query quantum result versus the 2-query classical minimum.

### Problem 5: Scaling to the Deutsch-Jozsa algorithm
Implements `build_oracle(truth_table)` for 4-bit functions using MCX gates with inverted controls, then wraps it with `deutsch_jozsa(oracle)` and a `classify()` helper that checks for the `0000` outcome. The notebook tests constant and balanced truth tables (including one generated from Problem 1) and includes a gate cost snapshot after transpilation.
