---
layout: post
title:  "Simplifying Quantum Operators and States"
date:   2022-07-03 03:59:42 -0700
categories: quantum operator advanced
---
We have learnt about two quantum objects, state and operators.
Let us take a second to contextualize this information.
Mathematically, states are vectors and operators are matrics that transform vectors.
Physically, states are the wavefunctions that describe quantum particles such as electrons and photons and operators are effects that change the sate of the particles such as electromagnetic force, gravity or even just time evolution. 

As we shall soon see, doing quantum calculations can get complicated very quickly. There are some optimizations, I will use going forward to make the calculations simpler. 

We don't need to keep track of both states and operators, we can simplify by reducing the input states and output states to `[0, 1]` and offloading all analysis to the operators. Let's see some examples.

The circuit below creates `+` states starting from `[0, 1]` states. We measure in the `[0, 1]` basis and get the following result.
Now, consider we just initialize a state already in `+` state and then proceed to measure it in the `[0, 1]` basis.
We see that these two are equivalent.

Finally lets flip this circuit on its head, this time we start from `[0, 1]` and measure in the `[+, -]` basis. Thus measuring in the `+` basis is equivalent to the above two cases.

problem and apply what is known as a bell measurement, i.e measurement in the bell state basis.
Turns out the two are equivalent.

The circuit below creates bell states starting from `[0, 1]` states. We measure in the `[0, 1]` basis and get the following states.
Let us flip this circuit on its head, this time we start from. problem and apply what is known as a bell measurement, i.e measurement in the bell state basis.
Turns out the two are equivalent.



Heisenberg representation


So far we have only explored the Pauli gates X, Y and Z gates and their corresponding 2-qubit control gates.

This is a special group of operators called the Clifford group. You can read more about the Clifford group here.

For our purpose, the Clifford group is defined as the generators of the Pauli group i.e any operator C in the Clifford group applied on any Pauli gate P obeys
```
CPC\adjoint = P'
```

The Clifford
[Clifford group]: 

Note that in the previous chapter, we did not define the operations on qubit data structure. So, what operations can you do with a qubit?

Think of what you would do with classical computers. You have a number of bits. To do any computations, you need to apply transformations on bits, also known as gates. You may be aware of gates such as OR, AND, NOT, NAND etc. There is a well known result that NAND gates are universal, i.e. you can make any gate or combination of gates using just NAND gates as building blocks.

So let's look at the NAND gate -

'img'

Truth table - ``

Lets make these concepts quantum. There is a single universal gate in the quantum world as well called the Toffoli gate. But unlike classical computers, quantum hardware is not advanced enough to the point that we can easily build hundreds of Toffoli gates to simulate other gates. Therefore we try to minimize the numbers of gates we have to build even if it means building different types of gates. So let us learn about some of the quantum gates, dont worry, there are only 4 you need to know right now.

## The Pauli gates - X Y and Z

## CX

That was easy enough. Now we just need to know one more thing before we can do some quantum computation. And this is where it gets real.


