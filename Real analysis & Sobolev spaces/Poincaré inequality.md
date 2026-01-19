
# Definition: Poincaré inequality

**Type:** #definition  

## Definition
- Let $\Omega \subset \mathbb{R}^{n}$ be a [[Totally bounded|bounded]] [[Domain]] with a [[Sufficiently regular boundary]] 
- A Poincaré inequality is then an inequality of form: $$||u-u_{\Omega}||_{L^{p}(\Omega)}\leq C||\nabla u||_{L^{p}(\Omega)}, \ \ \ 1\leq p < \infty,$$ where $$u_{\Omega}:=\frac{1}{|\Omega|}\int_{\Omega}u(x)dx$$ is the mean of $u$ on $\Omega$ and $C=C(\Omega,p)$ and is a constant
- A special case is when $u\in H^{1}_{0}(\Omega)$, as then the functions vanish on the boundary and the inequality becomes the zero-boundary Poincaré inequality: $$||u||_{L^{p}(\Omega)}\leq C||\nabla u||_{L^{p}(\Omega)}, \ \ \ 1\leq p < \infty,$$

## Intuition (optional)
- It states that on a bounded domain, the [[Function oscillation]] of a function is controlled by the size of the [[Gradient]]
- If the gradient is really small then the oscillation should be aswell

- This is fundamental for:
	- [[coercivity]] of the [[Dirichlet energy]]
	- existence and uniqueness of [[weak solutions]] to [[elliptic PDE]]
	- [[spectral property]] of [[Laplacian]]
	- the definition and analysis of [[Dirichlet form]]

- The inequality actually shows that the
	[[Seminorm]] $||\nabla u||_{L^p}=$ [[Sobolev norm]]  $||u||_{W^{1,p}(\Omega)}=||u||_{L^{p}(\Omega)}+\sum_{i=1}^{n}||D_{i}u||_{L^{p}(\Omega)},$ for $u \in H_{0}^{1}(\Omega)$ 

- The boundedness of the domain is required as then the functions can not have an arbitrarily small gradient but still grow into infinity (it is the same as needing integrability conditions at infinity)
## Equivalent Formulations (optional)
- Zero-mean version:
	- $u\in W^{1,p}(\Omega)$ and $\int_{\Omega}u=0$ gives $$||u||_{L^{p}(\Omega)}\leq C||\nabla u||_{L^{p}(\Omega)}, \ \ \ 1\leq p < \infty$$
- Zero-trace version:
	- $u \in H_{0}^{1}(\Omega)$ gives $$||u||_{L^{2}(\Omega)}\leq C||\nabla u||_{L^{2}(\Omega)}$$
- Spectral version:
	- $u \in \text{ Hilbert space}$ gives $$\int_{\Omega}|u|^{2}\leq \frac{1}{\lambda_{1}}\int_{\Omega}|\nabla u|^{2},$$ where $\lambda_{1}$ is the first [[Dirichlet eigenvalue]] of $-\Delta$ (negative [[Laplacian]])$$-\Delta:H^{1}_{0}(\Omega)\mapsto H^{-1}(\Omega)$$

## Related Concepts

