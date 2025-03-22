---
layout: post
math: true
title: Raman spectroscopy and machine learning
category: 
- machine learning
- physics
- incomplete
---

**This is incomplete**. I just update on the go.

It's been a while since there is anything happening on the frontal page. And, considering that I just have done a small essay on Raman spectroscopy, and the topic of optical physics, it's a good thing to visit this topic a bit further than before. 

# Introduction
This article, or rather, the small post (not so small, however) will introduce certain topics on optical physics and its interaction with materials, the interpretation of such events, scattering and Raman scattering, and spectroscopic application of the exact jargon we just threw around there, and certain data-specific, machine learning approach - *coincidentally* my essay as well. 

Hopefully it's will be nice and shiny.
# I. Optical physics
So, what is it about? The theory of optics, and whatever going on with **lights**, have various conjectures, theories and interpretation. At least to be familiar of one such, we might as well proceed with the simplest one - *ray optics*, and this, alongside *wave optics*, found the foundation of the discussion for modern optics. 

One particular aspect of why rays and wave optics are easier than others comes from the fact that they are developed, and treated succinctly without the knowledge of electromagnetism. Of course, Maxwell was born in the 19th century and not earlier, so that is understandable. So, here, *light is not considered to be an electromagnetic phenomenon*.
## I.1. Ray optics

While the nature of light is far more complex than one can simply make it out of such, the naive definition of light can be defined two-fold - a *dynamic container* of energy to specific configuration, and by the configuration, either wave-like behaviour, and particle-like observations. For ray optics, the most correct model of said treatment is caleld the *Corpuscular theory of light*, by Issac Newton and Pierre Gassendi (the first guy I know - everyone knows - the second... well not quite), where matter or light is made up of small particles called corpuscles (or 'little particles'). 


> Notice that by the above passage, we directly infer that, if you do not know by now, and to clarify, that light can be both waves, or streams of particles. As a wave, we can speed of the **propagation speed** of the wave $\omega$ as $v(\omega)=\dot{x}=f\lambda$ for $\lambda$ the wavelength. However, for ray optics, we consider only somewhat the particle case more.

The fundamental assumption in the theory of ray optics is that light travels in the form of rays. A **ray** means, or represents a beam of light, however, this ray is often not monochromatic - but polychromatic - or with the shade of multiple colors. This model of light is fairly limited, since there exist only two ways of interaction: *reflection* or *refraction*. We would want to see what is more important in such theory. 

For light to travels, as for things to live, it propagates, or moves in a media. Hence, most of our results lives in what is called **optical media**. *Space*, without anything, is one kind of exception in such space. Assuming the media are lossless[^1], we can characterize them completely by a quantity called **index of refraction**, denoted by $n$. For the empty space, $n=1$, and usually, $n\geq 1$, or by how light is bent (refracted, or strays from its original vector directive). 

The fundamental principle of ray optics, called **Fermat's principle**, concerns of the *optical path length*. Consider a path $\mathbf{r}(s)$ between points $A$ and $B$ in an optical medium; this path is paramterized by $s$, so that $A=\mathbf{r}(0), B=\mathbf{r}(d)$, where $s,d\to L$ for dimension. Then, the optical path length is the length is this path, weighted by the local refractive index. That is 

$$
\ell [\mathbf{r}]:= \int_{0}^{d} n(\mathbf{r}) \: ds
$$
This quantity is proportional to the time light takes to traverse the path, $\Delta t= \ell /c_{0}$. Fermat's principle states that the optical rays traverse paths that satisfy $\delta \ell = 0$, or the path length is the same throughout the path. This principle is also often called the *principle of least time*. For ray optics, this principle settles the analysis and path calculations. 

### Paraxial rays.
For ray optics, we need a formalism for keeping track of optical rays. Represent a ray by a vector, which keep track of the position and direction of the ray with respect to the **optical axis**, the reference axis for optical propagation. The displacement $y$ from the optical axis, and the direction $\theta$ are sufficient to *completely* specify the ray at a particular longitudinal position $z$. 

![The components of light ray](/images/optics_ass_1.png){: .align-center width=400px}

An observation can conclude that $\theta = y'$, which then makes the coordinate to be 

$$
\begin{bmatrix}
    y \\ \theta
\end{bmatrix} = \begin{bmatrix}
    y \\ y'
\end{bmatrix}
$$

For any optical system of rays, we want to calculate the change in the ray vectors. In this sense, we get the model of optical system as a *transformation* of the ray vectors during its propagation. 

$$
\begin{bmatrix}
    y \\ \theta
\end{bmatrix} =\mathbf{f} \begin{bmatrix}
    y \\ y'
\end{bmatrix}
$$

for $\mathbf{f}$ modelling the optical system. Dealing with multivariate expressions, we obtain the approximation: 

$$
\begin{bmatrix} 
y_2 \\ y_2'
\end{bmatrix} = \left.
\begin{bmatrix} 
\frac{\partial f_1}{\partial y_1} & \frac{\partial f_1}{\partial y_1'} \\ 
\frac{\partial f_2}{\partial y_1} & \frac{\partial f_2}{\partial y_1'}
\end{bmatrix}\right|_{y_1 = y_1' = 0}
\begin{bmatrix} 
y_1 \\ y_1'
\end{bmatrix} +\text{higher-order terms in } y_1, y_1'
$$

by Taylor-expanding the function. This is the **paraxial approximation**. The matrix of derivatives is the **transfer matrix** that represents the optical system in the paraxial approximation. Hence, we obtained an effective formalism for treating change of optical system. 

## I.2. Wave optics

Another theory of light, much different than what is perceived as rays, or particle stream by Newton's corpuscular theory, is Crhistiaan Huygen's wave theory (1960, Traité de la Lumière). For such theory, it follows: 
1. Light travels in a hypothetical medium ether (high elasticity with very low density) as waves. 
2. He proposed that light waves are of longitudinal nature. Later on, it was found that they are transverse. 

# II. Raman scattering

## Preliminary (or recap)
### II.1. Basic definition
The expression *material system* will be used for the **matter** involved in the scattering act. This will always be taken to be an assembly of free rotating, non-interacting molecules. 
2. *Radiation* refers to electromagnetic radiation, characterized among other things, by frequency $f$ and related quantities. The frequency in interest is the *angular frequency* $\omega\:(\mathrm{rad\:s}^{-1})$. 
3. In the material system, the energy of a molecule in its initial state $i$, before the interaction, is defined by $E_{i}$, in its final state $f$, is defined by $E_{f}$. The ground is denoted by $E_{g}$. **Excited electronic state** is denoted by $$E_{e}\to E_{e_{1}},\dots,E_{e_{n}},\dots$$
4. **Transition energy** between states are $E_{fi}=E_{f}-E_{i}$, and can be defined more by the associated $\omega$: $$E_{fi}=\hbar \omega_{fi},\omega_{fi}=\omega_{f}-\omega_{i}$$
5. The *incident radiation* will be taken to consists of one or more **monochromatic EM waves** (of singular colour) of frequency $\omega_{1},\omega_{2},\dots$ with photon energies $\hbar \omega_{1},\hbar \omega_{2},\dots$ If there is only **one** monochromatic component, the interaction is called *one-colour process*. Conversely, for $M$ components, it is called $\mathbf{M}$-colour process. 
6. All light-scattering processes are characterized by the fact that, unlike direct absorption, the *energy* of an *incident photon* is not **required** to be equal to the energy corresponding to the difference between two discrete energy levels of the material system. 
### II.2. Optical processes
Optical properties and processes observed in optical system is comprised of several definitions and terms describing such. 

The simplest group of optical phenomena consists of **reflection**, **propagation**, and **transmission**. These phenomena can occur while light propagates through an optical medium. 
In the propagation phase (of the interaction between material and the incident light that was not reflected), there are several phenomena that can happens: 
1. Refraction: Reduction of velocity when exiting the material (entering free space), which causes the bending of lights. 
	1. Question: Why this happens? Excluding the Snail's law, or Huygens' principle, what is the "physical" explanation? 
2. Absorption: This occurs if the frequency $f$ of the light is resonant with the *transition frequencies* of the atoms in the medium (this occurs during atomic electron transition process, governed by $E=hf$), which attenuates the incident light gradually. Selective absorption is the result for coloration in many materials. 
3. Luminescence: Is the phenomena of spontaneous emission of light, from the *excited atoms of the material*. This is accompanied, usually by absorption, such that to pull the atom state into excited state. Certain properties are
	1. Light emitted during de-excitation process is non-aligned to the incident light propagating through the material. 
	2. Frequency is different, and based of excited electron and material's type. 
	3. There's a characteristic amount of time for the de-excitation process to occurs. 
	4. Not always accompanies absorption as a reemission process, since excited energy can dissipate before the characteristic time. 
4. Scattering: Redirection and changes of frequency of incident lights propagating through the medium. The scattering effect is **elastic** if frequency is constant, but **inelastic** if it varies. 
Other than the abovementioned phenomena, there's nonlinear optical phenomenon, such as frequency double. All of which happens within high intensity light. 
## The Raman effect
When **monochromatic radiation** of frequency $\omega_{1}$ is incident on system of material, most of it is transmitted without change, but some scattering occurs. 



![Types of effects](/images/rtas.png){: .align-center width=400px}

If the frequency content of the scattered radiation is analysed, aside from $\omega_{1}$, there is also various *new frequencies* of type $\omega_{1}\pm \omega_{M}$. The frequency $\omega_{M}$ in a **molecular** system are found to lie principally in the ranges associated with transitions between *rotational, vibrational* and *electronic* levels. Those levels are referring to **energy level** of excited state aside from the ground state $E_{g}$. For rotational for example, the diatomic molecule has the rotational energy level at $$E(J)=B(J+1)$$ where $J$ is the quantum number of the total rotational angular momentum, $B$ is the rotational constant, and $$B=\frac{h}{2\pi^{2}cI}$$ where $I=\mu r^{2}$ being the moment of inertia of the molecule. As such, there are a lot of excited state in those ranges.

Scattering *without change* of frequency is called **Rayleigh** scattering, and that with change of frequency is called **Raman scattering** after C. V. Raman. Raman bands at frequencies less than the incident frequency are referred to as **Stokes-band scattering**, while the opposite is called **anti-Stokes scattering**. For Mie scattering, then it is a version of Rayleigh (technically speaking) but **much stronger**. 

Statistically, during the event of light incidents that leads to scattering effect, **most** light passing through undergoes Rayleigh scattering. This is an *elastic effect*, which means that the light does not gain or lose energy during the scattering. Therefore, it stays at the same wavelength. 

Raman scattering is then *different* in that it is inelastic. The light photons *lose* or *gain* energy during the scattering process, and therefore increase or decrease in wavelength respectively.

For most experiments and practical purposes, we often take, for such reason, Rayleigh scattering as the basis for selecting the region of scattering frame that we want to focus on. Usually, anti-Raman is not a good indicator and readable spectrum, since it *blends* in with large noises and thereof, hence we would like to use the left-hand side - Stokes line more than enough. This does not mean that anti-Stokes holds no values or information - from a statistical standpoint however - capturing anti-Stokes is much more difficult.

> **The origin for the Stokes name.**
> According to Stokes' law, the frequency of fluorescent light is always smaller or at most **equal** of that exciting light. Stokes lines are thus those that correspond to Stoke's law, and anti-Stokes line are those that contradict it. This is adopted for the Raman effect, in spite of its difference from the original intended term of usage. 

## Spectroscopy
Spectroscopy utilizes electromagnetic radiation, when interaction with atoms and molecules. Their 'after effect' varies, for example, being induced absorption, spontaneous emission, induced emission. Some of the more direct descriptions includes luminescence and fluorescence, scattering, and reflections. Of all, the typical interest is based on the event of **scattering**.

Even with some of its drawback, characteristic scattering is less susceptible to the environment (*fluorescence spectroscopy*), spectrum is easier to decodes (*IR spectroscopy*), somewhat easier to set up and maintain (*reflection-absorption spectroscopy*), and others.

Traditionally, Raman used light from the Sun focused through a telescope to achieve a high enough intensity in his scattered signal. 

Modern **spectrometers** use both improved sources and more sensitive detectors to obtain better results. Nowadays, lasers are normally employed due to their high intensity, single wavelength and coherent beam instead. 

### Comparison to other spectroscopic methods
In the commonly used infrared absorption spectroscopy, infrared light excites certain vibrational frequencies of molecules and is absorbed by them, not re-emitted. This gives an **absorption spectrum**, with bands at characteristic **wavenumbers**. Other absorption techniques use higher energy radiation (e.g. ultraviolet) and raise electrons to an excited state.

*Fluorescence* occurs when light (often UV) is incident on a molecule and promotes an electron to an excited state. The molecule is also vibrating. Firstly it relaxes from its vibrational state, dissipating this energy (normally as heat). Then, when it drops back down to the ground state, the photon released has less energy than the incident photon. The increased wavelength often means that the light is now in the visible region. This is how *fluorescent* lighting works, by ionisation of mercury to produce UV light, which is then absorbed by a fluorescent coating and re-radiated as visible light. Fluorescence can also be used for spectroscopy.

Under such consideration, Raman is listed of several advantages: 
- Can be used with solids, liquids or gases.
- No sample preparation needed. For infrared spectroscopy solids must be ground into KBr pellets or with nujol to form a mull.
- Non-destructive
No vacuum needed unlike some techniques, which saves on expensive vacuum equipment.
- Short timescale. Raman spectra can be acquired quickly.
- Can work with aqueous solutions (infrared spectroscopy has trouble with aqueous solutions because the water interferes strongly with the wavelengths used)
- Glass vials can be used (unlike in infrared spectroscopy, where the glass causes interference)
- Can use down fibre optic cables for remote sampling.

Conversely, their drawbacks are not lacking:
- Cannot be used for metals or alloys.
- The Raman effect is very weak, which leads to low sensitivity, making it difficult to measure low concentrations of a substance. This can be countered by using one of the alternative techniques (e.g. Resonance Raman) which increases the effect.
- Can be swamped by fluorescence from some materials.

The second point might be one of the biggest drawback for Raman spectroscopic system - it is simply **too expensive** to guarantee specific error and retrieval acceptance bound when handling experiments related to spectroscopic extraction. Even the best, most DIY-like spectroscoper costs almost $4000 [^2]

[^1]: By Ohm's law, $\mathbf{J}=\sigma \mathbf{E}$, where $\sigma$ is the conductivity. A media that is lossless has the conductivity $\sigma$ to be negligible, its permeability $\mu$ and permittivity $\epsilon$ finite. When an electromagnetic wave propagates through a lossless medium, the amplitude of its electric field or magnetic field remains constant throughout the propagation. Thus, we can call it a 'non-interrupting' medium for waves. 

[^2]: See [this article on ACS.](https://pubs.acs.org/doi/10.1021/acs.jchemed.0c01028)