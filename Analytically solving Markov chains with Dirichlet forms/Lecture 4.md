# Lecture 4 — Transience, invariance, irreducibility

## 1. Topological properties we want to translate to Dirichlet-form language
The goal is to understand **long-time / global behaviour** of a Markov process (or semigroup) and express it in the equivalent languages:
$$
(T_t) \leftrightarrow (G_\alpha) \leftrightarrow L \leftrightarrow (\mathcal E, D(\mathcal E)).
$$

Key qualitative properties today:
- **conservativeness** (no killing / no explosion)
	- Lifetime of the process is $+\infty$ a.s.
	- Process does not leave state space $X$.
	- $T_t \mathbf 1 = \mathbf 1 \quad \forall\, t>0,$ where $\mathbf{1}$ is the constant function on the whole space.
- **transience**
	- process does not eventually return to any bounded region of the space with a positive probability.
	- e.g., in $\mathbb{R}$ a BM always visits space around zero point, but in $\mathbb{R}^{d}$ for $d>1$ it does not.
- **recurrence**
	- if it does return to any bounded region with positive probability
	- e.g., “Neumann is reflective, so it is recurrent.”
- **invariance**
	-  $A \subseteq X$ (borel set) is $M$-invariant if $M^{*}:=M$ conditioned to start at $x \in A$, does **not** leave $A$ for all times
- **irreducibility**
	- $M$ is irreducable if borel set $A$ being invariant implies $A\equiv_{m-a.s.}\{ \emptyset,X \}$,
		- i.e., $m(A\Delta\emptyset)=_{a.s.}0$ and $m(A\Delta X)=_{a.s.}0$.
- **ergodicity**
	- if the long time behaviour of the process is independent of the starting point

For all of the above $C_{0}$ is not a rich enough space.

---

## 2. Conservativeness (stochastic completeness)
Let $M$ be a Markov process with **lifetime** $\zeta$.

### Definition (conservative)
$M$ is **conservative** if it does not leave $X$:
$$
\mathbb P_x(\zeta = +\infty)=1 \quad\text{for all }x.
$$

On the semigroup side this is (formally) the statement
$$
T_t \mathbf 1 = \mathbf 1 \quad \forall\, t>0.
$$
*(Caveat: $\mathbf 1\notin L^2$ in many situations, so this is naturally an $L^\infty$-type statement.)*

### Remark (manifolds)
For Brownian motion on a Riemannian manifold, conservativeness is the same as **stochastic completeness**.

### If not conservative: cemetery extension
If $T_t$ is not conservative, one can “add a cemetery point Dirac” $\delta_{\partial}$ so that the extended process becomes conservative on $X\cup\{\delta_{\partial}\}$.
Heuristically:
- probability mass $\mathbf1-T_t\mathbf 1$ is the probability that the process has been killed / has moved to $\delta_{\partial}$ by time $t$,
- and $\delta_{\partial}$ is Dirac of cemetery
We then get $$\hat{T}_{t}:L^{2}\oplus \mathbb{R} \to L^{2}\oplus \mathbb{R}$$
---

## 3. Transience vs recurrence: why we introduce a monotone object

Remarks:
- **Transience** and **recurrence** are only mutually exclusive if the process is **ergodic**.

A recurring annoyance:
$$
t\mapsto (T_t f)(x)\quad \text{need not be monotone in }t.
$$
Underneath we see that as time increases $T_{t}f$ gets smoothed out, but this smoothing is not necessarily monotone

![[l4-fig-nonmonotone-smoothing.png]]

So for comparison arguments we introduce a monotone-in-$t$ substitute.
### Definition (monotone semigroup)
For $f\ge 0$, define
$$
(S_t f)(x) := \int_0^t (T_s f)(x)\,ds .
$$
Then for $f\ge 0$, $t\mapsto S_t f(x)$ is monotone increasing (a.e.).
### Exercise (as in the notes)
- $T_t, S_t: L^2_m\to L^2_m$ extend to operators $T_t, S_t: L^1_m\to L^1_m$,
- for $f\in (L^1_m)^+$, $t\mapsto S_t f(x)$ is $m$-a.e. monotone increasing.

---

## 4.  Transience using the monotone semigroup (Green operator?)
### Definition (Green operator via $S_t$?)
For $f\in (L^1_m)^+$, define
$$
Gf := \lim_{t\to\infty} S_t f \in [0,+\infty]\quad (m\text{-a.e.})
$$
(the limit exists now because $S_t f$ is monotone, with $T_{t}$ this was not possible).

### Definition (transient semigroup)
$(T_t)$ is **transient** if
$$
Gf <\infty \quad m\text{-a.e. for all } f\in (L^1_m)^+.
$$

### Resolvent relation
For $\alpha>0$,
$$
G_\alpha f := \int_0^\infty e^{-\alpha t}\,T_t f\,dt,
\qquad\text{so that } G_\alpha = (\alpha - L)^{-1}.
$$
Formally,
$$
Gf = \lim_{\alpha\downarrow 0} G_\alpha f.
$$

### “Reference function” formulation
A transient semigroup admits a **reference function** $g$ such that
- $g>0$ $m$-a.e.,
- $\langle g, Gg\rangle_{L^2}\le 1$.

Here we use an integral definition instead of a point-wise definition of $Gf$.
In the $\langle g, Gg\rangle_{L^2}\le 1$ equation we would need $g=0$, but we restrict the reference function to be $g>0$ , so what happens is...

(Here $Gg\ge 0$ by definition and also the inner product is non-negative since $T_t$ preserves positivity.)

---

## 5. Transience for the Dirichlet form
### Definition (transient form via a reference function)
$(\mathcal E, D(\mathcal E))$ is **transient** if there exists
$$
g\in L^1_m\cap L^\infty_m,\qquad g>0\ \ m\text{-a.e.},
$$
such that for all $u\in D(\mathcal E)$,
$$
\int_X |u|\,g\,dm \ \le\ \sqrt{\mathcal E(u)}.
\tag{$*$}
$$

**Why the square-root?** $\mathcal E$ is quadratic (2-homogeneous), while $u\mapsto\int|u|g\,dm$ is 1-homogeneous.

**Heuristic:** the seminorm $\mathcal E^{1/2}$ cannot control constants, but in the transient regime it can control “mass at infinity” through ($*$).

---

## 6. Equivalence proposition (FOT Lemma 1.5.1 + Thm 1.5.1)
The following are equivalent:
1. $(T_t)$ is transient,
2. $\exists g\in (L^1_m)^+$ with $g>0$ $m$-a.e. and $Gg<\infty$ $m$-a.e.,
3. $(\mathcal E, D(\mathcal E))$ is transient.

Moreover, in all cases the same $g$ can be taken as a **reference function** for both the semigroup and the form (latter being the $g$ that satisfies ($*$)).

---

## 7. Extended domain $D(\mathcal E)_e$ (a.k.a. extended Dirichlet space $F_e$)
“Controlling $\mathbf 1$ is not enough”; we need a space that captures behaviour at infinity.

### Definition (extended domain)
Define $D(\mathcal E)_e$ as the set of $f\in L^{0}_{m}$ such that there exists $f_n\in D(\mathcal E)$ with
- $f_n\to f$ locally in measure, i.e., $m$-$\lim_{ n \to \infty }f_{n}=f$
- $(f_n)$ is **$\mathcal E^{1/2}$-Cauchy** (note: seminorm, so **not** $\mathcal E_1^{1/2}$-Cauchy).

Visually: we have that the $f_{n}$ for large enough $n$ begins to look like a constant on part of the graph and this is more and more as $f_{n}\to f$.
![[l4-fig-extended-domain-approx-constant.png]]

### Facts
- $\mathcal E(f):=\lim_n \mathcal E(f_n)$ is well-defined (independent of the approximating sequence choice $f_{n}$).
- $D(\mathcal E)_e\cap L^2_m = D(\mathcal E)$.
- The form is transient is equivalent to $\big(D(\mathcal E)_e,\,\mathcal E^{1/2}\big)$ is complete (note that we are again working with a **seminorm** here).

### Theorem (FOT, “this and many more statements”)
For a transient Dirichlet form $(\mathcal E, D(\mathcal E))$, $(\mathcal F_e,\mathcal E)$ is its extended space iff:
1. $(\mathcal F_e,\mathcal E)$ is complete (Hilbert after identifying $\mathcal E$-null functions),
2. the reference-function inequality ($*$) holds for all $u$ in the larger space $\mathcal F_e$,
3. $\mathcal F_e\cap L^2_m$ is dense in both $L^2_m$ and in $D(\mathcal E)$,
4. every **normal contraction** operates on $\mathcal F_e$.

“Idea is start with something small, make it something large, then get back the same something small.”

### Exercise
- Show the simple random walk is transient on $\mathbb{Z}^{d}$ for $d\geq 3$
---

## 8. Invariant sets
### Definition (invariance)
A Borel set $A\subset X$ is **$M$-invariant** if the process started in $A$ does not leave $A$ a.s., i.e.,
$$\int_{A}p_{t}(.,dy)=\mathbf{1}_{A}$$
Equivalently (semigroup statement):
$$
T_t(\mathbf 1_A f) = \mathbf 1_A\,T_t f \qquad \forall f \in L^2_m.
$$

### Theorem (characterisations of invariance)
The following are equivalent:
1. $A$ is $T_t$-invariant,
2. $T_t\mathbf 1_A = \mathbf 1_A T_t$ holds on $L^\infty_m\to L^\infty_m$ (stronger-looking statement as $\mathbf{1}_{A}$ can see the $\infty$ part in $A$),
3. $G_\alpha \mathbf 1_A = \mathbf 1_A G_\alpha$,
4. if $f\in D(\mathcal E)$ implies $\mathbf 1_A f\in D(\mathcal E)$, and the form **splits**:
   $$
\mathcal E(f,g) = \mathcal E(\mathbf 1_A f,\mathbf 1_A g) + \mathcal E(\mathbf 1_{A^c} f,\mathbf 1_{A^c} g)
$$
   (i.e. cross-terms vanish),
   Same statement but for $f\in D(\mathcal E)_{e}$
5. (generator viewpoint) $L$ kills the indicator: “locally $\mathbf 1_A$ is $L$-harmonic”.

Moreover, invariant sets form a $\sigma$-algebra we denote as $\Sigma_{\mathrm{inv}}$.

### Example: Brownian motion on a Riemannian manifold
For process $M$, a Brownian motion on $(M,g)$,
$$
A\text{ invariant}\quad \Longleftrightarrow\quad A \text{ is a union of connected components}.
$$
Later is in union form as manifold components are defined invariant themselves and a BM is continuous.

Since a (reasonable) Riemannian manifold is metrizable, the $\sigma$-algebra generated by connected components is countably generated.

Remark: $A\subseteq M$ is a union of connected components $\iff$ $A$ is “clopen” (open and closed).

---

## 9. Irreducibility
### Definition (irreducible)
$(\mathcal E, D(\mathcal E))$ (or $T_t$, or $G_\alpha$) is **irreducible** if
$$
A\ \text{invariant}\quad\Longrightarrow\quad A \equiv \emptyset\ \text{or}\ A\equiv X
$$
(up to $m$-null sets).

This means having one connected component.
### Restricting to an invariant set
If $A$ is invariant, then
$$
(\mathcal E_A, D(\mathcal E_A)) := (\mathcal E,\ \mathbf 1_A D(\mathcal E))
$$
is again a Dirichlet form.

Interpretation: this is the form of $M$ **conditioned to live on $A$**.  
(If this worked for arbitrary  borel $B\subset X$, we could “choose our favourite $B$”; invariance is exactly the compatibility condition.)

Remark: If $A$ is invariant s.t. $(\mathcal E_A, D(\mathcal E_A))$ is irreducable, then it is a connected component "as seen by" process $M$
### Later on: Diffusions and “quasi-clopen”
For diffusions (continuous sample paths) we'll see that invariance corresponds to a topological notion (“quasi-clopen”), hence topology becomes essential.

See example below, where we have two discs with one connection point. For Neumann boundaries the probability of reaching the other disc starting from one of the two (not the connection point) is zero. We can see this is because the discs are **not** clopen. 

![[l4-fig-discs-not-clopen.png]]

---

## 10. Recurrence and the conservative/dissipative decomposition
### Definition (recurrent)
$T_t$ (or $(\mathcal E,D(\mathcal E))$) is **recurrent** if for $f\in (L^1_m)^+$,
$$
Gf = 0 \quad\text{or}\quad Gf=+\infty
\qquad (m\text{-a.e.})
$$
(no nontrivial finite potentials).

### Sufficient criterion
If $\mathbf 1\in D(\mathcal E)$ and $\mathcal E(\mathbf 1)=0$, then the form is recurrent.  
(As noted: this is only a sufficient criterion. Also $\mathbf 1\in L^2_m$ forces $m(X)<\infty$.)

This condition implies by $\mathbf 1\in D(\mathcal E)$ that $m$ is a finite measure through the fact that $D(\mathcal E) \subseteq L^{2}_{m}$.
### Conservative vs dissipative part
Fix $g\in L^1_m$ with $g>0$ $m$-a.e. Define
$$
X_c := \{Gg = \infty\},\qquad
X_d := \{Gg < \infty\}.
$$
Facts:
- $X_c, X_d$ do **not** depend on the choice of $g$,
- it turns out that $X_c$ and $X_d$ are invariant by this definition.

### Theorem (FOT Lemma 1.6.4 p55)
- $T_t$ is transient $\Longleftrightarrow\ X_d \equiv X$,
- $T_t$ is recurrent $\Longleftrightarrow\ X_c \equiv X$,
- if $T_t$ is irreducible, then it is either transient or recurrent (no mixture).

Transient/recurrent answers will you return always to parts of the space.
If you also consider irreducibility then you can answer whether you will visit all of space.

---

## 11. Example: biased random walk on $\mathbb Z$
Consider the discrete-time nearest-neighbour walk on $\mathbb Z$ (by discrete time it is a jump process):
- step right to point $i+1$ with probability $p$,
- step left to point $i-1$with probability $q$,
- $p+q=1$.

![[l4-fig-biased-rw-step.png]]
Using standard notation
$$p_{t}(x,dy)=p_{x,y}^{(t)}$$

Return probabilities:
- for odd steps $p_{ii}^{(2n+1)}=0$,
- for even steps $p_{ii}^{(2n)} = \binom{2n}{n} (pq)^n$, we get binomial pdf.

By Stirling,
$$
p_{ii}^{(2n)}=\frac{(2n)!}{n!^{2}}(pq)^{n} \sim \frac{(4pq)^n}{\sqrt{\pi n}}.
$$
Hence
$$
s_{i}:=\sum_{n\ge 0} p_{ii}^{(n)}
= \sum_{n\ge 0} p_{\infty}^{(n)}\sim \sum_{n\ge 0}\frac{(4pq)^n}{\sqrt{\pi n}}
\text{ diverges iff } 4pq=1.
$$
Note conceptually:
$$s_{i}:=\sum_{n\ge 0} p_{ii}^{(n)}
=\text{"}S_{\infty}\mathbf{1}_{\{ i \}}\text{"}=\text{"}G\mathbf{1}_{\{ i \}}\text{"}$$
from the divergence of the sum we conclude that if:
- $p=q=\tfrac12 \Rightarrow$ recurrent,
- $p\neq \tfrac12 \Rightarrow 4pq<1 \Rightarrow$ transient (bias drives you away).

---

## 12. Decomposition into components and ergodic decomposition
### Question we can ask is
When is $X$ a union of “connected components as seen by $M$” (i.e. minimal invariant sets)?

### Th. (Kuwae ’21)
If $\Sigma_{\mathrm{inv}}$ is countably generated (e.g. on manifolds), then “minimal invariant sets” can be taken countably, and we get decompositions like:
$$
X = \bigcup_{A\ \text{minimal inv}} A=\bigsqcup A,\qquad
L^2_m = \bigoplus_{A\ \text{minimal inv}} L^2_{m}|_{A},
$$
and likewise
$$
(\mathcal E,D(\mathcal E)) = \bigoplus_{A\ \text{minimal inv}} (\mathcal E_A, D(\mathcal E_A)),
\qquad
T_t = \bigoplus_{A\ \text{minimal inv}} T_t\,\mathbf 1_A.
$$
Note: Countably many **minimal** invariant sets, **not** “countably many invariant sets”.

### Example: $\Sigma_{\mathrm{inv}}$ uncountably generated
Let $X=[0,1]^2$ with Dirichlet form
$$
\mathcal E(f) = \int_{[0,1]^2} |\partial_x f|^2\,d\mathrm{Leb}^2,
$$
Take domain as only having $H^1$ regularity in the horizontal direction, vertically there is no need to be connected at all.
Then we write
$$
D(\mathcal E) = L^2([0,1]_y;\,H^1([0,1]_x))
\cong L^2([0,1])\ \otimes_{H} H^1([0,1]),
$$
where $\otimes_{H}$ is the Hilbert tensor product.
Even more we have that $$L^2([0,1])\ \widehat\otimes\ H^1([0,1])\cong\int^{\otimes}_{[0,1]}H^{1}([0,1])\subseteq L^2(\mathrm{Leb}^2)$$
Note from this that we take now an integral, which is like a sum, over an uncountable set. This means we can not use the theorem of Kuwae '21.

![[l4-fig-horizontal-topology.png]]

In this model, for $A$ being a set vertically,
$$
A\ \text{invariant}\quad\Longleftrightarrow\quad A \equiv_{m-a.s.} [0,1]\times B
$$
for an arbitrary Borel (thus measurable) $B\subseteq[0,1]$, or $B$ being a Lebesgue measure.
This is not the same statement as we had earlier that $A\equiv_{m-a.s.}\{ \emptyset,X \}$.
We see thus that $\Sigma_{\mathrm{inv}}$ is uncountably generated and “countable component decompositions” fail.

### Ergodic decomposition (Dello Schiavo ’23)
If $(\mathcal E, D(\mathcal E))$ is a regular Dirichlet form and $m$ is a **finite** measure, then there exists a measure space $(Z,T,\nu)$ and a disintegration of $m$ over $Z$,  $\xi\mapsto m_\xi$ being a measure, s.t.,
$$
L^2_m = \int_Z^\oplus L^2_{m_\xi}\,d\nu(\xi),
\qquad
(\mathcal E,D(\mathcal E)) = \int^\oplus (\mathcal E_\xi, D(\mathcal E_\xi))\,d\nu(\xi),
$$
and each component $(\mathcal E_\xi, D(\mathcal E_\xi))$ is **irreducible**.

---
Additional remark on connected components:
- If we have only 1 connected component it **must** be that $Gg\neq 0$