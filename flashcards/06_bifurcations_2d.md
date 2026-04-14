+++
order = 6
subject = "Math"
tags = ["math", "dynamical-systems", "hopf-bifurcation", "homoclinic", "heteroclinic", "global-bifurcations"]
+++

# Dynamical Systems — Bifurcations in Two Dimensions

## 6.1 Local vs Global Bifurcations

Q: Distinguish [LOCAL] vs [GLOBAL] bifurcations.
A: LOCAL: involve changes near a single fixed point or cycle — detected by local linearization or normal forms. Examples: saddle-node, transcritical, pitchfork, Hopf. GLOBAL: involve large-scale structural changes (heteroclinic/homoclinic orbits, saddle-node of cycles, infinite-period bifurcations) — require information about the entire phase portrait. Global bifurcations are generally HARDER to predict analytically but are common in real systems.

## 6.2 Hopf Bifurcation Restated

Q: Restate the [supercritical Hopf bifurcation] in normal form.
A: $\dot{r} = \mu r - r^3, \dot{\theta} = \omega + b r^2$ (in polar coordinates near the bifurcating fixed point). For $\mu < 0$: origin is stable spiral, no cycle. For $\mu > 0$: origin unstable, STABLE LIMIT CYCLE at $r = \sqrt{\mu}$, amplitude $\propto \sqrt{\mu}$. Frequency shifts slightly with amplitude (term $b r^2$). The "soft" birth of oscillations from a stable equilibrium.

Q: Describe the [subcritical Hopf bifurcation].
A: Normal form: $\dot{r} = \mu r + r^3, \dot{\theta} = \omega$. For $\mu < 0$: stable origin surrounded by an UNSTABLE limit cycle of radius $\sqrt{-\mu}$. As $\mu \to 0^-$: cycle shrinks to origin; at $\mu = 0$: merges; for $\mu > 0$: both gone, origin unstable. Trajectories ESCAPE to infinity (or to a far-away attractor). "Hard" loss of stability — can be catastrophic. Often stabilized globally by higher-order terms, creating bistability + hysteresis.

## 6.3 Hopf Bifurcation Theorem

Q: State conditions for a [Hopf bifurcation] at a fixed point.
A: Consider $\dot{\mathbf{x}} = f(\mathbf{x}, \mu)$ with fixed point $x^*(\mu)$. If: (1) Jacobian $J(\mu)$ has a pair of COMPLEX EIGENVALUES $\lambda(\mu) = \alpha(\mu) \pm i \beta(\mu)$. (2) At $\mu = \mu_c$: $\alpha(\mu_c) = 0$ (cross imaginary axis), $\beta(\mu_c) \neq 0$. (3) TRANSVERSALITY: $\alpha'(\mu_c) \neq 0$ (eigenvalues cross nonzero speed). (4) No other eigenvalues on imaginary axis. Then: a limit cycle is born at $\mu = \mu_c$. The cubic term coefficient determines super- vs subcritical.

## 6.4 Saddle-Node of Cycles

Q: Describe the [saddle-node (or fold) bifurcation of LIMIT CYCLES].
A: Two limit cycles (one stable, one unstable) collide and annihilate as a parameter varies — analogous to saddle-node of fixed points but for orbits. The unique coalesced cycle at bifurcation is SEMI-STABLE. After the bifurcation: no nearby cycles — trajectories go to a different attractor (often a faraway fixed point). Can trigger HYSTERESIS in systems with multiple attractors. Occurs in lasers, chemical oscillators, cardiac dynamics.

## 6.5 Homoclinic Bifurcation

Q: What is a [homoclinic bifurcation]?
A: A saddle's stable and unstable manifolds MERGE to form a [homoclinic orbit] (a trajectory leaving the saddle along the unstable manifold and returning via the stable manifold). At this bifurcation: a limit cycle COLLIDES with a saddle — period of the cycle diverges to infinity just before the collision (period $\sim \ln(1 / |\mu|)$). After the bifurcation: cycle DESTROYED. Appears in "blue-sky catastrophe," neuronal excitability, and chaos routes.

Q: Why is the period LOGARITHMIC near a homoclinic bifurcation?
A: Because trajectories pass arbitrarily close to the saddle — where the vector field is arbitrarily small — spending longer and longer near it. The "time stuck near saddle" scales as $\ln(1 / d)$ where $d$ is the distance of closest approach (driven by the parameter $\mu$). Signature: period $T(\mu) \sim c_1 - c_2 \ln |\mu - \mu_c|$. Detectable experimentally — a hallmark of homoclinic bifurcation.

## 6.6 Heteroclinic Bifurcation

Q: What is a [heteroclinic bifurcation]?
A: Two DIFFERENT saddles' manifolds merge: a trajectory goes from one saddle's unstable manifold to another saddle's stable manifold. This heteroclinic connection is STRUCTURALLY UNSTABLE — a tiny perturbation destroys it. At the bifurcation: chains of heteroclinic orbits can form, creating complex global dynamics. In systems with SYMMETRY, heteroclinic cycles can be STABILIZED and attract trajectories.

## 6.7 Saddle-Node on Invariant Circle (SNIC)

Q: Describe the [SNIC bifurcation].
A: A saddle-node bifurcation OCCURRING ON a limit cycle. The cycle's period DIVERGES to infinity as the two fixed points appear on it. For parameters past critical: cycle disappears, leaving a saddle and a stable fixed point on the former cycle. Arises in TYPE I NEURONS: models the transition from quiescence to PERIODIC FIRING, with FIRING RATE approaching 0 continuously at threshold (square-root scaling in parameter). Contrast: Type II (Hopf) neurons fire at nonzero frequency at onset.

## 6.8 Cusp and Other Codimension-2 Bifurcations

Q: What is a [cusp bifurcation]?
A: Codimension-2: occurs when TWO parameters must be tuned simultaneously. Generic form: $\dot{x} = h + rx - x^3$. In $(h, r)$ parameter plane: a CUSP-shaped region where three fixed points coexist (bistability). At the cusp point: three fixed points merge. Boundary: saddle-node curves meeting tangentially. Basis of CATASTROPHE THEORY — the "cusp catastrophe" with classical applications (stock market crashes, aggression in dogs, buckling).

## 6.9 Bogdanov-Takens Bifurcation

Q: What is the [Bogdanov-Takens (BT) bifurcation]?
A: Codimension-2 bifurcation where the Jacobian has a DOUBLE ZERO eigenvalue (non-semisimple). Normal form: $\dot{x} = y, \dot{y} = \mu_1 + \mu_2 x + x^2 + \sigma xy$. Complex unfolding: near the BT point, the system exhibits saddle-node, Hopf, AND homoclinic bifurcations — they emanate from BT as CURVES in the two-parameter plane. BT organizes the SIMULTANEOUS appearance of fixed points and cycles.

## 6.10 Bifurcations and Catastrophe Theory

Q: What is [catastrophe theory]?
A: Classification of the typical ways a system's equilibria can change with multiple parameters (Rene Thom, 1960s-70s). Seven elementary catastrophes in up to 4 parameters: fold, cusp, swallowtail, butterfly, hyperbolic umbilic, elliptic umbilic, parabolic umbilic. Each has a canonical polynomial normal form. Applications: phase transitions, psychology (Zeeman), engineering failure. Oversold in its heyday but mathematically rigorous.

## 6.11 Bifurcations in Applications

Q: Give BIOLOGICAL examples of Hopf and homoclinic bifurcations.
A: (1) [Heartbeat]: supercritical Hopf bifurcation from silent state to sinus rhythm as pacemaker parameters change. (2) [Insulin secretion]: Hopf at threshold of glucose-induced oscillations. (3) [Type II neurons]: Hopf bifurcation from rest to firing; minimum firing frequency. (4) [Homoclinic bifurcations]: Morris-Lecar neuron model — transition between spiking and bursting regimes. (5) [Cardiac arrhythmias]: heteroclinic bifurcations disrupt normal rhythms.

## 6.12 A Worked Bifurcation Diagram

P: Analyze the system $\dot{x} = \mu x - y - x(x^2 + y^2), \dot{y} = x + \mu y - y(x^2 + y^2)$ as $\mu$ varies. Identify and characterize the bifurcation at $\mu = 0$.
S:
**IDENTIFY**: 2D system parameterized by $\mu$. Convert to polar coordinates (similar to Ch. 5 example).

**PLAN**: Compute $\dot{r}, \dot{\theta}$; analyze dependence on $\mu$; classify bifurcation.

**EXECUTE**:
In polar: $\dot{r} = \mu r - r^3, \dot{\theta} = 1$.

Fixed points of $\dot{r}$: $r = 0$ or $r^2 = \mu$.
- For $\mu < 0$: only $r = 0$. Stability: $\dot{r}|_{r = 0 + \epsilon} = \mu \epsilon < 0$ — origin STABLE (spiral). No cycle.
- For $\mu = 0$: only $r = 0$. Stability: $\dot{r} = -r^3$, weakly stable (cubic decay).
- For $\mu > 0$: $r = 0$ unstable; $r = \sqrt{\mu}$ is a limit cycle. Stability of cycle: $f'(r) = \mu - 3r^2$ at $r = \sqrt{\mu}$ gives $\mu - 3\mu = -2\mu < 0$ — STABLE.

At $\mu = 0$: fixed point changes stability, new limit cycle born with amplitude $\sqrt{\mu}$ — SUPERCRITICAL HOPF BIFURCATION.

Bifurcation diagram (amplitude vs $\mu$): horizontal line $r = 0$ solid (stable) for $\mu < 0$, dashed (unstable) for $\mu > 0$; parabolic branch $r = \sqrt{\mu}$ solid (stable) for $\mu > 0$.

**EVALUATE**: Classical supercritical Hopf. Amplitude of oscillation grows as $\sqrt{\mu - \mu_c}$ — the signature square-root scaling. Frequency at bifurcation: $\omega = 1$ (constant here). Soft onset — small cycle, smooth emergence. Physical interpretations: laser at threshold, onset of convection rolls past Rayleigh number, Hopf bifurcation in Hodgkin-Huxley neuron. This SAME normal form (up to rescaling) approximates EVERY supercritical Hopf bifurcation locally — a powerful universality.
