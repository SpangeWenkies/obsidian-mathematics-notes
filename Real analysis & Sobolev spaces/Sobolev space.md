
# Definition: Sobolev space

**Type:** #definition  

## Definition
- $W^{1,p}(\Omega)$ for $1\leq p\leq \infty$ :
	- consists of all functions $u \in L^{p}(\Omega)$ ([[Lp-space]]) s.t. each [[Weak derivative]] $D_{i}u$ exists and belongs to $L^{p}(\Omega)$ , i.e., $$W^{1,p}(\Omega)= \{ u \in L^{p}(\Omega):D_{i}u \in L^{p}(\Omega), \ \forall i=1,\dots,n\}$$
	- The [[Sobolev norm]] of the space is defined on the functions $u$ as: $$||u||_{W^{1,p}(\Omega)}=||u||_{L^{p}(\Omega)}+\sum_{i=1}^{n}||D_{i}u||_{L^{p}(\Omega)}$$
	- Having a [[Norm]] makes this a [[Banach space]]
	- Functions in $W^{1,p}(\Omega)$ have integrable values and (weakly) integrable gradients. They may not be [[Smooth function]], but they are [[Sufficiently smooth function]] such that [[Integration by parts]] identities hold

- $H^{1}(\Omega) = W^{1,2}(\Omega)$ 
	- consists thus of all functions $u \in L^{2}(\Omega)$ whose weak derivatives exist and all lie in $L^{2}(\Omega)$ 
	- These thus have an [[Inner product]] $$<u,v>_{H^{1}}=\int_{\Omega} uv \ dx+\int_{\omega}\nabla u \nabla v \ dx$$
	- Having the [[Dot product]] defined as this [[Inner product]] makes it a [[Hilbert space]]
	- These are functions whose value and gradient have finite "energy"

- $H^{1}_{0}(\Omega)$ are the [[Closure]] of [[Smooth function|smooth]], [[Compact support|compactly supported]] functions in the $H^{1}$-norm defined as:$$H^{1}_{0}(\Omega):=\overline{C^{\infty}_{c}(\Omega)}^{||.||_{H^{1}}(\Omega)}$$
	- Elements of these spaces are [[Sobolev function|sobolev functions]] that "vanish on the [[Boundary]]" in the [[Variational sense]] 
	- Functions in this space can be approximated by [[Smooth function]] that are 0 near the [[Boundary]] $\partial \Omega$
	- These satisfy the natural form of the [[Dirichlet form]] boundary condition $u|_{\partial \Omega}=0$
	- This is the [[Canonical domain]] for the[[ Dirichlet Laplacian]] and classical Dirichlet forms

## Intuition (optional)


## Equivalent Formulations (optional)


## Related Concepts

- [[Banach space]]