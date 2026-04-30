arXiv:0806.4525v1[math.AP]27 Jun 2008

THE SECOND ITERATE FOR THE NAVIER-STOKES EQUATION

PIERRE GERMAIN

Abstract. We consider the iterative resolution scheme for the Navier-Stokes equation, and focus on the second iterate, more precisely on the map from the initial data to the second iterate at a given time t.

We investigate boundedness properties of this bilinear operator. This new approach yields very interesting results: a new perspective on Koch-Tataru solutions; a ﬁrst step towards weak strong uniqueness for Koch-Tataru solutions; and ﬁnally an instability result in B˙∞−1,q, for q > 2.

1. Introduction

- 1.1. The equation. The Cauchy problem for the Navier-Stokes equation reads

(NS)

∂tu − ∆u + P(u · ∇u) = 0 u|t=0 = u0 ,

where u is a function of (t,x) ∈ [0,∞) × Rd valued in Rd. We denote u · ∇ = ui∂i and P the Leray projector on divergence free vector ﬁelds, which is given on the Fourier side by (Pu)∧(ξ) = P(ξ)u(ξ),

with Pij(ξ) = 1 − ξ|ξiξ|2j . The initial data u0 is taken to be divergence free. This feature is conserved by the ﬂow of the above equation, namely u remains divergence free at any later time.

![image 1](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile1.png)

- 1.2. Iterative resolution of (NS). A natural way of solving the above system consists in setting up an iterative scheme: set u0 = 0 and for any n ≥ 1 let un solve


- (1)

∂tun − ∆un + P(un−1 · ∇un−1) = 0 (un)|t=0 = u0 ,

If the sequence (un) converges, the limit is, formally at least, a solution of (NS) with initial data u0. Observe that un − un−1 is an n-linear operator from the data space to the solution space; let us denote it Fn(u0 , ... , u0). Under appropriate convergence assumptions, one gets the following analytic expansion for the solution u

- (2) u =

∞

n=1

Fn(u0 , ... , u0) .

The question is now to show convergence of the above iterative scheme; this is naturally done using functional spaces which are invariant by the scaling associated to (NS)

- (3) u0(x) −→ λu0(λx) u(x,t) −→ λu(λx, λt) .


This approach has been developped since the seminal paper of Fujita and Kato [7] by (among others) Kato [7], Cannone [2], and ﬁnally Koch and Tataru [13]. These authors considered respectively data in the following scale-invariant spaces

d p

H˙ d2−1 ֒→ Ld ֒→ B˙ −1+

![image 2](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile2.png)

p,q ֒→ ∇BMO (with d < p < ∞ and d ≤ q ≤ ∞) .

![image 3](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile3.png)

Here we denoted B˙p,qs for the standard Besov space (see subsection 2.2), and ∇BMO for the space of derivatives of functions of BMO. It is believed that ∇BMO is the optimal space in which the above scheme can be implemented.

1

The space B˙∞−1,∞ is only a triﬂe larger than ∇BMO, and contains any space of tempered distributions whose norm is invariant by (3). It has been showed by Montgomery-Smith [16], for an equation similar to (NS), that the iterative scheme cannot be run in B˙∞−1,∞.

We prove in the present paper that the iterative scheme for (NS) cannot be used for u0 ∈ B˙∞−1,∞; namely one cannot deﬁne properly the second iterate.

- 1.3. L2 stability of solutions. Another approach to solving the above system is to use conservation of energy, and compactness arguments; one then obtains weak solutions in the energy class L∞([0,∞),L2)∩L2([0,∞),H˙ 1), ﬁrst constructed by Leray [15]. Is is not known in general whether these weak solutions are unique.


In order to prove uniqueness of a given solution w in the energy class, the weak-strong method essentially consists in proving L2 stability for (NS) around w. Due to the conservation of energy for (NS), this essentially reduces to L2 stability for the linearized equation around w. In other words, one needs to show that if w solves

the L2 norm of v, solution of

∂tw − ∆w + P(w · ∇w) = 0 w|t=0 = w0 ,

- (4)

∂tv − ∆v + P(v · ∇w + w · ∇v) = 0 v|t=0 = v0 ,

can be controlled by the L2 norm of v0 and some norm of w0.

Such an L2 stability result has been proved for w0 belonging to one of the spaces in the following hierarchy

- B˙ −1+


d p

![image 4](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile4.png)

p,q ֒→ B˙ −1+

d p

![image 5](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile5.png)

Lp,∞,q ֒→ B˙ −1+

d p

![image 6](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile6.png)

Mr,p,q ֒→ B˙ −1+

d p

![image 7](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile7.png)

M(H˙ d/p,L2),q with

2 q

![image 8](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile8.png)

+

d p

![image 9](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile9.png)

= 1 , 2 < r ≤ p and d < p < ∞ .

(we refer to Subsection 2.2 for a deﬁnition of the Besov spaces appearing above, and to the book of Lemarie´-Rieusset [14] for a deﬁnition of the Morrey spaces Mr,p and of the multiplier spaces M(H˙ d/q,L2)). The L2 stability results for w0 in the above spaces are due, respectively, to Prodi [17], Dubois [6] and Lemarie´-Rieusset [14]. The same result holds for w0 small in one of the spaces in the following hierarchy

Ld ֒→ Ld,∞ ֒→ Mr,d ֒→ M(H˙ 1,L2) with 2 < r ≤ d , this is due respectively to Von Wahl [19], Dubois [6] and Lemarie´-Rieusset [14].

All the mentioned results were obtained by the following method: take the scalar product with v of (4), and integrate in space and time. Optimal results using this method were obtained by the author [8] (it essentially consists of the spaces described above, with a broader range for p and q). Thus a new method is needed if one wants to improve on the results just mentioned.

This is our aim here to follow a diﬀerent approach. As in the previous subsection, we observe that v can be expanded into a series of multilinear operators

- (5) v =


∞

Gn(v0 , w0 ,... , w0) ,

n=0

where Gn(v0 , w0 ,... , w0) is linear in v0 and n-linear in w0. In this case though, a formula giving explicitly the (Gn) would have to be more complicated than in the previous subsection.

We prove in the following that the second term (ie n = 1) in the above expansion is bounded in L2

if v0 ∈ L2, w0 ∈ B˙∞0 ,∞. We shall extend this result in a forthcoming article, and prove weak-strong uniqueness for Koch-Tataru solutions, that is solutions corresponding to data in ∇BMO.

2. Harmonic analysis background We adopt the unitary normalization for the Fourier transform, thus

1 (2π)d/2

f(ξ) =

![image 10](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile10.png)

1 (2π)d/2

e−ixξf(x)dx and f(x) =

![image 11](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile11.png)

e−ixξf(ξ)dξ .

- 2.1. Littlewood-Paley decomposition. We deﬁne here the Littlewood-Paley operators, that will be of constant use in the following

To begin with, let us ﬁx a dyadic partition of unity. In order to do so, pick a smooth function ψ : R+ → R+ such that Suppψ is a subset of 34 ; 83 and

![image 12](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile12.png)

![image 13](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile13.png)

(6)

j∈Z

ψ

ξ 2j

![image 14](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile14.png)

= 1 for ξ > 0 .

Deﬁne the Fourier multipliers

∆N def= ψ |D|

![image 15](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile15.png)

2N ∆≤N def=

j≤N

ψ |D| 2j

![image 16](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile16.png)

∆≥N def=

j≥N

ψ |D| 2j

![image 17](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile17.png)

∆M≤·≤N def=

N

j=M

ψ |D| 2j

![image 18](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile18.png)

.

The two following identities hold (on any Lp, 1 ≤ p < ∞, and more generally on functional spaces which impose decay at inﬁnity)

j

∆j = Id and ∆≤0 +

j≥1

∆j = 1 .

- 2.2. Besov spaces. In this paragraph, we quickly deﬁne Besov spaces, and refer to the book of Lemarie´-Rieusset [14] for further information. Then we study the embedding properties of ∇BMO and B˙∞−1,p.


If (s,q) ∈ R × [1,∞] × [1,∞] and E is a Banach space, the Besov space B˙E,qs is the space given by the norm

 

 

1/q

def= 2js ∆jf E ℓq

2jsq ∆jf qE

=

f B˙s

E,q

j

j∈Z

(with the usual modiﬁcation of the ℓq norms in case the index is inﬁnite). This is a Banach space under appropriate conditions on E, s and q.

In case E is the Lebesgue space Lp, with 1 ≤ p ≤ ∞, we simpy denote B˙p,qs for B˙E,qs . Thus

 

 

1/q

def= 2js ∆jf Lp

2jsq ∆jf qLp

=

f B˙s

x ℓqj

p,q

j∈Z

In particular,

 

 

1/q

2−jq ∆jf q∞

2−j ∆jf ∞ .

=

= sup

for 1 < q < ∞, and f B˙−1

f B˙−1

∞,q

∞,∞

j∈Z

j∈Z

Lemma 1. The following embeddings hold B˙∞−1,q ֒→ B˙∞−1,r if q ≤ r B˙∞−1,2 ֒→ ∇BMO ֒→ B˙∞−1,∞ .

Proof: The ﬁrst embedding follows immediately from the deﬁnition of Besov spaces. The second embedding can be seen as an immediate consequence of the following equivalent characterization of the norms of B˙∞−1,2 and BMO

∞

et∆f 2∞ dt

∼

f B˙−1

∞,2

0

- (7)


R2

1 Rd

|(et∆f)(y)|2 dy dt .

f ∇BMO ∼ sup x,R

![image 19](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile19.png)

0 B(x,R)

As for the last embedding, it follows from the equivalent characterization of B˙∞−1,∞ f B˙−1

√

t et∆f L∞ f ∇BMO (the proof of the above equivalences can be found in the book of Lemarie´-Rieusset [14]).

![image 20](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile20.png)

∼ sup

∞,∞

t>0

3. Main result Computing explicitly the two ﬁrst terms of the expansion (2) yields

t

es(|ξ|2−|η|2−|ξ−η|2) (u0(η) · (ξ − η)u0(ξ − η)) dη ds + ... . For the expansion (5), one gets

u(t,ξ) = e−t|ξ|2u0(ξ) + P(ξ)e−t|ξ|2

0

v(t,ξ) = e−t|ξ|2v0(ξ)

+ P(ξ)e−t|ξ|2

+ ... .

0

t

es(|ξ|2−|η|2−|ξ−η|2) (v0(η) · (ξ − η)w0(ξ − η) + w0(η) · (ξ − η)v0(ξ − η)) dη ds

Our aim is to study the boundedness properties of the bilinear terms appearing in the above expressions. By scaling, it suﬃces to consider the case t = 1. Thus we are interested in the boundedness properties of T1, T2 given by

- (T1(f,g))∧ (ξ) def= P(ξ)e−|ξ|2

1

0

es(|ξ|2−|η|2−|ξ−η|2) f(η) · (ξ − η)g(ξ − η) dη ds .

- (T2(f,g))∧ (ξ) def=


1

P(ξ)e−|ξ|2

es(|ξ|2−|η|2−|ξ−η|2) f(η) · (ξ − η)g(ξ − η) + g(η) · (ξ − η)f(ξ − η) dη ds ,

0

where f, g, as well as Ti(f,g) are divergence free maps from Rd to Rd.

- Theorem 1. (We denote in the statement of this theorem Eσ for divergence free vector ﬁelds in the Banach space E. In the following, we shall drop the subscript σ to make notations lighter.)


- (i) The operator T2 is bounded from B˙∞−1,∞


× L2 σ to L2 σ.

σ

- (ii) The operator T1 is bounded from (∇BMO)σ × (∇BMO)σ to (∇L∞)σ.
- (iii) The operator T1 is not bounded from B˙∞−1,q σ


× B˙∞−1,q

to S′ if q > 2. This is the case even if one restricts T1 to the diagonal (f,f) ∈ B˙∞−1,q

σ

× B˙∞−1,q

. What does the above theorem mean for the PDE problems evoked in the introduction?

σ

σ

- • Point (i) of the theorem is a ﬁrst step towards weak-strong uniqueness for the Koch-Tataru

solutions; or in other words, towards proving that if the data u0 belongs to ∇BMO ∩ L2, then the solution to (NS) is unique in the energy class. We will address this question in a forthcoming article.

- • Point (ii) of the theorem says that the second iterate of (1) belongs to L∞([0,∞),∇L∞)

if u0 ∈ ∇BMO. This is not proving the existence of a solution for such data (theorem of Koch and Tataru), but we believe it does provide interesting insight: it corresponds to the frequency approach, whereas Koch and Tataru’s proof is done in physical space. Notice that the regularity of the bilinear term, L∞∇L∞, is slightly better than that of the linear term, L∞∇BMO.

- • Point (iii) proves that the iteration scheme cannot be used to build up solutions associated to data in B˙∞−1,q, if q > 2. This is not quite an ill-posedness result, but it says that the map which associates to the data a solution of (NS) cannot be of class C2 from B˙∞−1,q to S′.


We would like to mention here the article of Germain, Masmoudi and Shatah [9]. It somehow corresponds to the dispersive equation version of the approach followed here for (NS), in particular in the use which is made of bilinear operators. The essential diﬀerence between these two settings is that (space-time) resonances, which are the key to understanding global existence for dispersive equations, are not so relevant for a dissipative equation.

Finally, we learned after completion of the present work from J. Bourgain and N. Pavlovicˇ that they have just ﬁnished the proof of an ill-posedness result for the Navier-Stokes equation in the spaces B˙∞−1,q, with q > 2.

4. Bilinear operators

Before proceeding with the proof of Theorem 1, let us recall some classical facts about bilinear operators.

The pseudo-product operator B associated to the symbol m(ξ,η) is deﬁned by

(Bm(f,g))∧ (ξ) =

m(ξ,η)f(η)g(ξ − η)dη .

Rd

Under appropriate conditions, these bilinear operators enjoy the same bounds as the ones given by H¨older’s inequality for the standard multiplication. This is the content of the celebrated theorem of Coifman and Meyer.

- Theorem 2 (Coifman-Meyer [4] [12] [10]). If the symbol m satisﬁes for suﬃciently many derivatives


- (8) |∂ξα∂ηβm(ξ,η)|


then the associated operator is bounded Bm : Lp × Lq −→ Lr with

1 p

+

![image 21](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile21.png)

1 (|ξ| + |η|)|α|+|β|

,

![image 22](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile22.png)

1 q

1 r

=

, 1 < p,q ≤ ∞ , 1 ≤ r < ∞ .

![image 23](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile23.png)

![image 24](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile24.png)

Unfortunately, the above theorem misses the endpoint (∞,∞,∞). This shortcoming can be overcome by strengthening the conditions on m.

Proposition 2. Suppose the symbol m satisﬁes

m, (∇ξ,η)d+1 m ∈ L2ξ,η . Then Tm is bounded from L∞ × L∞ to L∞.

Proof: Notice ﬁrst that, if M denotes the inverse Fourier transform (in ξ and η) of m, then Bm(f,g) = M(x − z , x + z − y)f(y)g(z)dy dz . Furthermore, under the assumptions of the proposition, M ∈ L1.

5. Proof of (i) in Theorem 1

- 5.1. Reduction of the problem. First, it is possible to simplify a little the problem by observing that


- • Since we are dealing with divergence free functions, it is possible to replace in the deﬁnition of T1 and T2 ξ − η by ξ.
- • One can forget the Leray projector at the beginning of the expression of T2, since it reduces to Riesz projections, which are bounded on the spaces of interest for us.
- • The vectorial nature of the functions f and g in the deﬁnition of T2 will not play any role. Thus we replace f and g by scalar functions.
- • A function in B˙∞−1,∞ can be written di=1 ∂ifi, with fi in B˙∞0 ,∞.


The above considerations show that the boundedness of T2 : B˙∞−1,∞ × L2 −→ L2 is implied by the following

- Claim 1. If ℓ1 and ℓ2 are linear functions, the operator Bµ with symbol


µ(ξ,η) = e−|ξ|2ℓ1(η)ℓ2(ξ)

is bounded from B˙∞0 ,∞ × L2 to L2.

1

es(|ξ|2−|η|2−|ξ−η|2) ds

0

The idea of the proof of this claim is to decompose the (ξ,η) plane into three regions, by picking three smooth functions χ1, χ2 and χ3 of (ξ,η) such that

- χ1 + χ2 + χ3 = 1

- Supp(χ1) ⊂ {|ξ| + |η| ≤ 2}
- Supp(χ2) ⊂ {|ξ| + |η| ≥ 1, |ξ| ≥

1 6|η|}

![image 25](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile25.png)

- Supp(χ3) ⊂ {|ξ| + |η| ≥ 1, |ξ| ≤


1 5|η|}

![image 26](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile26.png)

- χ2 and χ3 homogeneous of degree 0 for |ξ| + |η| ≥ 3


Now let us deﬁne Bµ1, Bµ2 and Bµ3 by their symbols

µi(ξ,η) def= χi(ξ,η)µ(ξ,η) . Then obviously µ1 + µ2 + µ3 = µ.

In the following subsections, we prove the boundedness of Bµ1, Bµ2 and Bµ3 from B˙∞0 ,∞ ×L2 to L2. Since Bµ = Bµ1 + Bµ2 + Bµ3, this shall prove the claim, hence part (i) of Theorem 1.

- 5.2. The region where |ξ| + |η| 1: boundedness of Bµ1 : B˙∞0 ,∞ × L2 → L2. It is clear that

∆≤1ℓ1(D) : B˙∞0 ,∞ −→ L∞ is bounded . We also observe that the symbol

µ1(ξ,η)(ℓ1(η))−1 = e−|ξ|2χ1(ξ,η)ℓ2(ξ)

1

0

es(|ξ|2−|η|2−|ξ−η|2) ds

satisﬁes the conditions of Theorem 2 (it actually even belongs to C0∞). Thus one can estimate Bµ1(f,g) 2 = Bµ1(∆≤1f , g) 2

= Bµ1(ξ,η)(ℓ1(η))−1 ∆≤1ℓ1(D)f , g 2 ∆≤1ℓ1(D)f ∞ g 2 f B˙0

∞,∞

g 2 .

- 5.3. The region where |ξ| + |η| 1 and |ξ| |η|: boundedness of Bµ2 : B˙∞0 ,∞ × L2 → L2. On the one hand,

∆≥−1e1001 ∆ : B˙∞0 ,∞ −→ L∞ is bounded . On the other hand, the symbol

![image 27](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile27.png)

µ2(ξ,η)e1001 |η|2 = e1001 |η|2e−|ξ|2χ2(ξ,η)ℓ2(ξ)ℓ1(η)

![image 28](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile28.png)

![image 29](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile29.png)

1

0

es(|ξ|2−|η|2−|ξ−η|2) ds

satisﬁes the conditions of Theorem 2. Indeed, any derivative of this symbol decays like an inverse exponential of |ξ|2 + |η|2. Let us see quickly how such a decay estimate can be obtained for µ2(ξ,η)e1001 |η|2, and it will become clear that the same holds for any derivative. Using ﬁrst that |ξ|2 − |η|2 − |ξ − η|2 ≤ 12|ξ|2, and then that on the support of χ2, |ξ| ≥ 16|η|, we have

![image 30](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile30.png)

![image 31](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile31.png)

![image 32](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile32.png)

|µ2(ξ,η)e1001 |η|2| ≤ e1001 |η|2e−21|ξ|2χ2(ξ,η)|ℓ1(η)ℓ2(ξ)| ≤ e−101 |ξ|2χ2(ξ,η)|ℓ1(η)ℓ2(ξ)| e−10001 (|ξ|2+|η|2) . Thus we can estimate

![image 33](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile33.png)

![image 34](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile34.png)

![image 35](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile35.png)

![image 36](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile36.png)

![image 37](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile37.png)

Bµ2(f,g) 2 = Bµ2(∆≥−1f , g) 2

= Bµ

2(ξ,η)e1001 |η|2 ∆≥−1e1001 ∆f , g

![image 38](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile38.png)

![image 39](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile39.png)

2 ∆≥−1e1001 ∆f

![image 40](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile40.png)

∞

g 2 f B˙0

∞,∞

g 2 .

- 5.4. Further reﬁnement in the region where |ξ| + |η| 1 and |ξ| << |η|. In this region, which essentially corresponds to the support of χ3, the idea is to integrate out in time and get


ℓ2(ξ)ℓ1(η) |ξ2| − |η|2 − |ξ − η|2

µ3(ξ,η) = χ3(ξ,η)

![image 41](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile41.png)

Thus we can decompose

e−|ξ−η|2−|η|2 − e−|ξ|2 .

µ3(ξ,η) = µ′3(ξ,η) − µ′′3(ξ,η) where

2(ξ)ℓ1(η)

µ′3(ξ,η) = χ3(ξ,η) ℓ

|ξ2|−|η|2−|ξ−η|2e−|ξ−η|2−|η|2 µ′′3(ξ,η) = χ3(ξ,η) ℓ

![image 42](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile42.png)

2(ξ)ℓ1(η)

|ξ2|−|η|2−|ξ−η|2e−|ξ|2 .

![image 43](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile43.png)

- 5.5. Boundedness of Bµ′

3

: B˙∞0 ,∞ × L2 → L2. Observing that

µ′3(ξ,η)e|η|2 = χ3(ξ,η)

ℓ2(ξ)ℓ1(η) |ξ2| − |η|2 − |ξ − η|2

![image 44](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile44.png)

e−|ξ−η|2 satisﬁes the conditions of Theorem 1, we can easily estimate

Bµ′

3

(f,g) 2 = Bµ′

3

(∆≥−1f , g) 2

= Bµ′

3e|η|2(∆≥−1e∆f , g) 2 ∆≥−1e∆f ∞ g 2 f B˙0

∞,∞

g 2 .

- 5.6. Boundedness of Bµ′′


: B˙∞0 ,∞ × L2 → L2. Observe that the symbol

3

µ′′3(ξ,η)|η| = χ3(ξ,η)ℓ2(ξ)e−|ξ|2 |η|ℓ1(η)

1 |η| satisﬁes the conditions of Theorem 2. Using furthermore that

![image 45](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile45.png)

![image 46](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile46.png)

|ξ2| − |η|2 − |ξ − η|2

1 |D|

: B˙∞0 ,∞ → L∞ is bounded, we can estimate

∆≥−1

![image 47](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile47.png)

(f,g) 2 = Bµ′

(∆≥−1f , g) 2

Bµ′′

3

3

1 |D|

f , g) 2

= Bµ′′

3|η|(∆≥−1

![image 48](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile48.png)

1 |D|

∆≥−1

f ∞ g 2 f B˙0

![image 49](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile49.png)

g 2 .

∞,∞

6. Proof of (ii) in Theorem 1

The proof of point (ii) is similar to that of point (i). For this reason, we only sketch it, but emphasize the modiﬁcations that need to be done.

- 6.1. Reduction of the problem. As in subsection 5.1, we observe that the boundedness of T1 : ∇BMO × ∇BMO −→ ∇L∞ is implied by the


- Claim 2. If ℓ1 and ℓ2 are linear functions, the operator Bν with symbol


1

es(|ξ|2−|η|2−|ξ−η|2) ds is bounded from BMO × BMO to L∞.

ν(ξ,η) = e−|ξ|2ℓ1(η)ℓ2(ξ − η)

0

As in subsection 5.1, let us deﬁne Bν1, Bν2 and Bν3 by their symbols

νi(ξ,η) def= χi(ξ,η)ν(ξ,η) . Then obviously ν1 + ν2 + ν3 = ν.

In the following subsections, we prove the boundedness of Bν1, Bν2 and Bν3 from BMO ×BMO to L∞.

- 6.2. The region where |ξ|+|η| 1: boundedness of Bν1 : BMO ×BMO → L∞. We proceed as in subsection 5.2, using that

∆≤1ℓ1(D) : BMO −→ L∞ is bounded , and then Proposition 2 instead of Theorem 2.

- 6.3. The region where |ξ|+|η| 1 and |ξ| |η|: boundedness of Bν2 : BMO×BMO → L∞. We proceed as in subsection 5.3, using that

∆≥−1e1001 ∆ : BMO −→ L∞ is bounded . and then Proposition 2 instead of Theorem 2.

![image 50](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile50.png)

- 6.4. Further reﬁnement in the region where |ξ| + |η| 1 and |ξ| << |η|. We integrate out in time and get

ν3(ξ,η) = χ3(ξ,η)

ℓ1(η)ℓ2(ξ − η) |ξ|2 − |η|2 − |ξ − η|2

![image 51](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile51.png)

e−|ξ−η|2−|η|2 − e−|ξ|2 . Thus we can decompose

ν3(ξ,η) = ν3′(ξ,η) − ν3′′(ξ,η) where

ν3′(ξ,η) = χ3(ξ,η) ℓ

1(η)ℓ2(ξ−η)

![image 52](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile52.png)

|ξ2|−|η|2−|ξ−η|2e−|ξ−η|2−|η|2 ν3′′(ξ,η) = χ3(ξ,η) ℓ

1(η)ℓ2(ξ−η)

![image 53](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile53.png)

|ξ2|−|η|2−|ξ−η|2e−|ξ|2 .

- 6.5. Boundedness of Bν′


: BMO × BMO → L∞. Let us further decompose

3

ℓ1(η)ℓ2(ξ − η) |ξ2| − |η|2 − |ξ − η|2 as

N(ξ,η) def= χ3(ξ,η)

![image 54](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile54.png)

∞

∞

ψ |η| 2j

Nj(ξ,η) def=

N(ξ,η) =

N(ξ,η)

![image 55](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile55.png)

j=1

j=1

(recall that ψ is deﬁned in (6)). Observe that N1 satisﬁes the hypotheses of Proposition 2, hence BN1 : L∞ × L∞ −→ L∞ is bounded. By scaling, the BNj : L∞ × L∞ −→ L∞ are uniformly bounded.

, we need the following lemma from Chemin [2]. Lemma 3. There exists a constant c such that

To prove boundedness of Bν′

3

et∆∆jf ∞ e−c22j ∆jf ∞ . We can conclude:

(f,g) ∞ = BN(e∆f,e∆g) ∞ ≤

Bν′

3

∞

BNj(∆j−1≤·≤j+1e∆f,∆j−1≤·≤j+1e∆g) ∞

j=0

∞

∆j−1≤·≤j+1e∆f ∞ ∆j−1≤·≤j+1e∆g ∞

j=0

∞

e−c22j ∆j−1≤·≤j+1f ∞ ∆j−1≤·≤j+1g ∞ f BMO g BMO .

j=0

: BMO ×BMO → L∞. An important feature of the symbol ν3′′ is that it only allows frequency interactions of the type “high - high gives low”. Examining a little more this symbol, it becomes clear that Bν′′

- 6.6. Boundedness of Bν′′


3

can be written -up to an easily estimated operator-

3

(f,g) = e∆

Bαj(∆jf,∆jg) ,

Bν′′

3

j≥−1, |j−k|≤1

where α belongs to C0∞ and αj(ξ,η) = α 2ξj , 2ηj (to make notations lighter, we consider in the following that j = k).

![image 56](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile56.png)

![image 57](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile57.png)

Expanding α in Fourier series, we see that for some constant c depending on the support of α, α(ξ,η) =

λm,neic(mη+n(ξ−η)) .

m,n∈Zd

This implies that Bν′′

(f,g)(x) = e∆

λm,n∆jf(x + c2−jm)∆jg(x + c2−jn) .

3

j≥−1 m,n∈Zd

We can assume that the norms of f and g in BMO are comparable. Taking advantage of the strong decay of the kernel associated to e∆, we can estimate

e∆

λm,n∆jf(x + c2−jm)∆jg(x + c2−jn)

j≥−1 m,n∈Zd

∆jf(x + c2−jm)∆jg(x + c2−jn)

λm,n

supx∈Rd

j≥−1

m,n∈Zd

L1(B(x,1))

 

  dx .

∆jf(x + c2−jm) 2 + ∆jg(x + c2−jn) 2

λm,n

supx∈Rd

B(x,1)

j≥−1

m,n∈Zd

Using the following characterization of the norm of BMO, which is essentially a rephrasing of (7),

- 1

![image 58](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile58.png)

- 2Jd B(x,2J) j≥−J


|∆jf|2 dx .

f BMO = sup

J∈Z, x∈Rd

yields now

λm,n∆jf(x + c2−jm)∆jg(x + c2−jn)

e∆

j≥−1 m,n∈Zd

λm,n(|m| + 1)d(|n| + 1)d f BMO g BMO

m,n∈Zd

f BMO g BMO where we used in the last inequality the rapid decay of the (λm,n).

7. Proof of (iii) in Theorem 1 If q > 2, we want to build up a counterexample to boundedness of T2 : B˙∞−1,q × B˙∞−1,q −→ S′ .

- 7.1. Idea behind the counterexample. Examining the analysis performed in the preceding section, it appears that if one excludes the region |ξ| + |η| 1, |ξ| << |η|, the operator T2 :


B˙∞−1,∞ × B˙∞−1,∞ → ∇L∞ is bounded.

Thus our example should generate a “high - high gives low” frequency interaction, which becomes unbounded.

This insight is actually the only use that we shall make of the preceding analysis: the counterexample will be otherwise self-contained.

 

 

 , e2 =

 ,

1 0 0

- 0
- 1 0


- 7.2. The counterexample. For simplicity, we set d = 3 and pick e1 =


 

  an orthonormal basis of R3. We shall denote × the vector product.

0

- 0
- 1


e3 =

Next, let φ be a smooth, even, non-negative (real-valued) function on Rd, such that φ = 1 on

B(0,2) and φ = 0 outside of B(0,3). Also let (αk) be a sequence in ℓq \ℓ2. Deﬁne fN by its Fourier transform

N

N

fN(ξ) =

fk,+(ξ) −

fk,−(ξ)

k=10

k=10

N

N

ξ |ξ|

ξ |ξ|

def=

2kαkφ(ξ + 2ke1)

2kαkφ(ξ − 2ke1)

× e2 −

× e2 .

![image 59](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile59.png)

![image 60](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile60.png)

k=10

k=10

It is clear that fN is real-valued, divergence-free, and uniformly bounded (with respect to N) in B˙∞−1,q. Remark. Let us pause for a moment and make two observations

- • First, notice that the above sequence is very similar to the one used by MontgomerySmith [16] to prove the result mentioned in the introduction, namely that for a Navier-Stokes like equation the iterative resolution method does not work for data in B˙∞−1,∞. This is also

very similar to the example used by Stein [18] to prove that symbols in S10,1 are not in general associated to operators which are bounded on L2. Thus, as Montgomery-Smith puts it, it might be that the non-boundedness result which we are about to prove “says more about the nature of the B˙∞−1,∞ space than about the Navier-Stokes equation itself”.

- • Second, we believe it is very instructive to relate the instability result for the data fN that we will momentarily prove - to a result proved by Chemin and Gallagher [3]. These


authors build up data which are large in B˙∞−1,∞ but still yield global solutions of the NavierStokes equation. These data have the following peculiarity: the diﬀerent scales are physically separated, in other words the oscillations at diﬀerent scales occur at diﬀerent places; this is ensured by a fractal like transformation. This is to be contrasted with the (fN) for which oscillations at all scales occur at the same location.

From now on, we ﬁx

  thus P(ξ0) =

  .

 

 

1 0 0 0 12 −21 0 −12

- 0
- 1

![image 61](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile61.png)

- 2


ξ0 def=

![image 62](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile62.png)

![image 63](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile63.png)

- 1

![image 64](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile64.png)

- 2


- 1

![image 65](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile65.png)

- 2


![image 66](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile66.png)

An important and elementary observation is that the only possible interaction of fN with itself yielding this frequency ξ0 corresponds to fk,± interacting with fk,∓.

This observation, along with performing the time integral in the deﬁnition of T1, yields

1 − e|ξ0|2−|η|2−|ξ0−η|2 |ξ0|2 − |η|2 − |ξ0 − η|2

ξ0 − η |ξ0 − η|

η |η|

T1(fN,fN)∧(ξ0) = P(ξ0)e−|ξ0|2

× e2 N

× e2

ξ0 ·

![image 67](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile67.png)

![image 68](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile68.png)

![image 69](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile69.png)

α2k22kφ(η − 2ke1)φ(ξ0 − η + 2ke1)dη

k=10

1 − e|ξ0|2−|η|2−|ξ0−η|2 |ξ0|2 − |η|2 − |ξ0 − η|2

ξ0 − η |ξ0 − η|

η |η|

+P(ξ0)e−|ξ0|2

× e2 N

ξ0 ·

× e2

![image 70](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile70.png)

![image 71](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile71.png)

![image 72](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile72.png)

α2k22kφ(η + 2ke1)φ(ξ0 − η − 2ke1)dη

k=10

or, reorganizing things a little,

T1(fN,fN)∧(ξ0) = e−|ξ0|2φ(η)φ(ξ0 − η)

N

22k(1 − e|ξ0|2−|η+2ke1|2−|ξ0−η−2ke1|2) |ξ0|2 − |η + 2ke1|2 − |ξ0 − η − 2ke1|2

α2k

![image 73](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile73.png)

k=10

ξ0 − η − 2ke1 |ξ0 − η − 2ke1|

η + 2ke1 |η + 2ke1|

× e2

× e2

P(ξ0) ξ0 ·

![image 74](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile74.png)

![image 75](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile75.png)

N

22k(1 − e|ξ0|2−|η+2ke1|2−|ξ0−η−2ke1|2) |ξ0|2 − |η − 2ke1|2 − |ξ0 − η + 2ke1|2

α2k

+

![image 76](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile76.png)

k=10

η − 2ke1 |η − 2ke1|

ξ0 − η + 2ke1 |ξ0 − η + 2ke1|

P(ξ0) ξ0 ·

× e2 dη It is easily seen that if η ∈ Suppφ, and k ≥ 10

× e2

![image 77](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile77.png)

![image 78](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile78.png)

 

  ⊗

 

 

0

0

22k(1 − e|ξ0|2−|η+2ke1|2−|ξ0−η−2ke1|2) |ξ0|2 − |η + 2ke1|2 − |ξ0 − η − 2ke1|2

ξ0 − η − 2ke1 |ξ0 − η − 2ke1|

η + 2ke1 |η + 2ke1|

- 1

![image 79](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile79.png)

- 2


- 0
- 1


- 0
- 1


× e2 ∼ −

× e2

![image 80](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile80.png)

![image 81](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile81.png)

![image 82](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile82.png)

  .

 

  ⊗

 

0

0

22k(1 − e|ξ0|2−|η+2ke1|2−|ξ0−η−2ke1|2) |ξ0|2 − |η − 2ke1|2 − |ξ0 − η + 2ke1|2

η − 2ke1 |η − 2ke1|

ξ0 − η + 2ke1 |ξ0 − η + 2ke1|

- 1

![image 83](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile83.png)

- 2


- 0
- 1


- 0
- 1


× e2

× e2 ∼ −

![image 84](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile84.png)

![image 85](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile85.png)

![image 86](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile86.png)

We conclude that if η ∈ Suppφ, and k ≥ 10

 

 

- 0
- 1 8 −18


22k(1 − e|ξ0|2−|η+2ke1|2−|ξ0−η−2ke1|2) |ξ0|2 − |η + 2ke1|2 − |ξ0 − η − 2ke1|2

η + 2ke1 |η + 2ke1|

ξ0 − η − 2ke1 |ξ0 − η − 2ke1|

× e2

× e2 ∼

P(ξ0) ξ0 ·

![image 87](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile87.png)

![image 88](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile88.png)

![image 89](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile89.png)

![image 90](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile90.png)

![image 91](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile91.png)

 

  .

- 0
- 1 8 −18


22k(1 − e|ξ0|2−|η+2ke1|2−|ξ0−η−2ke1|2) |ξ0|2 − |η − 2ke1|2 − |ξ0 − η + 2ke1|2

ξ0 − η + 2ke1 |ξ0 − η + 2ke1|

η − 2ke1 |η − 2ke1|

× e2 ∼

× e2

P(ξ0) ξ0 ·

![image 92](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile92.png)

![image 93](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile93.png)

![image 94](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile94.png)

![image 95](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile95.png)

![image 96](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile96.png)

Integrating over η and taking advantage of the positivity of φ, we see that there exists a constant

- C = 0 such that


 

  ,

- 0
- 1 −1


N

α2k

T1(fN,fN)∧(ξ0) ∼ C

k=1

and in particular

N

T1(fN,fN)∧ 3 (ξ0)

α2k .

k=1

 

 , and obtain that, uniformly in

- 0
- 1

![image 97](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile97.png)

- 2


We can run the same argument in a neighbourhood of ξ0 =

- 1

![image 98](09_Gozar_Interface-SC-Metal-Mott_Nature2008_images/imageFile98.png)

- 2


ζ ∈ B (ξ0 , ǫ), for ǫ small enough,

N

T1(fN,fN)∧ 3 (ζ)

α2k .

k=10

The series in the right hand side diverges. Thus, in spite of the boundedness of fN in B˙∞−1,q, the Fourier transform of T1(fN,fN) is, on B (ξ0 , ǫ), larger than a diverging sequence. This means that T1(fN,fN) is not bounded in S′.

References

- [1] Cannone, Marco, Ondelettes, paraproduits et Navier-Stokes. With a preface by Yves Meyer. Diderot Editeur, Paris, 1995.
- [2] Chemin, Jean-Yves, Th´eor`emes d’unicit´e pour le syst`eme de Navier-Stokes tridimensionnel. J. Anal. Math. 77

(1999), 27–50

- [3] Chemin, Jean-Yves; Gallagher, Isabelle, Wellposedness and stability results for the Navier-Stokes equations in R3, to appear in Annales de l’Institut H. Poincar, Analyse non Linaire.
- [4] Coifman, Ronald; Meyer, Yves, Au del`a des op´erateurs pseudo-diﬀ´erentiels. Aste´risque 57 Socie´te´ Mathe´matique de France, Paris, 1978
- [5] David, Guy; Journe´, Jean-Lin, A boundedness criterion for generalized Caldern-Zygmund operators. Ann. of Math. (2) 120 (1984), no. 2, 371–397
- [6] Dubois, Sandrine, Uniqueness for some Leray-Hopf solutions to the Navier-Stokes equations. J. Diﬀerential Equations 189 (2003), no. 1, 99–147
- [7] Fujita, Hiroshi; Kato, Tosio, On the Navier-Stokes initial value problem. I. Arch. Rational Mech. Anal. 16 1964 269–315
- [8] Germain, Pierre, Multipliers, paramultipliers, and weak-strong uniqueness for the Navier-Stokes equations. J. Diﬀerential Equations 226 (2006), no. 2, 373–428.
- [9] Germain, Pierre; Masmoudi, Nader; Shatah, Jalal, Global solutions for 3D quadratic Schr¨odinger equations, submitted
- [10] Grafakos, Loukas; Torres Rodolfo, Multilinear Calder´n-Zygmund theory., Adv. Math. 165 (2002), no. 1, 124–164
- [11] Kato, Tosio, Strong Lp-solutions of the Navier-Stokes equation in Rm, with applications to weak solutions. Math. Z. 187 (1984), no. 4, 471–480
- [12] Kenig, Carlos; Stein Elias, Multilinear estimates and fractional integration. Math. Res. Lett. 6 (1999), no. 1, 1–15
- [13] Koch, Herbert; Tataru, Daniel, Well-posedness for the Navier-Stokes equations. Adv. Math. 157 (2001), no. 1, 22–35
- [14] Lemarie´-Rieusset, Pierre-Gilles, Recent developments in the Navier-Stokes problem. Chapman & Hall/CRC Research Notes in Mathematics, 431. Chapman & Hall/CRC, Boca Raton, FL, 2002
- [15] Leray, Jean, Sur le mouvement d’un liquide visqueux emplissant l’espace. Acta Math. 63 (1934), no. 1, 193–248
- [16] Montgomery-Smith, Stephen, Finite time blow up for a Navier-Stokes like equation. Proc. Amer. Math. Soc. 129 (2001), no. 10, 3025–3029
- [17] Prodi, Giovanni, Un teorema di unicita` per le equazioni di Navier-Stokes. Ann. Mat. Pura Appl. (4) 48 1959 173–182
- [18] Stein, Elias M., Harmonic analysis: real-variable methods, orthogonality, and oscillatory integrals. With the assistance of Timothy S. Murphy. Princeton Mathematical Series, 43. Monographs in Harmonic Analysis, III. Princeton University Press, Princeton, NJ, 1993
- [19] von Wahl, Wolf, The equations of Navier-Stokes and abstract parabolic equations. Aspects of Mathematics, E8. Friedr. Vieweg & Sohn, Braunschweig, 1985


