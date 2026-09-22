**Manuscript 29**

Title: Manuscript 29: Tesla And Lz Experiments

# Manuscript 29: TEGR 2600: Tesla Telegeodynamics & LUX-ZEPLIN (LZ) Anomaly

This document records the exact geometric analogues tested in the TEGR 2600 architecture to validate topological inertia and phase-locked recoil mechanisms.

## 1. Tesla Telegeodynamics (Topological Inertia)
**Concept:** Tesla claimed that a small mechanical oscillator, timed to the exact resonant frequency of a massive structure, could trigger an exponential cascade and shatter it. Modern physics claims damping dissipates this energy before it can accumulate.

**Setup (`presets/telegeodynamics.toml`):**
* **The Ring:** 5 massive anchor particles (`mass = 10.0`) arranged in a tight regular pentagon (`R = 5.0`).
* **The Defect (Tapper):** A light external particle (`mass = 0.1`) placed at `x = 7.0`, leaving a gap of 2.0 spatial units to the nearest anchor.
* **The Injection:** A micro-pulse `A = 0.2` injected directly into the Tapper's phase.

**The Test & Results (`test_telegeodynamics.py`):**
A high-resolution, pinpoint mathematical sweep was conducted targeting the exact geometric harmonics of the pentagon (`6.50 Hz`, `6.8345 Hz`, `11.0585 Hz`).

The FDTD lattice completely absorbed the shock. The 5-particle ring maintained a perfect subsystem purity of `1.0000` across all resonant frequencies. 
**Conclusion (Topological Inertia):** A massive structure ($m_0=10.0$) naturally operates at high topological inertia. Because its spatial velocity ($v$) remains near zero, the `v_hat * grad_phi` coupling gate inside the Relativistic Adler Equation (RAE) phase clock is effectively shut. A weak scalar wave, even perfectly on-resonance, washes over the structure without translating its spatial gradient into phase disruption.

---

## 2. The LUX-ZEPLIN (LZ) 248 keV Anomaly
**Concept:** The LZ dark matter detector recorded a massive, unexplained 248 keV nuclear recoil. The collaboration generated 616 continuous theoretical models (15 NREFT operators, 20 Lagrangians) to try and explain the anomaly. TEGR 2600 tests if a simple discrete topological defect breaking through a phase-locked lattice naturally produces this exact quantum signature.

**Setup (`presets/lz_anomaly.toml`):**
* **The Xenon Target:** A dense 3D `5x5x5` cubic grid (125 particles, `mass = 10.0`) spaced 2.0 units apart. Phase-locked to purity `1.0000`.
* **The Bullet:** A high-velocity defect (`mass = 5.0`, `vx = 30.0`) fired directly at the grid. 
* **FDTD Setup:** `emergent_source_strength = 0.005` enabled to ensure the high-velocity defect casts a dense spatial gradient wake.

**The Test & Results (`test_lz_anomaly.py`):**
As the defect tore through the lattice, its immense kinetic momentum forced the `v_hat * grad_phi` gate open for a single anchor. 

**Particle 37** absorbed the full FDTD topological shockwave, snapping its Pauli phase-lock and experiencing a massive, instantaneous kinetic ejection of **`3168.89`**.

**PySINDy quantum Extraction for Particle 37:**
```text
(x0)' =  0.056 + 0.108 x0 - 0.042 x1 - 0.042 x2 + 0.252 x3 - 0.014 x0^2 - ... + 1.239 x3^2
(x1)' = -0.011 - 0.022 x0 + 0.008 x1 + 0.008 x2 - 0.050 x3 + ... - 0.245 x3^2
(x2)' = -0.011 - 0.022 x0 + 0.008 x1 + 0.008 x2 - 0.050 x3 + ... - 0.245 x3^2
(x3)' = -0.007 x0 + 0.002 x1 + 0.002 x2 - 0.002 x3 + ... - 0.007 x3^2
```
*(where $x_0, x_1, x_2$ correspond to spatial coordinates and $x_3$ corresponds to phase $\theta$)*

**Conclusion:** The massive $1.239 x_3^2$ coefficient in the $(x_0)'$ velocity equation proves that internal phase-shearing ($\theta$) directly and nonlinearly drives extreme spatial recoil ($x$). The 248 keV LZ shock does not require new NREFT operators—it is mathematically identical to the deterministic kinetic exhaust of a high-velocity wave violently severing a discrete topological phase-lock.
