
# Definition: Metric space

**Type:** #definition  

## Definition
- A set together with a notion of distance between its elements is called a metric space $(X,d)$
- A metric space always induces a [[Topological space]], i.e., topological spaces are either metrizable or non-metrizable
- A metric space induces existence of [[Openness|open]] [[Ball|balls]], $B(x,r)=\{ y:d(x,y)<r \}$
	- which give open sets, as a set $U \subseteq X$ is open if $\forall x \in U, \exists r>0 \text{ with } B(x,r)\subseteq U$
	- which satisfy the three axioms of a topological space, 
	- which were that $\emptyset, X$ are open, arbitrary unions of the sets are open, finite intersections of open sets are open
	So a metric space gives a topological space (but not vice versa)
## Intuition (optional)


## Equivalent Formulations (optional)

## Examples
- [[Polish space]] (for most results and theorems this is nice as it is a completely metrizable separable space)
- [[Lusin space]]
- [[Standard Borel space]]

- Results in Dirichlet forms and Hunt processes are **not** defined on metric spaces but generally on topological spaces
	- Allows for infinite state spaces
	- generalized is better for potential theory
	- other processes that do not live naturally on metric space topology

## Related Concepts

