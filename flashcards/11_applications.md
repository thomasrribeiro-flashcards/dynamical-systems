+++
order = 11
subject = "mathematics"
tags = ["math", "dynamical-systems", "biology", "climate", "neuroscience", "ecology", "applications"]
+++

# Dynamical Systems — Applications in Biology, Climate, and Neuroscience

## 11.1 Why Applications

Q: Why are dynamical systems WIDELY APPLICABLE?
A: Because ANY system that evolves in time — populations, chemical concentrations, neurons, atmospheric variables, stock prices, disease spread — is a candidate. The SAME MATHEMATICAL STRUCTURES (fixed points, limit cycles, bifurcations, chaos) appear across fields, allowing cross-pollination: insights from neuroscience inform climate modeling; fluid chaos illuminates population dynamics. Dynamical systems provides a UNIVERSAL LANGUAGE for time-evolving phenomena.

## 11.2 Predator-Prey Systems

Q: Write the [Lotka-Volterra equations].
A: $\dot{x} = \alpha x - \beta x y$ (prey population grows naturally, eaten by predators), $\dot{y} = \delta xy - \gamma y$ (predator population sustained by prey, dies naturally). Parameters: $\alpha$ prey birth rate, $\beta$ predation rate, $\delta$ predator efficiency, $\gamma$ predator death rate. Classic model of ecological oscillations (Lotka 1910, Volterra 1920s).

Q: What's the dynamical structure of LOTKA-VOLTERRA?
A: Two fixed points: $(0, 0)$ (extinction) and $(\gamma/\delta, \alpha/\beta)$ (coexistence). Coexistence is a CENTER — closed orbits in $(x, y)$ plane. Conserved quantity: $V = \delta x - \gamma \ln x + \beta y - \alpha \ln y$. Orbits are OSCILLATIONS with prey peaking before predator peaks (predators lag). Fragile: adding any perturbation destroys the cycles (center → spiral). More realistic MacArthur models (with carrying capacity) have stable equilibria or limit cycles.

## 11.3 Epidemic Models

Q: Describe the [SIR model] of epidemics.
A: $\dot{S} = -\beta S I, \dot{I} = \beta S I - \gamma I, \dot{R} = \gamma I$. $S$ = susceptible, $I$ = infected, $R$ = recovered (immune). Parameters: $\beta$ transmission rate, $\gamma$ recovery rate. $R_0 = \beta S_0 / \gamma$ = BASIC REPRODUCTION NUMBER. Epidemic grows ($I$ increases) iff $R_0 > 1$ — a TRANSCRITICAL BIFURCATION threshold. Below 1: disease dies out. Above 1: major outbreak. Basis of every infectious disease model (COVID, flu, measles).

Q: What CONTROL STRATEGIES follow from the SIR model?
A: Reduce $R_0$ below 1 by: (1) Vaccination: fraction $1 - 1/R_0$ immunized prevents outbreaks ("herd immunity threshold"). (2) Lowering $\beta$: masks, social distancing, lockdowns. (3) Raising $\gamma$: early treatment, isolation. Each maps to a specific modeling parameter. During COVID-19: $R_0 \approx 2.5$ → need $\sim 60\%$ immunity. Pharmaceutical and non-pharmaceutical interventions correspond to different bifurcation-control actions.

## 11.4 Neural Dynamics

Q: Describe the [FitzHugh-Nagumo model] of a neuron.
A: Simplified Hodgkin-Huxley: $\dot{v} = v - v^3/3 - w + I, \dot{w} = \epsilon(v + a - bw)$. $v$ = membrane potential, $w$ = recovery variable, $I$ = input current. For $I$ below threshold: stable fixed point (rest). Above threshold: LIMIT CYCLE (repetitive firing). Transition: Hopf bifurcation or SNIC depending on parameters. Captures action potentials, refractory period, excitability with just 2 variables. Cornerstone of theoretical neuroscience.

Q: Why does the NEURON have a THRESHOLD?
A: Because the phase portrait has two distinct domains separated by an UNSTABLE MANIFOLD. Small perturbations from rest decay back; large perturbations cross the manifold, trigger a full action potential, return to rest via the recovery variable. This is a dynamical-systems signature of EXCITABILITY — analogous to an unstable saddle organizing an "all-or-nothing" response. Same mechanism in: Van der Pol relaxation oscillator, cardiac cells, certain chemical clocks.

## 11.5 Climate Dynamics

Q: What is [Lorenz's 3-equation weather model] and why it matters?
A: The Lorenz (1963) equations (Chapter 9) arose from truncating Navier-Stokes equations for atmospheric convection. Revealed: EVEN DRASTICALLY SIMPLIFIED weather models are CHAOTIC. Tiny measurement errors → totally different trajectories. Proved that PERFECT LONG-TERM WEATHER PREDICTION is IMPOSSIBLE — fundamental limit, not a matter of technology. Led to PROBABILISTIC FORECASTING: ensemble methods running many slightly perturbed simulations.

## 11.6 El Niño and Climate Oscillations

Q: How does DYNAMICAL SYSTEMS explain [El Niño-Southern Oscillation (ENSO)]?
A: A coupled ocean-atmosphere oscillator. Simplified models (Cane-Zebiak, delayed oscillator) reveal: El Niño events are approximately PERIODIC limit cycles in the climate system. Positive feedback (Bjerknes) plus delayed negative feedback (equatorial waves) create oscillations of period $\sim 3-7$ years. Understanding via DELAY DIFFERENTIAL EQUATIONS; bifurcation analysis reveals ENSO's origin as a Hopf bifurcation in coupled dynamics.

## 11.7 Ecosystem Tipping Points

Q: What is a [tipping point] in ecology?
A: A PARAMETER threshold beyond which a system switches abruptly from one stable state to a qualitatively different one — a SADDLE-NODE BIFURCATION. Examples: (1) [Lake eutrophication]: clear lake → turbid/algae-dominated past nutrient threshold. (2) [Amazon rainforest]: potential collapse to savanna past deforestation threshold. (3) [Coral reef]: coral-dominant → algae-dominant past stress threshold. (4) [Arctic sea ice]: partial → complete loss. Warning signals: "critical slowing down" — recovery from perturbations slows near the bifurcation.

Q: What are [early warning signals] for approaching tipping points?
A: Near a bifurcation, the system's response to perturbations shifts: (1) [Critical slowing down]: recovery rate $\to 0$. (2) [Increased variance]: fluctuations grow. (3) [Rising autocorrelation]: state becomes more "memory-full." (4) [Skewness changes]: distribution of fluctuations becomes asymmetric. Detectable from time-series data BEFORE the tipping. Applied to: ancient climate records (paleoclimate transitions), financial markets, medical symptoms.

## 11.8 Epilepsy and Brain Dynamics

Q: How can DYNAMICAL SYSTEMS frame EPILEPTIC SEIZURES?
A: Epilepsy = ABNORMAL SYNCHRONIZATION of neural populations. Normal brain activity = asynchronous, near-chaotic firing. Seizures = transitions to highly synchronized, often oscillatory, dynamics — a BIFURCATION into a different attractor (limit cycle or chaotic synchronous state). Early-warning signals (critical slowing) precede seizure onset, enabling closed-loop intervention. Neural models (Wilson-Cowan, Jansen-Rit) simulate this dynamically.

## 11.9 Cardiac Dynamics and Arrhythmias

Q: How does chaos theory APPLY to CARDIAC ARRHYTHMIAS?
A: The heart is a COMPLEX NONLINEAR OSCILLATOR. Normal rhythm = stable limit cycle. Arrhythmias = (1) fibrillation (spatiotemporal chaos), (2) tachycardia (altered limit cycle period), (3) period-doubling bifurcations leading to complex rhythms. Defibrillators exploit this: strong electrical pulse RESETS the cardiac attractor, restoring the stable normal rhythm. Period-doubling cascade in cardiac cells (Guevara-Glass 1981) precedes ventricular fibrillation — a chaotic signal used in clinical monitoring.

## 11.10 Biological Clocks

Q: How do CIRCADIAN CLOCKS exemplify limit-cycle dynamics?
A: Near-24-hour rhythms in gene expression (PER, TIM, CRY, CLK, BMAL1 in vertebrates) form NEGATIVE-FEEDBACK LOOPS with DELAYS. These loops generate STABLE LIMIT CYCLES (oscillators). External light input ENTRAINS the cycle via PHASE RESETTING — well-described by circle-map dynamics and Arnold tongues. Desynchronization (jet lag, shift work) corresponds to exiting a tongue. Mathematical understanding informed light-therapy treatments and chronobiology.

## 11.11 Population Dynamics in Ecology

Q: What population model adds a carrying capacity $K$ to bounded growth, and what is its equation?
A: Logistic growth: $\dot{N} = rN(1 - N/K)$.

Q: What is the ALLEE EFFECT in population dynamics?
A: Small populations crash (e.g. difficulty finding mates) — a saddle-node below which extinction is inevitable.

Q: What type of population model uses reaction-diffusion PDEs, and what phenomenon does it produce?
A: Spatial models — producing traveling waves (disease spread, invasive species).

Q: In ecology, what is a METAPOPULATION?
A: A network of connected habitat patches, prone to extinction cascades.

Q: What complex dynamics do multi-species FOOD WEB models exhibit?
A: Chaos, multi-stability, and regime shifts.

## 11.12 A Worked Application

P: Analyze the SIR epidemic model: for $\beta = 0.3, \gamma = 0.1$ and initial $S_0 = 1000, I_0 = 1, R_0 = 0$, compute $R_0$ and determine whether an epidemic occurs.
S:
**IDENTIFY**: SIR model with given parameters. Threshold analysis.

**PLAN**: Compute basic reproduction number $R_0 = \beta S_0 / \gamma$; compare to 1.

**EXECUTE**:
$R_0 = \beta S_0 / \gamma = 0.3 \cdot 1000 / 0.1 = 3000$.

$R_0 \gg 1$ → epidemic DOES occur.

Dynamics:
- Initially: $\dot{I}(0) = \beta S_0 I_0 - \gamma I_0 = 0.3 \cdot 1000 \cdot 1 - 0.1 \cdot 1 = 299.9 > 0$. Infection grows.
- Peak: $\dot{I} = 0 \Rightarrow \beta S I = \gamma I \Rightarrow S = \gamma/\beta = 1/3 \approx 0.33$ (fraction). With population 1001 total: $S_{\text{peak}} \approx 334$.
- Final size: solve $\ln(S_\infty / S_0) = -R_0 (1 - S_\infty / S_0) / (1 - I_0/N)$. For $R_0 = 3000 \cdot \ldots$ — but wait, using effective $\tilde{R}_0 = \beta N / \gamma$: here really we normalize. The useful $R_0$ is population-normalized: $R_0 = \beta \langle \text{contacts}\rangle/\gamma$, NOT $\beta S_0 / \gamma$.

Recomputing: typical normalization uses $\beta$ as per-capita contact rate times prob-of-transmission, and the effective $R_0 = \beta / \gamma$ at full susceptible population. With $\beta = 0.3, \gamma = 0.1$: $R_0 = 3$. Epidemic occurs since $R_0 > 1$. Herd immunity threshold: $1 - 1/R_0 = 2/3 \approx 67\%$. Final fraction susceptible $S_\infty \approx 0.059$ (6%); $\sim 94\%$ of population infected over the epidemic.

**EVALUATE**: Classic textbook epidemic: $R_0 = 3$ → ~94% cumulative infection without intervention. Peak infection: $\sim 30\%$ of population infected simultaneously. Public health: vaccinate $\sim 67\%$ to prevent epidemic. Actual viruses: measles $R_0 \approx 12$–18 (need ~95% vaccination), COVID-19 $R_0 \approx 2$–4, influenza $R_0 \approx 1.3$. Dynamical analysis directly informs public-health policy.
