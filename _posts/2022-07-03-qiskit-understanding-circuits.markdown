---
layout: post
title:  "Qiskit - Circuits"
date:   2022-07-02 23:59:42 -0700
categories: qiskit circuits
---
So we built our first Qiskit circuit.
Let us build something bigger and learn about compound gates.


Finally, we get to the juicy coding stuff. In this post, I am going to explore Qiskit. Qiskit has by far the best documentation, especially for the basics of quantum computing. 
 - They have a full textbook which is absolutely fantastic. If you found my previous chapters interesting but want to learn more about it in a systematic way, highly recommend the textbook. The interplay of physics and mathematical text interspersed with coding blocks make it super engaging and 
 - Qiskit also has a youtube series. Honestly I found the series quite dull and unengaging. I personally don't really like seeing handwritten text on a youtube video, but if you like it, they cover a lot of physics there as well.
 - The Qiskit github page is a great and much more complete than what I am going to be covering here so go check it out if you like it.
 - Qiskit also has a very cool `draw` method throughout their library which allows you to visualize the qunatum circuit easily.
All the above make Qiskit a very good framework to start with.

So let's begin.

First step, installation and setup. You will need jupyter notebooks to run Qiskit. You can set it up using either 
- follow this to install jupyter notebook on your local machine.
- follow this to run jupyter notebooks on your Google Cloud project if you have one.

I tried to run Qiskit on Google's free Colab notebook and it works pretty well.

## Basics
Computation on Qiskit is done using quantum circuits. A quantum circuit is a framework to visualize the inputs, operations and outputs of a quantum computation. 

### Creating a circuit
Check out this simple circuit to initialize 2 qubits, apply some gates and then measure the output. 
`[Cell basic circuit]`
```
from qiskit import QuantumCircuit
# Setup a new quantum circuit with 2 qubits
num_qubits = 2
qc = QuantumCircuit(num_qubits)
# Initialize the first qubit to 0 and second to 1
qc.initialize([1, 0], 0)
qc.initialize([0, 1], 1)
# Apply Pauli X on first qubit
qc.h(0)
# Apply Pauli Z on second qubit
qc.z(1)
# Save statevector
qc.save_statevector()
# Measure all qubits.
qc.measure_all()
qc.draw()
```

### Simulating a circuit
Note that creating a circuit does not compute the output of the circuit even if we have specified the input. As we learnt in the quantum measurement section, a single measurement of a qubit does not tell use everything about the quantum state. Check out this simple example of measuring the output of the circuit we created above.
`[Cell basic circuit simulation]`


