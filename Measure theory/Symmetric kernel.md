
# Definition: Symmetric kernel

**Type:** #definition  

## Definition
- A [[Kernel]]/[[Transition kernel]] is symmetric relative to a measure $m$ if $\forall \text{ measurable }A,B \subseteq X$: $$\int_{A}K(x,B)m(dx)=\int_{B}K(y,A)m(dy)$$
- Symmetry is expressed over integrals and not pointwise and we see they should equal except on a [[Product space]] $A\times B$ of [[Measure zero]] (symmetry only up to null sets)

## Intuition (optional)
- They have that the [[Measure]] of going forward is equal to the measure going backwards
- Probability of going from $A$ to $B$ is same as from $B$ to $A$ after weighting by the reference measure $m$

- same as the [[Self-adjointness]] of an [[Operator]]
## Equivalent Formulations (optional)
- $K(x,dy)m(dx)=K(y,dx)m(dy)$

## Consequences/properties
- If a kernel is symmetric and its transition density is defined as $K(x,dy)= k(x,y)m(dy)$, then we get that $k(x,y)=k(y,x), m\times m$ [[almost everywhere]]

## Related Concepts

