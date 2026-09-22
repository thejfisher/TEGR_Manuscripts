**Manuscript 8**

# Manuscript 08: Emergent Transference Wave Dynamics from quantum Wave Defects in a Teleparallel Vacuum

**J. Byron Fisher**  
*Affiliation (Independent Researcher)*  
Corresponding author: j.byron.fisher@gmail.com

---

## Abstract
The reconciliation of macroscopic spacetime geometry with microscopic quantum kinematics remains a central challenge in modern physics. Building upon the quantum extension of 10-dimensional space onto localized resonant wave defects in a Teleparallel Equivalent of General Relativity (TEGR) vacuum, we investigate the macroscopic limit of dense defect arrays. While discrete N-body pilot-wave mechanics rely on explicit computationally intensive $O(N^2)$ non-local calculations to route particles, we demonstrate via a data-driven approach that these interactions converge smoothly into a local continuum surrogate equation. Grounded in the recent field-theoretical formalism of TEGR—which proves that tetrad perturbations can act as finite dynamical fields—this continuum equation naturally routes non-interacting wave defects into discrete macroscopic probability distributions. Utilizing the Tonomura double-slit protocol, we show that simple restoring quantum couplings between spatial strain and internal phase are entirely sufficient to reproduce robust macroscopic bimodal banding and deterministic Bohmian-style phase routing. Crucially, this surrogate equation formally maps the transference wave not as a secondary or competing field, but as the underlying driving engine of the singular teleparallel wave structure—simultaneously operating through three distinct properties: phase, strain, and geometric displacement. This single-wave framework proves that transference wave dynamics emerge purely as an "in-between" topological consequence of this unified 10-dimensional teleparallel defect architecture.

---

## 1. Introduction: The quantum Synthesis

The mathematical framework of Kaluza-Klein theory traditionally invokes extra‑dimensional spacetime, while the Teleparallel Equivalent of General Relativity (TEGR) offers a flat four‑dimensional description of gravitation where torsion, rather than curvature, mediates gravitational effects. We have previously established a **quantum isomorphism** that maps the extra degrees of freedom of String Theory onto the internal state variables of localized resonant wave defects propagating in a flat TEGR vacuum.

In this paradigm, physics is not a competition between fundamental forces, but a synthesis. Gravity, electromagnetism, and Pauli exclusion emerge naturally from the local kinematic coupling of these wave-defects to the surrounding torsional spacetime (the Weitzenböck connection). 

However, simulating dense swarms of defects at the fundamental scale poses a severe computational challenge. Generating non-local probability distributions traditionally demands explicit $O(N^2)$ pairwise interactions, mirroring the complexity of the Schrödinger equation and traditional pilot-wave formulations. In this paper, we seek to find the "in-between"—the macroscopic continuum limit where the discrete 10D defect interactions smooth out into a generalized geometric field theory, and explore whether macroscopic transference wave dynamics can drop out naturally as an emergent outcome of that field.

---

## 2. Theoretical Foundation: Field-Theoretical TEGR

To model a macroscopic continuum limit, we must transition from tracking discrete point-like defects to treating the collective defect array as a dynamic perturbation on the spacetime.

The mathematical scaffolding for this approach has been rigorously established by the recent work of Emtsova & Petrov (2026) [1]. In their *field-theoretical formalism for TEGR*, they demonstrate that the teleparallel Lagrangian can be formulated such that background fields are separated from tetrad perturbations:
$$ e^a_\mu = \bar{e}^a_\mu + \kappa^a_\mu $$
Crucially, they prove that these tetrad perturbations ($\kappa^a_\mu$) are not restricted to infinitesimal approximations. They are exact, finite, dynamic fields propagating on the spacetime. Furthermore, by applying Noether's theorem to the dynamic Lagrangian of these perturbations, Emtsova and Petrov derive exact conserved currents. 

In our quantum isomorphism, the 10-variable defect array is not merely a generalized analogy, but a direct mapping to these symmetric TEGR perturbations. Emtsova and Petrov demonstrate that after applying local Lorentz gauge fixing to cancel the antisymmetric, non-dynamical degrees of freedom, the remaining symmetric part of the tetrad perturbation ($\varkappa_{(\mu\nu)}$) contains exactly 10 propagating degrees of freedom. The localized compression of spacetime ($\gamma$) and the de Broglie clock phase ($\theta$) operate as physical manifestations of these exact 10 degrees of freedom. Furthermore, the conserved currents derived in the field-theoretical formalism provide the rigorous guarantee that our macroscopic defect array will conserve its probability/energy currents deterministically, mirroring quantum probability conservation.

## 3. Deriving the Continuum Phase-Routing Equation

In earlier experiments, we observed that isolated resonant wave defects experience topological runaways (phase-slipping) when encountering massive strain, causing the unconstrained relativistic tension ($\gamma$) to diverge. This instability indicated a missing restoring force in the macroscopic continuum limit.

Rather than imposing a solution from quantum mechanics, we utilized a purely data-driven approach via Sparse Identification of Nonlinear Dynamics (SINDy). By feeding the explicit $O(N^2)$ N-body collision data to the optimizer, we extracted the generalized, local continuum equations dictating the defect propagation.

The data yielded a simple, stable **continuum phase-routing formula**. Initially, a mathematical bounding sequence was employed to prevent topological runaway (negative phase slipping). However, PySINDy autonomously extracted the robust Relativistic Adler Equation, which naturally resolves this bounding without artificial limits. (The algorithm's extraction of ostensibly "quantum" $	heta - \sin(	heta)$ collinearity structures from this classical quantum data is formally addressed in Manuscript 05). The pairwise interference summation collapses into just two primary variables:
1. **The Spatial Strain** ($\nabla \gamma$): The local deformation gradient of the tetrad field.
2. **The Restoring Phase-Spring**: The non-linear phase coupling term $-\kappa \sin(\theta - \bar{\theta})$ governs massive phase slips and discrete interference jumps. It simplifies to the linear Hookean term $+\kappa(\theta - \bar{\theta})$ only in the low-strain limit, when defects are nearly synchronized with the spacetime. This strict distinction prevents the equations from violating periodic boundary conditions at high relativistic tensions.

In this continuum surrogate, particles no longer explicitly calculate their distance to every other particle in the universe. Instead, they act as simple quantum defects surfing the continuous topological strain ($\gamma$) of the field.

---

## 4. Computational Validation: The Double Slit

To verify that the continuum surrogate equation retains the necessary quantum complexity to generate interference phenomena, we implemented the Tonomura double-slit protocol.

### 4.1 Protocol Parameters and Grid Mechanics
A beam of $N = 10,000$ independent wave defects (rest mass $m_0 = 0.511$ MeV, $p = 10.0$) was fired through a solid geometric barrier comprising two slits. The simulation relied entirely on the continuum phase-routing equation, meaning none of the $10,000$ particles possessed an explicit pairwise connection. 

To achieve this without explicit $O(N^2)$ pairwise Lagrangian calculations, the continuum spatial strain ($\nabla \gamma$) was evaluated on a discrete spatial mesh using a Finite-Difference Time-Domain (FDTD) matrix. The 10,000 defects functioned strictly as Lagrangian tracers propagating through this Eulerian FDTD grid. The grid itself held the Weitzenböck connection values, allowing the defects to read the local $\nabla \gamma$ gradient directly without polling the other 9,999 particles. They interacted only with this local torsional field strain generated by the barrier and the coherent plane-wave initialization.

### 4.2 Macroscopic Transference Fringes
The macroscopic result was unambiguous. As the defects tunneled through the slits and crossed the vacuum to the detection screen, the local spatial strain ($\nabla \gamma$) steered the non-interacting particles into distinct zones of constructive and destructive classical banding.

![Spatial Distribution of Screen Hits](MS8_Figure3_Spatial_Distribution.jpg)
*Figure 1: RAE-Guided Macroscopic Transference Fringes. The particles self-organize into discrete bands without explicit N-body wave equations.*

The resulting scatter plot of screen hits revealed three distinct, highly dense macroscopic bands—a structured transference wave distribution.

### 4.3 Microscopic Phase Routing: The Empirical SINDy Validation

By plotting the final hidden phase of the defects against their final landing position on the screen, we observe perfectly ordered stratification.

![The Phase Router](MS8_Figure4_Phase_Routing.png)
*Figure 2: The RAE Phase Router. Terminal screen position strongly correlates with the internal geometric clock phase.*

The phase router data confirms that Bohmian-style deterministic routing is completely intact under the continuum equation. During an aggressive Bohmian Reverse Integration test (Run 40: $p=51.3$, $24\%$ screen penetration, zero crossing violations), PySINDy successfully extracted the empirical formula governing the phase evolution of the defect ($\partial \theta / \partial t$, mapped as `hue'`). 

The extraction yielded an extraordinarily deterministic $R^2 = 0.9818$, isolating three critical quantum terms:

$$ \text{hue}' = \dots - 1073.799 \, \text{hue} + 303.563 \sin(\text{hue}) - 140.594 \, m_0 \dots $$

1. **The Massive Restoring Force (The Topological Anchor): $-1073.799 \, \text{hue}$**  
This is the massive linear Hookean restoring phase-spring. It actively fights to yank the internal phase clock back to a stable baseline, mechanically anchoring the particle to the underlying geometric spacetime.
2. **The Soliton Defense: $+ 303.563 \sin(\text{hue})$**  
Because the linear spring is so aggressive, the geometric engine balances the equation with an opposing sine-Gordon topological soliton. This is the non-linear geometric phase synchronization limit ($-\kappa \sin(\theta - \bar{\theta})$) defending the discrete phase jumps from the massive linear damping of the spacetime.
3. **The Thermodynamic Toll: $-140.594 \, m_0$**  
The internal phase clock's evolution is directly penalized by its own rest mass. The heavier the particle, the slower its phase ticks. This is the organic, quantum emergence of Relativistic Time Dilation.

This explicit regression validates the Relativistic Adler Equation, proving that the continuum formula successfully guides particles into discrete macroscopic bands based strictly on deterministic, geometric kinematics.

---

## 5. Discussion: The "In-Between"

The presence of structured transference fringes in a simulation lacking the explicit Schrödinger equation—and lacking explicit $O(N^2)$ pilot-wave summations—is highly instructive.

It suggests that quantum mechanics does not necessarily need to be an axiomatic starting point for fundamental physics. Instead, macroscopic transference wave distributions can emerge as the "in-between" outcome—the natural deterministic statistical behavior of 10-dimensional topological wave defects surfing a flat, 4-dimensional torsional spacetime (TEGR). 

By anchoring this behavior in Emtsova and Petrov's field-theoretical TEGR perturbations, we establish a rigorous classical foundation for these emergent effects without introducing conflicting, multi-wave mechanics. The wave-particle duality is resolved cleanly within a strictly singular framework: the particle is the localized core of the tetrad defect, and the wavefunction is mathematically defined as the dynamic perturbation ($\kappa^a_\mu$) propagating through the Weitzenböck connection. Acting as the driving engine of this single wave structure, it routes the defect through the unified properties of phase, spatial strain, and geometric displacement. 

### 5.1 Limitations
As discussed in our primary work, this framework operates strictly within the paradigm of local realism and the causal wave impedance of spacetime ($v \le c$). It successfully reproduces localized transference geometries but inherently does not model instantaneous non-local interaction beyond the light cone.

---

## References

1. Emtsova, E. D., & Petrov, A. N. (2026). *The field-theoretical formalism for TEGR*. arXiv:2605.23376v1 [gr-qc].
2. Einstein, A. (1916). *The foundation of the general theory of relativity.* Annalen der Physik, 49, 769–822.
3. Hayashi, K., & Shirafuji, T. (1979). *New General Relativity.* Phys. Rev. D, 19, 3524–3553.
4. Tonomura, A., et al. (1989). *Demonstration of single-electron buildup of an interference pattern.* American Journal of Physics, 57(2), 117-120.
5. Arndt, M., et al. (1999). *Wave-particle duality of C60 molecules.* Nature, 401(6754), 680-682.
6. Bochner, S. (1946). *Vector fields and Ricci curvature.* Bulletin of the American Mathematical Society, 52(9), 776-797.
7. Fisher, J. B. (2026). *Resonant Wave Defects in a Teleparallel Vacuum: A quantum Extension of 10-Dimensional Space in Flat Spacetime.*
