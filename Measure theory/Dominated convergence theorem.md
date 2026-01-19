
# Theorem: Dominated convergence theorem

**Type:** #theorem  

## Statement
- Suppose $f_{n}$ converges pointwise to $f$ [[almost everywhere|a.e.]]
- Suppose $\exists$ an integrable dominating function $g$ s.t. $|f_{n}(x)|\leq g(x), \forall n$
- Suppose $g$ has a finite integral, i.e., $\int|g(x)|d\mu<\infty$, or equivalently $g\in L^{1}$ the [[Lp-space]] 
$\implies g$ is integrable and $f_{n}$ is "capped"
	$$\implies \lim_{ n \to \infty }\int f_{n}d\mu=\int \lim_{ n \to \infty }f_{n}d\mu$$
	and $f = \lim_{ n \to \infty }f_{n}\in L^{1}$ as well
## Proof Idea (optional)


## Consequences / properties
- Now you may even swap integral when the sequence is not monotone
- Still strong equality result unlike the $\leq$ result of Fatou's lemma

## Related Definitions
- [[Fatou's lemma]]
- [[Monotone convergence theorem]]
