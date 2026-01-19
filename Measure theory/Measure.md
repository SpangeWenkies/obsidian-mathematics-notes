
# Definition: Measure

**Type:** #definition  

## Definition
- $X$ is a set, $\Sigma$  is a $\sigma$-[[Sigma algebra|algebra]]
- over $X$, defining the subsets over $X$ that are "Measurable"
- A [[Set function]] $\mu$ from $\Sigma$ to the [[Extended real number line]] is a **measure** if the following hold:
	- $\mu(\emptyset)=0$
	- Non-negativity: $\forall E \in \Sigma$ , $\mu (\Sigma)\geq0$ 
	- [[Countable additivity]]: $\forall$ countable collections $\{ E_{k} \}^{\infty}_{k=1}$  [[Pairwise disjoint set|Pairwise disjoint sets]] in $\Sigma$ $$\mu\left( \bigcup^{\infty}_{k=1}E_{k} \right)=\sum^{\infty}_{k=1}\mu(E_{k})$$

- If condition $\mu(\emptyset)=0$ is relaxed and $\mu(E)$ only ever equals either $+$ or $-\infty$, i.e., no distinct sets have measures $+\infty$  or $-\infty$ 
	$\implies$ $\mu$ is a **signed** measure

- $(X, \Sigma)$ is a **measurable space**
	- members of $\Sigma$ are measurable sets

- $(X,\Sigma,\mu)$ is a **measure space**
	- A **probability** measure is a measure with total measure equal to one, i.e., $\mu(X)=1$
	- A **probability** space is then a measure space with a probability measure

- The definition of a measurable selection:
	- Take a [[Measure space]] $X$ and a measure space $Y$
	- You have a [[Set-valued map]] $\Phi: X \mapsto \mathcal{P}(Y)$
		- This means for each $x \in X, \Phi(x)$ is a **set** of possible choices
		- Like how in a markov process at each state $x$ the kernel gives a set of next possible states
	- Say now you pick one element from each $\Phi(x)$, which is a function $f(x)\in \Phi(x)$
	- Now if this $f$ is a [[Measurable function]], then this is a measurable selection
	- A theorem that confirms the existence of a measurable selection is the [[Kuratowski-Ryll-Nordzewski theorem]] 
## Intuition (optional)
- The approach of defining a measure as a countably subadditive real-valued function of sets, which distributes over disjoint sets is intuitive. But, this direct intuition it gives is somewhat less than ideal. 
- Properly understood, measures are one of the most powerful objects in mathematics, especially useful and beautiful in analysis.
- A reduction to merely generalizations of area does not do them justice
- Best way to look at measures is through [[functional analysis]]. They bridge [[Topology|topological]] information into [[analysis|analytical]] information.
	- in this way measures are half of the equation and the other half is the notion of an [[indicator function]]
		- given a set $S$, we can construct an indicator function $1_{S}$
		- [[Urysohn's lemma]] tells us that if $S$ is a [[Closure|closed]] subset of a [[Topological space]] $X$, then $X$ is a [[normal space]] iff we can extend $1_{S}$ to a continuous function $f$ on $X$. This function $f$ must vanish on some closed subset $T$ of the [[complement]] of $S$, we denote as $S\setminus T$
		- We can see that as $S\setminus T$ shrinks that $f$ becomes a closer and closer approximation of $1_{S}$
		- indicator functions transform [[Operator|operations]] among sets onto operations among functions
		- indicator function of complement of $S$ is $1-1_{S}$ 
		- given two disjoint sets $U$ and $V$, the indicator function of their union is the sum of their individual indicator functions, the indicator function of the intersection is the product of the individual indicator functions
		- using the indicator function, we can identify the measure $\mu(S)$ of our set $S$ with the [[Image]] of $1_{S}$ under the [[linear functional]] $d\mu$ 
			- This way the [[Countable additivity|countable subadditivity]] property of measures gets translated into [[countable linearity|countable sublinearity]] of the associated linear functional
	- One of the fundamental ideas behind measure-theoretic integration like [[Lebesgue integration]] is that we prove things first for [[Simple function|simple functions]], which are indicator functions of [[Measurability|measurable sets]], we then take limits by approximating more complicated functions using linear combinations of the simple functions
		- This shows what measure theory is capable of when it comes to integration.
		- We can also because of measures now easily replace the [[Sigma algebra]] of measurable sets with the sigma algebra of functions, by considering the sigma algebra of the indicator functions associated to the measurable sets in our sigma algebra
	- In functional analysis our ability to approximate general functions by certain classes of simple functions can be realized in [[Norm|norms]] (or [[locally convex topology|locally convex topologies]]) 
		- e.g., consider the topological [[Closure]] of the [[Space]] of simple functions w.r.t. the [[supremum norm]] or w.r.t. the [[Lp-norm]] for some $1<p$ 
	- when we extend our notion of what kinds of linear functionals we choose to call measures to include linear functionals involving [[Differentiability|differentiation]], [[Fourier transform|fourier transforms]], and others
		$\implies$ then [[distribution|distributions]] arise 
- If we thus think about measures this way, we see that something like a [[Dirichlet function]] will provide us with a way to determine what (if any) [[regularity]] is required for functions to be [[integrability|integrable]] w.r.t. a given measure
	- That is, because now that we view measures $\mu$ as continuous linear functionals $d\mu$ on spaces of functions, a measure does not live on its own, but rather lives alongside a family of functions with which it seems to be compatible
		- Thus, e.g., the [[Dirac delta]] (a.k.a. the evalutation functional) is compatible with continuous functions, but not with $L^1$ functions (in [[Lp-space]]). This is as the value of a $L^{1}$ function at any given point is undefined.
			- it is undefined as you can always change the value of an $L^{1}$ function at a single point without changing the [[equivalence class]] in $L^{1}$ to which the value belongs

- Measures are needed in defining a [[Random variable]] 
- The [[expectation]] of a random variable is defined through Lebesgue integration which builds on measures
- 
## Equivalent Formulations (optional)

## Related Concepts
- [[Dirac measure]]
- [[Borel measure]]
- [[Radon measure]]
- [[Lebesgue measure]]
- [[Outer measure]]

- [[Measurability]]