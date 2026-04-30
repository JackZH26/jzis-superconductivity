arXiv:cond-mat/0402506v2[cond-mat.dis-nn]4 Mar 2005

Random Matrices with Correlated Elements: A Model for Disorder with Interactions

Pragya Shuklaa,b

(a) Department of Physics, University of Illinois at Chicago, Chicago, Illinois-60607, (b) Department of Physics, Indian Institute of Technology, Kharagpur, India. (November 1, 2018)

# Abstract

The complicated interactions in presence of disorder lead to a correlated randomization of states. The Hamiltonian as a result behaves like a multiparametric random matrix with correlated elements. We show that the eigenvalue correlations of these matrices can be described by the single parametric Brownian ensembles. The analogy helps us to reveal many important features of the level-statistics in interacting systems e.g. a critical point behavior different from that of non-interacting systems, the possibility of extended states even in one dimension and a universal formulation of level correlations.

PACS numbers: 68.65.-k, 05.40.-a, 05.30.-d

## Typeset using REVTEX

I. INTRODUCTION

The theoretical formulation of physical properties of electronic systems is usually based on independent electron approximation. However, experiments on quantum dots as well as extended semi-conducting electron heterostructures show that Coulomb interaction between electrons is by no means small [1,2]. The inﬂuence of Coulomb interaction is particularly strong in presence of a disordered environment, with bulk and mesoscopic systems both revealing new features [4,7]. Examples include Coulomb Blockade phenomena, low energy anomalies in transport and thermodynamics coeﬃcients, non-Fermi liquid eﬀects in eﬀectively one dimensional structures, various manifestations of the Kondo eﬀects, the fractional quantum Hall eﬀects etc. A theory of physical properties including electron electron (e-e) interaction is therefore very much required.

The presence of interactions along with disorder makes a physical system so complex that its properties can be analyzed only by a statistical tool. In past, the statistics of single particle states of non-interacting systems with external disorder potential has been well-modeled by the Wigner-Dyson ensembles, also known as standard Random matrix ensembles (RMT) [5,3,7]. The ensembles have also been used successfully to describe the statistical properties of the high energy states of many body systems with no disorder e.g. nuclei, atoms etc [5,3,7]. The intuition suggests therefore a possibility of random matrix modeling of systems when disorder and interactions are both present. Recent studies in this direction have led to two types of random matrix models however both impose speciﬁc conditions on nature and degree of e-e interactions as well as disorder in the system [8,9]. In this paper, we consider a random matrix model suitable for generic conditions for both disorder and interactions and show that the spectral statistics can be described by a mathematical formulation analogous to that of non-interacting disordered systems. The parameter governing the localization → delocalization transition however turns out to be diﬀerent in the two cases.

The complexity of many body interactions or external disorder potential associates a degree of uncertainty in the exact determination of the Hamiltonian. As a result, some (or all) elements of the Hamiltonian matrix behave like random variables. The distribution properties of the matrix elements are governed by the nature of interactions and disorder; their distributions need not be same, may or may not be correlated and some of them can be non-random too. For example, a single particle Hamiltonian with a ”white noise” disorder potential (that is, no e-e interaction or impurity interaction) can be modeled by a random matrix with uncorrelated elements. However the presence of local interactions among impurities or electrons or both will result in a correlated randomization of matrix elements of the Hamiltonian. Unfortunately not much information for random matrices with correlated elements has been available so far. Our objective in this study is to suggest a way to ﬁll in this information gap. Here we show that the eigenvalue distributions of various ensembles, with correlated matrix elements and a multi-parametric probability density, appear as non-equilibrium stages of a Brownian type diﬀusion process. The diﬀusing eigenvalues evolve with respect to a single parameter which is a function of the correlation strengths

between various matrix elements. The parameter is therefore related to complexity of the system represented by the ensemble and can be termed as ”complexity” parameter. The solution of the diﬀusion equation for a given value of complexity parameter gives, therefore, the distribution of eigenvalues, and thereby their correlations, for corresponding system. As discussed later, the diﬀusion equation can be solved by using its analogy with the one governing the evolution of Brownian ensembles [10]. The analogy also helps in theoretical formulation of the level-density correlations of interacting disordered systems.

The paper is organized as follows. In section II, we derive the diﬀusion equation for the matrix elements of the Hermitian operators governing the dynamics in complex systems. For a clear exposition of our technique, we ﬁrst consider the cases with 2nd and 3rd order matrix elements correlations and generalize to nth order correlations later on. The diﬀusion equation for the matrix elements is then used to obtain the equation governing the evolution of the eigenvalues in section III. To maintain the ﬂow of the discussion, only relevant steps are given in the sections II, III; the details can be found in the appendices. As mentioned above, the evolution equation for the eigenvalues turns out to be a very well-known equation and calculation of the eigenvalue correlations from the equation has been discussed in detail many times. We therefore avoid the repetition but give a brief discussion to keep the article self-content. This is followed, in section IV, by a discussion of the application of our technique to two well-known systems. We conclude in section V by summarizing our main results.

II. SINGLE PARAMETRIC EVOLUTION OF MATRIX ELEMENTS

Let us consider a complex system represented by a N × N Hermitian matrix H with Hkl = βs=1(i)s−1Hkl;s as its matrix-elements. The subscript s to a variable refers to one of its components with β as their total number. The parameter β contains the information about underlying symmetry of the system. For example, for systems with time-reversal symmetry and integer angular momentum, the Hamiltonian in a generic representation is a real-symmetric matrix which gives β = 1. The Hamiltonians for system without time reversal symmetry are, in general, complex Hermitian which gives β = 2. Due to its Hermitian nature, the independent real parameters Hkl;s, which determine all matrix-elements of H, are M˜ = N + N(N −1)β/2 in number. For notational simpliﬁcation, let us denote them by Hµ where µ ≡ {kl; s} is a single index which can take a value from 1 → M.

The elements of H describe the overlap between various states of the basis in which H is represented. A complicated nature of interactions or presence of disorder in the system associates a deterministic uncertainty with the matrix elements Hµ. As the interaction between various states is governed by the nature and complexity of the region, the randomness associated with the elements Hµ can be of various types. In general, the complexity of a region can cause multiple interactions between basis states, resulting in correlations between matrix elements. In this section, we consider the cases which can be modeled by an ensemble described by a probability density ρ˜(H, b) ∝ e−F(H) with function F(H) as a sum over various combinations of the matrix elements of H.

A. Correlated Gaussian Case

A Gaussian ensemble of Hermitian matrices with correlated elements can be described by a matrix elements distribution

M

bµ

ρ˜(H, b) = Cexp[−

1

µ1=1

1 −

Hµ

M

1µ2Hµ

bµ

1

µ1,µ2=1

)] = Cρ(H, b) (1)

Hµ

2

1µ2. Here the subscripts to a coeﬃcient are indicators of the terms present in the product of which it is a coeﬃcient. Further, in µ

and bµ

with C as a constant and b as the set of coeﬃcients bµ

1

1,µ2, similar pairs are included only once. The distribution parameters b2;µ

1,µ2 are the measures of correlations between pairs of the matrix elements: < Hµ

>= ∂b∂logC

Hµ

. In general, diﬀerent system conditions can give rise to diﬀerent sets of distribution parameters b. A slight perturbation of the system due to a change in its parameters perturbs the matrix elements and therefore the probability density ρ(H, b). In the following, we consider a particular ﬂow in the matrix space generated by an operator L (describing the diﬀusion of the matrix elements with a constant drift and conﬁned by a quadratic potential),

![image 1](07_Bozovic_PRL2004_images/imageFile1.png)

1

2

2;µ1µ2

L =

µ

∂ ∂Hµ

![image 2](07_Bozovic_PRL2004_images/imageFile2.png)

gµ 2

∂ ∂Hµ

+ γHµ (2)

![image 3](07_Bozovic_PRL2004_images/imageFile3.png)

![image 4](07_Bozovic_PRL2004_images/imageFile4.png)

where gµ = 1 + δµ with δµ = 1 for µ = (kk; s) and δµ = 0 for µ = (kl; s), k = l. The parameter γ is arbitrary, giving the freedom to choose the end of the evolution [10]. The choice of the above form of L is motivated by our desire to obtain the equation governing the eigenvalue-dynamics in a well-known mathematical form.

The evolution of the probability density ρ(H, b), generated by operator L in the matrix space, is related to a multi-parametric ﬂow in b-space. This can be shown as follows. The probability density being a function of both H and b, the rates of change of ρ with variation of matrix elements and parameters b can be given as

∂ρ ∂Hµ

η(µ

1)

= − bµ

+

ρ (3) ∂ρ

µ1µ2bµ

1µ2Hµ

![image 5](07_Bozovic_PRL2004_images/imageFile5.png)

1

2

µ2

1

= −Hµ

Hµ

ρ (4) ∂ρ

![image 6](07_Bozovic_PRL2004_images/imageFile6.png)

1

2

∂bµ

1µ2

= −Hµ

ρ (5)

![image 7](07_Bozovic_PRL2004_images/imageFile7.png)

1

∂bµ

1

where η(µ

1)

(i.e η(µ

Hµ

µ1µ2 is the frequency of occurrence of the term Hµ

in the combination Hµ

2

1

1

1)

µ1µ2 = 2 for µ1 = µ2 and 1 for µ1 = µ2. With the help of eq.(3) and (4), a drift in the matrix space can be written in terms of a drift in parametric space,

µ1

Hµ

1

∂ρ ∂Hµ

= −

![image 8](07_Bozovic_PRL2004_images/imageFile8.png)

1

=

µ1

Hµ

cµ

1

µ1

∂ρ ∂bµ

cµ

![image 9](07_Bozovic_PRL2004_images/imageFile9.png)

1

1

ρ +

Hµ

1µ2Hµ

cµ

1

1

2

µ1,µ2

∂ρ ∂bµ

+

cµ

1µ2

![image 10](07_Bozovic_PRL2004_images/imageFile10.png)

1µ2

µ1,µ2

ρ

(6)

1µ2 = η(µ

1)

1µ2. Similarly a diﬀusion in the matrix space can be expressed as a combination of drifts in parametric space,

µ1µ2bµ

where c1;µ = bµ and cµ

∂2ρ ∂Hµ2

= (c2µ

1µ1)ρ + 2

1 − cµ

![image 11](07_Bozovic_PRL2004_images/imageFile11.png)

µ2

1

= (c2µ

1 − cµ

1µ1)ρ − 2

µ2

1µ2Hµ

cµ

cµ

2

1

+

∂ρ ∂bµ

cµ

cµ

−

1µ2

![image 12](07_Bozovic_PRL2004_images/imageFile12.png)

1

2

cµ

µ2,µ3

µ2,µ3

1µ3Hµ

1µ2cµ

2

ρ (7)

Hµ

3

∂ρ ∂bµ

cµ

1µ3cµ

2µ3

![image 13](07_Bozovic_PRL2004_images/imageFile13.png)

2µ3

(8)

A substitution of above equalities in eq.(2) gives us the following,

Lρ = Tρ + Cρ˜ (9) with C˜ = µ

[γ + gµ

- 1

![image 14](07_Bozovic_PRL2004_images/imageFile14.png)

- 2 (c2µ


1µ2)] and T as the generator of the dynamics in the parametric space,

1 −cµ

1

T ≡

µ1

∂ ∂bµ

∂ ∂bµ

fµ

+

. (10)

fµ

1µ2

![image 15](07_Bozovic_PRL2004_images/imageFile15.png)

![image 16](07_Bozovic_PRL2004_images/imageFile16.png)

1

1µ2

µ1,µ2

1

gµ

cµ

1µ3cµ

2µ3.

gµ

cµ

cµ

1µ2 and fµ

1µ2 = γcµ

1µ2 − (1/2) µ

Here fµ

= γcµ

1 − µ2

3

2

2

1

3

The above equation appears complicated, with many parametric derivatives present on its right side. However it is possible to map the multi-parametric ﬂow in the M-dimensional b-space to a single parametric drift in another parametric space, say y-space, consisting of variables yi, i = 1 → M where M = [3 + M˜ ]M/˜ 2. In other words, the generator T of the ﬂow in the b-space can be reduced to a partial derivative with respect to just one y-space variable, say y1:

∂ρ ∂y1|y2,..,yM (11)

T(y[b])ρ ≡

![image 17](07_Bozovic_PRL2004_images/imageFile17.png)

The desired transformation b → y required to convert eq.(10) into the form (11) can be obtained as follows. By using the deﬁnition ∂x∂ = Mk=1 ∂y

∂

∂yk, with x as various b parameters, T(b) (eq.(10)) can be transformed in terms of the derivatives with respect to y,

k

![image 18](07_Bozovic_PRL2004_images/imageFile18.png)

![image 19](07_Bozovic_PRL2004_images/imageFile19.png)

![image 20](07_Bozovic_PRL2004_images/imageFile20.png)

∂x

where

Tρ =

k

∂ρ ∂yk

Ak

![image 21](07_Bozovic_PRL2004_images/imageFile21.png)

(12)

Ak ≡

µ1

∂yk ∂bµ

∂yk ∂bµ

+

. (13)

fµ

fµ

1µ2

![image 22](07_Bozovic_PRL2004_images/imageFile22.png)

![image 23](07_Bozovic_PRL2004_images/imageFile23.png)

1

1µ2

µ1,µ2

1

The eq.(12) can be reduced in the desired form of eq.(11), if the transformation b → y satisﬁes following condition:

Ak = δk1 for k = 1 → M (14) The parameters y as a function of b can now be obtained by solving the set of conditions

(14),

y1 =

µ1

zµ(1)

G +

dbµ

1

1

µ1,µ2

1µ2zµ(1)

1µ2G + constant (15)

dbµ

zµ(1)

1µ2]−1 and the set z(1) of the functions zµ(1)

, zµ(1)

1,µ2 zµ(1)

where G = [ µ

+ µ

fµ

1µ2 are chosen such that the ratio

1µ2fµ

1

1

1

1

µ1

zµ(1)

zµ(1)

dbµ

+

1µ2 G (16)

1µ2dbµ

1

1

µ1µ2

is a complete diﬀerential (see appendix B). Note it is possible that the ratio (16) can be made an exact diﬀerential for diﬀerent sets z(1) which will lead to diﬀerent solutions of y. However any two of such solutions for y are diﬀerent from each other only by a constant (appendix B).

The conditions (14) further imply that parameters yk, k > 1 behave as the constants of the dynamics (generated by L) in the matrix space,

yk =

µ1

zµ(k)

dbµ

+

1

1

µ1,µ2

1µ2zµ(k)

dbµ

1µ2 + constant for k > 1 (17)

1,µ2 zµ(k)

zµ(k)

1µ2fµ

1µ2 = 0 for k > 1.

fµ

+ µ

with µ

1

1

1

The substitution of eq.(11) in eq.(9), gives the single parametric evolution of the joint probability density ρ(H) in the matrix space

µ

∂ ∂Hµ

![image 24](07_Bozovic_PRL2004_images/imageFile24.png)

∂ρ˜ ∂y1

∂ρ˜ ∂Hµ

+ γHµ ρ˜ =

![image 25](07_Bozovic_PRL2004_images/imageFile25.png)

![image 26](07_Bozovic_PRL2004_images/imageFile26.png)

(18)

where y1 is given by eq.(15). As the distribution parameters depend on the complexity of the system, y1 can be termed as the complexity parameter.

The parametric space transformation b → y maps the probability density ρ(H, b) to ρ(H, y(b)). As a result, ρ depends on various parameters yk, k = 1 → N˜. However eq.(18) implies that the diﬀusion, generated by the operator L in the matrix space, is governed by y1 only; the rest of them, namely yk, k > 1, remain constant during the evolution. Note it is always possible to deﬁne a transformation from the set b → y with yk, k > 1 as constants of the dynamics generated by L. This can be explained as follows. A matrix element, say Hij, describes how a basis state ψi interacts with state ψj through H. This results in dependence of the matrix element correlations and, thereby, of the set b, on the basis parameters e.g. basis indices. As the basis remains ﬁxed during the evolution, the suitable functions of basis parameters can be chosen to play the role of yk, k > 1. (Note a similar transformation has been used to obtain a single parametric evolution of multi-parametric Gaussian ensembles of Hermitian matrices; see [10] for details).

B. Non-Gaussian Case with third order matrix elements correlations

Let us consider an ensemble of Hermitian matrices with a 3rd correlations among its matrix elements, described by a probability density

M

bµ

ρ˜(H, b) = Cexp[−

1

µ1=1

M

1 −

Hµ

µ1,µ2=1

Hµ

1µ2Hµ

bµ

1

M

2 −

µ1,µ2,µ3=1

Hµ

1µ2µ3Hµ

bµ

2

1

] = Cρ(H, b) (19)

Hµ

3

1µ2µ3 are the measures of correlations among three matrix elements: < Hµ

Again the parameters bµ

>= ∂b∂logC

Hµ

Hµ

. Proceeding as in the Gaussian case, we get

![image 27](07_Bozovic_PRL2004_images/imageFile27.png)

3

2

1

µ1µ2µ3

∂ρ ∂Hµ

= − cµ

+

ρ (20) ∂ρ

cµ

1µ2Hµ

+

cµ

1µ2µ3Hµ

Hµ

![image 28](07_Bozovic_PRL2004_images/imageFile28.png)

1

2

2

3

µ2

µ2,µ3

1

= −Hµ

Hµ

Hµ

ρ (21)

![image 29](07_Bozovic_PRL2004_images/imageFile29.png)

1

2

3

∂bµ

1µ2µ3

The derivatives ∂b∂ρ

![image 30](07_Bozovic_PRL2004_images/imageFile30.png)

µ

and ∂b∂ρ

µ1

Hµ

1

∂ρ ∂Hµ

=

![image 31](07_Bozovic_PRL2004_images/imageFile31.png)

1

![image 32](07_Bozovic_PRL2004_images/imageFile32.png)

µ1µ2

remain same as in the Gaussian case (given by eqs.(4,5)),

µ1

cµ

1

∂ρ ∂bµ

+

cµ

![image 33](07_Bozovic_PRL2004_images/imageFile33.png)

µ1,µ2

1

∂ρ ∂bµ

1µ2

![image 34](07_Bozovic_PRL2004_images/imageFile34.png)

1µ2

+

cµ

µ1,µ2,µ3

∂ρ ∂bµ

1µ2µ3

![image 35](07_Bozovic_PRL2004_images/imageFile35.png)

1µ2µ3

(22)

1µ2µ3 = η(µ

1)

1µ2µ3 with η(µ

1)

µ1µ2µ3 as the frequency of occurrence of the term Hµ

where cµ

µ1µ2µ3bµ

. The second order derivative of ρ with respect to Hµ can be calculated by diﬀerentiating eq.(20) which, on combining with eq.(21), again leads to the form Lρ˜ = (T + C˜)ρ. Here L is still given by eq.(2) however the generator T now contains the ﬁrst order parametric derivatives as well as their products,

in the combination Hµ

Hµ

Hµ

1

1

2

3

Tρ =

µ1

fµ

1

∂ρ ∂bµ

+

fµ

![image 36](07_Bozovic_PRL2004_images/imageFile36.png)

µ1,µ2

1

+

µ1,µ2,µ3µ4µ5

cµ

1µ2µ3cµ

1µ4µ5

∂ρ ∂bµ

+

fµ

1µ2

![image 37](07_Bozovic_PRL2004_images/imageFile37.png)

1µ2

µ1,µ2,µ3

1 ρ

∂ρ ∂bµ

∂ρ ∂bµ

![image 38](07_Bozovic_PRL2004_images/imageFile38.png)

![image 39](07_Bozovic_PRL2004_images/imageFile39.png)

![image 40](07_Bozovic_PRL2004_images/imageFile40.png)

2µ3

4µ5

∂ρ ∂bµ

1µ2µ3

![image 41](07_Bozovic_PRL2004_images/imageFile41.png)

1µ2µ3

(23)

2µ2µ1(η(µ

1)

gµ

[2cµ

cµ

1µ2 + cµ

µ2µ2µ1 − 1)], fµ

1µ2 = γcµ

1µ2 − (1/2) µ

with fµ

= γcµ

1 − (1/2) µ

2

2

1

2

gµ

cµ

2µ4cµ

1µ3µ4.

gµ

[cµ

1µ3cµ

2µ3 + 2cµ

cµ

1µ2µ3] and fµ

1µ2µ3 = γcµ

1µ2µ3 − µ4

4

3

3

3

Similar to Gaussian case, eq.(23) can also be reduced to a single parametric derivative, namely form (11), by using a transformation from the set b to another set y. The operator

- T in this case transforms as


Tρ =

k

∂ρ ∂yk

+

Ak

![image 42](07_Bozovic_PRL2004_images/imageFile42.png)

∂ρ ∂yi

∂logρ ∂yk

Bik

![image 43](07_Bozovic_PRL2004_images/imageFile43.png)

![image 44](07_Bozovic_PRL2004_images/imageFile44.png)

i,k

(24)

where

Ak =

µ1

fµ

1

∂yk ∂bµ

+

fµ

![image 45](07_Bozovic_PRL2004_images/imageFile45.png)

µ1,µ2

1

Bik =

µ1,µ2,µ3µ4µ5

1µ2µ3cµ

cµ

1µ4µ5

∂yk ∂bµ

+

fµ

1µ2

![image 46](07_Bozovic_PRL2004_images/imageFile46.png)

1µ2

µ1,µ2,µ3

∂yk ∂bµ

∂yi ∂bµ

![image 47](07_Bozovic_PRL2004_images/imageFile47.png)

![image 48](07_Bozovic_PRL2004_images/imageFile48.png)

2µ3

4µ5

∂yk ∂bµ

1µ2µ3

![image 49](07_Bozovic_PRL2004_images/imageFile49.png)

1µ2µ3

(25)

(26)

The reduction of eq.(24) for Tρ to a single derivative ∂y∂ρ

will impose following conditions on the transformation b → y:

![image 50](07_Bozovic_PRL2004_images/imageFile50.png)

1

Ak = Nδk1 (27)

Bik + Bki = 0 (28) By solving conditions (27), y1 can be obtained as a function of the parameters b,

- y1 =


µ1

zµ(1)

dbµ

G +

1

1

µ1,µ2

1µ2zµ(1)

dbµ

1µ2G +

µ1,µ2,µ3

1µ2µ3zµ(1)

dbµ

1µ2µ3G + constant (29)

1µ2µ3]−1. Again the choice of the functions z(1) is so as to make the ratio

1µ2µ3 zµ(1)

1,µ2 zµ(1)

zµ(1)

1µ2µ3fµ

1µ2fµ

1µ2 + µ

fµ

+ µ

where G = [ µ

1

1

1

µ1

zµ(1)

zµ(1)

zµ(1)

dbµ

+

1µ2dbµ

1µ2 +

1µ2µ3 G (30)

1µ2µ3dbµ

1

1

µ1µ2

µ1µ2µ3

a complete diﬀerential. However the set z(1) in this case have to satisfy an extra set of conditions given by eq.(29). Again as in the Gaussian case, the parameters yj, j > 1 behave as constants of dynamics for this case too,

yk =

µ1

zµ(k)

dbµ

+

1

1

µ1,µ2

1µ2zµ(k)

dbµ

1µ2 +

µ1,µ2µ3

1µ2zµ(k)

dbµ

1µ2µ3 for k > 1 (31)

1,µ2 zµ(k)

zµ(k)

with arbitrarily chosen functions zµ(k) satisfy the constraint µ

1µ2 + µ1,µ2 zµ(k)

1µ2fµ

fµ

+ µ

1

1

1

1µ2µ3fµ

1µ2µ3 = 0 for k > 1 as well as the conditions given by eq.(28).

Using the b → y transformation given by eq.(29,31), the dynamics of ρ(H) with third order matrix element correlations can again be described by eq.(18). Note although the evolution is governed by same equation, however the complexity parameters are diﬀerent for Gaussian and non-Gaussian cases.

C. General Case

A generalized ensemble of Hermitian matrices with correlated elements can be described by a matrix elements distribution ρ˜(H) = Cρ(H) where

n

exp

ρ(H) =

r=1

 −

bp(r) rj=1Hµ

Pj

p(r)

  (32)

with C as a normalization constant. Here symbol p(r) refers to a combination of r elements chosen from a set of total M˜ = N + N(N − 1)β/2 elements of upper (or lower) diagonal matrix; note the terms present in a given combination need not be all diﬀerent. The

r

implies a product over r terms present in the pth combination with coeﬃcient bp(r) as a measure of their correlation: < rj=1Hµ

j=1 Hµ

Pj

>= ∂∂blogC

. The p(r) is a sum over all possible combinations (total (M˜ )r) of r elements chosen from a set of total M˜ of them; the sum includes only diﬀerent combinations. (Henceforth subscript p(r) will be written as p only unless details required for clariﬁcation).

![image 51](07_Bozovic_PRL2004_images/imageFile51.png)

pj

p(r)

Using eq.(32), the partial derivatives of ρ in matrix space and parametric space can be given as

 bp

 

n

∂ρ ∂Hµ

= −

![image 52](07_Bozovic_PRL2004_images/imageFile52.png)

r=1 p

∂ρ ∂bp(r)

= − rj=1Hµ

![image 53](07_Bozovic_PRL2004_images/imageFile53.png)

Pj

  ρ (33)

 

∂logHµ

r

r

pj

Hµ

![image 54](07_Bozovic_PRL2004_images/imageFile54.png)

pj

∂Hµ

j=1

j=1

ρ (34)

As a result, a drift in the matrix space can be related to a drift in the parametric space:

µ

∂ρ ∂Hµ

Hµ

=

![image 55](07_Bozovic_PRL2004_images/imageFile55.png)

∂ρ ∂bp

ηp(µ)bp

![image 56](07_Bozovic_PRL2004_images/imageFile56.png)

µ r,p(r)

(35)

where the term ηp(µ(r)) = rm=1 δ(µp

; µ) counts the frequency of occurrence of the element Hµ in the pth combination of r elements (δ(µp

m

= µ. Similarly a diﬀusion in the matrix space is related to a nonlinear ﬂow in the parametric space,

, µ) = 1 if µp

= µ and 0 is µp

j

j

j

 

  (36)

n

∂2ρ ∂Hµ2

∂ρ ∂bp−µ2

∂ρ ∂bp′+µ

∂ρ ∂bp′+p−µ2

∂ρ ∂bp+µ

ηp(µ′ )bp′

ηp(µ)bp

ρ−1 −

+ (ηp(µ) − 1)

=

ηp′;µbp′

![image 57](07_Bozovic_PRL2004_images/imageFile57.png)

![image 58](07_Bozovic_PRL2004_images/imageFile58.png)

![image 59](07_Bozovic_PRL2004_images/imageFile59.png)

![image 60](07_Bozovic_PRL2004_images/imageFile60.png)

![image 61](07_Bozovic_PRL2004_images/imageFile61.png)

r=1 p(r)

r′≤(n+2−r) p′(r′)

r′>(n+2−r) p′(r′)

Here the notation A+B refers to a combination which contains the elements of both A and B. Similarly A−B indicates dropping of all the elements of B from A. Further the notation µk is used to denote a combination Hµk (that is, kth power of Hµ).

Again, the matrix space ﬂow generated by the operator L (eq.(2)) can be related to a parametric ﬂow generated by the operator T, Lρ = Tρ + Cρ˜ , where T is now given by

  ∂ρ

 

n

m

∂logρ ∂bp′

gµ 2

+ fp

(37)

hpp′

Tρ ≡

![image 62](07_Bozovic_PRL2004_images/imageFile62.png)

![image 63](07_Bozovic_PRL2004_images/imageFile63.png)

![image 64](07_Bozovic_PRL2004_images/imageFile64.png)

∂bp

µ

r=1 p(r)

r′>(n+2−r) p′(r′)

with hpp′ = bubu′[ µ gµηu(µ)ηu(µ′)] and fp = − r′,p′(r′) bp′bq[ µ gµηp(µ′ )ηq(µ)]+[ µ ηv(µ)gµ(ηv(µ)− 1)]bv + 2γ[ µ ηp(µ)]bp. here q refers to a combination of r1 = r′ − r + 2 elements, such that q(r1) ≡ p′(r′) − p(r) + (kl)2. Similarly u, u′, v refer to combinations u(r0) = p(r) + 1, u(r1) = p′(r′) + 1 and v(r2) = p(r) + 2 of r0 = r + 1, r1 = r + 1 and r2 = r + 2 elements respectively.

The desired transformation b → y required to convert eq.(37) into form T(y[b])ρ ≡ ∂y∂ρ

![image 65](07_Bozovic_PRL2004_images/imageFile65.png)

1

= Mk=1 Dkj ∂y∂

can be obtained as follows. The substitution of ∂b∂

in eq.(37) with Dkj ≡

![image 66](07_Bozovic_PRL2004_images/imageFile66.png)

![image 67](07_Bozovic_PRL2004_images/imageFile67.png)

p(r)

k

∂yk

∂bp(r) transforms T in the form of eq.(24) where Ak and Bik are now given as Ak(y, b) =

![image 68](07_Bozovic_PRL2004_images/imageFile68.png)

fpDkp (38)

r p(r)

Bik(y, b) =

hpp′(x)DipDkp′ (39)

r,p(r) r′,p′(r′)

Again, for desired reduction of T to ∂y∂ρ

, the transformation b → y should satisfy conditions given by eq.(27,28). The conditions (27) can then be solved to obtain the variables in set y as functions of variable in set b (see appendix B)

![image 69](07_Bozovic_PRL2004_images/imageFile69.png)

1

yk =

r,p(r)

dbpzp(k)[1 − δk1 + Gk] + constant (40)

with Gk = δk1 r,p(r) zp(1)fp −1 and zp(k) as arbitrary functions which make r,p(r) dbpzp(k)[1+ (G − 1)δk1] an exact diﬀerential and satisfy the constraint r,r′ p(r),p′(r′) zp(i)zp(k′)fpp′G21 = 0 (the latter is required by the conditions (39)).

We ﬁnd, therefore, that, the diﬀusion of probability density for ensembles of Hermitian operators with correlated matrix elements (any order), is governed by a single parameter y1 with evolution described by eq.(18). The eigenvalue statistics of the above ensembles can therefore be studied by an exact diagonalization of eq.(18).

III. SINGLE PARAMETRIC EVOLUTION OF EIGENVALUES

The eigenvalue equation for the matrix H can be given as HU = λU with λ as the diagonal matrix with eigenvalues λi of H as its matrix elements and U as the eigenvector matrix (unitary for complex Hermitian case and orthogonal for real-symmetric case). The probability density P(E, y, b) of ﬁnding eigenvalues λi between Ei and Ei + dEi at a given Y can then be obtained from the matrix elements distribution,

![image 70](07_Bozovic_PRL2004_images/imageFile70.png)

![image 71](07_Bozovic_PRL2004_images/imageFile71.png)

![image 72](07_Bozovic_PRL2004_images/imageFile72.png)

P(E, y[b]) =

![image 73](07_Bozovic_PRL2004_images/imageFile73.png)

N

δ(Ei − λi)˜ρ(H, y[b])dH (41)

i=1

Here E refers to a diagonal matrix with elements E1, .., EN. As the Y ≡ y1-dependence of P in eq.(41) enters only through ρ, a derivative of P with respect to Y can be written as follows

![image 74](07_Bozovic_PRL2004_images/imageFile74.png)

∂P ∂Y

=

![image 75](07_Bozovic_PRL2004_images/imageFile75.png)

N

∂ρ˜ ∂Y

δ(Ei − λi)

i=1

dH (42)

![image 76](07_Bozovic_PRL2004_images/imageFile76.png)

The diﬀusion equation for ρ˜, namely eq.(18), can now be used to rewrite eq.(42) as

∂P ∂Y

= I1 + I2 (43) where

![image 77](07_Bozovic_PRL2004_images/imageFile77.png)

I1 = γ

µ

I2 =

µ

∂(Hµρ˜) ∂Hµ

δ(E − λ)

dH (44)

![image 78](07_Bozovic_PRL2004_images/imageFile78.png)

N

∂2ρ˜ ∂Hµ2

δ(Ei − λi)

![image 79](07_Bozovic_PRL2004_images/imageFile79.png)

i=1

dH (45)

The integral I1 can be simpliﬁed by using integration by parts

I1 = −γ

µ

N

∂ ∂En

= γ

![image 80](07_Bozovic_PRL2004_images/imageFile80.png)

n=1

N

∂ ∂Hµ

δ(Ei − λi) Hµ ρ˜ dH (46)

![image 81](07_Bozovic_PRL2004_images/imageFile81.png)

i=1

N

∂λn ∂Hµ

δ(Ei − λi)

Hµ ρ˜ dH (47)

![image 82](07_Bozovic_PRL2004_images/imageFile82.png)

µ

i=1

A further simpliﬁcation of the above equation requires a knowledge of the rate of change of eigenvalues of H due to a small change in its matrix elements. The rate can be obtained by using the eigenvalue equation for matrix H along with unitary (or orthogonal for realsymmetric H) nature of its eigenvectors (see appendix A). Using eq.(A2) of the appendix A in eq.(47) we get

I1 = γ

n

∂ ∂En

(EnP) (48)

![image 83](07_Bozovic_PRL2004_images/imageFile83.png)

The second term can similarly be rewritten as follows

I2 =

n

∂ ∂En µ

![image 84](07_Bozovic_PRL2004_images/imageFile84.png)

gµ 2

![image 85](07_Bozovic_PRL2004_images/imageFile85.png)

∂ ∂EnEm i

=

![image 86](07_Bozovic_PRL2004_images/imageFile86.png)

m,n

∂λn ∂Hµ

∂ ∂Hµ i

δ(µi − λi)

![image 87](07_Bozovic_PRL2004_images/imageFile87.png)

![image 88](07_Bozovic_PRL2004_images/imageFile88.png)

gµ 2

∂λm ∂Hµ

δ(Ei − λi)

![image 89](07_Bozovic_PRL2004_images/imageFile89.png)

![image 90](07_Bozovic_PRL2004_images/imageFile90.png)

µ

ρ˜dH (49)

∂λn ∂Hµ

![image 91](07_Bozovic_PRL2004_images/imageFile91.png)

ρ˜dH −

m

∂ ∂En i

![image 92](07_Bozovic_PRL2004_images/imageFile92.png)

δ(Ei − λi)

µ

∂2λn ∂Hµ2

gµ 2

![image 93](07_Bozovic_PRL2004_images/imageFile93.png)

![image 94](07_Bozovic_PRL2004_images/imageFile94.png)

ρ˜dH (50)

Now by using eqs.(A3,A5) of the appendix A, I2 can be expressed in terms of eigenvalue derivatives of ρ,

 

  (51)

∂2P ∂En2

∂ ∂En

βP Em − En

I2 =

+

![image 95](07_Bozovic_PRL2004_images/imageFile95.png)

![image 96](07_Bozovic_PRL2004_images/imageFile96.png)

![image 97](07_Bozovic_PRL2004_images/imageFile97.png)

n

n

m=n

A substitution of I1 and I2, given by eqs.(47,51), in eq.(43) leads an equation describing the single parametric evolution of the eigenvalues of ensemble ρ(H),

  ∂

 P (52)

∂P ∂Y

β Em − En

∂ ∂En

+

+ γEn

=

![image 98](07_Bozovic_PRL2004_images/imageFile98.png)

![image 99](07_Bozovic_PRL2004_images/imageFile99.png)

![image 100](07_Bozovic_PRL2004_images/imageFile100.png)

![image 101](07_Bozovic_PRL2004_images/imageFile101.png)

∂En

n

m=n

The eq.(52) describes the evolution of the eigenvalue density P(E, y[b]) ≡ P(E, Y, y2, ..yM) due to variation of the parameter Y from an arbitrary initial state, say P(E0, y[b0]) ≡ P(E0, Y0, y2, ..yM) occurring at Y = Y0. Note here the parameters yj (j > 1) being constants of motion, have a same value for both initial ensemble ρ(H0, b0) as well as ρ(H, b). The evolution of the eigenvalues tends to an steady state in limit ∂Y∂P → 0 or Y → ∞. The solution of eq.(52) in the limit is a Wigner-Dyson ensemble [7]: P(E) = i<j |Ei − Ej|βe−

![image 102](07_Bozovic_PRL2004_images/imageFile102.png)

![image 103](07_Bozovic_PRL2004_images/imageFile103.png)

![image 104](07_Bozovic_PRL2004_images/imageFile104.png)

![image 105](07_Bozovic_PRL2004_images/imageFile105.png)

![image 106](07_Bozovic_PRL2004_images/imageFile106.png)

γ

2 k Ek2 (thus a GOE for β = 1 and a GUE for β = 2). Note, under certain conditions, the steady state solution may also correspond to the eigenvalue distribution of an ensemble of anti-symmetric Hermitian matrices. A knowledge of the solution of eq.(52) can now help us in determining the n-level density correlations Rn, deﬁned as Rn(E1, E2, ..En; Y ) =

![image 107](07_Bozovic_PRL2004_images/imageFile107.png)

![image 108](07_Bozovic_PRL2004_images/imageFile108.png)

N j=n+1 dEjP(E; Y −Y0). The ﬁrst order correlation R1 is also known as mean level density and its inverse gives the mean level spacing ∆ of the full spectrum (that is, averaged of spacings in full length of the spectrum). By a direct integration, eq.(52) can also be used to study the evolution of Rn with changing complexity of the system.

N! (N−n)!

![image 109](07_Bozovic_PRL2004_images/imageFile109.png)

![image 110](07_Bozovic_PRL2004_images/imageFile110.png)

Equation (52) is applicable for arbitrary values of the coeﬃcients b; it is therefore valid for the case of uncorrelated Gaussian ensembles too. The latter have been shown to be good models for non-interacting systems [7]. Within random matrix framework, therefore, we ﬁnd that the energy levels of both systems, interacting as well as non-interacting, undergo a same diﬀusion process with changing system parameters. As a result, the level-statistics (and related physical properties) in the two cases can be described by the same mathematical formulation. However note that, due to diﬀerent complexity parameters in general, the rate of evolution is diﬀerent in the two cases.

The advantages of a single parametric formulation of the evolution of eigenvalues is manifold and have been discussed in detail in [10] in context of non-interacting systems (or uncorrelated ensembles); the similarity of eq.(52) with that of eq.(17) of [10] allows us to use the discussion given in sections I.(D),I.(E), II of [10] for the correlated ensembles too (with µ replaced by E). However, for completeness sake, we brieﬂy review it here again. The eq.(52) is similar to the equation governing the evolution of eigenvalues in the Dyson’s Brownian motion model which was originally introduced by Dyson to describe the eigenvalue-dynamics of an ensemble of Hermitian matrices subjected to random perturbation; the non-equilibrium states of this model are known as Brownian ensembles (see chapter 8 of [5]). Later on it was shown that when an ensemble H0 (ﬁxed or random) is subjected to a random perturbation, of strength √Y − Y0, by a standard random matrix ensemble V (described by a probability density e−(γ/2)TrV2), the resulting ensemble H = H0 + (√Y − Y0)V behaves like a Brownian ensemble (BE) (see chapter 14 of [5], chapter 6 of [6] and [12,10]). Here H0 and V may belong to a same symmetry class, with √Y − Y0 governing the parametric eigenvalue dynamics, or diﬀerent symmetry classes with √Y − Y0 as a parameter for symmetry admixing transitions. The statistical properties of BE depend only on the parameter √Y − Y0 besides underlying symmetry and many of their correlations are already known [12].

![image 111](07_Bozovic_PRL2004_images/imageFile111.png)

![image 112](07_Bozovic_PRL2004_images/imageFile112.png)

![image 113](07_Bozovic_PRL2004_images/imageFile113.png)

![image 114](07_Bozovic_PRL2004_images/imageFile114.png)

![image 115](07_Bozovic_PRL2004_images/imageFile115.png)

As discussed in [12], the mean level density R1 of a BE changes from an initial state to

a semi-circular form (typical of Wigner-Dyson ensembles) at the scale of γ(Y − Y0) ≃ N∆2l with ∆l(E, Y ) as the local mean level spacing at energy E; its evolution can therefore be described in terms of the parameter (Y − Y0). However the transition of level-density correlations to equilibrium, with (Y −Y0) as the evolution parameter, is rapid, discontinuous for inﬁnite dimensions of matrices [12]. For small-Y and large N, a smooth crossover can be seen in terms of a rescaled parameter Λ(E):

Λ(E) = γ|Y − Y0|/∆2l (53)

The limits Λ → 0 and Λ → ∞ correspond to the level-statistics approaching the initial state and Wigner-Dyson ensembles, respectively. As obvious from the deﬁnition of Λ, an intermediate state between two limits occurs when the perturbation √Y − Y0 mixes levels in a ﬁnite energy-range of r local mean level-spacings, r ≃

![image 116](07_Bozovic_PRL2004_images/imageFile116.png)

√Y − Y0/∆η, 0 < r < N. For ﬁnite size BE, Λ varies smoothly with changing Y − Y0 which results in a continuous family of BEs, parameterized by Λ. However the level-statistics for the large BE (size N → ∞) can be divided into three regions:

![image 117](07_Bozovic_PRL2004_images/imageFile117.png)

- (i) initial regime: (Y −Y0)∆−l 2 → f(N−1): If the local mean level spacing ∆l increases with size N at a rate faster than that of √Y − Y0, the perturbation will mix fewer number of levels as system size increases. The level-statistics therefore approaches its initial state in the inﬁnite size limit.

![image 118](07_Bozovic_PRL2004_images/imageFile118.png)

- (ii) WD regime: (Y − Y0)∆−l 2 → f(N): Due to change in ∆η with size N being slower than that of √Y − Y0), even a small change in complexity parameter in this case is capable of mixing the levels in an increasing energy range of many local mean level-spacings. This results in an increasing delocalization of eigenfunctions and Wigner-Dyson behavior of level-statistics.

![image 119](07_Bozovic_PRL2004_images/imageFile119.png)

- (iii)Critical regime: (Y − Y0)∆−l 2 = f(N0) = α= a constant: The perturbation in this case mixes only a ﬁnite (non-zero), ﬁxed number of levels even when the system is growing in size. The ﬁnite, non-zero Λ-value in limit N → ∞ therefore gives rise to a third statistics, intermediate between initial ensemble and Wigner-Dyson ensemble, which is known as the critical Brownian ensemble (CBE). This being the case for arbitrary values of α (non-zero and ﬁnite), an inﬁnite family of critical BE, characterized by can occur during initial ensemble → Wigner-Dyson ensembles.


The same evolution equations of P for correlated ensembles and BE imply a similarity in their eigenvalue distributions for all Y -values, under similar initial conditions (that is,

- P(E, Y0) same for both the cases). As a result, one obtains the analogous evolution equations for their correlations Rn too (see eq.(16) of [12]). The mean level density R1 of a correlated ensemble can therefore be given by the mean level-density of a BE with same (Y − Y0) value and belonging to a same symmetry class (as that of correlated ensemble). Further the analogy of evolutions of higher order correlations (n > 1) in the two cases implies (i) the discontinuity of transition of Rn for inﬁnite size correlated ensembles, (ii) a smooth crossover of Rn for ﬁnite correlated ensembles. The crossover parameter for correlated ensembles can again be deﬁned by eq.(54) where now Y − Y0 is the complexity parameter of the correlated ensemble and ∆l as its local mean level spacing. Note, in the case of d-


![image 120](07_Bozovic_PRL2004_images/imageFile120.png)

dimensional disordered systems of linear size L, the number of states in a volume of linear dimension ζ in d-dimensions is n(0)ζd with n(0) as the density of states at Fermi level and ζ as the localization length. Consequently, the typical energy separation between such states is ∆l(E, Y ) = (n(0)ζd)−1. Similarly the mean level spacing of states in the full length of the spectrum is ∆(E, Y ) = (n(0)Ld)−1. For disordered systems, the local mean level spacing ∆l can therefore be expressed in terms of the mean level density R1 as ∆l = (L/ζ)dR1−1.

The parameter Λ, being a function of the distribution parameters of the matrix elements, is sensitive to the changes in the system parameters, due to their inﬂuence on the system-interactions and their uncertainties. Some examples of such system parameters are disorder, dimensionality, boundary and topological conditions, system size etc. The presence of disorder randomizes the interactions in the system with degree of disorder aﬀecting the distribution parameters b and consequently Λ. The dependence of Λ on dimensionality and boundary conditions can be explained by using a simple example. Consider a N ×N lattice with a Gaussian site disorder as well as a Gaussian type random interaction between nearestneighbor sites. The lattice Hamiltonian H, in site representation, is a sparse matrix with only (Z +1)N non-zero, independently distributed matrix elements; here Z is the number of nearest-neighbors of a site. Consequently only (Z+1)N b-parameters (out of N2) contribute to Y . As the coordination number Z is diﬀerent for diﬀerent dimensions and boundaries of the lattice, the Z-dependence of Y results in its dependence on the dimensionality as well as boundary conditions of the system. Further the local mean level spacing is also sensitive to the dimensionality as well as the boundary conditions. A variation of any of the latter parameters can aﬀect both ∆l and Y and therefore Λ; (See also [11] where the dependence of Λ on system parameters is explained by considering an example of Anderson Hamiltonian).

The size-dependence of Λ also plays a crucial role in determining the level statistics of the correlated ensemble in the crossover regime. In general, both Y −Y0 as well as the local mean level density are the functions of system-size N which results in N-dependence of Λ. As a consequence, the level statistics in ﬁnite systems smoothly approaches one of the two end points, namely, Λ → 0 or Λ → ∞, with increasing system size. However, as in BE case, the variation of Λ in inﬁnite correlated ensembles may lead to an abrupt transition, with its critical point given by the condition Λ = size independent. As in the BE case, the sizeindependence of Λ at the critical point, results in a level-statistics diﬀerent from the two end points. Note if the size-dependence of ∆2l in a correlated ensemble remains diﬀerent from that of Y − Y0 under all complexity conditions, the system will never undergo a transition in level-statistics.

IV. EXAMPLES

In this section, we consider two examples corresponding to 2nd and 3rd order matrix elements correlations and provide the theoretical formulation for 2-point eigenvalue correlations for the cases by using the Brownian ensemble analogy.

A. Quantum Hall System

Let H = H0 + V (r) be the single particle Hamiltonian for a disordered quantum Hall system with H0 as the kinetic energy of the electrons and V (r) as a space correlated disordered potential e.g < V (r)V (r′) >= f(r, r′) (with < V (r) >= 0). Using the Landau states ψnk(r) ≡< r|nk > (the eigenstates of H0) as the basis, H can be written as Hnk;n′k′ = ǫnδn,n′δk,k′ + Vnk;n′k′ where Hnk;n′k′ ≡< nk|H|n′k′ > and ǫn = (n + 1/2)¯hω as the eigenvalues of H0. The interaction between impurities results in a correlation of the matrix elements of V and thereby H [13]:

2k2(r)ψn∗

3k3;n4k4 >= drdr′ψn∗

1k1(r)ψn

1k1;n2k2Vn

< Vn

4k4(r′)f(r, r′). (54)

3k3(r′)ψn

The parameter Λ can now be determined if mean level spacing ∆ and the real-space correlations for the potential V are explicitly known. For example, consider the case when magnetic ﬁeld B becomes much stronger than the disorder potential. The Hamiltonian matrix H in this case is divided into various independent blocks (each corresponding to a diﬀerent Landau level) and the statistics of energy states in each Landau Level can be discussed independently [13]. For a Gaussian type disorder < V (r)V (r′) >= (V02/2πσ2)e−|r−r′|2/2σ2, the matrix element correlations in the lowest Landau level n = 0 can be given as < V0i;0j V0k;0l >≡< Vij Vkl > where

√

2α2/2e−(i−k)

2/2α2 (55)

![image 121](07_Bozovic_PRL2004_images/imageFile121.png)

< VijVkl >= (V02/lcLyα

2π)δ(i − j, l − k)e−(i−j)

with α2 = (1 + σ2/lc2) as a measure of the correlation length of the potential relative to the magnetic length lc = (¯h/eB)1/2 [13]. Using the notation H0k;0l ≡ Hkl, the distribution parameters of the matrix elements of the Hamiltonian in the Landau level n = 0 can be given as

< Hij > = ǫ0δij (56)

< Hij;s Hkl;s > = ǫ20δijδkl+ < Vij;sVkl;s > (57) with < Vij;sVkl;s > as the correlations between diﬀerent components of the elements of V ,

< Vij;s Vkl;s′ >=

- 1

![image 122](07_Bozovic_PRL2004_images/imageFile122.png)

- 2


[< VijVlk > +(−1)s−1 < VijVkl >] δss′ (58)

The distribution of the local Hamiltonian for the lowest Landau level can then be represented by eq.(1) with parameters b obtained from eqs.(56,57) (here µ1 ≡ (ij; s), µ2 ≡ (kl; s)); see appendix C for an example. A substitution of the b-parameters in eq.(15) gives us the complexity parameter governing the energy level dynamics in the lowest Landau level. As shown in the appendix C by a simple case N = 2, the parameters b and, therefore Y , turns out to be a function of the disordered potential α, V0, system length Ly as well as magnetic ﬁeld B and can be varied by changing any one of them.

The above discussion is valid for higher order landau Levels too, with complexity parameter still described by eq.(15) however the coeﬃcients bµ

1µ2 are diﬀerent for diﬀerent Landau levels (see [13] for the matrix element correlations of potential V ). The rate of transition of level-statistics therefore diﬀers, in general, from one Landau level to another. For weak magnetic ﬁelds, where various Landau levels can not be considered as independent, H can still be represented by the ensemble eq.(1). However, now the number of coeﬃcients bµ

1µ2

which contribute to Y is much larger (due to correlations between levels in two diﬀerent Landau Levels).

In absence of disorder, under the independent Landau Level approximation, all energy levels in a given Landau Level are degenerate and matrix H = H0 is a diagonal matrix with a Poisson behavior for its eigenvalues (due to dominance of zero spacings). The switching of disorder removes the degeneracy and delocalizes the wavefunction if the impurities are interacting. The degree of delocalization depends on the strength of impurity interactions with respect to the magnetic ﬁeld strength B. If the latter is strong enough to mix the levels in an energy range of many mean level spacings, (which corresponds to the limit H ≈ V ), the energy levels of H show a GUE behavior. (This is similar to the case of strongly interacting many body systems e.g. the statistics of resonances in complex nuclei which can be well-modeled by GOE or GUE [7]). Under an intermediate state of disorder, therefore, the ensemble H lies between the Poisson ensemble and GUE and can be modeled by eq.(1). The level statistics for this case can then be given by the one for a BE appearing during a Poisson → GUE transition . The two point correlator R2 [12] for states in lowest Landau level can therefore be given as

(1 − z2)(1 + 2z√x) 1 + x + 2z√x

![image 123](07_Bozovic_PRL2004_images/imageFile123.png)

  (59)

 

![image 124](07_Bozovic_PRL2004_images/imageFile124.png)

dz cos(2πrx) exp −8π2Λx(1 + x + 2z√x)

4 π

∞

1

![image 125](07_Bozovic_PRL2004_images/imageFile125.png)

R2(r; Λ) − R2(r; ∞) =

dx

![image 126](07_Bozovic_PRL2004_images/imageFile126.png)

![image 127](07_Bozovic_PRL2004_images/imageFile127.png)

![image 128](07_Bozovic_PRL2004_images/imageFile128.png)

0

−1

2(πr)

where R2(r, ∞) = 1 − sin

π2r2 (the GUE limit); the above formulation was obtained for the BE in [12].

![image 129](07_Bozovic_PRL2004_images/imageFile129.png)

Let us now consider the case with weak magnetic ﬁelds where the interaction between various Landau levels can not be ignored. The eigenvalue spectrum of H0 for this case behaves as a uniform spectrum [13] (that is, an initial spectrum of uniform spacing). The switching of interacting-impurities potential V again results in broadening of the wavefunctions. In the limit where impurity interactions are strong enough to mix energy levels in diﬀerent Landau levels (that is H ≈ V ), the eigenvalues of H show a GUE behavior. The varying degree of the interaction between impurities therefore leads to a transition of the level statistics from uniform spectrum → GUE behavior. The two point correlation for the level-statistics at any intermediate stage of impurity interaction can then be given by that of a BE appearing during the uniform spectrum → GUE transition:

∞

1 0

2qxΛ [cos(2πqr) − cos(2π(q + x)r)] (60)

2q2Λ

dx(1 − x)e−8π

e−8π

R2(r; Λ) − R2(r; ∞) = 2

q=−∞

with Λ → ∞ corresponding to GUE limit.

B. Disordered Systems with fermionic interactions

Consider a general Hamiltonian for spinless interacting fermions

H =

ij

Vija+i aj +

![image 130](07_Bozovic_PRL2004_images/imageFile130.png)

1 4 ijkl

Uijkla+i a+j alak (61)

here the states |i >= a+i |0 > describe a ﬁxed basis of m single-particle states with Vij as matrix elements of the one body Hamiltonian and Uijkl as the antisymmetrized matrix elements of the two body interaction U. The presence of disorder randomizes both V and

- U. For example, for V as a white noise, its matrix elements are independently distributed random variables. However the fermionic interaction results in correlations among matrix elements of U: < UijklUklmnUmnij >= d3r1d3r2d3r3ψij∗ (r1)ψkl(r1)ψkl∗ (r2)ψmn(r2)ψmn∗ (r3)ψij(r1)f(r1, r2)f(r2, r3)f(r3, r1) (62)

with f(r1, r2) as the interaction between two fermions at positions r1 and r2. The Hamiltonian H will therefore be a matrix with varying degree of correlations between its elements and can be represented by ensemble eq.(19). In absence of fermionic interaction, the matrix H = V and its statistical properties depend on the degree of disorder. For example, in presence of strong disorder, the eigenvalues of V show a Poisson distribution with localized eigenfunctions [11,3,7]. The weak disorder limit of V shows a Wigner-Dyson distribution for its eigenvalues with extended eigenfunctions. Similarly in absence of disorder, H = U and its statistical behavior is governed by the fermionic density in various parts of the system. The presence of almost uniform fermionic density in the system leads to delocalization of eigenfunctions and U behaves like an ensemble of anti-symmetric Hermitian matrices (see [5] for details on anti-symmetric random matrices). However non-uniform electronic density in various parts of the system (that is, stronger interactions in certain parts of the system as compared to others) can result in localization of wavefunctions and thereby a Poisson behavior for the eigenvalues of U.

In presence of both disorder as well as fermionic interaction, the behavior of H is governed by the inter-competition between them. In this case, it is preferable to represent H in the N = m2 dimensional basis of two particle states |ij >; the choice of the basis results in appearance of the disorder elements as the diagonal elements of H and fermionic interaction elements as the oﬀ-diagonals: < ij|H|ij >= Vij and < ij|H|kl >= Uijkl. The changing strength of the fermionic interaction in presence of disordered potential subjects the level-statistics to undergo a transition from the initial state (given by the statistics of

- V ) to Wigner-Dyson statistics (when U ≃ V ). However, in the limit when the disorder potential becomes negligible as compared to fermionic interactions, the level-statistics of H approaches that of anti-symmetric matrices. As obvious, the level-statistics for all other cases, corresponding to diﬀerent strengths of disorder potential and fermionic density, will lie on the transition curve from Poisson → Wigner-Dyson → anti-symmetric ensembles.


Using eq.(19) as the model for intermediate states, the level-statistics for this case can then be described by BE lying between Poison → anti-symmetric ensemble.

The ground state properties of electrons in nano-particles or quantum dots, that is, ﬁnite systems of fermions interacting via coulomb forces, are not yet fully understood. Using ensemble (19) or (32) as their model, the physical properties of these system can now be probed further and earlier experimental observations may be explained. For example, it has been experimental observed that the peak-spacing statistics for an irregular quantum dot in Coulomb blockade regime undergoes a crossover from Wigner-Dyson to Gaussian behavior as the strength of electron-electron interaction increases [1,2]. Within our formulation, the observed behavior can be explained as follows. The single electron dynamics inside a quantum dot of irregular shape is chaotic; the level-statistics of single particle Hamiltonian V can therefore be modeled by the Wigner-Dyson behaviour [3]. The addition of more electrons switches the potential U, however, due to non-uniform electronic density during initial stages, the correlation between various matrix elements of U need not be same. The statistical behavior of the quantum dot can therefore be described by an ensemble given by eq.(19). As electron density increases, U dominates over V and the level-statistics approaches the behavior of anti-symmetric matrices. It is already known that the nearest-neighbor spacing distribution for non-central spacings in the spectrum of anti-symmetric Hermitian matrices behaves like a Gaussian distribution [5]. The observed Gaussian behavior of the peak-spacings in the strong interaction limit is therefore well in agreement with theoretical expectations. Using ensemble (19) as a model for the quantum dot Hamiltonian, the behavior of peak-spacings in the intermediate regime can be predicted to be similar to that of a BE appearing during a cross-over from GOE → anti-symmetric ensembles. A detailed quantitative analysis of such cases is still in progress and will be published elsewhere.

In general, the size dependence of the parameter Y − Y0 and the local mean level spacing ∆l for a system with e-e interaction is diﬀerent from the non-interacting systems. In interacting systems, therefore, the critical point of level-statistics, given by condition Λ = N − independent, can occur at a disorder strength (or energy) diﬀerent from the one for non-interacting systems. This is consistent with the results given by renormalization group techniques [15] which show that the introduction of interactions into quantum dots can produce phase transitions in the limit of weak disorder, leading to behavior qualitatively diﬀerent from the non-interacting case. Further for one dimensional non-interacting systems, it is known that the wavefunctions are localized even in a weak disorder limit. However our formulation indicates that the fermionic interaction may lead to extended states even in one dimensional disordered system; the implication is in agreement with earlier studies in this context [16].

V. CONCLUSION

In summary we show, for the ﬁrst time, that the level-statistics of disordered systems with interactions is governed by a single parameter, namely, the rescaled complexity parameter Λ. Note the level-statistics of non-interacting systems can also be described in terms of Λ [10].

However the introduction of interactions modiﬁes the dependence of Λ on system parameters which can signiﬁcantly aﬀect the location of the critical point for the phase transitions and corresponding level statistics. Our study also reveals a deep level of universality underlying physical systems, namely, the Brownian ensembles as the statistical back bone of both interacting as well non-interacting systems. This universality should be explored in full detail as it may reveal many new connections among a wide range of complex systems and can be helpful in theoretical formulation of many of their physical properties.

APPENDIX A: THE CHANGE OF EIGENVALUES AND EIGENFUNCTIONS

The eigenvalue equation of a complex Hermitian matrix H is given by HU = UΛ with Λ as the matrix of eigenvalues λn and U as the eigenvector matrix, unitary in nature. As obvious, a slight variation of the matrix elements of H will, in general, lead to variation of both the eigenvalues as well as the eigenvectors and associated rates of change can be obtained as follows (see appendices A-E of [10] for more details):

As λn = i,j UniHijUnj∗ , the rate of change of λn with respect to Hkl;s (with s referring to real, s = 1, and imaginary, s = 2, parts of Hkl) can be given

is−1 gkl

∂λn ∂Hkl;s

[UlnUkn∗ − (−1)sUln∗ Ukn]. (A1) where gkl = 1 + δkl. This can further be used to obtain the following relations

=

![image 131](07_Bozovic_PRL2004_images/imageFile131.png)

![image 132](07_Bozovic_PRL2004_images/imageFile132.png)

2

∂λn ∂Hkl;s

HklUlnUkn∗ = λn (A2) and

Hkl;s =

![image 133](07_Bozovic_PRL2004_images/imageFile133.png)

s=1

k,l

k≤l

2

∂λn ∂Hkl;s

∂λm ∂Hkl;s

gkl

= 2δmn (A3)

![image 134](07_Bozovic_PRL2004_images/imageFile134.png)

![image 135](07_Bozovic_PRL2004_images/imageFile135.png)

s=1

k≤l

As obvious from eq.(A1), the second order change of an eigenvalue with respect to a matrix element requires a knowledge of the rate of change of one of the eigenvector components with respect to Hkl. The latter can again be obtained by using the eigenvalue equation,

is−1 gkl m=n

∂Upn ∂Hkl;s

1 λn − λm

Upm(Ukm∗ Uln + (−1)s+1Ulm∗ Ukn) (A4)

=

![image 136](07_Bozovic_PRL2004_images/imageFile136.png)

![image 137](07_Bozovic_PRL2004_images/imageFile137.png)

![image 138](07_Bozovic_PRL2004_images/imageFile138.png)

Now by diﬀerentiating eq.(A1) with respect to Hkl;s and by using the eq.(A4) we can show that

2

∂2λn ∂Hkl2 ;s

1 λn − λm

= 2β

(A5)

gkl

![image 139](07_Bozovic_PRL2004_images/imageFile139.png)

![image 140](07_Bozovic_PRL2004_images/imageFile140.png)

m

s=1

k≤l

For the real-symmetric case, the corresponding relations can be obtained by using U+ = UT (as eigenvector matrix is now orthogonal) in eq.(A1) and taking Hij;2 = 0 for all values of i, j.

APPENDIX B: SOLUTION OF EQ.(38)

According to theory of partial diﬀerential equations (PDE) [14], the general solution of a linear PDE

M

∂Z ∂xi

Pi(x1, x2, .., xM)

![image 141](07_Bozovic_PRL2004_images/imageFile141.png)

i=1

= R (B1)

is F(u1, u2, .., un) = 0 where F is an arbitrary function and ui(x1, x2, .., xn, Z) = ci (a constant), i = 1, 2, .., n are independent solutions of the following equation

dx1 P1

![image 142](07_Bozovic_PRL2004_images/imageFile142.png)

dx2 P2

dxk Pk

=

= .....

![image 143](07_Bozovic_PRL2004_images/imageFile143.png)

![image 144](07_Bozovic_PRL2004_images/imageFile144.png)

dxM PM

dZ R

= ......

=

![image 145](07_Bozovic_PRL2004_images/imageFile145.png)

![image 146](07_Bozovic_PRL2004_images/imageFile146.png)

(B2)

Note the function F being arbitrary, it can also be chosen as F ≡

(uj − cj) = 0 (B3)

j

The equations for various yj in the set of eq.(38) are of the same form as eq.(B2) and, therefore, can be solved as described above. Let us ﬁrst consider the equation for y1; its general solution can be given by a relation F(u1, u2, .., uM) = 0 where function F is arbitrary and uj are the functions of M parameters of set b such that uj({b}, y1) = cj (with cj’s as constants). The functions uj are the independent solutions of the equation

dbp(2) fp(2)

dbp(1) fp(1)

= .... =

![image 147](07_Bozovic_PRL2004_images/imageFile147.png)

![image 148](07_Bozovic_PRL2004_images/imageFile148.png)

dbp(r) fp(r)

= .....

= ...... = dy1 (B4)

![image 149](07_Bozovic_PRL2004_images/imageFile149.png)

where the equality between ratios is implied for all possible combinations p(r) of r terms, r = 1 → n, with M as the total number of combinations. It is easy to see that each of

(1) p dbp

the above ratios is equal to r,p(r)z

r,p(r)zp(1)fp where zp(1) are arbitrary functions. The eq.(B4) can therefore be rewritten as

![image 150](07_Bozovic_PRL2004_images/imageFile150.png)

zp(1)dbp r,p zp(1)hp

dy1 = r,p(r)

![image 151](07_Bozovic_PRL2004_images/imageFile151.png)

(B5)

- A solution, say u1 of eq.(B5), or alternatively eq.(B4), can now be obtained by choosing the functions zp(1) such that the right side of the above equation becomes an exact diﬀerential:


u1 ≡ y1 −

r,p(r)

dbpzp(1)G1 = constant (B6)

where G1 = [ r,p(r) zp(1)hp]−1. The general solution for y1 can therefore be given by a combination of all possible functions u obtained by using arbitrary set of z-functions. It

can be shown that each such solution diﬀer from the other only by a constant: uj = ui + constant; (this is due to equality of the two ratios obtained by choosing two diﬀerent sets

- z(1) of the functions). The y1 can therefore be written as follows,


y1 =

r,p(r)

dbpzp(1)G1 + constant (B7)

which gives eq.(40) for k = 1.

The set of equations (38) can similarly be solved for other yj (j > 2). For example, the solution of eq.(38) for yk can be given by the function Fk(v1, ..vM) = 0 where vj({b}, yk) = constant are the independent solutions of following equality

dbp(1) fp(1)

dbp(2) fp(2)

= .... =

= .....

![image 152](07_Bozovic_PRL2004_images/imageFile152.png)

![image 153](07_Bozovic_PRL2004_images/imageFile153.png)

dbp(r) fp(r)

dyk 0

= ......

![image 154](07_Bozovic_PRL2004_images/imageFile154.png)

![image 155](07_Bozovic_PRL2004_images/imageFile155.png)

. (B8)

- A solution, say v1, of eq.(B8) can now be given as


v1 ≡ yk −

r,p(r)

dbpzp(k) = constant (B9)

where zp(k) are arbitrarily chosen M functions which satisfy the condition

zp(k)fp = 0 (B10)

r,p(r)

As obvious, one possible choice for z(k) functions satisfying the above condition is zp(k) = 0 for all p(r) which gives yk = constant.

As each solution of eq.(B8) is diﬀerent from the other only by a constant, the general solution for yk, k > 1, can now be given as

yk =

r,p(r)

dbpzp(k) + constant (B11)

The eq.(B7) and eq.(B11) together give the set of eqs.(40).

APPENDIX C: EXAMPLE FOR QUANTUM HALL CASE

Within independent Landau level approximation, the Quantum Hall ensemble can be described by the probability density ρ(H) given by eq.(1) with coeﬃcients b given by eqs.(57,58). However it can further be simpliﬁed by choosing the origin of energy at ǫ0 which makes bµ =< Hµ >= 0. The matrix element distribution in the Quantum Hall case can now be described by a probability density

M

bµ

ρ˜(H, b) = Cexp[−

µ1,µ2=1

1µ2Hµ

1

)] (C1)

Hµ

2

with C as the normalization constant

C−1 = dHe−

2

bµ1µ2Hµ1Hµ2) = (

µ1µ2

s=1

DetBs)−1/2 (C2)

Here B(s) is the matrix of coeﬃcients bµ

1µ2 are related to second order correlation < Hµ

1µ2. The parameters bµ

>:

Hµ

2

1

Hµ

< Hµ

2

1

> = Hµ

1

ηµ

- 1µ2

![image 156](07_Bozovic_PRL2004_images/imageFile156.png)

- 2


=

ρ˜dH (C3)

Hµ

2

∂lnC ∂bµ

![image 157](07_Bozovic_PRL2004_images/imageFile157.png)

1µ2

(C4)

1µ2 = 2 and 1 for pairs {µ1} = {µ2} and {µ1} = {µ2} respectively. Let Q(s) be the matrix with its elements as the correlations between elements of H, that is, (Q(s))µ

where ηµ

1µ2 = (4/ηµ

1µ2) < Hµ

Hµ

>. By using eq.(C2) in eq.(C4), we get

1

2

∂lnDet[B(s)] ∂bµ

Q(µs)

1µ2 =

![image 158](07_Bozovic_PRL2004_images/imageFile158.png)

1µ2

Cof(Bµ

1µ2) Det[B(s)]

== (B(s))−1µ

2µ1 (C5)

=

![image 159](07_Bozovic_PRL2004_images/imageFile159.png)

where Cof(Bµ(s)

1µ2) implies the cofactor of the element Bµ

1µ2 in the matrix Bs. This implies

- Q(s) = (B(s))−1. The matrix B(s) for the QH case can therefore be obtained by inverting the


correlation matrix Q(s) = {Q(µs)

1µ2}.

Let us consider the case N = 2. Using the Hµ notation, various components of matrix elements can now be denoted as H1 = H11;1, H2 = H12;1, H3 = H22;1, H4 = H12,2. Following eq.(60), the correlation matrix Q(1) in this case is a 3 × 3 matrix

a o 2ax





Q(1) =

(C6)

o a/2x1 0

 

 

2ax 0 a

where a = (V02/2lcLyα√2π), x = e−1/2α2 and x1 = eα2/2. By using the relation (C5), B(1) can be given as

![image 160](07_Bozovic_PRL2004_images/imageFile160.png)

1 o −2x





1 a(1 − 4x2)

B(1) =

o 8x1(1 − 4x2) 0

(C7)

![image 161](07_Bozovic_PRL2004_images/imageFile161.png)

 

 

−2x 0 1

Due to Hermitian nature of H, only its oﬀ-diagonal elements have imaginary parts. For N = 2 case, therefore, B(2) is just a 1 × 1 matrix, corresponding to correlation < H4H4 >

with µ4 ≡ (12; 2): B(2) = b44 = (2 < H4H4 >)−1. The parameter set y for this case can now be obtained by solving the condition Ak = 4i,j=1 fij ∂y

∂bij = δk1 where fij = γbij −

k

![image 162](07_Bozovic_PRL2004_images/imageFile162.png)

(1/2) 4k=1 gkcikcjk; here gk = 2 for odd k and gk = 1 for even k. As discussed in appendix (B), a solution of the condition can be given as

db12 f12

db13 f13

db22 f22

db31 f31

db23 f32

db33 f33

db44 f44

dyk δk1

db11 f11

=

=

=

=

=

=

=

=

. (C8)

![image 163](07_Bozovic_PRL2004_images/imageFile163.png)

![image 164](07_Bozovic_PRL2004_images/imageFile164.png)

![image 165](07_Bozovic_PRL2004_images/imageFile165.png)

![image 166](07_Bozovic_PRL2004_images/imageFile166.png)

![image 167](07_Bozovic_PRL2004_images/imageFile167.png)

![image 168](07_Bozovic_PRL2004_images/imageFile168.png)

![image 169](07_Bozovic_PRL2004_images/imageFile169.png)

![image 170](07_Bozovic_PRL2004_images/imageFile170.png)

![image 171](07_Bozovic_PRL2004_images/imageFile171.png)

The above equations can now be solved by making the ratio exact diﬀerential, (following from eq.(B5) of appendix B)

dyk δk1

dFk Gk

=

![image 172](07_Bozovic_PRL2004_images/imageFile172.png)

![image 173](07_Bozovic_PRL2004_images/imageFile173.png)

(C9)

where dFk ≡ i,j zij(k)dbij and Gk ≡ i,j zij(k)fij with z(k) as arbitrary functions. Using eq.(C7), the Gk can be shown to be

4 (1 − 4x2)2a2

(z11(k) + z33(k))[(γa − 4) − 4x2(γa + 1)] + (z13(k) + z31(k))4x(8 − γa(1 − 4x2)) + +16z22(k)a−2x1(γa − 16x1) − z44(k)ax−1 1(2γx1 + a)/2 (C10)

Gk =

![image 174](07_Bozovic_PRL2004_images/imageFile174.png)

Similarly dFk ≡

zij(k)dbij = (z11(k) + z33(k))dx2 − 2(z13(k) + z31(k))d(xx2) + 2(4z22(k) − z44(k))d(x1/a) (C11)

ij

where x2 = a−1(1 − 4x2)−1. As both dF1 and G1 are functions of lc and σ (through a and α), y1 will turn out to be a function of parameter lc and σ,

y1 =

ij

zij(1) G1

dbij

=

![image 175](07_Bozovic_PRL2004_images/imageFile175.png)

dF1(lc, σ) G1(lc, σ)

![image 176](07_Bozovic_PRL2004_images/imageFile176.png)

(C12)

Proceeding similarly for yk k > 2, a solution for yk can be given as yk =

dbijzij(k) (C13)

ij

where z(k) satisfy the conditions Gk = 0

Note the condition G2 = 0 is satisﬁed for a following choice of z(2): z11(2) = −z33(2), z13(2) = −z31(2) and z22(2) = z44(2) = 0. The y2 for this choice turns out to be a constant. Similarly the condition G3 = 0 can be satisﬁed for a following choice of z(3): z

(3) 11 +z33(3)

2) (γa−4)−4(γa+1)x2

= 4x8−γa(1−4x

![image 177](07_Bozovic_PRL2004_images/imageFile177.png)

![image 178](07_Bozovic_PRL2004_images/imageFile178.png)

z13(3)−z31(3)

(3) 22

3x31(γ+ax1/32)

z44 = a

and z

64(γax1−16) . Using these z values in eq.(c13), one can obtain y3 as a function of σ and lc. Note although y3 varies with changing σ and lc, however ij fij ∂y

![image 179](07_Bozovic_PRL2004_images/imageFile179.png)

![image 180](07_Bozovic_PRL2004_images/imageFile180.png)

∂bij = 0 and therefore y3 does not aﬀect the evolution of ρ(H).

3

![image 181](07_Bozovic_PRL2004_images/imageFile181.png)

# REFERENCES

- [1] U.Sivan et al., Phys. Rev. Lett. 77, 1123 (1996).
- [2] S.R.Patel et al., Phys. Rev. Lett., 80, 4522 (1998); F.Simmel et al., Phys. Rev.B, 59, 10441 (1999); J.A.Folk et al., Phys. Rev. Lett. 86, 2102 (2001); S. Luscher et al., Phys. Rev. Lett., 77, 1123 (1996).
- [3] T.Guhr, G.A.Muller-Groeling and H.A. Weidenmuller, Phys. Rep. V299, 189, (1998).
- [4] V.M.Pudalov, M.D’Iorio, S.V.Kravchenko and J.W.Campbell, Phys. Rev. Lett. 70, 1866

(1993).

- [5] M.L.Mehta,Random Matrices, Academic Press, (1991);
- [6] F. Hakke,Quantum Signatures of Chaos, Springer (Berlin), (1991);
- [7] Y.Alhassid, Rev.Mod.Phys. 72, 895 (2000); A.D.Mirlin, Phys. Rep. 326, 259, (2000).
- [8] Y.Alhassid, Ph.Jaquod and A.Wobst, Phys.Rev. B, 61, R13357, (2000).
- [9] Ph.Jacquod and D.L.Shepelyansky, Phys.Rev.Lett. 79, 1837, (1997).
- [10] P.Shukla, Phys. Rev. E 62, 2098, 2000.
- [11] P.Shukla, J. Phys.: Condens. Matter 17, 1653 (2005).
- [12] A.Pandey, Chaos, Solitons and Fractals, 5, (1995).
- [13] B.Huckestein, Rev. Mod. Phys, 67, (1995).
- [14] R.Snedden,Elements of Partial Diﬀerential Equations, McGraw-Hill, (1988).
- [15] G.Murthy and H.Mathur, Phys. Rev. Lett., 89, 126804, 2002.
- [16] D.H.Dunlap, H.-L. Wu and P.W.Phillips, Phys. Rev. Lett. 65, 88 (1990); F.A.B.F. de Moura, M.L.Lyra, Phys. Rev. Lett., 81, 3725 (1998).


