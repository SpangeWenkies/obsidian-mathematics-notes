
# Theorem: Fully extended Beurling-Deny representation theorem

**Type:** #theorem  

## Setup
$X,m$ satisfy (1.1.7), i.e., the topological assumption that
- $X$ is a locally compact separable metric space
	- separable is a topological property, it means $X$ contains a countable dense subset
		- it gives you a countable base for metric spaces
		- dense subset means its closure is all of $X$
		- gives useful countability properties like second countability
	- locally compact
		- compactness
			- a subset of a space is compact if every open cover of the subset has finitely many subcovers
			- compact = complete + totally bounded
			- closed can also be that it is complete in the graph-norm $\|u\|_{\mathcal E_\alpha^{1/2}} := \sqrt{\mathcal E(u)+\alpha\|u\|_H^2}$
			- in finite dim euclidean compact = closed & bounded
			- compact -> no way for sequence to escape to infinite distance or into a hole or edge or into infinite dimensions
			- compactness often allows for locally defined properties to be extended to global properties 
		- locally compact if every point has a compact neighbourhood
			- for every point there exists an open set in which it is contained that has its closure be compact
			- even if the whole space is not compact, zooming around the point makes it seem compact
		- counter-example: infinite dimensional Banach spaces like infinite dimensional Hilbert spaces are not locally compact as closed balls are not compact, this is one of the reasons we go towards quasi-regularity.
- $m$ is a positive Radon measure on $X$ s.t. $\text{supp}[m]=X$
	- i.e., $m$ is a non-negative Borel measure on $X$ finite on compact sets and strictly positive on non-empty open sets.
	- $\text{supp}[m]$
		- Notation: For an $m$-measurable function $u$, the support $\text{supp}[u\cdot m]$ of the measure $u\cdot dm$ is denoted by $\text{supp}[u]$. 
		- if $u\in C(X)$ then $\text{supp}[u]$ is just the closure of $\{ x\in X:u(x)\neq 0 \}$
		- $\text{supp}[m]$ can be defined two equivalent ways:
			- Complement-of-largest-zero-open-set definition $\text{supp}[m]:=X\setminus \bigcup \{ U\subset X:U\text{ is open and }m(U)=0 \}$
			- Neighbourhood characterisation: $x \in \text{supp}[m]\iff m(U)>0, \forall \text{ open neighbourhoods }U \owns x$, and $x\not\in \text{supp}[m]\iff \exists \text{ an open set }U \owns x\text{ with }m(U)=0.$ 
	- Radon measure:
		- locally finite: $m(K)<\infty$ for every compact $K\subset X$, i.e., never infinite mass in a compact region in $X$.
		- inner regularity: for every Borel set $A\subset X$, $m(A)=\sup\{ m(K):K\subset A,K\text{ compact} \}$, i.e., a measure of a Borel set is determined by its compact subsets.
		- outer regularity: for every Borel set $A\subset X$, $m(A)=\inf\{ m(U):U\subset A,U\text{ open} \}$, i.e., a measure of a Borel set is determined by its open supersets.
		- intuition:
			- no mass in topological pathological ways
			- you can capture almost all mass of a set by taking a compact chunk in it
			- you can cover sets by taking open neighbourhoods whose mass gets arbitrarily close from above
			- mass in compact (small/bounded) regions is always finite
		- why Radon?
			- we need $C_{0}(X)$ to interact with measures how we want it to (Riesz-Markov repr. th.)
			- vague convergence works cleanly
			- support behaves as expected
			- $L^2(X;m)$ is local in the sense that compact regions have finite mass
	- why positive? -> to represent mass/size/probability

$C(X)$ is the space of all real continuous functions on $X$.
Subspace $C_{0}(X)=\{ u\in C(X) : \text{supp}[u]\text{ is compact} \}$.

A core $\mathcal{C}$ of a symmetric form $\mathcal{E}$ is a subset of $\mathcal{D}(\mathcal{E})\cap C_{0}(X)$ s.t. it is $\|.\|_{\mathcal{E}_{1}^{1/2}}$-dense in $\mathcal{D}(\mathcal{E})$ and $\|.\|_{\infty}$-dense in $C_{0}(X)$, where
$$\|u\|_{\mathcal E_1^{1/2}} := \big(\mathcal E(u)+\|u\|_{L^2}^2\big)^{1/2}\text{ and }\|u\|_{\infty}:=\sup\{ |u(x)|:x \in X \}.$$
$\mathcal{D}(\mathcal{E})\cap C_{0}(X)$ is a special standard core when $\mathcal{E}$ is regular.

Standard core: $\mathcal{C}$ is a dense linear subspace of $\mathcal{D}(\mathcal{E})\cap C_{0}(X)$, i.e., for any real $\epsilon>0, \exists$ a real function $\phi_{\epsilon}(t)$ s.t. 1.1.5 is satisfied s.t. $\phi_{\epsilon}(u)\subset \mathcal{C}$ whenever $u\subset\mathcal{C}.$

Special standard, when additionally: $\mathcal{C}$ is a dense subalgebra of $C_{0}(X)$, i.e., for every compact set $K$ and relatively compact open set $G$ with $K\subset G$, $\mathcal{C}$ admits an element $u$ s.t. $u\geq0$ and $u=1$ on $K$ and $u=0$ on $X\setminus G$.

$L^2(X;m)$
- m is nonnegative s.t. the space can be defined by the norm which is actually a norm

Regular Dirichlet form: $\mathcal{E}$ is regular if it possesses a core $\mathcal{C}$, that is iff $\mathcal{D}(\mathcal{E})\cap C_{0}(X)$ is a core of $\mathcal{E}$.

Symmetric form

A symmetric form $\mathcal{E}$ has the local property if:
- $u,v\in \mathcal{D}(\mathcal{E})$, $\text{supp}[u]$ and $\text{supp}[v]$ are disjoint compact sets $\implies \mathcal{E}(u,v)=0$
and strongly local if:
- $u,v\in \mathcal{D}(\mathcal{E})$, $\text{supp}[u]$ and $\text{supp}[v]$ are compact, $v$ is constant on a neighbourhood of $\text{supp}[u]$ $\implies \mathcal{E}(u,v)=0$.

Beurling and Deny give a general representation theorem on regular Dirichlet forms. Afterwards after looking at energy forms and their local part we look at a transformation rule of those by LeJan.

An immediate consequence is then the Beurling-Deny expression for a local part $\mathcal{E}^{(c)}$ of form $\mathcal{E}$.

From now denote the domain of the dirichlet form $\mathcal{D}(\mathcal{E})$ by $\mathcal{F}$.

## Statement
Theorem 3.2.1:

Any regular Dirichlet form on $L^2(X;m)$ can be expressed for $u,v\in\mathcal{F}\cap C_{0}(X)$ as follows:
$$\mathcal{E}(u,v)=\mathcal{E}^{(c)}(u,v)+\int_{X\times X\setminus d}(u(x)-u(y))(v(x)-v(y))J(dx,dy)+\int_{X}u(x)v(x)k(dx).$$

Here $\mathcal{E}^{(c)}$ is a symmetric form with domain $\mathcal{D}(\mathcal{E}^{(c)})=\mathcal{F}\cap C_{0}(X)$ and it satisfies the strong local property, i.e., $$\mathcal{E^{(c)}}(u,v)=0\quad\text{for }u \in\mathcal{D}(\mathcal{E}^{(c)})\text{ and }v\in l(u),$$
where $$l(u)=\{ v\in \mathcal{D}(\mathcal{E}^{(c)}) :v\text{ is constant in a neighbourhood of supp}[u]\}.$$
$J$ (jumping measure) is a symmetric positive Radon measure on the product space $X\times X$ off the diagonal $d$.
$k$ (killing measure) is a positive Radon measure on $X$.

The $\mathcal{E}^{(c)},J,k$ are uniquely determined by $\mathcal{E}$.

Every normal contraction operates on form $\mathcal{E}^{(c)}$.
## Proof Idea
Proof has 3 parts.

#### I. Decomposition is unique:
From $$\mathcal{E}(u,v)=\mathcal{E}^{(c)}(u,v)+\int_{X\times X\setminus d}(u(x)-u(y))(v(x)-v(y))J(dx,dy)+\int_{X}u(x)v(x)k(dx)$$
it follows that $$\mathcal{E}(u,v)=-2\int_{X\times X}u(x)v(x)J(dx,dy),$$ for any $u,v\in \mathcal{F}\cap C_{0}(X)$ with disjoint supports.

By using that $\mathcal{E}$ is regular and using lemma 1.4.2 we see that the functions $\sum_{i=1}^{p}u_{i}(x)v_{i}(x)$ s.t. $u_{i},v_{i}\in \mathcal{F}\cap C_{0}(X)$, $\text{supp}[u_{i}]\cap \text{supp}[v_{i}]=\emptyset$ for $1\leq i\leq p$, constitute a dense subalgebra of $C_{0}(X\times X\setminus d)$.

From this we can conclude that a positive Radon measure $J$ on $X\times X\setminus d$ satisfying $$\mathcal{E}(u,v)=-2\int_{X\times X}u(x)v(x)J(dx,dy),$$ is uniquely determined by $\mathcal{E}$.

It is important that we have a Radon measure here, as by Riesz-Markov representation theorem this becomes uniquely determined. The output of Riesz-Markov is a locally finite + regular measure (thus Radon).

Now observe the equality $$\mathcal{E}(u,v)=\int_{X\times X\setminus d}(u(x)-u(y))(v(x)-v(y))J(dx,dy)+\int_{X}u(x)k(dx),$$ where $v\in \mathcal{F}\cap C_{0}(X)$ is a function identically equal to $1$ in a neighbourhood of $\text{supp}[u]$.
Since such a $v$ exists for any $u\in \mathcal{F}\cap C_{0}(X)$ by virtue of theorem 1.4.2, the above equality uniquely determines a positive Radon measure $k$. (again here Riesz-Markov representation theorem)

Now that measures $J$ and $k$ are proven to be uniquely determined, form $\mathcal{E}^{(c)}$ must be unique also.
#### II. Writing down measure $J$ as a vague limit:
First we start with the definition of vague limit as we'll use this in this part of the proof.

##### Definition of vague convergence
Let $Y$ be a locally compact Hausdorff space. 

All metric spaces are Hausdorff spaces and Hausdorff spaces are also second countable, so we could also take $Y$ to be a locally compact separable metric space, which is what we are working with.

In the proof we will see vague convergence where we take $Y=X\times X\setminus d$ or $Y=G_{l}$.

Let $\mathcal{M}_{+}(Y)$ be the set of positive Radon measures on $Y$.

Now a sequence (or net) $\mu_{n}\in\mathcal{M}_{+}(Y)$ converges vaguely to $\mu \in\mathcal{M}_{+}(Y)$ if $$\int_{Y}\phi d\mu_{n}\to \int_{Y}\phi d\mu\qquad ,\forall \phi \in C_{0}(Y).$$
Here we take compactly supported functions as this is important when the total mass $\mu_{n}(Y)$ could be infinite or when mass could escape to infinity, but we want the definition to capture what happens locally, i.e., the definition is such that we converge on every compact region even if mass might drift away globally.

##### Important example of the mass escaping to infinity
Take $Y=\mathbb{R}, \mu_{n}=\delta_{n}$. Then for any $\phi \in C_{0}(\mathbb{R})$, $\text{supp}[\phi]$ is on some bounded interval $[-R,R]$. Also for $n>R$, $\phi(n)=0$. Hence we get $$\int \phi d\delta_{n}=\phi(n)\to 0.$$
This means $\delta_{n}\to0$ vaguely.

Interpretation: on every fixed compact set, eventually there is no mass. The mass didn't "vanish", it escaped to infinity. Vague convergence treats that as the convergence to the zero measure.

This escape phenomenon is exactly why the proof will make use of vague convergence instead of weak convergence of probability measures. 

In weak convergence of probability measures you test against $C_{b}(Y)$ (bounded) which needs the notion of "tightness", while with vague convergence we test against $C_{0}(Y)$, and that works for Radon measures in controlling total mass.

If we'd have finite Radon measures then vague convergence + convergence of total mass is the same as weak convergence on $C_{0}(Y)$. But Beurling-Deny does not assume that total mass bounds globally.
##### Start of proof part

For this part of the prove, use the approximation form of $\mathcal{E}$, namely $\mathcal{E}^{(\beta)}$, given by equation 1.3.16 together with the positive Radon measure $\sigma_{\beta}$ on $X\times X$ determined by lemma 1.4.1 (and 1.4.7).

We then determine the limits of the next equations, where $u,v\in \mathcal{F}\cap C_{0}(X)$ and $\text{supp}[u]\cap \text{supp}[v]=\emptyset$, as follows:
$$\mathcal{E}^{(\beta)}(u,v)=-\beta \int_{X\times X}u(x)v(y)\sigma_{\beta}(dxdy)\to \mathcal{E}(u,v),\quad\text{as } \beta \to \infty$$
The above implies that there exists a unique positive Radon measure $J$ on $X\times X\setminus d$ that satisfies $$\mathcal{E}(u,v)=-2\int_{X\times X}u(x)v(x)J(dx,dy)$$
and that uniquely determined $J$ is the limit of the following:
$$\frac{\beta}{2}\sigma_{\beta}\to J,\quad \text{vaguely on }X\times X\setminus d\text{ as }\beta\to \infty$$
In fact we can see by the formula for the limit of $\mathcal{E}^{(\beta)}$ that the family $\{ \beta \sigma_{\beta}:\beta>0 \}$ of measures is uniformly bounded on each compact subset of $X\times X\setminus d$.

This makes it s.t. a subsequence $\beta_{n}\sigma_{\beta_{n}}$ converges vaguely on $X\times X\setminus d$ as $\beta_{n}\to \infty$ to a positive Radon measure $J$. And as $J$ satisfies the above equality and is shown to be unique we get the convergence of $\frac{\beta}{2}\sigma_{\beta}\to J$.

We can see that there is a subsequence that converges vaguely from the following statement:
If $Y$ is locally compact and second countable (which is always true for separable metric spaces), and $(\mu_{n})$ is a sequence of Radon measures s.t.
$$\sup_{n}\mu_{n}(K)<\infty \text{ for every compact }K\subset Y,$$
then $(\mu_{n})$ has a vaguely convergent subsequence.

In our proof we have $\mu_{n}$ is $\mu_{\beta}:=\frac{\beta}{2}\sigma_{\beta}$ and $Y:=X\times X\setminus d$

The uniformly bounded on compact sets condition above is also called locally bounded or bounded on compacts.
It gives that if $\phi \in C_{c}(Y)$ has $\text{supp}[\phi]\subset K$, then $$|\int \phi d\mu_{n}|\leq\|\phi\|_{\infty}\mu_{n}(K)\leq\|\phi\|_{\infty}\sup_{n}\mu_{n}(K)<\infty,$$ so for each test function $\phi$, the sequence of real numbers $\int \phi d\mu_{n}$ is bounded. So bounded sequences of real numbers always have convergent subsequences.

We need these measures with that condition to also be Radon measures as
- Radon has local finiteness on compacts built in, this ensures restrictions $\mu_{n}|_{K}$ are finite measures and integrals $\int_{K}\phi d\mu_{n}$ make sense and are uniformly controlled.
- Regularity (inner/outer approximation) is what makes vague convergence against $C_{0}$ the right topology and ensures the limit is again a Radon measure.
- Second countability/separability is what turns the weak compactness into sequential compactness, so we can talk about subsequences.

In general we see that we work with Radon measures as it makes us able to switch in the proof between the following concepts
- functionals on $C_{0}$ and measures (by Riesz-Markov)
- uniform bounds on compacts and vague subsequence limits (compactness in the space of Radon measures)

How we get to the vaguely convergent subsequence:
- We want to pick a countable dense set of test functions.
	- As $Y$ is second countable we can choose subsequence $\{ \phi_{j} \}_{j\geq{1}}\subset C_{0}(Y)$ that is dense in $C_{0}(Y)$ in the usual sense used in these arguments (e.g. uniform norm on each compact, via an exhaustion by compacts).
- We extract subsequences per function
	- for $\phi_{1}$, $\int \phi_{1}d\mu_{n}$ is bounded, so we can pick a subsequence $n^{(1)}_{k}$ along which it converges
	- then for $\phi_{2}$, $\int \phi_{2}d\mu_{n^{(1)}_{k}}$ is still bounded, and we pick a further subsequence $n^{(2)}_{k}$ where it converges
	- etc.
- Then we look at a diagonal subsequence
	- Define the diagonal indices $m_{k}:=n^{(k)}_{k}$ 
	- For each fixed $j$, $$\int \phi_{j}d\mu_{m_{k}}\quad\text{converges as }k\to \infty,$$ because eventually you end up in a stage where $\phi_{j}$ stabilizes.
	- Now we thus have a subsequence $\mu_{m_{k}}$ for which integrals converge for all of the $\phi_{j}$ in the countable dense set of test functions 
- Using the above we define a limit functional and show its convergence
	- Define $$L(\phi_{j}):=\lim_{ k \to \infty } \int \phi_{j}d\mu_{m_{k}}.$$
	- We can extend $L$ to all of $C_{0}(Y)$ by dense property and the fact that we have uniform bounds on compacts.
	- We can then see that the following 3 hold:
		- $L$ is linear
		- $L(\phi)\geq{0}$ when $\phi\geq 0$
		- $L$ is continuous on the right locally convex topology on $C_{0}(Y)$
	- By Riesz-Markov we then get the Radon measure $\mu$ s.t. $$L(\phi)=\int \phi d\mu,\quad\forall \phi \in C_{0}(Y)$$
- This is the conclusion that $\mu_{m_{k}}\to \mu$ vaguely

How it exactly fits into this part of the proof:
As said earlier we take $Y=X\times X\setminus d$ and $\mu_{\beta}:=\frac{\beta}{2}\sigma_{\beta}$ (restricted off diagonal).

We show for every compact $K\subset X\times X\setminus d$ that the bounded on compacts holds, i.e., $$\sup_{\beta\geq 1}\mu_{\beta}(K)<\infty.$$ We do that using energy form bounds $\mathcal{E}^{(\beta)}(u,u)\leq \mathcal{E}(u,u)$, with some cleverly supported $u$'s.

Then from this we get:
- bounded on compacts $\implies$ vague subsequence, choosing $\beta_{n}\to \infty$ with $\mu_{\beta_{n}}\to J$ vaguely
- that we can show any subsequential limit must be the same $J$, thus we get uniqueness
-  by the point above that the whole family of measures $\mu_{\beta}\to J$ vaguely (not just subsequences). So uniqueness makes subsequence convergence full convergence.
#### III. Construction of $k$ and $\mathcal{E}^{(c)}$:
Beneath we will use $\delta_{l}$ for $\Gamma_{l}$ because of the next remark:

Vague convergence is seen to control integrals against continuously compactly supported functions, not indicators $\mathbf{1}_{A}$.

If we want to pass limits for integrals over regions such as $\Gamma_{l}=\{ \rho\geq \delta_{l} \}$, we want the boundary of the region $\partial \Gamma_{l}$ to have zero limit-measure mass, i.e., $$J(\partial \Gamma_{l})=0.$$
When that is the case we can approximate $\mathbf{1}_{\Gamma_{l}}$ from above or below by $C_{0}$ functions and then conclude $$\mu_{n}(\Gamma_{l})\to \mu(\Gamma_{l}).$$
We can do the same for $\int \mathbf{1}_{\Gamma_{l}}\phi d\mu_{n}$.

This will all make $\delta_{l}$ for $\Gamma_{l}$ a continuity set for $J$.
##### Start of proof part
Fix a metric $\rho$ on $X$ that is compatible with the given topology.
Choose a sequence of relatively compact open sets $G_{l}$ that are increasing to $X$.
Also choose a sequence of numbers $\delta_{l} \downarrow 0$ s.t. the set $$\Gamma_{l}=\{ (x,y)\in G_{l}\times G_{l}:\rho(x,y)\geq \delta_{l} \}$$ is a continuous set w.r.t. measure $J$, for every $l$.

Now just like in equation 1.4.8. we can rewrite $\mathcal{E}^{(\beta)}$ as follows: for $u\in \mathcal{F}\cap C_{0}(X)$ s.t. $\text{supp}[u]\subset G_{l}$, $$\mathcal{E}^{(\beta)}(u,u)=\frac{1}{2}\beta \int_{G_{l}\times G_{l}}(u(x)-u(y))^{2}\sigma_{\beta}(dxdy)+\beta \int_{G_{l}}u(x)^2(1-\beta G_{\beta}\mathbb{1}_{G_{l}}(x))m(dx).$$
This implies that the family of measures $\{ \beta(1-\beta G_{\beta}\mathbb{1}_{G_{l}}(x))m(dx) :\beta>0\}$ is uniformly bounded on each compact subset of $G_{l}.$
Hence a subsequence $\beta_{n}\uparrow\infty$ and positive Radon measures $k_{l}$ and $G_{l}$ exist and for each $l$ we have that $$ \beta_{n}(1-\beta_{n} G_{\beta_{n}}\mathbb{1}_{G_{l}}m\to k_{l}\quad\text{vaguely on }G_{l}\text{, as }\beta_{n}\to \infty.$$

Now using $$\frac{\beta}{2}\sigma_{\beta}\to J,\quad \text{vaguely on }X\times X\setminus d\text{ as }\beta\to \infty,$$
$$\mathcal{E}^{(\beta)}(u,u)=\frac{1}{2}\beta \int_{G_{l}\times G_{l}}(u(x)-u(y))^{2}\sigma_{\beta}(dxdy)+\beta \int_{G_{l}}u(x)^2(1-\beta G_{\beta}\mathbb{1}_{G_{l}}(x))m(dx),$$
and
$$ \beta_{n}(1-\beta_{n} G_{\beta_{n}}\mathbb{1}_{G_{l}}m\to k_{l}\quad\text{vaguely on }G_{l}\text{, as }\beta_{n}\to \infty,$$
we get that for every $l$ s.t. $\text{supp}[u]\subset G_{l},$
$$\begin{aligned}\mathcal{E}(u,u)=
\lim_{ \beta_{n} \to \infty } \frac{\beta_{n}}{2}\int_{G_{l}\times G_{l}, \rho(x,y)<\delta_{l}}(u(x)-u(y))^{2}\sigma_{\beta_{n}}(dxdy)\\+\int_{\Gamma_{l}}(u(x)-u(y))^{2}J(dxdy)\\+\int_{G_{l}}u(x)^{2}k_{l}(dx).\end{aligned}$$
We extend the measures $k_{l}$ to $X$ by setting $k_{l}(E)=k_{l}(E\cap G_{l})$, because now by $$\frac{\beta}{2}\sigma_{\beta}\to J,\quad \text{vaguely on }X\times X\setminus d\text{ as }\beta\to \infty,$$ we get that $k_{l}$ is non-increasing on each compact set. Denote the vague limit of $k_{l}$ by $k$, i.e., $$k_{l}\to k\quad \text{vaguely on }X,\text{ as }l\to \infty.$$
Now if we let $l\to \infty$, we get from the three term equation above, the equation of the Beurling-Deny decomposition, where now
$$\mathcal{E}^{(c)}=\lim_{ l \to \infty } \lim_{ \beta_{n} \to \infty }\frac{\beta_{n}}{2} \int_{G_{l}\times G_{l}, \rho(x,y)<\delta_{l}}(u(x)-u(y))\times(v(x)-v(y))\sigma_{\beta_{n}}(dxdy).$$

This expression for the local part tells us that condition 3.2.2. (strong local property) is satisfied and that every normal contraction operates on $\mathcal{E}^{(c)}$.
## Consequences / properties
First observe that identity 1.4.8 implies that for $f,u\in \mathcal{F}_{b}$,
$$2\mathcal{E}(uf,u)-\mathcal{E}(u^2,f)=\lim_{ \beta \to \infty } \left( \beta \int_{X\times X\setminus d}(\tilde{u}(x)-\tilde{u}(y))^{2}\tilde{f}(x)\sigma_{\beta}(dx,dy)+\beta \int_{X}\tilde{u}^{2}(x)\tilde{f}(x)(1-s_{\beta(x)})dm \right),$$ where $\mathcal{F}_{b}$ denotes the set of all essential bounded functions in $\mathcal{F}$ and $\tilde{f},\tilde{u}$ are any Borel modifications of $f,u$.

Hence we get $$2\mathcal{E}(uf,u)-\mathcal{E}(u^2,f)\leq_{2}\|f\|_{\infty}\mathcal{E}(u,u)$$ and the l.h.s. is non-negative when $f\geq0$ $m$-a.e. 

From this we conclude that there exists a positive Radon measure $\mu_{\braket{u}}, u \in \mathcal{F}_{b}$ satisfying
$$\int_{X}f(x)d\mu_{\braket{u}}=2\mathcal{E}(uf,u)-\mathcal{E}(u^{2},f),\quad f\in \mathcal{F}\cap C_{0}(X).$$
By the above estimate we see that $\mu_{\braket{u}}(X)$ is finite. From now we call $\mu_{\braket{u}}$ the energy measure of $u\in \mathcal{F}_{b}$.
Now if we introduce a bounded signed measure $\mu_{\braket{u,v}}$ by $$\mu_{\braket{u,v}}=\frac{1}{2}(\mu_{\braket{u+v}}-\mu_{\braket{u}}-\mu_{\braket{v}}),$$ then for $f\in \mathcal{F}\cap C_{0}(X)$ and $u,v \in \mathcal{F}_{b}$ we get $$\int_{X} f(x)d\mu_{\braket{u,v}}=\mathcal{E}(uf,v)+\mathcal{E}(vf,u)-\mathcal{E}(uv,f).$$
We also get that 

$$\begin{aligned}\int_{X} f(x)d\mu_{\braket{u,v}}=
\lim_{ \beta \to \infty }( \beta \int_{X\times X\setminus d}(\tilde{u}(x)-\tilde{u}(y))(\tilde{v}(x)-\tilde{v}(y))f(x)\sigma_{\beta}(dx,dy)\\+\beta \int_{X}\tilde{u}(x)\tilde{v}(x)f(x)(1-s_{\beta(x)})dm).\end{aligned}$$

Since $\mu_{\braket{u,v}}$ is bilinear in $u,v$ and $\mu_{\braket{u}}$ is a positive measure, we get the following inequality $$\left|\left( \int_{X}fd\mu_{\braket{u}} \right)^{1/2}-\left( \int_{X}fd\mu_{\braket{v}} \right)^{1/2}\right|\leq\left( \int_{X}fd\mu_{\braket{u-v}} \right)^{1/2},$$ for $u,v\in \mathcal{F}_{b}$ and non-negative bounded Borel function $f$.

Now if we combine this bound with the earlier bound $$2\mathcal{E}(uf,u)-\mathcal{E}(u^2,f)\leq_{2}\|f\|_{\infty}\mathcal{E}(u,u),$$ we get that the energy measure $\mu_{\braket{u}}$ can be uniquely defined for any $u$ in the extended Dirichlet space $\mathcal{F}_{e}$.
#### Lemma 3.2.1: (plus proof)
For $f,u,v\in \mathcal{F}\cap C_{0}(X)$ we have that $$\begin{aligned}
\int_{X}fd\mu_{\braket{u^{2},v}}-2\int_{X}fud\mu_{\braket{u,v}}=-2\int_{X\times X\setminus d}(u(x)-u(y))^{2}(v(x)-v(y))f(x)J(dxdy)\\-\int_{X}u^{2}(x)v(x)f(x)k(dx)
\end{aligned}$$
Proof:
Let $G_{1}$ and $G_{2}$ be relatively compact open sets s.t. $\text{supp}[f]\cup \text{supp}[u]\cup \text{supp}[v]\subset G_{1}\subset \overline{G}_{1}\subset G_{2}$.
Then by 3.2.8, 3.2.9, 3.2.16, we get that the l.h.s. of the equality of lemma 3.2.1 equals the following $$\begin{aligned}
-\lim_{ \beta \to \infty } \left( \beta \int_{G_{2}\times G_{2}}(u(x)-u(y))^{2}(v(x)-v(y))f(x)\sigma_{\beta}(dxdy)\right)-\int_{X}u^{2}(x)v(x)f(x)k(dx)\\=-\lim_{ \beta \to \infty } I(\beta)-\lim_{ \beta \to \infty } II(\beta)-\int_{X}u^{2}(x)v(x)f(x)k(dx),
\end{aligned}$$
where
$$I(\beta)=\beta \int_{G_{2}\times G_{2}}(u(x)-u(y))^{2}(v(x)-v(y))f(x)\phi(y)\sigma_{\beta}(dxdy)$$
$$II(\beta)=\beta \int_{G_{2}\times G_{2}}u^{2}(x)v(x)f(x)(1-\phi(y))\sigma_{\beta}(dxdy)$$
with $\phi \in \mathcal{F}\cap C_{0}(X)$ being non-negative function s.t. $\phi=1$ on $G_{1}$ and $\text{supp}[\phi]\subset G_{2}$.

Then to calculate the limit of $I(\beta)$ we use the following three properties:
- $(v(x)-v(y))f(x)\phi(y)$ belongs to $C_{\infty}(X\times X\setminus d)$,
- measures $\beta(u(x)-u(y))^{2}\sigma_{\beta}(dxdy)$ are uniformly bounded by $2\mathcal{E}(u,u)$
- the above measures converge vaguely to $2(u(x)-u(y))^{2}J(dxdy)$ on $X\times X\setminus d$ as $\beta \to \infty$
We get $$\lim_{ \beta \to \infty } I(\beta)=2\int_{X\times X}(u(x)-u(y))^{2}(v(x)-v(y))f(x)\phi(y)J(dxdy).$$

Now using 3.2.2 and 3.2.9 we see that
$$II(\beta)=\beta(u^{2}vf,\phi-\beta G_{\beta}\phi)-\beta(u^{2}vf,1-\beta G_{\beta}\mathbf{1}_{G_{2}})$$
and taking the limit of $\beta\to \infty$ gives
$$\mathcal{E}(u^{2}vf,\phi)-\int_{X}u^{2}(x)v(x)f(x)k(dx)=2\int_{X\times X\setminus d}u^{2}(x)v(x)f(x)(1-\phi(y))J(dxdy).$$

Substituting these limits into the first equation of the proof yields the identity we state in the lemma.
#### Lemma 3.2.2: interesting

#### Lemma 3.2.3: interesting

#### Lemma 3.2.4: interesting

#### Lemma 3.2.5: interesting

## Related Definitions

