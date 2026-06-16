# Paktron-Version-6.1.6
# 🚀 PKTron Quantum HPC & SDK Simulator v6.1.6

### Quantum Computing • HPC Acceleration • SDK Development Platform

![Python](https://img.shields.io/badge/Python-3.8+-blue)
![License](https://img.shields.io/badge/License-MIT-green)
![Downloads](https://img.shields.io/badge/Downloads-10K+-brightgreen)
![GPU](https://img.shields.io/badge/GPU-cuQuantum%20Ready-orange)
![MPI](https://img.shields.io/badge/MPI-Distributed-red)
![HPC](https://img.shields.io/badge/HPC-Ready-purple)

---

## 🌟 What is PKTron?

**PKTron v6.1.6** is a unified **Quantum Computing + High Performance Computing (HPC) + Software Development Kit (SDK)** framework that combines advanced quantum simulation, quantum algorithms, quantum machine learning, quantum chemistry, quantum cryptography, and distributed HPC acceleration into a single platform.

With more than **10,000 downloads**, PKTron provides one of the broadest open-source quantum software ecosystems available today.

```bash
pip install pktron
```

---

# ⚡ Key Highlights

### Quantum Simulation

* 13 Quantum Simulation Backends
* Statevector, Density Matrix, MPS
* Clifford & Extended Stabilizer
* Tensor Networks (MPS, PEPS, MERA)
* Pulse-Level Simulation
* Multi-GPU Simulation
* Distributed MPI Runtime
* Matchgate & Fermionic Gaussian Simulators

### Quantum Algorithms

* 50+ Algorithms
* Grover Search
* Shor's Factoring
* Quantum Phase Estimation
* QAOA
* HHL
* Quantum Walks
* QSVT
* Quantum Metropolis
* Quantum SDP
* Quantum NAS
* GRAPE Optimal Control

### Quantum Chemistry

* VQE
* UCCSD
* ADAPT-VQE
* Jordan-Wigner
* Bravyi-Kitaev
* Parity Mapping
* Molecular Hamiltonians

### Quantum Machine Learning

* QNN
* QSVM
* Quantum GAN
* QCNN
* QBM
* Quantum Reinforcement Learning
* Quantum Federated Learning
* Quantum Transfer Learning

### Quantum Error Correction

* Surface Code
* Steane Code
* Bacon-Shor
* Color Code
* Repetition Code
* Heavy-Hex

### Quantum Cryptography

* BB84
* E91
* B92
* TF-QKD
* MDI-QKD
* Device Independent QKD

### Industry Modules

* Finance
* Defense
* Portfolio Optimization
* Credit Risk Analysis
* Mission Scheduling
* Quantum Cryptanalysis

---

# 🆕 What's New in v6.1.6

PKTron 6.1.6 introduces major HPC and SDK upgrades inspired by modern production-grade quantum runtimes.

## NVIDIA cuQuantum Integration

### cuStateVec Backend

```python
import pktron as pk

qc = pk.QuantumCircuit(2)
qc.h(0)
qc.cx(0,1)

result = pk.cuStateVec().run(qc, shots=1024)
```

Features:

* NVIDIA cuQuantum acceleration
* Automatic GPU detection
* CuPy integration
* Transparent CPU fallback

---

## cuTensorNet Backend

Tensor-network simulation accelerated through NVIDIA cuTensorNet.

```python
backend = pk.cuTensorNet()
```

Features:

* GPU tensor contractions
* Large-scale tensor networks
* Automatic MPS fallback

---

## GPU Quantum Primitives

New GPU-accelerated primitives:

```python
pk.GPUSampler()
pk.GPUEstimator()
```

Built directly on top of cuStateVec.

---

## Automatic Backend Selection

PKTron can now automatically choose the best simulation strategy.

```python
pk.auto_select_method(circuit)

backend = pk.AutoBackend()
```

Selection logic:

* Clifford → Stabilizer
* Low Entanglement → MPS
* CUDA Available → GPU
* Otherwise → Statevector

---

## Gate Fusion Optimization

New transpiler optimization:

```python
pm = pk.PassManager([
    pk.GateFusionPass()
])

optimized = pm.run(circuit)
```

Benefits:

* Fewer gates
* Faster execution
* Exact equivalence

---

## Unitary Synthesis

Exact synthesis of arbitrary unitaries.

```python
pk.UnitarySynthesis()
```

Includes:

* OneQubitEulerDecomposer
* TwoQubitBasisDecomposer

---

## Solovay-Kitaev Compiler

Approximate arbitrary single-qubit unitaries using discrete gate sets.

```python
pk.SolovayKitaev()
```

Supported basis:

* H
* T
* T†
* S
* S†

---

## Dynamics Backend

Time-dependent Hamiltonian simulation.

```python
pk.DynamicsBackend()
```

Capabilities:

* Schrödinger evolution
* Pulse simulation
* Rabi oscillations
* JAX acceleration
* RK4 integration

---

## New Quantum Information Structures

### PauliTable

Vectorized symplectic Pauli representation.

```python
pk.PauliTable()
```

### StabilizerState

Exact CHP-tableau stabilizer simulator.

```python
pk.StabilizerState(circuit)
```

Scales to thousands of Clifford qubits.

---

# 🚀 Installation

## Standard

```bash
pip install pktron
```

## GPU Support

```bash
pip install pktron[gpu]
```

---

# ⚡ Quick Start

## Bell State

```python
import pktron as pk

qc = pk.QuantumCircuit(2)

qc.h(0)
qc.cx(0,1)

result = pk.execute(qc, shots=1024)

print(result["counts"])
```

---

## Grover Search

```python
import pktron as pk

grover = pk.GroverSearch(
    n_qubits=4,
    marked_states=[5,10]
)

result = grover.run()

print(result["found"])
```

---

## VQE for H₂

```python
import pktron as pk

H = pk.QuantumChemistry.h2_hamiltonian(
    distance=0.735
)

result = pk.VQE(H).run()

print(result["energy"])
```

---

# 📊 Framework Scale

| Category                 | Capability |
| ------------------------ | ---------- |
| Simulators               | 13         |
| Algorithms               | 50+        |
| QML Models               | 10+        |
| Error Correction Codes   | 6          |
| Error Mitigation Methods | 9+         |
| QKD Protocols            | 6          |
| Finance Modules          | 6          |
| Defense Modules          | 6          |
| Submodules               | 39         |
| Public APIs              | 190+       |
| Downloads                | 10K+       |

---

# 🔄 Interoperability

PKTron integrates with:

* Qiskit
* Cirq
* PennyLane
* OpenQASM 2
* OpenQASM 3
* Quil
* IonQ
* Amazon Braket

---

# 🏗 HPC Infrastructure

### CPU

* AVX-512
* AVX2
* SSE
* OpenMP

### GPU

* CUDA
* CuPy
* NVIDIA cuStateVec
* NVIDIA cuTensorNet

### Distributed

* MPI Runtime
* Multi-GPU Runtime
* Async Execution
* Circuit Cache

---

# 📚 Documentation

Detailed documentation includes:

* 150+ Classes
* 39 Submodules
* 50+ Algorithms
* Quantum Chemistry
* Quantum Machine Learning
* Error Correction
* Error Mitigation
* Cryptography
* Finance
* Defense
* HPC Infrastructure

See:

* Documentation
* API Reference
* Changelog
* Examples

---

# 🏛 Developed By

**CETQAC**

Centre of Excellence for Technology, Quantum & AI

Canada 🇨🇦 • Pakistan 🇵🇰

---

# 📜 License

MIT License

Copyright © 2024–2026 CETQAC

---

### ⭐ Star the Repository

If PKTron supports your research, education, or development work, consider starring the repository and contributing to its future development.

