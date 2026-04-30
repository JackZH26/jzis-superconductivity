arXiv:0704.3444v1[cond-mat.soft]26 Apr 2007

A Symmetric Free Energy Based Multi-Component Lattice Boltzmann Method

Qun Li and A.J. Wagner

Department of Physics, North Dakota State University, Fargo, ND 58105

We present a lattice Boltzmann algorithm based on an underlying free energy that allows the simulation of the dynamics of a multicomponent system with an arbitrary number of components. The thermodynamic properties, such as the chemical potential of each component and the pressure of the overall system, are incorporated in the model. We derived a symmetrical convection diﬀusion equation for each component as well as the Navier Stokes equation and continuity equation for the overall system. The algorithm was veriﬁed through simulations of binary and ternary systems. The equilibrium concentrations of components of binary and ternary systems simulated with our algorithm agree well with theoretical expectations.

I. INTRODUCTION

Multicomponent systems are of great theoretical and practical importance. An example of an important ternary system, that inspired the current paper, is the formation of polymer membranes through immersion precipitation [1]. In this process a polymer-solvent mixture is brought in contact with a non-solvent. As the non-solvent diﬀuses into the mixture, the mixture phaseseparates, leaving behind a complex polymer morphology which depends strongly on the processing conditions. The dependence of the morphology on the parameters of the system is as yet poorly understood. Preliminary lattice Boltzmann simulations of this system exist [1]. However, this work did not recover the correct drift diﬀusion equation. A general fully consistent lattice Boltzmann algorithm with an underlying free energy to simulate multicomponent systems is still lacking. This paper strives to bring us a step nearer to achieving this goal.

There are several previous lattice Boltzmann methods for the simulation of multi-component systems. There are three main roots for these approaches. There are those derived from the Rothmann-Keller approach [2, 3] that attempt to maximally phase-separate the diﬀerent components. A second approach by Shan and Chen is based on mimicking the microscopic interactions [4, 5, 6] and a third approach after Swift, Orlandini and Yeomans [7, 8] is based on an underlying free energy. All of these have diﬀerent challenges. Since we are interested in the thermodynamics of phase-separation we ﬁnd it convenient to work with a method based on a free energy. This allows us to easily identify the chemical potentials of the components. This is convenient since the gradients of the chemical potentials drive the phase separation as well as the subsequent phase-ordering.

The challenge for the LB simulation of a multicomponent system lies in the fact that momentum conservation is only valid for the overall system but not for each component separately, and diﬀusion occurs in the components. For a binary system of components A and B with densities ρA and ρB, the simulation usually traces the evolution of the total density ρA+ρB and the density diﬀerence ρA−ρB [8]. Although this scheme is successful in the simulation of a binary system [8, 9], its generaliza-

tion for the LB simulations of systems with an arbitrary number of components is asymmetric. For instance, to simulate a ternary system of components A, B, and C with densities ρA, ρB and ρC, the total density of the system, ρA + ρB + ρC, should be traced, and the other two densities to be traced may be chosen as, e.g., ρB and ρA − ρC [10]. This approach is likely to be asymmetric because the three components are treated diﬀerently as is the case of Lamura’s model [10]. If an LB method is not symmetric, it will lose generality an will only be adequate for special applications. In this paper, we established a multicomponent lattice Boltzmann method based on an underlying free energy that is manifestly symmetric.

II. MACROSCOPIC EQUATIONS FOR MULTICOMPONENT SYSTEM

The equation of motion for a multicomponent system are given by the continuity and Navier-Stokes equations for the overall system and a drift diﬀusion equation for each component separately. The continuity equation is given by

∂tρ + ∇ · J = 0, (1)

where ρ is the mass density of the ﬂuid, J is the mass ﬂux which is given by J ≡ ρu, and u is the macroscopic velocity of the ﬂuid. The Navier-Stokes equation describes the conservation of momentum:

∂t(ρuα) + ∂β(ρuαuβ) = −∂βPαβ + ∂βσαβ + ρFα, (2)

where Pαβ and σαβ are the pressure and viscous stress tensors respectively, Fα is the component α of an external force on a unit mass in a unit volume, and the Einstein summation convention is used. For Newtonian ﬂuids, the viscous stress tensor is given by

σαβ = η ∂βuα + ∂αuβ −

d 2

δαβ∇ · u +µBδαβ∇·u, (3)

![image 1](04_Gedik_Ultrafast-Electron-Crystallography-Cuprate_Science2007_images/imageFile1.png)

where η is the shear viscosity, and µB is bulk viscosity, and d is the spacial dimension of the system.

Free energy, chemical potential, and pressure are key thermodynamic concepts to understand the phase behavior of a system. The chemical potential of each component can be obtained by a functional derivative as

δF δnσ

µσ =

, (4)

![image 2](04_Gedik_Ultrafast-Electron-Crystallography-Cuprate_Science2007_images/imageFile2.png)

where µσ is the chemical potential of component σ; nσ is the number density of component σ; and F is the total free energy of the system.

The pressure in a bulk phase in equilibrium is given by p =

nσµσ − ψ. (5)

σ

The pressure tensor is determined by two constraints: Pαβ = pδαβ in the bulk and ∆Pαβ = σ nσ∇µσ everywhere.

In multicomponent systems, there are two mechanisms for mass transport: convection and diﬀusion. Convection is the ﬂow of the overall ﬂuid, while diﬀusion occurs where the average velocities of components are diﬀerent. The velocity of the overall ﬂuid is a macroscopic quantity because it is conserved, but the average velocities of the components are not. The macroscopic velocity of the ﬂuid u can be expressed in terms of the density ρσ and velocity uσ of each component in the form of

With the notation

ρσuσ σ ρσ

u ≡ σ

. (6)

![image 3](04_Gedik_Ultrafast-Electron-Crystallography-Cuprate_Science2007_images/imageFile3.png)

∆uσ ≡ uσ − u, (7)

the ﬂux of each component can be divided into a convection part Jσc and a diﬀusion part Jσd:

Jσ ≡ ρσuσ = ρσ(u + ∆uσ) = Jσc + Jσd. (8)

Because mass conservation still holds for each component, the continuity equation for each component is valid:

∂tρσ + ∇ · Jσ = 0. (9)

Substituting Eq. (8) into Eq. (9), the convection diﬀusion equation for a component can be obtained.

∂tρσ + ∇ · Jσc = −∇ · Jσd. (10) From Eqs. (6) and (7), we see that

σ

Jσd = 0, (11)

which ensures the recovery of the continuity equation for the overall system. The diﬀusion process between two components is related to the diﬀerence of the chemical potential of the two components, which is also called the exchange chemical potential [11]. Recognizing that the gradient of the exchange chemical potential determines

the diﬀusion processes, we obtain a ﬁrst order approximation for the diﬀusion ﬂux of one component into all other components as

Jσd = −

σ′

′

′

Mσσ

∇(µσ − µσ

), (12)

′

where σ and σ′ enumerate the components; µσ and µσ

are the chemical potentials of components σ and σ′; and Mσσ

′

is a symmetric positive deﬁnite mobility tensor.

A simple model for the diﬀusion process assumes that a diﬀusion ﬂux between two components is proportional to the overall density and the concentration of each component. Then mobility tensor can be expressed as

′

Mσσ

′

′ ρσρσ

= kσσ

, (13)

![image 4](04_Gedik_Ultrafast-Electron-Crystallography-Cuprate_Science2007_images/imageFile4.png)

ρ

′

where kσσ

is the constant diﬀusion coeﬃcient between components σ and σ′. It depends on components but is independent of the total densities and concentration of each component. Substituting Eq. (13) into Eq. (12), we have

Jσd = −

σ′

′

′ ρσρσ

′

∇(µσ − µσ

kσσ

). (14)

![image 5](04_Gedik_Ultrafast-Electron-Crystallography-Cuprate_Science2007_images/imageFile5.png)

ρ

Substituting Eq. (14) into Eq. (10), the general form of a convection diﬀusion equation is obtained as

∂tρσ + ∇(ρσu) = ∇

σ′

′

′ ρσρσ

′

∇(µσ − µσ

kσσ

). (15)

![image 6](04_Gedik_Ultrafast-Electron-Crystallography-Cuprate_Science2007_images/imageFile6.png)

ρ

III. LATTICE BOLTZMANN FOR MULTICOMPONENT SYSTEM

To simulate a multicomponent ﬂuid using LB we set up a LB equation for each component. The LBE for a component σ of a multicomponent system is given by

fiσ(r + vi∆t,t + ∆t) − fiσ(r,t)

1 τ

fiσe(r,t) − fiσ(r,t) + Fiσ , (16)

= ∆t

![image 7](04_Gedik_Ultrafast-Electron-Crystallography-Cuprate_Science2007_images/imageFile7.png)

where fiσ(r,t) is the particle distribution function with velocity vi for component σ, fσe(r,t) is its equilibrium distribution and Fiσ is the forcing term of component σ due to the mean potential ﬁeld generated by the interaction of the component σ with the other components. The main task in setting up this lattice Boltzmann method is to determine the correct form of the forcing term Fiσ which will recover the convection diﬀusion equation (15).

The density of each component and the total density are given by

ρσ =

ρ =

i

σ

fiσ, (17)

ρσ. (18)

The average velocity of one component σ and the overall ﬂuid can be deﬁned as

ρσuσα ≡

ρuα ≡

i

σ

fσviα, (19)

ρσuσα, (20)

where uσα is the average velocity of the component σ, and uα is the average velocity of the overall ﬂuid.

The moments of equilibrium distributions for one component are chosen to be

i

fiσe = ρσ,

i

fiσeviα = ρσuα,

i

ρσ 3

fσeviαviβ =

δαβ + ρσuαuβ,

![image 8](04_Gedik_Ultrafast-Electron-Crystallography-Cuprate_Science2007_images/imageFile8.png)

i

ρσ 3

fσeviαviβviγ =

(uαδαβ + uβδαγ + uγδαβ)(21)

![image 9](04_Gedik_Ultrafast-Electron-Crystallography-Cuprate_Science2007_images/imageFile9.png)

The moments for the forcing terms of one component are

i

Fiσ = 0 (22)

i

Fiσviα = ρσaσα, (23)

i

Fiσviαviβ = ρσ(aσαuσβ + aσβuσα), (24)

i

1 3

Fiσviαviβviγ =

ρσ(aσαδβγ + aσβδαβ + aσγδαβ)(25).

![image 10](04_Gedik_Ultrafast-Electron-Crystallography-Cuprate_Science2007_images/imageFile10.png)

To utilize the analysis of the one component system we can establish a LB equation for the total density by deﬁning

fiσ = fi,

σ

Fiσ = Fi,

σ

ρσaσα = ρaα. (26)

σ

Similar to the counterparts of the one-component system, the moments for the overall equilibrium distribution function are given by

i

fie = ρ,

i

fieviα = ρuα,

i

1 3

fieviαviβ =

ρδαβ + ρuαuβ,

![image 11](04_Gedik_Ultrafast-Electron-Crystallography-Cuprate_Science2007_images/imageFile11.png)

i

1 3

fieviαviβviγ =

ρ(uαδβγ + uβδαγ + uγδαβ)

![image 12](04_Gedik_Ultrafast-Electron-Crystallography-Cuprate_Science2007_images/imageFile12.png)

+ρuαuβuγ + Qαβγ. (27)

The moments for the overall force terms are then given by

i

i

Fi = 0,

Fiviα = ρaα,

Using Eq. (24), we obtain

=

Fiviαviβ

i

(aσαuσβ + aβuσα)

σ

= ρ(aαuβ + aβuα) +

(aσα∆uσβ + aσβ∆uσα), (28)

σ

where the second term of Eq. (28) is of a higher order smallness than the ﬁrst terms, and therefore does not enter the hydrodynamic equations to second order. For the third moment we have

i

Fiviαviβviγ =

1 3

ρ(aαδβγ + aβδαβ + aγδαβ). (29)

![image 13](04_Gedik_Ultrafast-Electron-Crystallography-Cuprate_Science2007_images/imageFile13.png)

By summing Eq. (16) over σ, an eﬀective LB equation for the total density is

fi(r + vi∆t,t + ∆t) − fi(r,t)

1 τ

fie(r,t) − fi(r,t) + Fi , (30)

= ∆t

![image 14](04_Gedik_Ultrafast-Electron-Crystallography-Cuprate_Science2007_images/imageFile14.png)

This is identical to the LB equation for a system of one component. Therefore, the continuity equation and the Navier Stokes equation of the overall ﬂuid of a multicomponent system are recovered as

∂tρ + ∂α(ρUα) = 0 + O(ǫ3), (31)

where Uα ≡ uα + aα∆t/2 is the macroscopic velocity of the ﬂuid. The Navier Stokes equation for the overall ﬂuid is:

∂t(ρUβ) + ∂α(ρUαUβ)

1 3

= −∂α

ρδαβ

![image 15](04_Gedik_Ultrafast-Electron-Crystallography-Cuprate_Science2007_images/imageFile15.png)

w 3

ρ(∂αUβ + ∂βUα) + ρaβ −w∂γ∂αρuαuβuγ. (32)

+∂α

![image 16](04_Gedik_Ultrafast-Electron-Crystallography-Cuprate_Science2007_images/imageFile16.png)

To recover the convection diﬀusion equation of each component, we performed a Taylor expansion on the left of Eq. (16) to second order:

(∆t)2 2

∆t(∂t + viα∂α)fiσ +

(∂t + viα∂α)2fiσ + O(ǫ3)

![image 17](04_Gedik_Ultrafast-Electron-Crystallography-Cuprate_Science2007_images/imageFile17.png)

1 τ

(fiσe − fiσ) + Fiσ . (33)

= ∆t

![image 18](04_Gedik_Ultrafast-Electron-Crystallography-Cuprate_Science2007_images/imageFile18.png)

Because of the recursive nature of Eq. (33), fiσ can be expressed by fiσe and derivatives of fiσe as

fiσ = fiσe + τFiσ −τ(∂t + viα∂α)(fiσe + τFiσ) + O(ǫ2). (34)

Substituting Eq. (34) into the left side of Eq. (33) we obtain

(∂t + viα∂α)(fiσe + τFiσ) − w(∂t + viα∂α)2(fiσe + τFiσ) + O(ǫ3).

1 τ

(fiσe + τFiσ − fiσ). (35) Summing Eq. (35) over i gives,

=

![image 19](04_Gedik_Ultrafast-Electron-Crystallography-Cuprate_Science2007_images/imageFile19.png)

∂tρσ + ∂α(ρσuα) + τ∂α(ρσaσα) − w

(∂t + viα∂α)2(fiσe + τFiσ) = O(ǫ3) (36)

i

The ﬁrst moment of fie and fiσe are not identical, and the continuity equation cannot be obtained. Eq. (36) shows

that ∂tρσ + ∂α(ρσuα)+ τ∂α(ρσaσα) is of order O(ǫ2), and Fiσ is of order O(ǫ). Therefore ∂tρσ+∂α(ρσuα) is of order O(ǫ2), and we get

(∂t + viα∂α)2(fiσe + τFiσ)

w

i

ρσ 3

= w∂β ∂t(ρσuβ) + ∂α(

+ ρσuαuβ) + O(ǫ3).

![image 20](04_Gedik_Ultrafast-Electron-Crystallography-Cuprate_Science2007_images/imageFile20.png)

So Eq. (36) can be simpliﬁed to ∂tρσ + ∂α(ρσuα) + τ∂αρσaσα + O(ǫ3) −w∂β ∂t(ρσuβ) + ∂α(

ρσ 3

+ ρσuαuβ) = 0. (37)

![image 21](04_Gedik_Ultrafast-Electron-Crystallography-Cuprate_Science2007_images/imageFile21.png)

Eqs. (32) yields

1 ρ

∂tUβ = −Uα∂αUβ −

∂α

![image 22](04_Gedik_Ultrafast-Electron-Crystallography-Cuprate_Science2007_images/imageFile22.png)

ρ 3

δαβ + aβ + O(ǫ2). (38)

![image 23](04_Gedik_Ultrafast-Electron-Crystallography-Cuprate_Science2007_images/imageFile23.png)

From Eq. (36) it follows that

∂tρσ = −∂α(ρσUα) + O(ǫ2). (39) Inserting Eqs. (38) and (39) into Eq. (37) we get

ρσ ρ

ρ 3

∂t(ρσuβ) = − ∂α(ρσUαUβ) −

∂α

δαβ

![image 24](04_Gedik_Ultrafast-Electron-Crystallography-Cuprate_Science2007_images/imageFile24.png)

![image 25](04_Gedik_Ultrafast-Electron-Crystallography-Cuprate_Science2007_images/imageFile25.png)

+ ρσaβ + O(ǫ2). (40) Substituting Eq. (40) into Eq. (37) results in

ρσ 3 −w

∂tρσ + ∂α(ρσUα) = ∂α τρσaα − τρσaσα + w∂α

![image 26](04_Gedik_Ultrafast-Electron-Crystallography-Cuprate_Science2007_images/imageFile26.png)

ρσ ρ

ρ 3

, (41)

∂α

![image 27](04_Gedik_Ultrafast-Electron-Crystallography-Cuprate_Science2007_images/imageFile27.png)

![image 28](04_Gedik_Ultrafast-Electron-Crystallography-Cuprate_Science2007_images/imageFile28.png)

From this we deduce that the correct form of the forcing term is

w τ

ρσaσα ≡ −

w τ

= −

1 3

ρσ∂α(µσ −

![image 29](04_Gedik_Ultrafast-Electron-Crystallography-Cuprate_Science2007_images/imageFile29.png)

![image 30](04_Gedik_Ultrafast-Electron-Crystallography-Cuprate_Science2007_images/imageFile30.png)

![image 31](04_Gedik_Ultrafast-Electron-Crystallography-Cuprate_Science2007_images/imageFile31.png)

ρσ∂αµσ −

lnρσ)

1 3

∂αρσ , (42)

![image 32](04_Gedik_Ultrafast-Electron-Crystallography-Cuprate_Science2007_images/imageFile32.png)

where the coeﬃcient is wτ = 1 − ∆2τt. This coeﬃcient approaches 1 as ∆t approaches 0, as one would expect from

![image 33](04_Gedik_Ultrafast-Electron-Crystallography-Cuprate_Science2007_images/imageFile33.png)

![image 34](04_Gedik_Ultrafast-Electron-Crystallography-Cuprate_Science2007_images/imageFile34.png)

the continuum limit. This constitutes the main result of this paper. Plugging Eq. (42) into Eq. (41), we then obtain the convection diﬀusion equation

∂tρσ + ∂α(ρσUα) = ∂α w

σ′

′

ρσρσ

′

∂α(µσ − µσ

)(43).

![image 35](04_Gedik_Ultrafast-Electron-Crystallography-Cuprate_Science2007_images/imageFile35.png)

ρ

The diﬀusion ﬂux of component σ is

Jσd = −w

σ′

′

ρσρσ

′

∂α(µσ − µσ

). (44)

![image 36](04_Gedik_Ultrafast-Electron-Crystallography-Cuprate_Science2007_images/imageFile36.png)

ρ

′

So that the w in Eq. (44) is equivalent to kσσ

in Eq. (14).

IV. NUMERICAL VALIDATION

We examined the equilibrium behavior of phase separated binary and ternary systems. We used the FloryHuggins free which is a very popular model to study polymer solutions. It is given by

F = −

σ

θnσmσ +

σ

nσθ lnφσ

+

σ σ′

- 1

![image 37](04_Gedik_Ultrafast-Electron-Crystallography-Cuprate_Science2007_images/imageFile37.png)

- 2


′

′

χσσ

θmσnσφσ

dV, (45)

where mσ is the polymerization of the component σ, nσ is its number density, and φσ is its volume fraction. It is deﬁned as

mσnσ σ(mσnσ)

φσ =

=

![image 38](04_Gedik_Ultrafast-Electron-Crystallography-Cuprate_Science2007_images/imageFile38.png)

ρσ ρ

, (46)

![image 39](04_Gedik_Ultrafast-Electron-Crystallography-Cuprate_Science2007_images/imageFile39.png)

where ρσ is the mer density of component σ and ρ is the mer density of the system, which is a constant in the Flory-Huggins model. To validate our algorithm we compared the binodal lines obtained by our algorithm to the theoretical ones obtained by minimizing the free energy. We used the interfacial tension parameter κ = 0 in all our LB simulations of binary and ternary systems, because there is an intrinsic surface tension in the LB simulation due to higher order terms [12], which did not appear explicitly in the second order Taylor expansion presented in this paper. Since we are only evaluating the phasebehavior here we use a one dimensional model known as D1Q3. This model has the velocity set {vi} = {−1,0,1}.

- 0

- 0.5
- 1


φB

|φΒ (theor.), m = 1<br><br>φΒ, m = 1, 1/τ = 0.7 φΒ, m = 1, 1/τ = 0.9 φΒ (theor.), m = 10<br><br>φΒ, m = 10, 1/τ = 0.9<br><br>|
|---|


FIG. 1: (Color online) Comparison of the binodal lines for monomer and polymer systems show good agreement with theory. For mA = 1, mB = 1 we also show that the results are independent of the relaxation time. For the polymer system with mA = 10, mB = 1, the binodal points by LB with 1/τ = 0.9 the match is slightly less good for large volume fractions of φB.

This is an important test since all other frequently used higher dimensional model have this D1Q3 model as a projection.

We consider two binary systems: a monomer system with mA = 1 and mB = 1, and a polymer system with mA = 10 and mB = 1. For both systems, the total density was ρ = 100. Throughout this paper we choose the self interaction parameters to vanish: χσσ = 0. The critical volume fractions for the monomer system are φA = 0.5 and φB = 0.5 and for the polymer systems are φA = 0.24 and φB = 0.76. To induce phase separation a small sinusoidal perturbation ∆φ(x) was added in the initial conditions. The amplitude of the perturbation is 0.1 and its wavelength is the lattice size. The initial volume fraction of component A is given by φA(x) = φA0 + ∆φ(x). The initial volume fraction of component B is given by φB(x) = φB0 − ∆φ(x).

The monomer system was simulated with diﬀerent inverse relaxation times. In Figure 1 we show results for

- 1/τ = 0.7, and 0.9. We see that the equilibrium densities have only a very slight dependence on the relaxation time, although the range of stability depends noticeably on the relaxation time. The polymer system was simulated with only one inverse relaxation time of 1/τ = 0.9. Starting from the critical point and increasing the χAB value for each initial condition until the simulations were numerically unstable, we obtained a pair of binodal points for each initial condition. The system reached a stable state after about 5000 time steps. The measurement were taken after 50000 time steps to be sure that an equilibrium state had been reached.


0 1 2 3 4 5 6 χΑΒ

For the polymer system, Figure 2 shows the compar-

- 0.8
- 1


|φA<br><br>φA (theor.)<br><br>φB<br><br><br>φB (theor.)<br>|
|---|


0.6 φ

0.4

0.2

0

0 20 40 60 80 100 Lattice points

0

- -5
- -4
- -3
- -2
- -1


|µΑ<br><br>µA (theor.)<br><br>µΒ µΒ (theor.)<br><br>| |
|---|
<br><br>|
|---|


µ

30 40 50 60 70 Lattice points

FIG. 2: (Color online) The volume fraction and the chemical potentials of the two components for the polymer-monomer mixture. The parameters are mA = 10, mB = 1, χAB = 0.94, κ = 0, and 1/τ = 0.9.

ison of the total density, and the volume fractions and chemical potentials of each component to the corresponding theoretical values. The total density of a system in equilibrium by LB is essentially constant with a variation of ∆ρ/ρ < 10−5. The volume fractions of each component in the LB simulation agree well with the theoretical values. The chemical potential of each component by the LB simulation was very close to the theoretical value. The chemical potential µA, corresponding to the polymer component, varied slightly with a diﬀerence for the bulk values of about 2·10−2 and a variation in the interface of about 4 · 10−2. This is the underlying reason for the small deviation from the theoretically predicted concentration. The potential µB was nearly constant with a variation of less than 10−4 in the bulk and a variation of about 10−3 at the interface. For large values of χAB this discrepancy increases leading to the noticeable variation of the equilibrium densities of the polymer system as shown in Figure 1.

We also performed LB simulations with two ternary systems: a monomer system with mA = 1, mB = 1, and mC = 1 and a polymer system with mA = 10, mB = 1, and mC = 1. The χ parameters for both systems were χAB = 3, χAC = 0.5, and χBC = 0.2. The other χ parameters were zero. The inverse relaxation time constant for both simulations was 1/τ = 0.9. The critical point for

- 0.8
- 1


|m= 1<br><br>m=1 theor.<br><br>m=10 by LB<br><br>m=10 theor.<br><br>|
|---|


0.6 φB

0.4

0.2

0

0 0.2 0.4 0.6 0.8 1 φA

- FIG. 3: (Color online) The binodal points of two ternary systems obtained by LB simulation. The monomer system has mA = 1, mB = 1, and mC = 1; the polymer system has mA = 10, mB = 1, and mC = 1. The parameters for both systems are χAB =3, χAC = 0.5, χBC = 0.2 and 1/τ = 0.9.

0 20 40 60 80 100 Lattice points

0

0.2

0.4

0.6

0.8

φ

|φA<br><br>φB<br><br>φC<br><br><br>φA (theor.)<br><br>φB (theor.)<br><br>| |
|---|
<br><br>φC (theor.)<br>|
|---|


20 40 60 Lattice points

- -5
- -4
- -3
- -2
- -1


0

µ

|µA<br><br>µA (theor.)<br><br>µB<br><br>| |
|---|
<br><br>µB (theor.)<br><br>µC<br><br>µC (theor.)<br><br><br><br><br>|
|---|


- FIG. 4: (Color online) The volume fractions and the chemical potentials for three component polymer system. The parameters are mA = 10, mB = 1, mC = 1, χAB = 3, χAC = 0.5, χBC = 0.2, and 1/τ = 0.9. The initial homogeneous volume fractions were φA = 0.14, φB = 0.11, and φC = 0.75.


the monomer system was φA,cr = 0.32, φB,cr = 0.32, and φC,cr = 0.36. The critical point for the polymer system was φA,cr = 0.14, φB,cr = 0.11, and φC,cr = 0.75. The initial state of each simulation were set from the critical points towards the end point (φA = 0.5, φB = 0.5, φC = 0). Initially a small sinusoidal wave perturbation ∆φ of an amplitude of 0.1 and wavelength of the lattice size was superimposed on the initial volume fraction of the A component. This perturbation was subtracted from the B component and the C component was constant. I performed a LB simulation for each set of initial volume fractions and obtained the volume fractions of the two phases in the equilibrium state, resulting in two binodal points. The simulation reached a stable state after about 20,000 time steps. The measurements were taken after 200,000 time steps to make sure the equilibrium state was reached.

Figure 3 shows the comparison of the binodal points by LB simulation to the theoretical binodal lines of both systems. The binodal points obtained by the LB simulation agree fairly well with the theoretical binodal lines for the monomer and polymer systems. The simulation becomes unstable when φA is close to zero, i.e. when one component is nearly depleted. In this region the simulation results also deviate noticeably from the theoretical binodal lines. Immediately near the critical point, the evolution of the system becomes extremely slow so the slight deviation between the binodal points obtained through the LB simulation and the theoretical ones probably indicates that the LB simulation was not yet fully equilibrated.

For the polymer system Figure 4 shows a comparison of the volume fractions and chemical potentials of each component. The total density of the system is again nearly constant with variation of less than ∆ρ/ρ < 10−4 in the bulk. At the interface there is a small variation of ∆ρ/ρ < 10−2. The volume fractions of each phase in the simulation were very close to their theoretical values. The chemical potential of component A was slightly different in two phases with a variation of about 2 · 10−2, while the chemical potentials of components B and C were much closer in the two phases with a variation of less than 10−4.

V. OUTLOOK

We have presented a general lattice Boltzmann algorithm for systems with an arbitrary number of components which is based on an underlying free energy. In this algorithm the key thermodynamic quantities such as the chemical potentials of the components are immediately accessible. It is also manifestly symmetric for all components. We tested the equilibrium behavior of the new algorithm for two and three component systems in each case examining both the case of monomer and polymer mixtures with an underlying Flory-Huggins free energy. We obtained to expected phase-diagrams to good

accuracy and the chemical potentials were constant to good accuracy for the monomer systems. Polymer systems were more challenging to simulate but still obtained acceptable results for m = 10. Higher polymerizations, however, become increasingly diﬃcult to realize with the current algorithm.

There are three directions in which we hope to extend this algorithm in the future. The current algorithm does not allow for component dependent mobility. We are

working on developing an algorithm that can recover an arbitrary mobility tensor κσσ

′

. The chemical potential is only approximately constant. Recent progress for liquidgas systems [12] makes us hopeful that we will be able to ensure that the chemical potential is constant up to machine accuracy. And lastly we hope to extend to model so that it can simulate polymer systems with signiﬁcantly larger polymerization.

![image 40](04_Gedik_Ultrafast-Electron-Crystallography-Cuprate_Science2007_images/imageFile40.png)

![image 41](04_Gedik_Ultrafast-Electron-Crystallography-Cuprate_Science2007_images/imageFile41.png)

![image 42](04_Gedik_Ultrafast-Electron-Crystallography-Cuprate_Science2007_images/imageFile42.png)

![image 43](04_Gedik_Ultrafast-Electron-Crystallography-Cuprate_Science2007_images/imageFile43.png)

- [1] A. Akthakul, C. Scott, A. Mayes, and A.J. Wagner, J. Membrane Sci. 249, 213 (2005).
- [2] D.H. Rothman and J.M. Keller, J. Stat. Phys. 52, 1119

(1988).

- [3] T. Reis and T.N. Phillips J. Phys. A 40, 4033 (2007).
- [4] X. Shan and H. Chen, Phys. Rev. E 47, 1815 (1993).
- [5] X. Shan and H. Chen, Phys. Rev. E 49, 2941 (1994).
- [6] X. Shan and G. Doolen, Phys. Rev. E 54, 3614 (1996).
- [7] W. Osborn, E. Orlandini, M.R. Swift, J.M. Yeomans, and J.R. Banavar, Phys. Rev. Lett. 75, 4031 (1995).


- [8] M.R. Swift, E. Orlandini, W.R. Osborn, J.M. Yeomans, Phys. Rev. E 54, 5041(1996).
- [9] A.J. Wagner and M. Cates, Europhys. Lett. 56, 556

(2001).

- [10] A. Lamura, G. Gonnella, and J.M. Yeomans, Europhys. Lett. 45, 314 (1999).
- [11] R. Jones, Soft Condensed Matter (Oxford University Press, 2002).
- [12] A.J. Wagner, Phys. Rev. E 74, 056703.1 (2006).


