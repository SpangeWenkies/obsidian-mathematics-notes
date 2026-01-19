---
title: Lecture 1 — Dirichlet forms ↔ Markov processes (the dictionary)
course: Analytical Markov chains via Dirichlet forms
lecture: 1
tags:
  - markov-chains
  - dirichlet-forms
  - semigroups
  - generators
  - stochastic-processes
  - "#functional-analysis"
  - "#stochastic-calculus"
---

# Lecture 1 — Dirichlet forms ↔ Markov processes (the dictionary)

## Big picture
**General idea:** build a *property-translation dictionary* (1-to-1 correspondance) between

- **Functional analysis**: quadratic/energy forms, generators, semigroups  
and
- **Stochastic analysis**: Markov processes, transition kernels, path properties.

### Examples of “dictionary entries”
- **Symmetry on** $L^2(m)$  $\Longleftrightarrow$  **$m$-reversibility** of the Markov process.
- **Conservativeness**  $\Longleftrightarrow$  the process **never leaves the state space / does not die**.
  - (There is an abstract definition on the functional-analytic side.)
- **Irreducibility**  $\Longleftrightarrow$  **ergodicity**, i.e. only one connected component:
  - “we can go everywhere from each starting point”.
- **Strong locality (Dirichlet form)**  $\Longleftrightarrow$  **diffusion** (sample paths continuous a.s.).
  - Note: strong locality is phrased without much topology, whereas continuity of paths involves topology.

### Why this is useful (to each other)
- Functional analysis often makes **existence** proofs easier/cleaner.
- Stochastic analysis often provides **nice probabilistic properties/interpretations**.

---

## Programme of the theory (objects and arrows)

Fix a Hilbert space
$$
L^2(m)=L^2(S,\Sigma,m).
$$

We want to relate the following objects:

### 1) Energy functional / Dirichlet form $\mathcal E$
A (typically) **quadratic** object:
- “always quadratic, hence symmetric”
- lower semicontinuous
- satisfies the parallelogram identity
- induces a seminorm via $\mathcal E(u,u)$

### 2) Generator $L$
(For the symmetric case in your notes:)
- nonnegative
- self-adjoint

### 3) Semigroup $T:=(T_t)_{t\ge 0}$
- acts on $L^2(m)$
- strongly continuous
- contraction
- semigroup property $T_{t} \circ T_{s}=T_{t+s}$

### 4) Kernel / transition probabilities $p_t(x,dy)$
Measure-valued kernel:
$$
p_t: x \mapsto p_t(x,\cdot), \qquad p_t(x,dy)\ \text{a measure in } y.
$$
and the semigroup can be written as
$$
(T_t f)(x)=\int_{S} f(y)\,p_t(x,dy).
$$

### The “connecting theorems” (as sketched)
- $\mathcal E \to L$: **Lax–Milgram theorem**
- $L \rightarrow T$: **Mille–Yoshida theorem**
- $T \rightarrow p_t$: **Dunford–Pettis representation** 
- a kernel can be written from the Markov process definition, so no theorem from MP
- a Markov process can be written defined by the kernel, so no theorem to go to MP

---

## Markov processes and semigroups

### Markov process (setting)
A **time-homogeneous** Markov process $X$ with
- $m$-symmetry
- state space $S$
- transition kernels $p_t$

## Dictionary will turn out to work in reverse

- under conditions, **forms ↔ generators ↔ semigroups ↔ kernels ↔ Markov processes**.

### Semigroup via kernel (Dunford-Pettis reversed)
The associated semigroup is
$$
(T_t f)(x):=\mathbb E_x[f(X_t)].
$$
This is a semigroup because the **Markov property implies the semigroup property**:
$$
T_{s+t}=T_{s}\circ T_t.
$$

### Generator via semigroup (Mille–Yosida reversed)
$$
(Lf)(x):=dt|_{t=0}(T_t f)(x).
$$
- here $dt|_{t=0}$ is the infinitesimal change in $t$ and then evaluated at $t=0$
	- is this the same as $\lim_{ t \to 0 }$ ?
---

## Example: Brownian motion on $\mathbb R^d$

### Simple example with continuous paths
$W^{1,2}(\mathbb{R}^d)$-Sobolev semi-norm defines the energy form:
$$
\int_{\mathbb R^d}|\nabla u|^2\,d\mathrm{Leb}^d \;=:\; \mathcal E(u,u)=:\mathcal E(u)
$$
integrated to the Lebesgue measure on $\mathbb{R}^d$.

Bilinear version via polarization identity:
$$
\mathcal E(u,v)=\int_{\mathbb R^d}\nabla u\cdot \nabla v\,d\mathrm{Leb}^d.
$$

Integration by parts + Lax-Milgram theorem will give that there exists a generator $L$ s.t. :
$$
\mathcal E(u,v)=\langle u,\;Lv\rangle_{L^2(m)},
$$
and the generator is (up to convention) the **negative Laplacian**:
$$
L = -\Delta:=\nabla ^2,
$$
which is the gradient of the gradient.

#### Heat semigroup and kernel
We get the hear semigroup:
$$
T_t = e^{t(-\Delta)}.
$$

By using the Neumann series expansion (as written):
$$
e^{t(-\Delta)}=\sum_{n\ge 0}\frac{t^n}{n!}(-\Delta)^n.
$$

From the semigroup we get the heat kernel by using Fourier transform methods:
$$
p_t(x,dy)=\frac{1}{(4\pi t)^{d/2}}
\exp\!\left(-\frac{|x-y|^2}{4t}\right)\,d\mathrm{Leb}^d(y).
$$

Then Brownian motion is the Markov process whose transition kernel is the heat kernel.

“no reason it should be continuous” — i.e. a general Markov process need not have continuous paths (contrast with diffusions).

---

## Example: Ornstein–Uhlenbeck process (Gaussian reference measure)

Example to show that construction could be sensitive to very small changes

Let $\gamma_d$ be the standard Gaussian measure on $\mathbb R^d$.

Energy:
$$
\mathcal E(u)=\int_{\mathbb R^d}|\nabla u|^2\,d\gamma_d.
$$

By an integration-by-parts computation under $\gamma_d$, the generator becomes
$$
L = -\Delta + x\cdot \nabla,
$$
leading to the **OU process**
$$
dX_t = -X_t\,dt + dB_t.
$$

if $\int|\nabla u|^2\,d\mu$ has something like semi-lower-cont., we can use that in functional analysis to show existence in a measurable trajectory way

---

If a brownian motion is continuous in both $x$ and $y$ then we have a Feller process

Now what if it starts in every point a.s. instead of every point (like for Feller process)?

---

## Jump process example: continuous-time simple random walk on $\mathbb Z^d$
- example to go from kernel to generator
### Construction
- Waiting times $(\tau_j)_{j\ge 1}$ i.i.d. $\mathrm{Exp}(1)$.
- One-step jump variable $Z$ independent of the $T_j$, with
$$
\mathbb P^x(Z=y)=
\begin{cases}
\frac{1}{2d}, & |x-y|=1,\\
0, & \text{otherwise}.
\end{cases}
$$
- Counting process
$$
N_t=\sum_{j=1}^\infty \mathbf 1_{\{\tau_1+\dots+\tau_{j}< t\}},
\qquad t>0, \qquad N_t\sim \mathrm{Poisson}(t).
$$

### Figure: lattice jump picture
![[l1-fig-ct-rw-grid.png]]

- for each $x \in \mathbb{Z}^{d},$ by definition of a simple random walk $$X^{x}_{t}= x\mathbf{1}_{\{N_{t}=0\}}+Z\mathbf{1}_{\{N_{t}=1\}}+X^{x}_{t}\mathbf{1}_{\{N_{t}\geq 2\}}$$
- “stay at $x$ if $N_t=0$, jump once if $N_t=1$, otherwise iterate”?

### Semigroup
For bounded measurable $f:\mathbb Z^d\to\mathbb R$,
$$
(T_t f)(x)=\mathbb E^x[f(X_t)].
$$
Decomposition by number of jumps:
$$
(T_t f)(x)
= f(x)\,\mathbb P(N_t=0)
+ \mathbb E^x\!\left[f(Z)\mathbf 1_{\{N_t=1\}}\right]
+ \mathbb E^x\!\left[f(X_t)\mathbf 1_{\{N_t\ge 2\}}\right]
$$
Using independence of $Z$ and $\tau_{j}$ 
$$=f(x)\,\mathbb P(N_t=0)
+ \mathbb E^x\!\left[f(Z)\right]\mathbb P(N_t=1)
+ \mathbb E^x\!\left[f(X_t)\mathbf 1_{\{N_t\ge 2\}}\right]$$
Bounding the $N_t\ge2$ term by supremum norm $\|f\|_\infty$:
$$
(T_t f)(x)
\le f(x)e^{-t}
+ \frac{1}{2d}\sum_{y\sim x} f(y)\,t e^{-t}
+ \|f\|_\infty\Bigl(1-(1+t)e^{-t}\Bigr),
$$
and the last term is “small” for small $t$ due to the supnorm.

### Generator = discrete Laplacian
Taking $dt\big|_{t=0}$ gives 
$$
(Lf)(x)= \lim_{ t \to 0 } \dots
= -f(x)+\frac{1}{2d}\sum_{y\sim x}f(y)
= \frac{1}{2d}\sum_{y\sim x}\bigl(f(y)-f(x)\bigr).
$$
by dividing by $t$ and taking the limit of the individual terms
$$\lim_{ t \to 0 } \frac{f(x)e^{-t}}{t}=-f(x),\quad \lim_{ t \to 0 }\frac{\frac{1}{2d}\sum_{y\sim x} f(y)\,t e^{-t}}{t}=-f(x)+\frac{1}{2d}\sum_{y\sim x}f(y),$$
$$\lim_{ t \to 0 }\frac{\|f\|_\infty\Bigl(1-(1+t)e^{-t}\Bigr)}{t}=0.$$
Now if we look at the term $\frac{1}{2d}\sum_{y\sim x}\bigl(f(y)-f(x)\bigr),$ we see this is actually the **standard discrete Laplacian** (up to convention).

---

- There is a general extension of the correspondence theorems we show for non-linear markov processes. This is fairly recent and we try to replace quadratic functionals by convex ones.
- Paper in 2024, another earlier, and right now for example one that prof. Dello Schiavo is working on

---
## What this framework is for
Use Dirichlet-form/semigroup methods to prove:
- existence,
- uniqueness,
- properties,
- convergence,

especially where it’s hard to do directly in functional analysis or directly in stochastic calculus.

---

## Brownian motion on a domain $\Omega\subset\mathbb R^d$: boundary conditions

Let $\Omega$ be a “nice” domain (note: smooth boundary; “works up to Lipschitz”).

To define Brownian motion on $\Omega$, boundary conditions matter:

- **Reflecting / Neumann BC**: path is reflected normally inside $\Omega$ (inward normal direction).
- **Absorbed / killed / Dirichlet BC**: path is killed at the boundary.
- **Stopped BC**: path is stopped at $\partial\Omega$.
- **Robin BC**: partially reflective, partially absorbing.
- **Sticky-reflected BC**: partly reflected, partly constrained to move along $\partial\Omega$
  (“lets you explore the boundary”).
	- Gothaus–Voßau (2017)
	- Bormann–von Renesse-Wang (2024/2025)

### Figure: sketch of a domain $\Omega$
![[l1-fig-domain-omega.png]]



---

## Some facts on domains: boundary measure and trace

Let $\sigma_{\partial\Omega}$ be the $(d-1)$-dimensional Hausdorff measure on $\partial\Omega$.
- If $\partial\Omega\in C^\infty$, $\sigma_{\partial\Omega}$ is the usual surface measure.

The **trace operator**
$$
\mathrm{Tr}: u \mapsto u|_{\partial\Omega}
$$
is well-defined and bounded:
$$
\mathrm{Tr}: H^1(\Omega)=W^{1,2}(\Omega)\longrightarrow L^2_{\sigma_{\partial\Omega}}(\partial\Omega)
$$
(a.s. with respect to $(d-1)$-Hausdorff measure).

> [!todo] There’s a parenthetical note “unique continuous extension?” — not fully legible.

---

## Explicit forms for functionals

Base energy (heuristic):
$$
\mathcal E(u)=\int_\Omega |\nabla u|^2\,d\dots_{\Omega}^{d}.
$$

### Neumann
$$
(\mathcal E,\;H^1(\Omega)).
$$

### Dirichlet
$$
(\mathcal E,\;H^1_0(\Omega)), 
\qquad
H^1_0(\Omega)=\overline{C_c^\infty(\Omega)}^{\,H^1}.
$$

 - if everything is forced to be $0$ at the boundary, “we do not know where it hit the boundary” , so one needs a **rich enough test class** via the semigroup $T_t f$.

### Stopped
$$
(\mathcal E,\;H_0^1(\Omega)\oplus R),
$$
where $R$ is the consistent (constants) functions on $\Omega$.
- Idea: adding constants lets you distinguish “stopped” vs “killed” behavior via testing along trajectories with $f(X_{t})$.

### Robin
Your notes indicate an added boundary penalty:
$$
\mathcal E_{\mathrm{Rob}}(u)
=
\mathcal E(u)+\int_{\partial\Omega}\mathrm{Tr}(u)^2\,\rho\,d\sigma_{\partial\Omega},\qquad\rho\in C_b(\Omega)
$$
- imagine $\rho\in[0,1]$, then $\rho$ is Bernoulli parameter
- we take $\rho\in C_b(\Omega)$, such that we can make $\rho$ always element of $[0,1]$ by normalising and...

form domain / core then is
$$
\mathcal D(\mathcal E_{\mathrm{Rob}})
=
\left\{u\in H^1(\Omega)\;:\;\int_{\partial\Omega}\mathrm{Tr}(u)^2\,\rho\,d\sigma_{\partial\Omega}<\infty\right\}.
$$
### Sticky-reflected
Your notes add a **tangential energy** along the boundary:
$$
\mathcal E_{\mathrm{sticky}}(u)
=
\mathcal E(u)
+\int_{\partial\Omega}|\nabla^\tau u|^2\,\rho\,d\sigma_{\partial\Omega},
$$
where $\nabla^\tau$ is the **tangential gradient on** $\partial\Omega$.

Domain / core:
$$
\mathcal D(\mathcal E_{\mathrm{sticky}})
=
\left\{u\in H^1(\Omega)\;:\; u|_{\partial\Omega}\in H^1(\partial\Omega)\right\}.
$$

Remark:
- We cannot write these using kernels, but we can write it in forms (functional analysis).

---

## Brownian motion on manifolds (two viewpoints)

### Chart-based construction (sketch)
Draw a manifold $M^d$ with a chart $\varphi$ mapping a neighborhood into $\mathbb R^d$,
and a procedure from **Ikeda–Watanabe** (book) defining stopping times $\tau_0,\tau_1,\dots,\tau_{n}$

Issue noted:
- paths may only be defined up to $\sum_n \tau_n$
- if neighborhoods shrink too fast (e.g. a “cusp”), one can have $\sum_n \tau_n$ undefined
so the construction may break. 
- in general though we have that $\sum_n \tau_n<\infty$ 

#### Figures
![[l1-fig-manifold-chart.png]]
![[l1-fig-cusp-explosion.png]]

### Alternatively operator viewpoint (use Laplace–Beltrami)
Alternative: take the **Laplace–Beltrami operator** $\Delta^g$ on $(M,g)$
(“Laplacian of manifold $M$”).

Brownian motion on $M$ is (by definition) the process generated by
$$
L = -\Delta^g.
$$

Energy form by (heuristic) integration by parts can sloppily be written as:
$$
\mathcal E(f)=\int_M |\nabla^g f|^2\,d\mathrm{vol}_g.
$$

We must actually write using Sobolev space that energy form and f are given by:
$$
f \in W^{1,2}(M,g)
:=
\left\{
f\in \mathcal D'(M):
f\in L^2,\ |\nabla^g f|\in L^2
\right\}.
$$

- note: $W^{1,2}\neq H^1 := cl_{W^{1,2}}(C^\infty)$, where $cl$ is the closure

---

## Interpretation: what do $u,v$ mean in $\mathcal E$?

- $u,v$ are functions on the state space, i.e. elements of $L^2(S,\Sigma,m)$.
- If $u\in\mathcal D(\mathcal E)$, it has **finite energy**.
- $u,v$ are nice enough functions, meaning we can differentiate them in $L^2$ (weak) sense
### Dynamics interpretation
In $Q(u)=\mathcal E(u,u)$, we feed one finite-energy function $u$ and it measures (informally)
how much $u$ *varies under the dynamics* when you look at $u(X_t)$.

### Fukushima-type decomposition
Often one has
$$
u(X_t)-u(X_0)=M_t^u+N_t^u,
$$
where
- $M_t^u$ is the **martingale part** (random fluctuations),
- $N_t^u$ is the **finite-variation part** (drift-like, tied to the generator).

Heuristic meanings:
- $Q(u)=\mathcal E(u,u)$ is the **quadratic-variation rate** (variance per unit time) of $M^u$.
- $\mathcal E(u,v)$ is a **cross-energy**, like the covariance pairing between $M^u$ and $M^v$.

### Semigroup formula for $\mathcal E$ (as written)
$$
\mathcal E(u,v)
=
\lim_{t\downarrow 0}\frac{1}{t}\,\langle u-T_tu,\ v\rangle_{L^2}.
$$
Mnemonic:
- “push forward $u$ and measure first-order change against $v$”.
