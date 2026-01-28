# Lecture 5 — Beurling–Deny & LeJan representation formulas

## Motivation: topology vs “exploration connectedness”
- Previously, “connectedness” was only in an *exploration/invariance* sense, not topological.
- Now we introduce a topology so it makes sense to talk about continuity, regularity, etc.

---

## Regularity (regular Dirichlet forms)
Assume:
- $(X,\tau)$ is **second countable**, **locally compact**, **Hausdorff**.
  - Then $X$ is **Polish** (separable + completely metrizable), hence the Borel $\sigma$-algebra $\mathcal B_\tau$ is **countably generated**.
  - In particular, $L^2(X,m)$ is separable (in this framework).
- $m$ is a **Radon measure** (locally finite / tight-type behaviour; $\sigma$-finite in the notes).
- $(\mathcal E, D(\mathcal E))$ is a Dirichlet form on $L^2_m$ and admits a core $\mathcal C\subseteq D(\mathcal E)$, which is:
	- $\mathcal C$ is dense in $(D(\mathcal E),\|\cdot\|_{\mathcal E^{1/2}_1})$, where $$\|u\|_{\mathcal E_1^{1/2}} := \big(\mathcal E(u)+\|u\|_{L^2}^2\big)^{1/2}.$$and $\mathcal C$ is dense in $C_0(X,\tau)$ in $\|\cdot\|_\infty$, where $$\|u\|_{\infty}:=\sup\{ |u(x)|:x \in X \}$$
		- when $u$ is continuous and $\|u\|_{p}\in(0,\infty)$ we can see this as $\lim_{ p \to \infty }\|u\|_{p},$ where $$\|u\|_{p}=\big(\int|u|^{p}d\mu\big)^{1/p}$$
		- $C_{0}\cap D(\mathcal E)$ is a special standard core giving an Urysohn algebra (good such functions)


Then $(\mathcal E, D(\mathcal E))$ is **regular** (w.r.t. $(X,\tau)$).

Remark: “regular forms are not enough … we can create trivial core”  
(i.e. regularity depends on the chosen topology / which continuous functions you insist on approximating).

---

## We need topological Lusin spaces (bigger setting than Polish)
A **topological Lusin space**: $(X,\tau)$ is the **Borel image of a compact metric space**.
- Can be seen as a generalisation of Polish spaces.
- Lets us work beyond the nicest locally-compact situations (while still controlling measurability).
- It can be seen as one up better from borel sets

---

## Better regularity to not get a trivial core by using Lusin, closed sets and the restricted domain $D(\mathcal E)_F$
- Let $(X,\tau)$ be a **Lusin space**:
- Take $m$ as $\sigma$-finite (not Radon like before)
- $(\mathcal E, D(\mathcal E))$ is a Dirichlet form on $L^2_{m}$
- Let $F\subset X$ be **closed**. Define
$$
D(\mathcal E)_F := \{ f\in D(\mathcal E):\ f|_F\in C(F)\ \text{(cont. on relative topology of F)},\ \ f\equiv0\ m\text{-a.e. on }F^c\}.
$$
Heuristic: functions that behave continuously on $F$ and vanish outside.

Remark: we can use this because of a theorem (find name for this theorem) that states that closed functions on set-closed $F$ can be extended continuously to the whole space $X$. 

Note: this way of defining regularity works for at least Banach spaces, but anything more crazy than Banach is also not considered practically, so it is good enough.

---

## Nests
A family $(F_k)_k$ of closed sets in $X$ is an **$\mathcal E$-nest** for $(\mathcal E, D(\mathcal E))$ on $L^2_m$ if
$$
\bigcup_k D(\mathcal E)_{F_k}\ \text{is dense in }(D(\mathcal E),\|\cdot\|_{\mathcal E^{1/2}_1}).
$$
Note: we **do not** require $\bigcup_k F_k = X$.

---

## Polar sets and quasi-everywhere
### Polar set
A set $N\subseteq X$ is **polar** if there exists an $\mathcal E$-nest $(F_k)_{k}$ such that
$$
N \subseteq \left(\bigcup_k F_k\right)^c.
$$
Heuristically: this is used as some small exception set in quasi definitions.

### Quasi-everywhere (q.e.)
A property $(P)$ holds **$\mathcal E$-q.e.** if it holds for all $x\in N^c$ for some polar set $N$.

---

## Quasi-open / quasi-closed / quasi-continuous
Fix some $\mathcal E$-nest $(F_k)$.

- $G\subseteq X$ is **quasi-open** if $G\cap F_k$ is open (relative to $F_k$) for all $k$.
- $F$ is **quasi-closed** if $F^c$ is quasi-open.
- $f:X\to\mathbb R$ is **$\mathcal E$-quasi-continuous** if $f|_{F_k}$ ($f$ restricted to $F_{k}$) is continuous for all $k$.

Intuition: the theory “does not see” the boundaries of the $F_k$’s.

We will replace the notion of a core with $\bigcup_{k}D(\mathcal E)_{F_{k}}$, which will be a good enough core to characterise what the topology sees.

---

## Capacity
For Borel $A\subseteq X$ define
$$
\mathrm{Cap}(A)
:=\inf\left\{\mathcal E_1(f): f\in D(\mathcal E),\ f\ge 1\ \mathcal E\text{-q.e. on }A\right\},
$$
where we had $\|.\|_{\mathcal E_{1}}:=\mathcal E + \|.\|^{2}_{L^2}$.

The core is dense in this, so we can approximate the norm.
### Sobolev example
For open set $U\subseteq\mathbb R^d$:
$$
\mathrm{Cap}^{1,2}(U)
:=\inf\left\{\|f\|_{W^{1,2}}^2:\ f\in C^\infty(\mathbb R^d),\ f\equiv 1\text{ (or e.g. }f\geq \mathbf{1}\text{)}\text{ on }U\right\}.
$$

### Fact
For Borel $N$:
$$
N\text{ is polar}\quad\Longleftrightarrow\quad \mathrm{Cap}(N)=0.
$$
(show this)
### Regular case simplification
Suppose $(\mathcal E,D(\mathcal E))$ is regular with core $\mathcal C$, then it is enough to test using $f\in\mathcal C$:
- for open $U$:
  $$
  \mathrm{Cap}(U)=\inf\{\mathcal E_1(f): f\in\mathcal C,\ f\equiv \mathbf{1}\text{ on }U\},
  $$
- for Borel $A$:
  $$
  \mathrm{Cap}(A)=\inf_{A\subseteq U,\ U\ \mathrm{open}}\mathrm{Cap}(U).
  $$
Remark: a notion of continuity is only possible when talking about a function in the core, not a function. (as core has topology?)

(Analogy: Choquet theory.)

---

## Example: Brownian capacity of a point
Let $\mathcal E=\mathcal E^{BM}$ on $\mathbb R^d$, and $A=\{0\}\subseteq U$.

Use radially symmetric cutoffs $f_n$ supported in a tiny ball, with a steep transition layer.
One gets an estimate of the form
$$
\mathcal E_1^{BM}(f_n)\ \lesssim\ n^2\,\Omega_d\,n^{-d} \ +\ (2n^{-1})^d\,\Omega_d \ \longrightarrow\ 0
\quad\text{if }d\ge 3,
$$
so $\mathrm{Cap}(\{0\})=0$ in $d\ge 3$ (points are polar).

Note:
- $n^{2}$ is square due to Sobolev norm
- $2n^{-1}$ is from $L^{2}$ norm

![[l5-fig-capacity-bump-singleton.png]]
Above is simple visual for $d=1$.

Notes/exercises from the page:
- $\mathrm{Cap}(\{0\})>0 \iff d=1$. (show this)
- In $d=2$ you need a sequence decaying more slowly (logarithmic profile) than $\mathcal{E}^{BM}_{1}(f_{n})$.
- From above you can see Sobolev functions are specified at every point (continuously), depending on $d$. (Co-haussdorf property & polar sets cause this?)

---

## Quasi-regularity (definition)
$(\mathcal E, D(\mathcal E))$ on $L^2_m$ is **quasi-regular** if:

- (QR1) $\exists$ an $\mathcal E$-nest consisting of $\tau$-compact sets.  
	- Intuitively: used as a replacement for “vanishing at infinity” / replacing $C_0$.

- (QR2) $\exists\ \mathcal C\subset D(\mathcal E)$, $\mathcal E_1^{1/2}$-dense in $D(\mathcal E)$, such that every $f\in\mathcal C$ has an $\mathcal E$-quasi-continuous $m$-version $\tilde f$.
	- Intuitively: $\exists$ a dense linear subspace of domain classes and each representative of a class is quasi-continuous.

- (QR3) $\exists$ a polar set $N$ and a countable family $\{f_n\}\subseteq D(\mathcal E)$ such that each $f_n$ has a quasi-continuous version $\tilde f_n$ and $\{\tilde f_n\}$ separates points in $X\setminus N$.
	- Intuitively: used to say that we have sufficiently many functions to cover the set and that we thus are quasi-continuous outside a polar set.

Notes:
- “We can’t test on polar sets” but the Markov process will never see polar sets (as probability of visiting those exactly should be zero).
- Take $F_{k'}\cap F_{k}$ compact for $F_{k'}$ being from some other nest than $F_{k}$, then WLOG (without loss of generality), take nests to be increasing and compactness is preserved.
	- From this fact we can use other nests for each quasi-regularity condition and still have that if all prove to be true for different nests that we have a quasi-regular $(\mathcal E, D(\mathcal E)).$

---

## Quasi-homeomorphism
(Comparing a quasi-regular form to a regular one.)

Intuitively: this is the notion of isomorphism we had for regular forms, but this now is for quasi-regular forms. Isomorphism would not have been usefull / worked for quasi-regularity.

Take $(\mathcal E, D(\mathcal E))$ on $L^{2}_{m}$ and take another form $(\mathcal E', D(\mathcal E'))$ on $L^{2}_{m'}$ (with a possibly different measure).
Then:
- $\exists$ a $\tau$-compact $\mathcal E$-nest $(F_k)$ in $X$,
- $\exists$ a $\tau'$-compact $\mathcal E'$-nest $(F_k')$ in $X'$,
- $\exists$ a measurable map
  $$
  j:\bigcup_k F_k \to \bigcup_k F_k'
  $$
  that is injective and measurable (such that $j:F_k\to F_k'$ is a homeomorphism for each $k$?),
- **measure transport**: $j_{\#} := m\circ j^{-1}=m$ (“move measure”),
- **form transport**: $D(\mathcal E)$ corresponds to pullbacks $u\circ j$ and
  $$
  \mathcal E(u\circ j)=\mathcal E'(u)
  $$
  on the nests,
	- i.e., $$
\begin{equation}
  \mathcal{E}=j^{*}\mathcal{E}' :=
    \begin{cases}
      D(\mathcal E) =\{ f' \circ j : f \in D(\mathcal E') \}\\
      \mathcal{E}(f' \circ j)=\mathcal{E}'(f)
    \end{cases}       
\end{equation}
$$
Define polar sets:
$$
N:=\left(\bigcup_k F_k\right)^c,\qquad
N':=\left(\bigcup_k F_k'\right)^c.
$$

![[l5-fig-quasi-homeomorphism-diagram.png]]

Note: this $j$ need only be continuous on the nests, not the whole space.
### Theorem (Z. Q. Chen ’93; see Chen–Ma–Röckner ’94)
$(\mathcal E,D(\mathcal E))$ is quasi-regular  
$\Longleftrightarrow$  
$(\mathcal{E},D(\mathcal{E}))$ is a quasi-homeomorphic form to a **regular** Dirichlet form $(\mathcal E',D(\mathcal E'))$.

(See FOT Appendix A: proof via Gelfand transform.)

---
Now what will happen is we will instead of the original space study a space that is some (nasty to interpret) locally compact space. 

We just study it through translating the original space into this locally compact one. 

Can we then still relate what we find back to everything on the original space for which we wanted to study.

For example, in the original space we could have the question of what will happen when we start in the polar set. On the new locally compact space this polar set is not seen. So how will we solve these kind of questions?

---

## Example: Neumann BM on a “pinched” domain (touching disks)
Example picture: two disks touching in a point (or joined by an infinitesimal neck).

This example shows what happens when $d=2$. (earlier we looked at $d=1$ and $d\geq3$)

In $d=2$ a point can be polar, so (q.e.) you can “remove the touching point” and split the space into two components.

![[l5-fig-touching-discs-quasihomeo.png]]

As seen above through a careful pick of nests we can get a translation using quasi-homeomorphism such that the discs seperate. 

In this example we have a brownian motion with Neumann boundary, where the boundary is included. This we denote by saying we have $\mathcal{E}^{BM,N}$ on $\Omega =\overline{\Omega}$.

Typical nest idea:
Define
$$
F_k := \left(\overline {B_1(-1)}\cup \overline{B_1(1)} \right)\setminus B_{1/k}(0)
$$
and
$$F_{k}' := \left(\overline {B_1(-1)}\setminus B_{\frac{1}{k}}(0)- \{ 1 \}\right)\cup\left(\overline {B_1(1)}\setminus B_{\frac{1}{k}}(0)+ \{ 1 \}\right)$$
The latter definition we use a Minkowski sum.
Intuitively thus remove a tiny ball around the pinch point.

Goal: show $D(\mathcal{E}^{BM,N})_{F_k}$ is $\mathcal E_1^{1/2}$-dense in $D(\mathcal{E}^{BM,N})=H^1(\Omega)$.

Here $D(\mathcal{E}^{BM,N})_{F_k}\supseteq C^{\infty}_{c}(F_{k})\supseteq C^{\infty}_{c}(\mathring{F_{k}})$, where $\mathring{F_{k}}$ is the interior relative to $\Omega$, not to $L^2$.

Right-hand sketch on the page is a boundary/traces cutoff picture:
![[l5-fig-boundary-1-0.png]]
Interpretation: ...

A density follows as $\mathrm{Tr}:C^{\infty}_{c}(\mathring{F_{k}})\to L^{2}(\partial \Omega)$ is a surjective map.
And note that a $H^1(\Omega)$ function is a trace.

We shrink the inner boundary (trace) to zero by $k\to \infty$.

It will be (zero) in the sobolev $H^1$-norm, not just the $L^2$-norm.

We need to approximate an arbitrary function in $H^{1}(\Omega)$

---

## Support of a measure (topological Lusin remark)
- $(X,\tau)$ being a topological Lusin space ($\implies$ $(X,\tau)$ is hereditary Lindelöf) $\implies$ every Borel measure has support.

Define
$$
\mathrm{supp}\,m := \bigcap\{F\subset X: F\text{ closed and } m(X\setminus F)=0\}.
$$
$m$ has support if $m(X\setminus \mathrm{supp}\,m)=0$.

Because we look at a topological lusin space every borel measure has support. This means we cant have support zero.

There exists measures with support zero in general.

---

## Locality vs strong locality
A quasi-regular Dirichlet form is:

- **local**: if $\mathcal E(f,g)=0$ whenever $f\equiv 0$ on $\mathrm{supp}(g)$ for $f,g \in D(\mathcal{E})$.
- **strongly local**: if $\mathcal E(f,g)=0$ whenever $f\equiv \mathrm{constant}$ on $\mathrm{supp}(g)$ for $f,g \in D(\mathcal{E})$.

Important note: because the earlier definition of support does not define the support of a class of functions (not continuous) and because we cant have that the measure has support zero we actually define:
$$\mathrm{supp}(g):=\mathrm{supp}[gm]$$

Example:
$$
\mathcal E(f,g)
:= \int_\Omega \nabla f\cdot\nabla g\,d\lambda_\Omega + \int_\Omega f g\,d\lambda_{\Omega}\text{ is local}
$$
and
$$\mathcal E(f,g)
:= \int_\Omega \nabla f\cdot\nabla g\,d\lambda_\Omega\text{ is strongly local}$$
Note: $\int_\Omega f g\,d\lambda_{\Omega}$ corresponds to a killing part (form is then still local).

Jump form example:
$$
\mathcal E(f,g):=\int_{\Omega}(f(x)-f(y))(g(x)-g(y))\,d\lambda^{\otimes2}(x,y),
$$
which is neither local or strongly local (“we jump from $x$ to $y$, and we can't determine if we jumped by looking just around a single point, we have to look at where we landed too”).

Heuristics from the page:
- $\mathcal E^{BM}$ is local
- $\mathcal E^{BM}$ is strongly local $\Leftrightarrow$ local + conservative (no killing).

Fact in general: local + conservative $\Rightarrow$ strongly local (not $\iff$)

---

## Beurling–Deny decomposition

### Theorem (Beurling–Deny)
If $(\mathcal E, D(\mathcal E))$ is a **regular** Dirichlet form, then
$$
\mathcal E(u,v)
=
\mathcal E^{(c)}(u,v)
+
\iint_{X\times X\setminus\Delta}(u(x)-u(y))(v(x)-v(y))\,dJ(x,y)
+
\int_X u v\,dK,
$$
where:
- $\mathcal E^{(c)}$ is a symmetric strongly local form on (a dense subspace of) $D(\mathcal E)\cap C_0(X)$ (“continuous/local part”),
- $J$ is a symmetric nonnegative Radon measure on $X\times X\setminus\Delta$ (jump measure; exclude diagonal to avoid jumping to itself),
- $K$ is a nonnegative Radon measure on $X$ (killing measure).

Uniqueness: $(\mathcal E^{(c)}, D(\mathcal{E})\cap C_{0}(X,\tau)), J, K$ are uniquely determined by $(\mathcal E, D(\mathcal E))$.

Margin note: $\mathcal E^{(c)}$ by itself need not be closed on that subspace, thus not lower semi-continuous, so it is not automatically a Dirichlet form on its own.

---
