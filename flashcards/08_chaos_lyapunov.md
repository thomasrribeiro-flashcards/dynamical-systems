+++
order = 8
subject = "mathematics"
tags = ["math", "dynamical-systems", "chaos", "lyapunov-exponents", "sensitivity", "butterfly-effect", "predictability"]
+++

# Dynamical Systems — Chaos and Lyapunov Exponents

## 8.1 What Chaos Is

Q: What are the THREE defining features of CHAOS?
A: (1) [Deterministic]: governed by fixed rules, no randomness. (2) [Sensitive to initial conditions]: infinitesimal perturbations grow exponentially — "butterfly effect." (3) [Aperiodic yet bounded]: trajectories never repeat (or very slowly) but stay within a finite region of phase space. Chaos is NOT randomness — given identical initial conditions, outcome is identical. But unpredictability follows from impossibility of measuring initial conditions with infinite precision.

## 8.2 The Butterfly Effect

Q: What is the [butterfly effect]?
A: Popularization of SENSITIVE DEPENDENCE ON INITIAL CONDITIONS: a butterfly flapping its wings in Brazil can cause a tornado in Texas weeks later. Coined by Lorenz (1972). Mathematically: two initial conditions differing by $\epsilon$ diverge as $\epsilon e^{\lambda t}$ for positive Lyapunov exponent $\lambda$. After $t \sim \ln(1/\epsilon) / \lambda$ time units, predictions become useless. Explains why weather forecasts are unreliable beyond ~2 weeks.

## 8.3 Lyapunov Exponents

C: The [largest Lyapunov exponent] $\lambda$ of a trajectory measures the AVERAGE EXPONENTIAL RATE of separation of nearby trajectories: $|\delta x(t)| \sim |\delta x(0)| e^{\lambda t}$.

Q: Formal definition of the LARGEST Lyapunov exponent.
A: For continuous systems: $\lambda = \lim_{t \to \infty} \frac{1}{t} \ln \frac{|\delta x(t)|}{|\delta x(0)|}$, for an infinitesimal perturbation $\delta x$. For maps: $\lambda = \lim_{n \to \infty} \frac{1}{n} \sum_{i=0}^{n-1} \ln |F'(x_i)|$ (1D case). Positive $\lambda \Rightarrow$ CHAOS. Negative $\Rightarrow$ trajectories converge (stable). Zero $\Rightarrow$ neutral (limit cycle or quasi-periodic).

## 8.4 The Full Lyapunov Spectrum

C: An $n$-dimensional system has $n$ [Lyapunov exponents] $\lambda_1 \geq \lambda_2 \geq \cdots \geq \lambda_n$, measuring exponential growth rates of perturbations along $n$ orthogonal directions.

Q: What does the FULL Lyapunov spectrum tell you?
A: (1) [Sum] $\sum \lambda_i$ = time-averaged divergence of flow — negative for DISSIPATIVE systems (attractors have zero measure), zero for CONSERVATIVE. (2) [One zero exponent] for any autonomous flow (along direction of motion). (3) [Largest positive] exponent gives chaos rate. (4) [Kaplan-Yorke dimension]: fractal dimension of attractor = $D_{KY} = j + \frac{\lambda_1 + \cdots + \lambda_j}{|\lambda_{j+1}|}$ for appropriate $j$. Full spectrum characterizes the attractor.

## 8.5 Lyapunov Exponent of the Logistic Map

Q: Compute the Lyapunov exponent of the logistic map $x_{n+1} = r x_n (1 - x_n)$ at $r = 4$.
A: $F'(x) = r(1 - 2x) = 4(1 - 2x)$. Invariant density: $\rho(x) = 1/(\pi\sqrt{x(1-x)})$.
$\lambda = \int_0^1 \ln|F'(x)| \rho(x) \, dx = \int_0^1 \ln|4(1 - 2x)| \frac{1}{\pi\sqrt{x(1-x)}} dx = \ln 2 \approx 0.693$ per iteration.
So two nearby initial conditions double their separation every iteration (in log sense). Characteristic of full-chaos logistic.

Q: What does a POSITIVE Lyapunov exponent $\lambda$ mean QUANTITATIVELY?
A: If you can measure initial conditions with precision $\epsilon$: predictions become useless after time $T \approx (1/\lambda) \ln(L/\epsilon)$ where $L$ is the system size. Example: weather has $\lambda \approx 1/\text{day}$. With $\epsilon = 10^{-9}$ precision, useful forecast horizon $\approx \ln(10^9) \approx 20$ days. Doubling measurement precision ADDS ONE Lyapunov time ($1/\lambda$) — logarithmic, not linear. Why weather prediction is fundamentally limited despite better models.

## 8.6 Power Spectra and Autocorrelation

Q: How can you DETECT chaos experimentally?
A: (1) [Broadband power spectrum]: periodic signals have sharp peaks; chaos has a continuous (noise-like) spectrum, often with some peaks corresponding to unstable periodic orbits embedded in the attractor. (2) [Decaying autocorrelation]: $\langle x(t) x(t + \tau) \rangle$ decays exponentially for chaos; stays at unity for periodic. (3) [Positive Lyapunov exponent] computed from data (Wolf algorithm, Rosenstein). (4) [Fractal dimension] $< $ phase space dimension. Care: noise mimics chaos' broadband spectrum; additional tests needed.

## 8.7 Attractor Reconstruction

Q: What is [Takens' embedding theorem]?
A: Given a scalar time series $x(t)$ from a chaotic attractor: the attractor's dynamics can be RECONSTRUCTED in a space of DELAY COORDINATES $(x(t), x(t - \tau), x(t - 2\tau), \ldots, x(t - (m - 1)\tau))$ for sufficient embedding dimension $m$ and delay $\tau$. Provides a diffeomorphism between original attractor and reconstructed one — preserving topological/dynamical invariants. Essential for analyzing data from experiments where only ONE observable is measured.

## 8.8 Strange Attractors

C: A [strange attractor] is a bounded attracting set on which the dynamics are CHAOTIC and the attractor has FRACTAL structure.

Q: Why are strange attractors called "STRANGE"?
A: Because they combine seemingly contradictory features: DISSIPATIVE (trajectories converge to a set of zero volume) yet CHAOTIC (trajectories on the set diverge exponentially). Geometrically FRACTAL: zoom in arbitrarily and find the same structure (self-similarity). TOPOLOGICALLY complex: not a manifold, can't be parameterized locally by smooth coordinates. Examples: Lorenz attractor, Rössler attractor, Hénon attractor — canonical "strange" shapes.

## 8.9 Stretching and Folding

Q: Describe the GEOMETRIC mechanism producing chaos: [stretching and folding].
A: In any finite region of phase space: (1) [Stretching] along unstable directions (positive Lyapunov exponent) amplifies separations. (2) [Folding] (due to bounded phase space) brings distant trajectories back close. The repeated combination (like a baker's transformation) creates INFINITELY FINE STRUCTURE — fractal attractors. "Horseshoe map" (Smale) formalizes this: a region stretched and folded back creates a fully chaotic sub-dynamics on a Cantor-like invariant set.

## 8.10 Symbolic Dynamics

Q: What is [symbolic dynamics]?
A: Encode trajectories by SEQUENCES OF SYMBOLS corresponding to which region of phase space the trajectory visits. For the doubling map or Smale horseshoe: binary sequences. For the tent map: same. Properties of sequences (periodic, shift-invariant) correspond to dynamical properties. Reduces chaotic dynamics to SHIFT on symbol sequences — combinatorial/topological framework. Basis of ergodic theory, entropy, and rigorous analysis of chaos.

## 8.11 Routes to Chaos

Q: Name the THREE classic ROUTES to chaos.
A: (1) [PERIOD-DOUBLING] (Feigenbaum): infinite sequence of period-doubling bifurcations accumulating at chaos. Universal scaling constant $\delta \approx 4.669$. (2) [QUASI-PERIODICITY] (Ruelle-Takens): after two Hopf bifurcations, dynamics lie on a torus; tori break down via resonances or "Newhouse" bifurcations into chaotic attractors. (3) [INTERMITTENCY] (Pomeau-Manneville): periodic behavior interrupted by chaotic bursts; classes I, II, III distinguish types. Observed routinely in fluids, lasers, chemical reactors.

## 8.12 A Worked Lyapunov Calculation

P: Numerically compute the Lyapunov exponent of the logistic map at $r = 3.8$ (chaotic regime).
S:
**IDENTIFY**: 1D map; Lyapunov exponent = time-average of $\ln|F'(x)|$ over a typical orbit.

**PLAN**: Iterate the map starting from a random $x_0$, discard transient, compute $\frac{1}{N} \sum \ln|F'(x_i)|$ over long orbit.

**EXECUTE**:
$F(x) = 3.8 x(1-x)$, $F'(x) = 3.8(1 - 2x)$.

Pseudo-iterate from $x_0 = 0.5$:
- $x_0 = 0.5$: $F'(0.5) = 0$ (degenerate! skip transient)
- Discard first 100 iterations.
- Iterate $N = 10000$ more, accumulate $\sum \ln|F'(x_i)|$.
- Numerical result: $\lambda \approx 0.43$ per iteration (well-known value for $r = 3.8$).

Meaning: initial condition separations grow by factor $e^{0.43} \approx 1.54$ per iteration. After 20 iterations, perturbation of $10^{-6}$ grows to $\sim 10^{-6} \cdot 1.54^{20} \approx 10^{-2}$ — observable macroscopic difference.

**EVALUATE**: $\lambda = 0.43 > 0$ CONFIRMS chaos at $r = 3.8$. Compare: $r = 3.5$ gives period-4 (non-chaotic): $\lambda < 0$. $r = 4$ (full chaos): $\lambda = \ln 2 \approx 0.693$. Bifurcation diagram of $\lambda$ vs $r$: negative in periodic windows, positive in chaotic regions, zero at bifurcation points and windows boundaries. Numerical Lyapunov exponent is a STANDARD DIAGNOSTIC for chaos in any dynamical system — applicable to experimental time series via Wolf's algorithm.
