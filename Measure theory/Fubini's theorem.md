
# Theorem: Fubini's theorem

**Type:** #theorem  

## Statement
- No non-negativity, as opposed to [[Tonelli's theorem]], but now we require [[Absolute integrability]] , i.e., $\int_{X\times Y}|f(x,y)|d(\mu \times \nu)<\infty$
- Then we may say
	- the integral of f exists and is finite (as opposed to Tonelli's theorem)
	- the integral may be split into an iterated integral and swapped like so $$\int_{X\times Y}f=\int_{X}\int_{Y}f=\int_{Y}\int_{X}f$$
	- the individual functions $x \mapsto \int_{Y}f(x,y)d\nu$ and $y \mapsto \int_{X}f(x,y)d\mu$ are both integrable and finite [[almost everywhere]]
## Proof Idea (optional)

## Examples
- If function $f(x,y)$ is absolutely integrable then $$\int_{\mathbb{R}\times[0,1]}f(x,y)d(\mu \times \nu)=\int_{\mathbb{R}}\left( \int_{0}^{1}f(x,y)d\nu \right)d\mu=\int_{0}^{1}\left( \int_{\mathbb{R}}f(x,y)d\mu \right)d\nu$$


## Consequences / properties
- Tonelli's theorem is a special case of Fubini's theorem

- A consequence of the possibility to [[Swapping integration order]] is that we can
	- compute expactations
	- work with [[Kernel|kernels]] as [[Transition kernel|transition kernels]] of [[Markov process|Markov processes]] require the swapping
	- work with [[Heat kernel|heat kernels]] 
	- work with [[Dirichlet form|dirichlet forms]] 

## Related Definitions

