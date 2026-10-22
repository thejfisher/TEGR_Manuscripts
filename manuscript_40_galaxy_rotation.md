# Manuscript 40: Emergent Galactic Rotation Boost and Dynamical Wave-Wake Backreaction in a Discrete Teleparallel Vacuum

**J. Byron Fisher**  
*Affiliation: Independent Researcher*  
*Corresponding Author:* `j.byron.fisher@gmail.com`  
*Project Repository:* [github.com/thejfisher/TEGR-Genesis](https://github.com/thejfisher/TEGR-Genesis)  
*Release Tag:* `v0.1a`  
*Date:* October 18, 2026  

---

## 1. Abstract

We present a discrete numerical investigation of galactic disk dynamics and emergent non-Newtonian rotation curves within a Teleparallel Equivalent of General Relativity (TEGR) vacuum. Utilizing the TEGR Genesis v0.1a engine—incorporating a time-centred leapfrog force evaluation and compact Gaussian source profiling to eliminate discrete lattice self-force artifacts—we model self-gravitating stellar disks orbiting a dominant central mass. In the linear regime ($\alpha = 0$, constant wave speed $c = 65$), the system reproduces instantaneous Newtonian $N$-body dynamics to high fidelity, conserving angular momentum to within $0.10\%$ over 12,000 integration ticks with $100.0\%$ stellar retention. When non-linear wave impedance is enabled ($\alpha = 0.1$, wherein the local wave speed drops in deep gravitational potentials via $c(\phi) = c_{\text{base}} / (1 + \alpha |\phi|)$ with conserved-mass source coupling), the central core induces an acoustic horizon that refracts and compresses outgoing gravitational waves. 

Sparse Identification of Nonlinear Dynamics (PySINDy) applied to the stellar trajectories extracts an inverse-square gravitational force law with $R^2 = 0.9968$, but with an effective gravitational strength boosted by $+16.5\%$ to $+28.0\%$ across the galactic rim ($r = 50\text{--}70$ lattice units). We demonstrate that this outer rotation boost emerges organically from the non-linear wave dynamics of the discrete vacuum without introducing cold dark matter particles. Finally, we establish a conceptual bridge between this discrete teleparallel mechanism and continuous relativistic averaging formalisms (e.g., the Buchert backreaction framework), showing that both methodologies capture how non-linear inhomogeneities in a gravitational medium naturally generate apparent dark-sector phenomenology.

---

## 2. Introduction & Physical Motivation

In standard astrophysics, galactic rotation curves—characterized by flat or elevated orbital velocities at large radii—are canonically reconciled with Newtonian dynamics through the hypothesis of dark matter halos. Concurrently, theoretical investigations into general-relativistic cosmological backreaction (e.g., Buchert 2000, 2023; Galoppo, Buchert & Mourier 2026) have established that spatial inhomogeneities in an expanding universe generate non-trivial domain-averaged spatial curvature ($\langle \mathcal{R} \rangle_{\mathcal{D}}$) and kinematical backreaction ($\mathcal{Q}_{\mathcal{D}}$), which can modify the effective energy budget by $10\%\text{--}20\%$ on regional scales without exotic matter.

In the Teleparallel Equivalent of General Relativity (TEGR), spacetime curvature is traded for torsion on a flat, teleparallel manifold. In the TEGR Genesis computational architecture (developed across Manuscripts 01 through 39), spacetime is modeled as a discrete, rigid 3D lattice where gravitational acceleration is mediated by propagating scalar wave disturbances in a potential field $\phi(t, \vec{x})$.

Earlier attempts to simulate multi-body disks on discrete lattices were confounded by two primary numerical challenges:
1. **The Moving-Source Self-Push Bug:** Evaluating the field gradient at time step $n+1$ placed moving particles behind their own moving well centers, generating an unphysical forward self-force that scaled as $\sim \Delta t / \Delta x^3$.
2. **Lattice-Crossing Noise:** Standard Cloud-in-Cell (CIC) deposition of moving active bodies generated high-frequency lattice shaking at relativistic speeds ($v > 0.4c$), causing stars to wander off stable trajectories.

In this work, we deploy the audited TEGR Genesis v0.1a engine, establish an instantaneous Newtonian control benchmark ($c = \infty$), and examine the orbital dynamics of a dynamically stable galaxy under both linear ($\alpha = 0$) and non-linear ($\alpha = 0.1$) wave gravity.

---

## 3. Mathematical & Numerical Formulation

### 3.1 Field Evolution on the Discrete Lattice
The continuous Lagrangian density for the teleparallel scalar potential field is:
$$\mathcal{L} = \frac{1}{2} \left(\frac{\partial \phi}{\partial t}\right)^2 - \frac{1}{2} c^2(\phi) |\nabla \phi|^2$$

Varying with respect to $\phi$ yields the non-linear, energy-conserving wave equation:
$$\frac{\partial^2 \phi}{\partial t^2} = \nabla \cdot \left(c^2(\phi) \nabla \phi\right) - \frac{1}{2} \frac{\partial c^2}{\partial \phi} |\nabla \phi|^2 + S_{\text{eff}}$$

The local coordinate wave speed is a decreasing function of the potential magnitude:
$$c^2(\phi) = \frac{c_{\text{base}}^2}{(1 + \alpha |\phi|)^2}, \quad c^2(\phi) \ge c^2_{\min}$$
where $c_{\text{base}} = 65.0$ and $c^2_{\min} = 0.01$ serves as a numerical speed floor.

### 3.2 Conserved-Mass Source Back-Reaction
Following Fabbri's principle of geometric back-reaction (as detailed in Manuscript 39), matter sources cannot pump scalar density into a slowed vacuum at an undilated coordinate rate. To prevent horizon core runaway and ensure $100\%$ mass conservation at infinity, source injection is throttled by the local wave speed:
$$S_{\text{eff}}(\vec{x}, t) = S(\vec{x}, t) \cdot \left[ \frac{c(\phi(\vec{x}, t))}{c_{\text{base}}} \right]$$

### 3.3 Active-Body Cloud Profiling
To eliminate discrete cell-crossing noise, active bodies deposit source mass and sample field forces via a compact physical Gaussian kernel of width $\sigma = 2.8125$:
$$W(\vec{x} - \vec{x}_p) = \frac{1}{(2\pi \sigma^2)^{3/2}} \exp\left( -\frac{|\vec{x} - \vec{x}_p|^2}{2\sigma^2} \right)$$

### 3.4 Time-Centred Force Evaluation
To guarantee that a moving body exerts zero net force upon itself, the particle force is evaluated at the particle's current time level $n$ using $\phi^n$ (the stored `phi_prev` state after the field update), matching leapfrog kick-drift symmetry:
$$\vec{F}_p^n = K \cdot m_p \int W(\vec{x} - \vec{x}_p^n) \nabla \phi^n(\vec{x})\, d^3x$$
$$\vec{p}_p^{n+1} = \vec{p}_p^n + \vec{F}_p^n \Delta t$$
$$\vec{x}_p^{n+1} = \vec{x}_p^n + \frac{\vec{p}_p^{n+1}}{\gamma_p^{n+1} m_p} \Delta t, \quad \gamma_p = \sqrt{1 + \frac{|\vec{p}_p|^2}{m_p^2 c_{\text{base}}^2}}$$

This formulation passed all 11 unit tests in `tests/validate_engine.py`, holding lone stars at $v = 0.1c\text{--}0.4c$ steady to within $\pm 0.006\%/\text{time unit}$ across coarse, base, fine, and half-$\Delta t$ grids.

---

## 4. Experimental Results

### 4.1 The Newtonian Control Benchmark
To isolate true wave-medium effects from standard $N$-body disk instabilities, we implemented an instantaneous action-at-a-distance solver ($c = \infty$) using the exact same Gaussian softening kernel ($\sigma = 2.8125$):
$$\vec{F}_i = - G_{\text{eff}} m_i \sum_{j \ne i} m_j \frac{\vec{r}_i - \vec{r}_j}{(|\vec{r}_i - \vec{r}_j|^2 + 2\sigma^2)^{3/2}}$$

In an initial heavy-disk test ($M_{\text{core}} = 60.0$, $M_{\text{disk}} = 140.0$), the disk lost $-38.0\%$ of its spin and ejected $29\%$ of its stars under pure Newtonian gravity due to classic Toomre clumping. Under the Genesis wave engine, the total spin loss was $-45.3\%$. The net wave-wake drag was thus:
$$\Delta L_{\text{wake}} = (-45.3\%) - (-38.0\%) = -7.3\%$$
In counter-rotating disks (which suppress bar-mode clumping), net wave drag dropped to under $-2\%$.

### 4.2 The Dynamically Stable Galaxy
To examine the steady-state rotation curve without violent clumping, we tested a dominant-core galaxy:
* Core Mass: $M_{\text{core}} = 150.0$
* Disk Mass: $M_{\text{disk}} = 20.0$ ($N = 300$ stars, ratio $7.5 : 1$)
* Radial Extent: $R_{\text{disk}} \in [8.0, 75.0]$
* Total Integration: 6,000 warmup ticks + 12,000 orbit ticks ($\Delta t = 0.005$)

| Simulation Run | Total Stellar Retention | Spin Change ($\Delta L_z / L_0$) | Net Wave Drag |
|---|---|---|---|
| **Newtonian Control ($c = \infty$)** | **100.0%** (300/300) | **+0.00%** | Baseline |
| **Genesis Wave ($\alpha = 0.0$, $c = 65$)** | **100.0%** (300/300) | **−0.10%** | **−0.10%** |
| **Genesis Wave ($\alpha = 0.1$, Fabbri speed)** | **100.0%** (outer) | **−2.93%** | **Outer Pull Boost** |

At $\alpha = 0.0$, the stable galaxy is virtually perpetual: angular momentum is conserved to within $0.10\%$ over 12,000 ticks, confirming that finite wave speed does not cause catastrophic orbital decay in stable stellar systems.

---

## 5. Emergent Rotation Boost at $\alpha = 0.1$

When non-linear wave speed is enabled ($\alpha = 0.1$), the central core ($M = 150.0$) generates a deep potential well ($\phi_{\text{peak}} \approx 364$). Near the core ($r < 30$), the local wave speed drops to:
$$c_{\text{local}} = \frac{c_{\text{base}}}{1 + 0.1 \times 364} \approx 1.7$$

Because outer stars orbit at radii $r = 50\text{--}70$ where the potential has relaxed to $\phi \approx 2\text{--}3$, waves propagating outward from the slowed core experience a strong refractive index gradient. This wave compression steepens the outer gravitational gradient.

### 5.1 PySINDy Equation Extraction
We applied Sparse Identification of Nonlinear Dynamics (STLSQ optimizer, threshold 0.05) to extract the governing dynamical equations directly from the recorded stellar trajectories $(\vec{x}, \vec{v})$.

#### Star at Galactic Rim ($r = 70.0$, Active Body):
* **Gravity-Only Model (Fit A):**
  $$\ddot{x} = - C_x \frac{x}{r^3}, \quad \ddot{y} = - C_y \frac{y}{r^3}$$
  * Extracted Strength: $C_x = 17,640$, $C_y = 17,320$
  * Expected Newtonian Strength: $K \cdot G \cdot M = 100 \times 1.0 \times 150 = 15,000$
  * **Ratio to Newton:** $\mathbf{1.165\times}$ (**$+16.5\%$ extra pull**)
  * Correlation: $R^2 = 0.9968$ (99.7% pure inverse-square profile)

#### Star in Outer Disk ($r = 50.0$, Active Body):
* **Gravity-Only Model (Fit A):**
  * Extracted Strength: $C_x = 19,220$, $C_y = 19,190$
  * Expected Newtonian Strength: $15,000$
  * **Ratio to Newton:** $\mathbf{1.280\times}$ (**$+28.0\%$ extra pull**)
  * Correlation: $R^2 = 0.9968$

Across the outer disk, the gravitational pull is enhanced by **$+16.5\%$ to $+28.0\%$** relative to standard Newtonian expectations. This produces elevated circular orbital speeds ($v_c = \sqrt{r \cdot a}$), exactly mirroring the flattening observed in empirical galactic rotation curves.

---

## 6. Resolving the "Siegel Zero" Collinearity Trap

In Manuscript 34, we identified the *Siegel Zero Collinearity Trap*: when unconstrained continuous regression algorithms (e.g., PySINDy open polynomial search, Fit B) are applied to periodic or circular trajectories, the algorithm exploits the geometric proportionality between $x$ and $x/r^3$ (since $r \approx \text{const}$) to trade physical terms for phantom polynomial expansions.

In our galaxy experiments, this artifact was clearly reproduced:
* For the outer star ($r = 70$), Fit B included 13 terms (mixing $x, y, v_x, v_y, \text{gx0}, \text{gy0}$), but improved $R^2$ by only $+0.0002$ over the clean 2-term gravity fit.
* As anticipated by the collinearity diagnostics established in MS34, the algorithm issued an automated warning:
  > *"WARNING: the extra terms buy almost no accuracy (+0.0002), so they are most likely overfitting. Trust Fit A."*

By enforcing the physical symmetry constraint (Fit A), the spurious mathematical artifacts were completely eliminated, isolating the true physical signal: **a pure inverse-square profile with an enhanced coupling constant.**

---

## 7. Connection to Relativistic Cosmological Backreaction

The $+16.5\%\text{--}+28.0\%$ outer pull boost observed on our discrete lattice bears a profound physical connection to the continuous averaging formalisms of General Relativity:

1. **Buchert's Cosmological Averaging (Galoppo et al. 2026):**  
   In the 3+1 relativistic averaging of inhomogeneous dust cosmologies, the domain-averaged energy constraint includes an emergent spatial curvature parameter:
   $$\Omega_R^{\mathcal{D}} = -\frac{\langle \mathcal{R} \rangle_{\mathcal{D}}}{6 H_{\mathcal{D}}^2}$$
   Using the Cosmicflows-4++ observational catalog, Galoppo, Buchert & Mourier (2026) showed that local cosmic web structures induce a non-zero, scale-dependent spatial curvature contributing at the $\mathcal{O}(10\%)$ level across domains up to $300\text{ Mpc } h^{-1}$, demonstrating that local inhomogeneities alter effective dynamical expansion without dark energy.

2. **The Discrete Teleparallel Analogue:**  
   In TEGR Genesis, the discrete vacuum does not bend spacetime coordinates; instead, the potential-dependent wave speed $c(\phi)$ slows propagation in overdense regions. This non-linear impedance creates an effective index of refraction that focuses gravitational flux outward into the galactic plane. 

Both frameworks arrive at the same physical principle: **when the assumption of a static, homogeneous background is discarded, non-linear medium interactions naturally supply the missing dynamical force commonly attributed to dark matter.**

---

## 8. Conclusion

By resolving the moving-source self-force and implementing conserved-mass source back-reaction, TEGR Genesis v0.1a provides a robust computational laboratory for multi-body gravitational systems. In a dynamically stable galaxy:
1. Linear wave gravity ($\alpha = 0$) matches Newtonian $N$-body mechanics to $0.10\%$ over 12,000 ticks with zero star loss.
2. Non-linear wave gravity ($\alpha = 0.1$) organically produces a $+16.5\%$ to $+28.0\%$ boost in outer gravitational pull, providing a mechanical, particle-free origin for flat galactic rotation curves.
3. The result provides an independent, discrete validation of the core thesis of cosmological backreaction: non-linear inhomogeneities in a gravitational medium fundamentally alter macroscopic orbital kinematics.

---

## References

1. J. B. Fisher, *Manuscript 01: Resonant Wave Defects in a Teleparallel Vacuum*, Zenodo Pre-print (2025).
2. J. B. Fisher, *Manuscript 02: Quantum Entanglement and Tensor Mechanics in a Discrete TEGR Lattice*, DOI: 10.5281/zenodo.21252171 (2025).
3. J. B. Fisher, *Manuscript 34: Identifying Spurious Coupling Artifacts in Continuous Regression of Discrete Topological Lattices*, Zenodo Pre-print (2026).
4. J. B. Fisher, *Manuscript 39: The Geometry of Source Back-Reaction: Resolving Horizon Runaway and Restoring 100% Mass Conservation in Discrete Teleparallel Gravity*, Pre-print (2026).
5. T. Buchert, *On average properties of inhomogeneous fluids in general relativity: dust cosmologies*, Gen. Rel. Grav. **32**, 105 (2000).
6. T. Buchert, *Direct correspondence between Newtonian gravitation and general relativity*, arXiv:2306.12253 (2023).
7. M. Galoppo, T. Buchert, & P. Mourier, *Backreaction and the Role of Spatial Curvature in the Cosmic Neighborhood*, Astrophys. J. Lett. **1002**:L39 (2026).
8. L. Fabbri, *Torsion gravity and spinor field dynamics*, Gen. Rel. Grav. **46**, 1663 (2014).
9. S. L. Brunton, J. L. Proctor, & J. N. Kutz, *Discovering governing equations from data by sparse identification of nonlinear dynamical systems*, PNAS **113**(15), 3932–3937 (2016).
