
# Theorem: Jensen's inequality

**Type:** #theorem  

## Statement
- Let $\phi:\mathbb{R}\mapsto \mathbb{R}$ be a [[Convexity|convex]] function. Let $f$ be integrable w.r.t. a probability [[Measure]] $\mu$, then: $$\phi\left( \int fd\mu \right)\leq \int \phi(f)d\mu$$


## Proof Idea (optional)

## Examples
- for $\phi(x)=x^p$ we get for $p>1$: $$|\int fd\mu|\leq\left( \int|f|^pd\mu \right)^{1/p}$$
	- Which is a precursor to [[Hölder's inequality]]
- It is used in functions in combinations with conditional expectations to get: $$\phi(E[X|\mathcal{G}])\leq E[\phi(X)|\mathcal{G}]$$
- 


## Consequences / properties
- very powerful tool in probability theory
- Convex functions lie above their [[Secant line]],i.e.,
	- pick two points on a curve
	- draw a line between
	- if all points on the line are always below the curve than the curve is convex
## Related Definitions

