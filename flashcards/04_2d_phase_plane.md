+++
order = 4
subject = "Mathematics"
tags = ["math", "dynamical-systems", "phase-plane", "nullclines", "conservative", "reversible", "hamiltonian"]
+++

# Dynamical Systems — Two-Dimensional Flows and the Phase Plane

## 4.1 Why 2D Is Special

Q: What makes 2D flows QUALITATIVELY different from 1D and 3D?
A: (1) 1D flows are trivial: trajectories move monotonically between fixed points — NO oscillations (can't turn around without crossing). (2) 2D flows CAN oscillate (limit cycles) but CANNOT be chaotic — the plane is too constrained (Poincaré-Bendixson). (3) 3D flows can exhibit chaos. 2D is the RICHEST setting for analytic techniques: phase plane methods, nullclines, index theory — while remaining fully classifiable.

## 4.2 Nullclines

C: The [$x$-nullcline] is the curve where $\dot{x} = 0$; the [$y$-nullcline] is where $\dot{y} = 0$. FIXED POINTS are intersections of both nullclines.

Q: Why are NULLCLINES the starting tool for sketching a 2D phase portrait?
A: Because they divide the plane into REGIONS where each of $\dot{x}, \dot{y}$ has a definite sign — you can draw direction arrows in each region. Nullclines themselves show where the flow is purely horizontal ($\dot{y} = 0$) or vertical ($\dot{x} = 0$). Fixed points and nullcline intersections locate all equilibria. Combined with local linearization, this gives the global phase portrait skeleton.

## 4.3 Trajectories in the Phase Plane

Q: What are the possible LONG-TERM FATES of a 2D trajectory?
A: Settle to a FIXED POINT, approach a LIMIT CYCLE (closed periodic orbit), or escape to INFINITY (with special trajectories lying on heteroclinic/homoclinic connecting orbits). In 2D, these ARE the only possibilities — NO chaos, NO dense complicated wandering. Poincaré-Bendixson constrains the plane.

## 4.4 Conservative Systems

C: A system $\dot{\mathbf{x}} = f(\mathbf{x})$ is [conservative] if there exists a non-constant function $E(\mathbf{x})$ (the "energy") that is CONSTANT along trajectories: $\dot{E} = \nabla E \cdot f = 0$.

Q: What constrains the phase portrait of a CONSERVATIVE 2D system?
A: Trajectories lie on LEVEL CURVES of $E$. Centers and saddles are possible; ATTRACTORS (asymptotically stable fixed points) are IMPOSSIBLE — would require $E$ to decrease. NO limit cycles of the "attracting" kind. Generic conservative behavior: concentric closed orbits (centers) separated by saddle-connected separatrices. Example: undamped pendulum, frictionless particle in a potential well, Lotka-Volterra.

Q: Why can't a conservative system have an asymptotically STABLE fixed point?
A: Because asymptotic stability requires trajectories to approach the fixed point as $t \to \infty$, meaning $E$ must DECREASE along them. But $E$ is conserved — $\dot{E} = 0$ — so $E$ can't change. Hence all trajectories stay on constant-$E$ level sets, never crossing them to reach a single point. CENTERS (Lyapunov stable but not asymptotic) are the best you can do. Energy dissipation breaks conservativeness and ENABLES attractors.

## 4.5 Reversible Systems

C: A system is [reversible] under a reflection $R$ (involution: $R^2 = I$) if the dynamics LOOK THE SAME when time is reversed combined with $R$: $R \circ \phi_t = \phi_{-t} \circ R$.

Q: What does REVERSIBILITY imply for phase portraits?
A: Similar restrictions to conservative: typical examples are MECHANICAL systems where $(x, v) \to (x, -v)$ under time reversal. Trajectories symmetric under $R$; cycles and symmetric orbits abound. Attractors on the symmetric subspace are impossible. Mechanical systems WITHOUT friction are reversible; dissipative systems typically are not. Many physical models (lossless wave equations, undamped oscillators) are reversible.

## 4.6 Hamiltonian Systems

C: A [Hamiltonian system] on $\mathbb{R}^{2n}$ has the form $\dot{q}_i = \partial H / \partial p_i, \dot{p}_i = -\partial H / \partial q_i$ for a scalar "Hamiltonian" $H(q, p)$.

Q: What special properties do HAMILTONIAN systems have?
A: (1) $H$ is CONSERVED — energy conservation. (2) PHASE-SPACE VOLUME is preserved (Liouville's theorem): trajectories don't compress or expand regions. (3) FIXED POINTS are CENTERS or SADDLES — no spirals or nodes (no dissipation). (4) Rich invariants — integrability, KAM tori, action-angle variables. All of classical mechanics (Newton, orbits, electromagnetism) is Hamiltonian. Symplectic structure is preserved by Hamiltonian flows.

## 4.7 Lyapunov Functions Revisited

Q: What CONDITIONS must a Lyapunov function $V(x, y)$ satisfy to certify stability of a fixed point $(x^*, y^*)$?
A: $V(x^*, y^*) = 0$; $V > 0$ elsewhere near the fixed point; and $\dot{V} \leq 0$ along trajectories ($\dot{V} < 0$ strict for asymptotic stability). Intuition: $V$ is a "height function" trajectories descend. Challenge: finding $V$ is often AN ART — no general algorithm. Quadratic forms ($V = ax^2 + by^2$) are common first guesses.

## 4.8 Limit Sets

C: The [$\omega$-limit set] of a trajectory $x(t)$ is the set of all accumulation points as $t \to +\infty$. Similarly, the [$\alpha$-limit set] is for $t \to -\infty$.

Q: What types of $\omega$-limit sets can occur in 2D?
A: By Poincaré-Bendixson (chapter 5): in BOUNDED regions of 2D phase space with no equilibria, $\omega$-limit sets are: (1) a single FIXED POINT; (2) a PERIODIC ORBIT (limit cycle); (3) a set of fixed points connected by heteroclinic/homoclinic orbits. NO strange attractors in 2D. Severely limits possible long-term behavior — why 2D is "tame."

## 4.9 Gradient Systems

C: A [gradient system] is $\dot{\mathbf{x}} = -\nabla V(\mathbf{x})$ for some potential $V$.

Q: What restrictions apply to GRADIENT systems?
A: $V$ always DECREASES along trajectories: $\dot{V} = \nabla V \cdot \dot{\mathbf{x}} = -|\nabla V|^2 \leq 0$. Consequences: (1) NO CYCLES (would require $V$ to return to starting value, impossible for strictly decreasing $V$). (2) All $\omega$-limit sets are fixed points (local minima of $V$). (3) EIGENVALUES of the Jacobian at fixed points are REAL (no spirals). Gradient descent in optimization is a gradient system — explains monotonic convergence and no cycling.

## 4.10 Index Theory

Q: What is the [Poincaré index] of a closed curve in a 2D vector field?
A: An integer counting how many times the vector field $f$ rotates as you traverse the curve counterclockwise once. For a curve enclosing fixed points: NODE = $+1$, SPIRAL = $+1$, CENTER = $+1$, SADDLE = $-1$, no fixed point = $0$. Curves around a single fixed point: index = local index of that fixed point.

Q: Use index theory to prove: a closed orbit in 2D MUST enclose at least one fixed point.
A: A closed orbit has index $+1$ (vector field parallel to orbit rotates once). By additivity, sum of indices of enclosed fixed points = $+1$. If no fixed points, sum = $0$ — contradiction. Hence at least one fixed point must lie inside. Useful for RULING OUT limit cycles: if all candidate enclosed regions contain no fixed points (e.g., simply connected region avoiding equilibria), no cycle possible there.

## 4.11 Dulac's Criterion

Q: State [Dulac's criterion] for ruling out limit cycles.
A: If there's a smooth function $g(x, y) > 0$ in a simply connected region $R$ such that $\nabla \cdot (g \cdot f)$ has a DEFINITE SIGN in $R$: NO CLOSED ORBITS lie entirely in $R$. Proof via divergence theorem: integrating $\nabla \cdot (gf)$ over the disk bounded by a putative cycle yields a contradiction. Powerful negative tool; combined with Poincaré-Bendixson (which gives positive existence), frames the cycle question.

## 4.12 A Worked Phase Plane Sketch

P: Sketch the phase portrait of $\dot{x} = y, \dot{y} = x - x^3$ (undamped Duffing oscillator).
S:
**IDENTIFY**: Conservative 2D system (no damping). Energy: $E = \frac{1}{2} y^2 - \frac{1}{2} x^2 + \frac{1}{4} x^4$.

**PLAN**: Verify $\dot{E} = 0$; find fixed points; classify; sketch level curves.

**EXECUTE**:
Fixed points: $y = 0, x - x^3 = x(1 - x^2) = 0 \Rightarrow x = 0, \pm 1$.
Jacobian: $J = \begin{pmatrix} 0 & 1 \\ 1 - 3x^2 & 0 \end{pmatrix}$.
- At $(0, 0)$: $J = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix}$, eigenvalues $\pm 1$ — SADDLE.
- At $(\pm 1, 0)$: $J = \begin{pmatrix} 0 & 1 \\ -2 & 0 \end{pmatrix}$, eigenvalues $\pm i\sqrt{2}$ — CENTER.

Energy: $\dot{E} = y \dot{y} - x \dot{x} + x^3 \dot{x} = y(x - x^3) - xy + x^3 y = 0$ ✓ (conserved).

Phase portrait: closed orbits around each center $(\pm 1, 0)$, separated by a FIGURE-EIGHT homoclinic orbit through the saddle at origin. Inside each "lobe": oscillations around one minimum of the potential $V(x) = -\frac{1}{2} x^2 + \frac{1}{4} x^4$. Outside: closed orbits encircling BOTH wells (if energy is high enough) — particle bounces back and forth between the two wells.

**EVALUATE**: Classic DOUBLE-WELL POTENTIAL. Low energy: particle confined to one well (two sets of small closed orbits around $\pm 1$). Critical energy $E = 0$: homoclinic orbit through the saddle, forming the figure-8 separatrix. High energy: large orbits enclosing both wells. Adding DAMPING ($\dot{y} = x - x^3 - \gamma y$): centers become stable spirals, orbits spiral into one of the wells (depending on basin). Driven damped version: the celebrated DUFFING oscillator, a prototype for chaos in forced nonlinear systems.
