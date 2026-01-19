
# Definition: Lp-space

**Type:** #definition  

## Definition
- Let $(X,\Sigma,\mu)$ be a [[Measure space]]
- A function $f$ is in $L^p(X,\mu)$ defined for $1\leq p\leq \infty$ if $$\int_{X}|f(x)|^{p}d\mu(x)<\infty$$
- We then get a set of integrable functions $f$ from which the space is built
- Because the space has a norm it is a [[Normed vector space]] 
- 
## Intuition (optional)
- Useful when we would want to look at functions by their "size" instead of pointwise ([[Lebesgue integration]]) 
	- You would want to do this if you have functions with finitely many infinite spikes 
	- You would want to do this if a function only differs from another on [[Measure zero]] and thus should actually be treated equally
	- You would want to do this if you want to look at vector spaces of $\mathbb{R}^{n}$ behaviour, but want to look at the behaviour when $n \to \infty$

- For Lebesgue integration we want $L^p$-spaces, this is as they use the [[Lebesgue measure]] and these:
	- respect [[Limit|limits]] due to [[Monotone convergence theorem]]/[[Dominated convergence theorem]]/[[Fatou's lemma]]
	- make for Lebesgue integration
	- define "sizes" of sets
	- circumvent pathologies of [[Measure zero]]
	- $L^{p}(\mathbb{R}^n)=\left\{  f: \int|f|^{p}<\infty  \right\}$ is the natural space for
		- [[Partial differential equation]]
		- [[Sobolev space]] 
		- [[Markov process]]
		- [[Dirichlet form]] 

- If in $L^1$ then a function is integrable, if $L^2$ then square integrable
- If in $L^{\infty}$ then we say a function is [[Essentially bounded]] 

## Examples
- Are the following $f$ on $[0,1]$ in $L^{p}$?
	- $f(x)=1$: yes in all $L^p$ as $||1||_{p} = 1, \forall p$
	- $f(x)=\frac{1}{\sqrt{ x }}$: yes in $L^1$, no in $L^p,$ for $p>1$
	- $f(x)=\frac{1}{x}$: no, not in any for $p\geq1$

- In $L^{2}$, the [[Dot product]] $<f,g>$ defines the [[Inner product]] $\int f(x)g(x)d\mu$
	- This makes us able to do [[Matrix projection]] , use the [[Spectral theorem (infinite dimensional and continuous matrices)]], use matrices as [[Operator|operators]] and in $L^2$ [[Orthogonality]] makes sense
	- $L^2$ is a [[Hilbert space]] 
	- [[Dirichlet form]] lives on $L^2$ 

## Equivalent Formulations (optional)
- if the [[Lp-norm]] is finite and exists

## Related Concepts

