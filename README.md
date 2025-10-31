# Quantum Double-Slit Experiment: A Multi-Qubit Adaptation

## Summary
This project demonstrates the famous double-slit experiment on a quantum computer. The code in this notebook is adapted from the YouTube video [Running the Double-Slit Experiment on a Quantum Computer](https://youtu.be/PBrYoAdLzXo?si=1GKFmKGxF7wgDTPC) and has been updated to run on the modern IBM Quantum platform.

A key innovation in this notebook is the simulation methodology. Instead of running a single-qubit circuit multiple times to simulate one point on the screen, this version runs a multi-qubit circuit where each qubit represents a single point. This approach significantly changes how the problem is parallelized on quantum hardware.

### Key Improvements

1.  **IBM Quantum Platform Compatibility**: The original code has been refactored to use the latest (Oct 2025) `qiskit_ibm_runtime` and authentication methods required by the current IBM Quantum platform.

2.  **Multi-Qubit Parallelization**: The core logic was adapted to build a single, large quantum circuit. Each qubit in the circuit emulates a different point on the detection screen. This contrasts with the original method of repeatedly running a single-qubit circuit for each point.

3.  **Performance**: With this new approach, a circuit simulating a screen with 100 discrete points (using a 100-qubit circuit) takes approximately **2 seconds** to execute on a quantum processor, demonstrating an efficient use of multi-qubit systems for this type of simulation.

## Authors
* Jhoan Eusse

## Execution

1. Set Up IBM Quantum Credentials: To run the experiment on real quantum hardware, you need an IBM Quantum account.

2. Log in to your IBM Quantum account. Copy your API token and Instance name from the account settings page.

3. Replace "[YOUR_IBM_KEY_HERE]" and "[YOUR_IBM_INSTANCE_HERE]" with your token and instance name on the respective cell inside the [doubleSlit_parallel.ipynb](https://github.com/EusseJhoan/doubleSlit_Qiskit/blob/main/doubleSlit_parallel.ipynb) notebook.

```bash
# Initialize the Qiskit Runtime Service with your credentials
service = QiskitRuntimeService(channel="ibm_quantum_platform", instance = "[YOUR_IBM_INSTANCE_HERE]", token = "[YOUR_IBM_KEY_HERE]")
```

4. Execute the notebook [doubleSlit_parallel.ipynb: ](https://github.com/EusseJhoan/doubleSlit_Qiskit/blob/main/doubleSlit_parallel.ipynb)

## Prerequisites

To run this notebook, you will need Python 3.8+ and the following libraries:

*   `qiskit`
*   `qiskit_ibm_runtime`
*   `numpy`
*   `matplotlib`

You can install them using pip:
```bash
pip install qiskit qiskit_ibm_runtime numpy matplotlib

