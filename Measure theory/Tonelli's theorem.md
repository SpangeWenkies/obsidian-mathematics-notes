
# Theorem: Tonelli's theorem

**Type:** #theorem  

## Statement
- For non-negative functions, as opposed to [[Fubini's theorem]]
- if $f(x,y)\geq0$ and is a [[Measurable function]] , then $$\int_{X\times Y}f(x,y)d(\mu \times \nu)=\int_{X}\left( \int_{Y}f(x,y)d\nu(y) \right)d\mu(x)=\int_{Y}\left( \int_{X}f(x,y)d\mu(x) \right)d\nu(y)$$

## Proof Idea (optional)
- Used in [[Swapping integration order]]

## Consequences / properties
- We need no assumption of integrability of $f$, just the measurability and non-negativity and then integration orders can always be swapped
- We may have that the inner integral equates to $+\infty$, the outer integral will then also be equal to the same $+\infty$ 

## Related Definitions

