+++
order = 7
subject = "Mathematics"
tags = ["math", "dynamical-systems", "maps", "logistic", "period-doubling", "feigenbaum", "iteration"]
+++

# Dynamical Systems — Discrete Maps and the Logistic Map

## 7.1 Why Discrete Maps

Q: Why study ITERATED MAPS alongside continuous flows?
A: (1) Some systems are INHERENTLY DISCRETE (annual population counts, digital signal processing). (2) POINCARÉ SECTIONS reduce continuous 3D flows to 2D maps — turning continuous chaos into discrete analysis. (3) Maps can be CHAOTIC IN 1D (logistic map), whereas flows need 3D. Simplest setting for chaos theory. (4) NUMERICAL integrators (Euler, RK4) are effectively maps. Maps are TRACTABLE playgrounds for complex dynamics.

## 7.2 Fixed Points and Periodic Orbits

C: A [fixed point] of a map $F$ is a point $x^*$ with $F(x^*) = x^*$. A [period-$k$ orbit] is a sequence $x_1, x_2, \ldots, x_k, x_1, x_2, \ldots$ with $F^k(x_i) = x_i$.

Q: Characterize STABILITY of a fixed point $x^*$ of a 1D map.
A: Linearize: $F(x^* + \epsilon) \approx x^* + F'(x^*) \epsilon$. So $\epsilon_{n+1} = F'(x^*) \epsilon_n$ — geometric growth with ratio $|F'(x^*)|$. Fixed point is ATTRACTING iff $|F'(x^*)| < 1$; REPELLING iff $> 1$; MARGINAL iff $= 1$ (needs higher-order analysis). Parallels the sign-of-eigenvalue criterion for flows, but uses MAGNITUDE relative to 1 instead of sign relative to 0.

## 7.3 The Logistic Map

Q: State the [logistic map] and its domain of interest.
A: $x_{n+1} = r \cdot x_n (1 - x_n)$ for $r \in [0, 4]$ and $x_n \in [0, 1]$. Simplest model of population dynamics with BOUNDED GROWTH: $rx$ = linear growth, $(1 - x)$ = resource limitation. Despite simplicity, exhibits EVERY MAJOR DYNAMICAL phenomenon — fixed points, periodic orbits, period-doubling, chaos, windows of periodicity. Discovered by May (1976) as a cautionary example for naive population models.

## 7.4 Fixed Points of the Logistic Map

Q: Find the fixed points of the logistic map $x_{n+1} = r x_n (1 - x_n)$ and analyze their stability.
A: Fixed points: $x^* = rx^*(1 - x^*) \Rightarrow x^*(1 - r(1 - x^*)) = 0$. Solutions: $x^* = 0$ and $x^* = 1 - 1/r$ (the latter in $[0, 1]$ for $r \geq 1$).
Derivative: $F'(x) = r(1 - 2x)$.
- $F'(0) = r$: $x = 0$ stable for $r < 1$, unstable for $r > 1$.
- $F'(1 - 1/r) = r - 2(r - 1) = 2 - r$: $|F'| < 1 \iff 1 < r < 3$. Stable for $1 < r < 3$.

## 7.5 The Period-Doubling Cascade

Q: Describe the period-doubling route in the logistic map.
A: At $r = 3$: fixed point $1 - 1/r$ loses stability via $F'(x^*) = -1$. A period-2 orbit is born (PERIOD-DOUBLING BIFURCATION). At $r \approx 3.449$: period-2 becomes unstable, period-4 born. At $r \approx 3.544$: period-8. At $r \approx 3.564$: period-16. The $r$-values accumulate at $r_\infty \approx 3.5699$ — the onset of CHAOS. Infinitely many period-doublings in a finite parameter interval.

## 7.6 The Feigenbaum Constant

Q: What is the [Feigenbaum constant], and why is it UNIVERSAL?
A: Ratios of successive intervals between period-doublings converge: $\delta = \lim_{n \to \infty} \frac{r_n - r_{n-1}}{r_{n+1} - r_n} \approx 4.6692$. Feigenbaum (1978) discovered this ratio is the SAME for ALL smooth 1D maps with a single quadratic maximum — a UNIVERSAL constant of period-doubling. Like $\pi$ for circles, $\delta$ characterizes a universality class of dynamics. Confirmed experimentally in fluid convection, lasers, BZ chemistry — a breakthrough for nonlinear physics.

Q: What other universal constants arise in period-doubling?
A: Feigenbaum's $\alpha \approx 2.5029$: ratio of separations between successive bifurcation points along the "$x$-axis" (rescaling of attractor). Together $\delta$ and $\alpha$ define the universality class. Connection to RENORMALIZATION GROUP in statistical physics — period-doubling is a FIXED POINT of a functional renormalization transformation, with $\delta$ as its largest eigenvalue.

## 7.7 Chaos in the Logistic Map

Q: Describe CHAOS in the logistic map at $r = 4$.
A: $x_{n+1} = 4x_n(1 - x_n)$. Trajectories wander over the entire interval $[0, 1]$. Sensitive dependence on initial conditions: two nearby starting points diverge exponentially. Iterates have a statistical description via an invariant measure $\rho(x) = 1/(\pi \sqrt{x(1-x)})$ (beta distribution). Via conjugation $x = \sin^2(\pi y/2)$, the map becomes $y_{n+1} = 2 y_n \mod 1$ — the DOUBLING MAP — obviously chaotic.

Q: What does "CHAOS" mean precisely in a discrete dynamical system?
A: (1) SENSITIVE DEPENDENCE on initial conditions: nearby orbits diverge exponentially (positive Lyapunov exponent). (2) TOPOLOGICALLY TRANSITIVE: orbits are dense (roughly: any neighborhood eventually visits any other). (3) DENSE PERIODIC ORBITS in the attractor. Devaney's definition requires all three, though (3) has been shown to follow from (1)+(2) for most cases. "Deterministic yet unpredictable."

## 7.8 Windows of Periodicity

Q: What are [windows of periodicity] in the logistic map?
A: Amid chaos, there are intervals of $r$ where PERIODIC orbits reappear. Famous: the PERIOD-3 WINDOW near $r \approx 3.828$ — a stable period-3 orbit exists. Within each window: its own period-doubling cascade to chaos, embedded in the larger chaos. Fractal bifurcation diagram: self-similar periodic windows within chaotic bands. SHARKOVSKII's theorem: period-3 implies all periods present.

## 7.9 Sharkovskii's Theorem

Q: State [Sharkovskii's theorem].
A: Arrange natural numbers as $3 \triangleright 5 \triangleright 7 \triangleright \cdots \triangleright 2 \cdot 3 \triangleright 2 \cdot 5 \triangleright \cdots \triangleright 2^2 \cdot 3 \triangleright \cdots \triangleright 2^n \triangleright \cdots \triangleright 4 \triangleright 2 \triangleright 1$. For any continuous interval map $f : I \to I$: if $f$ has a periodic point of period $m$, it has periodic points of every period $n$ with $m \triangleright n$. Corollary: PERIOD-3 IMPLIES ALL PERIODS — i.e., "period 3 implies chaos" (Li-Yorke). Structural result about 1D dynamics.

## 7.10 Tent Map and Conjugate Chaos

Q: Describe the [tent map] and its relation to the logistic map.
A: Tent map: $T(x) = \begin{cases} 2x & 0 \leq x \leq 1/2 \\ 2(1-x) & 1/2 \leq x \leq 1 \end{cases}$. Chaotic on $[0, 1]$. Related to binary expansion: iterating the tent map is equivalent to left-shifting binary digits — explicitly chaotic. The FULL-STRENGTH LOGISTIC MAP ($r = 4$) is TOPOLOGICALLY CONJUGATE to the tent map via a smooth change of coordinates — so they share all dynamical invariants (Lyapunov exponents, periodic orbits).

## 7.11 Circle Maps and Mode Locking

Q: What is a [circle map], and what phenomena does it exhibit?
A: $\theta_{n+1} = \theta_n + \Omega - (K/2\pi) \sin(2\pi \theta_n) \mod 1$ — models periodic forcing of an oscillator. Exhibits [Arnold tongues]: regions in $(K, \Omega)$-parameter space where dynamics LOCK to a rational rotation number $p/q$. Between tongues: quasi-periodic behavior. At $K = 1$: tongues meet, fill the $\Omega$-axis — transition to chaos. Models: circadian rhythm entrainment, locked lasers, heart rhythm syncing to pacemaker.

## 7.12 A Worked Map Analysis

P: Compute the period-2 orbit of the logistic map for $r = 3.2$ and verify its stability.
S:
**IDENTIFY**: Period-2 solutions satisfy $F^2(x) = x$ but $F(x) \neq x$.

**PLAN**: Solve $F(F(x)) = x$ analytically; check stability via derivative of $F^2$.

**EXECUTE**:
$F(x) = rx(1-x) = 3.2 x(1-x)$.

$F^2(x) = x$ is a quartic. Roots include the fixed points $x = 0$ and $x = 1 - 1/r = 1 - 1/3.2 = 0.6875$. Factoring these out leaves a quadratic for the period-2 points:

$F^2(x) = x \Rightarrow r^2 x(1-x)(1 - rx(1-x)) = x$

Dividing out $x$ and $(x - (1 - 1/r))$ leaves: $r^2 x^2 - r(r+1) x + (r+1) = 0$.

For $r = 3.2$: $10.24 x^2 - 13.44 x + 4.2 = 0$, giving $x = \frac{13.44 \pm \sqrt{180.6 - 172.0}}{20.48} = \frac{13.44 \pm 2.93}{20.48}$.

$x_1 \approx 0.799$, $x_2 \approx 0.513$.

Verify: $F(0.513) = 3.2 \cdot 0.513 \cdot 0.487 \approx 0.800$ ✓.
$F(0.799) = 3.2 \cdot 0.799 \cdot 0.201 \approx 0.514$ ✓.

Stability: $(F^2)'(x_1) = F'(x_1) F'(x_2) = r(1 - 2x_1) \cdot r(1 - 2x_2) = 10.24 \cdot (1 - 1.598) \cdot (1 - 1.026) \approx 10.24 \cdot (-0.598) \cdot (-0.026) \approx 0.159$.

$|(F^2)'| \approx 0.159 < 1$ — period-2 orbit is STABLE.

**EVALUATE**: For $r = 3.2$, a stable period-2 orbit oscillates between $\sim 0.513$ and $\sim 0.799$. Fixed points $x = 0$ (unstable, $r > 1$) and $x = 0.6875$ (unstable, $r > 3$) exist but are repelling. At $r = 3$: period-2 is BORN (flipped eigenvalue crosses $-1$). At $r \approx 3.449$: $(F^2)'$ reaches $-1$ at this orbit → period-4 born. Cascade continues to accumulation $r_\infty \approx 3.5699$ — chaos. The logistic map's richness from a simple quadratic is astonishing.
