
# Definition: adjoint

**Type:** #definition  

## Definition
- For a [[linear map]] $A:\mathcal{D}_{A}\to\mathcal{H}$, the adjoint is the map $A^{*}:\mathcal{D}_{A^{*}}\to\mathcal{H}$ defined by $$\mathcal{D}_{A^{*}}:=\{ \psi \in\mathcal{H} \ | \ \forall \alpha \in\mathcal{D}_{A}, \ \exists \eta \in \mathcal{H}:<\psi,A\alpha> = <\eta,\alpha>\}$$
$$A^{*}(\psi):=\eta$$
- We can show that this $\eta$ is uniquely defined like this. if not then the adjoint map would be ill-defined
## Intuition (optional)
- It is important we define $\eta \in \mathcal{H}$ , that is $\eta$ is in the [[Target space]] and not just in the [[Domain]] of the linear map $\mathcal{D}_{A}$.
	- if not then we would get a smaller domain for the adjoint
	- if we then say a linear map / operator is [[Self-adjointness|self-adjoint]] we take the wrong $\mathcal{D}_{A}=\mathcal{D}_{A^{*}}$ 
	- This wrongful definition of the map $A$ being a self-adjoint map then means if we look at the [[spectrum]] of this operator, which is the set of possible outcomes, we see this spectrum $\sigma(A)\not\in \mathbb{R}$, while this is a desirable property that should arise naturally

## Equivalent Formulations (optional)


## Related Concepts

