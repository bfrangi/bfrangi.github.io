---
layout: post
title:  "The Qubit: Interpreting the Bloch Sphere"
date:   2024-09-22 09:28:59 +0100
categories: physics
---

### Introduction

In quantum computing, the qubit is often represented using what is known as the Bloch Sphere. This powerful visualization tool provides a simple yet comprehensive way to understand and manipulate qubit states once you grasp the underlying concepts. The Bloch Sphere representation is important for several reasons:

1. Intuitive visualization: It offers a clear, three-dimensional picture of qubit states, making it easier to conceptualize quantum superposition and phase relationships.

2. Parameter reduction: As explained in the article, it reduces the representation of a qubit state from four parameters to just two ($\theta$ and $\phi$).

3. State characterization: Any qubit state can be uniquely characterized by its position on the Bloch Sphere, providing a complete description of the qubit.

4. Relationship to coefficients: The Bloch Sphere coordinates directly relate to the coefficients $c_0$ and $c_1$, offering a geometric interpretation of these complex numbers.

5. Visualization of quantum operations: The Bloch sphere representation is particularly useful for visualizing single-qubit operations and quantum gates.

By understanding the Bloch Sphere, one gains valuable insights into the nature of qubits and their behavior in quantum systems.

### What is a qubit?

A qubit is the quantum equivalent of the classical bit. It is a quantum system that has two possible states, just like the classical bit. The difference between them is the fact that a qubit does not need to be in one of those two states, but it can also be in a superposition of the two. Physically, it can be modelled as a two-level system, with a state $\mid0\rangle$ and a state $\mid1\rangle$. Therefore, the state of a qubit can be written as:

$$\mid\psi\rangle = c_0 \mid0\rangle + c_1 \mid1\rangle$$

If this was a classical bit, we would only allow $c_0$ and $c_1$ the values $0$ or $1$, where exactly one of the two would need to be equal to $1$ and the other to $0$. In quantum computing, however, these two variables can take any pair of complex values $c_0$ and $c_1$ that fulfil $\mid c_0\mid^2 + \mid c_1\mid^2 = 1$. If both $c_0$ and $c_1$ are different from zero, the qubit is said to be in superposition.

### Representing the qubit

So, how can we represent the qubit? Notice that, to characterize a classical bit, we only need a single value (for example $c_0$), which can either be $0$ or $1$. This is because, given the restrictions that we explained above, if we know that $c_0$ is $0$, then the only possible value of $c_1$ is $1$. Likewise, if we know that $c_0$ is $1$, then the only possible value of $c_1$ is $0$.

This, however, is not the case for a qubit. Even if we know the value of $c_0$, there are infinite values of $c_1$ that satisfy the requirement $\mid c_0\mid^2 + \mid c_1\mid^2 = 1$. It seems like we will need to know two parameters, both $c_0$ and $c_1$, in order to characterise the state of the qubit. What is more, each of those two is composed of an amplitude _and_ a phase, so we need four parameters. Representing something in 4D is not pretty. 

Luckily, in quantum computing, and in quantum mechanics in general, there is one important thing that will reduce the four parameters to three, and it is the fact that global phases do not matter. There is no possible way to measure the global phase of anything, and in fact it has no physical significance. So, instead of keeping track of the absolute phases of $c_0$ and $c_1$, we can simply assume $c_0$ to be real and track only the relative phase $\phi$ between $c_0$ and $c_1$, assigning it to $c_1$. Further on, we will see that we can reduce the three parameters that we need in order to characterize a bit down to only two parameters, through the property $\mid c_0\mid^2 + \mid c_1\mid^2 = 1$.

But, let's not get ahead of ourselves; back to representing. Imagine a 2D system of cartesian coordinates, with axes named $\chi$ and $\upsilon$ (see image below), and forget for a minute the relative phase difference. Take now $\mid1\rangle$ as the unit vector in the $\chi$-axis and $\mid0\rangle$ as the unit vector of the $\upsilon$-axis. The components in this system of coordinates are the magnitudes of $c_0$ and $c_1$. It is clear that, since $\mid c_0\mid^2 + \mid c_1\mid^2 = 1$, the possible states of the qubit will be held inside the circumference of radius $1$ centered at the origin.

[![2D Representation of a Qubit][1]][1]

*Figure 1: 2D representation of a qubit state, showing the relationship between $\mid0\rangle$, $\mid1\rangle$, and the coefficients $c_0$ and $c_1$.*

How do we now introduce the phase difference into this representation? Well, there is one particular thing about phase, which is that it is contained inside a finite interval of values. Specifically, $\phi \in[0, 2\pi]$. This means that it is quite convenient to represent the third "dimension" of the qubit representation as an angle of rotation about some axis. The best way to do this in an intuitive way is to "open up" the $\chi$ and $\upsilon$ axes that we already constructed so that they make an angle of $180º$ between them, instead of $90º$, so that they merge to form a new axis that we name $z$-axis. 

[![Bloch Sphere][2]][2]

*Figure 2: Opening up the $\chi$ and the $\upsilon$ axes to form the new $z$-axis (left) and completing the Bloch Sphere representation of the qubit (right).*

In this way, the unit vectors that were previously perpendicular ($\mid0\rangle$ and $\mid1\rangle$) are now parallel and pointing in opposite directions. Then, $\phi$ can be represented as an angle of rotation about the new $z$-axis. The 2D circumference that contained the valid qubit states is now expanded into a 3D sphere of radius $1$. Any qubit state can be now characterised by its position on the Bloch Sphere, which we define with the variables $\phi$ and $\theta$. Here, $\theta$ represents the polar angle from the positive $z$-axis, and $\phi$ represents the azimuthal angle in the $x$-$y$ plane from the $x$-axis. We now only need two parameters to define a qubit!

It is important to note that, in this representation, $\theta$ is actually twice the real angle of the original 2D representation that we presented. Therefore, the coefficients $c_0$ and $c_1$ need to be computed taking $\theta/2$ instead of $\theta$. Given the angles $\theta$ and $\phi$ on the Bloch sphere, we can obtain the coefficients $c_0$ and $c_1$ using the following formulas:

$$c_0 = \cos(\theta/2)$$
$$c_1 = e^{i\phi} \sin(\theta/2)$$

### Summary

In summary, the Bloch sphere is a powerful visualization tool for representing the state of a qubit. Here are the key points to remember:

1. A qubit is a quantum system with two possible states, analogous to a classical bit.
2. Unlike classical bits, qubits can exist in superposition, represented by complex coefficients $c_0$ and $c_1$.
3. The Bloch sphere is a 3D representation of a qubit's state, where:
   - The north pole represents $\mid0\rangle$.
   - The south pole represents $\mid1\rangle$.
   - Any point on the surface represents a valid qubit state.
4. The state of a qubit on the Bloch sphere is defined by two angles:
   - $\theta$ (theta): the polar angle from the positive $z$-axis ($0 \leq \theta \leq \pi$). This angle determines the probability amplitudes of measuring the qubit in the $\mid0\rangle$ or $\mid1\rangle$ state. When $\theta = 0$, the qubit is in the $\mid0\rangle$ state, and when $\theta = \pi$, it's in the $\mid1\rangle$ state. For values in between, the qubit is in a superposition of $\mid0\rangle$ and $\mid1\rangle$, with the exact probabilities given by $\cos^2(\theta/2)$ for $\mid0\rangle$ and $\sin^2(\theta/2)$ for $\mid1\rangle$.
   - $\phi$ (phi): the azimuthal angle in the $x$-$y$ plane ($0 \leq \phi < 2\pi$). This angle represents the phase difference between the $\mid0\rangle$ and $\mid1\rangle$ components of the qubit state. Physically, it corresponds to the rotation of the qubit state around the z-axis of the Bloch sphere. Different values of $\phi$ lead to different quantum interference effects, which are crucial in many quantum algorithms and protocols.
5. The relationship between the Bloch sphere coordinates and the qubit coefficients is:

   $$c_0 = \cos(\theta/2)$$
   $$c_1 = e^{i\phi} \sin(\theta/2)$$

6. This representation reduces the four parameters needed to describe a qubit (real and imaginary parts of $c_0$ and $c_1$) to just two ($\theta$ and $\phi$), making it easier to visualize and understand qubit states.

Understanding the Bloch sphere representation is crucial for grasping the concepts of qubit manipulation and quantum gates in quantum computing.

  [1]: https://github.com/bfrangi/bfrangi.github.io/blob/master/assets/images/qubit-1.png?raw=true
  [2]: https://github.com/bfrangi/bfrangi.github.io/blob/master/assets/images/qubit-2.png?raw=true
