---
layout: post
title:  "Black Body Radiation and Thermodynamic Equilibrium"
date:   2025-01-29 07:28:59 +0100
categories: physics
---

### Introduction

Radiation heat transfer plays a fundamental role in thermodynamics and engineering, with the concept of a **black body** serving as a cornerstone in understanding how objects absorb and emit thermal radiation. A black body is an idealized object that absorbs all incident radiation, making it a perfect reference for studying real-world materials and their radiative properties. Its behavior is crucial for various scientific and technological applications, from astrophysics to thermal engineering.

In this post, we explore the defining characteristics of a black body, its absorptivity and emissivity, and the principles governing bodies in **thermodynamic equilibrium**, including *Kirchhoff’s Law*. Understanding these concepts allows us to analyze how real objects interact with thermal radiation and how energy exchange is regulated in different systems.

### Definition of the Black Body

A black body is an object that allows all incident radiation to enter into its interior and absorbs it completely (no radiation is reflected at the external surface or exits the body after entering into it), regardless of wavelength and angle of incidence. As such, a black body is a perfect absorber for all incident radiation [1].

Furthermore, a black body also diffusely (equally in all angles) emits the maximum possible radiant energy at each wavelength for any body at a particular temperature \\(T\\) [1]. This maximum possible radiant energy at each wavelength and temperature is given by *Planck's Law* [2].

### Absorptivity and Emissivity

#### Absorptivity

The *absorptivity* \\(\alpha(\lambda)\\) of a general body is a unitless coefficient defined as the ratio of the power the body absorbs at a specific wavelength to the total incident power. 

\\[
  \alpha(\lambda) = \frac{\text{power absorbed by the body at } \lambda}{\text{total incident power at } \lambda}
\\]

Since the black body is a perfect absorber, it follows that \\(\alpha_\text{blackbody} = 1\\), \\(\forall \lambda\\). In this way, the power absorbed by a black body can be used as a reference to obtain the absorptivity of other bodies.

\\[
  \alpha(\lambda) = \frac{\text{power absorbed by the body at } \lambda}{\text{absorbed power at } \lambda \text{ if the body was a black body}}
\\]

#### Emissivity

The *emissivity* \\(\varepsilon(\lambda)\\) of a general body is a unitless coefficient defined as the ratio of the power emitted by the body at a specific wavelength to the maximum possible power emitted by any body at the same temperature as the general body.

\\[
  \varepsilon(\lambda) = \frac{\text{power emitted by the body at } \lambda}{\text{maximum power emitted by any body at the same temperature at } \lambda}
\\]

Since the black body is a perfect emitter, it follows that \\(\varepsilon_\text{blackbody} = 1\\), \\(\forall \lambda\\), since it emits the maximum radiant energy that any body can emit for a particular temperature. In this way, the power emitted by a black body can be used as a reference to obtain the emissivity of other bodies.

\\[
  \varepsilon(\lambda) = \frac{\text{power emitted by the body at } \lambda}{\text{power emitted at }\lambda\text{ by a black body at the same temperature}} 
\\]

### Thermodynamic Equilibrium

#### Bodies in Thermodynamic Equilibrium and Kirchhoff's Law

A body is in thermodynamic equilibrium with its surroundings when it emits the same amount of energy that it absorbs. Thus, there is no net energy exchange between the body and its surroundings, and the body's temperature remains constant.

One consequence of thermodynamic equilibrium is *Kirchhoff's Law of Thermal Radiation* [3] which, simply put, states that, for an arbitrary body emitting and absorbing thermal radiation in thermodynamic equilibrium, its absorptivity function \\(\alpha (\lambda)\\) and its emissivity function \\(\varepsilon (\lambda)\\) are the equal. In other words, the absorptivity and emissivity of a body in thermal equilibrium are equal at each wavelength, \\(\alpha (\lambda) = \varepsilon (\lambda) \\). 

Note that the inverse is not necessarily true: a body such that \\(\alpha (\lambda) = \varepsilon (\lambda) \\), \\(\forall \lambda\\), is not necessarily in thermodynamic equilibrium. A clear example of this is the black body, which always satisfies \\(\alpha (\lambda) = \varepsilon (\lambda)\\) (equal to \\(1\\)) but is not necessarily in thermodynamic equilibrium with its surroundings.

#### Principle of Detailed Balance

Kirchhoff's Law of Thermal Radiation is even stronger than this: not only does it hold macroscopically, but also *in detail*.  This is the *Principle of Detailed Balance* [4], which states that, in thermodynamic equilibrium, the power radiated and absorbed by a body must be equal for every infinitesimal surface element, in every direction and polarization state, and across every wavelength interval. In other words, consider an infinitesimal surface element, select any direction and polarization state, and choose an infinitesimal wavelength interval. Under thermodynamic equilibrium, the power entering and leaving that element under those conditions must be equal, resulting in zero net power transfer.

This, of course, highlights just how idealized the concept of thermodynamic equilibrium is, as it requires objects to have perfectly matching emission and absorption spectra. For instance, a black body at temperature \\(T\\) can only be in thermodynamic equilibrium when surrounded by other black bodies at the same temperature. In contrast, a black body interacting with a real body could never achieve true thermodynamic equilibrium (even when at the same temperature), since real bodies typically deviate from ideal behavior (they may not follow Planck’s spectrum, may not emit diffusely, or may exhibit polarization characteristics that differ from those of a black body) and so detailed balance would never be achieved.

### Thermal Equilibrium without Detailed Balance

In general, a system is only considered to be in thermodynamic equilibrium if it satisfies the condition of detailed balance. However, some systems may be in some kind of equilibrium state, where the net macroscopic power exchanged between different elements of the system is zero, but the principle of detailed balance does not apply. In these cases (restricting our discussion to wavelength) \\(\alpha (\lambda) = \varepsilon (\lambda) \\) is verified but it does not mean that the power absorbed by the body at each wavelength is equal to the power emitted by the body at that same wavelength, but rather that the absorptivity and emissivity functions are equal at each wavelength. In the case of the absorptivity, we are comparing the power absorbed by the body to the total incident power, while in the case of the emissivity, we are comparing the power emitted by the body to the maximum possible power emitted by any body at the same temperature, which is given by *Plank's Law*:

\\[
  \text{power absorbed by the body at } \lambda = \alpha (\lambda) \times \text{total incident power at } \lambda
\\]
\\[
\text{power emitted by the body at } \lambda = \varepsilon (\lambda) \times 
\genfrac{}{}{0pt}{}{\text{power emitted at }\lambda \text{ by a black body}}{\text{at the same temperature}}
\\]

Clearly, these two quantities are not necessarily equal, even if \\(\alpha (\lambda) = \varepsilon (\lambda)\\). In fact, the power emitted by the body at a specific wavelength does not depend at all on the distribution of the absorbed power in wavelength, but only on the temperature of the body and its emissivity at that wavelength.

What does need to be equal, however, is the total power absorbed by the body and the total power emitted by the body, which is a consequence of the body being in thermodynamic equilibrium with its surroundings. This is obtained by integrating the power absorbed and emitted over all wavelengths:

\\[
  P_\text{absorbed} = \int_0^\infty \alpha (\lambda) \times \text{total incident power at } \lambda \, d\lambda
\\]

\\[
  P_\text{emitted} = \int_0^\infty \varepsilon (\lambda) \times \genfrac{}{}{0pt}{}{\text{power emitted at }\lambda \text{ by a black body}}{\text{at the same temperature}} \, d\lambda  
\\]

Equilibrium here implies \\( P_\text{absorbed} = P_\text{emitted} \\).

### Conclusion

In conclusion, this post has explored the fundamental concept of a *black body* as an idealized perfect absorber and emitter of thermal radiation. We defined *absorptivity* and *emissivity*, highlighting their wavelength dependence and their ideal value of unity for a black body. Furthermore, we delved into the crucial concept of *thermodynamic equilibrium*, introducing *Kirchhoff's Law*, which states that for a body in such equilibrium, its absorptivity and emissivity at a given wavelength are equal. The more stringent condition of the *Principle of Detailed Balance*, requiring equilibrium at every infinitesimal level, was also discussed, emphasizing the highly idealized nature of true thermodynamic equilibrium. Finally, we considered scenarios where macroscopic thermal equilibrium can exist without satisfying detailed balance, focusing on the equality of total absorbed and emitted power. This understanding of black body radiation and thermodynamic equilibrium is essential for various applications in physics and engineering, providing a foundation for analyzing real-world materials and their interactions with thermal radiation.


### Bibliography

[1] Siegel, R., & Howell, J. R. (2002). Thermal radiation heat transfer; Volume 1 (4th ed.). Taylor & Francis.

[2] Planck, M. (1901). On the law of distribution of energy in the normal spectrum. Annalen der Physik, 4(3), 553–563.

[3] Kirchhoff, G. (1860). On the relation between the radiating and absorbing powers of different bodies for light and heat. The London, Edinburgh, and Dublin Philosophical Magazine and Journal of Science, 20(130), 1–21. https://doi.org/10.1080/14786446008642901

[4] Reif, F. (2009). Fundamentals of Statistical and Thermal Physics. United States: Waveland Press.
