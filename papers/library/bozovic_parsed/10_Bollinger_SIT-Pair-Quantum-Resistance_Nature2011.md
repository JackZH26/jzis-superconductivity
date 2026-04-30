Mon. Not. R. Astron. Soc. 000, 1–24 (2002) Printed 25 October 2018 (MN LATEX style ﬁle v2.2)

# Galaxy formation in semi-analytic models and cosmological hydrodynamic zoom simulations

arXiv:1104.1626v2[astro-ph.CO]6 Oct 2011

Michaela Hirschmann1⋆, Thorsten Naab2, Rachel S. Somerville3,4, Andreas Burkert1, Ludwig Oser2

1Universita¨ts Sternwarte Mu¨nchen, Scheinerstr.1, D-81679 Mu¨nchen, Germany 2Max Planck Institut fu¨r Astrophysik, Karl-Schwarzschild-Str. 1, D-85741 Garching, Germany 3Space Telescope Science Insitute, 3700 San Martin Dr., Baltimore, MD 21218, USA 4Department of Physics and Astronomy, Johns Hopkins University, Baltimore, MD 21218, USA

Accepted by MNRAS, 10/05/2011

ABSTRACT

We present a detailed comparison between numerical cosmological hydrodynamic zoom simulations and the semi-analytic model of Somerville et al. (2008a), run within merger trees extracted from the simulations. The high-resolution simulations represent 48 individual halos with virial masses in the range 2.4 × 1011M⊙ < MHalo < 3.3 × 1013M⊙. They include radiative H & He cooling, photo-ionization, star formation and thermal SN feedback. We compare with diﬀerent SAM versions including only this complement of physical processes, and also ones including supernova driven winds, metal cooling, and feedback from Active Galactic Nuclei (AGN). Our analysis is focused on the cosmic evolution of the baryon content in galaxies and its division into various components (stars, cold gas, and hot gas), as well as how those galaxies acquired their gas and their stellar mass. Both the SAMs and simulations are compared with observational relations between halo mass and stellar mass, and between stellar mass and star formation rate, at low and high redshift. We ﬁnd some points of agreement and some important disagreements. SAMs that include the same physical processes as the simulations reproduce the total baryon fraction in halos and the fraction of cold gas plus stars in the central galaxy to better than 20%. However, the simulations turn out to have much higher star formation eﬃciencies (by about a factor of ten) than the SAMs, despite nominally being both normalized to the same empirical Kennicutt relation at z = 0. Therefore the cold gas is consumed much more rapidly in the simulations and stars form much earlier. Also, simulations show a transition between stellar mass growth that is dominated by in situ formation of stars to growth that is predominantly through accretion of stars formed in external galaxies. In SAMs, stellar growth is always dominated by in situ star formation, because they signiﬁcantly underpredict the fraction of mass growth from accreted stars relative to the simulations. In addition, SAMs overpredict the overall gas accretion rates relative to the simulations, and overestimate the fraction of “hot” relative to “cold” accretion. We discuss the reasons for these discrepancies, and identify several physical processes that are missing in our SAM and in other semi-analytic models but which should be included. We also highlight physical processes that are neglected in the simulations studied here, but which appear to be crucial in order to understand the properties of real galaxies.

Key words: galaxies: formation; galaxies: evolution; methods: N-body-simulations; methods: numerical

⋆ E-mail: mhirsch@usm.lmu.de

c 2002 RAS

1 INTRODUCTION

The dark energy dominated dark matter paradigm (ΛCDM) provides a successful theoretical model for understanding and simulating galaxy formation. Within this framework the

large-scale structure of dark matter develops from initially small-scale density ﬂuctuations, in a bottom-up scenario only driven by gravitational forces (Blumenthal et al. 1984). The baryonic component follows the dark matter, is shockheated, cools and condenses into galaxies (White & Rees

- 1978a; Rees & Ostriker 1977). The assembly of dark matter halos, which domi-


nate the total matter content in the Universe, in large cosmological volumes can be followed with merger trees based on analytic approaches, e.g. using Monte-Carlo methods based on the extended Press-Schechter formalism (EPS, Press & Schechter 1974; Bower 1991; Bond et al. 1991; Somerville & Kolatt 1999; Neistein & Dekel 2008; Zhang et al. 2008; Angulo & White 2010). Alternatively, the full dynamical evolution of dark matter can be accurately followed with collisionless particles in direct numerical simulations which are, by now, well resolved at the relevant scales (Frenk et al. 1988; Navarro et al. 1997; Moore et al. 1999; Klypin et al. 1999; Bode & Ostriker 2003; Springel et al. 2005, 2008; Diemand et al. 2008; Klypin et al. 2010). Here the identiﬁcation of dark matter halos and the construction of merger trees is considerably more demanding and various diﬀerent approaches have been discussed (e.g. Davis et al. 1985; Kauﬀmann et al. 1993; Ghigna et al. 2000; Springel et al. 2001; Weller et al. 2005; Genel et al. 2008; Fakhouri & Ma 2008; Planelles & Quilis 2010; Skory et al. 2010 and references therein). In particular, Springel et al. (2005) constructed and analysed merger trees for the Millennium simulation, using the “Friends of Friends” (FOF) technique (Davis et al. 1985) to identify halos, and Subfind (Springel et al. 2001) to identify sub-halos (bound objects within larger virialized dark matter halos).

Simulations of the formation and evolution of the galaxies which are believed to inhabit these dark matter halos are more demanding, theoretically as well as numerically. Additional gas-dynamical and radiative processes, such as the formation of stars and black holes as well

- as the respective feedback, have to be taken into account. To follow the evolution of galaxies two main approaches have been developed over the past decades: Semianalytic models (SAMs) and direct cosmological simulations. SAMs (White & Frenk 1991; Kauﬀmann et al. 1993; Cole et al. 1994; Kauﬀmann 1996; Somerville & Primack 1999; Kauﬀmann et al. 1999; Kauﬀmann & Haehnelt 2000; Cole et al. 2000; Springel et al. 2001; Hatton et al. 2003; Kang et al. 2005; Baugh et al. 2005; Khochfar & Silk 2006a; Croton et al. 2006; Bower et al. 2006; De Lucia & Blaizot


- 2007; Somerville et al. 2008a; Font et al. 2008; Guo et al.


- 2009; Weinmann et al. 2009) use pre-calculated dark matter merger trees either from EPS or direct cosmological simulations and follow the formation of galaxies with simpliﬁed, physically and observationally motivated, analytic recipes. The computational costs of this approach are typically low, and the inﬂuence of diﬀerent physical mechanisms can be investigated separately in a straightforward way. Modern SAMs are quite successful at reproducing observed statistical properties of galaxies in large cosmological volumes over a large range of galaxy masses and redshifts (e.g. Somerville et al. 2008a; Guo et al. 2010). Disadvantages are that the dynamics of the baryonic component (gas and stars) and the interaction between baryonic matter and dark matter are not followed directly and that in many


cases the assumed models are simpliﬁed and use a large number of free parameters to ﬁt diﬀerent observations simultaneously (Somerville et al. 2008a; Benson & Bower 2011; Bower et al. 2010).

Direct cosmological galaxy formation simulations can follow the evolution of dark matter and gas explicitly. Even though they treat the underlying dynamics more correctly than SAMs, the spatial and mass resolution, at present, is not high enough to accurately simulate intermediate and low mass galaxies in large cosmological volumes. In addition, small scale processes like e.g. the formation of stars and black holes with the associated feedback has to be computed in a simpliﬁed manner with sub-grid/subresolution models (Cen & Ostriker 1993; Dave´ et al. 2001; Springel & Hernquist 2003; Maller & Bullock 2004; Nagamine et al. 2005; Keresˇ et al. 2005a; Navarro et al. 2009; Schaye et al. 2010a), which again require the introduction of parameters. Ab initio cosmological zoom simulations with proper cosmological boundary conditions enable direct simulations of the baryonic physics of certain regions of interest at higher resolution, either limited to small cosmological volumes (Crain et al. 2009) or, more popularly, individual halos (Navarro & Steinmetz 1997; Governato et al. 2007; Naab et al. 2007; Brooks et al.

- 2009a; Oser et al. 2010; Wadepuhl & Springel 2011; Puchwein et al. 2010; Teyssier et al. 2010; Sawala et al.
- 2010; Piontek & Steinmetz 2011; Agertz et al. 2011). These simulations can attain very high resolution, and provide a way to resolve galaxies of very diﬀerent masses with the appropriate resolution in each case. However they are very time consuming and therefore not currently feasible for representative studies of large populations of galaxies. In addition, the sub-resolution models are uncertain and it is still unclear how sensitive various results may be to the details of these sub-grid models or the parameter values.


Both approaches make deﬁnite predictions for the evolution of galaxy properties at various masses over cosmic time. Because of their greater computational eﬃciency, SAMs generally include more models for physical processes than current numerical simulations, and because of their greater ﬂexibility, it has been possible to tune them to obtain quite good agreement with a broad range of galaxy properties in the local Universe. SAMs have also been shown to reproduce the statistical properties (e.g. luminosity and stellar mass functions, star formation rates) of high redshift galaxies (z ∼< 6) quite well, at least for massive galaxies (mstar ∼> 1010M⊙; e.g. Somerville et al. 2011; Fontanot et al. 2009). Therefore we might expect SAMs to do a better job of reproducing the observed universe than the simulations, but we might worry that they could do so for the wrong reasons. Because there is a great deal of uncertainty in many of the important processes, and most of the physical recipes contain free parameters, if one physical process (e.g. gas cooling and accretion) is modelled inaccurately in the SAM, it is currently possible to compensate by tuning a competing process (such as feedback). By running SAMs within merger trees extracted from numerical hydrodynamic simulations, in order to constrain the evolution of the dark matter component to be the same in both cases, we can isolate various physical processes and attempt to improve the accuracy of the semi-analytic recipes. At the same time, by comparing the detailed predictions of the forma-

tion histories of galaxies in the simulations with the SAM predictions, we may gain insights into the origin of existing discrepancies between the simulations and the real universe.

Various comparison studies between simulations and SAMs for large galaxy populations as well as individual halos have been discussed in the literature (we summarize these results in section 2) following diﬀerent philosophies. For some studies only individual physical processes, like cooling, were investigated (Lu et al. 2010; Benson & Bower 2011), while others focussed on the evolution of individual objects, as a high-mass galaxy cluster (Saro et al. 2010) or a single disk galaxy (Stringer et al. 2010).

Our approach is new in many respects. We compare the evolution of individual halos but use the, up to now, largest number of high-resolution zoom simulations (48), presented in Oser et al. (2010). The simulations cover dark matter halos in the mass range of 2.4 ×1011M⊙ < MHalo < 3.3 × 1013M⊙. Although a limited complement of physical processes have been taken into account in the simulations, the more massive of these halos have been shown to represent fairly well the evolution of observed massive galaxies (Oser et al. 2010). These simulations are compared to results from the full SAM of Somerville et al. (2008a), which has been shown to represent present day galaxy properties reasonably well over a wide range of masses, as well as different stripped down versions. The SAMs are run within merger trees extracted directly from the numerical simulations. In addition, we compare both model predictions to observations at diﬀerent redshifts and point out where the respective models succeed or fail either to match each other and/or the observations.

The paper is organized as follows: In section 2 we discuss results from previous comparisons between SAMs and simulations. The hydrodynamical simulations and the mergertree construction method used for this study are discussed in section 3 and we brieﬂy review the ingredients of the Somerville et al. (2008a) SAM in section 4. The redshift evolution of the baryonic components in simulations and SAMs is compared in section 5 followed by a comparison to observations in section 6. In section 7 we summarize and discuss our main results. A resolution study for individual halos can be found in the Appendix.

- 2 PREVIOUS COMPARISON STUDIES


Previous quantitative comparisons between simulations and SAMs have either focused on whole populations of galaxies (Benson et al. 2001; Yoshida et al. 2002; Helly et al. 2003; Cattaneo et al. 2007; Benson & Bower 2011; Lu et al. 2010) or individual objects like a galaxy cluster (Saro et al. 2010) and a single disk galaxy (Stringer et al. 2010). Helly et al. (2003) compared the eﬃciency of gas cooling for diﬀerent dark matter halos as a function of redshift between a (50Mpc/h)3 SPH (Smoothed-Particle-Hydrodynamics) simulation (Hydra, Pearce et al. 2001) excluding star formation, heating and feedback and a stripped down version – without star formation or feedback – of the Galform SAM (Cole et al. 2000). For z = 0 they ﬁnd good agreement of the cold gas mass between the SPH simulation and the SAM. At high redshifts, however, more gas tends to cool in lowmass halos in the simulation due to the limited numerical

resolution. Still, they conclude that simulations and SAMs give consistent results for the evolution of cooling galactic gas and conﬁrm earlier ﬁndings of Benson et al. (2001) and Yoshida et al. (2002).

Cattaneo et al. (2007) did consider star formation and supernova feedback for a similar comparison in a 34.19Mpc3 volume. For the SPH-simulation they used TreeSPH (Dave et al. 1997 and the input for their SAMcode GalICS (Hatton et al. 2003) was the merger trees constructed from the dark matter component of the SPHsimulation. The SAM did not include a photo-ionising background but followed the cooling by metals, while the simulations did include a photo-ionizing background and assumed primordial composition of He and H. The star formation prescription in the SAM was quite standard (star formation occurs above a certain gas surface density, according to a Kennicutt-Schmidt-like relation), and a simple recipe for SN-driven winds was also included. In order to replicate AGN feedback, star formation is quenched when the bulge component of a galaxy reaches a critical mass. For the comparison they used two diﬀerent SAM versions: one with no feedback and the ‘full’ model. In general, they found good agreement between simulations and the no-feedback model for the baryonic mass functions at diﬀerent redshifts and in diﬀerent environments. Moreover, simulations and the no-feedback SAM made similar predictions for the ‘hot’ and ‘cold’ mode gas accretion histories of galaxies (e.g. Keresˇ et al. 2005b). However, at low redshifts, much less gas was left over in the simulation than in the no-feedback SAM with both approaches over-predicting the observed baryonic mass function, in particular at the high mass end. The full SAM, on the other hand, matched the observations due the inclusion of supernova-driven outﬂows and AGN feedback, which suppresses gas cooling in large halos. They concluded that the simulations and the no-feedback model failed as a consequence of missing physics rather than computational inaccuracies.

Saro et al. (2010) compared the galaxy populations within a massive cluster (Mcluster = 1.14 × 1015M⊙) using a high-resolution cosmological re-simulation run with Gadget2 (Dolag et al. 2009) and the SAM model of De Lucia & Blaizot (2007). They focused on diﬀerences between the central and the satellite galaxies considering only gas cooling and star formation and neglecting any form of feedback. In general, they ﬁnd similar statistical properties for the galaxy populations, e.g. the stellar mass function with a few remarkable object by object diﬀerences. The central galaxy in the simulation starts with a more intense and shorter initial burst of star formation at high redshift and forms fewer stars at low redshift than in the SAM. While in the SAM all stars in the central galaxy are formed in its progenitors, in the simulations the ﬁnal stellar mass is larger than the sum of all progenitors. Satellite galaxies can lose up to 90 per cent of their stellar mass due to tidal stripping – a process, which is, however, not included in the De Lucia & Blaizot (2007) semi-analytic model, nor in most models discussed in the recent literature.

Moreover, Stringer et al. (2010) presented a comparison for the evolution of a single disk galaxy using the SPHcode Gasoline (Wadsley et al. 2004) and the semi-analytic model Galform (Bower et al. 2006) based on the dark matter merger history of the simulation. They ﬁnd that the two

techniques show a potential consistency for the evolution of the stellar and gas components by assuming the same physics and the same initial conditions. They try to mimic in the SAM the ‘blast wave’ SN feedback implemented in the simulation, i.e. after a supernova explosion no cooling is allowed in a certain volume. However, using the Galform model as described in Bower et al. (2006) (including chemical enrichment, supernova and AGN feedback), the resulting system is not recognisably the same as predicted by simulations. At all redshifts, the stellar mass is much larger and the hot gas fraction is much lower in the simulation than in the SAM.

Finally, Lu et al. (2010) and Benson & Bower (2011) focus on the algorithms for gas cooling in SAMs in great detail. Benson & Bower (2011) compare cold (rapid) and hot (slow) accretion rates in the Galform SAM and in simulations from Keresˇ et al. (2009) (50 Mpc/h, 2 × 2883 particles). They used their ‘full’ model including feedback and metal cooling, although these processes are not included in the simulations. Moreover, they modiﬁed their SAM by adopting an updated calibration for the transition between the rapid and slow cooling regime following the methodology of Birnboim & Dekel (2003a). They ﬁnd reasonably good agreement for the hot and cold mode accretion fraction in the SAM and the simulations and thus, they conclude that the cold-mode physics is already adequately accounted for in SAMs. In the study of Lu et al. (2010) ﬁve diﬀerent SAMs (‘Munich’ model: Croton et al. 2006, ‘Kang’ model: Kang et al. 2005, ‘Galform’ model: Cole et al. 2000, ‘GalICS’ model: Hatton et al. 2003 and the ‘Somerville’ model: Somerville & Primack 1999) are compared to the simulations of Keresˇ et al. (2009), without considering any feedback or metal enrichment in either method. They ﬁnd a signiﬁcant diﬀerence between hot and cold accretion rates: compared to the simulations, the cold mode accretion rates are too low and the hot mode accretion are too high in SAMs. They construct a modiﬁed cooling recipe for the SAM to enable simultaneous hot and cold accretion, resulting in much better agreement between the SAMs and the simulations.

Throughout the course of this paper, we will refer back to these studies and comment upon the similarities and differences with our results.

- 3 THE SIMULATION AND MERGER TREE CONSTRUCTION


3.1 Simulation setup

The cosmological zoom simulations presented in this paper are described in detail in Oser et al. (2010) and we brieﬂy review the simulation setup here. The dark matter halos for further reﬁnement were selected from a dark matter only N-body simulation (Gadget-2, Springel et al. 2005) with a comoving periodic box length of L = 100 Mpc and 5123 particles (see also Moster et al. 2010). We assume a ΛCDM cosmology based on the WMAP3 measurements (see e.g. Spergel et al. 2003) with σ8 = 0.77, Ωm = 0.26, ΩΛ = 0.74, and h = H0/(100 kms−1) = 0.72. The simulation was started at z = 43 and run to z = 0 with a ﬁxed comoving softening length of 2.52 h−1kpc and a dark matter particle mass of MDM = 2 × 108M⊙/h. Starting at an

expansion factor of a = 0.06 we constructed halo catalogues for 94 snapshots until z = 0 separated by ∆a = 0.01 in time. From this simulation, we picked 48 halos identiﬁed with the halo ﬁnder algorithm FOF at z = 0. To construct the high-resolution initial conditions for the re-simulations, we trace back in time all particles that are closer than 2·r200 to the center of the halo in any snapshot and replace them with dark matter as well as gas particles at higher resolution (Ωb = 0.044, ΩDM = 0.216). In the high resolution region the dark matter particles have a mass resolution of mDM = 2.1 · 107M⊙h−1, which is 8 times higher than in the original simulation, and the gas particle masses are mGas = mStar = 4.2 · 106M⊙h−1. Individual cases were run at 64 times higher mass resolution and 4 times higher spatial resolution. The re-simulated halos cover a mass range of two orders of magnitude (2.4×1011M⊙ < MHalo < 3.3×1013M⊙).

For modeling the gas component we use the entropy conserving formulation of SPH (Gadget-2, Springel et al. 2005). We include star formation and cooling for a primordial composition of hydrogen and helium (Theuns et al. 1998). The cooling rates are computed under the assumption that the gas is optically thin and in ionization equilibrium. Furthermore, our simulations include a spatially uniform redshift dependent UV background radiation ﬁeld according to Haardt & Madau (1996), where reionization takes place at z ≈ 6 and the radiation ﬁeld peaks at z ≈ 2 − 3.

To model star formation and SN feedback we use the approach of Springel & Hernquist (2003). In this model, the ISM is treated as a two-phase medium where clouds of cold gas form from cooling of hot gas and are embedded in the hot gas phase assuming pressure equilibrium. The hot gas is heated by supernovae and can evaporate the cold clouds. Stars form from the cold gas whenever the local density exceeds a threshold density (ρ > ρth = 0.205cm−3). The star formation rate is calculated by

dρ∗ dt

ρc t∗

= (1 − β)

![image 1](10_Bollinger_SIT-Pair-Quantum-Resistance_Nature2011_images/imageFile1.png)

![image 2](10_Bollinger_SIT-Pair-Quantum-Resistance_Nature2011_images/imageFile2.png)

(1)

Here, β is the mass fraction of massive stars, which are assumed to explode as supernovae type II, ρc is the density of cold gas and t∗ = t0∗(ρ/ρth)−1/2 is the star formation time scale. The supernova explosions heat the surrounding gas with an energy input of 1051 ergs. Springel & Hernquist (2003) used an idealized, isolated disk galaxy simulation to set the free parameters ρth and t0∗, by adjusting them to obtain a match to the observed Schmidt-Kennicutt relation. We adopt the same values of these parameters here.

3.2 Merger trees

We extract the merger trees for the dark matter component directly from the cosmological re-simulations as described in Hirschmann et al. (2010). For every snapshot at a given redshift, we ﬁrst identify individual dark matter haloes using a FOF (Friends-of-Friends) algorithm with a linking length of b = 0.2 (≈ 28kpc, Davis et al. 1985). In a second step we extract the subhalos of every FOF group using the Subfind algorithm (Springel et al. 2001). This haloﬁnder identiﬁes over-dense regions and removes gravitationally unbound particles. In this way we split the FOF group into a main or host halo and its satellite halos. In most cases, 90% of the total mass is located in the main halo.

![image 3](10_Bollinger_SIT-Pair-Quantum-Resistance_Nature2011_images/imageFile3.png)

Figure 1. Visualisation of merger trees for four re-simulated halos with diﬀerent masses: upper left:Mvir = 8 × 1012M⊙, upper right: Mvir = 1 × 1012M⊙, lower left: Mvir = 5 × 1011M⊙, lower right: Mvir = 1 × 1011M⊙. Black circles show the dark matter halo at every time-step of the simulations. The symbol size is proportional to the square root of the halo mass normalized to the halo mass at z=0. The yellow stars indicate the stellar mass, the blue and red ﬁlled circles the cold and hot gas mass within the virial radius of the dark matter halo. The symbol sizes for the baryons scale with the square root of the masses normalized to the maximum total baryonic mass

- at z=0.


The sizes and virial masses of the main halos (i.e. the most massive Subfind halos) are determined by a spherical overdensity criterion. The minimum halo mass is set to 20 particles (5×108M⊙/h). In the following, we will use isolated merger trees which are constructed only for the the main halos, i.e. the central objects of one FOF group identiﬁed by Subfind. The mass of a central object is deﬁned by the dark

matter mass within the virial radius using the overdensity approximation in the spherical collapse model according to Bryan & Norman (1998). The algorithm to connect the dark matter halos between the snapshots at diﬀerent redshifts is described in detail in Maulbetsch et al. (2007). The branches of the trees for z = 0 halos are constructed by connecting the halos to their most massive progenitors (MMP) at previous

snapshots. Thereby, halo j with nj particles at redshift zj with the maximum probability p(i,j) is chosen to be a MMP of halo i containing ni particles at redshift zi (where j < i). The probablity p(i, j) is deﬁned as

nov(i, j) nmax(i, j)

p(i,j) =

with (2) nov = ni(zi) ∩ nj(zj) and

![image 4](10_Bollinger_SIT-Pair-Quantum-Resistance_Nature2011_images/imageFile4.png)

nmax(i, j) = max(ni(zi), nj(zj))

Here, nov is the number of particles found in both halos and nmax is the particle number of the larger halo. We remove ‘fake’ haloes which exist only within one timestep and have no connection to any branch (halo masses are generally near to the resolution limit). The low redshift ends of the branches are then checked for mergers. A halo j at tj is assumed to merge into halo i at ti, if at least 50% of the particles of halo j are found in halo i. In case of a merger the branches are connected.

Note that the tree-algorithm is only applied to the dark matter particles – star or gas particles are not separately traced back in time. They are assumed to follow the evolution of the dark matter. Therefore, we assign to each dark matter halo in a tree a hot/cold phase gas mass by counting hot/cold gas particles within the virial radius of the central halo. The stellar and cold gas particles within 1/10 of the virial radius are deﬁned as the stellar and gas mass of the central galaxy. We distinguish between hot and cold gas particles by using the following deﬁnition:

log T < 0.3 log ρ + 3.2 → cold (3) log T > 0.3 log ρ + 3.2 → hot (4)

Note that the above discrimination between hot and cold gas was established by looking directly at the phase diagrams of the re-simulations, where we have divided between the gas in the disk heated by SN feedback and the shock heated gas. With the above deﬁnition for cold gas we mainly capture the dense, star-forming gas.

In Fig. 1 we show a visualization of four merger trees of re-simulated halos with virial masses of 8 × 1012M⊙, 1 × 1012M⊙, 5 × 1011M⊙ and 1 × 1011M⊙. The size of the black circles approximates the dark matter halo mass, the yellow stars the stellar mass within the virial radius and the blue and red ﬁlled circles the cold and hot gas component, respectively. The symbol sizes scale with the square root of mass normalized to the ﬁnal dark matter halo mass (dark matter component) and to the ﬁnal baryonic mass (star, hot and cold gas mass). We clearly see that galaxies at high redshift contain more cold gas, which either turns into stars or is heated towards lower redshifts. In general, for more massive halos the fraction of cold gas and stars at z = 0 is lower.

To study the inﬂuence of numerical resolution on the evolution of the dark matter and the baryonic components we have simulated a few halos with 4 × higher spatial resolution (= 64 × higher mass resolution) than the original dark matter simulation. A comparison of the results can be found in the Appendix. The overall mass assembly of the main halos and the number of major mergers do not show any signiﬁcant variation, although the number of identiﬁed minor mergers increases due to the higher resolution. Overall, we

conclude that our results are well-converged and would not change signiﬁcantly if we improved the resolution.

4 THE SEMI-ANALYTIC MODEL

The merger-trees constructed as described above are used as input for the semi-analytic model described in Somerville et al. (2008a, hereafter S08). The SAM makes use of merger trees for “isolated” halos only, and treats the evolution of sub-structure within virialized halos using semianalytic approximations. The ‘full’ version includes photoioniziation, gas cooling, star formation, SN feedback, metal enrichment, and black hole growth in a radio and quasar mode with corresponding feedback. However, to provide a more meaningful comparison to our simulations, we do not only consider the ‘full’ version, but also ‘stripped down’ models by separately switching oﬀ AGN feedback, metal cooling, Supernova-driven winds, and ‘thermal’ Supernova feedback. We consider the following diﬀerent versions:

- • NF: no Feedback, primordial metallicity
- • SN: thermal SN-feedback, primordial metallicity
- • SNWM: thermal SN-feedback, SN-driven Winds,


metal cooling

• FULL: ‘full’ version, including thermal SN-feedback, SN winds, metal cooling, and AGN feedback

In the following we brieﬂy summarize how the diﬀerent physical mechanisms are implemented and how they diﬀer from the ones in the simulations. For full details we refer the reader to Somerville et al. (2008a). In Table 1, we provide a summary of the galaxy formation parameters used here. In Table 2, we give an explicit overview of the physical recipes assumed in the diﬀerent SAM versions starting from the NF model. These are compared to the physics which are implemented in simulations.

(i) Radiative cooling: The rate of gas condensation via atomic cooling is computed based on the model proposed by White & Frenk (1991). The cooling time is computed as

3/2µmpkT ρg(r)Λ(T, Zh)

. (5)

tcool =

![image 5](10_Bollinger_SIT-Pair-Quantum-Resistance_Nature2011_images/imageFile5.png)

Here, T is the virial temperature, µmp is the mean molecular mass, ρg(r) is the radial density proﬁle of the gas and Λ(T, Zh) is the cooling function, which is temperature and metallicity dependent. The cooling time is the time required for the gas to radiate away all its energy starting at the virial temperature. The gas density proﬁle ρg(r) is assumed to follow an isothermal sphere: ρg(r) = mhot/(4πrvirr2). Putting this expression in Eq. 5 one can solve for a cooling radius rcool. Within the cooling radius all gas can cool within the cooling time tcool. The cooling rate for the mass within rcool is

dmcool dt

=

![image 6](10_Bollinger_SIT-Pair-Quantum-Resistance_Nature2011_images/imageFile6.png)

- 1

![image 7](10_Bollinger_SIT-Pair-Quantum-Resistance_Nature2011_images/imageFile7.png)

- 2


rcool rvir

1 tcool

. (6)

mhot

![image 8](10_Bollinger_SIT-Pair-Quantum-Resistance_Nature2011_images/imageFile8.png)

![image 9](10_Bollinger_SIT-Pair-Quantum-Resistance_Nature2011_images/imageFile9.png)

Following Springel et al. (2001) and Croton et al. (2006) it is assumed that the cooling time is equal to the halo dynamical time tcool = tdyn = rvir/Vvir. Two diﬀerent modes of accretion are distinguished: the rapid (“cold mode”) and the slow (“hot mode”) cooling regime. In the rapid cooling

- Table 1. Summary of the galaxy formation parameters in the ﬁducial model, which are partly deviating from the ones in S08

![image 10](10_Bollinger_SIT-Pair-Quantum-Resistance_Nature2011_images/imageFile10.png)

Parameter Description Fiducial value Quiescent star formation

![image 11](10_Bollinger_SIT-Pair-Quantum-Resistance_Nature2011_images/imageFile11.png)

![image 12](10_Bollinger_SIT-Pair-Quantum-Resistance_Nature2011_images/imageFile12.png)

AKS Normalization of Kennicutt law 1.67 × 10−4 M⊙ yr−1 kpc−2 NK Power-law index in Kennicutt law 1.4 Σcrit Critical surface density 6M⊙ pc−2

![image 13](10_Bollinger_SIT-Pair-Quantum-Resistance_Nature2011_images/imageFile13.png)

Burst star formation µcrit Critical mass ratio for burst activity 0.1

![image 14](10_Bollinger_SIT-Pair-Quantum-Resistance_Nature2011_images/imageFile14.png)

SN feedback ǫ0SN Normalization of reheating fct 1.3 αrh Power-law slope of reheating fct 2.0 Veject Velocity scale for ejecting gas 120 km s−1 χre−infall Time-scale for re-infall of ejected gas 0.1 Chemical evolution y Chemical yield 1.5 Black hole growth

![image 15](10_Bollinger_SIT-Pair-Quantum-Resistance_Nature2011_images/imageFile15.png)

![image 16](10_Bollinger_SIT-Pair-Quantum-Resistance_Nature2011_images/imageFile16.png)

ηrad Eﬃciency of conversion of rest mass to radiation 0.1 Mseed Mass of seed black hole 100 M⊙ fBH,ﬁnal Scaling factor for mass after merger 0.8 fBH,crit Scaling factor for critical BH mass 0.4

![image 17](10_Bollinger_SIT-Pair-Quantum-Resistance_Nature2011_images/imageFile17.png)

AGN-driven winds ǫwind Coupling factor for AGN-driven winds 0.5

![image 18](10_Bollinger_SIT-Pair-Quantum-Resistance_Nature2011_images/imageFile18.png)

Radio-mode feedback κradio Normalization of ’radio mode’ accretion rate 2 × 10−3 κheat Coupling eﬃciency of radio jets with hot gas 1.0

![image 19](10_Bollinger_SIT-Pair-Quantum-Resistance_Nature2011_images/imageFile19.png)

- Table 2. Overview of the diﬀerent physical mechanisms for galaxy formation assumed in the diﬀerent SAM versions and implemented in the simulations.


![image 20](10_Bollinger_SIT-Pair-Quantum-Resistance_Nature2011_images/imageFile20.png)

Model Gas cooling Star formation Metals Thermal SN feedack SN winds AGN feedback NF Yes Yes No No No No SN Yes Yes No Yes No No SNWM Yes Yes Yes Yes Yes No FULL Yes Yes Yes Yes Yes Yes SIM Yes Yes No Yes No No

![image 21](10_Bollinger_SIT-Pair-Quantum-Resistance_Nature2011_images/imageFile21.png)

![image 22](10_Bollinger_SIT-Pair-Quantum-Resistance_Nature2011_images/imageFile22.png)

![image 23](10_Bollinger_SIT-Pair-Quantum-Resistance_Nature2011_images/imageFile23.png)

![image 24](10_Bollinger_SIT-Pair-Quantum-Resistance_Nature2011_images/imageFile24.png)

![image 25](10_Bollinger_SIT-Pair-Quantum-Resistance_Nature2011_images/imageFile25.png)

![image 26](10_Bollinger_SIT-Pair-Quantum-Resistance_Nature2011_images/imageFile26.png)

![image 27](10_Bollinger_SIT-Pair-Quantum-Resistance_Nature2011_images/imageFile27.png)

regime, where the cooling radius is larger than the virial radius rcool > rvir, the cooling rate is set to the gas accretion rate, which is governed by the mass accretion history. Slow cooling occurs whenever the cooling radius is smaller than the virial radius rcool < rvir. Here, the cooling rate is calculated according to eq. 6. The same cooling function is used in the simulations, however, the cooling rate is calculated locally based on the density and temperature.

(ii) Photo-ionization: Photo-ionization heating is considered in all four SAM versions. It causes halos below a certain ﬁltering mass MF to have a lower baryon fraction than the universal average. The collapsed baryon fraction

- as a function of redshift and halo mass is parameterized by the expression:


fb [1 + 0.26MF (z)/Mvir]3

fb,coll(z, Mvir) =

, (7)

![image 28](10_Bollinger_SIT-Pair-Quantum-Resistance_Nature2011_images/imageFile28.png)

where fb is the universal baryon fraction. The ﬁltering mass is a function of redshift and depends on the reionization history of the universe (Kravtsov et al. 2004). Note that photo-ionization heating has very little eﬀect on galaxies with circular velocities larger than about 30–50 km/s, and therefore plays a minor role in our study, which mainly focusses on larger galaxies. In the simulations a UV heating background is implemented instead of a ﬁltering mass. However, the ﬁltering mass treatment adopted in the SAM is based on the results of numerical hydrodynamic simulations (Kravtsov et al. 2004), so we do not expect this to introduce any signiﬁcant discrepancy (see also Hambrick et al. 2009 and references therein).

(iii) Star formation: The SAM distinguishes between quiescent star formation in isolated disks and merger-driven starbursts. The quiescent star formation is based on the the

empirical Schmidt-Kennicutt (SK) relation (Kennicutt 1989, 1998). The star formation rate density is calculated according to

ΣSFR = AKennΣNgasK (8)

with AKenn = 1.67×10−4, NK = 1.4, and Σgas is the surface density of cold gas in the disk. The normalisation uses the conversion factor appropriate for a Chabrier IMF (Chabrier 2003a). The gas follows an exponential disk (proportional to the scale-length of the stellar disk) and only gas above a critical surface density threshold Σcrit (= 6M⊙/pc2) is available for star formation.

Star formation during starbursts is driven by merger events. The star formation rate is assumed to be a function of the mass ratio and the combined cold gas content of the merging galaxies, the bulge to total stellar component and burst timescale. The starburst eﬃciency as a function of these variables is based on hydrodynamic simulations of binary galaxy mergers (see references in S08). While in the SAMs we use a 2D implementation for quiescent star formation following the Schmidt-Kennicutt law and a simple recipe for starbursts, in simulations, the star formation eﬃciency (in both quiescent and burst modes) is determined by the local 3D cold gas density. The normalization of the Schmidt-Kennicutt law was chosen by requiring a smooth, isolated disk to lie on the observed relation (see Springel & Hernquist 2003).

(iv) Supernova feedback: Exploding supernovae deposit thermal energy in the interstellar medium, which may heat the cold gas, and in certain situations may drive winds that unbind the gas from the potential well of the dark matter halo. In the SAM, these processes are modeled by removing cold gas from the galaxy and depositing it either in the hot gas reservoir, where it can cool again fairly quickly, or ejecting it from the halo, where it can fall back again on a longer timescale. We will refer to the former

- as “thermal” SN feedback and the latter as “SN-driven winds”. The SN model includes only the thermal SN FB, while the SNWM includes both thermal SN feedback and SN-driven winds. While supernova driven winds have been implemented in some numerical hydrodynamic simulations (e.g. Oppenheimer & Dave´ 2008), only thermal SN feedback is implemented in the simulations used in this study.


The heating rate of the cold gas is given by

m˙ rh = ǫSN0

Vdisk 200 km/s

![image 29](10_Bollinger_SIT-Pair-Quantum-Resistance_Nature2011_images/imageFile29.png)

αrh

m˙ ∗, (9)

where ǫSN0 and αrh are free parameters and m˙ ∗ is the star formation rate. We assume the circular velocity Vdisk to be the maximum rotation velocity of the dark matter halo, Vmax. To estimate reasonable values for the parameter ǫSN0 we follow the prescription of Kauﬀmann et al. (1993), in which it is assumed that the energy released from supernovae heats the gas to the virial temperature of the halo (corresponding to a value of αrh = −2). Using this recipe, the thermal energy rate is given as

E˙thermal = ǫthermal ηSN ESN m˙ ∗ = m˙ rh Vdisk2 , (10)

where ηSN is the number of supernovae expected per solar mass of stars formed (= 4 × 10−3M⊙−1), ESN the kinetic energy of the ejecta from each supernova (≈ 1051erg) and

ǫthermal the eﬃciency with which supernova energy is deposited in the gas, which is highly uncertain. With equations 9 and 10 ǫSN0 is deﬁned as:

ηSN ESN (200km/s)2

ǫSN0 = ǫthermal

, (11)

![image 30](10_Bollinger_SIT-Pair-Quantum-Resistance_Nature2011_images/imageFile30.png)

We assume a value for the thermal eﬃciency of ǫthermal ≈ 0.16.

Additionally we assume to have a kinetic SN feedback, i.e. reheated gas can be blown out of the halo. Thereby, the fraction of reheated gas, which is ejected from the halo into the intergalactic medium (IGM), is given by

feject(Vvir) = 1 +

Vvir Veject

![image 31](10_Bollinger_SIT-Pair-Quantum-Resistance_Nature2011_images/imageFile31.png)

αeject −1

(12)

with αeject = 6 and Veject a free parameter (≈ 100 − 150 km/s). Note that using this deﬁnition the total amount of released energy from SN explosions is not exceeded.

Moreover, the ejected gas can re-collapse onto the halo at later times and then is available for cooling. As in Springel et al. (2001) and De Lucia & Blaizot (2007) the rate of reinfall of rejected gas is given by

m˙ reinfall = χreinfall

meject tdyn

![image 32](10_Bollinger_SIT-Pair-Quantum-Resistance_Nature2011_images/imageFile32.png)

(13)

Here, χreinfall is a free parameter, meject is the mass of the ejected gas outside of the halo and tdyn = rvir/Vvir is the dynamical time of the halo. This treatment is quite similar to that used in simulations which explicitly include large-scale winds (e.g. Oppenheimer & Dave´ 2008), however, as noted above the simulations considered here do not include such a treatment of winds, and the thermal energy deposition that is included is not able to drive gas out of the galaxies.

- (v) Metal enrichment: To track the production of metals, we assume that, together with a parcel of new stars dm∗ a certain mass of metals dMZ = ydm∗ is created and instantaneously mixed with the cold gas in the disc. The yield is assumed to be constant and is treated as free parameter. Whenever new stars are formed, they are assumed to have the metallicity of the cold gas at this time step. When metals get ejected from the disc due to SN-winds, either the metals are mixed with the hot gas or ejected from the halo into the ‘diﬀuse’ IGM in the same proportion as reheated cold gas. Note that only metal enrichment due to Supernovae TypeII is tracked. Note that in our simulations we consider only primordial metallicity cooling and no metal evolution is included.
- (vi) Black hole growth and AGN feedback: Every “top level” halo (halo with no progenitors) in the merger tree is seeded with a black hole with mass ∼ 100M⊙. Black holes can grow by two channels: quasar mode and radio mode. The quasar mode is the bright mode of black hole growth observed as optical or X-ray bright AGN radiating at a signiﬁcant fraction of their Eddington limit (L ≈ (0.1−1)LEdd; Vestergaard 2004; Kollmeier et al. 2006). Such bright AGN are believed to be fed by optically thick, geometrically thin accretion disks (Shakura & Sunyaev 1973). In contrast, AGN activity in the radio-mode is much less dramatic. A large fraction of massive galaxies are detected at radio wavelengths (Best et al. 2007) without showing characteristic emission lines of classical optical or X-ray bright quasars (Kauﬀmann et al. 2008). Their accretion rates are believed


to be a small fraction of the Eddington rate and they are radiatively extremely ineﬃcient. Even if AGN spend most of their time in the radio-mode, they gain most of their mass during the short and Eddington limited episodes of quasar phases which in the model are assumed to be triggered by merger events. The energy released during the rapid growth of the black holes can drive powerful galactic scale winds that sweep cold gas out of the galaxy.

In contrast to the quasar mode, the radio mode has lowEddington ratio accretion rates, is radiatively ineﬃcient and associated with eﬃcient production of radio jets that can heat gas in a quasi-hydrostatic hot halo. Assuming BondiHoyle accretion combined with an isothermal cooling ﬂow solution (Nulsen & Fabian 2000) we calculate the accretion rate in the radio mode

m˙ radio = κradio

kT Λ(T, Zh)

![image 33](10_Bollinger_SIT-Pair-Quantum-Resistance_Nature2011_images/imageFile33.png)

M• 108M⊙

![image 34](10_Bollinger_SIT-Pair-Quantum-Resistance_Nature2011_images/imageFile34.png)

. (14)

Note that the central black hole accretes at this rate whenever hot halo gas is present (‘hot mode’ accretion, rcool < rvir). The energy that eﬀectively couples to and heats the hot gas is given by Lheat = κheatηradm˙ radioc2. Assuming that all the hot gas is at the virial temperature of the halo, the heating rate is given by

Lheat 3/4 Vvir2

m˙ heat =

![image 35](10_Bollinger_SIT-Pair-Quantum-Resistance_Nature2011_images/imageFile35.png)

(15)

The net cooling rate is then the usual cooling rate minus the heating rate from the radio-mode. Note that in our simulations, black hole growth and AGN feedback is not implemented.

Note that in merger trees from N-body simulations it may happen that the total mass of two merging halos at the beginning of a merger event is larger than the mass of the merged object afterwards, as during the merger particles can become unbound through tidal forces. Therefore, in the SAM we impose an upper limit on the hot halo mass of

Mhot = Mbar − Mstar,tot − Mcold − Meject (16)

Here, Meject is the mass ejected by winds, Mstar,tot and Mcold are the total star and cold gas masses within the merged halo and Mbar is the expected baryonic fraction of the halo. In this way, we prevent the sum of all baryonic components in the halo from exceeding the universal baryon fraction.

- 5 REDSHIFT EVOLUTION OF GALAXY PROPERTIES


In this section, we compare the cosmic evolution of the baryonic components of the galaxies and halos from the direct cosmological simulations to the results from the SAMs using the dark matter merger trees constructed from the resimulations. Here we only consider the evolution of the central galaxy in the main branch of the merger tree (largest progenitor halo). We divided the 48 halos into three bins according to their halo mass at z = 0 (every bin contains 16 halos) with 4.5 ×1012M⊙ < Mhalo < 4×1013M⊙ (high-mass), 1.2×1012M⊙ < Mhalo < 4.5×1012M⊙ (intermediate-mass), and 2.4 × 1011M⊙ < Mhalo < 1.2 × 1012M⊙ (low-mass). All comparisons in this Section make use of these bins.

Note also that a resolution study of the evolution of the

| | | |
|---|---|---|
| | | |


| | |
|---|---|
| | |


Figure 2. Total baryonic mass Mbar = Mgas + M∗, as a fraction of the cosmic baryon fraction times the halo mass fbar × Mhalo, as a function of lookback time for diﬀerent semi-analytic models (red: no feedback - NF; green: thermal Supernova feedback - SN; blue: thermal Supernova feedback, SN-driven winds and metal cooling - SNWM; purple: ‘full’ model including feedback from black holes - FULL) and for the SPH-re-simulation (black lines). Upper panel: Average values for the high mass bin with 4.5 × 1012M⊙ < Mhalo < 3.3 × 1013M⊙. Middle panel: Average values for the intermediate mass bin with 1.2×1012M⊙ < Mhalo < 4.5× 1012M⊙. Lower panel: average values for halo masses between 2.4 × 1011M⊙ < Mhalo < 1.2 × 1012M⊙.

baryonic component in SAMs based on 2 × and 4 × higher resolution simulations for a high- and a low mass halo can be found in the Appendix. In both cases the results based on the simulations with diﬀerent resolution are consistent.

5.1 Baryon fraction

For a ﬁrst comparison we compute the total baryonic mass Mbar = (Mstar + Mcold + Mhot) within the virial radius of

the main halo at every redshift for the simulations and the SAMs, respectively. In the re-simulations as well as in the SAMs, we consider the hot gas mass within the whole halo (i.e. within the virial radius), but the stars and the cold gas only of the central galaxy. We neglect contributions from substructures, diﬀuse stars and cold gas and satellite stars and cold gas. The baryonic mass is compared to the mass of available baryons within each halo, deﬁned as fbar × Mhalo, where fbar = 0.169 is the cosmic baryon fraction.

In Fig. 2 we show the average ratio of Mbar/(fbar × Mhalo), as a function of redshift for the three mass bins. The simulations are compared to the four SAM variants: NF, SN, SNWM, and FULL (for details see section 4). We expect the simulations to be most directly comparable to the NF or SN SAMs, as these SAMs include the same complement of physical processes as the simulations. Considering ﬁrst the NF model, we see that at low redshift, the SAM overestimates the baryon fraction in high mass halos, nearly agrees in intermediate mass halos, and slightly underestimates it in low mass halos. At high redshift, the NF SAM overestimates the baryon fraction at high redshift in high and intermediate mass halos, by a somewhat larger factor in the former. Turning next to the SN SAM, we see that the SAM predicts baryon fractions that are everywhere higher than the simulation results, though much more so for the high and intermediate mass halos. This is because the “thermal” SN feedback removes baryons from satellite galaxies, which are not counted in this census, and deposits them in the hot gas component which is included here. In the SNWM and FULL model, we see the impact of the SN-driven winds, which remove baryons from low-mass halos. The additional metal cooling in the SNWM and the FULL model does not have any impact on the total baryon fraction (only on the individual components, see next sections.) AGN feedback (in the FULL model) mainly prevents hot gas from cooling, so does not aﬀect the total baryon fraction signiﬁcantly, but will be important for the fraction of stars and hot gas, which will be discussed later.

5.2 Cold gas and stars

In Fig. 3 we show the evolution of the mass of condensed baryons (stars and cold gas, M∗ +Mcold) as a fraction of the total baryon mass as a function of redshift for the three mass bins. There is fairly good agreement between the simulations and the NF model over the whole redshift range, although the SAM is a little low at high redshift and a bit high at low redshift, particularly in the high and intermediate mass bin. In the SN model, the condensed baryon fraction is lowered by an almost ﬁxed factor relative to the NF model, and is signiﬁcantly lower than the simulation results. This suggests that the “thermal feedback” implemented in the simulation is less eﬀective than that included in the SAM.

It may seem curious that the SNWM model results are higher than the SN model, in fact close to the NF model in the high and intermediate mass bin. This is because the SNWM model includes metal cooling, leading to more efﬁcient star formation, while the SN model does not. The enhanced cooling rates partly compensate for the removal of cold gas via the SN-driven winds. In particular for the high- and intermediate mass bin the eﬀect of the SN winds is almost the opposite of that of metal cooling, resulting in

Figure 3. The evolution of the mass of the condensed baryons M∗+Mcold as a fraction of the total baryon mass as a function of redshift for the three mass bins. The condensed baryon fraction in halos of all masses is in reasonable agreement with the NF model at all redshifts. We can see that SN FB most strongly aﬀects the low-mass bin, while AGN FB aﬀects the high mass bin.

condensed baryon fractions close to the NF model. Only in the low-mass bin, the eﬀect of SN winds is not completely compensated by metal cooling (so condensed baryon fractions are below the NF model).

Finally, we see that in the FULL model, the AGN FB begins to quench star formation in the massive halos after about z ∼ 2, while it has little eﬀect on the lower mass bins.

In Fig. 4 we plot the evolution of the mean cold gas fraction of the central galaxy (in Fig. 3 we plotted cold gas plus stars). The eﬃciency of the conversion of cold gas to stars is clearly very diﬀerent between the simulations and SAMs. In both cases (simulations and SAMs), the ﬁnal cold gas fraction is increasing with decreasing halo mass. For the NF model, the SN and the SNWM model the cold gas fraction varies only slightly over time and is signiﬁcantly

Figure 4. Evolution of mean cold gas fraction Mcold/(fbar × Mhalo) of central galaxies. Mass bins and colors are the same as in Fig. 2. In all simulations the cold gas is depleted more eﬃciently than in the SAMs due to the large star formation eﬃciency at high redshifts. The red dotted line shows the cold gas fraction assuming ten times higher eﬃciency for star formation in the NF model (see Eq. 17).

higher (about an order of magnitude since z = 2) than for the simulations. This shows that the inclusion of SN FB has little impact on the gas fractions of galaxies. Only the FULL model shows a much stronger decrease of the gas fraction with cosmic time for massive galaxies due to the radio mode feedback. The initial cold gas fraction, at high redshifts 4 < z < 8, is almost the same for the simulations and SAMs. With evolving cosmic time the cold gas content decreases more rapidly in the simulations due to the more efﬁcient conversion into stars. The cold gas in the simulations is already converted into stars at high redshift and there is almost no more cold gas left to turn into stars at lower redshifts. This is similar to the results found in the comparison of Cattaneo et al. (2007).

Figure 5. Comparison of the stellar baryon fraction of the central galaxy between simulations and SAMs. The mass bins and colors are the same as in Fig. 2. For all mass bins the simulations agree best with the NF SAM, but form signiﬁcantly more stars at high redshifts z > 1. We can reproduce the simulation results fairly well with the NF SAM if we increase the star formation eﬃciency parameter by a factor of ten (red dotted lines). At high masses the AGN feedback (FULL) and at low masses the SN feedback (SN and SNWM) reduce the stellar baryon fractions in the SAMs.

In Fig. 5 we show the corresponding fraction of available baryons that are converted into stars in the central galaxy M∗/(fbar ×Mhalo), sometimes termed baryon conversion efﬁciency (Guo et al. 2009; Moster et al. 2010). In general, all simulations predict a decreasing (high-mass) or almost constant conversion eﬃciency with redshift (low-mass), whereas most SAMs predict increasing conversion eﬃciencies with the exception of high-mass galaxies in the FULL model with AGN feedback.

At low redshift z < 0.6 the conversion eﬃciencies agree well between the simulations and the NF model, with higher values for lower mass galaxies. However, at high redshifts

z > 1 the conversion eﬃciencies are signiﬁcantly higher for the simulations. This is in contrast to the results of Cattaneo et al. (2007), where the stellar masses agree at high redshift, but the SAM masses are larger than in simulations at low redshift. The diﬀerence in the behaviour of the SAMs and the simulations can be explained in terms of star formation eﬃciency. We changed the normalization of the SK-relation in the SAM by introducing a factor τ∗ in Eq. 8:

AKS τ∗

ΣNgasK, (17)

ΣSFR =

![image 36](10_Bollinger_SIT-Pair-Quantum-Resistance_Nature2011_images/imageFile36.png)

with τ∗ ≈ 0.1. The results of the NF model with this elevated star formation eﬃciency for the stellar and cold gas mass evolution is shown in Figs. 4 and 5. At high redshift, gas is more eﬃciently depleted and converted into stars, resulting in a better agreement between this ‘high SFE’ model and the simulations. However, for the high-mass and intermediatemass bin, the ‘high SFE’ model overpredicts the stellar fraction at low redshifts, suggesting that the Cattaneo et al. (2007) SAMs may also have had a higher SFE, and this could explain the discrepancy between their results and our initial results. In all three mass bins, the NF model produces the most massive stellar components. Again, the more eﬃcient cooling due to metals in the SNWM and the FULL model is cancelled by the eﬀect of winds and, for massive galaxies, also by AGN feedback, resulting in lower stellar masses than in the NF model. The separate behaviour of metal cooling and SN winds is the same as for the total condensed baryon fraction.

- 5.2.1 Star Formation Rates


To conﬁrm the previous ﬁndings we compare the star formation rates in Fig. 6. At very high redshifts z > 4, the SFRs in the simulations are much higher than in the SAMs. Only by assuming more eﬃcient star formation in the NF SAM (τ∗ = 0.1) do we obtain a reasonable match to the simulations. However, at z < 1.5, the high SFE model results in similar SFRs as the original NF model, as the larger SF eﬃciencies at high redshift lead to a more rapid depletion of the cold gas. In the simulation, the cold gas is rapidly turned into stars, resulting in lower SFRs at low redshifts compared to SAMs because of gas depletion. Only the FULL model shows a strongly decreasing SFR with decreasing redshift due to radio mode feedback, which becomes especially important for low redshifts and large halo masses. This result is consistent with the study of Saro et al. (2010), who compared their stripped-down versions of SAMs (with no feedback) to simulations, and found ﬁnd higher SFRs in the simulations for all galaxies within a cluster (central and satellites)

- at high redshifts and lower SFRs at low redshifts. In addition, Stringer et al. (2010) ﬁnd a similar discrepancy for the speciﬁc star formation rates at high redshifts (larger in simulations than in their SAM) and good agreement for low redshifts.


To better understand this discrepancy between simulations and SAMs we take a closer look at the respective implementations of star formation. According to Springel & Hernquist (2003), stars in the simulations are formed locally out of cold gas with the star formation rate density proportional to the local three-dimensional density

| | |
|---|---|
| | |


| | | | |
|---|---|---|---|
| | | | |


Figure 6. Evolution of the star formation rates in simulations and SAMs for three mass bins. The mass bins and colors are the same as in Fig. 2. At high redshifts, SFRs are higher in the simulations than in the SAMs, leading to more rapid depletion of the cold gas and very low SFRs at low redshifts.

of gas to the power of 1.4, ρSF ∝ ρ1.4/t∗. The star formation timescale t∗ was set to reproduce the observed local Schmidt-Kennicutt relation (SK) for a simulation of a smooth, isolated disk-dominated galaxy set up to resemble the Milky Way. In the SAMs the cold gas is assumed to settle into smooth exponential disks and stars form according to the SK-relation, implemented in terms of surface densities.

In Fig. 7, we plot the SFR surface density versus the surface density of the cold gas for the simulated galaxies at z = 2 and z = 4 within 1/10 rvir for all re-simulations. The black dashed line is the SK-relation assuming a Salpeter IMF (Salpeter 1955), as given in the original Kennicutt papers and as implemented in the simulations following Springel & Hernquist (2003). We would naively expect the simulations to follow this line. The red solid line shows the SK-relation for a Chabrier IMF (Chabrier 2003b), as as-

Figure 7. Star formation rate surface densities versus cold gas surface densities for the simulated galaxies within 1/10rvir. Black and blue stars correspond to diﬀerent re-simulations at z = 2 or z = 4, respectively. The red solid line illustrates the Kennicutt relation implemented in the SAM with a normalization consistent with a Chabrier IMF, while the black dashed line the one used to normalize the simulations (Springel & Hernquist 2003), which assumes a Salpeter IMF.

sumed in the SAMs. At a given gas surface density, the SFR surface densities of the simulations lie mostly above the expected SK-relation. The change of normalization associated with converting from Salpeter to Chabrier cannot account for the increased star formation eﬃciency in the simulations. In general, star formation in the cosmological simulations is about a factor of ﬁve more eﬃcient than for simulations of smooth isolated disks using the identical model (see Springel & Hernquist 2003). This discrepancy is a consequence of the clumpy structure of cold gas in the cosmological simulations. In the clumps the gas can reach higher local densities than in the idealized smooth disks that have been used by Springel & Hernquist (2003) to calibrate the star formation timescale by matching the SK-relation. As the implemented SK-relation is not linear, the structure of the cold gas distribution plays an important role for the overall star formation eﬃciency within the galaxies (see Teyssier et al. (2010) for a discussion on galaxy mergers). In other words, for any star formation model with a non-linear dependence on the local gas density (exponent larger than unity), a more clumpy gas distribution will eﬀectively increase the star formation eﬃciency. These combined eﬀects explain the much higher SF eﬃciencies at high redshift in the simulations relative to the SAMs.

- 5.2.2 Modes of Stellar Mass Growth


In the hierarchical picture, galaxies can grow their stellar masses in two ways: 1) by converting cold gas into stars in situ 2) by accreting already formed stars via mergers. We refer to these two modes as “in situ” and “accreted”. Our simulations exhibit two phases of growth, with a rapid early phase at z > 2 during which stars are formed in situ from infalling cold gas, followed by an extended phase at z < 3 during which the growth is primarily due to accretion of stars formed in external galaxies (Oser et al. 2010). We

Figure 8. Fraction of in situ to accreted stellar mass versus redshift for diﬀerent halo masses. The mass bins and colors are the same as in Fig. 2. In situ star formation dominates over accretion in all the SAM variants at all redshifts, in contrast to the simulations for which accretion dominates at late times, especially in massive halos.

now investigate whether the SAMs show the same behavior. In Fig. 8, we show the fraction of cumulative in situ over accreted stellar mass as a function of redshift for the three diﬀerent mass bins. For the SAMs the qualitative trend of a decreasing fraction of in situ growth is reproduced for the high mass bin. However, the fraction of in situ formed stars dominates over accreted stars for all models, all masses, and at all redshifts. This is in contrast with the simulations, where accretion dominates over in situ formation for massive systems at low redshifts as discussed in Oser et al. (2010).

We note several interesting trends in the in situ to accreted fraction as we vary the physics in the SAMs. Adding thermal SN FB increases the in situ fraction at all redshifts and in all mass bins. This is presumably because it suppresses star formation in low-mass satellites which are the

Figure 9. Comparison of the mean in situ (left column) and accreted (right column) stellar masses in diﬀerent mass bins. The mass bins and colors are the same as in Fig. 2. The in situ stellar masses in SAMs agree with the ones in simulations reasonably well, whereas the accreted stellar mass is smaller in the SAMs than in the simulations.

source of accreted stars. Adding the SN-driven winds and metal cooling further increases the in situ fraction, again at all redshifts below z ∼ 4. Switching on AGN FB increases the in situ fraction at high redshift and decreases it at low redshift in the high mass bin (and to a lesser extent in the intermediate mass bin). This is because the radio mode feedback shuts oﬀ cooling at late times in massive halos, removing the supply of new gas needed to fuel ongoing in situ star formation. Interestingly, increasing the star formation eﬃciency in the NF model has almost no eﬀect on the in situ to accreted fraction. This is presumably because the SF eﬃciency is increased in the central and (accreted) satellite galaxies alike. However, if the SFE were higher in high redshift galaxies than at low redshift, this would presumably increase the accreted fraction in present day galaxies. This

may be part of the reason for the higher accreted fractions in the simulations.

In Fig. 9, we show the evolution of the cumulative mass of insitu and accreted stars separately for the simulations and the various SAM variants. Here we can see that the NF SAM actually reproduces the growth of in situ stellar mass fairly well, though overproducing the in situ mass at low redshift somewhat, especially in the highest mass bin. We speculate that gravitational heating in the simulations prevents some of the late cooling in the highest mass bin and leads to lower in situ stellar mass than the NF SAM (Naab et al. 2007, 2009a; Johansson et al. 2009; Feldmann et al. 2010). The radio mode AGN FB in the FULL model leads to a similar suppression of this in situ mass growth in the massive halos. The NF model with increased SFE gives an even

better match to the simulations at high redshift. The discrepancy arises from the much lower accreted masses in the SAM. Here again, the SF model with high SFE comes the closest to matching the simulation results, but it still falls short by a considerable amount.

Part of the reason for the lower predicted accreted masses in the SAMs is that the SAMs used here only allow cooling onto the central galaxy in the halo, eﬀectively assuming that the hot gas reservoir of a satellite galaxy is stripped as soon as it enters the virial radius of the host. This is known to result in satellites that are too red and have star formation rates that are too low compared with observations (Kimm et al. 2009). It will also truncate their star formation, resulting in a smaller amount of stellar mass that will eventually be accreted when they merge (Khochfar & Ostriker 2008).

- 5.3 Hot halo gas


The evolution of the mean hot gas fraction is shown in the three panels of Fig. 10. In all but the SN SAMs the hot gas fraction increases with increasing halo mass, which is qualitatively similar to the simulations. In the simulations this eﬀect is caused by shock heating of infalling baryonic material which becomes more eﬃcient for massive halos (e.g. Silk 1977; Binney 1977; White & Rees

- 1978b; Birnboim & Dekel 2003b; Birnboim et al. 2007; Keresˇ et al. 2005b; Khochfar & Ostriker 2008; Keresˇ et al.


- 2009; Johansson et al. 2009). This trend is also seen by the SAMs, except for the SN model, where the supernova energy input heats most of the available gas to the virial temperature of the halos, keeping the hot gas fraction constant independent of halo mass. For the SNWM and FULL models, the supernova winds drive some of the hot gas out of the low mass halos. In contrast, the additional metal cooling shows a negligible eﬀect on the evolution of the hot halo gas. The additional eﬀect of Radio mode heating (FULL model), which prevents late cooling in massive halos and therefore leads to larger amounts of hot gas, is apparent for the intermediate and high mass galaxies. The NF model agrees


fairly well with the simulations in all mass bins at z ∼< 1.5 but substantially overpredicts the amount of hot gas at high redshift.

To understand the diﬀerences in the hot gas content at high redshift we investigate the gas accretion modes onto the central galaxies. For the simulations we distinguish between hot and cold accretion by considering the highest temperature a gas particle had before it was accreted onto the galaxy, i.e. 1/10th of the virial radius. We use the same deﬁnition to distinguish between between hot and cold gas as given by equation 3 (similar to Keresˇ et al. 2005b). In the SAMs, we distinguish between hot and cold mode accretion (slow and rapid cooling) depending on whether the ratio of the cooling radius to the virial radius rcool/rvir is larger (cold mode) or smaller (hot mode) than unity (White & Frenk 1991). The distinction between hot and cold mode accretion approximately speciﬁes whether the gas was heated to the virial temperature of the host halo before it was accreted onto the galaxy (hot mode) or was directly accreted without being heated (cold mode). The cold mode accretion is meant to represent the ‘cold ﬂows’ recently discussed in the literature (Keresˇ et al. 2005b, 2009; Oser et al. 2010; Dekel et al.

| | |
|---|---|
| | |


Figure 10. Evolution of the mass fraction of hot gas in simulations and SAMs normalized to the available mass in baryons. The mass bins and colors are the same as in Fig. 2. The SAMs tend to overpredict the mass of gas at high redshift relative to the simulations.

2009). Note that for the SNWM and FULL SAMs, we have not substracted the heating rates or rates of blown-out gas due to feedback processes from the accretion rates.

In Fig. 11 we show the comparison of the total (left panels), hot (middle panels) and cold mode (right panels) gas accretion rates onto the central galaxies as a function of redshift. For all SAMs, the total gas accretion rates onto the galaxies are signiﬁcantly higher than for the simulations. This is caused solely by higher hot mode accretion rates from the generally larger hot gas reservoir in particular at high redshift (middel panel in Fig. 11 and see Fig. 10). The cold mode accretion rates are much lower in the SAMs than in the simulations, and in the SAMs without metal cooling (which are more relevant to compare with these simulations), the cold mode is truncated at z ∼< 4 for massive halos, z ∼< 1–1.5 for low mass halos, while it declines smoothly until z ∼ 0 in

- Figure 11. Comparison of the mean accretion rates of all gas (left column), the rate of hot mode accretion (intermediate column) and of cold mode accretion (right column) in simulations and SAMs onto the central galaxies. The mass bins and colors are the same as in Fig. 2. Note that in the FULL and SNWM we have not substracted heating rates or rates from blown-out gas from the accretion rates. Compared to simulations, hot mode accretion is overestimated in all SAMs, whereas cold mode accretion is in general underestimated.


the simulations. However, the predicted rates of cold mode accretion are much higher in the SAMs that include metal cooling.

In contrast to our results, Cattaneo et al. (2007) ﬁnd a reasonably good match for the evolution of the hot gas content as well as for the hot and cold mode accretion rates in their SAM version without any feedback. However, they include metal cooling in their SAM, but not in their simulations. Benson & Bower (2011) compare cold and hot mode accretion rates from SAMs to simulations, varying the supernova feedback and conditions for the rapid cooling regime according to Birnboim & Dekel (2003a). They concluded that cold-mode physics is already adequately accounted for in SAMs — but they also used simulations with only primordial H & He cooling, but included metal cooling in their SAMs. Lu et al. (2010) assume only H & He cooling in their SAMs as well as in the simulations (like we do) and ﬁnd qualitatively similar results to ours: a discrepancy for the

hot halo gas fraction at high redshift associated with larger hot mode and smaller cold mode accretion rates in the SAMs than in the simulations.

This suggests that the agreement presented in Cattaneo et al. (2007) and Benson & Bower (2011) is fortuitous, and arises because of the enhanced cold ﬂows resulting from the metal cooling included in the SAMs. It is unclear whether this agreement would persist if metal cooling were also included in the simulations, but it appears that the agreement is not nearly as good as they claim when metal cooling is omitted from both techniques. Therefore, provided that the physical mechanisms taken into account in SAMs and simulations are the same, we might conclude that the diﬀerence between cold and hot mode accretion rates in SAMs and simulations is a general result, independent of the speciﬁc SAM that is considered. This indicates that the cooling recipe should be improved in SAMs. In addition, the recipes for gas accretion in SAMs do not currently

| | |
|---|---|
| | |


| | |
|---|---|
| | |


| | |
|---|---|
| | |


| | |
|---|---|
| | |


| | |
|---|---|
| | |


| | |
|---|---|
| | |


| | |
|---|---|
| | |


| | |
|---|---|
| | |


| | |
|---|---|
| | |


| | |
|---|---|
| | |


| | |
|---|---|
| | |


| | |
|---|---|
| | |


| | |
|---|---|
| | |


| | |
|---|---|
| | |


| | | |
|---|---|---|
| | | |


| | |
|---|---|
| | |


| | |
|---|---|
| | |
| | |


| | |
|---|---|
| | |
| | |


| | |
|---|---|
| | |


| | |
|---|---|
| | |


| | |
|---|---|
| | |


| | |
|---|---|
| | |


| | |
|---|---|
| | |


| | |
|---|---|
| | |


| | |
|---|---|
| | |


| | |
|---|---|
| | |


| | |
|---|---|
| | |


| | |
|---|---|
| | |


- Figure 12. Stellar mass versus dark matter halo mass for simulations (upper row), NF model (middle row) and the FULL model (lower row). The left column shows the dependence on halo mass for z = 0, the middle one for z = 1 and the right one for z = 2. The black lines with the light grey shaded areas show the ﬁt for the halo occupation distribution from Moster et al. (2010). The green lines with the dark grey shaded areas the one from Wake et al. (2011). The diﬀerent black, dashed and dashed-dotted lines illustrate the total expected


baryon fraction (fbar ∗ Mhalo), 50% and 10% of the total expected baryon fraction. The black and green thin, vertical lines show the observational mass limit of the survey used in Moster et al. (2010) and Wake et al. (2011), respectively.

allow co-existing cold and hot gas accretion as seen in simulations. For this, Lu et al. (2010) proposed a new model that explicitly incorporates cold-mode accretion independent of the hot halo gas. By ﬁtting the hot and cold gas fraction in simulations as a function of redshift and halo mass and assuming accretion onto the galaxy within a free-fall time they calculate the accretion rate of the cold component and thus, achieve a better match of their SAMs to simulations.

- 6 COMPARISON TO OBSERVATIONS


In this section we compare our results from the SAMs and simulations to observational data and empirical constraints

- at diﬀerent redshifts. We focus on two key observational constraints: the relationship between halo mass and stellar mass (the Mgal − Mhalo-relation) and the relationship between stellar mass and star formation rates (m˙ star − Mgalrelation).


Fig. 12 shows the relation of galaxy mass and dark matter halo mass for z = 0 (left panels), z = 1 (middle panels), and z = 2 (right panels). We show the NF and FULL SAMs, and the simulations. We also show the empirical constraints on the Mgal − Mhalo-relation from Moster et al. (2010), which were obtained by asking how halos and sub-halos in a N-body simulation must be populated in order to reproduce the observed stellar mass functions at diﬀerent redshifts (halo abundance matching). The thin, black vertical lines illustrate the observational lower observational mass limit. Also shown are the similar constraints from Wake et al. (2011), which are derived using galaxy clustering data from the NEWFIRM Medium Band Survey between 1 < z < 2 (see also Wechsler et al. 2006; Zheng et al. 2007; Conroy & Wechsler 2009; Guo et al. 2009; Zehavi et al. 2010; Behroozi et al. 2010). Note that the ﬁtting functions of Moster et al. (2010) and Wake et al. (2011) are somewhat diﬀerent, in particular at the low mass end (lower observational mass limit is

shown by thin, green lines). This is not surprising, as they were derived using diﬀerent methods and from diﬀerent observational data sets. As our sample consists of only 48 halos covering a mass range between approximately 1011M⊙ and 1013M⊙, the comparison to observational data is not statistically rigorous due to the relatively small number of simulated halos. However, the 48 halos have been chosen randomly from a cosmological simulation and therefore, they should generally follow the mean abundance matching trends that relate halo mass to stellar mass. At all redshifts, the simulations overpredict the stellar masses at a given halo mass by about a factor of two for halos more massive than 1012M⊙. At higher redshifts the progenitor galaxies have lower masses, and deviate more from the expected distribution. At z = 2 the diﬀerence can be almost two orders of magnitude for halos of ∼ 1011M⊙, in line with the ﬁndings of the previous section — at high redshift, gas is very eﬃciently converted into stars in the simulations. Implementation of more eﬃcient feedback from supernovae would help to solve this problem. Indeed it has been shown that simulations that do include eﬀective SN FB agree much better with expectations (see e.g. Scannapieco et al. 2009; Sawala et al.

- 2010; Genel et al. 2010; Governato et al. 2010 and references therein). In addition, it is apparent the simulations require an additional process that can quench star formation at late times in massive halos, such as radio mode AGN feedback.


For high mass halos, the NF model (middle row) predicts galaxy masses close to the relation at z = 1 and z = 2 due to less eﬃcient star formation at high redshifts (see Fig. 5), but, like the simulations, overpredicts the stellar masses in low mass halos. By z = 0 the oﬀset is about as large as for the simulations. For the FULL SAM there is good agreement at z = 0, which is not surprising because the model was tuned to match the observed stellar mass function. However, the FULL model still predicts galaxy masses that are about a factor of two to three too high for low mass halos (log(Mhalo) < 11.5) at high redshift. This is related to the excess of low mass galaxies at high redshift and other connected problems discussed in Fontanot et al. (2009), and is seen in both SAMs and hydro simulations from several groups. It is likely that these problems are due to limitations in our current understanding or implementation of the physics of star formation and/or SN feedback.

The relation between the star formation rates and the galaxy stellar masses Mstar is shown in Fig. 13 for redshifts z = 0, z = 1, and z = 2. We distinguish between starforming and non-star-forming galaxies (illustrated as crosses or open squares, respectively) using a criterion according to Franx et al. (2008): galaxies with speciﬁc star formation rates SFR/Mstar smaller than 0.3 × t−hubble1 , are considered to be quiescent, whereas galaxies with larger speciﬁc star formation rates are assumed to be star-forming. The black, solid lines always refer to the observed relation at the corresponding redshift (z = 0: SDSS, Elbaz et al. (2007); z = 1: GOODS, Elbaz et al. (2007); z = 2: GOODS, Daddi et al.

- (2007)) for star-forming galaxies. Note that we show the relation of Daddi et al. (2007) at z = 2 re-normalised 0.3 dex downwards, following the re-calibration of SFR derived from 24 micron luminosity based on recent Herschel observations (Nordon et al. 2010). We show Fig. 13 in order to illustrate


the variation in the population of the SFR-Mstar plane for diﬀerent implementations of the SAMs and the simulations.

| | | |
|---|---|---|
| | | |


| | |
|---|---|


| | |
|---|---|
| | |


| | |
|---|---|
| | |


| | |
|---|---|
| | |


| | |
|---|---|
| | |


| | |
|---|---|
| | |


| | |
|---|---|


Figure 13. Star formation rate versus stellar mass for simulations and two diﬀerent semi-analytic models (NF and FULL). Solid lines illustrate the observed relations at diﬀerent redshifts: z = 0, 1: Elbaz et al. (2007), z = 2: Daddi et al. (2007). Dashed lines illustrate the corresponding 1 − σ-range of the scatter. Note that in light of the recalibration of SFR from 24 µm observations based on Herschel results (see text), we have plotted the Daddi et al. relation shifted downwards by 0.3 dex.

Note that this is not intended to be a quantitative comparison to observations, but only a qualitative illustration. In particular, we can see that — with regard to the SAMs — only in the FULL model, do we have SF and non-SF (quenched) galaxies co-existing as in the observations. This reﬂects the well-known need for some mechanism, such as AGN feedback, to quench SF in massive galaxies.

In general, the simulations underpredict the star formation rates for star forming galaxies at all redshifts, but most notably at z > 1, due to the high star formation efﬁciencies at even higher redshifts and the resulting gas depletion (see section 5.2). Once again, implementing more effective supernova feedback would presumably suppress star

formation in the small, high redshift progenitors of these galaxies and result in higher SFR at these redshifts (see e.g. Oppenheimer & Dave´ 2008; Genel et al. 2010). The NF SAMs ﬁt the SF sequence at z = 0, but have too many high mass galaxies with high SFR. In the FULL model, these galaxies are quenched by radio mode feedback, in agreement with observations (see Somerville et al. 2008b). Both the NF and FULL SAMs SF sequences are about a factor of two too low at z ∼ 1 and 2. This also seems to be generic to many SAMs, as shown by Fontanot et al. (2009) and others. It is interesting to note that star forming galaxies in both the NF and FULL SAM galaxies all lie on the same SF sequence. This implies that SN feedback simply moves galaxies along the sequence, reducing both the stellar mass and the SFR such that the galaxies remain on the same relation, and is due to the self-regulating nature of SN feedback in the SAMs. In constrast, AGN FB quenches star formation and moves massive galaxies oﬀ of the SF sequence (seen in the FULL model).

- 7 DISCUSSION AND CONCLUSIONS


In this paper we present a detailed comparison between a set of 48 cosmological hydrodynamic zoom simulations and different stripped-down versions of semi-analytic models based on dark matter merger trees extracted from the simulations. The hydro simulations are run using the entropy-conserving formulation of SPH with the Gadget-2 code, and include atomic cooling assuming a primordial composition of H and He, a UV background radiation ﬁeld, star formation, and supernova feedback. We present results from a “no feedback” (NF) version of the SAM which contains the same physical ingredients as the simulations, and also versions that include thermal feedback by SNae (SN), a version that also includes large-scale SN-driven winds and metal cooling (SNWM), and the FULL version which includes all the previously mentioned ingredients as well as AGN feedback. With this approach we can compare the predictions of the two methods over two orders of magnitude in halo mass at unprecedented resolution.

The two approaches try to answer the same questions but diﬀer in methodology. In the simulations the full dynamical and hydrodynamical evolution of the systems is followed by solving the equations of motion computationally. Additional physical processes like star formation and supernova feedback are included using sub-resolution models. The semi-analytic models are based on the computed dark matter accretion history and approximate the gas physics, star formation, and feedback processes with simpliﬁed recipes. Our analysis is focused on the cosmic evolution of the baryon content in the central galaxies of the main branch of the merger trees and its division into various components (stars, cold gas, and hot gas), as well as how those galaxies acquired their gas — whether through “cold” or “hot” mode accretion — and their stellar mass (e.g. through in situ star formation vs. accretion).

The results of our comparison are quite rich, with some surprising agreement and some striking disagreement. First, we note that we expect the results of the simulations to lie somewhere in between the NF and the SN SAMs, since these SAMs include the same physical processes as the sim-

ulations. In most cases, the agreement is best between the simulations and the NF model, suggesting that the SN FB implemented in the simulations has little eﬀect. The NF SAMs produce very good agreement with the simulations for the mass of cold gas plus stars at all redshifts and for all halo masses. The SAMs slightly underestimate this “condensed baryon” fraction at high redshift (z > 1) and overestimate it at low redshift. This indicates that the overall cooling and accretion rates in the SAM and the simulations must be similar. The NF SAM also produces fairly good agreement (better than ∼ 20% since z ∼ 4) with the overall baryon fractions (i.e. hot gas plus cold gas and stars in the central galaxy) in the simulations, here overestimating the baryon fractions at high redshift in high and intermediate mass halos.

A striking diﬀerence is that when we study the evolution of the stellar and cold gas components separately, we ﬁnd that the cold gas fractions agree at very high redshifts, but the gas is consumed much more rapidly in the simulations, leading to cold gas fractions at all redshifts less than about z ∼ 3–4, and in halos of all masses, that are much lower (by up to two orders of magnitude) than in the NF SAM. Correspondingly, we ﬁnd much higher stellar masses in the simulations than the SAMs at high redshift, although they converge to almost the same value as the NF SAMs at z = 0. We interpret this as an indication that the star formation eﬃciency is much higher in the simulations than in the SAMs, and the reason for the convergence in the stellar masses at low redshifts is because nearly all available gas has been consumed in the simulations. This conjecture is supported by our ﬁnding that if we boost the star formation eﬃciency in the NF SAM by a factor of ten, we ﬁnd excellent agreement with the stellar mass fraction evolution in the simulations, and improved agreement with the cold gas fraction evolution.

However, both the simulations and SAMs supposedly adopt the same empirical Schmidt-Kennicutt relation between cold gas density and star formation rate. How can the star formation eﬃciencies be so diﬀerent? We note several diﬀerences in the implementation of the star formation recipe in the simulations and SAMs. In SAMs, the only available information about the structure of the star forming gas in galactic disks is an estimate of the scale radius of the total baryonic component of the disk, which comes from angular momentum conservation arguments (Mo et al. 1998; Somerville et al. 2008). The SAMs then make a series of assumptions — that the gas is in a smooth, thin exponential disk with a radius that is a simple multiple of the stellar scale radius — and apply the Kennicutt relation in terms of the predicted gas surface density. Only gas above a critical surface density is allowed to form stars. In constrast, the simulations provide detailed 3D predictions for the structure of the cold gas in galaxies, and implement the SK relation in terms of 3D volume density (also applying a threshold for SF in terms of a critical volume density). It is well known that high redshift galaxy assembly in cosmological simulations is dominated by clumpy, high density, cold mode accretion. Disks may be more compact than in the idealized case of perfect conservation of angular momentum, and are thick and clumpy. The adopted SF recipe is super-linear in the gas volume density (i.e. the exponent in the SK relation is

larger than unity), and therefore star formation will be more eﬃcient in a clumpy gas distribution than in a smooth one.

The appropriate values of the SF and SN feedback eﬃciency parameters for the simulations were obtained by tuning them to match the observed Kennicutt relation for an idealized, smooth thin exponential disk, designed to resemble a Milky Way-like galaxy at z = 0 (Springel & Hernquist 2003). Using these same values for the parameters, we ﬁnd that the high redshift galaxies in our cosmological simulations lie about a factor of ﬁve above the Kennicutt relation with the normalization adopted by Springel & Hernquist (2003). A second, more minor issue, is that the SAMs were tuned to match a Kennicutt relation with a normalization a factor of two lower than the one used by Springel & Hernquist (2003), reﬂecting a diﬀerent choice of IMF in the conversion from observed ﬂux to SFR.

This seems to explain the reason for the factor of ∼ 10 higher SFE in the simulations relative to the SAMs, but begs the question: is this a robust prediction of the simulations that should be taken seriously? Are these higher star formation eﬃciencies in high redshift galaxies really physical? There are several issues that are relevant here. First, the predicted “clumpyness” of the disks is highly sensitive to the assumed sub-grid recipes. For example, implementation of more eﬀective SN FB would reduce the clumpyness of the disks at high redshift, but might increase the clumpyness at z ≈ 2(e.g. Genel et al. 2010) in the simulations. Observed disks at high redshift are known to be more clumpy than nearby ones (Genzel et al. 2006, 2008, 2010; F¨rster Schreiber et al. 2009, 2011), but it remains highly uncertain which recipe for SN FB will produce the “correct” degree of clumpyness and overall structure for statistical samples of high redshift galaxies while simultaneously reproducing the properties of local spirals (Piontek & Steinmetz 2011; Governato et al. 2009; Scannapieco et al. 2009; Brooks et al. 2009b). Moreover, recent observational studies indicate that star formation rate densities in local galaxies as well as at high redshift correlate linearly with the surface density of the molecular gas, with no evolution in the molecular SK relation (Bigiel et al.

- 2008; Daddi et al. 2010; Genzel et al. 2010). This is also true for galaxies with very clumpy star formation, as expected for a linear dependence with gas density. Only interacting galaxies undergoing a signiﬁcant starburst seem to show an increased star formation eﬃciency (Daddi et al.


- 2010; Genzel et al. 2010). Neither the SAMs nor the simulations presented here include these eﬀects, although we are working on updated models that will do so.


A second major diﬀerence between the SAMs and the simulations is in the mode in which galaxies acquire most of their stellar mass. We distinguish between “in situ” growth, due to stars that form out of cold gas within the galaxy in question, and “accretion” of stars that formed in external galaxies and are accreted via mergers. This distinction is important because it may determine the characteristic size evolution of early type galaxies (Khochfar & Silk 2006b; Naab et al. 2009b; Guo et al. 2011; Covington et al. 2011). It has been shown previously that massive galaxies in the simulations and semi-analytic models have an early phase of growth dominated by the in situ mode, and then switch over to a mode that is dominated by growth through accretion (De Lucia et al. 2006; Khochfar & Silk 2006c; Guo & White

2008; Oser et al. 2010; Feldmann et al. 2010; Zehavi et al. 2011). Although the ratio of in situ to accreted stars always decreases with time in the SAMs, in qualitative agreement with the simulations, in the SAMs in situ growth dominates over accretion in halos of all masses at all times. Examining the absolute mass in stars formed in situ or accreted, we ﬁnd that this is primarily because the SAMs predict much less mass growth through accretion — the in situ mass evolution agrees fairly well with the simulation results. The comparison between SAMs with diﬀerent physical processes included gives us further insights into the origin of the discrepancy: 1) Increasing the eﬃciency of SN FB (SN and SNWM SAMs) reduces the accreted mass because star formation is suppressed in the low-mass satellites that eventually get accreted. 2) Including radio mode AGN FB (FULL SAM) reduces the in situ growth in massive galaxies at late times, because it shuts oﬀ the fuel supply for in situ star formation in these objects. Interestingly, increasing the SF eﬃciency in the SAM does not aﬀect the fraction of in situ versus accreted mass, presumably because all galaxies are boosted equally.

In summary, it is likely that the contributions from in situ and accreted stars are currently incorrectly predicted in both the simulations and SAMs, for the following reasons. In order to match observations, the simulations presented here clearly require both a process that suppresses star formation in low mass objects at all redshifts (such as SN-driven winds) and one that can shut oﬀ residual cooling and quench star formation in massive galaxies at late times (such as radio mode AGN FB). The former will reduce the accreted mass, while the latter will decrease the in situ mass in massive objects at late times. In addition, if the SFE is higher in high redshift galaxies than at late times, this is likely to increase the accreted mass. On the other hand, the SAMs presented here, like many SAMs in the literature, make the assumption that hot gas from the halo can only be accreted onto the central galaxy. This rapidly truncates the star formation in satellite galaxies and is likely to artiﬁcially decrease the accreted mass fraction. As a possible solution, strangulation of satellite galaxies might be delayed if the depth of the potential well of the sub-halo is deep enough to retain the hot halo gas for a longer time (e.g. Khochfar & Ostriker 2008). In this case, the accreted objects may have longer ongoing cooling resulting in longer on-going star formation. In addition, the SAMs neglect gravitational heating, which is clearly important in the simulations and should reduce the in situ growth in massive halos at late times. The recent study of Fontanot et al. (2011) has shown that the S08 SAM and other similar SAMs in which radio mode feedback is used to solve the overcooling problem overpredict the fraction of radio loud galaxies compared with observations, and the implemented dependence of radio luminosity on stellar and halo mass is too steep. Gravitational heating could play a similar role (Khochfar & Ostriker 2008; Dekel & Birnboim 2008; Birnboim & Dekel 2010) and thereby reduce the need for such strong radio mode heating.

A third important result is that the cooling recipe implemented in these SAMs (which is widely used in many SAMs) overpredicts the overall accretion rate of gas by a factor of 1.5 (in low mass halos) to four (in massive halos). If the accretion rates in the simulations are accurate, this implies that the SAMs that match present day galaxy

properties are compensating for this “extra” accretion by artiﬁcially “tuning up” the feedback. Moreover, when we divide the gas accretion into “hot mode” and “cold mode” (Birnboim & Dekel 2003a; Keresˇ et al. 2005b), we ﬁnd that the SAMs systematically overestimate the hot mode growth (by up to an order of magnitude) and underestimate the cold mode. As well, in the SAMs without metal cooling, the cold mode shuts oﬀ completely at low redshifts (the shutoﬀ redshift depends on halo mass), while in the simulations it declines smoothly but continues to low redshifts. This is likely to be a result of the fact that, in the SAMs, the criterion for discriminating between hot and cold mode is based on the assumption of smooth, spherical halos, while in simulations cold gas can stream into halos along cold, dense ﬁlaments. In addition, in the SAMs, gas is assumed to accrete either in cold mode or hot mode, but simultaneous cold and hot mode accretion is not allowed. In the simulations, the dense, cold streams can penetrate deep into the diﬀuse hot halos, allowing for both accretion modes to occur within the same halo (Keresˇ et al. 2005b, 2009; Brooks et al. 2009a). We consider this discrepancy to be a general feature of currently existing SAMs (see section 5.3) and for example, similar results were found in the study of Lu et al. (2010). In order to overcome the weakness of SAMs in this respect, they proposed a new model that explicitly incorporates cold-mode accretion independent of the hot halo gas. By ﬁtting the hot and cold gas fraction in simulations as a function of redshift and halo mass and assuming accretion onto the galaxy within a free-fall time, they calculate the accretion rate of the cold component and thus, achieve a better match of their SAMs to simulations. However, motivated by hydrodynamical simulations, implementing gravitational heating might provide a more promising mechanism as it treats gas inﬂow and heating in a self-consistent way. Following Khochfar & Ostriker

- (2008), the heating of the intracluster medium (ICM) would be calculated by the net surplus of gravitational potential energy released from gas that has been stripped from infalling satellites. Gravitational heating is found to be an efﬁcient heating source for massive dark matter halos, where it prevents cooling, and becomes especially important at late times. Therefore, if we generally assumed cold infalling gas and heating of gas due to the binding energy of the halo potential, this might imply an automatic, less eﬃcient heating at high z and for low mass halos. This should result naturally in larger cold accretion fractions for these objects and thus, also in a better match of the hot gas content for high-redshift galaxies.


We compared both the simulations and SAMs to two key observational constraints at z = 0, 1, and 2: the relationship between dark matter halo mass and stellar mass, and the relationship between stellar mass and star formation rate. We found that the simulations predict stellar masses that are too large for their halo masses at all redshifts. The stellar masses are too high by a factor of a few for massive halos ( ∼> 1012M⊙), and by an order of magnitude or more for lower mass halos. The SAM results for the NF model are qualitatively similar, although the stellar masses at high redshift are lower, due to the lower star formation eﬃciencies, as already discussed. In the SAMs, the curvature in the empirical Mgal − Mhalo relation can be achieved by including supernova driven winds, which suppress star formation in low mass halos, and radio mode AGN FB, which suppresses

star formation in high mass halos. We found that the SFR at a given stellar mass were too low in the simulations at all redshifts z ∼< 2, probably because of the overly eﬃcient SF at higher redshifts and the resulting gas consumption. SF galaxies in all SAMs were found to lie on the same relation, with supernova feedback shifting the galaxies along the relation. The SAMs (both FULL and NF) showed better agreement with the observed m˙ star − Mgal relation than the simulations, but have SFR at a given stellar mass that are about a factor of ∼ 2 too low at high redshifts.

In ﬁnal summary, we conclude that on the one hand, we are encouraged by the robustness of SAMs as a tool for exploring the qualitative eﬀects of varying the physical ingredients of galaxy formation. On the other hand, we have also identiﬁed several important areas where the quantitative accuracy of fundamental physical recipes in the SAMs should be improved, and several physical processes that are missing in our SAM but which should be included. Additionally, there is a tendency to treat numerical simulations as “truth”, but we have shown that key predictions of these simulations are sensitive to uncertain sub-grid recipes. We have also highlighted several physical processes that are neglected in the simulations studied here, but which appear to be crucial in order to understand the properties of real galaxies. These include more effective implementation of supernova-driven winds, chemical enrichment and metal cooling, and a self-consistent treatment of the growth of and feedback from black holes. Of course, these are hardly new suggestions, and considerable progress has been made recently in all of these areas (e.g. Di Matteo et al. 2005; Cattaneo et al. 2005; Sijacki et al. 2007; Oppenheimer & Dave´ 2008; Booth & Schaye 2009; Scannapieco et al. 2009; Governato et al. 2010; Schaye et al. 2010b; Sawala et al. 2010; Ostriker et al. 2010). In conclusion, we suggest that using these two complementary techniques (SAMs and hydrodynamic simulations) together in close coordination may provide the most powerful approach to understanding galaxy formation and evolution for the near future.

ACKNOWLEDGMENTS

This research was supported by the DFG Cluster of Excellence ‘Origin and Structure of the Universe’. We thank Simon White for helpful and interesting discussions. RSS thanks USM for hospitality during her visit. MH thanks the STScI for hospitality and support for visits.

REFERENCES

Agertz O., Teyssier R., Moore B., 2011, MNRAS, 410, 1391 Angulo R. E., White S. D. M., 2010, MNRAS, 401, 1796 Baugh C. M., Lacey C. G., Frenk C. S., Granato G. L., Silva

L., Bressan A., Benson A. J., Cole S., 2005, MNRAS, 356, 1191

Behroozi P. S., Conroy C., Wechsler R. H., 2010, ApJ, 717,

379 Benson A. J., Bower R., 2011, MNRAS, 410, 2653 Benson A. J., Pearce F. R., Frenk C. S., Baugh C. M.,

Jenkins A., 2001, MNRAS, 320, 261

Best P. N., von der Linden A., Kauﬀmann G., Heckman T. M., Kaiser C. R., 2007, MNRAS, 379, 894 Bigiel F., Leroy A., Walter F., Brinks E., de Blok W. J. G.,

Madore B., Thornley M. D., 2008, AJ, 136, 2846 Binney J., 1977, ApJ, 215, 483

- Birnboim Y., Dekel A., 2003a, MNRAS, 345, 349
- Birnboim Y., Dekel A., 2003b, MNRAS, 345, 349 Birnboim Y., Dekel A., 2010, ArXiv:1008.1060 Birnboim Y., Dekel A., Neistein E., 2007, MNRAS, 380,


339 Blumenthal G. R., Faber S. M., Primack J. R., Rees M. J.,

1984, Nature, 311, 517 Bode P., Ostriker J. P., 2003, ApJS, 145, 1 Bond J. R., Cole S., Efstathiou G., Kaiser N., 1991, ApJ,

379, 440 Booth C. M., Schaye J., 2009, MNRAS, 398, 53 Bower R. G., 1991, MNRAS, 248, 332 Bower R. G., Benson A. J., Malbon R., Helly J. C., Frenk

C. S., Baugh C. M., Cole S., Lacey C. G., 2006, MNRAS, 370, 645

Bower R. G., Vernon I., Goldstein M., Benson A. J., Lacey C. G., Baugh C. M., Cole S., Frenk C. S., 2010, MNRAS, 407, 2017

Brooks A. M., Governato F., Quinn T., Brook C. B., Wad-

- sley J., 2009a, ApJ, 694, 396

Brooks A. M., Governato F., Quinn T., Brook C. B., Wad-

- sley J., 2009b, ApJ, 694, 396


Bryan G. L., Norman M. L., 1998, ApJ, 495, 80 Cattaneo A., Blaizot J., Devriendt J., Guiderdoni B., 2005,

MNRAS, 364, 407

Cattaneo A., Blaizot J., Weinberg D. H., Keresˇ D., Colombi S., Dave´ R., Devriendt J., Guiderdoni B., Katz N., 2007, MNRAS, 377, 63

Cen R., Ostriker J. P., 1993, ApJ, 417, 415

- Chabrier G., 2003a, PASP, 115, 763
- Chabrier G., 2003b, PASP, 115, 763 Cole S., Aragon-Salamanca A., Frenk C. S., Navarro J. F.,


Zepf S. E., 1994, MNRAS, 271, 781 Cole S., Lacey C. G., Baugh C. M., Frenk C. S., 2000,

MNRAS, 319, 168 Conroy C., Wechsler R. H., 2009, ApJ, 696, 620 Covington M. D., Primack J. R., Porter L. A., Croton D. J.,

Somerville R. S., Dekel A., 2011, ArXiv:1101.4225

Crain R. A., Theuns T., Dalla Vecchia C., Eke V. R., Frenk C. S., Jenkins A., Kay S. T., Peacock J. A., Pearce F. R., Schaye J., Springel V., Thomas P. A., White S. D. M., Wiersma R. P. C., 2009, MNRAS, 399, 1773

Croton D. J., Springel V., White S. D. M., De Lucia G., Frenk C. S., Gao L., Jenkins A., Kauﬀmann G., Navarro J. F., Yoshida N., 2006, MNRAS, 365, 11

Daddi E., Dickinson M., Morrison G., Chary R., Cimatti A., Elbaz D., Frayer D., Renzini A., Pope A., Alexander D. M., Bauer F. E., Giavalisco M., Huynh M., Kurk J., Mignoli M., 2007, ApJ, 670, 156

Daddi E., Elbaz D., Walter F., Bournaud F., Salmi F., Carilli C., Dannerbauer H., Dickinson M., Monaco P., Riechers D., 2010, ApJ, 714, L118

Dave´ R., Cen R., Ostriker J. P., Bryan G. L., Hernquist L., Katz N., Weinberg D. H., Norman M. L., O’Shea B., 2001, ApJ, 552, 473

Dave R., Dubinski J., Hernquist L., 1997, NewA, 2, 277

Davis M., Efstathiou G., Frenk C. S., White S. D. M., 1985,

ApJ, 292, 371 De Lucia G., Blaizot J., 2007, MNRAS, 375, 2 De Lucia G., Springel V., White S. D. M., Croton D., Kauﬀ-

mann G., 2006, MNRAS, 366, 499 Dekel A., Birnboim Y., 2008, MNRAS, 383, 119 Dekel A., Birnboim Y., Engel G., Freundlich J., Goerdt

T., Mumcuoglu M., Neistein E., Pichon C., Teyssier R., Zinger E., 2009, Nature, 457, 451

Di Matteo T., Springel V., Hernquist L., 2005, Nature, 433, 604 Diemand J., Kuhlen M., Madau P., Zemp M., Moore B., Potter D., Stadel J., 2008, Nature, 454, 735 Dolag K., Borgani S., Murante G., Springel V., 2009, MNRAS, 399, 497 Elbaz D., Daddi E., Le Borgne D., Dickinson M., Alexander

- D. M., Chary R., Starck J., Brandt W. N., Kitzbichler M., MacDonald E., Nonino M., Popesso P., Stern D., Vanzella
- E., 2007, A&A, 468, 33


Fakhouri O., Ma C., 2008, MNRAS, 386, 577 Feldmann R., Carollo C. M., Mayer L., Renzini A., Lake

G., Quinn T., Stinson G. S., Yepes G., 2010, ApJ, 709, 218

Font A. S., Bower R. G., McCarthy I. G., Benson A. J., Frenk C. S., Helly J. C., Lacey C. G., Baugh C. M., Cole S., 2008, MNRAS, 389, 1619

Fontanot F., De Lucia G., Monaco P., Somerville R. S., Santini P., 2009, MNRAS, 397, 1776 Fontanot F., Pasquali A., De Lucia G., van den Bosch F. C., Somerville R. S., Kang X., 2011, MNRAS, pp 198–+

F¨rster Schreiber N. M., Genzel R., Bouche´ N., Cresci G., Davies R., Buschkamp P., Shapiro K., Tacconi L. J., Hicks 2009, ApJ, 706, 1364

F¨rster Schreiber N. M., Shapley A. E., Erb D. K., Genzel R., Steidel C. C., Bouche´ N., Cresci G., Davies R., 2011, ApJ, 731, 65

Franx M., van Dokkum P. G., Schreiber N. M. F., Wuyts S., Labbe´ I., Toft S., 2008, ApJ, 688, 770 Frenk C. S., White S. D. M., Davis M., Efstathiou G., 1988, ApJ, 327, 507 Genel S., Genzel R., Bouche´ N., Naab T., Sternberg A., 2008, ArXiv:0812.3154

Genel S., Naab T., Genzel R., F¨rster Schreiber N. M., Sternberg A., Oser L., Johansson P. H., Dave´ R., Oppenheimer B. D., Burkert A., 2010, ArXiv:1011.0433

Genzel R., Burkert A., Bouche´ N., Cresci G., F¨rster Schreiber N. M., Shapley A., Shapiro K., Tacconi L. J., Buschkamp P., Cimatti A., 2008, ApJ, 687, 59

Genzel R., et al., 2010, MNRAS, 407, 2091 Genzel R., Tacconi L. J., Eisenhauer F., F¨rster Schreiber

N. M., Cimatti A., Daddi E., Bouche´ N., 2006, Nature, 442, 786

Ghigna S., Moore B., Governato F., Lake G., Quinn T., Stadel J., 2000, ApJ, 544, 616

Governato F., Brook C., Mayer L., Brooks A., Rhee G., Wadsley J., Jonsson P., Willman B., Stinson G., Quinn T., Madau P., 2010, Nature, 463, 203

Governato F., Brook C. B., Brooks A. M., Mayer L., Willman B., Jonsson P., Stilp A. M., Pope L., Christensen C., Wadsley J., Quinn T., 2009, MNRAS, 398, 312

Governato F., Willman B., Mayer L., Brooks A., Stinson G., Valenzuela O., Wadsley J., Quinn T., 2007, MNRAS,

374, 1479

Guo Q., White S., Boylan-Kolchin M., De Lucia G., Kauﬀmann G., Lemson G., Li C., Springel V., Weinmann S.,

- 2010, ArXiv:1006.0106

Guo Q., White S., Boylan-Kolchin M., De Lucia G., Kauﬀmann G., Lemson G., Li C., Springel V., Weinmann S.,

- 2011, MNRAS, pp 164–+


Guo Q., White S., Li C., Boylan-Kolchin M., 2009,

ArXiv:0909.4305 Guo Q., White S. D. M., 2008, MNRAS, 384, 2 Haardt F., Madau P., 1996, ApJ, 461, 20 Hambrick D. C., Ostriker J. P., Naab T., Johansson P. H.,

2009, ApJ, 705, 1566 Hatton S., Devriendt J. E. G., Ninin S., Bouchet F. R., Guiderdoni B., Vibert D., 2003, MNRAS, 343, 75 Helly J. C., Cole S., Frenk C. S., Baugh C. M., Benson A., Lacey C., Pearce F. R., 2003, MNRAS, 338, 913 Hirschmann M., Khochfar S., Burkert A., Naab T., Genel S., Somerville R. S., 2010, MNRAS, 407, 1016 Johansson P. H., Naab T., Ostriker J. P., 2009, ApJ, 697, L38 Kang X., Jing Y. P., Mo H. J., B¨orner G., 2005, ApJ, 631,

21 Kauﬀmann G., 1996, MNRAS, 281, 487 Kauﬀmann G., Colberg J. M., Diaferio A., White S. D. M.,

1999, MNRAS, 303, 188 Kauﬀmann G., Haehnelt M., 2000, MNRAS, 311, 576 Kauﬀmann G., Heckman T. M., Best P. N., 2008, MNRAS,

384, 953 Kauﬀmann G., White S. D. M., Guiderdoni B., 1993, MNRAS, 264, 201

Kennicutt Jr. R. C., 1989, ApJ, 344, 685 Kennicutt Jr. R. C., 1998, ApJ, 498, 541 Keresˇ D., Katz N., Fardal M., Dave´ R., Weinberg D. H.,

2009, MNRAS, 395, 160

- Keresˇ D., Katz N., Weinberg D. H., Dave´ R., 2005a, MNRAS, 363, 2
- Keresˇ D., Katz N., Weinberg D. H., Dave´ R., 2005b, MNRAS, 363, 2


Khochfar S., Ostriker J. P., 2008, ApJ, 680, 54

- Khochfar S., Silk J., 2006a, ApJ, 648, L21
- Khochfar S., Silk J., 2006b, MNRAS, 370, 902
- Khochfar S., Silk J., 2006c, MNRAS, 370, 902 Kimm T., Somerville R. S., Yi S. K., van den Bosch F. C.,


Salim S., Fontanot F., Monaco P., Mo H., Pasquali A., Rich R. M., Yang X., 2009, MNRAS, 394, 1131

Klypin A., Kravtsov A. V., Valenzuela O., Prada F., 1999, ApJ, 522, 82 Klypin A., Trujillo-Gomez S., Primack J., 2010, ArXiv:1002.3660

Kollmeier J. A., Onken C. A., Kochanek C. S., Gould A., Weinberg D. H., Dietrich M., Cool R., Dey A., Eisenstein D. J., Jannuzi B. T., Le Floc’h E., Stern D., 2006, ApJ, 648, 128

Kravtsov A. V., Gnedin O. Y., Klypin A. A., 2004, ApJ, 609, 482 Lu Y., Keresˇ D., Katz N., Mo H. J., Fardal M., Weinberg

M. D., 2010, ArXiv:1008.1075 Maller A. H., Bullock J. S., 2004, MNRAS, 355, 694 Maulbetsch C., Avila-Reese V., Colı´n P., Gottl¨ober S.,

Khalatyan A., Steinmetz M., 2007, ApJ, 654, 53 Mo H. J., Mao S., White S. D. M., 1998, MNRAS, 295, 319

Moore B., Ghigna S., Governato F., Lake G., Quinn T., Stadel J., Tozzi P., 1999, ApJ, 524, L19

Moster B. P., Somerville R. S., Maulbetsch C., van den Bosch F. C., Maccio` A. V., Naab T., Oser L., 2010, ApJ, 710, 903

- Naab T., Johansson P. H., Ostriker J. P., 2009a, ApJ, 699, L178
- Naab T., Johansson P. H., Ostriker J. P., 2009b, ApJ, 699, L178


Naab T., Johansson P. H., Ostriker J. P., Efstathiou G., 2007, ApJ, 658, 710 Nagamine K., Cen R., Hernquist L., Ostriker J. P., Springel V., 2005, ApJ, 627, 608 Navarro J. F., Frenk C. S., White S. D. M., 1997, ApJ, 490, 493

Navarro J. F., Sales L. V., Owls Team 2009, in S. Jogee, I. Marinova, L. Hao, & G. A. Blanc ed., Astronomical Society of the Paciﬁc Conference Series Vol. 419 of Astronomical Society of the Paciﬁc Conference Series, Disk Galaxies at z=2 in OWLS. pp 10–+

Navarro J. F., Steinmetz M., 1997, ApJ, 478, 13 Neistein E., Dekel A., 2008, MNRAS, 383, 615 Nordon R., et al., 2010, A&A, 518, L24+ Nulsen P. E. J., Fabian A. C., 2000, MNRAS, 311, 346 Oppenheimer B. D., Dave´ R., 2008, MNRAS, 387, 577 Oser L., Ostriker J. P., Naab T., Johansson P. H., Burkert

A., 2010, ArXiv:1010.1381 Ostriker J. P., Choi E., Ciotti L., Novak G. S., Proga D., 2010, ApJ, 722, 642

Pearce F. R., Jenkins A., Frenk C. S., White S. D. M., Thomas P. A., Couchman H. M. P., Peacock J. A., Efstathiou G., 2001, MNRAS, 326, 649

Piontek F., Steinmetz M., 2011, MNRAS, 410, 2625 Planelles S., Quilis V., 2010, A&A, 519, A94+ Press W. H., Schechter P., 1974, ApJ, 187, 425 Puchwein E., Springel V., Sijacki D., Dolag K., 2010, MN-

RAS, 406, 936 Rees M. J., Ostriker J. P., 1977, MNRAS, 179, 541 Salpeter E. E., 1955, ApJ, 121, 161 Saro A., De Lucia G., Borgani S., Dolag K., 2010,

ArXiv:1001.3115 Sawala T., Scannapieco C., Maio U., White S., 2010, MNRAS, 402, 1599 Scannapieco C., White S. D. M., Springel V., Tissera P. B., 2009, MNRAS, 396, 696

Schaye J., Dalla Vecchia C., Booth C. M., Wiersma R. P. C., Theuns T., Haas M. R., Bertone S., Duﬀy A. R., McCarthy I. G., van de Voort F., 2010a, MNRAS, 402, 1536

Schaye J., Dalla Vecchia C., Booth C. M., Wiersma R. P. C., Theuns T., Haas M. R., Bertone S., Duﬀy A. R., McCarthy I. G., van de Voort F., 2010b, MNRAS, 402, 1536

Shakura N. I., Sunyaev R. A., 1973, A&A, 24, 337 Sijacki D., Springel V., Di Matteo T., Hernquist L., 2007,

MNRAS, 380, 877 Silk J., 1977, ApJ, 211, 638 Skory S., Turk M. J., Norman M. L., Coil A. L., 2010,

ApJS, 191, 43

Somerville R. S., Barden M., Rix H., Bell E. F., Beckwith S. V. W., Borch A., Caldwell J. A. R., H¨außler B., Heymans C., Jahnke K., Jogee S., McIntosh D. H., Meisen-

heimer K., Peng C. Y., S´anchez S. F., Wisotzki L., Wolf C., 2008, ApJ, 672, 776

Somerville R. S., Gilmore R., Primack J., Domı´nguez A., 2011, MNRAS Somerville R. S., Hopkins P. F., Cox T. J., Robertson B. E.,

- Hernquist L., 2008a, MNRAS, 391, 481

Somerville R. S., Hopkins P. F., Cox T. J., Robertson B. E.,

- Hernquist L., 2008b, MNRAS, 391, 481


Somerville R. S., Kolatt T. S., 1999, MNRAS, 305, 1 Somerville R. S., Primack J. R., 1999, MNRAS, 310, 1087 Spergel D. N., Verde L., Peiris H. V., Komatsu E., Nolta

M. R., Bennett C. L., Halpern M., Hinshaw G., Jarosik N., Kogut A., Limon M., Meyer S. S., Page L., Tucker G. S., Weiland J. L., Wollack E., Wright E. L., 2003, ApJS, 148, 175

Springel V., Hernquist L., 2003, MNRAS, 339, 289 Springel V., Wang J., Vogelsberger M., Ludlow A., Jenkins

A., Helmi A., Navarro J. F., Frenk C. S., White S. D. M., 2008, MNRAS, 391, 1685

Springel V., White S. D. M., Jenkins A., Frenk C. S., Yoshida N., Gao L., Navarro J., Thacker R., Croton D., Helly J., Peacock J. A., Cole S., Thomas P., Couchman H., Evrard A., Colberg J., Pearce F., 2005, Nature, 435, 629

Springel V., White S. D. M., Tormen G., Kauﬀmann G., 2001, MNRAS, 328, 726 Springel V., Yoshida N., White S. D. M., 2001, New Astronomy, 6, 79 Stringer M. J., Brooks A. M., Benson A. J., Governato F., 2010, ArXiv:1001.0594

Teyssier R., Chapon D., Bournaud F., 2010, ApJ, 720, L149 Teyssier R., Moore B., Martizzi D., Dubois Y., Mayer L.,

2010, ArXiv:1003.4744 Theuns T., Leonard A., Efstathiou G., Pearce F. R.,

Thomas P. A., 1998, MNRAS, 301, 478 Vestergaard M., 2004, ApJ, 601, 676 Wadepuhl M., Springel V., 2011, MNRAS, 410, 1975 Wadsley J. W., Stadel J., Quinn T., 2004, NewA, 9, 137 Wake D. A., Whitaker K. E., Labbe´ I., van Dokkum P. G.,

Franx M., Quadri R., Brammer G., Kriek M., Lundgren B. F., Marchesini D., Muzzin A., 2011, ApJ, 728, 46

Wechsler R. H., Zentner A. R., Bullock J. S., Kravtsov A. V., Allgood B., 2006, ApJ, 652, 71

Weinmann S. M., Kauﬀmann G., van den Bosch F. C., Pasquali A., McIntosh D. H., Mo H., Yang X., Guo Y., 2009, MNRAS, 394, 1213

Weller J., Ostriker J. P., Bode P., Shaw L., 2005, MNRAS, 364, 823 White S. D. M., Frenk C. S., 1991, ApJ, 379, 52

- White S. D. M., Rees M. J., 1978a, MNRAS, 183, 341
- White S. D. M., Rees M. J., 1978b, MNRAS, 183, 341 Yoshida N., Stoehr F., Springel V., White S. D. M., 2002,


MNRAS, 335, 762 Zehavi E., Leshem A., Levanda R., Han Z., 2010,

ArXiv:1008.1372 Zehavi I., Patiri S., Zheng Z., 2011, ArXiv:1104.0389 Zhang J., Ma C., Fakhouri O., 2008, MNRAS, 387, L13 Zheng Z., Coil A. L., Zehavi I., 2007, ApJ, 667, 760

| | |
|---|---|


Figure A1. Upper panel: comparison of aggregation history for halo M0501, with total mass 3.0×1012M⊙, for two diﬀerent resolutions (2x: red dotted line and 4x: black solid line). Intermediate panel: Number of minor mergers (> 10 : 1) as a function of lookback time for the two diﬀerent resolutions. Lower panel: Number of major mergers (< 10 : 1) as a function of lookback time for the two diﬀerent resolutions.

APPENDIX A: EFFECTS OF NUMERICAL RESOLUTION

A1 Dark matter component

For one high and low mass halo with ﬁnal masses of Mhalo = 3 × 1012M⊙ (M0501) and of Mhalo = 8 × 1011M⊙ (M1646), we have performed re-simulations with 4× the original spatial resolution. We traced back the particles that are closer than 2 × r200 to the center of the halo in any of our snapshots and replace them with dark matter and gas particles of higher resolution, achieving a 16× better mass resolution in the high resolution region than in the original simulation: mDM = 2.5 × 106M⊙h−1 and mGas = mStar = 5 × 105M⊙h−1. The mass aggregation history of the dark matter component in both halos is very similar for the two diﬀerent resolution limits as shown in the upper panel of

Figure A2. Same as Fig. A1, but for halo M1646, with a smaller mass of 8.0 × 1011M⊙.

Figs. A1 and A2. In the middle and lower panel of Figs. A1 and A2, one can see from the histograms of major (> 1 : 10) and minor mergers (< 1 : 10) that the number of major mergers stays almost the same, while as expected, we can resolve more minor mergers (< 1 : 10) in the higher resolution case. This suggests that, since galaxy formation in the SAMs is mainly inﬂuenced by the accretion history of the main halo and by major merger events (> 1 : 10), the results from the SAMs are expected to be well-converged in our re-simulations.

Figure A3. Evolution of the baryonic components for two different mass resolutions (2x: dotted lines, 4x: solid lines) for halo M0501. The upper panel shows the evolution of the stellar component, the middle panel the evolution of the cold gas fraction and the lower panel shows the hot halo gas component. Black lines illustrate the re-simulations, and colored lines show the diﬀerent SAM versions (see main text).

in both the SAMs and the simulations. Therefore, due to computational costs, we restrict our main study to 2× resimulations.

A2 Baryonic components

Figs. A3 and A4 show explicitly the evolution of the star, cold and hot gas mass in SAMs and simulations based on the trees from the two re-simulated individual halos for 2 × and 4 × higher resolution. As expected from the similar evolution of the dark matter component, for both the low and the high mass halo re-simulations, we ﬁnd no signiﬁcant diﬀerence in the evolution of the central galaxy/main halo

### Figure A4. Same as Fig. A3, but for halo M1646.

