# Quantum-computing
Problem Statement and solutions on quantum computing 
from qiskit import QuantumCircuit, transpile, assemble, Aer, execute

# Create a quantum circuit with 1 qubit
circuit = QuantumCircuit(1)

# Apply the Hadamard gate to create a superposition
circuit.h(0)

# Measure the qubit to get a classical output
circuit.measure_all()

# Display the circuit
print(circuit)

# Execute the circuit on a simulator
simulator = Aer.get_backend('qasm_simulator')
job = execute(circuit, simulator, shots=1000)
result = job.result()

# Get the counts of the results
counts = result.get_counts(circuit)
print("Measurement results:", counts)
