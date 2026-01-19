
# Definition: Dense in space

**Type:** #definition  

## Definition
- e.g. $C^{\infty}_{c}(\Omega)$ (space of [[Smooth function]] with [[Compact support]]) is dense in [[Sobolev space]] $W^{1,p}(\Omega)$ if for every function $u \in W^{1,p}(\Omega)$ and for every $\epsilon>0$ there exists $u_{\epsilon}\in C^{\infty}_{c}(\Omega)$ s.t. $$||u-u_{\epsilon}||_{W^{1,p}(\Omega)}<\epsilon$$
	- This holds if $\Omega$ has a [[Sufficiently regular boundary]] , which is if the functions in $\Omega$ are [[Smooth function]] or [[Lipschitz continuity|Lipschitz continuous]] 
	- It holds always thus for a [[Dirichlet space]] $H^{1}_{0}(\Omega)$
	- 

## Intuition (optional)
- for $C^{\infty}_{c}(\Omega)$ being dense in $W^{1,p}(\Omega)$ this means any function in a [[Sobolev space]] $W^{1,p}(\Omega)$ can be approximated (by [[Mollification]] of the function) as closely as desired by smooth functions that vanish near the boundary
	- This is crucial because:
		- smooth functions are easier to differentiate
		- [[Integration by parts]] works automatically
		- constructions are simpler
		- existence/uniqueness proofs usually start with smooth [[Test function]]
		- Dirichlet forms and energy minimization arguments rely on this density
	- Makes Sobolev spaces behave like classical smooth spaces and the [[Weak derivative]] be calculated as classical derivatives or approximations

## Equivalent Formulations (optional)


## Related Concepts

