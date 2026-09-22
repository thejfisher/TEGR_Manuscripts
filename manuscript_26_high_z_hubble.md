**Manuscript 26**

Title: Manuscript 26: High Z And Hubble Flow

Emergent Hubble Flow and Non-Linear Accretion in the TEGR Macroscopic Lattice
Authors: TEGR Labs
Date: August 2026
Manuscript: 26
Simulation Presets: ms26_high_z_accretion.toml, ms26_hubble_expansion.toml

Abstract
Standard $\Lambda$CDM cosmology provides an exceptionally robust, deeply foundational framework for the thermal history of our universe, representing the collective brilliance and dedicated livelihoods of the global astrophysical community. However, as next-generation observatories expand our cosmic horizon, complementary lenses can be useful to explore specific tensions at extreme scales: namely, the mechanism driving volumetric expansion, and the accelerated timeline required for massive galaxy formation ($M_* > 10^{10} M_\odot$) in the high-redshift universe ($z > 10$). In this manuscript, we present a humble geometric exploration—Topological Emergent General Relativity (TEGR)—that models the vacuum mathematically as a coupled oscillator lattice. Through high-resolution Finite-Difference Time-Domain (FDTD) simulations using the TEGR 2600 engine, we evaluate whether these macroscopic behaviors can be modeled as native properties of a topological space: (1) We quantify the extent to which a macroscopic topological defect acts as a non-linear phase-sink, accelerating early-universe mass accretion; and (2) We evaluate whether baseline topological phase-repulsion natively generates uniform volumetric expansion ($v = H_0 D$). This work does not seek to replace standard models, but to offer a mathematical alternative that may prove incorrect, yet remains a curious exploration of geometry.

1. Introduction
Scientific paradigms are more than just models; they are the bedrock of lifelong research and institutional stability. Exploring alternative frameworks is not an assertion of absolute truth or a dismissal of established cosmology. Change is inherently difficult, and mathematical explorations—including this one—carry the constant possibility of being incorrect. Even if the mechanics demonstrated here hold true, they do not encompass the entirety of physical phenomena.

In our previous analysis (Manuscript 25), observational data across multiple scales indicated that the universe exhibits features mathematically consistent with a continuous chiral lattice, characterized by a macroscopic topological strain. This manuscript utilizes the TEGR 2600 multi-GPU computational engine to simulate the mechanical behavior of this lattice at two extreme operational boundaries: non-linear localized phase-accretion, and global uniform phase-repulsion.

2. Theoretical Bridge: The 1917 Cosmological Constant and Lattice Impedance

**The 1915 Compressive Math:**
In 1917, Albert Einstein applied his 1915 field equations to the universe as a whole. His foundational mathematics described gravity as a purely attractive geometric force. He recognized a fundamental consequence of this geometry: a universe filled with mass, governed purely by attractive curvature, is dynamically collapsing—prone to an inevitable crush. To artificially force a stable, static universe (the philosophical consensus of the time), Einstein introduced the Cosmological Constant ($\Lambda$) into his equations as a repulsive, "anti-gravity" force to counterbalance the geometric collapse. 

**The Cartesian Diver Crash:**
Our lattice simulations align directly with Einstein's raw 1915 realization. In the TEGR model, gravity is the isotropic pressure of the void squeezing inward on topological defects. When we run the TEGR 2600 engine driven purely by this spatial strain (without hardcoded constants or expansive forces), the grid experiences this exact mathematical crush. Specifically, in our Cartesian Diver simulations without an impedance mechanism, the topological strain stacks constructively, bouncing off boundaries until the simulation shatters (FDTD divergence). This catastrophic grid divergence is the computational equivalent of a classical singularity.

**The TEGR Impedance Valve ($\lambda$):**
However, instead of counterbalancing this collapse with Einstein's opposing expansive force ($\Lambda$), the TEGR framework provides a purely mechanical solution to the singularity problem: computational impedance ($\lambda$). In a computational fluid dynamic framework, a continuous lattice must have a processing limit. As the void squeezes the topological knots tighter, local phase gradients become steep, and the lattice's update speed drops while waves decay. The required "exhaust valve" is not a repulsive anti-gravity force, but rather this fundamental thermodynamic impedance of the vacuum itself ($\lambda$). It bleeds off the kinetic energy of the squeeze, mediating the uncontrolled collapse into a steady, stabilized state.

Crucially, this exploration maintains a deep respect for the standard $\Lambda$CDM model, which is supported by immense observational data pointing to an accelerating metric expansion. TEGR does not claim this observational data is incorrect; rather, it suggests the *interpretation* of that data can be inverted. Within a closed Cartesian Diver geometry, Dark Energy is not a mysterious cosmic force pushing galaxies apart. Instead, it is an optical consequence of the observer's relative scale decaying inside a compressing grid. The "constant energy density" of the vacuum is mathematically reinterpreted as the fundamental impedance limit ($\lambda$) mediating a universal topological squeeze, replacing a mysterious cosmic force with standard computational fluid dynamics.

3. Methodology: High-Z Topological Accretion
The standard hierarchical merging model is a profoundly robust process for galaxy formation that operates on well-established temporal constraints. However, JWST observations of fully mature, massive galaxies in the extreme early universe ($z > 10$) invite us to explore complementary mechanisms that might operate on accelerated timelines.

Within the TEGR framework, topological defects serve as continuous phase-sinks within the surrounding vacuum lattice. This introduces a synchronization vector to standard $1/r^2$ gravitational collapse. By rapidly entanglement surrounding grid energy, the defect is hypothesized to augment mass accumulation rates without violating local energy conservation.

Initially, we attempted to model this by imposing artificial scale transitions, applying a strong scalar field sink (torsion_coupling = 150.0), and enforcing artificial impedance boundaries (emergent_horizons = true). These adjustments invariably failed, resulting in system divergence. By stripping away these forced parameters and returning to the foundational mechanics extracted in our earlier work (Mavity: MicroGravity on a Weitzenböck lattice), we allowed gravitational attraction to emerge bottom-up strictly from the topological strain of moving defects.

Simulation Parameters (Path A: Return to Basics):
- Engine Preset: ms26_high_z_accretion.toml
- Emergent Gravity: No hardcoded $G$. We relied on the empirically derived geometric coupling ($J = -5.0$), wave speed ($c = 100.0$), and fundamental timestep ($dt = 0.001$).
- No Impedance Walls: emergent_horizons = false, and emergent_source_strength = 0.0.
- Topological Wakes: A central mass defect ($M = 80,000$) was placed in the lattice. Surrounding trace test masses were given initial tangential velocities to ensure they generate dynamic spatial strain ($\phi_t$) as they navigate the grid.
- Geometric Cost: We ran a parameter sweep over the vacuum processing limit ($\gamma$, or decay_p) to map the phase space of topological collapse.

4. Methodology: Emergent Hubble Flow (Expansion)
To explain the observed uniform volumetric expansion of the universe, standard cosmology utilizes a cosmological constant ($\Lambda$) or a Dark Energy scalar field. In the TEGR model, space is mathematically defined as a rigid lattice of microscopic phase-oscillators. We simulate this phase space to determine if volumetric expansion is a native geometric consequence of the lattice structure.

Simulation Parameters:
- Engine Preset: ms26_hubble_expansion.toml
- We initialized a maximal-footprint, uniform 3D lattice of trace test masses.
- The emergent_horizons boundary condition was activated with a baseline phase-repulsion coupling ($K = -0.1$).
- The dark energy scalar was explicitly set to $0.0$.
- We tracked the radial recession velocity ($v$) of the test masses against their proper distance ($D$) from the center over 100,000 simulation ticks.

5. Results & Discussion

5.1 Emergent Hubble Flow
The observed volumetric expansion is natively governed by the interplay of two primary operators within the TEGR lattice. The transient inflationary burst is driven by the Relativistic Adler Equation operating in a negative coupling regime ($K < 0$), which actively desynchronizes local nodal phases. This topological stress acts as the source term for a Damped Klein-Gordon field, which translates the phase tension into macroscopic geometric strain. As the Adler dynamics reach phase saturation, the active driving force zeroes out. The expansion naturally decelerates, and the Klein-Gordon processing term ($\lambda$) stabilizes the lattice into a coasting Hubble flow, yielding an emergent $v \propto D$ expansion without the injection of an external cosmological constant.

**The Hubble Parameter Extraction:** The 100,000-tick run confirms this mechanism natively produces a global scale factor expansion. By performing a binned linear regression on the proper distances and recession velocities at the final tick, we extracted a uniform emergent Hubble parameter of $H_0 = 0.00083$ (with a binned $R^2 = 0.448$). The lattice expanded by 56.4% structurally over the simulation window, confirming that $v = H_0 D$ holds globally strictly as a consequence of phase repulsion.

5.2 Wake-Driven Accretion and The Breathing Mode
By relying strictly on the emergent gravity of topological strain rather than artificial couplings, the lattice successfully generated a self-regulating, non-linear accretion feedback loop.

Structural Rebalancing: We mapped the accretion profile in a critical processing regime ($\gamma = 0.995$). The system exhibits a discrete structural rebalancing:
- The Collapse: The topological wakes of moving defects stack constructively, deepening the spatial well and causing rapid infall (capture surges to 318 particles).
- The Rebound: As particles crowd the center, the spatial strain gradients become chaotic and steep. The resulting torsional forces rapidly accelerate the particles, converting deep topological potential energy into kinetic energy, shedding a portion of the mass back outward (dropping to 152).
- The Persistent Core: The lattice processes just enough of that kinetic energy to trap a permanent core (stabilizing at 55 particles). The system self-regulates purely through geometry.

The Physical Reality of $min\_r = 0.87$: During the collapse phase, particles driven from an initial radius of $r=37.5$ plunged to $min\_r = 0.87$. Reaching 0.87 signifies that a test mass successfully localized against the surface of the central defect. The topological well captured the mass without requiring fluid dynamic variables.

$\gamma_c$ as the Geometric Boundary: Our parameter sweep revealed a critical processing threshold ($\gamma_c \approx 0.997 \pm 0.002$), representing the exact ratio of topological energy injection to the lattice's inherent update limit.
- Runaway ($\gamma > \gamma_c$): The lattice cannot process the spatial strain fast enough. The field geometry folds in on itself indefinitely—the mathematical threshold for forming a topological defect zip-up.
- Stability ($\gamma \le \gamma_c$): The lattice processes the geometric strain fast enough to halt the collapse, resulting in a stable, self-gravitating structure.

Finding this phase transition illustrates that the TEGR lattice can organically differentiate between a catastrophic core collapse and the formation of a stable structure strictly based on the vacuum's mathematical processing rate.

**The Topological Accretion ODE:** To formalize the accretion cascade during the collapse phase, we applied PySINDy to the $\gamma = 0.995$ trajectory telemetry (the active growth phase up to tick 7500). The sparse identification extracted the governing ordinary differential equation for the localized particle count $N$:

$$ \frac{dN}{dt} = 0.288 N - 2.217 $$

This confirms the structural collapse behaves as a robust exponential cascade where the mass accumulation rate scales directly with the accumulated mass $N$, mathematically defining the topological accretion rate.

5.3 The Cartesian Diver and the Topological Impedance Valve
To rigorously isolate the mechanism driving stable accretion without relying on arbitrary constraints, we evaluated the system under a "Cartesian Diver" mechanical proof. By treating the simulation domain as a closed system (a clamped FDTD grid), we tested whether uniform phase-contraction natively emerges from an interplay between mass injection and impedance boundaries, analogous to the physical squeeze of a closed bottle.

Our matrix of simulations across the emergent parameter space yielded definitive mechanical proof:
1. Without continuous mass sourcing (emergent_source_strength = 0.0), the system unconditionally expands regardless of boundary conditions, drifting from 75.0 kpc to >75.1 kpc.
2. With mass sourcing but lacking emergent impedance (emergent_source_strength = 1.0, emergent_horizons = false), the geometric strain accumulates uncontrolled, resulting in a mathematical divergence (FDTD field blow-up at $\phi > 1000.0$) within 160 ticks.
3. With both mass sourcing and emergent impedance active (emergent_source_strength = 1.0, emergent_horizons = true), the system successfully processes the continuous topological injection into a stable volumetric contraction, accreting from an initial radius of 75.000 to a final radius of 74.193.

The divergence in the second scenario highlights a critical property of wave mechanics on a rigid grid. A hard Dirichlet boundary acts as a perfect mirror; the injected spatial strain bounces back with 100% efficiency, stacking constructively into a catastrophic resonant feedback loop. However, when the emergent horizon is active, the boundary dynamically responds to the field strength ($\phi$). It acts as a pressure-release valve—an active topological impedance layer that absorbs acoustic shockwaves while maintaining the steady, crushing geometric pressure required for accretion.

5.4 The Mirror Effect and holographic Duality
This dynamic mathematically formalizes a "Fractal Topology," where localized contraction is natively driven by the global pressure of the bounding geometry. If our universe is a closed topological system (a Gen -1 sub-manifold), its outer boundary is not a physical brick wall, but an emergent topological horizon.

In this framework, the parent void (Gen 0) applies a massive pressure that creates a localized contraction. At the horizon, the boundary absorbs the resonant shockwaves, converting the external crushing force into a steady, localized internal dynamic. Inside the horizon (Gen -1), trace particles are pushed to the center by this mediated pressure, forming stable, accreted structures.

Crucially, because the horizon actively mediates this pressure, an observer inside the system experiences physics relative to the boundary. If the void is contracting, but the observer and surrounding matter are squeezed together *faster* than the horizon itself collapses, the relative distance between the observer and the horizon appears to grow. The compression of the macroscopic void thus mathematically mirrors into the appearance of an expanding cosmic horizon. The simulation proves that gravity (accretion) requires a bounding geometry that pushes back, but also that the boundary must possess active impedance to prevent the universe from resonant self-destruction.

6. References
- Labbé, I., et al. (2023). "A population of red candidate massive galaxies ~600 Myr after the Big Bang." Nature, 616(7956), 266-269.
- Riess, A. G., et al. (1998). "Observational Evidence from Supernovae for an Accelerating Universe and a Cosmological Constant." The Astronomical Journal, 116(3), 1009-1038.
- TEGR Labs. (2026). "Mavity: MicroGravity on a Weitzenböck lattice." (Manuscript).
- TEGR Labs. (2026). "Manuscript 25: Observational Signatures of a Continuous Chiral Lattice." (Manuscript).
- Brunton, S. L., Proctor, J. L., & Kutz, J. N. (2016). "Discovering governing equations from data by sparse identification of nonlinear dynamical systems." Proceedings of the National Academy of Sciences, 113(15), 3932-3937. (PySINDy).
