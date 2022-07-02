---
layout: post
title:  "Quantum states"
date:   2022-06-30 23:59:42 -0700
categories: quantum state
---
Now we are ready to define a quantum state in Python. We shall start with the simplest quantum state, a quantum bit or qubit. A qubit is a quantum object analogous to a classical bit which has 2 possible states 0 or 1. Thus both the classical bit and qubit have a basis of length 2, which we can denote for convenience as ['0', '1']. 

If the classical bit is in state '0', its probability density vector is [1., 0.]. If it is in state '1', its probability density vector is [0., 1.]. The classical bit cannot be in any other state. There are 3 properties that make Qubits very different from classical bits -
1. The qubit probability density vector covers the full range of possibilities, i.e it can be [0.5, 0.5], or [0.25, 0.75]. This is what is known as `superposition`, a qubit can be in both 0 and 1 at the time. (The total probability still adds up to 1 so it is not violating math, just your intuition).
2. Quantum objects have 1 additional degree of freedom because they can interfere with each other like waves do. So we can define a probability amplitude vector for each state such that probability density = |probability amplitude|^2 i.e probability amplitude = probability density e^{i\theta}, where theta is the new degree of freedom. Let us quickly put it down into code.

basis = ['0', '1']
bit0 = [1, 0]
bit1 = [0, 1]
qubita_density_vector = [0.5, 0.5]
qubitb_density_vector = [0.25, 0.75]
qubita_wave_vector = [np.sqrt(0.5)e^{i\theta} np.sqrt(0.5)e^{i\phi}]
qubita_density_vector = |qubita_wave_vector|^2


So let us summarize all that to define a qubit data structure. 
### Construction
A qubit data structure is an array of length 2, which we shall call wave vector.
### Constraints
- The array elements are complex numbers of the form re^{i\theta}.
- |wave vector|**2 = probability density vector, so it must obey all the constraints of the probability density data structure.
