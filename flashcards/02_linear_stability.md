+++
order = 2
subject = "mathematics"
tags = ["math", "dynamical-systems", "linear-systems", "stability", "eigenvalues", "jacobian", "linearization"]
+++

# Dynamical Systems — Linear Systems and Stability Analysis

## 2.1 Linear Dynamical Systems

C: A [linear dynamical system] in $\mathbb{R}^n$ is $\dot{\mathbf{x}} = A \mathbf{x}$ where $A$ is an $n \times n$ matrix. The flow is $\phi_t(\mathbf{x}_0) = e^{At} \mathbf{x}_0$.

Q: Why do we STUDY LINEAR SYSTEMS despite most real systems being nonlinear?
A: Because (1) linear systems can be SOLVED EXACTLY using matrix exponentials and eigendecomposition. (2) [Hartman-Grobman theorem]: near a HYPERBOLIC fixed point, the nonlinear system is locally equivalent to its linearization. Linear analysis thus gives LOCAL behavior of nonlinear systems. (3) Linear systems are the natural test-bed for stability concepts before generalizing. Linear theory is the foundation upon which all nonlinear analysis builds.

## 2.2 The Matrix Exponential

C: The [matrix exponential] of $A$ is $e^{At} = \sum_{k=0}^\infty \frac{(At)^k}{k!} = I + At + \frac{(At)^2}{2!} + \cdots$, converging for all $t$.

Q: How does matrix exponential SOLVE linear systems?
A: If $A$ is diagonalizable as $A = P D P^{-1}$ with $D$ diagonal of eigenvalues $\lambda_i$: $e^{At} = P e^{Dt} P^{-1}$ where $e^{Dt}$ is diagonal with entries $e^{\lambda_i t}$. So solutions decompose into eigenvector components: $\mathbf{x}(t) = \sum_i c_i e^{\lambda_i t} \mathbf{v}_i$, where $\mathbf{v}_i$ are eigenvectors and $c_i$ are initial-condition coefficients. Each eigenvalue governs one mode of evolution.

## 2.3 Stability of Linear Systems

Q: State the STABILITY CRITERION for linear systems $\dot{\mathbf{x}} = A\mathbf{x}$.
A: (1) [Asymptotically stable] iff ALL eigenvalues of $A$ have $\text{Re}(\lambda_i) < 0$ — every mode decays. (2) [Unstable] iff any eigenvalue has $\text{Re}(\lambda_i) > 0$ — some mode grows. (3) [Marginally stable / Lyapunov] iff all eigenvalues have $\text{Re}(\lambda_i) \leq 0$, with zero real parts having simple Jordan blocks — oscillates or is constant in neutral directions.

Q: Why does the SIGN OF THE REAL PART of eigenvalues determine stability?
A: Because $e^{\lambda t} = e^{\text{Re}(\lambda) t} \cdot e^{i \text{Im}(\lambda) t}$. The real part controls magnitude: $|e^{\lambda t}| = e^{\text{Re}(\lambda) t}$ — decays iff $\text{Re}(\lambda) < 0$. The imaginary part creates rotations/oscillations but doesn't change magnitude. So growth/decay of each mode depends ENTIRELY on real parts. Complex eigenvalues come in conjugate pairs (real matrix) — their real parts are equal.

## 2.4 Classification in 2D

Q: How do the eigenvalues of a 2D linear system relate to the trace $\tau = \text{tr}(A)$ and determinant $\Delta = \det(A)$?
A: Eigenvalues satisfy $\lambda^2 - \tau \lambda + \Delta = 0$, so $\lambda = \frac{\tau \pm \sqrt{\tau^2 - 4\Delta}}{2}$.

C: Trace-determinant classification: $\Delta < 0$ gives a [SADDLE] (real eigenvalues of opposite signs — always unstable).

C: Trace-determinant classification: $\Delta > 0$ with $\tau^2 > 4\Delta$ gives a [NODE] (real eigenvalues of the same sign — stable if $\tau < 0$, unstable if $\tau > 0$).

C: Trace-determinant classification: $\Delta > 0$ with $\tau^2 < 4\Delta$ and $\tau \neq 0$ gives a [SPIRAL / FOCUS] (complex eigenvalues — stable if $\tau < 0$).

C: Trace-determinant classification: $\Delta > 0$ with $\tau = 0$ gives a [CENTER] (pure imaginary eigenvalues — closed orbits).

Q: Describe the behavior near a SADDLE point.
A: Two real eigenvalues of OPPOSITE SIGN, with eigenvectors forming the STABLE and UNSTABLE MANIFOLDS. Trajectories approach along the stable direction (negative eigenvalue) and recede along the unstable direction (positive eigenvalue). NONE stay near the saddle except those on the stable manifold itself. Saddles are UNSTABLE but organize flow: stable/unstable manifolds form separatrices that partition phase space into qualitatively distinct regions.

## 2.5 Spiral vs Node

Q: What distinguishes a SPIRAL (focus) from a NODE?
A: Both have eigenvalues of the same sign (or zero), but NODE has REAL eigenvalues (trajectories approach along eigenvector directions in straight lines) while SPIRAL has COMPLEX eigenvalues (trajectories spiral in or out). Physically: a spiral is an oscillatory decay/growth (damped oscillator); a node is monotonic (overdamped). Transition: critical damping ($\tau^2 = 4\Delta$) gives a DEGENERATE NODE — the boundary between nodes and spirals.

## 2.6 Centers and Conservation

Q: When does a linear system have a CENTER (pure imaginary eigenvalues)?
A: When $\tau = \text{tr}(A) = 0$ and $\Delta = \det(A) > 0$. Eigenvalues $\lambda = \pm i\sqrt{\Delta}$ — pure oscillations, no growth or decay. Trajectories are ellipses. Centers occur in HAMILTONIAN (conservative) systems: the phase-space "volume" is preserved (Liouville's theorem), so trajectories can't spiral in or out. Examples: harmonic oscillator, undamped pendulum at small angle, simple planetary motion.

## 2.7 Hartman-Grobman Theorem

Q: State the [Hartman-Grobman theorem].
A: If $x^*$ is a HYPERBOLIC fixed point of $\dot{\mathbf{x}} = f(\mathbf{x})$ — meaning the Jacobian $Df(x^*)$ has no eigenvalues with zero real part — then NEAR $x^*$ the nonlinear flow is TOPOLOGICALLY EQUIVALENT to its linearization $\dot{\mathbf{x}} = Df(x^*) \mathbf{x}$. I.e., a continuous change of coordinates maps trajectories of the nonlinear system to trajectories of the linearized one, preserving direction.

Q: What does HARTMAN-GROBMAN LET US DO in practice?
A: For hyperbolic fixed points, LINEARIZE to determine LOCAL behavior: compute Jacobian at $x^*$, find eigenvalues, classify as node/saddle/spiral/etc. — these classifications carry over to the full nonlinear system LOCALLY. Hyperbolicity is key: if the Jacobian has zero-real-part eigenvalues (centers, degenerate), NONLINEAR TERMS CAN CHANGE BEHAVIOR — linearization is inconclusive, and you must consider higher-order terms.

## 2.8 Linearization at Fixed Points

Q: How do you LINEARIZE a nonlinear system $\dot{\mathbf{x}} = f(\mathbf{x})$ at a fixed point $x^*$?
A: Compute the JACOBIAN $J = Df(x^*) = \left[\partial f_i / \partial x_j\right]_{x = x^*}$. Near $x^*$, let $\mathbf{u} = \mathbf{x} - x^*$; then $\dot{\mathbf{u}} \approx J \mathbf{u}$ (Taylor expand, drop higher-order terms). Analyze LOCAL behavior via eigenvalues of $J$. If hyperbolic, Hartman-Grobman gives local equivalence; if not, linearization may fail (e.g., centers).

## 2.9 Stable and Unstable Manifolds

C: The [stable manifold] $W^s(x^*)$ is the set of points approaching $x^*$ as $t \to +\infty$. The [unstable manifold] $W^u(x^*)$ is the set approaching $x^*$ as $t \to -\infty$.

Q: What's the SIGNIFICANCE of invariant manifolds?
A: They are the SKELETONS of the phase portrait. They (1) partition phase space into regions of different long-term behavior; (2) organize transitions between fixed points (heteroclinic orbits) or cycles (homoclinic); (3) form the boundaries between BASINS OF ATTRACTION of different attractors; (4) host complex dynamics near their intersections (homoclinic tangles → chaos). In numerical work, stable/unstable manifolds are computed by forward/backward integration from near $x^*$ along stable/unstable eigendirections.

## 2.10 Jordan Blocks and Degenerate Cases

Q: What happens if $A$ is NON-DIAGONALIZABLE?
A: $A$ has Jordan blocks. The solution includes terms like $t e^{\lambda t}$ (for a double eigenvalue with one eigenvector). Stability still determined by real parts: ASYMPTOTIC if all $\text{Re}(\lambda) < 0$; but MARGINAL stability (zero real part) may become UNSTABLE if a repeated eigenvalue has polynomial growth. Example: $A = \begin{pmatrix} 0 & 1 \\ 0 & 0 \end{pmatrix}$ has double eigenvalue 0; solutions include $y(t) = y_0, x(t) = x_0 + y_0 t$ — linear growth, unstable.

## 2.11 Lyapunov Functions

Q: What is a [Lyapunov function], and why is it useful for nonlinear stability?
A: A scalar function $V(\mathbf{x})$ that decreases along trajectories: $\dot{V} = \nabla V \cdot f(\mathbf{x}) < 0$ near $x^*$ (positive definite around $x^*$). Existence proves $x^*$ is asymptotically stable WITHOUT needing linearization or explicit solution. Physical intuition: $V$ is an "energy" function; if energy dissipates, system converges. Works for NON-HYPERBOLIC fixed points where linearization fails.

## 2.12 A Worked Stability Analysis

P: Classify the fixed points of $\dot{x} = y, \dot{y} = -x - y$ (damped harmonic oscillator).
S:
**IDENTIFY**: 2D linear system. Write as $\dot{\mathbf{x}} = A \mathbf{x}$ with $A = \begin{pmatrix} 0 & 1 \\ -1 & -1 \end{pmatrix}$.

**PLAN**: Compute $\tau, \Delta$; classify; compute eigenvalues.

**EXECUTE**:
- $\tau = 0 + (-1) = -1$.
- $\Delta = 0 \cdot (-1) - 1 \cdot (-1) = 1$.
- Discriminant: $\tau^2 - 4\Delta = 1 - 4 = -3 < 0$ → complex eigenvalues.
- Since $\tau < 0$ and $\Delta > 0$: STABLE SPIRAL.
- Eigenvalues: $\lambda = \tfrac{-1 \pm \sqrt{-3}}{2} = -\tfrac{1}{2} \pm i\tfrac{\sqrt{3}}{2}$.
- Magnitude: $e^{-t/2}$ (decays). Angular frequency: $\sqrt{3}/2$.

**EVALUATE**: Origin is a STABLE SPIRAL: trajectories spiral inward, completing rotations at angular speed $\sqrt{3}/2$, with amplitude shrinking as $e^{-t/2}$. Matches physical intuition — damped oscillation. If damping coefficient were increased: $\dot{y} = -x - 2y$ would give $\tau = -2, \Delta = 1, \tau^2 - 4\Delta = 0$: CRITICAL DAMPING (degenerate node). Further: $\dot{y} = -x - 3y$ gives $\tau^2 - 4\Delta = 5 > 0$: OVERDAMPED NODE (no oscillation). The trace-determinant diagram cleanly delineates all three regimes.
