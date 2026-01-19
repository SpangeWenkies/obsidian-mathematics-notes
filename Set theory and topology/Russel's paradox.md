
# Definition: Russel's paradox

**Type:** #definition  

## Definition
Counterexample to naïve set theory looking at the [[Axiom on epsilon-relation]]: [[Russel's paradox]]
	- Assume there exists $u$ which contains all sets that do not contain themselves as elements
	- $\exists u:\forall z:(z \in u \iff z \not\in z)$
	- Is then $u$ a set? -> no
		- proof: if $u$ is a set, we must be able to decide if a statement including an [[epsilon relation]] is true or false as it is a proposition then.
			- assuming $u\in u$ is true, then we have that $u \not\in u$ follows (contradiction)
			- assuming $u \in u$ is false, we can say whatever we want after an "$\iff$" and we might say $u \not\in u$ (contradiction as well)
			$\implies$ $u$ is not a set as we can not see it as a proposition
	- This counterexample is why "naïve" set theory is inconsistent and we need [[Zermelo-Fraenkel axioms including the axiom of choice]]

## Intuition (optional)


## Equivalent Formulations (optional)


## Related Concepts

