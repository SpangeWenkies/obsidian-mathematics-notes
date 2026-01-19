
# Definition: Infimum

**Type:** #definition  

## Definition
- Let $(S,\leq)$ be a [[Total order|Totally ordered]] or at least [[Partial order|partially ordered]] set and let $A\subseteq S$.
- Then a number $m \in S$ is the infimum (or greatest [[Lower bound]]) of A if:
	- $m$ is a lower bound of $A$, i.e., $\forall a\in A, m\leq a$
	- $m$ is the greatest of such a lower bound, i.e., 
		if $b\in S$ is any lower bound of $A$, ($b\leq a$  for all $a\in A$), then we have that $b\leq m$ 
## Intuition (optional)

- it is the greatest possible lower bound. If we have for example an interval $[1,2]$ on $\mathbb{R}$ we have that possible lower bounds are all values lower or equal than 1, e.g., $\{ -4212, -10, 0.5, 1 \}$.
	$\implies$ The infimum is then the lower bound equal to 1
## Equivalent Formulations (optional)

## Properties
- If the infimum of both sets $A \text{ and } B$ exist, and $A\subseteq B$ then $\inf B \leq \inf A$
- If $A$ has a [[Minimum]] then $\inf A = \min A$, e.g., open interval has no minimum
- For any non-empty set $A$ [[Bounded below]] , $\inf A\in \mathbb{R}$, by the [[Completeness]] of $\mathbb{R}$ 
## Related Concepts

- [[Supremum]] 