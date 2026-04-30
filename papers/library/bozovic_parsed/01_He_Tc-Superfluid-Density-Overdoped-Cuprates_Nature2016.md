# arXiv:1608.03566v3[physics.flu-dyn]15 Apr 2017

## A collision model for grain-resolving simulations of ﬂows over dense, mobile, polydisperse granular sediment beds

##### Edward Biegert1,a, Bernhard Vowinckel2,a, Eckart Meiburg3,a

aDepartment of Mechanical Engineering, University of California, Santa Barbara, CA, USA

#### Abstract

We present a collision model for phase-resolved Direct Numerical Simulations of sediment transport that couple the ﬂuid and particles by the Immersed Boundary Method. Typically, a contact model for these types of simulations comprises a lubrication force for particles in close proximity to another solid object, a normal contact force to prevent particles from overlapping, and a tangential contact force to account for friction. Our model extends the work of previous authors to improve upon the time integration scheme to obtain consistent results for particle-wall collisions. Furthermore, we account for polydisperse spherical particles and introduce new criteria to account for enduring contact, which occurs in many sediment transport situations. This is done without using arbitrary values for physically-deﬁned parameters and by maintaining the full momentum balance of a particle in enduring contact. We validate our model against several test cases for binary particle-wall collisions as well as the collective motion of a sediment bed sheared by a viscous ﬂow, yielding satisfactory agreement with experimental data by various authors.

Keywords: Direct Numerical Simulations, Immersed Boundary Method, contact modeling, particle-laden ﬂow, sediment transport

1ebiegert@engineering.ucsb.edu 2vowinckel@engineering.ucsb.edu 3meiburg@engineering.ucsb.edu

Preprint submitted to Journal of Computational Physics September 30, 2018

c 2017. This manuscript version is made available under the CC-BY-NC-ND 4.0 license http: // creativecommons. org/ licenses/ by-nc-nd/ 4. 0/

#### 1. Introduction

The ﬂow over dense, mobile granular beds plays a central role in multiple applications in environmental, mechanical, and process engineering. Prime examples of this type of problem are turbidity currents and powder snow avalanches (Meiburg and Kneller, 2010), for which resuspension of particles essentially determines the dynamics of the ﬂow. The resuspension threshold is quantiﬁed by the ratio of hydrodynamic drag and lift forces to the weight of the particles, known as the Shields number (Shields, 1936). The critical Shields parameter, however, has proven to be a poor predictor for the onset of particle erosion (Garcia, 2008), and substantial eﬀorts have been made in hydraulic engineering to overcome this diﬃculty (Seminara, 2010). To date, progress has been slow due to the experimental diﬃculty of measuring dense particle-laden ﬂows in a laboratory. In recent years, numerical simulations have provided an alternative way to study ﬂuid-particle interactions under these complex conditions. In particular, the Direct Numerical Simulation (DNS) of particle-laden ﬂows using the Immersed Boundary Method (IBM) has become a very attractive option. A main advantage of this approach is that it allows for a fully-coupled system by accounting for particle-ﬂuid, ﬂuid-particle, and particle-particle interactions. While coupling between the particle and the ﬂuid can be realized by a straightforward implementation of an IBM, particle-particle coupling has to be modeled by suitable expressions for the collision processes involved.

A number of diﬀerent phase-resolving methods to simulate mobile particles in a viscous ﬂow have been developed in the past two decades. Glowinski et al. (1999) and Patankar et al. (2000) developed a Distributed Lagrange Multiplier (DLM)/ﬁctitious domain approach that forces the ﬂuid throughout the volume of the particle to move in a rigid body motion with the particle. While this method was designed for a ﬁnite element framework, Kajishima et al. (2001) and Apte et al. (2009) later developed diﬀerent versions to be used in a ﬁnite diﬀerence framework. More recently, other methods that enforce the no-slip condition on the particle surface have been developed. Zhang and Prosperetti

(2005) developed PHYSALIS, which uses the analytical solution for Stokes ﬂow around a sphere. Uhlmann (2005) developed an IBM that enforces the no-slip condition using interpolation and spreading operations via Dirac delta functions. Kempe and Fr¨hlich (2012b) extended this method to make it stable for a larger range of particle/ﬂuid density ratios. Although there exists a variety of phaseresolving methods, the choice of collision models, on the other hand, has not been as diverse. Derksen (2011) and Derksen (2015) used a hard-sphere model, which resolves collisions instantaneously. Glowinski et al. (1999) have developed a repulsive potential (RP) model that prevents particles from overlapping by applying a repulsive force at some small distance before the particles come in contact. Many other authors have adopted this model for simulations involving dilute suspensions of particles. For example, Uhlmann (2008) and Santarelli and Fro¨hlich (2015) investigated particles in a vertical turbulent channel ﬂow, Lucci et al. (2010) studied the impact of ﬁnite size particles on isotropic turbulence, and Breugem (2012) and Picano et al. (2015) have presented results for a horizontal ﬂow laden with neutrally-buoyant particles. In these simulations, particles rarely came in contact, and thus were successfully governed mostly by the IBM, using the repulsive potential only to prevent overlap.

For the situation involving shear ﬂow over a densely-packed sediment bed, however, particle-particle contact becomes ubiquitous (Balachandar and Eaton, 2010). Hard sphere models cannot maintain simultaneous collisions or enduring contacts between multiple interacting particles, but instead represent sediment beds as particles in constant, minute motion (Derksen, 2015). However, they have been used to reproduce critical erosion conditions for a laminar shear ﬂow (Derksen, 2011). The drawbacks of the RP model for the situation of sediment transport have been clearly-elaborated by Kempe et al. (2014). Using the RP in the framework of the IBM introduces an artiﬁcial gap of two times the grid cell size between colliding particles so that the ﬂuid in the gap between the particle surfaces can still be resolved (Glowinski et al., 2001). For the situation of sediment transport, however, the artiﬁcial gap also introduces an unphysical protrusion of the particles into the horizontal ﬂow, which is critical as the

protrusion has been acknowledged to be a very sensitive parameter for particle mobilization (Fenton and Abbott, 1977). In addition, the RP model introduces a material stiﬀness kn which has to be calculated a priori to design a collision model that is numerically stable. If the value of kn is chosen too high, the repulsive force is overestimated and the particle would experience an unphysical high rebound velocity. On the other hand, if kn is too low, the duration of the particle collision would be too large. The resuspension mechanisms, however, generate a high variety of particle impact velocities uin for the collisions, typically characterized by the nondimensional Stokes number St = ρpuinDp/(9ρf νf), where ρp and ρf are the particle and ﬂuid density, respectively, Dp is the particle diameter, and νf is the kinematic viscosity of the ﬂuid. In fact, for bed-load transport in water the variety can span from St 10 (saltating particles, Ni˜no and Garcı´a, 1998) to St = O(10) (rolling particles, Lajeunesse et al., 2010) to St 1 (enduring contact within the sediment bed). Hence, selecting a stiﬀness that is stable for high-impact velocities results in excessively low stiﬀnesses within the bed, which acts as an unphysical dampening of the system.

Although there are studies of particle-laden horizontal ﬂows such as Shao

- et al. (2012) and Kidanemariam et al. (2013) in which the model by Glowinski et al. (1999) has been employed, these had to be limited to small volume fractions and conclusions about particle-particle interaction have not been possible. Kidanemariam and Uhlmann (2014) used an improved repulsive linear springdashpot model that solves the issues with calibrating kn, but still relies on an artiﬁcial gap distance. Thus, in order to obtain appropriate bulk sediment transport quantities, they calibrated the dry restitution coeﬃcient edry = −uout/uin, where uout is the rebound velocity as soon as the collision process is ﬁnished, although this parameter can be set exactly as a material property. It describes the dissipation of kinetic energy due to the inelastic mechanics of the dry contact and is typically in the range of 0.8 ≤ edry < 1 for silicate materials (e.g. Joseph et al., 2001). In the study of Kidanemariam and Uhlmann (2014), a rather unphysical value of edry = 0.3 was used to match the bulk transport rates of glass spheres from the experiments of Aussillous et al. (2013).


More recently, a more consistent approach has been advocated in the literature for which the artiﬁcial gap size is no longer needed (Simeonov and Calantoni, 2012; Kempe and Fr¨hlich, 2012a; Izard et al., 2014; Costa et al., 2015; Sierakowski and Prosperetti, 2016). This approach uses a lubrication force when the particles come in close contact (0 < ζn ≤ 2h, where ζn is the distance between the two surfaces), and a contact force when the surfaces come in contact and slightly overlap (ζn ≤ 0). The lubrication force, which is based on lubrication theory, models the ﬂuid forces acting on the particle that cannot be resolved by the computational mesh. The contact force models material deformations and friction through components that are, respectively, normal and tangent to the surface. Since these models attempt to address the actual physics of the collision, they have had much success in reproducing the desired restitution coeﬃcients over a range of Stokes numbers for the experiments by Joseph et al. (2001). Simeonov and Calantoni (2012) performed a detailed analysis breaking down the individual eﬀects from lubrication forces, contact forces, and hydrodynamic forces. However, only Kempe and Fr¨hlich (2012a) and Costa et al. (2015) have demonstrated that their models were able to reproduce the trajectories of a particle-wall impact provided by the benchmark experiments of Gondret et al. (2002). Both studies show that the good agreement with the rebound trajectories is made possible by slightly stretching the collision process in time: long enough to resolve the response of the ﬂuid ﬁeld to the particle kinematics but shorter than any relevant physical timescale in the ﬂow. In addition, both modeling approaches use an adaptive procedure to obtain mathematically-rigorous solutions to the ordinary diﬀerential equations governing particle motion during contact. Using the model of Kempe and Fro¨hlich (2012a), a breakthrough was achieved by Vowinckel et al. (2014), who successfully carried out numerical simulations of turbulent horizontal channel ﬂow laden with tens of thousands of particles.

In the present work, we build on the model proposed by Kempe and Fr¨hlich (2012a) to extend it to situations of very dense packing fractions. For example, in order for their collision model to work as designed, Kempe and Fr¨hlich

(2012a) neglect the hydrodynamic forces acting on a particle while it is in contact with another object. This was addressed implicilty by Kempe et al. (2014), even though it was not stated in their paper, by including the hydrodynamic forces in the equation of motion regardless of the type of collision (Kempe & Fr¨hlich, 2016, private communication). Furthermore, their model for the tangential contact force, which is designed to exactly enforce zero slip between particles, does not converge to a steady-state conﬁguration for enduring contact. While this model worked well for simulations involving thin beds of particles at higher Reynolds numbers and Stokes numbers, we would like to extend it to work for thick beds of particles at a range of diﬀerent Stokes numbers. At this point, models from the Discrete Element Method (DEM) community, who simulate dry granular ﬂows, seem to be more appropriate, as they introduce a “memory” of the friction required to reach steady-state conditions (Zhu et al., 2008). Costa et al. (2015) proposed a scheme with an enhanced treatment of lubrication forces, which can also be applied to smaller Stokes numbers as well as a variety of impact angles ψin. In this reference, however, they neither considered the situation of enduring contact nor conducted a validation on a larger scale addressing the collective eﬀects of particle motion.

Finally, another aspect that has received far less attention so far is the situation of a sediment consisting of particles with varying particle diameters. Interestingly, all of the references cited so far deal with spherical monodisperse particles. To the knowledge of the authors the only study considering horizontal channel ﬂows laden with polydisperse sediment has been performed by Fukuoka et al. (2014) using a front-tracking technique, but neither did the authors account for the feedback of the particles on the ﬂow nor have they provided a validation for the experimental standard benchmark test cases such as particles settling in an ambient ﬂuid or colliding with a wall. The absence of studies addressing polydisperse sediment with fully coupled IBM simulations is ever the more surprising, since its impact has been acknowledged as a key issue in the development and evolution of bedforms by segregation eﬀects as reviewed by Charru et al. (2013).

As a consequence, the present work aims to resolve the problems mentioned above. Among the key challenges identiﬁed are i) deriving collision models for polydisperse sediment, ii) avoiding the introduction of an artiﬁcial gap between colliding particles, iii) adaptively-calibrating the particle stiﬀness to simulate a wide range of Stokes numbers in a consistent manner, iv) introducing suitable criteria to extend existing models towards the numerically-challenging situation of enduring contact for both normal and oblique collisions, and v) minimizing the number of tunable parameters within the model framework. We achieve our goals by presenting an implementation of collision models for polydisperse sediment. We use the adaptive procedure proposed by Kempe and Fr¨hlich

- (2012a) for normal forces and the tangential model of Thornton et al. (2013), which stems from DEM. Furthermore, we extend both of these approaches for the situation of enduring contact. In particular, for enduring contact, we took care to retain all the governing terms of the momentum balance of a particle, i.e. hydrodynamic forces, buoyant weight, and collision forces. This measure turns out to be crucial when simulating ﬂows over sediment beds, as the Shields parameter is based on the ratio of hydrodynamic to buoyant forces. The proposed enhancements allow us to reproduce several laboratory benchmark test cases for binary collisions. In addition, we present a detailed validation of our simulation results with wall-normal proﬁles of the ﬂuid and particle velocities

- as well as bulk ﬂow quantities using the experimental data of Aussillous et al.


- (2013). The paper is structured as follows. We brieﬂy recall the numerical method,


including the ﬂuid solver, IBM, and the structure of the collision model, in Section 2, followed by the mathematical description of the collision model employed in Section 3. We then present necessary enhancements to the collision model to deal with small Stokes numbers (Section 4) and to simulate dense granular packings with the gross of the particles in enduring contact (Section 5). Subsequently, the enhanced model is validated for the collective motion of polydisperse sediment sheared by a laminar ﬂow in Section 6.

#### 2. Particle motion and four-way coupling in the framework of theImmersed Boundary Method

- 2.1. Fluid solver For the present simulations, we solve the unsteady Navier-Stokes equations


for an incompressible Newtonian ﬂuid, given by

∂u ∂t

1

ρf ∇p + νf∇2u + fIBM , (1) and the continuity equation, given by

+ ∇ · (uu) = −

∇ · u = 0 , (2)

on a uniform rectangular grid with grid cell size ∆x = ∆y = ∆z = h. Here, u = (u,v,w)T designates the ﬂuid velocity vector in Cartesian components,

- p the pressure, νf the kinematic viscosity, t the time, and fIBM an artiﬁcial volume force introduced by the IBM (Mittal and Iaccarino, 2005). This volume force, which acts on the right-hand side of (1) in the vicinity of the interphase boundaries, connects the motion of the particles to the ﬂuid phase. The transfer of quantities, such as force and velocity, between Eulerian points and Lagrangian points, i.e. between ﬂuid points of the regular background grid and points on the surface of the particle, is performed by interpolation and spreading operations via a weighted sum of regularized Dirac delta functions (Uhlmann, 2005), of which we use the 3-point stencil function of Roma et al. (1999). The source term fIBM is computed in such a way that the no-slip condition at the particle surface is satisﬁed. Time advancement is achieved by a fractional step method, a third-order explicit low-storage three-step Runge-Kutta (RK) scheme is employed for the convective terms, and a second-order semi-implicit CrankNicolson scheme is used for the viscous terms (Fadlun et al., 2000), which are solved with the conjugate-gradient method. Spatial derivatives are evaluated using second-order central-diﬀerencing. The pressure is treated with a direct solver based on Fast Fourier Transformations (FFT). Our code can handle a


variety of boundary conditions at the diﬀerent walls, including no-slip, slip, periodic, and inﬂow/outﬂow.

- 2.2. Computation of particle motion Within the framework of the IBM, we calculate the motion of each individual


spherical particle by solving an ordinary diﬀerential equation for its translational velocity up = (up,vp,wp)T

dup dt

mp

=

τ · n dA

##### +Vp (ρp − ρf) g

+Fc,p , (3)

Γp

=Fg,p

=Fh,p

and its angular velocity ωp = (ωp,x,ωp,y,ωp,z)T

dωp dt

=

Ip

r × (τ · n) dA

+Tc,p . (4)

Γp

=Th,p

Here, mp is the particle mass, Γp the ﬂuid-particle interface, τ the hydrodynamic stress tensor, ρp the particle density, Vp the particle volume, g the gravitational acceleration, Ip = 8πρpRp5/15 the moment of inertia, and Rp the particle radius. Furthermore, the vector n is the outward-pointing normal on the interface Γp, r = x−xp is the position vector of the surface point with respect to the center of mass xp of a particle, and Fc,p and Tc,p are the force and torque due to particle collisions, respectively. Furthermore, note the designation of the hydrodynamic force and torque as Fh,p and Th,p, respectively, as well as Fg,p the force due to gravity, which will be used in the following for brevity.

We employ the approach of Kempe and Fr¨hlich (2012b) for evaluating the IBM forces and solving (3) and (4). We validated the ﬂuid-particle coupling of the method against experimental data of a sphere settling in an unbounded quiescent ﬂuid (Mordant and Pinton, 2000) as well as towards a wall (Ten Cate et al., 2002). The particle was initially at rest for both setups and accelerated downwards due to gravity. For the unbounded case, the particle reached a constant terminal velocity u∞. The Reynolds number Rep = u∞Dp/νf based on this settling velocity is Rep = 41. For the wall-bounded case, the particle

0.0

0.00

|Mordant & Pinton<br><br>Present|
|---|


|ten Cate et al.<br><br>Present|
|---|


##### a) b)

- -1.2

- -1.0

- -0.8

- -0.6

- -0.4

- -0.2


- -0.25

- -0.20

- -0.15

- -0.10

- -0.05


###### v/vref

v/vref

0 5 10 15 20 25 30 35 40

0 10 20 30 40 50

t/tref

t/tref

- Figure 1: Comparison of the present numerical method against experimental data with vref = gDp and tref = Dp/g. a) Settling sphere in an inﬁnite medium at Rep = 41 (Mordant and Pinton, 2000) and b) settling sphere in a wall-bounded medium at Rep = 12 (Ten Cate et al., 2002).


reached a terminal velocity but then decelerated as it approached the wall. For now, we only consider the particle motion before impact, which is governed by the IBM. The collision model governing the impact will be described and validated further below in the text. The Reynolds number based on the velocity before deceleration is Rep = 12. In both cases, the particle was discretized with 20 grid cells per diameter. The respective data are plotted in Figure 1, showing excellent agreement.

- 2.3. Structure of the collision model As mentioned in the introduction, one of the major advantages of the IBM


is the direct computation of long-range interactions between the particles. Only short-range interactions and collisions need to be modeled. For example, consider a particle approaching and colliding with a wall, as shown in Figure 2. As the particle comes close to the wall, two problems need to be dealt with: ﬁrst, the smoothed Dirac delta functions used for the IBM overlap with the wall, and second, the discrete mesh can no longer resolve the ﬂuid being squeezed out from between the two surfaces.

We can solve the ﬁrst problem by disabling Lagrangian marker points whose supports overlap with the wall (red dashed circle in Figure 2a), as was done

##### a) b)

| | | | | | | | | | | | | |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| | | | | | | | | | | | | |
| | | | | | | | | | | | | |
| | | | | | | | | | | | | |
| | | | | | | | | | | | | |
| | | | | | | | | | | | | |
| | | | | | | | | | | | | |
| | | | | | | | | | | | | |
| | | | | | | | | | | | | |
| | | | | | | | | | | | | |
| | | | | | | | | | | | | |
| | | | | | | | | | | | | |
| | | | | | | | | | | | | |


- Figure 2: Regions where short-range interactions occur. Points on particle surface represent Lagrangian markers. Red markers have been turned oﬀ. a) Lubrication region where red dashed circle illustrates support of Dirac delta function and b) Contact region.


by Kempe and Fr¨hlich (2012b). This means that the forcing by these select markers on both the ﬂuid and the particles is ignored, preventing the particle from using undeﬁned information from outside of the domain and from competing with the wall for enforcing the no-slip condition. Figure 2 illustrates the red markers that have been disabled. Similarly, overlapping markers between two particles are disabled. We solve the second problem by adding a lubrication force, which models the subgrid forces on the particle due to the narrow gap and also accounts for some of the ﬂuid forces from the disabled Lagrangian markers. We apply this force when the particle-wall distance is less than two grid cells (0 < ζn ≤ 2h), illustrated by the blue region in Figure 2a. Once the particle comes into contact with the wall (ζn ≤ 0), we apply a contact force to prevent particles from overlapping too much and to account for proper momentum transfer and energy loss. This contact force involves components both normal and tangent to the two surfaces, representing material deformations and friction, respectively.

Hence, the following case distinctions can be made for the normal collision

- Figure 3: Sketch of polydisperse particles in a mobile granular bed and the resulting interactions due to collisions.


forces

 

0 ζn > 2h lubrication model (9) 0 < ζn ≤ 2h normal contact model (10) ζn ≤ 0

(5)

Fn =



and the tangential collision forces

 

0 ζn > 0 tangential contact model (14) ζn ≤ 0 .

Ft =

(6)



The interactions of a single particle with its environment, however, are in general more diverse. Let us consider a particle p embedded in a mobile granular bed of polydisperse, spherical particles (Figure 3). The dynamics of this particle are mainly determined by all the collision forces exerted upon it by particles q,q = p as well as the wall. The total force Fc,p acting on a particle p during the collision process may be decomposed as

Fc,p =

Np

(Fn,q + Ft,q) + Fn,w + Ft,w , (7)

q, q=p

where Np is the number of particles simulated, Fn,q and Fn,w are the normal collision forces described by (5) with particle q and the wall, respectively, and

Ft,q and Ft,w are the tangential collision forces described by (6) with particle

- q and the wall, respectively. In what follows, the mathematical expressions are formulated for both particle-wall and particle-particle collisions, where the radii of the two colliding particles can be arbitrary. Whenever a distinction between particle-wall and particle-particle has to be made, a reference to Appendix A is given for brevity, providing all deﬁnitions and nomenclature needed to distinguish between the two diﬀerent cases.


The torque Tc,p on a spherical particle p generated by the tangential contact forces is

Np

Rp,cp n p,q × Ft,q + Rp,cp n p,w × Ft,w (8)

Tc,p =

q, q=p

where n p,q and n p,w are the unit vectors pointing to the collision partner q or the wall, respectively, and Rp,cp is the particle radius at the contact point as deﬁned per Appendix A in (A.6), which accounts for surface overlap. In the next section, we will provide the mathematical description of the models used in the present study.

#### 3. Collision modeling

- 3.1. Lubrication model When the distance between the surfaces of two approaching particles be-


comes small, the ﬂuid is squeezed out of the gap. The ﬂuid grid cannot resolve this process as soon as ζn < 2h, where h is the grid cell size. Hence, we employ a lubrication model, which also acts on particles rebounding after the collision, when ﬂuid is drawn into the gap. The lubrication force is dissipative, since it is always directed opposite to the relative velocity. The model is based on the analytical derivation of Cox and Brenner (1967), who solved for the force under Stokes ﬂow conditions

6πρfνfReﬀ2 max(ζn,ζn,min)

Fn = −

gn,cp , (9)

where Reﬀ is the eﬀective radius accounting for polydisperse sediment and gn,cp the normal component of the relative particle velocity as deﬁned per Appendix

A in (A.1) and (A.9) respectively. The original model scales as 1/ζn which introduces a singularity as ζn → 0. This has been addressed by Simeonov and Calantoni (2012) and Kempe and Fr¨hlich (2012a), who set Fn = 0 for 0 < ζn < ζn,min, and Izard et al. (2014), who have shifted the denominator of (9) to ζn + ζn,min. In the present approach, as in the approach of Costa et al. (2015), lubrication forces are held constant as soon as the gap size becomes smaller than the critical value ζn,min, which provides a continuous forcing on the particles when they are close to sustained contact. This parameter can be interpreted as the micro-texture of the particle surface, which acts as a surface roughness, as will be discussed further in Section 4.4 below.

- 3.2. Normal contact model To account for normal contact forces, we implemented the Adaptive Collision


Time Model (ACTM) proposed by Kempe and Fr¨hlich (2012a). The main idea of the ACTM is to use an adaptive procedure to obtain the desired restitution coeﬃcient edry and to resolve the collision on the timescale of the ﬂuid solver. The ACTM is based on a nonlinear spring-dashpot system

Fn = −kn|ζn|3/2n − dngn,cp , (10)

which involves empirical parameters for the coeﬃcients of stiﬀness kn and damping dn. Here, n is the normal vector pointing either towards the collision partner or towards the wall as deﬁned per Appendix A in (A.3). The nonlinear term |ζn|3/2 arises from Hertzian contact theory (Hertz, 1882).

Since the timescale of a collision according to Hertzian contact theory is several orders of magnitude smaller than the typical temporal discretization of the ﬂuid solver, the collision event has to be stretched in time to maintain the eﬃciency of the numerical procedure. This measure is also needed for the ﬂuid to adapt to the sudden change in the particle trajectory (Kempe and Fro¨hlich, 2012a; Costa et al., 2015). However, the duration of contact Tc is mainly determined by the stiﬀness parameter kn. This becomes of particular importance for the complex situation of bed-load transport, where a broad range

of impact velocities is encountered, ranging from high-impact collisions at the top of the bed to enduring contact within the bed.

The ACTM ﬁxes this problem by adaptively calibrating the parameters kn and dn depending on the impact velocity uin, the desired restitution coeﬃcient edry, and the desired collision time Tc. The latter is a parameter of the model and should be minimized to avoid excessive particle overlaps and temporal stretching. Kempe and Fr¨hlich (2012a) demonstrated that Tc = 10∆t is a suitable choice for the collision time given that all timescales related to ﬂuid and particle motion are signiﬁcantly larger than the timescale of particle contact. For glass and hard metals, edry = 0.97 is a typical value (e.g Foerster et al., 1994; Joseph et al., 2001; Gondret et al., 2002). For immersed collisions, the restitution coeﬃcient ewet, measured some small distance away from the wall, becomes a function of the Stokes number (Joseph et al., 2001). The ACTM, however, uses the IBM and lubrication model to account for ewet through additional dissipative ﬂuid eﬀects.

In order to ﬁnd values for kn and dn, we ﬁrst neglect all non-contact forces acting on the particle so that (3) and (10) together give the following nonlinear ordinary diﬀerential equation:

d2ζn dt2

dζn dt

+ knζn3/2 = 0 , (11)

meﬀ

+ dn

where meﬀ is the eﬀective mass accounting for polydisperse sediment as deﬁned per Appendix A in (A.2). Note that dζn/dt = −gn,cp·n. Together with (11) and initial and ﬁnal conditions, the constraints edry and Tc allow for determination of kn and dn using either an iterative procedure, as was done by Kempe and Fro¨hlich (2012a), or an explicit formulation, as was proposed by Ray et al. (2015). In the present study, we implemented the explicit formulation, which is provided in Appendix B. According to Ray et al. (2015), the error in uout increases with decreasing edry, but does not exceed 1.3% for edry > 0.7 or 3% for edry > 0.4, making this method useful for most sediment materials such as silicate, glass, or even metal.

- 3.3. Tangential collision model To account for frictional contact between the particles, we implemented a


tangential contact model based on the linear spring-dashpot model described in the review paper of Thornton et al. (2013):

Ft,LS = −ktζt − dtgt,cp , (12) which has stiﬀness and damping coeﬃcients kt and dt. This model uses gt,cp, the tangential component of the relative surface velocities as described in (A.10) of Appendix A, as well as ζt, the tangential spring displacement, which represents the accumulated relative tangential motion between the two surfaces:

ζt =

t

gt,cp(t )dt , (13)

ti

where ti is the time of impact. The discretized form of (13) is described in Appendix C.

This model limits the maximum force based on Coulomb’s friction criterion:

Ft = min(||Ft,LS||,||µFn||)t , (14) where µ represents the coeﬃcient of friction between the two surfaces (described further in Section 5.3) and t = Ft,LS/||Ft,LS|| points in the direction of the tangential force.

This model has two important features for simulating densely-packed beds. First, the spring allows many particles to interact in a smooth, stable manner, provided the stiﬀness is chosen properly. Second, the model has a memory of the friction force via the tangential displacement ζt, which permits a steady-state frictional bed conﬁguration. In contrast, a model that only uses gt,cp, such as the one proposed by Kempe and Fr¨hlich (2012a), can only react to slip, not predict it.

Similarly to the ACTM, we can adaptively compute kt and dt for each collision. According to Thornton et al. (2011), the stiﬀness can be set to

κmeﬀ π2 Tc2

kt =

. (15)

Here, κ is based on Poisson’s ratio ν:

2(1 − ν) 2 − ν

κ =

, (16)

which is a well-studied material property typically ranging between 0.22 < ν < 0.30 (e.g Foerster et al., 1994; Gondret et al., 2002; Joseph and Hunt, 2004). Hence, a value of ν = 0.22 was used in the present study.

In addition, the damping is computed according to Thornton et al. (2013) to account for the inelasticity of the collisions

dt = 2 meﬀ kt −lnedry π2 + ln2edry

. (17)

Having created a uniform collision time Tc with the normal contact model, we obtain the correct rebound characteristics for oblique impacts using these values for kt and dt, as shown in Section 5.3. Consistently, the model does not require any calibration but instead can be parameterized using material properties obtained from experiments.

#### 4. Enhancements to the normal contact model

- 4.1. Motivation In order to obtain a good agreement with immersed collision experiments, we


had to implement a few enhancements to the normal contact model described in Section 3.2. Both changing the time integration to a scheme of higher accuracy and adding more timesteps to the integration of particle motion without changing the ﬂuid timestep allowed us to reproduce the collision trajectories of Gondret et al. (2002) in a robust manner.

- 4.2. Improved time integration


The ACTM normal contact force Fc,p is a function of the surface distance ζn and the relative velocity gn,cp, which in turn depend on the particle position xkp−1 and velocity upk−1 at the previous substep k − 1. We can write

this functional dependence as Fc,p(xkp−1,ukp−1). Integrating the particle equation of motion with a Forward Euler/Crank Nicholson scheme for the particle’s velocity/position, we obtain:

2∆tαk mp

ukp = ukp−1 +

Fc,p xkp−1, ukp−1 (18a) xkp = xpk−1 + ∆tαk ukp + ukp−1 , (18b)

where k is the number of the RK-substep and αk is the RK-coeﬃcient (Rai and Moin, 1991). For now, we ignore the hydrodynamic, gravitational, and lubrication forces in order to focus on the contact forces alone. We conducted a simple test to analyze the accuracy of this scheme. A particle of density ρp/ρf = 7.8 and with radius Rp = 10u∞∆t was initialized with a velocity of up = (0,u∞,0)T

- at a position yp > Rp above a wall at y = 0. Subsequently, the particle was released and eventually collided with the wall. Neglecting hydrodynamic effects as well as gravity yields an impact velocity of uin/u∞ = 1. Choosing the collision time to be Tc = 10∆t as suggested by Kempe and Fr¨hlich (2012a), gave good results for the duration of the desired contact phase Tc, but rather large errors of the rebound velocity were observed compared to the prescribed edry = 1. The value of uout = −edry uin was overestimated by more than 12%.


Turning our attention to Figure 4, we can see that the discretization of (18) leads to a poor estimation of the collision force ||Fc,p|| when compared to the simulation in which 104 timesteps were used to resolve the collision, which can be taken as the exact solution. This inaccuracy in the collision force was observed for a variety of simulations using diﬀerent Rp, ρp, uin, and edry. In order to reduce the error to 0.1%, a temporal discretization of Tc = 1000∆t would be required, which is not feasible for simulations of sediment transport. Hence, we implemented a temporal discretization scheme with a higher order of accuracy. Utilizing the same three-step RK scheme that integrates the NavierStokes equations, we reformulated the collision integration with a predictor-

corrector scheme:

∆t mp

γkFc,p xkp−1, ukp−1 + ζkFc,p xkp−2, ukp−2 (19a) xp = xkp−1 + ∆tαk up + upk−1 (19b) ukp = ukp−1 +

up = ukp−1 +

∆tαk mp

Fc,p (xp, up) + Fc,p xpk−1, upk−1 (19c)

xkp = xkp−1 + ∆tαk ukp + ukp−1 . (19d) Here, tilde indicates predicted values, and γk and ζk are the RK coeﬃcients for the explicit third-order scheme according to Rai and Moin (1991). Hence, the velocity predictor step (19a) is third-order accurate while the other steps use second-order Crank-Nicholson schemes. A similar approach was taken by Costa et al. (2015), but in this reference, the predicted value is determined by an iterative scheme, which is computationally more costly than the present scheme. In Figure 4 we can see that this predictor-corrector scheme yields a much better approximation of ||Fc,p|| compared to the Forward Euler method, reducing the error of uout by almost two orders of magnitude to 0.17% for Tc/∆t = 10. For completeness, we have also included a solution that uses the Backward Euler method, which underestimates the rebound velocity by 11%. This improvement has been achieved by a minimal increase of the computational costs, as the most expensive part of (3) is the computation of the hydrodynamic forces Fh,p.

- 4.3. Temporal substepping Having improved the accuracy of the contact model, we carried out simu-


lations of particle-wall collisions in a ﬂuid to compare to the experiments of Gondret et al. (2002). The details of the simulations, including the material properties as well as the physical and numerical parameters, are summarized in Table 1. Gondret et al. (2002) released particles from heights large enough to accelerate to their terminal velocities before colliding with the wall. For these simulations, the horizontal wall and vertical particle trajectories allow us to only consider normal collision forces. To control the impact velocity uin, we accelerated the particle in the numerical simulations according to the relation

u(t) = uin e−40t − 1 , ζn > Rp . (20)

|Exact solution Forward Euler Backward Euler<br><br>Predictor-corrector|
|---|


14

12

10

||||Fc

8

6

4

2

0

0.000 0.002 0.004 0.006 0.008 0.010 0.012 0.014

t

- Figure 4: Collision forces vs. time for Forward Euler, Backward Euler, and predictorcorrector schemes.


In other words, we prescribed the falling velocity of the particle so that it accelerated in a smooth manner so that uin matched the Stokes number reported in Gondret et al. (2002) as shown in Table 1. Two scenarios were considered: one with a rather high Stokes number St = 152 and one with a lower Stokes number of St = 27, the latter of which is within the range of Stokes numbers that have been reported for the numerical simulations of Kempe et al. (2014). Once the particle reached a distance of ζn = Rp, we turned oﬀ the prescribed velocity, allowing the particle to move on its own volition according to the hydrodynamic, buoyant, and collision forces acting on it.

While attempting to reproduce the experimental trajectories, the simulations produced large variations in the results from small changes to the initial conditions. To show this, we executed ﬁve simulations for St = 27, varying only the initial position of the particle y0 from the value recorded in Table 1 within the interval of one grid cell h. Figure 5a shows the range of trajectories encountered. For St = 27, a substantial variation in the rebound height of up to 83% can be observed. We would thus expect the collision model to produce a variety of incorrect trajectories for the simulation of sediment transport in a horizontal channel ﬂow. Even the mean of the variety of trajectories is not able

St 27 152 Rep 30 164 Rp (m) 0.003 0.0015 uin (m/s) 0.518 0.585 ρp/ρf 8.083 8.342 νf (m2/s) 1.036 × 10−4 1.070 × 10−5 edry 0.97 0.97 g (m/s2) 9.81 9.81 Domain size (m) (Lx × Ly × Lz) 0.08 × 0.16 × 0.08 0.02 × 0.2 × 0.02 Domain boundary conditions p × ns × p p × ns × p Initial position of sphere center (m) 0.075 0.197 Grid cells in x-direction 256 128 Grid cells per diameter 19 19 Timestep ∆t = 2.5e-4 ∆t = 8.9e-5

Table 1: Simulation parameters to match the experiments of Gondret et al. (2002). Boundary conditions can be periodic (p), slip (s), or no-slip (ns).

to fully reproduce the experimental trajectory.

To better understand the observed variability, we plot the time evolution of the collision forces, i.e. lubrication and contact forces, for the low Stokes number case St = 27 in Figure 6. In this plot, we can see the particle approaching the wall with the lubrication force growing as 1/ζn (phase I). Subsequently, the lubrication forces become zero during the contact phase starting at t/tref = −0.1. During this phase (phase II), the contact force grows and then decays with the particle-wall overlap as the particle changes direction to rebound. Finally, the particle experiences the lubrication force again during the rebound phase starting at t/tref = 0 (phase III). At this time, lubrication is acting in the opposite direction because lubrication is dissipative. The dotted line in Figure 6 shows the forces acting on the particle for a time discretization based on CFL = 0.5 for the settling velocity. As expected, the normal contact model with the

##### a) b)

0.7

0.7

|Gondret et al.<br><br>Mean<br><br>Bounds|
|---|


|Gondret et al.<br><br>Mean<br><br>Bounds|
|---|


0.6

0.6

0.5

0.5

0.4

0.4

###### ζ/Dnp

ζ/Dnp

0.3

0.3

0.2

0.2

0.1

0.1

0.0

0.0

−0.1

−0.1

−0.5 0.0 0.5 1.0 1.5 2.0 2.5

−0.5 0.0 0.5 1.0 1.5 2.0 2.5

t/tref

t/tref

- Figure 5: Sensitivity of rebound trajectories to initial position y0 for St = 27. a) Trajectories computed without particle substeps and b) trajectories computed with particle substeps.


modiﬁcations described in Section 4.2 above is able to give a smooth evolution of contact forces with the time step size of the ﬂuid solver. However, it turns out that the lubrication forces remain under-resolved during approach and rebound, especially as ζn approaches zero directly before and after the contact phase. This leads to either more or less total impulse acting on the particle, depending on where the timestep happens to land, which in turn results in variability between simulations. This eﬀect strongly depends on the Stokes number, since the lubrication force decreases with increasing St. Hence, the ratio of the normal contact force to the lubrication force increases when approaching dry contact conditions.

Since the lubrication model used is an algebraic relation that does not depend on the surrounding hydrodynamics, we have implemented a substepping method that integrates the particle motion with smaller timesteps than the ﬂuid motion. This method works as follows:

- 1. We solve the ﬂuid equations of motion, IBM, and hydrodynamic forces acting on the particle as normal.
- 2. We divide the ﬂuid RK substep k into a number of substeps Nsub,k = {8,2,5}. This choice results in a total of 15 substeps of constant size per ﬂuid timestep (∆tsub = ∆t/15), which is most eﬃcient since 2αk =


100

I II III

50

F/Wbuoy

0

−50

With substeps

Without substeps

−100

−0.12 −0.10 −0.08 −0.06 −0.04 −0.02 0.00 0.02

t/tref

- Figure 6: Collision forces acting on the particle at St = 27 including: the lubrication force during approach (phase I), the normal force during contact (phase II), and the lubrication force during rebound (phase III). Vertical dashed lines indicate a change in phase. Wbuoy = (1 − ρf/ρp)mp g is the buoyant weight of the particle.


{8/15,2/15,5/15} as used in (19).

- 3. For each of the substeps, we solve the particle equations of motion with the three-step RK method. As we update the particle velocities and positions, we re-evaluate the collision (lubrication and contact) forces, but the hydrodynamic forces remain constant. This compromise makes the present approach very eﬃcient.
- 4. At the end of the 8, 2, or 5 substeps, we use the ﬁnal particle position and velocity for the next ﬂuid RK substep.


This measure eﬀectively increases the resolution of a collision to a timestep 15 times smaller than the ﬂuid timestep to integrate particle motion, allowing us to compute the lubrication forces with higher accuracy. Since the contact duration of Tc = 10∆t is maintained, the contact phase is now resolved with a total of 150 timesteps with only a marginal increase to the computational cost. Substepping has also been used by Kidanemariam and Uhlmann (2014) and Costa et al.

- (2015) but the authors did not illustrate the variability we have observed for the trajectories of particle-wall collisions. Meanwhile, Kidanemariam and Uhlmann


- (2014) do not provide a comparison with the data of Gondret et al. (2002) at all. The scheme presented by Costa et al. (2015) still relies on an iterative procedure subdividing every ﬂuid timestep into 50 substeps, which is less eﬃcient than the scheme presented here. The results of our approach can be appreciated in Figure 6. The solid line, which was resolved with ﬁfteen times more timesteps, can be viewed as a better approximation of the exact solution to the model we have implemented. Figure 5b shows how this method almost eliminates the variability in the rebound trajectories of the particle-wall collisions discussed above.


- 4.4. Choice of particle surface roughness As shown in Figure 5, the improved integration scheme described in Sections


- 4.2 and 4.3 yields excellent results in reproducing the rebound trajectory of the St = 27 experiment of Gondret et al. (2002). Having obtained consistent results that are insensitive to the initial condition, we can use the same setup of particle-wall collisions to select the most suitable surface roughness ζn,min for the lubrication model (9). This is the only parameter involved that requires calibration as an inverse problem. However, the range of values that can be assigned to ζn,min should neither fall below the surface roughness of the actual simulated particle nor exceed the length of a grid cell in order for the lubrication model to make physical sense.


The impact of ζn,min on particle rebound trajectories for St = 27 is illustrated in Figure 7. A clear trend can be identiﬁed: decreasing the value of ζn,min also decreases the rebound height due to more damping within the lubrication layer. However, the results are moderately sensitive to the roughness value. For instance, note that changing the roughness by an order of magnitude has a similar eﬀect to excluding substeps (as shown in Figure 5). Based on the present results, we selected ζn,min = 3e-3Rp to optimize agreement with the experimental data. We have used this value for all simulations in the present work. Note that a surface roughness of 1e-4Rp has been reported by Gondret et al. (2002), and other authors have used the physical particle roughness length

|Gondret et al.<br><br>ζn,min =2e-3Rp<br><br>ζn,min =3e-3Rp<br><br>ζn,min =4e-3Rp<br><br><br>ζn,min =6e-3Rp ζn,min =1e-2Rp<br><br>|
|---|


0.7

0.6

0.5

0.4

ζ/Dnp

0.3

0.2

0.1

0.0

−0.1

−0.5 0.0 0.5 1.0 1.5 2.0 2.5

t/tref

Figure 7: Eﬀect of changing ζn,min on rebound trajectories for St = 27.

for this parameter (Kempe and Fr¨hlich, 2012a; Costa et al., 2015) to avoid the singularity in the lubrication force. Thus, we do not consider this parameter to be an exact physical representation of the actual surface roughness, but rather as a parameter to be calibrated within a reasonable range (small enough to be meaningful relative to the particle size and large enough to be resolved by the substeps).

- 4.5. Particle momentum balance for high Stokes number collisions Finally, we present a clariﬁcation to the ACTM as written by Kempe and


Fro¨hlich (2012a). As already mentioned in Section 3.2, the ACTM assumes that (11) represents the equation of motion for the particle in determining the coeﬃcients kn and dn. In other words, no ﬂuid or gravitational forces act on the particle during the contact phase. Though not stated in their paper, Kempe and Fro¨hlich (2012a) excluded hydrodynamic and buoyant weight forces in order to reproduce the trajectories of Gondret et al. (2002) (Kempe & Fr¨hlich, 2016, private communication). Thus, during contact the non-disabled Lagrangian markers still aﬀect the ﬂuid, but not the particle momentum. This procedure is somewhat delicate for the situation of sediment transport in a horizontal channel considering the fact that the governing nondimensional number is the ratio of the

- 0.0

0.5

1.0

- 1.5

- 2.0

2.5

3.0

- 3.5

- 4.0


0.5

##### a) b)

|Gondret et al.<br><br>Dry contact Wet contact<br><br>|
|---|


|Gondret et al.<br><br>Dry contact Wet contact<br><br>|
|---|


0.4

0.3

###### ζ/Dnp

ζ/Dnp

0.2

0.1

0.0

−1 0 1 2 3 4 5 6 7 8

0.0 0.5 1.0 1.5 2.0

t/tref

t/tref

- Figure 8: Eﬀect of including (“wet”) or excluding (“dry”) ﬂuid forces during contact on rebound trajectories. a) St = 152 and b) St = 27.


hydrodynamic stress to the buoyant weight of the particle. This characteristic number is classically known as the Shields parameter Sh = τw/((ρp − ρf)gDp), where τw is the wall shear stress (Shields, 1936). It is, therefore, very desirable to include gravitational and buoyant forces in (3) during the contact phase. In our experience, including the gravitational force during contact has a negligible eﬀect in changing the desired Tc and edry. In fact, the results presented so far have all been generated by including buoyant weight during contact.

On the other hand, including the ﬂuid forces during contact can lead to signiﬁcant drag on the particle throughout the collision. Figure 8 shows how excluding ﬂuid forces during contact gives us excellent agreement with the experimental results, while including ﬂuid forces during contact leads to excessive damping because the ﬂuid surrounding the particle has not been able to adapt to the change of the kinematics of the particle. Indeed, the simulations of Simeonov and Calantoni (2012) show coeﬃcients of restitution below experimental values for moderate Stokes numbers (20 < St < 100). Hence, we decided to follow Kempe and Fr¨hlich (2012a) and to exclude ﬂuid forces during contact for collisions with St 1, redeﬁning (3) as follows:

 

Fh,p + Fg,p + Fc,p ζn > 0 Fg,p + Fc,p ζn ≤ 0 .

dup dt

=

(21)

mp



Costa et al. (2015) implemented a similar method for particle-wall collisions, but they turned oﬀ ﬂuid forces when the collision overlap exceeded the expected overlap due to the particle’s weight, i.e. ζn < −(1 − ρf/ρp)gmp/kn. For the cases shown in Figure 8, the timescale of the contact phase is much smaller than the timescale of the general ﬂuid ﬂow, i.e. the timescale of the particle rebound. Thus, while neglecting ﬂuid forces has an important eﬀect on realizing the correct ewet, it has a minimal eﬀect on the general ﬂow.

However, neglecting ﬂuid forces can lead to unphysical situations for enduring contact, which we deﬁne to be when the timescale of contact matches or exceeds that of the general ﬂow. Consider, for example, a single particle at rest and in contact with a wall. If we then impose a shear ﬂow over the particle, it should be swept up into the ﬂow, or at the very least be carried downstream. However, in a simulation using (21), because the particle is in contact with the wall, it does not experience the hydrodynamic forces. It will therefore continue to sit on the wall, oblivious to the ﬂow around it, until another particle collides with it. This was addressed in Kempe et al. (2014) by switching on the hydrodynamic forces for all collisions regardless of the Stokes number, even though it was not explicitly mentioned in this reference (Kempe & Fr¨hlich, 2016, private communication). We address this problem in detail in the subsequent Section

- 5 to introduce a suitable threshold for the inclusion of the hydrodynamic forces in (3) and (4).


#### 5. Enduring contact model

- 5.1. Accounting for ﬂuid forces As shown in the results from Section 4, neglecting ﬂuid forces acting on


the particle during contact produces a good match with the experimental data of Gondret et al. (2002), which involve collisions of ﬁnite duration. However, problems can arise in the limit of enduring contact. We therefore propose to include ﬂuid forces during contact below some threshold Stokes number Stcrit. For collisions above Stcrit, the contact duration should be ﬁnite (Tc = 10∆t) so

that no major loss of physicality is encountered. For collisions below Stcrit, the particle is not going to experience an appreciable rebound so that the particle motion is not governed by collision forces during contact, but by hydrodynamic forces. Neglecting hydrodynamic forces in the low-Stokes number regime introduces artifacts in particle mobility. Indeed, this was observed in Vowinckel et al.

- (2016) for the situation of a horizontal turbulent open-channel ﬂow laden with particles heavier than their critical threshold of motion. Using the same method for collisions, these particles formed a closed bed of resting particles. In this reference, it was shown that a collision with a fast moving particle was necessary for almost all of the erosion events recorded to dislodge a particle out of the sediment packing. However, it has not been possible to clarify to what extent this triggering collision is merely a consequence of the collision procedure.


To investigate what the critical value for the Stokes number may be, we compared particle-wall collisions that include hydrodynamic forces during contact (“wet” contact) to those that exclude hydrodynamic forces during contact (“dry” contact), as illustrated in Figure 9. For this scenario, we used the same parameters as those summarized in Table 1 (St = 27) and repeated the simulations for ever-decreasing St. The Stokes number was controlled by prescribing the particle’s velocity until it made direct contact with the wall. Unlike the previous simulations, we did not allow the lubrication layer to slow the particle before contact.

For the cases with higher Stokes numbers, we can clearly see how including hydrodynamic forces during contact leads to signiﬁcant undershooting of the rebound trajectory. As the Stokes number decreases, however, the signiﬁcance of this undershooting also decreases. For St < 5 (Figure 9d), there is no appreciable rebound, and we consider the particle to be in enduring contact. Thus, based on these plots, we selected the critical Stokes number to be Stcrit = 5. This value is consistent with the work of other researchers (Gondret et al., 2002; Joseph et al., 2001), who experimentally observed no rebounds for St < 10. Note that the Stokes numbers reported in Figure 9 and our resulting Stcrit are based on the particle velocity at contact, i.e. when ζn = 0, whereas most other authors

0.5

0.5

- a) b)

c) d)

Figure 9: Comparison of trajectories of particle-wall collisions without (“dry”) and with (“wet”) hydrodynamic forces during contact for various Stokes numbers a) St = 20,

- b) St = 15, c) St = 10, d) St = 5, where uin is measured at ζn = 0.


|Dry contact Wet contact<br><br>|
|---|


|Dry contact Wet contact<br><br>|
|---|


0.4

0.4

0.3

0.3

ζ/Dnp

ζ/Dnp

0.2

0.2

0.1

0.1

0.0

0.0

−0.1

−0.1

0.0 0.5 1.0 1.5 2.0

0.0 0.5 1.0 1.5 2.0

t/tref

t/tref

0.5

0.5

|Dry contact Wet contact<br><br>|
|---|


|Dry contact Wet contact<br><br>|
|---|


0.4

0.4

0.3

0.3

ζ/Dnp

ζ/Dnp

0.2

0.2

0.1

0.1

0.0

0.0

−0.1

−0.1

0.0 0.5 1.0 1.5 2.0

0.0 0.5 1.0 1.5 2.0

t/tref

t/tref

report Stokes numbers at some distance from the wall, before the lubrication layer has fully slowed the particle. With this enduring contact model, we can expand the particle equation of motion (21) to

 

Fh,p + Fg,p + Fc,p, ζn > 0

dup dt

(22)

=

mp

- Fg,p + Fc,p, ζn ≤ 0 ∧ max{St} > Stcrit
- Fh,p + Fg,p + Fc,p, ζn ≤ 0 ∧ max{St} ≤ Stcrit ,




where the max{St} function represents the maximum Stokes number among all active collisions for particle p, and ﬂuid forces acting on the particle are only included from non-disabled markers. The same consideration applies for the angular momentum (4). Using this scheme now allows us to include the full momentum balance for particles in enduring contact, i.e. the hydrodynamic stresses as well as the buoyant weight of the particle, so that the considerations

of the Shields parameter become applicable.

- 5.2. Optimizing enduring particle overlap


In the case of St 1, the impact velocity uin approaches zero. This means in turn that the computed stiﬀness in (B.1d) would approach inﬁnity. This problem is addressed by Kempe and Fr¨hlich (2012a) who have introduced a critical Stokes number Stcrit, which establishes a minimum impact velocity to limit kn for enduring contact:

9Stcrit ρfνf ρpDp

uin,crit =

. (23)

In the present study, this critical impact velocity was used in (B.1d) and (B.1c) to compute kn and dn, respectively, for such collisions. This implementation diﬀers slightly from that of Kempe and Fr¨hlich (2012a), who do not apply any damping for collisions with St < Stcrit, i.e. they have set dn = 0. We included this damping for enduring contact in order to help reach steady-state conditions. Our implementation also diﬀers in that we use Stcrit = 5 whereas Kempe and Fro¨hlich (2012a) used Stcrit = 1.

Furthermore, we retain the buoyant weight forces in the equation of motion during contact as outlined in Section 4.5. This means that, for particle packings several diameters thick, the weight of a single sphere resting on another layer of particles is passed along to deeper layers. This eﬀect enhances the physical realism because frictional contact forces increase with depth, but it also results in increasing particle surface overlap with depth and ultimately in a change of porosity of the sediment bed, which has been acknowledged as a crucial parameter to deﬁne the hydraulic resistance of a sediment to the ﬂow (Vowinckel et al., 2014). However, a ﬂow with a lower Reynolds number would result in collisions with lower Stokes numbers such that uin,crit could become large relative to the particle size and relevant time scales. A large uin,crit would result in a low kn and hence a large overlap between particles, which is undesirable. To prevent this large overlap, we enforce a maximum overlap distance  Rp through the following procedure: for a collision with St < Stcrit, the stiﬀness is given by

 

√meﬀ

uin > uin,crit max(kn,crit, kn,grav) uin < uin,crit

uint5∗

kn =



where meﬀ and t∗ are deﬁned in (A.2) and (B.1b), respectively,

meﬀ uin,critt5∗

kn,crit =

is the stiﬀness limited by the critical impact velocity, and

(24)

(25)

kn,grav = max mpg( Rp)−3/2, mqg( Rq)−3/2 (26)

is the stiﬀness required for particle p (or q) to have a steady-state overlap of  Rp (or  Rq) with a wall due to gravity. To have a minimal constant overlap we set = 10−3. Thus, we ensure that a bed of particles contains a uniform set of collision stiﬀnesses that minimize particle overlap.

- 5.3. Rolling and sliding motion The coeﬃcient of friction for a material can depend on whether the contact


is rolling or sliding (Fishbane et al., 1996). The rolling condition implies zero slip at the contact point, i.e. gt,cp = 0 (cf. Appendix A). As a consequence, particle surfaces are in sticking contact for rolling motion until a critical threshold of static friction Fs = µs Fn is exceeded, where µs is the coeﬃcient of static friction. As soon as this condition is met, signiﬁcant slip occurs and the contact condition changes from sticking to sliding, so that the threshold for kinetic friction Fk = µk Fn must be used, where µk is the coeﬃcient of kinetic friction, with µs always greater than µk. Apart from the physical reasoning presented above, limiting the frictional forces also becomes important from a numerical point of view whenever two or more collision partners are involved. Otherwise the multiple contact points competing for no-slip conditions can lead to instabilities in the calculation of the frictional forces.

In the present study, the distinction between rolling/sticking and sliding is made by the following scheme, which is comparable to that of Luding (2008):

Case Dry oblique collision Rolling in shear ﬂow Rp 0.00159 0.0625 ρp/ρf 2500 2.5 edry 0.83 0.97 ν 0.22 0.3 µk 0.11 0.15 µs 0.8 0.8 g 0 9.81 νf 0 0.02 Timestep ∆t = 2e−5 CFL = 0.5

Table 2: Simulation setup for oblique and rolling sphere simulations.

- • While the particle is sticking, i.e. ||Ft,LS|| < ||µFn||, we set µ = µs to test for the onset of slipping.
- • Once slipping occurs, i.e. ||Ft,LS|| > ||µFn||, we set µ = µk until the friction force falls below the Coulomb friction force.


The aim of the present study is to simulate natural sediment. Hence we parametrized the coeﬃcients of friction with typical values of silicate materials, yielding µk = 0.15 based on the work of Joseph and Hunt (2004), who worked with glass spheres, and µs = 0.8 based on the work of Dieterich (1972), who found values ranging from 0.75 to 0.85 for diﬀerent rock materials like quartz, granite, and sandstone.

We have validated the tangential collision model using an oblique dry impact experiment, i.e. neglecting hydrodynamic forces, by Foerster et al. (1994), whose parameters are summarized in Table 2. Figure 10 shows that our simulations compare well to the experiments in reproducing the rebound angle

ut,out un,in

ψout =

, (27)

0.6

|Foerster et al.<br><br>Present|
|---|


0.5

0.4

0.3

ψout

0.2

0.1

0.0

−0.1

−0.2

0.0 0.2 0.4 0.6 0.8 1.0 1.2 1.4

ψin

Figure 10: Rebound vs. impact angles for a particle-wall oblique collision.

which depends on the impact angle

ut,in un,in

ψin =

. (28)

Here, un,in is the impact velocity normal to the wall, while ut,in and ut,out are the impact and rebound velocities, respectively, of the particle’s contact point tangential to the wall (ut = up + Rp ωp,z for a particle obliquely colliding in the x-direction). For a particle with no initial rotation, ψin is the tangent of the angle the particle makes with the wall from the normal (ψin = 0 means no relative tangent motion). The rebound angle is zero when the contact is sticking perfectly at the time of release. However, the rebound angle is negative when, at the point of release, |up| < |ωp,z| (since ωp,z < 0 for our example). The linear-spring tangential collision model is able to perfectly capture these negative values for ψout at low impact angles.

To test both situations, rolling and sliding, we simulated a particle in a Couette ﬂow. We placed a sphere of radius Rp/H = 0.0625 on the bottom wall of a channel of height H. We initialized the particle at rest at a distance ζn/Rp = 1.6×10−5 above the bottom wall. We subsequently exposed the sphere to a linear shear ﬂow, holding it ﬁxed for a short time (tU/H = 0.01) to allow the ﬂow to develop around it before releasing it. The numerical parameters

- 0.00

- 0.01

- 0.02

- 0.03

- 0.04

- 0.05

u/Uw

|up<br><br>−ωp,z Rp,cp|
|---|


0.0 0.2 0.4 0.6 0.8 1.0 1.2 1.4 1.6

tUw/H

0.00

0.01

0.02

0.03

0.04

0.05

u/Uw

|up<br><br>−ωp,z Rp,cp|
|---|


a) b)

- Figure 11: Translational and rotational velocities of a particle exposed to a linear shear ﬂow. a) sliding motion for ReH = 10 and b) rolling motion for ReH = 50.


are summarized in Table 2. We found that slipping motion occurs for a lower Reynolds number of ReH = UH/νf = 10, where U is the lid velocity. On the other hand, perfect rolling motion occurs at ReH = UH/νf = 50.

Figure 11 shows how the particle accelerates until it reaches a steady-state translational velocity. As soon as the particle makes contact with the wall, gravity holds it there with a slight overlap according to the conditions deﬁned in Section 5.2. Accounting for ﬂuid forces during contact allows the particle to accelerate to a steady-state speed while in contact with the wall. As expected the particle achieves perfect rolling without slip (Figure 11b), marked by the match between the translational velocity up and the rotational velocity relative to the particle center −ωp,z Rp,cp. Accordingly, the particle shows signiﬁcant slip for the lower Reynolds number (Figure 11a), where the increased viscosity leads to increased drag on the particle, which in turn overpowers the friction from the particle’s weight.

- 6. Flow over dense sediment


0.0 0.2 0.4 0.6 0.8 1.0 1.2 1.4 1.6

tUw/H

- 6.1. Physical setup We presented a detailed validation of binary particle-wall collisions in Sec-


tions 4 and 5. To address the bulk behavior of a dense granular bed sheared by a laminar Poiseuille ﬂow, we carried out numerical simulations to reproduce

![image 1](01_He_Tc-Superfluid-Density-Overdoped-Cuprates_Nature2016_images/imageFile1.png)

- Figure 12: Left plot: Instantaneous snapshot of a slice through the xy-plane for case A10M. Contours show the streamwise component of the ﬂuid velocity. Particles are colored grayscale according to their velocity. Right plot: Streamwise and spanwise averages of ﬂuid and particle velocities. Arrows correspond to the length scales for the clear ﬂuid, hf, the particle bed, hp, the mobile bed layer, hm, and the motionless bed layer, hc.


the experimental results of Aussillous et al. (2013), who studied pressure-driven ﬂows over glass spheres with a mean diameter Dp = 1.1mm and a standard deviation of σ(Dp) = 0.1mm as sediment material. This experimental work provides investigations over a range of submergences hf/Dp and Reynolds numbers in the laminar regime, where hf is the height of the clear-water layer above the sediment bed illustrated in Figure 12. We deﬁne hf to be the height above which the average particle volume fraction φ < 0.05, which is the threshold for negligible impact of particle-particle interaction on the ﬂow (Capart and Fraccarollo, 2011). We deﬁne the mobile bed height hm to be the portion of the particle bed above which the mean particle velocity is higher than 1% of the value at the ﬂuid/particle interface.

Ga 0.397 Rp (m) 0.0444 ρp/ρf 2.1 νf (m2/s) 0.219 g (m/s2) 9.81 edry 0.97 ζn,min (m) 3.0 × 10−3Rp µk 0.15 µs 0.8

Domain size (m) (Lx × Ly × Lz) 1.0 × 2.0 × 1.0 Domain boundary conditions p × ns × p

Grid cells in x-direction 256 Dp/h 22.7 Volume fraction in center of bed 0.609 Timestep CFL = 0.1

- Table 3: Simulation parameters to match the experiments of Aussillous et al. (2013). Boundary conditions are periodic (p) and no-slip (ns). The Galileo number Ga is deﬁned in (29).


In their experiments, Aussillous et al. (2013) ﬁlled a long chamber with particles and then applied a constant pressure gradient, which eroded the particles from the chamber. Initially, the ﬂuid height hf was small and the pressure gradient drove a large number of particles so that the height of the mobile bed layer, hm in Figure 12, was large. Since no new particles were added to the chamber, hf increased as the particles eroded away until, at long periods of time, the experiment reached a steady-state conﬁguration where the inﬂux of particles into the observation window remained in equilibrium with the outﬂux. Due to our use of periodic boundary conditions, we will only try to replicate the long-term steady-state ﬂow conditions, of which there are only a few data from Aussillous et al. (2013)

Case A1 A2 A9 A10 A10M Reb 0.301 0.402 1.01 1.15 1.15 hf/Dp (Exp.) 7.05 ± 0.5 8.15 ± 0.5 10.29 ± 0.5 11.27 ± 0.5 11.27 ± 0.5 hf/Dp (Sim.) 7.15 8.31 10.33 11.29 11.05 Sh (Exp.) 0.24 ± 0.03 0.24 ± 0.03 0.37 ± 0.04 0.35 ± 0.03 0.35 ± 0.03 Sh (Sim.) 0.224 0.222 0.358 0.343 0.357 qf (m2/s) 0.0659 0.0880 0.220 0.251 0.251 Np,m 2031 1870 1559 1419 1407∗ Np,f 132 132 132 132 132 Tavg (s) 139.5 137.9 126.2 127.3 111.0

- Table 4: Parameters that vary between the diﬀerent cases. The bulk Reynolds number Reb is deﬁned in (30) and the Shields number Sh is deﬁned in (31). The ﬂuid height hf (and hence Shields number) do not exactly match between the experiments (Exp.) and simulations (Sim.). ∗Polydisperse particle diameters follow a Gaussian distribution with a standard deviation of σ(Dp) = 0.1Dp.


We executed several simulations in an attempt to match four of the experiments of Aussillous et al. (2013) at diﬀerent ﬂow rates and ﬂuid heights. The physical and numerical parameters associated with these simulations are listed in Table 3, and the diﬀerences between the four cases are listed in Table 4. These experiments can be characterized by the Galileo number

(ρp/ρf − 1)gDp3 νf

Ga =

, (29)

the bulk Reynolds number

qf νf

, (30) where qf is the ﬂuid ﬂow rate, and the Shields number

Reb =

6Reb Ga2

Sh =

Dp hf

2

, (31)

which represents the ratio of the shear stress acting on the particle bed to the buoyant weight of a particle. Aussillous et al. (2013) reported an uncertainty

for the determination of the bed height as hf ± Rp, which we have included in

- Table 4 as the deviations in hf and Sh, which depends on hf. We required a low CFL = 0.1 in order to maintain the stability of the ﬂuid-


particle coupling. This restricted CFL value was necessary to avoid numerical instabilities arising from the simultaneous particle-particle interactions of a multitude of particles within the thick sediment bed. We also used a grid resolution of Dp/h = 22.7 to resolve the interstitial ﬂow, though we did not see any appreciable diﬀerence in the bulk ﬂow properties for a coarser discretization of Dp/h = 17.0.

We generated the initial sediment bed using a precursor simulation, in which we randomly distributed Np,m particles in a computational domain with periodic x- and z-boundaries above a layer of Np,f ﬁxed particles, which we arranged in a hexagonal packing with random heights varying from 0 < y0 < Dp. These ﬁxed particles were used to avoid over-idealized smooth conditions at the lower wall. We subsequently allowed the non-ﬁxed particles to settle under “dry” conditions, i.e. without considering hydrodynamic forces. We then applied a large pressure gradient to produce a ﬂuid ﬂow rate 8 times that of the ﬁnal desired ﬂow rate, mobilizing the entire bed. This mobilization also caused the bed to dilate, or have the average local volume fraction decrease, which in turn decreased hf. Once hf dropped to about 0.15Dp below the desired value, we immediately decreased the ﬂow rate to the ﬁnal ﬂow rate reported in Table 4, which is deﬁned as

1 LxLz

qf =

Lz

0

Ly

0

Lx

(1 − φ)udxdy dz , (32)

0

where φ is the particle volume fraction. We adopted this procedure because we noticed a hysteresis in the particle ﬂux between an increased ﬂow rate and a decreased ﬂow rate, which has also been observed by Clark et al. (2015). Note that this procedure more closely resembles the experiments, where the particle bed is largely mobilized and then settles into a lower particle ﬂux.

However, one problem with this procedure is that we cannot determine the ﬁnal bed height a priori. The dilation and contraction accompanying the two

a) b)

0.0

0.0

−0.1

−0.1

###### −yh/h()pf

###### −yh/h()pf

−0.2

−0.2

−0.3

−0.3

|Fluid<br><br>Particles<br><br>Aussillous et al.|
|---|


|Fluid<br><br>Particles<br><br>Aussillous et al.|
|---|


−0.4

−0.4

−0.5

−0.5

0.00 0.05 0.10 0.15 0.20

0.00 0.05 0.10 0.15 0.20

u/(qf/hf)

u/(qf/hf)

- c) d)


0.0

0.0

−0.1

−0.1

−yh/h()pf

###### −yh/h()pf

−0.2

−0.2

−0.3

−0.3

|Fluid<br><br>Particles<br><br>Aussillous et al.|
|---|


|Fluid<br><br>Particles<br><br>Aussillous et al.|
|---|


−0.4

−0.4

−0.5

−0.5

0.00 0.05 0.10 0.15 0.20

0.00 0.05 0.10 0.15 0.20

u/(qf/hf)

u/(qf/hf)

- Figure 13: Wall-normal proﬁles of average ﬂuid and particle velocities near the particle/ﬂuid interface compared to the wall-normal particle velocity proﬁle from Aussillous


- et al. (2013). a) Case A1, b) Case A2 c) Case A9 d) Case A10.


ﬂow rates is diﬃcult to predict without executing an iterative procedure of running simulations with varying numbers of particles. Due to the computational costs of the simulations, we did not iterate on this method, but instead accepted the values we obtained for hf, which, with the exception of case A10M, are larger than those in the experiments, as seen in Table 4.

- 6.2. Comparison of wall-normal proﬁles In Figure 13 we compare the particle velocity proﬁles of the simulation to


the experimental results of Aussillous et al. (2013). We calculated the particle velocity proﬁle up(y) from our simulations by averaging the velocities of all the particles in the streamwise and spanwise directions whose center fell within a given range of heights. We used bins of width Rp arranged such that the topmost bin extended from y = hp−Rp to y = hp. We evaluated the ﬂuid velocity proﬁle

by averaging the u-velocity ﬁeld in the streamwise and spanwise directions for each grid cell of the y-coordinate. For this calculation, we used the particle cell volume fractions φ to exclude ﬂuid velocities existing within the particles:

Lz 0

Lx 0 (1 − φ)udxdz

(33)

u xz =

Lx 0 (1 − φ)dxdz

Lz 0

The ﬂuid velocity proﬁles exhibit a parabolic shape in the clear ﬂuid above the bed, as shown in Figure 12. At the interface between the clear ﬂuid and particle bed, we observe some slip between the ﬂuid and the particles, but within the bed the two velocity proﬁles are very similar, with only a slight diﬀerence due to ﬂow between the particles. The particle velocity proﬁles from the simulations compare very well with the experiments for cases A9 and A10, and reasonably well for cases A1 and A2.

Part of the discrepancy between our experiments and the simulations is due to the diﬀerences in bed heights and Shields numbers as seen in Table 4. In this table, we can see that cases A1 and A2 exhibit the largest diﬀerences in the ﬂuid height between the simulations and experiments, which may have resulted in the larger deviations in the velocity proﬁles seen in Figure 13. Likewise, for these two cases we can also see larger diﬀerences in the Shields number, which can be sensitive to the ﬂuid height hf.

- 6.3. Comparison of bulk quantities


We ran the simulation until it reached a constant particle velocity ﬂux qv, deﬁned as

Ly

qv =

up(y)dy , (34)

0

where up(y) is the particle velocity proﬁle as deﬁned in the previous section. Unlike qf, which had no variability in time, qv did vary as particles occasionally locked in place or rolled over one another. We therefore evaluated a timeaveraged value of the particle velocity ﬂux

1 Tavg

qv T =

tf

##### qv dt , (35)

ts

Case Experimental value Simulation value qv −T /qf qv T/qf qv +T /qf qv T/qf

- A1 5.e-3 1.2e-2 1.9e-2 6.71e-3

- A2 5.e-3 1.1e-2 1.6e-2 5.17e-3


- A9 4.87e-3 8.20e-3 1.15e-2 7.61e-3

- A10 5.17e-3 7.04e-3 8.91e-3 5.84e-3


A10M 5.17e-3 7.04e-3 8.91e-3 7.56e-3

- Table 5: Comparison of the velocity ﬂux qv T between our simulations and the experi-


ments of Aussillous et al. (2013). qv +T /qf and qv −T /qf represent the mean qv T/qf plus and minus the standard deviation over the averaging time, respectively.

where tf is the time at the end of the simulation, ts is the time at which the particle ﬂux reached steady-state, and Tavg = tf − ts is the time interval over which the data was averaged. The values of Tavg are given in Table 4.

In Table 5, we can see a good agreement between our numerical results and the experimental values of the velocity ﬂux qv. Because these quantities are derived from the particle velocity proﬁles, we expect to see the similar trends, namely that we underestimate the mean values from the experiments and obtain better matches for cases A9 and A10. However, our results still fall within the margin of error of the experiments.

- 6.4. Polydisperse ﬂow Furthermore, we conducted another simulation to show the eﬀect of poly-


dispersity. In experiments, it is impossible to have a perfectly monodisperse set of particles. In their article, Aussillous et al. (2013) reported having a set of spheres with diameters following a Gaussian distribution of mean Dp = 1.1mm and standard deviation σ(Dp) = 0.1mm, which is almost 10% of the mean. We created a simulation containing this distribution of particle diameters and a similar submergence depth to that of case A10. The parameters used are listed under case A10M in Table 4.

0.2

0.0

−0.2

### −yh/h()pf

−0.4

−0.6

|A10<br><br>A10M|
|---|


−0.8

−1.0

0.0 0.1 0.2 0.3 0.4 0.5 0.6 0.7

φ

Figure 14: Wall-normal proﬁles of average particle volume fractions.

In Figure 14, we do not see any appreciable changes in the particle bed volume fractions between cases A10 and A10M. The average volume fraction within the bed is φ = 0.609, which is consistent with a random sphere packing fraction. On the other hand, in Figure 15, we see a slightly increased velocity proﬁle compared to that of case A10 (Figure 13d). This is likely due to the decreased value of hf compared to that of A10, which results in a higher Shields number, as shown in Table 4. Therefore, we also obtain a velocity ﬂux that overpredicts the mean experimental value, as shown in Table 5. However, the particle velocity proﬁle and velocity ﬂux still agree very well with the experimental results, and the results suggest that using monodisperse spheres is a valid approximation to polydisperse spheres for this experimental setup.

#### 7. Conclusions

In the present study, we presented and validated a contact model for the purpose of phase-resolved Direct Numerical Simulations, in which the disperse phase is represented by the Immersed Boundary Method. The present modeling approach allows for actual particle contact and takes all relevant contact forces into account without introducing parameters that require arbitrary calibration.

0.0

−0.1

### −yh/h()pf

−0.2

−0.3

|Fluid<br><br>Particles<br><br>Aussillous et al.|
|---|


−0.4

−0.5

0.00 0.05 0.10 0.15 0.20

u/(qf/hf)

Figure 15: Wall-normal proﬁles of average ﬂuid and particle velocities for the simulation with polydisperse particles (case A10M).

These forces include lubrication forces for small inter-particle gaps, normal repulsive forces to resolve inelastic collisions, and tangential forces to represent particle friction. We demonstrated that an improved integration scheme is necessary to obtain consistent results for particle-wall collisions. Subsequently, we presented enhancements that extend the model to deal with simulations of ﬂows over dense granular sediments. It turns out that these enhancements are crucial in order to deal with thick sediment packings. The measures taken allow us to generate sediment packings several diameters thick that are numerically stable as the packing reaches a steady-state condition. The simulations are performed by retaining the full momentum balance of a particle in enduring contact, which includes the hydrodynamic forces and the buoyant weight of a particle. Including these forces is crucial to represent phenomena like erosion and resuspension of particles. Moreover, the enhanced model allows for rolling and sliding contact, distinguishing between sticking and sliding conditions.

Altogether, the present approach yielded satisfactory agreement with the benchmark test cases for binary collisions as well as the collective motion of particles for a horizontal ﬂow over a dense granular packing. In addition, a ﬁrst test case involving polydisperse sediment was presented. The high degree

of accuracy achieved is going to enable us to analyze phase-resolved numerical simulation data in great detail. Although not explicitly stated, we believe that the present approach is also applicable for the situation of vertical channel ﬂows as well as neutrally buoyant particles in laminar and turbulent conditions. It can therefore provide a valuable tool to generate high-ﬁdelity data even on the grain scale of any kind of multiphase ﬂows involving rigid spheres.

#### 8. Acknowledgements

This research is supported in part by the Department of Energy Oﬃce of Science Graduate Fellowship Program (DOE SCGF), made possible in part by the American Recovery and Reinvestment Act of 2009, administered by ORISEORAU under contract no. DE-AC05-06OR23100. It is also supported by the Petroleum Research Fund, administered by the American Chemical Society, grant number 54948-ND9. BV gratefully acknowledges the Feodor-Lynen scholarship provided by the Alexander von Humboldt foundation, Germany, and EM thanks Petrobras for partial support. The authors thank E. Guazelli and P.´ Aussillous for stimulating discussions on their experimental work. P. Gondret, N. Mordant, and A. Ten Cate are acknowledged for kindly providing their data. Computational resources for this work used the Extreme Science and Engineering Discovery Environment (XSEDE), which was supported by the National Science Foundation, USA, Grant No. TG-CTS150053.

References References Apte, S.V., Martin, M., Patankar, N.A., 2009. A numerical method for fully

resolved simulation (FRS) of rigid particleﬂow interactions in complex ﬂows. Journal of Computational Physics 228, 2712–2738.

Aussillous, P., Chauchat, J., Pailha, M., M´edale, M.and Guazzelli, E., 2013. Investigation of the mobile granular layer in bedload transport by laminar shearing ﬂows. Journal of Fluid Mechanics 736, 594–615.

Balachandar, S., Eaton, J.K., 2010. Turbulent dispersed multiphase ﬂow. Annual Review of Fluid Mechanics 42, 111–133.

Breugem, W.P., 2012. A second-order accurate immersed boundary method for fully resolved simulations of particle-laden ﬂows. Journal of Computational Physics 231, 4469–4498.

Capart, H., Fraccarollo, L., 2011. Transport layer structure in intense bed-load. Geophysical Research Letters 38, 2–7.

Charru, F., Andreotti, B., Claudin, P., 2013. Sand ripples and dunes. Annu. Rev. Fluid Mech. 45, 469–493.

Clark, A.H., Shattuck, M.D., Ouellette, N.T., O’Hern, C.S., 2015. Onset and cessation of motion in hydrodynamically sheared granular beds. Physical Review E - Statistical, Nonlinear, and Soft Matter Physics 92, 1–7.

Costa, P., Boersma, B.J., Westerweel, J., Breugem, W.P., 2015. Collision model for fully resolved simulations of ﬂows laden with ﬁnite-size particles. Physical Review E 92, 053012.

Cox, R., Brenner, H., 1967. The slow motion of a sphere through a viscous ﬂuid towards a plane surface. Small gap widths, including inertial eﬀects. Chemical Engineering Science 22, 1753–1777.

Derksen, J.J., 2011. Simulations of granular bed erosion due to laminar shear ﬂow near the critical shields number. Physics of Fluids 23, 113303.

Derksen, J.J., 2015. Simulations of granular bed erosion due to a mildly turbulent shear ﬂow. Journal of Hydraulic Research 53, 622–632.

Dieterich, J.H., 1972. Time-dependent friction in rocks. Journal of Geophysical Research 77, 3690–3697.

Fadlun, E.A., Verzicco, R., Orlandi, P., Mohd-Yusof, J., 2000. Combined immersed-boundary ﬁnite-diﬀerence methods for three-dimensional complex ﬂow simulations. Journal of Computational Physics 161, 35–60.

Fenton, J.D., Abbott, J.E., 1977. Initial movement of grains on a stream bed

- eﬀect of relative protrusion. Proceedings of the Royal Society of London Series A-mathematical Physical and Engineering Sciences 352, 523–537.

Fishbane, P.M., Gasiorowicz, S., Thornton, S.T., 1996. Physics for scientists and engineers. Pearson College Division.

Foerster, S.F., Louge, M.Y., Chang, H., Allia, K., 1994. Measurements of the collision properties of small spheres. Physics of Fluids 6, 1108.

Fukuoka, S., Fukuda, T., Uchida, T., 2014. Eﬀects of sizes and shapes of gravel particles on sediment transports and bed variations in a numerical movablebed channel. Advances in Water Resources 72, 84–96.

Garcia, M., 2008. Sediment transport and morphodynamics, in: Garcia, M. (Ed.), American Society of Civil Engineers, Manuals and Reports on Engineering Practice 110, pp. 21–168.

Glowinski, R., Pan, T.W., Hesla, T.I., Joseph, D.D., 1999. A distributed Lagrange multiplier/ﬁctitious domain method for particulate ﬂows. International Journal of Multiphase Flow 25, 755–794.

Glowinski, R., Pan, T.W., Hesla, T.I., Joseph, D.D., Priaux, J., 2001. A ﬁctitious domain approach to the direct numerical simulation of incompressible viscous ﬂow past moving rigid bodies: Application to particulate ﬂow. Journal Computational Physics 169, 363–426.

Gondret, P., Lance, M., Petit, L., 2002. Bouncing motion of spherical particles in ﬂuids. Physics of Fluids 14, 643–652.

Hertz, H., 1882. Uber¨ die Beru¨hrung fester elastischer K¨rper. J. f. reine u. angewandte Math. 92, 156–171.

Izard, E., Bonometti, T., Lacaze, L., 2014. Modelling the dynamics of a sphere approaching and bouncing on a wall in a viscous ﬂuid. Journal of Fluid Mechanics 747, 422–446.

Joseph, G.G., Hunt, M.L., 2004. Oblique particle-wall collisions in a liquid. Journal of Fluid Mechanics 510, 71–93.

Joseph, G.G., Zenit, R., Hunt, M.L., Rosenwinkel, A.M., 2001. Particle-wall collisions in a viscous ﬂuid. Journal of Fluid Mechanics 433, 329–346.

Kajishima, T., Takiguchi, S., Hamasaki, H., Miyake, Y., 2001. Turbulence structure of particle-laden ﬂow in a vertical plane channel due to vortex shedding. JSME International Journal Series B-Fluids and Thermal Engineering 44, 526–535.

- Kempe, T., Fr¨hlich, J., 2012a. Collision modelling for the interface-resolved simulation of spherical particles in viscous ﬂuids. Journal of Fluid Mechanics 709, 445–489.
- Kempe, T., Fr¨hlich, J., 2012b. An improved immersed boundary method with direct forcing for the simulation of particle laden ﬂows. Journal of Computational Physics 231, 3663–3684.


Kempe, T., Vowinckel, B., Fr¨hlich, J., 2014. On the relevance of collision modeling for interface-resolving simulations of sediment transport in open channel ﬂow. International Journal of Multiphase Flow 58, 214–235.

Kidanemariam, A.G., Chan-Braun, C., Doychev, T., Uhlmann, M., 2013. Direct numerical simulation of horizontal open channel ﬂow with ﬁnite-size, heavy particles at low solid volume fraction. New Journal of Physics 15, 025031.

Kidanemariam, A.G., Uhlmann, M., 2014. Interface-resolved direct numerical simulation of the erosion of a sediment bed sheared by laminar channel ﬂow. International Journal of Multiphase Flow 67, 174–188.

Lajeunesse, E., Malverti, L., Charru, F., 2010. Bed load transport in turbulent ﬂow at the grain scale: Experiments and modeling. J. Geophys. Res.: Earth Surfarce 115.

Lucci, F., Ferrante, A., Elghobashi, S., 2010. Modulation of isotropic turbulence by particles of taylor length-scale size. Journal of Fluid Mechanics 650, 5–55.

Luding, S., 2008. Cohesive, frictional powders: contact models for tension. Granular Matter 10, 235–246.

Meiburg, E., Kneller, B., 2010. Turbidity currents and their deposits. Annu. Rev. Fluid Mech. 42, 135–156.

Mittal, R., Iaccarino, G., 2005. Immersed boundary methods. Annu. Rev. Fluid Mech. 37, 239–261.

Mordant, N., Pinton, J.F., 2000. Velocity measurement of a settling sphere. The European Physical Journal B-Condensed Matter and Complex Systems 18, 343–352.

Nin˜o, Y., Garcı´a, M., 1998. Experiments on saltation of sand in water. Journal of Hydraulic Engineering 124, 1014–1025.

Patankar, N.A., Singh, P., Joseph, D.D., Glowinski, R., Pan, T.W., 2000. A new formulation of the distributed Lagrange multiplier/ﬁctitious domain method for particulate ﬂows. International Journal of Multiphase Flow 26, 1509–1524.

Picano, F., Breugem, W.P., Brandt, L., 2015. Turbulent channel ﬂow of dense suspensions of neutrally buoyant spheres. Journal of Fluid Mechanics 764, 463–487.

Rai, M.M., Moin, P., 1991. Direct simulations of turbulent ﬂow using ﬁnitediﬀerence schemes. Journal of computational physics 96, 15–53.

Ray, S., Kempe, T., Fr¨hlich, 2015. Eﬃcient modelling of particle collisions using a non-linear viscoelastic contact force. International Journal of Multiphase Flow , accepted.

Roma, A., Peskin, C., Berger, M., 1999. An Adaptive Version of the Immersed Boundary Method. Journal of Computational Physics 153, 509–534.

Santarelli, C., Fr¨hlich, J., 2015. Direct numerical simulations of spherical bubbles in vertical turbulent channel ﬂow. International Journal of Multiphase Flow 75, 174–193.

Seminara, G., 2010. Fluvial sedimentary patterns. Annu. Rev. Fluid Mech. 42, 43–66.

Shao, X.M., Wu, T.H., Yu, Z.S., 2012. Fully resolved numerical simulation of particle-laden turbulent ﬂow in a horizontal channel at a low Reynolds number. Journal of Fluid Mechanics 693, 319–344.

Shields, A., 1936. Anwendung der Ahnlichkeitsmechanik¨ und der Turbulenzforschung auf die Geschiebebewegung. Ph.D. thesis. Mitteilungen der Preußischen Versuchsanstalt fu¨r Wasserbau und Schiﬀbau, Berlin (in German).

Sierakowski, A.J., Prosperetti, A., 2016. Resolved-particle simulation by the physalis method: Enhancements and new capabilities. Journal of Computational Physics 309, 164–184.

Simeonov, J.A., Calantoni, J., 2012. Modeling mechanical contact and lubrication in Direct Numerical Simulations of colliding particles. International Journal of Multiphase Flow 46, 38–53.

Ten Cate, A., Nieuwstad, C.H., Derksen, J.J., Van den Akker, H.E.A., 2002. Particle imaging velocimetry experiments and lattice-boltzmann simulations on a single sphere settling under gravity. Physics of Fluids 14, 4012–4025.

Thornton, C., Cummins, S.J., Cleary, P.W., 2011. An investigation of the comparative behaviour of alternative contact force models during elastic collisions. Powder Technology 210, 189–197.

Thornton, C., Cummins, S.J., Cleary, P.W., 2013. An investigation of the comparative behaviour of alternative contact force models during inelastic collisions. Powder Technology 233, 30–46.

Uhlmann, M., 2005. An immersed boundary method with direct forcing for the simulation of particulate ﬂows. Journal of Computational Physics 209, 448–476.

Uhlmann, M., 2008. Interface-resolved direct numerical simulation of vertical particulate channel ﬂow in the turbulent regime. Physics of Fluids 20, 053305.

Vowinckel, B., Jain, R., Kempe, T., Fr¨hlich, J., 2016. Erosion of single particles in a turbulent open-channel ﬂow: a numerical study. J. Hydraul. Res. 54, 158– 171.

Vowinckel, B., Kempe, T., Fr¨hlich, J., 2014. Fluid-particle interaction in turbulent open channel ﬂow with fully-resolved mobile beds. Advances in Water Resources 72, 32–44.

Zhang, Z., Prosperetti, A., 2005. A second-order method for three-dimensional particle simulation. Journal of Computational Physics 210, 292–324.

Zhu, H.P., Zhou, Z.Y., Yang, R.Y., Yu, a.B., 2008. Discrete particle simulation of particulate systems: A review of major applications and ﬁndings. Chemical Engineering Science 63, 5728–5770.

Appendix

- Appendix A. Deﬁnitions for particle-particle and particle-wall collisions


In order to discuss collisions in a general manner, we provide deﬁnitions for several variables that describe the contact. Some deﬁnitions will depend on whether the interaction is between particle p and a wall (particle-wall interaction, or P-W) or between particle p and particle q (particle-particle interaction, or P-P). For most of the deﬁnitions, collisions between a ﬁxed particle and a mobile particle are handled identically to particle-particle collisions, unless indicated otherwise (particle-ﬁxed, or P-F).

- • Reﬀ – eﬀective radius

Reﬀ =

Rp Rq Rp + Rq

(P-P) (A.1a) Reﬀ = Rp (P-W) (A.1b)

- • meﬀ – eﬀective mass

meﬀ =

mp mq mp + mq

(P-P) (A.2a) meﬀ = mp (P-W, P-F) (A.2b)

- • xw – point on wall closest to particle
- • n – unit vector normal to the surface of contact, points from xp to xq (P-P) or directly towards the wall (P-W)

n =

xq − xp ||xq − xp||

(P-P) (A.3a)

n =

xw − xp ||xw − xp||

(P-W) (A.3b)

- • ζn – distance between surfaces of the two bodies (negative value indicates overlap)


ζn = ||xq − xp|| − Rp − Rq (P-P) (A.4a) ζn = ||xw − xp|| − Rp (P-W) (A.4b)

- • xcp – location of contact point between surfaces, halfway between surface overlap (P-P)

xcp = xp + Rp +

ζn 2

n (P-P) (A.5a) xcp = xw (P-W) (A.5b)

- • Rp,cp – radius of particle p with respect to the contact point

Rp,cp = ||xcp − xp|| (A.6)

- • g – relative velocity between particle centers of mass

g = up − uq (P-P) (A.7a) g = up (P-W) (A.7b)

- • gcp – relative velocity of surface contact point

gcp = g + Rp,cp(ωp × n) + Rq,cp(ωq × n) (P-P) (A.8a) gcp = g + Rp,cp(ωp × n) (P-W) (A.8b)

- • gn,cp – component of gcp normal to surface

gn,cp = (gcp · n)n (A.9)

- • gt,cp – component of gcp tangent to surface


gt,cp = gcp − gn,cp (A.10)

#### Appendix B. Calculating the normal contact model coeﬃcients

In order to obtain the stiﬀness and damping coeﬃcients kn and dn, Ray et al.

- (2015) use nonlinear transformations and a series expansion of (11) to yield the following algebraic expressions:


1 α2τc,20 −

- 1

- 2


λ =

Cη +

1 4

C2η2 + α2τc,20η , (B.1a)

Tc τc,0

t∗ =

1 − Aλ − Bλ2 , (B.1b)

2λmeﬀ t∗

, (B.1c) and

dn =

meﬀ uint5∗

kn =

, (B.1d)

where A = 0.716,B = 0.830, C = 0.744, α = 1.111, and τc,0 = 3.218 are constants. The parameter η = (lnedry)2 accounts for the restitution coeﬃcient, and we measure the impact velocity to be uin = gn,cp · n at the ﬁrst occurrence of ζn ≤ 0.

#### Appendix C. The tangential displacement vector

Tangential models based on spring systems require a displacement as deﬁned by (13), which represents the accumulated relative motion between two surfaces We calculate ζt in a discrete sense as follows:

ζt = ζtk−1 − ζkt−1 · n n (C.1a)

ζt = ||ζkt−1||

ζt (C.1b)

||ζt||

ζkt = ζt + 2αk∆tgt,cp . (C.1c) Equations (C.1a) and (C.1b) rotate the displacement from the previous timestep onto a plane tangent to the two surfaces. Luding (2008) implemented this rotation to account for the change in reference frame that can take place between two timesteps. Without this rotation, the linear spring could contribute to the normal force acting between two particles.

Furthermore, when the two surfaces slip according to the Coulomb friction criteria, the displacement vector should not grow as the two surfaces continue to slide past one another. Instead, we reset the displacement to that which achieves the Coulomb friction force:

||µFn||t + dtgt,cp kt

ζt = −

if ||Ft,LS|| > ||µFn|| . (C.2)

