
# Theorem: Hölder's inequality

**Type:** #theorem  

## Statement
- Inequality in [[Lp-space]]
- For an $L^p$-space with $1<p<\infty$ and $q$ being its [[Conjugate exponent]] s.t. $$\frac{1}{p}+\frac{1}{q}=1$$
- Then for all $f \in L^{p}, g\in L^{q}$: $$\int|fg|d\mu\leq ||f||_{p}||g||_{q} $$
- i.e., the integral of a product is bounded by the product of the [[Norm]] of $g$ and of $f$
- 

## Proof Idea (optional)


## Consequences / properties
- This is the [[Cauchy-Schwarz inequality]] when $p=2$
- It proves that $L^p$ spaces are [[Dual space]]
- It means that $\int fgd\mu\leq \infty$ when $f\in L^p$ and $g \in L^q$ 
- Choosing $g=1$ we get that $\int|f|d\mu=|\int fd\mu|\leq||f||_{1}$
- This makes handling products of functions easier

## Related Definitions
- [[Minkowski's inequality]]
- [[Jensen's inequality]]
