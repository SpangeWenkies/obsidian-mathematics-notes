
# Theorem: Monotone convergence theorem (MCT)

**Type:** #theorem  

## Statement
- Let $f_{1}\leq f_{2}\leq\dots$ be a sequence of non-negative [[Measurable function|measurable functions]], i.e., for $f_{i}: X \mapsto Y$, if $Y$ is a [[Measurability|measurable set]] then $X$ is aswell
- Let the sequence increase pointwise to a [[limit]] $f_{n}(x) \to f(x), \forall x$
- Then we can say $$\lim_{ n \to \infty }\int f_{n}d\mu = \int \lim_{ n \to \infty } f_{n}d\mu $$

## Proof Idea (optional)


## Consequences / properties
- if the function grows upward [[Monotonicity|monotonically]], then the [[Limit]] can be put inside the integral
- intuitively we can see this is the case as when the function grows upward monotonically there can be no oscillation of cancelation in the increase in area under the function

## Related Definitions
- [[Fatou's lemma]]
- [[Dominated convergence theorem]] 
