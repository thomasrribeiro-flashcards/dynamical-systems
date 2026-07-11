+++
order = 5
subject = "mathematics"
tags = ["math", "dynamical-systems", "limit-cycles", "poincare-bendixson", "van-der-pol", "oscillations"]
+++

# Dynamical Systems — Limit Cycles and Poincaré-Bendixson

## 5.1 What a Limit Cycle Is

C: A [limit cycle] is an ISOLATED closed trajectory in phase space — a periodic orbit that neighboring trajectories spiral toward or away from.

Q: Why are LIMIT CYCLES FUNDAMENTAL to applied dynamical systems?
A: Because they model SELF-SUSTAINED OSCILLATIONS in biology (heartbeat, neural firing, circadian rhythms), engineering (clocks, oscillators, tuning circuits), and chemistry (Belousov-Zhabotinsky reaction). Unlike the oscillations of conservative systems (centers, where amplitude depends on initial conditions), LIMIT CYCLES have AMPLITUDE DETERMINED by the equations themselves — robust to perturbations, the defining feature of "real" oscillators.

## 5.2 Stable vs Unstable Cycles

Q: Distinguish STABLE, UNSTABLE, and SEMI-STABLE limit cycles.
A: STABLE (attracting): trajectories from BOTH sides spiral INTO the cycle. UNSTABLE (repelling): trajectories SPIRAL AWAY from both sides. SEMI-STABLE: trajectories approach from one side, leave on the other. Stable limit cycles are ROBUST attractors — typical physical oscillators. Unstable cycles rarely observed directly but ORGANIZE the flow; semi-stable occur at bifurcation boundaries (saddle-node of cycles).

## 5.3 Limit Cycle vs Center

Q: What's the ESSENTIAL difference between a LIMIT CYCLE and a CENTER (neutral closed orbit)?
A: A CENTER is one orbit in a CONTINUOUS FAMILY of closed orbits — different initial conditions give different amplitudes. A LIMIT CYCLE is ISOLATED: nearby orbits are NOT closed; they spiral toward (or away from) the one special closed orbit. Centers typically occur in CONSERVATIVE systems; limit cycles in DISSIPATIVE systems where amplitude is "picked" by the dynamics.

## 5.4 The Poincaré-Bendixson Theorem

Q: State the [Poincaré-Bendixson theorem].
A: In a 2D autonomous system: any TRAJECTORY confined to a CLOSED, BOUNDED region of phase space containing NO FIXED POINTS must approach a CLOSED ORBIT (limit cycle) as $t \to \infty$. If the region contains fixed points, the $\omega$-limit set is either (a) a fixed point, (b) a limit cycle, or (c) a chain of fixed points connected by heteroclinic/homoclinic orbits.

Q: What is the SIGNIFICANCE of Poincaré-Bendixson?
A: It CHARACTERIZES long-term behavior in 2D: there's nothing else besides fixed points and limit cycles (and connecting orbits). NO CHAOS in 2D autonomous flows — trapped by the theorem. Chaos requires 3+ dimensions. Also gives a METHOD to PROVE EXISTENCE of limit cycles: construct a trapping region (inflow on boundary) containing no equilibria — by PB, a cycle must exist inside.

## 5.5 Trapping Region Construction

Q: How do you PROVE existence of a limit cycle via the Poincaré-Bendixson approach?
A: (1) Find an ANNULAR REGION $R$ (or bounded region with no fixed points) in phase space. (2) Show the vector field points INWARD on the outer boundary AND OUTWARD on any inner boundary — so trajectories are TRAPPED in $R$. (3) Verify $R$ contains no fixed points. PB then guarantees at least one CLOSED ORBIT in $R$. Commonly used for the Van der Pol oscillator and predator-prey systems.

## 5.6 Van der Pol Oscillator

Q: Write the [Van der Pol equation] and its phase-plane form.
A: Second-order: $\ddot{x} - \mu(1 - x^2) \dot{x} + x = 0$. As 2D system: $\dot{x} = y, \dot{y} = \mu(1 - x^2) y - x$. "Nonlinear damping" — damping is NEGATIVE for $|x| < 1$ (energy pumped in) and POSITIVE for $|x| > 1$ (energy dissipated). The balance creates a UNIQUE stable limit cycle. Invented by Balthasar van der Pol (1920s) modeling radio vacuum-tube oscillators.

Q: Why does the VAN DER POL oscillator have a UNIQUE stable limit cycle?
A: Because amplitude-dependent damping (negative near origin, positive at large amplitude) self-regulates the oscillation. Small oscillations are AMPLIFIED by negative damping; large oscillations are DAMPED by positive damping. The equilibrium amplitude is where these balance. Any initial condition converges to this limit cycle — amplitude is dynamically selected, not imposed. Classical model for biological oscillators (heartbeat), electronics (self-excited circuits), acoustics.

## 5.7 Relaxation Oscillations

Q: What is a [relaxation oscillation]?
A: A limit cycle with TWO TIMESCALES: slow buildup phase, rapid discharge phase. Van der Pol for large $\mu$: trajectory slowly climbs the cubic nullcline, then rapidly jumps to the other branch. Models: neuron action potentials (slow depolarization, rapid spike), heartbeat (slow pressure buildup, rapid contraction), stick-slip friction, earthquakes. Analytical tool: singular perturbation theory, fast-slow decomposition.

## 5.8 Hopf Bifurcation

Q: Describe the [Hopf bifurcation].
A: A fixed point LOSES STABILITY as a pair of complex conjugate eigenvalues crosses the imaginary axis (real parts change sign). SUPERCRITICAL: stable fixed point → unstable fixed point + small-amplitude stable limit cycle. SUBCRITICAL: stable fixed point + large unstable cycle → unstable fixed point, cycle disappears. The Hopf theorem: SMOOTH bifurcation yields cycles with amplitude $\propto \sqrt{r - r_c}$ (for supercritical). The canonical route to OSCILLATIONS in 2D (and higher).

Q: What's the INTUITION behind the Hopf bifurcation?
A: Think of a stable spiral (focus) becoming weaker — eigenvalues with negative real part move toward imaginary axis. At criticality, system is "oscillatory on the edge." Past criticality, spiral becomes repelling; but nonlinear terms curve trajectories back, trapping them into a small limit cycle. Pervasive: onset of flutter in aircraft wings, instability of fluid flows (Taylor-Couette), onset of oscillation in lasers/chemistry.

## 5.9 Liénard Systems

C: A [Liénard system] has the form $\ddot{x} + f(x) \dot{x} + g(x) = 0$, equivalent to $\dot{x} = y - F(x), \dot{y} = -g(x)$ where $F(x) = \int_0^x f(s) ds$.

Q: State the [Liénard theorem] for existence of a unique limit cycle.
A: If (i) $F$ is odd, (ii) $g$ is odd with $g(x) > 0$ for $x > 0$, (iii) $F$ has exactly one positive zero at $x = a$, (iv) $F$ is decreasing for $0 < x < a$ and increasing for $x > a$, with $F(x) \to \infty$ as $x \to \infty$: then the system has a UNIQUE STABLE LIMIT CYCLE. Van der Pol (with $F(x) = \mu(x^3/3 - x)$) satisfies these — proving its limit cycle.

## 5.10 Weakly Nonlinear Oscillators

Q: How do you analyze NEARLY-SINUSOIDAL oscillations analytically?
A: [Method of multiple scales] or [averaging]: assume $x(t) = A(t) \cos(t + \phi(t))$ with slowly varying amplitude $A$ and phase $\phi$. Substitute into ODE; average over one fast cycle. Get SLOW ODEs for $A$ and $\phi$: their fixed points give limit cycle amplitude/frequency. Powerful for small-$\mu$ Van der Pol and many engineering oscillators. Perturbation theory for cycles.

## 5.11 Bendixson-Dulac Revisited

Q: When is BENDIXSON's criterion (simpler form of Dulac) useful?
A: Bendixson: if $\text{div}(f) = \partial f_1 / \partial x + \partial f_2 / \partial y$ has a DEFINITE SIGN (nonzero, consistent) in a simply-connected region, then NO CLOSED ORBITS lie entirely within. Quickly rules out cycles in regions where the divergence doesn't change sign. Dulac generalizes with a multiplier $g(x, y) > 0$: if $\text{div}(gf)$ is sign-definite. Standard negative result to complement Poincaré-Bendixson positive existence proofs.

## 5.12 A Worked Limit Cycle Proof

P: Prove that the system $\dot{x} = x - y - x(x^2 + y^2), \dot{y} = x + y - y(x^2 + y^2)$ has a limit cycle.
S:
**IDENTIFY**: 2D autonomous. Convert to polar coordinates to simplify.

**PLAN**: Use $r^2 = x^2 + y^2$, $\tan \theta = y/x$. Compute $\dot{r}$ and $\dot{\theta}$.

**EXECUTE**:
$r \dot{r} = x \dot{x} + y \dot{y} = x(x - y - xr^2) + y(x + y - yr^2) = x^2 - xy - x^2 r^2 + xy + y^2 - y^2 r^2 = r^2 - r^4$.
So $\dot{r} = r - r^3 = r(1 - r^2)$.

Similarly, $\dot{\theta}$: $r^2 \dot{\theta} = x \dot{y} - y \dot{x} = x(x + y - y r^2) - y(x - y - x r^2) = x^2 + xy - xy r^2 - xy + y^2 + xy r^2 = x^2 + y^2 = r^2$.
So $\dot{\theta} = 1$.

Radial equation $\dot{r} = r(1 - r^2)$:
- $r = 0$: unstable fixed point (origin, unstable spiral).
- $r = 1$: $\dot{r} = 0$; linearize $\dot{r} = r - r^3$ at $r = 1$: $f'(1) = 1 - 3 = -2 < 0$ — STABLE.

Angular equation $\dot{\theta} = 1$: uniform rotation, period $2\pi$.

Hence: $r = 1$ is a STABLE LIMIT CYCLE (a CIRCLE), and trajectories spiral into it with angular velocity 1.

**EVALUATE**: Circle $r = 1$ is indeed a limit cycle, stable, enclosing the unstable origin. Any initial condition ($r_0 > 0$) converges to $r = 1$ as $t \to \infty$. This is the SIMPLEST ANALYTICAL EXAMPLE of a limit cycle — all dynamics decouple in polar coordinates. Parallel to the NORMAL FORM of a supercritical Hopf bifurcation: $\dot{r} = \mu r - r^3, \dot{\theta} = \omega$. As $\mu$ varies through 0, cycle appears/disappears. Real-world Hopf bifurcations (say, onset of flow instability) locally reduce to this.
