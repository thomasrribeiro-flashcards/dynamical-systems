+++
order = 3
subject = "Mathematics"
tags = ["math", "dynamical-systems", "bifurcation", "saddle-node", "transcritical", "pitchfork", "normal-form"]
+++

# Dynamical Systems — One-Dimensional Bifurcations

## 3.1 What a Bifurcation Is

Q: What is a [bifurcation]?
A: A QUALITATIVE CHANGE in the phase portrait as a parameter crosses a critical value. Fixed points can appear, disappear, exchange stability, or split. Bifurcations mark TRANSITIONS between regimes of behavior — essential for understanding systems whose parameters change (temperature in climate, drug dosage in medicine, coupling in networks). The parameter value at which bifurcation occurs is the [bifurcation point].

Q: Why is BIFURCATION ANALYSIS central to applied dynamical systems?
A: Because real systems have TUNABLE PARAMETERS (temperature, concentration, connectivity); the interesting questions are: WHERE does behavior switch from steady state to oscillation? WHERE does chaos appear? Bifurcation theory identifies these thresholds cleanly. Also: engineering design seeks systems ROBUST to parameter variations — i.e., AVOIDING bifurcations near operating points. Medicine and ecology exploit bifurcations for desired state changes.

## 3.2 The Three Basic 1D Bifurcations

Q: Name the THREE canonical 1D bifurcations.
A: (1) [SADDLE-NODE] (fold): two fixed points collide and annihilate. (2) [TRANSCRITICAL]: two fixed points exchange stability as they pass through each other. (3) [PITCHFORK]: one fixed point becomes unstable and spawns two new stable ones (or vice versa). These three are the CODIMENSION-ONE bifurcations in 1D — the only generic ways a 1D system can qualitatively change with one parameter.

## 3.3 Saddle-Node Bifurcation

Q: Describe the [saddle-node bifurcation].
A: Normal form: $\dot{x} = r + x^2$ (for the simplest case) or $\dot{x} = r - x^2$. For $r < 0$ (one form): two fixed points at $x = \pm\sqrt{-r}$ (or $\pm\sqrt{r}$). At $r = 0$: they COLLIDE at $x = 0$ — a single DEGENERATE fixed point. For $r > 0$: NO fixed points remain. This is the GENERIC way fixed points are CREATED or DESTROYED as a parameter varies.

Q: What's the BIFURCATION DIAGRAM for saddle-node?
A: Plot fixed points vs parameter $r$. For $\dot{x} = r - x^2$: two branches $x = \pm\sqrt{r}$ for $r > 0$, meeting at a PARABOLA opening right (with cusp at $r = 0$). Upper branch $x = +\sqrt{r}$: STABLE. Lower branch: UNSTABLE. For $r < 0$: no fixed points, $\dot{x} < 0$ everywhere — trajectories go to $-\infty$. The diagram is the signature "fold" shape.

## 3.4 Transcritical Bifurcation

Q: Describe the [transcritical bifurcation].
A: Normal form: $\dot{x} = rx - x^2$. Fixed points at $x = 0$ and $x = r$. For $r < 0$: $x = 0$ stable, $x = r$ (negative) unstable. For $r > 0$: $x = 0$ unstable, $x = r$ (positive) stable. The two fixed points EXCHANGE STABILITY as $r$ crosses 0. Unlike saddle-node, NEITHER fixed point disappears; they cross and swap roles. Arises when one fixed point is GUARANTEED by the problem (e.g., $x = 0$ always a solution because $0 \cdot f(0) = 0$).

## 3.5 Pitchfork Bifurcation: Supercritical

Q: Describe the [supercritical pitchfork bifurcation].
A: Normal form: $\dot{x} = rx - x^3$. Fixed points: $x = 0$ always; and $x = \pm\sqrt{r}$ for $r > 0$. For $r < 0$: single fixed point at $x = 0$, STABLE. For $r > 0$: $x = 0$ becomes UNSTABLE, two new stable fixed points at $\pm\sqrt{r}$. Bifurcation diagram: "pitchfork" opening to the right. Models: spontaneous symmetry breaking, buckling beam, second-order phase transitions.

## 3.6 Pitchfork: Subcritical

Q: Describe the [subcritical pitchfork bifurcation].
A: Normal form: $\dot{x} = rx + x^3$. For $r < 0$: stable $x = 0$ and two UNSTABLE fixed points at $\pm\sqrt{-r}$. For $r > 0$: $x = 0$ unstable, no nearby fixed points — trajectories go to $\pm\infty$ (or to far-away stable states). Subcritical pitchforks are DANGEROUS: a hard loss of stability. Usually a HIGHER-ORDER TERM like $-x^5$ must be added to give nearby stable states for $r > 0$, creating a HYSTERESIS loop — system jumps abruptly between states.

## 3.7 Hysteresis and Bistability

Q: What is [hysteresis], and how does it arise from bifurcations?
A: The state depending on the HISTORY of parameter changes, not just the current value. In subcritical pitchfork with stabilizing higher-order term: as $r$ increases past critical, system jumps DOWN to a far-away stable state. To return, you must decrease $r$ to ANOTHER critical value (SADDLE-NODE) below the original — a hysteresis loop. Appears in: magnetism (B-H curves), elastic buckling, laser bistability, cell-fate switches in biology. ROBUST MEMORY through nonlinear dynamics.

Q: What is [bistability], and why is it important?
A: Two coexisting stable fixed points separated by an unstable one. Small perturbations stay near the starting attractor; large perturbations switch to the other. Forms the basis of BINARY MEMORY in biology (genetic switches like the $\lambda$-phage lysis/lysogeny, bacterial chemotaxis decisions). Subcritical pitchfork creates bistability from a single-stable state via bifurcation.

## 3.8 Normal Forms

Q: What is a [normal form] of a bifurcation?
A: The SIMPLEST polynomial equation exhibiting a given bifurcation — all higher-order terms removed by smooth coordinate changes. Saddle-node normal form: $\dot{x} = r - x^2$. Transcritical: $\dot{x} = rx - x^2$. Pitchfork: $\dot{x} = rx - x^3$. ANY system with the same bifurcation can be LOCALLY reduced to its normal form near the bifurcation point. Unifies: if you can identify which normal form applies, you know the full local behavior.

Q: How do you IDENTIFY which bifurcation a system undergoes?
A: At the critical point $x^*$ with parameter $r^*$: (1) Check $f(x^*, r^*) = 0$ and $f_x(x^*, r^*) = 0$ (fixed point with zero derivative). (2) If $f_r(x^*, r^*) \neq 0$ AND $f_{xx}(x^*, r^*) \neq 0$: SADDLE-NODE. (3) If $f_r = 0$ but other mixed partials nonzero: TRANSCRITICAL or PITCHFORK (further conditions distinguish). Guided by the IMPLICIT FUNCTION THEOREM's failure modes.

## 3.9 Imperfect Bifurcations

Q: What happens when the SYMMETRY of a pitchfork is BROKEN?
A: Adding an asymmetry parameter $h$: $\dot{x} = h + rx - x^3$. The sharp pitchfork is DESTROYED — replaced by a CONTINUOUS connected branch plus a SEPARATE pair (saddle-node). For $h \neq 0$: no sharp transition, but rapid (nearly-pitchfork-like) change near $r = 0$. Real systems almost never have perfect symmetry; [imperfect bifurcation] analysis accounts for small asymmetries. Classical catastrophe theory (Thom) treats these.

## 3.10 Stability via Derivative

Q: How do you determine LINEAR STABILITY of a 1D fixed point $x^*$?
A: Linearize: $\dot{u} = f'(x^*) u$ where $u = x - x^*$. Stability governed by sign of $f'(x^*)$: (1) $f'(x^*) < 0$: STABLE (perturbations decay). (2) $f'(x^*) > 0$: UNSTABLE. (3) $f'(x^*) = 0$: bifurcation, linearization INCONCLUSIVE — examine higher derivatives or apply normal-form classification.

## 3.11 Bifurcations in Biology

Q: Give examples of BIFURCATIONS in biological models.
A: (1) [Insect outbreak (spruce budworm)]: saddle-node bifurcations create hysteresis between low and high population states, explaining sudden outbreaks. (2) [Genetic switches]: bistability (two pitchforks) enables cells to commit to differentiation pathways. (3) [Neuron firing]: saddle-node bifurcation on a limit cycle (SNIC) explains onset of spiking in Type I neurons. (4) [Epidemic threshold]: transcritical at $R_0 = 1$ — disease-free vs endemic equilibria exchange stability.

## 3.12 A Worked Bifurcation Analysis

P: Analyze the bifurcations of $\dot{x} = r x - x^3$ as $r$ varies through 0.
S:
**IDENTIFY**: Supercritical pitchfork normal form.

**PLAN**: Find fixed points; classify stability; plot diagram.

**EXECUTE**:
Fixed points: $x(r - x^2) = 0 \Rightarrow x = 0$ or $x = \pm\sqrt{r}$ (real when $r \geq 0$).

Stability via $f'(x) = r - 3x^2$:
- $x = 0$: $f'(0) = r$. STABLE for $r < 0$, UNSTABLE for $r > 0$.
- $x = \pm\sqrt{r}$ (for $r > 0$): $f'(\pm\sqrt{r}) = r - 3r = -2r < 0$. STABLE.

Regimes:
- $r < 0$: single fixed point $x = 0$, stable. All trajectories converge to 0.
- $r = 0$: degenerate; $f'(0) = 0$. Bifurcation point.
- $r > 0$: $x = 0$ unstable (repels); $x = \pm\sqrt{r}$ stable. Trajectories go to $+\sqrt{r}$ or $-\sqrt{r}$ depending on sign of $x(0)$.

Bifurcation diagram: pitchfork opening rightward from origin. Horizontal axis $r$; vertical $x^*$. Branch $x = 0$ solid (stable) for $r < 0$, dashed (unstable) for $r > 0$. Branches $\pm\sqrt{r}$ solid (stable) for $r > 0$.

**EVALUATE**: Classic SUPERCRITICAL PITCHFORK — the prototype of SPONTANEOUS SYMMETRY BREAKING. As $r$ crosses 0, the $\mathbb{Z}_2$ symmetry ($x \to -x$) of the equation is preserved but the SOLUTION "picks" one of $\pm\sqrt{r}$ based on initial conditions. Physical realizations: (a) BUCKLING: compressing a column; past critical load, it buckles left or right. (b) LASER THRESHOLD: below pumping threshold, no lasing; above, two symmetric modes oscillate. (c) FERROMAGNETIC TRANSITION below Curie point: magnetization picks up or down. Symmetry-breaking is pervasive in physics — this normal form captures its mathematical essence.
