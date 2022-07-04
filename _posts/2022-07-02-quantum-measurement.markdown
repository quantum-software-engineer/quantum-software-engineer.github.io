---
layout: post
title:  "Quantum measurement"
date:   2022-07-02 03:59:42 -0700
categories: quantum measurement
---
This is the most important section of the introduction to quantum computing.

Some preamble : Up until now, all the quantum stuff we have done follows the same rules as classical stuff, with a few additional degrees of freedom. Measurement is where it all changes from theory to experiment. My advice here, if you are a quantum novice, is to just try to understand how it works, and not why it works this way. No one understands why. Einstein never truly accepted this and spent many years tried to disprove this unsuccessfully. Feynman said, if you think you understand it, you dont. The concepts and consequences of quantum measurement were `discovered` not `invented`. Physicists found out that the world works this way and then built a theory that matches the experiments and makes accurate predictions. A century of work has gone into trying to test quantum physics and/or find alternate theories, but the current formalism has been extraordinarily successful both in explaining known physics and predicting novel phenomena, so as far as we can tell, this is just how the world really works. Quantum computing is our attempt to harness this property to do computation that would not be possible using the standard rules of computing that we have invented.

Another way to think about it is, if all quantum computation just followed the expected classical rules, there would be no alpha in it. Quantum measurement `is` the alpha, it is where quantum computing derives a lot of its unique power from. So it is important to understand how it works.

The simplest one-liner difference between classical and quantum measurement is,
`measuring a quantum state changes the state`.

## Changes how exactly?
If a bit is in state `[0, 1]`, and if you measure it, you learn the state but nothing happens to the bit itself. If we take a quantum example, say a qubit is in state `[0.25, 0.75]`, and we `measure` it, some weird things happen -
- Weird fact 1
You don't get the numbers `[0.25, 0.75]`. Measurement results are `always` one of the basis states. So you will either get `[1, 0]` or `[0, 1]`. 
- Weird fact 2
The qubit state itself has changed after the measurement to the corresponding basis state. If you got `[1, 0]`, the state is now `[1, 0]`. Further measurements of the same state will give you `[1, 0]` and the state will stay in `[1, 0]`. If instead you had gotten `[0, 1]` as the answer for the first measurement, the qubit will now be in that state and further measurements will not makea  difference. 
- Wierd fact 3
If you have lots of, say a million, qubits in state `[0.25, 0.75]` lying around, and you measure all of them one by one, each individual qubit will randomly collapse into either `[1, 0]` or `[0, 1]` and it is `impossible` to predict which state it will collapse to. But the overall statistics of `[1, 0] : [0, 1]` will be `0.25:0.75` as predicted by the probability density vector. If you have a qubit already in state `[1, 0]`, you can make a million measurements on it, you will get exactly `[1, 0]` a million times.
- Weird fact 4
This property extends to multi-qubit states. If the original qubits are in state `[0.25, 0., 0., 0.75]`, (remember the basis is `[00, 01, 10, 11]`) and now you measure just the first qubit. The qubits collapses to 0 or 1. But in the original state, when the first qubit is 0 the second is also 0 and when the first qubit is 1 the second is also 1. Amazingly even if we just measure the first qubit and it collapses, it collapses the second qubit with it. So if the first qubit measures to be 0, we atuomatically know that the second qubit is also 0 even though we havent measured it.
- Weird fact 5
We can measure in different bases and the wavefunction collapse is in the basis of measurement. If we measure in the basis `[0.25, 0.75]`, we will get `[1, 0]` as the answer even the first time. This is because in the `[0.25, 0.75]` basis, the qubit is already in the state `[1, 0]`. 

Fact 1 is called collapse of the wavefunction, measurement causes the wavefunction to collapse into 1 of the basis states.
Fact 4 is named by Einstein as spooky action at a distance. The wavefunction of two entangled objects collapses for both simultaneously, even if they are in different rooms or buildings or countries.
Fact 5 is the foundation of measurement-based computation where a measurement in a rotated basis is equivalent to applying a rotation followed by a measurement in the unrotated basis. So if you have different measuring options, you can effectively get gates for free.

That's it. Now you have all the tools to do some basic quantum computation and circuits. If you understood most of the stuff till now but are hazy on the details, don't worry, we will harden the concepts described here with practical examples in the next section.