+++
order = 1
subject = "Math"
tags = ["math", "dynamical-systems", "flows", "phase-space", "fixed-points", "vector-fields"]
+++

# Dynamical Systems — Flows, Phase Space, and Fixed Points

## 1.1 What Dynamical Systems Studies

Q: What is the central question of DYNAMICAL SYSTEMS?
A: How does a system EVOLVE OVER TIME? Given a rule describing instantaneous change (typically an ODE or a map), characterize the LONG-TERM BEHAVIOR: do solutions converge to equilibria, oscillate periodically, or exhibit chaos? The answers connect pure mathematics (topology, ergodic theory) to physics, biology, economics, climate. Universal: any quantity that changes with time — populations, planetary orbits, electric circuits, neurons — is a candidate.

Q: Why study dynamical systems QUALITATIVELY rather than just solving ODEs?
A: Because MOST NONLINEAR ODEs CANNOT BE SOLVED in closed form. But we can still say MUCH about their solutions: existence of equilibria, stability, periodicity, chaos — without ever writing down $x(t)$. Poincaré's 1880s insight: topology and geometry of the PHASE PORTRAIT reveal all, often more efficiently than explicit solutions. This qualitative approach is especially essential when the governing equations are only approximately known.

## 1.2 Continuous-Time Systems

C: A [continuous-time dynamical system] is defined by an ODE $\dot{x} = f(x)$ where $x \in \mathbb{R}^n$ is the state and $f : \mathbb{R}^n \to \mathbb{R}^n$ is a VECTOR FIELD.

C: The [flow] $\phi_t$ is the solution operator: $\phi_t(x_0)$ is the state at time $t$ starting from $x_0$. Satisfies $\phi_0 = \text{id}$ and $\phi_{s+t} = \phi_s \circ \phi_t$ (group property).

Q: What does it mean that $f$ is AUTONOMOUS?
A: The vector field $f(x)$ depends ONLY on the current state $x$ — not explicitly on time $t$. So $\dot{x} = f(x)$, not $\dot{x} = f(x, t)$. Autonomous systems are TIME-TRANSLATION INVARIANT: if $x(t)$ is a solution, so is $x(t + c)$. This structure underlies the theory: trajectories depend only on starting POSITION, not starting TIME. Non-autonomous systems can be converted by adding $t$ as an extra state variable.

## 1.3 Phase Space

C: The [phase space] of a dynamical system is the space of all possible states $x$. For $\dot{x} = f(x)$ with $x \in \mathbb{R}^n$, phase space is $\mathbb{R}^n$ (or a manifold).

Q: Why is PHASE SPACE the fundamental object of dynamical systems?
A: Because it contains ALL POSSIBLE TRAJECTORIES simultaneously as curves tangent to the vector field $f$. Evolution = moving along these curves. Phase space geometry (fixed points, cycles, separatrices) exposes behavior invisible in any single time-series plot. For a pendulum, phase space is $(\theta, \dot{\theta})$ — curves encode both libration (back-and-forth) and rotation (over-the-top), distinguished by their topology.

## 1.4 Trajectories and the Phase Portrait

C: A [trajectory] (or orbit) is the image of the flow $\phi_t(x_0)$ as $t$ varies — a curve in phase space through $x_0$.

C: A [phase portrait] is a picture of phase space showing representative trajectories, arrows indicating direction of motion, and special features (fixed points, cycles).

Q: What's a KEY TOPOLOGICAL property of trajectories?
A: Trajectories NEVER CROSS (in autonomous systems). Uniqueness of ODE solutions (given Lipschitz $f$) means two trajectories starting from the same point are identical; two distinct trajectories cannot meet at a shared point without violating uniqueness. This makes 2D phase portraits topologically rigid — trajectories partition the plane into non-crossing curves. In 3D, this constraint is weaker, enabling chaos.

## 1.5 Fixed Points

C: A [fixed point] (equilibrium, steady state) of $\dot{x} = f(x)$ is a point $x^*$ with $f(x^*) = 0$ — the vector field vanishes, so the state doesn't move.

Q: Why are fixed points the FIRST THING to analyze in a dynamical system?
A: Because they are the SIMPLEST trajectories (single points), and LOCAL behavior near them is often determined by LINEARIZATION — a tractable problem. Global behavior is built from local pieces: trajectories approach, repel from, or spiral around fixed points. Listing and classifying fixed points is the entry point to any dynamical analysis. A system with no fixed points still has them "at infinity" or bounded by cycles.

## 1.6 Stability

C: A fixed point $x^*$ is [Lyapunov stable] if nearby trajectories STAY NEARBY: for every $\epsilon > 0$, there exists $\delta > 0$ such that $|x(0) - x^*| < \delta$ implies $|x(t) - x^*| < \epsilon$ for all $t \geq 0$.

C: A fixed point is [asymptotically stable] if it is Lyapunov stable AND nearby trajectories CONVERGE to it: $x(t) \to x^*$ as $t \to \infty$.

Q: What's the DIFFERENCE between Lyapunov stability and asymptotic stability?
A: Lyapunov = trajectories stay close but don't necessarily approach. Asymptotic = trajectories actively go to the fixed point. A pendulum at its DOWNWARD equilibrium with FRICTION is asymptotically stable (returns to rest). WITHOUT friction, it's only Lyapunov stable (oscillates forever at small amplitude). The DISTINCTION matters for control: asymptotic stability is robust; Lyapunov-only is fragile to perturbations.

## 1.7 Existence and Uniqueness

Q: Under what conditions does $\dot{x} = f(x), x(0) = x_0$ have a UNIQUE SOLUTION?
A: If $f$ is LIPSCHITZ continuous in a neighborhood of $x_0$ (in particular, if $f$ is continuously differentiable, $C^1$): the initial value problem has a UNIQUE solution on some time interval. Without Lipschitz, uniqueness can fail — e.g., $\dot{x} = \sqrt{|x|}, x(0) = 0$ has infinitely many solutions. Unless stated otherwise, dynamical systems theory assumes $C^1$ or smoother vector fields.

## 1.8 The Pendulum as Prototype

P: Sketch the phase portrait of the undamped pendulum $\ddot{\theta} + \sin \theta = 0$.
S:
**IDENTIFY**: Convert to 2D system: $\dot{\theta} = \omega, \dot{\omega} = -\sin \theta$. Phase space: $(\theta, \omega)$.

**PLAN**: Find fixed points; compute energy (conserved); sketch level curves.

**EXECUTE**:
Fixed points: $\omega = 0, \sin \theta = 0 \Rightarrow \theta = n\pi$.
- $\theta = 0$ (downward): CENTER (stable, oscillations).
- $\theta = \pi$ (upward): SADDLE (unstable).
Energy $E = \tfrac{1}{2} \omega^2 - \cos \theta$ is conserved (autonomous, $\dot{E} = 0$).
Level curves: (a) Small $E$ near $\theta = 0$: closed ellipses (libration). (b) Large $E$: open curves $\omega(\theta) = \pm\sqrt{2(E + \cos \theta)}$ — full rotation. (c) SEPARATRIX at $E = 1$: curves passing through $(\pm\pi, 0)$ saddle points.

**EVALUATE**: Phase portrait has a CENTER at origin surrounded by closed orbits (oscillation), bounded by the separatrix (the "heteroclinic" curves connecting the unstable equilibrium to itself via going over the top). Outside: rotation. This single picture captures ALL qualitative behaviors of the pendulum — no solving ODE needed. The pendulum is the archetypal CONSERVATIVE system; adding friction makes the origin asymptotically stable and destroys the cycles.

## 1.9 Discrete-Time Systems

C: A [discrete-time dynamical system] is defined by an ITERATED MAP $x_{n+1} = F(x_n)$, $n = 0, 1, 2, \ldots$, generating the sequence $x_0, F(x_0), F(F(x_0)), \ldots$.

Q: Why study DISCRETE maps alongside continuous flows?
A: Because (1) many real systems are naturally discrete (population counts per year, computer iterations, financial time series). (2) [Poincaré sections] reduce continuous flows to discrete maps — a powerful tool for analyzing limit cycles. (3) Maps can exhibit chaos in 1D (logistic map), whereas flows need at least 3D — making maps the simplest playground for chaos theory. (4) Numerical integrators (Euler, RK4) turn continuous ODEs into discrete maps.

## 1.10 Topology of Solutions

Q: What basic TOPOLOGICAL structures appear in phase portraits?
A: (1) Fixed points. (2) Periodic orbits (closed curves). (3) Heteroclinic orbits (connecting different fixed points). (4) Homoclinic orbits (starting and ending at the same fixed point). (5) Quasi-periodic orbits (dense on tori). (6) Chaotic attractors (fractal structures). Classifying a phase portrait means identifying these objects and how they are assembled. Invariant manifolds (stable and unstable) organize the dynamics globally.

## 1.11 Invariant Sets

C: A set $S$ is [invariant] under the flow if $\phi_t(S) \subseteq S$ for all $t$ (or $t \geq 0$ for positive invariance) — trajectories starting in $S$ stay in $S$.

Q: Why are INVARIANT SETS crucial to dynamical systems analysis?
A: Because the DYNAMICS can be decomposed into behavior ON invariant sets (simpler sub-problems) and behavior BETWEEN them (transitions). Fixed points are minimal invariant sets; cycles are 1D invariant curves; attractors are invariant regions. The LONG-TERM BEHAVIOR of any trajectory is captured by the invariant set it eventually approaches. Identifying invariant sets is the first step in understanding any nonlinear system.

## 1.12 A Worked Phase Portrait

P: Sketch the phase portrait of $\dot{x} = x(1 - x)$ (logistic ODE, 1D).
S:
**IDENTIFY**: 1D system. Fixed points where $\dot{x} = 0$: $x = 0$ and $x = 1$.

**PLAN**: Determine stability by sign of $f(x) = x(1 - x)$.

**EXECUTE**:
For $x < 0$: $f(x) = (\text{neg})(\text{pos}) < 0$, so $\dot{x} < 0$ — flow moves leftward (away from 0).
For $0 < x < 1$: $f(x) > 0$ — flow moves rightward (toward 1).
For $x > 1$: $f(x) = (\text{pos})(\text{neg}) < 0$ — flow moves leftward (toward 1).

Fixed points:
- $x = 0$: flow diverges on one side, converges from the other side — SEMI-stable in 1D, but "unstable" since perturbations to $x > 0$ grow. Formally: $f'(0) = 1 > 0$ — UNSTABLE.
- $x = 1$: flow converges from both sides. $f'(1) = -1 < 0$ — ASYMPTOTICALLY STABLE.

**EVALUATE**: 1D phase portrait on the real line: arrows point AWAY from 0 (to both left and right), TOWARD 1. Every initial condition $x(0) > 0$ converges to $x^* = 1$. Models BOUNDED GROWTH: $x$ = population, 1 = carrying capacity. Solutions: $x(t) = \frac{1}{1 + ((1/x_0) - 1) e^{-t}}$ (closed form exists here; unusual). Qualitative approach yielded the full picture without solving — the general DS philosophy.
