# Lecture 3 — Markovianity, contractions, and regularity

## 1. What we’re adding to the “$T_t \leftrightarrow G_\alpha \leftrightarrow L \leftrightarrow \mathcal E$” diagram
- We now want **positivity / order** properties so that semigroups/resolvents can be represented by **(sub-)probability kernels** and hence correspond to **Markov processes**.
- In the background: we may have **no symmetry** (non-reversible Markov processes); in many places one still assumes **self-adjointness** on the Hilbert side, except that the “energy” viewpoint (Dirichlet forms) is a quadratic form hence automatically symmetric.
- “Weak sector condition” is a typical hypothesis in the non-symmetric theory (Markov processes not reversible).

---

## 2. Why we leave general Hilbert space when talking about Markov kernels
**Goal:** represent $T_t$ by a measure $p_t(x,dy)$ or a kernel $p_t(x,\cdot)$ so that we may speak of a Markov process.

To speak about $p_t$ as a (sub-)probability kernel we need an **order** (“$\le$”, “$\ge$”), as we want to say things like $p_t(x,\cdot)\geq0$
But **general Hilbert spaces have no natural order**, so we try to work on a **Banach lattice**, typically:
- $(X,\Sigma,m)$ a measure space,
- $L^p_m := L^p(X,\Sigma,m)$.

A banach lattice is a Banach space on order structure, which has continuity defined w.r.t. the norm.

We eventually want **Hilbert** spaces theory to apply, so we keep $p=2$, but order is naturally expressed on $L^p$.

**Separability:** for $L^p$ spaces one convenient additional condition is separability:
- $\Sigma$ is **countably generated** and $m$ is **$\sigma$-finite**  
(then $L^p_m$ is separable for $1\le p<\infty$).

---

## 3. Markov / sub-Markov operators (order-theoretic definition)
Let $B:L^2_m\to L^2_m$ be bounded.

### Definition ((sub-)Markov property)
$B$ is has the Markov property if
- whenever $0\le f\le \mathbf{1}$ (a.e.)  $\implies 0\le Bf\le \mathbf{1}$ (a.e.).

If $B$ is represented by $p_t$ then this $p_t(.,d.)$ is a (sub-)probability.

Now we $B$ is sub-markovian if:
$$
B\mathbf 1 \leq \mathbf 1.
$$
and $B$ is markovian if:
$$B\mathbf 1 = \mathbf 1.$$

(Heuristically: sub-Markov $\leftrightarrow$ sub-probability kernels, Markov $\leftrightarrow$ probability kernels.)

### Useful reformulation (what “Markov” encodes)
Markov $=$
1. **Order-preserving:** $f\le g \implies Bf\le Bg$,
2. **$L^\infty$ non-expansive:** $\|Bf-Bg\|_\infty \le \|f-g\|_\infty$ for $f,g\in L^2_m \cap L^\infty_m$.

*(This is exactly the structure that shows up most clearly in non-linear Markov theory; see e.g. Cipriani–Grillo (2003) and later work such as Brigati–Della Schiavo (2025, as cited in the notes).)*

---

## 4. Kernel representation (Dunford–Pettis)
A key analytic input is that bounded operators on $L^1$ to $L^\infty$ admit kernel representations.

### Fact (Dunford–Pettis, 1948 — “representation theorem” consequence)
If $B:L^1_m\to L^\infty_m$ is bounded, then there exists a measurable kernel $p(x,dy)$ (in general a finite signed measure in $y$ for each $x$) such that
$$
(Bf)(x) = \int_X f(y)\,p(x,dy).
$$
This statement alone does **not** use order; order/positivity is what upgrades $p(x,\cdot)$ to a (sub-)probability kernel.

In particular,
- $B$ **(sub-)Markov** $\Longleftrightarrow$ $p(x,\cdot)$ is a **(sub-)probability** kernel.

---

## 5. Markov semigroups on $L^2$ and extension to $L^p$
A common practical issue: $\mathbf 1\notin L^2$ in many situations, but Markovianity is naturally expressed via $B\mathbf 1\le \mathbf 1$ or $B\mathbf 1=\mathbf 1$.

### Fact (extension to $L^p$)
If $(T_t)_{t\ge 0}$ is a **strongly continuous contraction** semigroup on $L^2_m$ and is **(sub-)Markov**, then:
- $T_t:L^2_m\cap L^{p_{m}\to}L^2_m\cap L^p_m$ is an **$L^p$-contraction**,
- and it extends to a contraction semigroup on **each** $L^p_m$, $1\le p\le\infty$, i.e., to $T_{t}:L^{p}_{m}\to L^p_{m}$
- it is **strongly continuous** on $L^p_m$ for $1\le p<\infty$,
- on $L^\infty_m$ one typically only expects **weak(-*) continuity** (since $L^\infty$ is not separable).

---

## 6. Dirichlet forms = closed quadratic forms + Markovianity
We now encode Markovianity at the level of the energy.

### Definition (Dirichlet form)
A densely defined closed quadratic form $(\mathcal E, D(\mathcal E))$ on $L^2_m$ is **Dirichlet form** if its domain $\mathcal{D}(\mathcal{E})$ satisfies the **Markov property** through implication:
$$
u\in \mathcal{D}(\mathcal{E})\quad\Longrightarrow\quad \bar u:=0\vee u\wedge 1\in \mathcal{D}(\mathcal{E})\ \ \text{and}\ \ \mathcal E(\bar u)\le \mathcal E(u).
$$
Note: it is not in general true that $\mathcal E(\bar u)\le \mathcal E(u)$

![[l3-fig-truncation.png]]

### Unit contractions
A map $\phi:\mathbb R\to\mathbb R$ is a **unit contraction** (as used in the notes) if:
- $\phi(0)=0$,
- $-t\le \phi(t)\le t$ for all $t$,
- $0\le \phi(s)-\phi(t)\le s-t$ for all $s\ge t$  
(in particular, $\phi$ is $1$-Lipschitz and order-preserving).

Then a standard equivalent formulation of the Markov property is:
$$
u\in D(\mathcal E)\ \Rightarrow\ \phi\circ u\in D(\mathcal E),\qquad \mathcal E(\phi(u))\le \mathcal E(u)
\quad\text{for all unit contractions }\phi.
$$

*(The notes also mention “normal contractions”: $u$ is a normal contraction of $v$ if
$|u(x)-u(y)|\le |v(x)-v(y)|$ for $m^2$-a.e. $(x,y)$. This is a convenient way to package contraction stability.)*

---

## 7. Equivalent “Markovianity” statements across the diagram (FOT)
A key theorem (Fukushima–Oshima–Takeda, 2011; see Thm. 1.4.1 as cited) says that Markovianity is consistent across semigroup/resolvent/form.

### Proposition (equivalences)
The following are equivalent (in the standard symmetric setting):
1. $(T_t)_{t>0}$ is **(sub-)Markovian** on $L^2_m$,
2. $(\alpha G_\alpha)_{\alpha>0}$ is **(sub-)Markovian**,
3. $(\mathcal E, D(\mathcal E))$ is a **Dirichlet form**,
4. **every unit contraction operates** on $(\mathcal E, D(\mathcal E))$:
   $\phi\circ u\in D(\mathcal E)$ and $\mathcal E(\phi(u))\le \mathcal E(u)$, (not just unit contractions 0,1 but every unit contraction)
5. (often included) **every normal contraction operates** on $(\mathcal E, D(\mathcal E))$:
   if $u$ is a normal contraction of $v\in D(\mathcal E)$, then $u\in D(\mathcal E)$ and $\mathcal E(u)\le \mathcal E(v)$.
6. equivalent statement for generator exists

![[l3-fig-commuting-diagram.png]]

### “It’s enough to check on a core”
- In practice, one often checks Markovianity on a dense subspace $C\subset D(\mathcal E)$ that is dense in the **$\mathcal E_1^{1/2}$-norm** on $L^2$:
$$
\|u\|_{\mathcal E_1^{1/2}} := \big(\mathcal E(u)+\|u\|_{L^2}^2\big)^{1/2}.
$$
This is like the earlier defined graph-norm giving a Hilbert-space topology on the form domain, which was defined as:
$$\|u\|_{\mathcal E_\alpha^{1/2}} := \big(\mathcal E(u)+\alpha\|u\|_{H}^2\big)^{1/2}.$$
Note we do not look at the semi-norm defined as:
$$\mathcal{E}^{1/2}(u):=(\mathcal{E}(u,u))^{1/2},$$
which can be zero even when $u$ non-zero (e.g., constants for Neumann laplacian on connected domain)

- Because truncations can be approximated by **smooth** unit contractions, verifying contraction stability on $C$ can be sufficient for saying properties holding on $C$ hold for $D(\mathcal E)$. (truncation is continuous)

![[l3-fig-smooth-approx.png]]
### Example proving form is Dirichlet form
- when is a form Dirichlet?
	- when it is closed, densely defined and quadratic
	- its form domain $D(\mathcal E)$ has the Markov property

- Now if we have a core $C$ that is dense in the **$\mathcal E_1^{1/2}$-norm** on $L^2$ that has the Markov property
- then the closed, densely defined quadratic energy form $(\mathcal{E}, D(\mathcal E))$ is a Dirichlet form as the form domain then has the Markov property

---

## 8. Lattice inequality (a “non-linear” face of Dirichlet)
A particularly transparent lattice consequence is:
$$
\mathcal E(u\wedge v)+\mathcal E(u\vee v)\ \le\ \mathcal E(u)+\mathcal E(v),
\qquad u,v\in D(\mathcal E).
$$
This is one reason Dirichlet forms behave well on Banach lattices.

---

## 9. Bringing topology in: regular Dirichlet forms
For kernels/Markov processes we usually want a **topological** state space. We then get rid of notation $S$ for a general state space and take $X$ as the state space equipped with topological structure.

### Setup
Let $(X,\tau)$ be a topological space and $\mathcal B_\tau$ its Borel $\sigma$-algebra.  
Let $\chi_{\tau}$ being compact sets
Typically we work with a topological measure space $(X,\Sigma,m)$ with $\mathcal B_\tau\subseteq \Sigma$ (often $\Sigma=\mathcal B_\tau$).

Let $C_0(X)$ be continuous functions vanishing at infinity

### Definition (regular Dirichlet form)
A Dirichlet form $(\mathcal E,D(\mathcal E))$ on $L^2_m(X)$ is **regular** if:
1. $(X,\tau)$ is second countable locally compact Hausdorff ($T_{2}$) space
	1. Now $C_0(X)$ is a separable Banach space when $(X,\tau)$ is second countable locally compact Hausdorff ($T_{2}$) space.
2. $m$ is a **Radon measure** (inner regular w.r.t. compact sets $\chi_{\tau}$ and finite on compacts $\chi_{\tau}$)
3. $D(\mathcal E)\cap C_0(X)$ is **uniformly dense** in ambient space $C_0(X)$ and is **$\mathcal E_1^{1/2}$-dense** in $D(\mathcal E)$,
	1. where we had $\|u\|_{\mathcal E_1^{1/2}} := \big(\mathcal E(u)+\|u\|_{L^2}^2\big)^{1/2}.$

### Classification of the assumptions
- Assumptions 1 and 2 say that we have a sufficiently nice setting
- Assumption 3 says that there is a good class of functions for which we can talk about properties of the form

### Remark (closability of restrictions)
- We want the ambient space in which $D(\mathcal E)\cap C_0(X)$ must be uniformly dense to still be Banach and separable, so we can not take a larger space than  $C_0(X)$ to be the ambient space.
- If $(\mathcal E,D(\mathcal E))$ is closed, then the restricted form $(\mathcal E, D(\mathcal E)\cap C_0(X))$ is **closable**. 
	- More generally, every subform of a closed form is closable if we take the closure w.r.t. the graph norm $\mathcal E_1^{1/2}$

---

## 10. Cores and bump functions
A very useful characterization is:

### Proposition (core characterization)
In the “nice setting”, and $(\mathcal{E},D(\mathcal{E}))$ is closed and quadratic then the following are equivalent:
- $(\mathcal E,D(\mathcal E))$ is regular,
- there exists a **core** $C\subseteq D(\mathcal E)\cap C_0(X)$ such that
  - $C$ is $\mathcal E_1^{1/2}$-dense in $D(\mathcal E)$,
  - $C$ is uniformly dense in $C_0(X)$.

Moreover, regular forms have cores which are sets that satisfy the above properties, we denote these cores by $C$ and they are either:

1. Standard (**Stability under (smooth) approximate contractions**)  
	$C$ is dense in a linear subspace and
	
	for every $\varepsilon>0$ there exists a (smooth) $\phi_\varepsilon:\mathbb R\to\mathbb R$ with
	$\phi_\varepsilon(t)=t$ on $[0,1]$,
	$-\varepsilon\le \phi_\varepsilon(t)\le 1+\varepsilon$,
	$0\le \phi_\varepsilon(s)-\phi_\varepsilon(t)\le s-t$ for $s\ge t$,
	such that $u\in C \Rightarrow \phi_\varepsilon\circ u\in C$.

	This is like the smooth version of a unit contraction (no hard corners by truncation)

2. Special (**Bump functions with Urysohn-like property)**
	$C$ is a dense subalgebra of $C_{0}$ and
	for every compact $K \subseteq \chi_{\tau}$ and (open?) $G \subset \tau$ with $K\subset G$, there exists $u\in C$ such that
	$$
   \mathbf 1_K \le u \le \mathbf 1_G.
   $$
	This lets you “test locally” on small compact sets without being affected by far-away behavior.

![[l3-fig-bump-function.png]]

---

## 11. Examples / non-examples (why regularity can fail)

### 11.1 Point interaction Hamiltonian for scattering problem
What is it about: problem of detection at a fine scale
Heuristic picture: Brownian motion on $\mathbb{R}^{3}$ with a “special point” (a point interaction / $\delta$-type perturbation).

So we have $L=-\Delta$ on domain of test functions $\{ f\in H^{2} \cap H_{0}^{1}:f(x_{i}=0) \}$
The following solves the scattering problem:
$$(-\Delta \pm i)u=\delta_{x_{1}}+\dots+\delta_{x_{n}},$$
where these are all Dirac delta's.
This solution tells you what happens when points are actually hit, not just that you move towards them by a brownian motion.
![[l3-fig-point-interaction.png]]

In one dimension, imposing $f(0)=0$ and looking at $H^{2} \cap H_{0}^{1}$ leads to a candidate core
$$
C=\{u\in C^1\cap H^1: f(0)=0\},
$$

For intuition look at the case where we look in $\mathbb{R}$ instead of $\mathbb{R}^{3}$ and we have $n=1$ and for that $n$ we have that $x_{1}=0$
We get the idea to get $C$ as the candidate core for $\mathcal{E}^{BM}:=\int_{\mathbb{R}}|f'|dLeb^{1}$
What we see is that $C$ is **not** $C_0(\mathbb R)$-dense (but can be dense in $C_0(\mathbb R\setminus\{0\})$).  


All of this in this example ties to the fact that $(-\Delta,C)$ admits (infinitely) many self-adjoint extensions, often described informally as
“$-\Delta+\alpha\,\delta_0$”, where $\alpha \in \mathbb{C}$

![[l3-fig-bm-line-bc.png]]

So the problem that is seen in this example is that the closure depends on what the $C_{0}$ sees function-wise. It can see anything, so we are not able to measure.
### 11.2 Non-Radon measures (local finiteness fails)
Take a weighted measure $m=\mu=\phi^2\,dLeb^{1}$ on $\mathbb R$ where $\phi$ has a non $L^1$-singularity at $0$ so that
$$
\mu(A)=\infty \quad\text{for every neighborhood }A\ni 0.
$$
Then a Brownian motion is pushed towards the singularity and goes explosive behaviour wise.

Lebesgue measure is translation invariant

Then many “nice” test functions may fail to lie in $L^2(\mu)$; for instance $C_c^\infty(\mathbb R)$ may be “too large of a space” and is not in $L^2$.
One may look to restrict to $C_c^\infty(\mathbb R\setminus\{0\})$.

Imagine by $\phi\equiv+\infty$, i.e., singular on a dense set. Then the measure explodes and we can't do integration.

In this case not even the property $(X,\tau)$ is second countable locally compact Hausdorff ($T_{2}$) space will help to make things behave nicely. The non-radon measure messes it up.

![[l3-fig-psi-singularity.png]]

---

## 12. Infinite-dimensional state spaces: 

- What is a BM on a general hilbert space?
This must be answered by functional analysis as we can't with kernels.
Difficult question to answer as there exists no Lebesgue measure on a Hilbert space. 
There is a theorem that says if groups are not locally compact then there exists no lebesgue measure on the space. (?)

- What is a OU process on a Hilbert space?
We then get the issue that we have a hard question: with which functions do we test?

If $X$ is an infinite-dimensional Banach space, then this is equivalent to:
- there are **no** open balls with compact closure,
- often $C_{c}(\tau \text{ Strong})$ is trivial (only $\{0\}$),
so the “regular” core condition becomes impossible, as no $C_{c}$ function exists and $C_{c}$ is too small.

Note that in this case the space is too small, while earlier we had considered spaces that we're too large for our purposes.

---

## 13. 1 Example: Banach spaces & Banach manifolds
### Wiener space
Let us consider paths and loops
- $\mathrm{Path}_0(\mathbb R^d)=\{f\in C^{0}([0,\infty):\mathbb R^d): f(0)=0\}$,
- Loop $\{f\in C^{0}([0,1]:\mathbb R^d): f(0)=f(1)\}$

- $X:=\mathrm{Path}_0(\mathbb R^d)$ is natural wiener
- $m$ = Wiener measure (law of Brownian motion).

Can one define natural Dirichlet forms on such spaces (connections to Malliavin calculus).

![[l3-fig-path-space.png]]

### 13.2 Example: infinite dimensional spaces (of measures)
One can talk about Markovian solutions to Stochastic PDEs or SPDEs. These solutions are (random) densities/measures, such as the Dean–Kawasaki type equation:
$$
d\rho = \Delta\rho\,dt + \nabla\cdot(\sqrt{\rho}\,dW)
$$

Or consider the more general equation:
$$d_{t}\rho=\Delta \rho + W,$$
with $W$ space-time $\mathbb R^d$-valued white noise.  

This $\rho$ solves the heat equation, with well-prepared initial $\rho_{0}\in P(\mathbb{R}^{d})$, where $P$ is a probability measure. We can then actually even show that  $\rho_{0}\in P(\mathbb{R}^{d}) \implies \exists \rho_{t}\in P(\mathbb{R}^{d}), t\geq 0$.

The term $\sqrt{\rho}$ in the Dean-Kawasaki equation highlights the need for frameworks beyond classical regularity, because what is the square root of a distribution?

The Dean-Kawasaki equation becomes less and less regular (and is seen to be very singular)

---

## 14. Dirichlet forms on Wasserstein space (example beyond regularity)
A recent example mentioned in the notes:
- Konarovskyi–Lehmann–von Renesse (2018) and related developments by Dello Schiavo (2022-2025).

We can say $\rho_{t}=T_{t}\rho_{0}$, where $T_{t}$ is the semigroup for:
$$\mathcal{E}(u):=\int_{\mathcal P_2(\mathbb R^d)}|\nabla u|^{2}_{\tau u \mathcal P_2(\mathbb R^d)}d\mathbf{D}(\mu)$$

For state space $\mathcal P_2(\mathbb R^d)$ being the **$L^2$-Wasserstein space** often used in optimal transport problems.

and where
- $\nabla$ is the **Eotto's gradient**,
- $\mathbf D$ is a **Dirichlet–Ferguson** type reference measure (as noted, used in Bayesian/statistical contexts),
- see also  Ambrosio–Gigli–Sauaré (2000/2001).

### Takeaway
These examples show **regularity is not enough**; one needs **quasi-regularity**, and initial data $\rho_0$ need not be smooth.
