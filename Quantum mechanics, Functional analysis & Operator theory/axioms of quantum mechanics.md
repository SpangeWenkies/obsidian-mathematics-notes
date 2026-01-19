
# Definition: axioms of quantum mechanics

**Type:** #definition  

## Definition
- (A1): with every [[quantum system]] there is associated a [[Separability|separable]] [[Hilbert space|complex Hilbert space]] , the states of that system are all [[positive]] [[trace-class]] [[linear map|linear maps]] $\rho:\mathcal{H}\to\mathcal{H}$ for which the trace $\mathrm{Tr} \ \rho=1$
	- often badly stated is that the ([[normalize|normalized]]) elements $\psi \in\mathcal{H}$ are the states of the quantum system, but this is not true
		- There are many (normalized) elements $\psi \in \mathcal{H}$ that are associated with a single state $\rho$
			- not 1-to-1, so you can not uniquely label a state $\rho$ if you know $\psi$ 

- (A2): The [[observable|observables]] of a [[quantum system]] are the [[Self-adjointness|self-adjoint]] [[linear map|linear maps]]/[[Operator|operators]] $$A:\mathcal{D}_{A}\to\mathcal{H}$$ where $\mathcal{D}_{A}$ is the [[Domain]] and the [[Target space]] is a [[Separability|separable]] [[Hilbert space|complex Hilbert space]] 
	- we extended the [[Self-adjointness]] definition to accommodate for the infinite dimensional space

- (A3): The [[probability]] that a measurement of any [[observable]] $A$ on a quantum system in state $\rho$ yields a results/outcome in the [[Borel set]] $E\subseteq \mathbb{R}$ is given by $$\mu_{\rho}^{A}(E):=\mathrm{Tr}(P_{A}(E)\dots\dots\dots)$$
## Intuition (optional)
- The first 3 axioms are "kinematic" axioms which tell you about the objects in quantum mechanics and how to use and evaluate them into a (probability) [[Measure]] $\mu_{\rho}^A$ if you have the quantum system state $\rho$ and the observable (self-adjoint operator/linear map) $A$ 
- The latter 2 axioms tell you about the dynamics of the development of a quantum system that exists in time

## Equivalent Formulations (optional)


## Related Concepts

