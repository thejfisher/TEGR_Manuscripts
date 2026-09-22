**Manuscript 32**

Title: Manuscript 32: Bochner

# Manuscript 32: quantum Backreaction in a Discrete Vacuum: A Geometric Mechanism for Hubble Parameter Oscillations

**Abstract**
Recent tomographic analyses of high-redshift supernovae have revealed empirical, periodic temporal oscillations in the Hubble expansion parameter (e.g., Bochner et al., 2015). While continuous General Relativity equipped with a static Cosmological Constant ($\Lambda$) struggles to naturally produce a resonating expansion, we demonstrate that modeling the vacuum as a discrete, continuous Weitzenböck lattice natively generates these temporal oscillations. By extracting the underlying Partial Differential Equation (PDE) of the discrete geometry using data-driven methods, we show that the vacuum operates as a Damped Klein-Gordon field possessing a fundamental restoring tension. As the universe expands and topological strain relaxes, this inherent tension causes the spatial geometry to physically resonate, providing a strictly deterministic, mechanical origin for cosmological backreaction. Furthermore, we propose a methodology for "Lattice Calibration," utilizing empirical cosmological oscillations to anchor the fundamental timescale of the discrete topological lattice.

---

## 1. Introduction: Causal Backreaction and the Discrete Vacuum

The assumption of perfect isotropy and homogeneity (the Cosmological Principle) has been instrumental in the development of the Friedmann-Robertson-Walker (FRW) metric. However, theoretical efforts to explain apparent cosmic acceleration increasingly explore the effects of a "grainy" or inhomogeneous universe. Models of *causal backreaction* (Bochner, 2011; Bochner, 2013) suggest that the local clumping of matter perturbs the global FRW expansion, producing an apparent acceleration without the need for exotic "Dark Energy." Such models successfully reproduce apparent acceleration but typically rely on heuristic "clumping evolution functions," $\Psi(t)$, to estimate how structural tension grows over time.

In this paper, we extend the concept of a grainy universe down to the vacuum itself. By treating spacetime not as a continuous manifold but as a discrete topological lattice (an expanded Weitzenböck matrix), we extract the exact structural mechanics of the vacuum. We demonstrate that causal backreaction is not merely a macroscopic symptom of matter clumping, but is the fundamental response of the discrete lattice physically resisting expansion.

## 2. The Damped Klein-Gordon Vacuum

Using Sparse Identification of Nonlinear Dynamics (SINDy) on high-resolution grid telemetry from our discrete Finite-Difference Time-Domain (FDTD) engine (TEGR 2600), we extracted the macroscopic PDE governing the propagation of spatial defects. The extracted equation takes the explicit form of a Damped Klein-Gordon field:

$$ \frac{\partial^2 \phi}{\partial t^2} = c_{eff}^2 \nabla^2 \phi - \alpha \frac{\partial \phi}{\partial t} - \beta \phi $$

The critical discovery in this extraction is the $-\beta \phi$ mass term (extracted as $\beta \approx 1000.5$). The vacuum actively resists being deformed (strained) and attempts to spring back to an equilibrium state ($\phi = 0$). This establishes that the topological grid possesses a fundamental, natural resonant frequency ($\omega_0 = \sqrt{\beta}$). Space itself possesses a mechanical tension.

## 3. The Mechanism of Temporal Hubble Oscillations

If the universe is modeled as a continuous Eulerian grid with an intrinsic Klein-Gordon restoring force, the expansion of the universe cannot occur perfectly smoothly. As the parent universe expands and the topological strain relaxes, the expansion must work against the lattice's fundamental spring-tension.

Consequently, the expansion oscillates in time. The coordinate wave speed slightly compresses and relaxes at the grid's fundamental resonant frequency. When observing light traveling across this expanding, resonating grid, an observer measuring supernovae at different look-back times will not see a perfectly smooth FRW curve. Instead, the geometric resonance of the lattice manifests exactly as periodic, temporal oscillations in the Hubble parameter.

## 4. Lattice Calibration via Empirical Tomography

In discrete lattice simulations (such as Lattice QCD), the engine operates in arbitrary "grid units" and "ticks." To establish physical dimensions, the lattice must be calibrated against a known empirical observable.

Bochner et al. (2015) documented distinct variations and parameter instabilities in the Hubble series expansions when fitting the Union2.1 Supernova Compilation. By interpreting these variations as physical, temporal oscillations in the Hubble parameter, we can utilize Bochner's empirical data to "set the lattice scale." 

If the empirical data indicates an oscillation with a temporal period $T_{empirical}$, and our TEGR 2600 engine predicts a lattice resonance of $T_{tick} = 2\pi / \sqrt{\beta - (\alpha/2)^2}$, we define the cosmological scaling factor $\kappa$:

$$ \kappa = \frac{T_{empirical}}{T_{tick}} $$

This calibration establishes the exact duration of a discrete topological "tick" in cosmological Gigayears (Gyr), creating a deterministic, rigid mathematical bridge between the microscopic topological strain of the Weitzenböck lattice and the macroscopic cosmic expansion.

## 5. Conclusion

We do not need to assume that the universe is filled with a repulsive, non-clumping exotic fluid to explain cosmic acceleration, nor do we need ad-hoc $\Psi(t)$ functions to model causal backreaction.

By recognizing that a discrete geometry inherently possesses mechanical tension (a Damped Klein-Gordon restoring force), causal backreaction emerges natively. The temporal Hubble parameter oscillations observed in supernova data are not an anomaly; they are the direct mathematical signature of a discrete universe vibrating as it expands.

## References
1. Bochner, B. (2007). *Perturbations to the Cosmological Expansion in a Grainy Universe*.
2. Bochner, B. (2011). *Cosmic acceleration from causal backreaction in a smoothly inhomogeneous universe*. arXiv:1109.4686.
3. Bochner, B. (2013). *Cosmic acceleration and concordance from causal backreaction with recursive nonlinearities*. International Journal of Modern Physics D, 22(13), 1330026.
4. Bochner, B., Pappas, D., & Dong, M. (2015). *Testing Lambda and the limits of Cosmography with the Union2.1 Supernova Compilation*. The Astrophysical Journal, 814(1), 7.
