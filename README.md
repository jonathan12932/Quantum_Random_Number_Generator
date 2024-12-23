# Quantum Random Number Generator (QRNG)

This project implements a **Quantum Random Number Generator (QRNG)** using **Qiskit** and IBM Quantum's **ibm_brisbane backend**. The QRNG generates truly random integers between 0 and 9 by leveraging quantum mechanics, specifically quantum superposition and probabilistic state collapse.

## Features

- **Quantum Randomness**: Utilizes a 4-qubit quantum circuit to achieve true randomness, surpassing classical pseudo-random generators.
- **Superposition and Entanglement**: Employs Hadamard gates to create superposition states and harnesses quantum measurement for unbiased random outputs.
- **Error Handling**: Includes a validation loop to ensure results fall within the range of 0–9.
- **Scalable Design**: Processes 100 quantum jobs, generating 100 valid random numbers in a single execution.

## Table of Contents

1. [Installation](#installation)
2. [Usage](#usage)
3. [How It Works](#how-it-works)
4. [Example Output](#example-output)
5. [Tech Stack](#tech-stack)
6. [License](#license)

## Installation

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/yourusername/quantum-random-number-generator.git
   cd quantum-random-number-generator
Set Up Environment:

Install Python 3.8 or later.
Install dependencies:
bash
Copy code
pip install qiskit qiskit-ibm-runtime python-dotenv
Set Up IBM Quantum Token:

Create a .env file in the project directory:
bash
Copy code
touch .env
Add your IBM Quantum token:
bash
Copy code
IBM_QUANTUM_TOKEN=your_ibm_quantum_token
Usage
Run the script to generate random numbers:

bash
Copy code
python quantum_random_number_generator.py
The program outputs 100 random integers between 0 and 9 to the console and stores them in a list.

How It Works
Quantum Circuit Design:

A 4-qubit circuit is initialized.
Hadamard gates are applied to each qubit, creating a superposition of all possible states.
Measurement:

Each qubit is measured, collapsing the quantum state to a classical bitstring (e.g., '0101').
Validation and Filtering:

The bitstring is converted to an integer (base-10).
Integers greater than 9 are discarded, and the circuit is re-executed until 100 valid integers are generated.
Backend Execution:

The circuit is transpiled and executed on IBM Quantum's ibm_brisbane backend using Qiskit.
Example Output
plaintext
Copy code
Measured integer: 5
Final random number (0–9): 5
Measured integer: 3
Final random number (0–9): 3
...
Random numbers: [5, 3, 7, 0, 1, 8, 6, 9, 4, 2, ...]
Tech Stack
Programming Language: Python
Quantum Framework: Qiskit
Quantum Backend: IBM Quantum (ibm_brisbane)
Environment Management: dotenv
