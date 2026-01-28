# Lecture 6 — Locality without topology; LeJan energy measures; intrinsic distance; Cheeger energy; stochastic preliminaries

## 1. Functional-analytic locality (Bouleau–Hirsch)

Goal: an **analytic** notion of locality that does *not* require a topology (yet), but uses functional analysis only.

### BH-locality (characterisation)
TFAE (Bouleau–Hirsch, “locality via functional analysis”):
$(\mathcal E, D(\mathcal E))$ is **BH-local** iff:
- We have that
  $$
  fg \equiv 0 \quad \Longrightarrow \quad \mathcal E(f,g)=0, m-a.s.
  $$
  for $f,g\in D(\mathcal E)$ (interpretation: “no interaction when supports are disjoint in analytic sense”).
- We have that the Markovianity/Dirichlet property implies contractions preserve the domain/energy and $|f|$ is a contraction:
  $$
  |f|\in D(\mathcal E),\qquad \mathcal E(|f|)= \mathcal E(f),
  $$
  and in the symmetric Dirichlet-form setting typically $\mathcal E(|f|)\leq\mathcal E(f)$.

Remarks:
- If the measure is not Radon (no topology), “support” is not a topological object as we can not speak of continuity in topological sense; this is why the definition is phrased purely via multiplication.
### BH-strong locality
TFAE:
$(\mathcal E, D(\mathcal E))$ is **BH-strongly local** iff:
- We have that
$$
  \exists c\in\mathbb R:\ (f+c)g\equiv_{m} 0 \quad \Longrightarrow \quad \mathcal E(f,g)=0.
  $$
  (Heuristic: “$f$ is constant on the part of the space where $g$ lives (constant on the support)”.)

- We have that for $\alpha>0$,
  $$
  \mathcal E\big(|f-\alpha|+\alpha\big)=\mathcal E(f),
  $$
  i.e. shift from below and add a constant back so the function stays in $L^2$ and thus has good integrability.
![[l6-fig-locality-shift-plateau.png]]
- We have that "using post-composition"
	- A practical criterion (same “test on $\mathbb R$” philosophy):
	- For $f\in D(\mathcal E)$ and $F,G\in C_c^\infty(\mathbb R)$ with disjoint supports,
		let $F_0:=F-F(0)$ and $G_0:=G-G(0)$. Then (criterion) this must imply
		$$
\mathcal E\big(F_0(f),\,G_0(f)\big)=0.
$$
	- Interpretation:
		- Instead of trying to understand supports on the base space directly, you push $f$ through test functions $F,G$ on $\mathbb R$ where supports are way clearer interpretable.
		- In practice one often only needs to verify such identities on a **core**.

---

Remark 1: 
- The BH book’s terminology “local” corresponds to what we call **BH-strong locality** here.

Remark 2: 
- An analogous characterisation of BH-locality has been made in the non-linear case by Brigati, Dello Schiavo '25, namely the following:
- We have that a process is $\mathcal{E}$-BH local iff: $$uv=0 \implies \mathcal{E}(u\wedge v)+\mathcal{E}(u\vee v)=\mathcal{E}(u)+\mathcal{E}(v)\qquad\text{(or }\leq \text{ when we have a Dirichlet form?)}$$
- Note that locality is a saturation property, in the sense that it saturates the inequality.

---

## 2. LeJan formula and Carré du champ operator

Recall: if $(\mathcal E, D(\mathcal E))$ is regular, then
$$
\mathcal E(u,v)
=
\mathcal E^{(c)}(u,v)
+
\iint_{X\times X\setminus\Delta}(u(x)-u(y))(v(x)-v(y))\,dJ(x,y)
+
\int_X uv\,dK,
$$
where $\mathcal E^{(c)}$ is strongly local, $J$ is the jump measure, $K$ the killing measure (all uniquely determined).

Question in the notes: can we characterise $\mathcal E^{(c)}$ better, and extend this to the **quasi-regular** case?

Turns out yes we can and yes we can. For the latter we will do it by pushing forward to the regular setting by quasi-homeomorphism map, decompose and then try to push back to the quasi regular setting.

### LeJan formula (FOT Lemma 3.2.3)
There exists a bilinear map (energy form for the continuous part)
$$
\mu^c_{\langle\cdot,\cdot\rangle}:\ D(\mathcal E)\times D(\mathcal E)\to \mathcal M^{\pm}_{b}(X,\mathcal{N}_{\mathcal{E}})
$$
into finite signed measures that **do not charge** sets $A\in\mathcal{N}_{\mathcal{E}}$ ($\mathcal E$-polar sets), such that for $u,v\in D(\mathcal E)\cap C_0(X,\tau)$,
$$
\mathcal E^{(c)}(u,v)=\frac12\,\mu^c_{\langle u,v\rangle}X,
$$
and for every test function $\varphi\in \mathcal C_0$, which is dense in $C_{0}$,
$$
\int_X \varphi\,d\mu_{\langle u,v\rangle}
=
\mathcal E^{(c)}(u,\varphi v)+\mathcal E^{(c)}(v,\varphi u)-\mathcal E^{(c)}(uv,\varphi).
$$

Heuristic: once you can test against sufficiently many $\varphi$ in a dense class, i.e. use $\varphi\in \mathcal C_0$, you can identify the measure 
- is this measure we can identify $\mu^c_{\langle u,v\rangle}$ or $\mu_{\langle u,v\rangle}$?.

### Carré du champ (square field operator)
A strongly local Dirichlet form is said to admit a **carré du champ** operator if
$$
\mu^c_{\langle u,v\rangle}\ll m
\quad\text{for all relevant }u,v,
$$
where $\ll$ denotes absolute continuity.
What then follows is that a Radon–Nikodym derivative exists which we call the carré du champ operator:
$$
\Gamma(u,v):=\frac{d\mu_{\langle u,v\rangle}}{dm}:X\to \mathbb{R}
$$
Then what follows is
$$
\mathcal E^{(c)}(u,v)=\frac12\int \Gamma(u,v)\,dm.
$$

Example (Brownian motion):
$$
\mathcal E^{BM}(u,v)=\frac12\int \nabla u\cdot\nabla v\,dm
\quad\Rightarrow\quad
\Gamma(u,v)=\nabla u\cdot\nabla v,
\qquad
\mathcal E^{BM}(u)=\frac12\int |\nabla u|^2\,dm.
$$

Recall: 
$$m(A):=\inf\{ \|.\|_{L^2} \}$$
This is different that what the capacity does, which is:
$$\mathrm{cap}(A):=\mathrm{inf}\{ \mathcal{E}_{1}\mathrm{-norm} \}$$

Remark: So for we got concrete representations using BD and LeJan, now what about non-linear setting? LeJan won't work. Non-symmetric will work (see paper from Röckner). We can for non-linear at least do quasi-regularity.

---

## 3. Beurling–Deny in the quasi-regular case (Kuwae ’98)
In the quasi-regular setting one still gets a BD-type decomposition, but:
- $\mathcal E^{(c)}$ is defined on a dense class of $\mathcal E$-quasi-continuous functions,
- $J$ and $K$ need only be symmetric and **$\sigma$-finite** (in particular $J$ may fail to be Radon).

Proof idea mentioned: **transfer method** via quasi-homeomorphisms.
Pullback of a continuous function will be quasi-continuous.
Remark: $j$ itself is not a quasi-continuous function.
Caveat: transfer is good for **q.e. statements**, not good for $\tau$-statements.

![[l6-fig-quasi-homeo-sketch.png]]

---

## 4. Intrinsic distance from a local form
To control finer “connectivity” phenomena with a polar set as connection, a partial answer is to define an **intrinsic distance** associated with a strongly local form admitting $\Gamma$.

It is an **extended pseudo-distance** (extended means it may take value $+\infty$ and pseudo means it can be 0 outside $\Delta X$) defined using strongly local $\mathcal{E}$ and using $\Gamma$ by:
$$
d(x,y)
:=
\sup\Big\{ f(x)-f(y)\ :\ f\in D(\mathcal E)\cap C_b,\ \Gamma(f):=\Gamma(f,f)\le 1\Big\}.
$$

Heuristic:
- If the space splits into parts that cannot be connected by functions with bounded “energy slope”, then $d(x,y)=+\infty$ across the split?
- Take $x$ in the one disc and take $y$ in the other?
- Using intrinsic distance is “finer than just a topology”.

![[l6-fig-intrinsic-distance-discs.png]]

---

## 5. From distances on a general metric space to Dirichlet forms: Cheeger energy
Question: can we go from a metric $d$ on a space to a Dirichlet form (e.g. “Brownian motion on a fractal that has a distance defined”)?

We need Cheeger energy.

Let $(X,d,m)$ be a metric measure space:
- $(X,d)$ completely separable (Polish),
- $m$ finite on all $d$-bounded sets (replacement for Radon).

### Auxiliary definition: Slope of a Lipschitz function
For $f\in \mathrm{Lip}_{d}(X)$ define the slope
$$
|Df|(x):=\limsup_{y\to x}\frac{|f(y)-f(x)|}{d(y,x)}\le \mathrm{Lip}_{d}[f].
$$
This is taken from every $y$ to $x$.
(Plays the role of $|\nabla f|$ when $f\in C^{1}$ on a manifold.)

Note: it is defined as $|D.|$, and thus we can not talk of $D.$ on its own.
### Cheeger energy
Define the Cheeger energy by taking relaxation over all Lipschitz functions:
$$
\mathrm{Ch}_{d,m}(f)
:=
\inf\left\{
\liminf_{n\to\infty}\int_X |Df_n|^2\,dm
\ :\ f_n\in \mathrm{Lip}_{d}(X),\ f_n\to f\text{ in }L^2(m)
\right\}.
$$
General properties (from the remarks):
- $\mathrm{Ch}$ is convex, $2$-homogeneous, and lower semicontinuous (thus closed).
	- Lower semi-continuity follows from infimum relaxation
- In general, $\mathrm{Ch}$ need not be quadratic.

Sidenote: there is an extremely fruitfull theory of metric measure spaces & cheeger energies in connection with synthetic Ricci-curvature lower bounds. See for example Lott-Villani, Sturm, Ambrosio-Gigli-Savaré,...
### Infinitesimally Hilbertian
$(X,d,m)$ is **infinitesimally Hilbertian** if $\mathrm{Ch}_{d,m}$ is **quadratic** (equivalently: it satisfies the parallelogram identity).
### Theorem (Savaré ’14)
If $(X,d,m)$ is infinitesimally Hilbertian, then $\mathrm{Ch}_{d,m}$ is a **strongly local quasi-regular Dirichlet form**.

Corollary: every infinitesimally Hilbertian metric measure space admits a (possibly trivial, see example below) Brownian motion.
- Here we say Brownian motion as strong locality implies a continuous path.

Example in the notes (Ambrosio ’13): 
- One gets that $\mathrm{Ch}_{d,m}\equiv 0$ (“no motion”), when $(X,d):=[0,1]$, $m=\sum s_{i}\delta_{x_{i}}$, $\{ x_{i} \}_{i}=\mathbb{Q}\cap[0,1]$.
- This is because there is no path between points $\{ x_{i} \}_{i}=\mathbb{Q}\cap[0,1]$ and it "wants to jump", but it can not jump.

---

## 6. Stochastic preliminaries: completion, filtration, and Markov processes (see MR)

### Completion / universal $\sigma$-algebra
Let $(S,\mathcal B)$ be measurable and $P$ a probability on $(S,\mathcal B)$.

We want to look at larger sets $\mathcal B$ that are also neglicable in eyes of $P$.

Completing $\mathcal B$ by $P$ adds all $P$-null subsets (like polar sets?) (Carathéodory completion). We denote the Carathéodory completion by $\mathcal{B}^{P}$.

One can then define the universal completion:
$$
\mathcal B^*:=\bigcap_{\text{all probabilities }P \text{ on }(S,\mathcal B)} \mathcal B^P,
$$
which is the $\sigma$-algebra of universally measurable sets.

### Filtration
A family $(\mathcal M_t)_{t\in[0,\infty]}$ is a filtration if $\mathcal{M}_{t}$ is a $\sigma$-algebra $\forall t\geq_{0}$ and $\mathcal M_s\subseteq \mathcal M_t$ for $s\le t$.
Note: $\infty$ is included as time value in series of filtrations.
- We thus define a $\mathcal{M}_{\infty}$ the following way:
$$\mathcal{M}_{\infty}:=\bigvee_{t\in[0,\infty)}\mathcal{M}_{t}:=\sigma\left( \bigcup_{t\in[0,\infty)}\mathcal{M}_{t} \right)$$
A filtration is right-continuous when:
$$
\mathcal M_{t+}:=\bigcap_{u>t}\mathcal M_u=\mathcal M_t.
$$
Show as an exercise that $\mathcal{M}_{t+}^{P}=(\mathcal{M}_{t}^{P})_{+}$, i.e., the Carathéodory completion and right envelope are interchangeable.

Usual conditions for a filtration on $(\Omega,\mathcal{F},P)$ in stochastic calculus are by convention: $\mathcal{M}$ is a Carathéodory completion with right-continuity and $\mathcal M_\infty=\mathcal F$ (important that we do not say $<$).

### Cemetery point and lifetime
From now on in the theory always add an isolated measurable point $\partial$ (cemetery) to $(S,\mathcal{B})$, so we get $(S_{\partial}, \mathcal{B}(S_{\partial}))$ and the $\partial$ is always in the space:
$$
S_\partial:=S\cup\{\partial\},\qquad \partial\in \mathcal B(S_\partial).
$$

A process $X=(X_t)_{t\ge 0}$ on $(\Omega,\mathcal F)$ with lifetime $\zeta$ is a stochastic process if following hold:
1. $X_t:\Omega\to S_\partial$ is $\mathcal F/\mathcal B(S_\partial)$-measurable for each $t\in[0,\infty)$;
2. $\zeta:\Omega\to[0,\infty]$ is $\mathcal F$-measurable;
3. $\exists \omega \in \Omega \text{ s.t. }X_t(\omega)\in S$ for $t<\zeta(\omega)$ and $X_t(\omega)=\partial$ for all $t\ge \zeta(\omega)$.

A stochastic process is measurable iff:
$$
(t,\omega)\mapsto X_t(\omega)\ \text{is }(\mathcal B(\mathbb R_+)\otimes\mathcal F)/\mathcal B(S_\partial)\text{-measurable},
$$
where we mean with the setminus: "with values in".

Remark: joint measurability is stronger than measurability.

Adapted:
$$
X_t \text{ is }\mathcal M_t/\mathcal B(S_\partial)\text{-measurable}\quad \forall t\geq0.
$$

### Markov process (definition skeleton from the notes)
A Markov process is a tuple
$$
\mathbb{M}=(\Omega,\mathcal F,X,(P_z)_{z\in S_\partial})
$$
with state space $S$, cemetery $\partial$, lifetime $\zeta$, and a filtration $(\mathcal M_t)$ such that:
- (MP1) There exists an $\mathcal{M}$-filtration and $X$ is a stochastic process such that it is $(\mathcal M_t)$-adapted.
- (MP2: time-homogeneity) $\forall t\geq0$, there exist shifts $\theta_t:\Omega\to\Omega$ s.t.
  $$
  X_s\circ\theta_t = X_{s+t}\quad \forall s,t\ge 0;
  $$
- (MP3) $\forall z\in S_{\partial},$ $P_{z}$ is a probability on $(\Omega,\mathcal{F})$ such that $z\mapsto P_{z}(\Gamma)$ is $\mathcal{B}(S_{\partial})^{*}$-measurable $\forall \Gamma \in\mathcal{F}$.
	- We require only $\mathcal{B}(S_{\partial})$-measurable if $\Gamma \in \sigma \{ X_{s}:s \in [0,\infty] \}$ and $P_{\partial}[X_{0}=\partial]=1$. 
		- This means it is measurable if in whole path or measurable if starting from cemetry because then we do not move from the cemetry again and we measure the cemetry point.
	- With $\mathcal{B}(S_{\partial})^{*}$-measurable we mean it is universally measurable, as in we measure $Q$ probabilities aswell (which is what happens for points in certain (null/polar sets) that can be reached but with probability zero and are not in the $\sigma$-algebra).
- (MP4: Markov property)$$
  P_z\big[X_{s+t}\in A\mid \mathcal M_s\big]
  =
  P_{X_s}\big[X_t\in A\big],
  \qquad P_z\text{-a.s.},\ \forall z\in S_{\partial},\ \forall A\in\mathcal B(S_{\partial}),
  $$
	- where $P_z\text{-a.s.}$ means almost surely every $\omega$.
	- This implies that there an underlying semigroup $(T_t)$ as this allows for the semigroup property.

More conditions for a Markov process are in the next lecture.

---
