---
title: "Lecture 2 — Testing, semigroups, resolvents, and closed/closable forms"
course: "Analytical Markov chains via Dirichlet forms"
lecture: 2
tags: [markov-processes, semigroups, resolvent, hille-yosida, closed-forms, feller, l2-theory]
---
# Lecture 2 — Testing, semigroups, resolvents, and closed/closable forms

## 1. Idea of testing (what space of test functions?)
Let $X$ be a Markov process with state space $S$.

Instead of talking directly about $X_t$, we often study properties of the map of **observables**
$$
t\mapsto f(X_t)\quad\text{for } f:S\to\mathbb R,
$$
instead of properties of $X$ because $S$ can be “very different types of spaces”.

**Remark (from notes):** $L^2_{m}$ is “too large” as a space of test functions:
- we lose measure-zero sets,
- it does not "see" points in $S$.

### Example: reflected Brownian motion on a smooth domain
Example object: $(\mathcal E, H^1(\Omega))$ as the form of reflected BM on a smooth $\Omega\subseteq\mathbb R^d$.

Test with something like
$$
H^1(\Omega)\cap C_b(\overline\Omega)
$$
but “alone $H^1(\Omega)$ not good enough” since these are *classes* of functions (equivalence a.e.).

### Two competing options (Hilbert vs Feller viewpoints)

**Option 1 (Hilbert / $L^2$-side):**
Define a semigroup:
$$T_t^{L^2}: H^1(\Omega)\cap C_b(\overline\Omega)\to H^1(\Omega)\cap C_b(\overline\Omega),$$
which is a continuity preserving map, is bounded on $L_{\lambda_{\Omega}}^2$ w.r.t. $L^2$ norm on a Banach space and extends to $L_{\lambda_{\Omega}}^2$ 

**Option 2 (Feller / $C_0$-side):**
Test on $C^1_b(\overline\Omega)$ and define semigroup:
$$
T_t^{C_b}: C^1_b(\overline\Omega)\to C^1_b(\overline\Omega),
$$
which is bounded on $C_{b}(\overline{\Omega})$ w.r.t. $\|\cdot\|_\infty$ (Banach-space / supremum norm) and extends to $C_{b}(\overline{\Omega})$.

### These choices can give different generators
These two constructions can give genuinely different semigroups/generators, *even if the test space is dense* somewhere as we see that $C_{b}$ is actually dense in $L^2$ and it gives a different generator.

- Kernel representation viewpoint: the two semigroups can be different (possibly even on a dense set).
- We know $C_b$ is dense in $L^2$, but that does **not** force the associated semigroups to coincide.
- **However:** if $\partial\Omega$ is **Lipschitz**, then “they are equal”.

### Example sketch: “room with passages”
![[l2-fig-room-with-passages.png]]

In this example, “everything shrinks” in domain $\Omega \subseteq \mathbb{R}^2$.
Example is for $L^p$.



then $\sigma(\Delta^{L^p})$ depends on $p$ and it could happen the spectrum is **not discrete**, even if the domain is compact.  
Conclusion in notes: “bad → thus we must choose which to use”.

---

## 2. Why we choose the Hilbert ($L^2$) setting
“We choose Hilbert: functionals are easier than operators; Feller harder.”

### Three trivial examples (in $(S,\mathcal E,m)$ language)

1) **No motion**
$$
\mathcal E\equiv 0,\qquad L\equiv0,\qquad T_t=\mathbb{1}_{L^2},
$$
where $\mathbb{1}_{L^{2}}:=id:L^{2}\to L^{2}$

2) **Pure killing**
Notes: $\mathcal E=\|\cdot\|_{L^2}^2$ and $L\equiv \mathbb{1}_{L^2}$, hence
$$
T_t = e^{-t\mathbb{1}_{L^2}}=e^{-t}\,_{L^2}.
$$

$e^{-t}\mathbb{1}_{L^2(S)}\oplus (1-e^{-t})\mathbb{1}_{\{\partial\}}$ (boundary $\delta$).  


3) **Instantaneous killing**
$$
\mathcal D(\mathcal E)=\{0\},\qquad
\mathcal E(u)=\begin{cases}
+\infty,& u\neq 0,\\
0,& u=0.
\end{cases}
$$
$L^2$ at a single point is $\partial$ (cemetery).

---

## 3. Operators on a Hilbert space

Let $H$ be a Hilbert space over $\mathbb R$ (or $\mathbb C$).

A (possibly unbounded) operator is
$$
(L,\mathcal D)\quad\text{with}\quad L:\mathcal D\to H,\;\; \mathcal D\subseteq H.
$$

- Possibly $L$ is **unbounded**.
- Typically $\mathcal D\subset H$ and $L$ is not continuous on all of $H$.

Assumption: $\mathcal D$ is dense in $H$.

**Remark:** If $(L,\mathcal D)$ is bounded, it extends uniquely to a bounded operator $L:H\to H$.

Now assume: “extend wherever possible”

Unbounded operators can have multiple extensions (e.g. at least “Neumann” and “Dirichlet” extensions in PDE contexts). It then extends to some $\mathcal D'$, where $\mathcal D \subseteq \mathcal D' \subset H$.

Notation: If $L$ is injective, then $L^{-1}$ is defined on $L(\mathcal D)\subseteq H$ by the obvious way.

---
### Definition contraction
A contraction $B:H\to H$ satisfies
$$
\|B\|_{\mathrm{op}}\le 1
$$
(note that we define by ≤, not <).

---

## 4. Resolvent set and spectrum

### Definitions
The **resolvent set**:
$$
\rho(L):=\Bigl\{\alpha\in\mathbb C:\; (\alpha-L):\mathcal D\to H\text{ injective},\; (\alpha-L)\mathcal D\text{ dense in }H,\; (\alpha-L)^{-1}\text{ bounded}\Bigr\}.
$$

The **spectrum**:
$$
\sigma(L):=\mathbb C\setminus\rho(L),
$$
and it “contains eigenvalues of $L$”.

For $\alpha\in\rho(L)$, the **resolvent operator** is
$$
G_\alpha := (\alpha-L)^{-1}:H\to H.
$$

### Proposition Resolvent identity (M-R I 1.3 )
1. For $\alpha,\beta\in\rho(L)$:
$$
G_\alpha - G_\beta = (\beta-\alpha)\,G_\alpha G_\beta = (\beta-\alpha)\,G_\beta G_\alpha,\qquad \text{which is the 1st resolvent identity.}
$$
2. If $\mathbb{R}^{+}\subset \rho(L)$ and $\alpha G_{\alpha}$ is a contraction on $H$, then
$$\lim_{\alpha\to\infty}\alpha G_\alpha u = u \quad \text{in }H,\;\forall u\in H,\qquad (\text{sometimes written as }H-\lim)$$
$$\text{which is equivalent to }\lim_{\alpha\to\infty}||\alpha G_{\alpha u}- u||_{H}=0,\text{ i.e., we have continuity in the strong topology.}$$
### Strongly continuous contraction resolvent
A family $(G_\alpha)_{\alpha>0}$ is a **strongly continuous contraction resolvent** if:

1. **Strong continuity at infinity:**
$$
\lim_{\alpha\to\infty}\alpha G_\alpha u = u \quad \text{in }H,\;\forall u\in H,
$$
i.e. $\lim_{\alpha\to\infty}\|\alpha G_\alpha u-u\|_H=0$ (strong topology).

2. **Contraction bound:**
$$
\|\alpha G_\alpha\|_{\mathrm{op}}\le 1.
$$
Intuitively for sufficiently large $\alpha$ we get something invertible.

3. **1st Resolvent identity** holds.



---

## 5. Closed operators

$(L,\mathcal D)$ on $H$ is **closed** if $\mathcal D$ is complete with respect to the **graph norm**
$$
\|u\|_{\text{graph}} := \|u\|_H+\|Lu\|_H.
$$
Comment in notes: if $L$ is unbounded, this is a stronger thing.

Notation: write $(L,\mathcal D(L))$ to indicate it is closed.

Examples (as written):
- $(-\Delta, C_c^\infty)$ not closed
- $(-\Delta,\;H^2)$ is closed (Neumann)
- $(-\Delta,\;H^2\cap H_0^1)$ is closed (Dirichlet)

### Proposition: Correspondence (M-R I I.5 in your notes)
There is a 1–1 correspondence between:
- closed, densely defined $(L,\mathcal D(L))$ with $\mathbb R^+\subset\rho(L)$  
and
- strongly continuous contraction resolvents $G_{0}:=(G_\alpha)_{\alpha>0}$ on $H$,

given by
$$
G_\alpha = (\alpha-L)^{-1}.
$$

---

## 6. Strongly continuous contraction semigroups and generators

### Definition: strongly continuous contraction semigroup
A family $T=(T_t)_{t\ge 0}$ on $H$ such that:

1. **Strong continuity:**
$$
\lim_{t\downarrow 0}T_t f = f \quad\text{in }H,\;\forall f\in H.
$$

2. **Contraction:**
$$
\|T_t\|_{\mathrm{op}}\le 1 \quad \forall t>0.
$$

3. **Semigroup property:**
$$
T_{s}\circ T_t=T_{s+t}=T_{t}\circ T_s.
$$

Sometimes define $T_0:=\mathbb{1}_H$ additionally.

### Generator
For the generator of $T.:=(T_{t})_{t\geq_{0}}$, define the domain
$$
\mathcal D(L):=\left\{f\in H:\exists\; \text{$H$-}\lim_{t\downarrow 0}\frac{1}{t}(T_tf-f)\right\},
$$
and for $f\in\mathcal D(L)$,
$$
Lf := \left.dt\right|_{t=0}T_tf,
$$
where the derivative is taken **in $H$, i.e., the $H-dt$**.

Margin note: “norm change makes the generator another generator” (generator depends on the topology/space).

---

## 7. Hille–Yosida theorem (M-R I 1.12)

Roughly, a 1–1 correspondence between generators and strongly continuous contraction semigroups:

Assume:
- $(L,\mathcal D)$ is densely defined
- $\mathbb R^+\subset\rho(L)$
- resolvent is a contraction in the sense
$$
\|\alpha(\alpha-L)^{-1}\|_{\mathrm{op}}\le 1 \quad \forall \alpha>0.
$$

Then $L$ generates a strongly continuous contraction semigroup on $H$, and conversely under the additional assumptions that if we go from generator to semigroup that $L$ is closed and if we go from semigroup to generator we assume additionally that using $\mathcal D(L)$ that it is closed in graph norm.

---

## 8. Generator ↔ semigroup ↔ resolvent 

Diagram:

![[l2-fig-hy-correspondence.png]]

Key formulas written (we are still missing energy functionals in this diagram):

- Strongly continuous contraction resolvent to (Laplace transform of) strongly continuous contraction semigroup:
$$
G_\alpha := \int_0^\infty e^{-\alpha t}T_t\,dt.
$$
- Recover SCC semigroup from SCC resolvent:
$$
T_t := \lim_{\alpha\to\infty} e^{\,t(\alpha G_\alpha - \mathbb{1}_H)}.
$$



- SCC semigroup to generator operator $(L, \mathcal{D}(L))$ for which $\mathbb{R}^{+}\subseteq \rho(-L)$ and $||\alpha(\alpha-L)^{-1}||_{op}\leq 1$ is done by Hille-Yosida, setting:
$$T_{t}:=\sum_{n\geq_{0}}\frac{1}{n!}(-t)^{n}L^{n}=e^{-tL}$$
- Recover same type generator from SCC semigroup by Hille-Yosida setting:
$$L:=d_{t}|_{t\geq_{0}}T_{t},\qquad \mathcal{D}(L):=\{\exists dt_{t}|_{t=0}\}$$



- SCC resolvent to generator operator $(L, \mathcal{D}(L))$ for which $\mathbb{R}^{+}\subseteq \rho(-L)$ and $||\alpha(\alpha-L)^{-1}||_{op}\leq 1$ is done by setting:
$$L:=(\alpha-G_{\alpha})^{-1}$$
- Recover same type generator from SCC resolvent by setting:
$$G_{\alpha}:=(\alpha - L)^{-1},\quad \alpha>0$$

---
### Remark on positive spectrum
We have positive $<u,Lu>_{H}\geq 0$.
This gives $<u,\lambda u>_{H}\geq0\implies \lambda\geq0\implies \text{spectrum is positive (or non-negative).}$

---

## 9. Functional calculus viewpoint (bounded case)

We could also use continuous functional calculus instead of $T_{t}:=\sum_{n\geq_{0}}\frac{1}{n!}(-t)^{n}L^{n}=e^{-tL}$, to go from generator (operator) to SCC semigroup.

Continuous functional calculus gets you a continuous function from an operator.

Assume $A$ is bounded. Then $\sigma(A)$ is compact.

We can compute
$$
I_H,\, A,\, A^2,\, A^3,\dots
$$
so define $p(A)$ for a polynomial $p$.

By Stone–Weierstrass, this extends to continuous functions on the spectrum:
$$
f(A)\quad\text{for } f\in C_{c}(\mathbb{C}) \text{ (or }C_b(\sigma(A))\text{)}.
$$

Note: “also possible by very careful consideration for unbounded”.

---

## 10. Self-adjointness and positivity (notes emphasis)
Assume from now on $A:=L$.

Notes say: Assume now $L,T,G$ are self-adjoint on $H$, i.e.
$$
A=A^*,
$$
so in particular
$$
\langle u, Av\rangle_H=\langle Au, v\rangle_H
$$
($A$ symmetric).

Non-symmetric versions of the following theorems can be done and is shown in M-R

There’s a boxed remark about **positivity** and “spectrum is positive”.

Same as earlier remark we have the standard implication:  
- if $\langle u,Lu\rangle_H\ge 0$ then $\sigma(L)\subset[0,\infty)$.

---

## 11. Closed quadratic forms (energy functionals)

A (quadratic) form:
- symmetric bilinear, nonnegative
$$
\mathcal E: \mathcal D\times \mathcal D \to \mathbb R,\qquad \mathcal E(u,u)\ge 0.
$$

Extend as a functional on $H$ by
$$
\mathcal E(u)=
\begin{cases}
\mathcal E(u,u),& u\in\mathcal D,\\
+\infty,& u\notin\mathcal D.
\end{cases}\quad \geq 0
$$

### Closedness
“Closed” here then means $\mathcal D$ is complete in the graph norm
$$
\|u\|_{\mathcal E_\alpha} := \sqrt{\mathcal E(u)+\alpha\|u\|_H^2}
$$
for some $\alpha>0$ (and then for all $\alpha>0$, “show”).

---

## 12. Closable quadratic forms

- We notate $(\mathcal E,\mathcal D(\mathcal E))$ always closed (i.e. after taking the closure), just like earlier.

Example motivating the issue:
$$
\mathcal E(u)=\int |\nabla u|^2\,d\mathrm{Leb},
\quad \text{defined first on } \mathcal D=C_c^\infty(\overline\Omega),
$$
then one wants to extend toward $W^{1,2}(\Omega)$, but “we do not know from start how to do $dt$ in $W^{1,2}(\Omega)$” → closability matters.

We then have $W^{1,2}(\Omega)=\mathcal D(\mathcal E)$.

### Definition (as in notes)
$\mathcal E:\mathcal D^{\times2}\to\mathbb R$ symmetric bilinear, nonnegative is **closable** if:

1. The extended functional $\mathcal E:H\to\mathbb R\cup\{+\infty\}$ is **strongly** lower semicontinuous.

2. $\mathcal E:H\to\mathbb R\cup\{+\infty\}$ is **weakly** lower semicontinuous (in weak topology on $H$).

3. **Closability criterion:**
- If $(u_n)_{n}\subset\mathcal D$ is $\mathcal E$-Cauchy (w.r.t. seminorm) and
$$
u_n \to 0\ \text{in }H,
$$
then
$$
\mathcal E(u_n)\to 0.
$$
- Equivalently (as written):
$$
\mathcal E(u_n-u_m)\to 0\ (n,m\to\infty),\;\; u_n\to 0\ \Rightarrow\ \mathcal E(u_n)\to 0.
$$

- Think of when this does not hold.

- Side note: “Always $H$ is separable (otherwise very complicated).”

4. There is also a statement in terms of the **identical embedding**
$$
\iota:\mathcal D\to H,
$$
extending **uniquely** to a function on the abstract completion given by the core $\mathcal D$ and the $\|\cdot\|_{\mathcal E_\alpha}$-norm ($\mathcal{E}^\frac{1}{2}_{\alpha}$).

- We can write this abstract completion as $\overline{\mathcal{D}}^{\mathcal{E}^\frac{1}{2}_{\alpha}}$

- The unique extending function of the identical embedding is then $\overline{\mathcal{D}}^{\mathcal{E}^{\frac{1}{2}_{\alpha}}}\to H$


Final remark: For convex sets in $H$ there is a theorem that, weakly closed $=$ strongly closed.

---

## 13. From energy functional to generator (theorem picture)

![[l2-fig-form-operator-diagram.png]]

From closed densely defined generator (operator) to energy form, being a closed densely defined quadratic form:
- The form domain can be described via a square root of the operator:
$$
\mathcal D(\mathcal E):=\mathcal D(\sqrt{-L})\quad\text{(or }\sqrt{L}\text{ depending on sign convention)}.
$$

- The bilinear form is then given by
$$
\mathcal E(u,v)=\langle u,Lv\rangle_H,
$$
and by self-adjointness assumption we can show this inner product is symmetric.



Now to go from $(\mathcal{E},\mathcal{D}(\mathcal{E}))$, densely defined, closed quadratic form to a generator $(L,\mathcal{D}(L))$, closed densely defined:
- The operator domain:
$$
\mathcal D(L)=\left\{u\in\mathcal D(\mathcal E): v\mapsto \mathcal E(u,v)\ \text{is continuous on }\mathcal D(\mathcal E)\right\}.
$$

- Then there exists $Lu\in H$ such that
$$
\langle Lu, v\rangle_H = \mathcal E(u,v)$$
(“by Markov representation theorem for the form”).

---

## 14. Toward kernels / Markov processes: sub-Markovianity
For “Dirichlet extension” (your words): to go from semigroups to **kernels** we need the semigroup to map
- probabilities to probabilities (at least in some weak sense),
- **positive functions to positive functions**,

and we need **sub-Markovianity**.

