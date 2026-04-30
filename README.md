# Emerging Technologies Assignment

This repository contains solutions to the Emerging Technologies assessment. The primary deliverable is `problems.ipynb`, a Jupyter notebook that explores quantum algorithms and their advantages over classical computation, with a focus on the Deutsch-Jozsa algorithm implemented in Qiskit.

The notebook is organised into five problems with explanations, Python implementations, tests, and demonstrations. It covers core quantum computing ideas including superposition, quantum oracles, quantum circuits, and the reasoning behind quantum speedups. It is written for an informed computing professional who may not have prior experience with quantum computing, so detailed context and references are included throughout.

---

## Setup

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
4. Launch the notebook:
	```bash
	jupyter notebook problems.ipynb
	```
	Or with JupyterLab:
	```bash
	jupyter lab problems.ipynb
	```

---

## Repository Structure

| File | Description |
|---|---|
| `problems.ipynb` | Main notebook with all solutions, explanations, and demonstrations |
| `requirements.txt` | Python package dependencies |
| `README.md` | This file |

---

## Problems Overview

**Problem 1 — Generating Random Boolean Functions**
Implements `random_constant_balanced()` to generate a callable `f(a, b, c, d) -> bool` guaranteed to be constant or balanced, with a helper `classify_constant_or_balanced()` to validate generated functions.

**Problem 2 — Classical Testing for Function Type**
Implements `determine_constant_balanced(f)` with an early-exit strategy that proves the $2^{n-1} + 1$ query bound for $n = 4$, giving a 9-query worst case. Includes targeted tests and a 1000-function random trial.

**Problem 3 — Quantum Oracles**
Builds Qiskit oracles for the four single-input Boolean functions using the standard reversible construction $|x\rangle|y\rangle \to |x\rangle|y \oplus f(x)\rangle$, with circuit diagrams and basis-state verification.

**Problem 4 — Deutsch's Algorithm**
Implements `deutsch_circuit(oracle)` to classify single-bit functions in one oracle query. Results are deterministic across all shot counts, with a comparison against the 2-query classical minimum.

**Problem 5 — Deutsch-Jozsa Algorithm**
Scales to 4-bit functions using `build_oracle(truth_table)` with MCX gates and inverted controls. Includes gate cost analysis after transpilation and a direct classical vs quantum query comparison across random functions.

---

## AI Usage

AI assistance tools including GitHub Copilot and Claude Sonnet 4.6 were used to help create docstrings, structure this README, and build test cases.