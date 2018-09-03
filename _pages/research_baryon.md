---
permalink: /research/baryon_mitigation/
title: "Modeling baryonic effects"
excerpt: "Hdfdsafdsa"
author_profile: false
sidebar:
  nav: "research"
---

The **PCA formalism** is an efficient baryonic physics mitigation technique. It utilizes suites of hydrodynamical simulations to build a set of principal components (PCs) to describe the modification of observables by baryonic physics. The PCA formalism has the following nice features:
- Flexible parametrization to capture a range of possible redshift and scale dependences of baryonic effects on the matter distribution, which is still highly uncertain from the constraints of hydrodynamical simulations.
- Not opening up too much degrees of freedom such that the cosmological information gained from small-scale modes being completely depleted due to model uncertainties. 


## How does PCA work ? 

`Step 1` **Build difference matrix** <b>Δ</b>

<img src="/images/Delta.png" style="float: left; width: 355px; margin-left: 0.1em; margin-right: 0.5em; margin-top: 0.0em; margin-bottom: 0.1em;">

We collect several hydrodynamical simulations to generate baryon-contaminated model vectors <b>B<sub>sim</sub></b> in the same format as the cosmic shear observables. Then build a difference matrix with each of the column quantifying the baryonic feature in terms of the difference between the baryon-contamiated and the pure DMO model vectors, <b>B<sub>sim x</sub></b>-<b>M</b>.

`Step 2` **Derive the noise-weighted difference matrix** <b>Δ<sub>ch</sub></b>

<img src="/images/Delta_ch.png" style="float: left; width: 370px; margin-left: 0.1em; margin-right: 0.5em; margin-top: 0.0em; margin-bottom: 0.1em;">
We weight the difference matrix <b>Δ</b> by the noise factor <b>L<sup>-1</sup></b>. The <b>L</b> matrix can be view as the squire root of the covariance matrix <b>C</b> = <b>L L<sup>t</sup></b>. 

`Step 3` **Perform PCA on** <b>Δ<sub>ch</sub></b>

We idenfy the PC basis set of <b>Δ<sub>ch</sub></b> through the [singular value decomposition (SVD)](http://web.mit.edu/be.400/www/SVD/Singular_Value_Decomposition.htm) analysis. The first _N_ PC modes can be used to efficiently span the baryonic fluctuations in each column of <b>Δ<sub>ch</sub></b>, i.e. the <b>B<sub>sim x,ch</sub></b>-<b>M<sub>ch</sub></b> vector. 
<img src="/images/B_M.png" style="float: center; width: 380px; margin-left: 4em; margin-right: 0.5em; margin-top: 0.0em; margin-bottom: 0.1em;">


`Step 4` **Generating baryonic models via combination of PC modes**

We can construct models with baryonic features via 
<img src="/images/Mbary.png" style="float: center; width: 360px; margin-left: 5em; margin-right: 0.5em; margin-top: 0.0em; margin-bottom: 0.1em;">, \\
with the cosmological dependence coming in through the DMO theoritical models <b>M(p<sub>co</sub>)</b>, and the baryonic effects being characterized through the amplitudes of PC modes  Q<sub>i</sub>. 
We have validated the flexibility of this parametrization for an LSST-like survey under several baryonic scenarios. 

## Performances of PCA

[<img src="/images/MCMC_ill.png" style="float: center; width: 500px; margin-left: 3em">](/images/MCMC_ill.png)

We demonstrate in the above figure the effectiveness of applying the PCA technique to mitigate baryonic effects if our Universe were like the [Illustris](http://www.illustris-project.org) simulation. The biases in cosmological parameters reduced after marginalizing over few PC modes. 

<!---
<img src="https://latex.codecogs.com/svg.latex?\Large&space;\bold \Delta_{\rm ch}"/>
<img src="https://latex.codecogs.com/svg.latex?\Large&space;\bold B_{\rm sim} - \bold M "/>. 
-->


{% include base_path %}
