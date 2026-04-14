+++
order = 9
subject = "Math"
tags = ["math", "dynamical-systems", "attractors", "lorenz", "rossler", "henon", "basin-of-attraction"]
+++

# Dynamical Systems — Strange Attractors

## 9.1 What an Attractor Is

C: An [attractor] is a CLOSED, INVARIANT set $A$ such that (1) a neighborhood of $A$ (the [basin of attraction]) exists whose trajectories all approach $A$ as $t \to \infty$, AND (2) $A$ is MINIMAL — no proper subset is also an attractor.

Q: What are the FOUR types of attractors?
A: (1) [Fixed point]: 0-dimensional. Asymptotic stability. (2) [Limit cycle]: 1-dimensional closed curve. Periodic behavior. (3) [Torus (quasi-periodic)]: 2+ dimensional. Dynamics with multiple incommensurate frequencies. (4) [Strange attractor]: fractal, chaotic. The FIRST THREE are "simple" / classical attractors; strange attractors are the hallmark of chaos. These exhaust all generic attracting sets.

## 9.2 Basins of Attraction

C: The [basin of attraction] of attractor $A$ is the set of all initial conditions whose trajectories approach $A$ as $t \to \infty$.

Q: Why can BASIN BOUNDARIES be FRACTAL?
A: In systems with multiple attractors, the boundary between their basins can be arbitrarily intricate. If the boundary is a STRANGE set (invariant but non-attracting), orbits near it experience CHAOTIC TRANSIENTS before settling. Uncertainty about initial conditions translates to huge uncertainty about WHICH attractor you'll reach — "sensitivity to initial conditions" in bulk outcome. Appears in: magnetic pendulum, driven oscillators, planetary escape problems.

## 9.3 The Lorenz System

Q: Write the [Lorenz equations].
A: $\dot{x} = \sigma(y - x)$, $\dot{y} = x(\rho - z) - y$, $\dot{z} = xy - \beta z$. Introduced by Edward Lorenz (1963) as a simplified atmospheric convection model. Classical parameters: $\sigma = 10, \beta = 8/3, \rho = 28$. For these parameters: the system exhibits the famous BUTTERFLY-SHAPED strange attractor — aperiodic, sensitive, bounded.

Q: Describe the STRUCTURE of the Lorenz attractor.
A: Two "wings" (tied to the two unstable fixed points $C^\pm$), connected by rapid jumps. Trajectory spirals outward on one wing, then gets flung to the other, spirals there, jumps back — aperiodically. Fractal structure: cross-section is (almost) a Cantor-like set. Hausdorff dimension $\approx 2.06$. Lyapunov exponents $(0.906, 0, -14.57)$ — positive, zero, large negative, summing to $-13.66$ (dissipation).

## 9.4 Lorenz Dynamics

Q: Identify the fixed points of the Lorenz system and analyze stability for varying $\rho$ (with $\sigma = 10, \beta = 8/3$).
A: Fixed points: origin $O = (0,0,0)$ always; and $C^\pm = (\pm\sqrt{\beta(\rho-1)}, \pm\sqrt{\beta(\rho-1)}, \rho-1)$ for $\rho \geq 1$. Stability:
- $O$: stable for $\rho < 1$, saddle for $\rho > 1$ (pitchfork at $\rho = 1$).
- $C^\pm$: stable for $1 < \rho < \rho_H \approx 24.74$. At $\rho = \rho_H$: SUBCRITICAL HOPF → $C^\pm$ lose stability; no nearby limit cycle; strange attractor is the only attractor.
- For $\rho > 24.74$: NO STABLE FIXED POINTS OR CYCLES — all trajectories go to the strange attractor.

## 9.5 Universality of the Lorenz Attractor

Q: Why is the Lorenz attractor HISTORICALLY IMPORTANT?
A: (1) FIRST ACKNOWLEDGED example of a strange attractor in a physical model (1963). (2) Revealed "sensitive dependence on initial conditions" in a simple deterministic system, challenging classical predictability. (3) Lorenz's numerical observation (small input error → vastly different weather) formalized the "butterfly effect." (4) Rigorously proven to be a strange attractor by Tucker (2002) via computer-assisted proof. Cultural icon of chaos theory.

## 9.6 The Rössler System

Q: Write the [Rössler system] and describe its attractor.
A: $\dot{x} = -y - z, \dot{y} = x + ay, \dot{z} = b + z(x - c)$. Constructed by Rössler (1976) as the SIMPLEST possible smooth 3D chaotic system. Classical parameters: $a = 0.2, b = 0.2, c = 5.7$. Produces a "BAND-LIKE" attractor: trajectories spiral outward in the $(x, y)$ plane, then get kicked up in $z$ and reinjected — a Möbius-strip-like structure. Period-doubling cascades as parameters vary.

Q: Compare the LORENZ and RÖSSLER attractors.
A: Lorenz: TWO-WING structure, symmetric under $(x, y) \to (-x, -y)$; trajectory flips between wings. More "physical" origin (Navier-Stokes-derived). Rössler: SINGLE-BAND structure, no symmetry; simpler topology — best for teaching. Both have positive Lyapunov exponent, fractal dimension. Rössler shows period-doubling route to chaos cleanly; Lorenz shows homoclinic explosion of chaos at $\rho \approx 24$.

## 9.7 The Hénon Map

Q: Write the [Hénon map].
A: $x_{n+1} = 1 - a x_n^2 + y_n$, $y_{n+1} = b x_n$. Introduced by Hénon (1976) as a 2D discrete analog of the Lorenz system — simpler for analysis. Classical parameters: $a = 1.4, b = 0.3$. Produces a STRANGE ATTRACTOR with beautiful fractal structure. Dissipation: $|b| < 1$ means the map CONTRACTS areas by factor $b$. Like Lorenz, exhibits stretching and folding but in discrete steps.

## 9.8 Fractal Dimension

Q: What is the [fractal (box-counting) dimension]?
A: For a set $S$: count $N(\epsilon)$ = minimum boxes of side $\epsilon$ needed to cover $S$. Box-counting dimension: $D_0 = \lim_{\epsilon \to 0} \frac{\log N(\epsilon)}{\log(1/\epsilon)}$. Integer for smooth manifolds (lines: 1, surfaces: 2, volumes: 3); NON-INTEGER for fractals. Examples: Cantor set $\log_3 2 \approx 0.63$; Lorenz attractor $\approx 2.06$; coastline of Britain $\approx 1.25$. Quantifies "crinkliness" of self-similar sets.

## 9.9 Other Fractal Dimensions

Q: Name OTHER definitions of fractal dimension.
A: (1) [Hausdorff dimension]: most rigorous; infimum over "dimension" for which $d$-dimensional Hausdorff measure is zero. Equals box-counting for "nice" sets. (2) [Information dimension]: weights boxes by probability — captures non-uniform fractals. (3) [Correlation dimension]: related to pair correlation function; EASIER TO COMPUTE from data (Grassberger-Procaccia algorithm). (4) [KAPLAN-YORKE] (Lyapunov) dimension: derived from Lyapunov exponents. Usually $D_1 \leq D_0$, with equality for uniform fractals.

## 9.10 Chua's Circuit

Q: What is [Chua's circuit]?
A: Electronic circuit (Chua 1983) exhibiting chaos using only three passive components + one nonlinear resistor (Chua diode). Produces a DOUBLE-SCROLL attractor topologically similar to Lorenz's. First EASILY REPRODUCIBLE physical chaos — a lab staple for demonstrating strange attractors, period-doubling, intermittency. Three-dimensional state (two voltages + one current) with piecewise-linear nonlinearity. Rigorously shown chaotic.

## 9.11 Strange Non-Chaotic Attractors

Q: What is a [strange non-chaotic attractor (SNA)]?
A: An attractor that is geometrically FRACTAL (strange) but dynamically NON-CHAOTIC (Lyapunov exponents $\leq 0$). Arises in QUASI-PERIODICALLY FORCED systems with irrational frequency ratios. Neither classical (torus) nor chaotic. Surprising: FRACTAL STRUCTURE WITHOUT SENSITIVITY. Detected in experiments (Heagy-Ditto 1991). Distinct category in the zoo of attractors; complicates the simple "strange ⇔ chaotic" equation.

## 9.12 A Worked Lorenz Analysis

P: For the Lorenz system with $\sigma = 10, \beta = 8/3, \rho = 28$: find the fixed points $C^\pm$ and linearize to confirm instability (subcritical Hopf past $\rho_H$).
S:
**IDENTIFY**: Lorenz at canonical chaotic parameters. Fixed points and Jacobian analysis.

**PLAN**: Solve $\dot{x} = \dot{y} = \dot{z} = 0$; compute Jacobian; check eigenvalues.

**EXECUTE**:
Fixed points: from $\dot{x} = 0$: $y = x$. From $\dot{z} = 0$: $z = xy/\beta = x^2/\beta$. From $\dot{y} = 0$: $x(\rho - z) - y = 0 \Rightarrow x(\rho - x^2/\beta) = x \Rightarrow x^2 = \beta(\rho - 1)$.
So $x = \pm\sqrt{\beta(\rho-1)} = \pm\sqrt{(8/3)(27)} = \pm\sqrt{72} \approx \pm 8.485$.
$C^\pm = (\pm 8.485, \pm 8.485, 27)$.

Jacobian at $C^+$:
$J = \begin{pmatrix} -\sigma & \sigma & 0 \\ \rho - z & -1 & -x \\ y & x & -\beta \end{pmatrix} = \begin{pmatrix} -10 & 10 & 0 \\ 1 & -1 & -8.485 \\ 8.485 & 8.485 & -8/3 \end{pmatrix}$.

Characteristic polynomial is cubic; numerical computation gives eigenvalues approximately: $-13.85$ (real, stable), $0.094 \pm 10.19 i$ (complex, POSITIVE real part).

One stable direction; one UNSTABLE complex pair → $C^+$ is a saddle-focus. Trajectories spiral OUTWARD in the unstable plane, are pulled back along the stable direction.

**EVALUATE**: Confirmed: at $\rho = 28$ (above $\rho_H \approx 24.74$), $C^\pm$ are UNSTABLE — no periodic orbit or fixed point to attract trajectories. Combined with dissipation ($\text{tr}(J) = -(\sigma + 1 + \beta) \approx -13.67 < 0$): trajectories confined to a bounded region, chaotically wandering on the STRANGE ATTRACTOR. Trajectories from either wing's neighborhood spiral outward, jump to the other wing (via stable manifolds of the origin), spiral there, jump back. No periodic structure — the famous butterfly-shaped chaos.
