G-Estimation Explanation
================

Conditional Exchangeability
===========================

The most important concept to understand in G-Estimation is this one:

*Y*<sup>*a*</sup> ⊥ ​​​ ⊥ *A*|*L*

This equation seems confusing but it's just the mathematical form of condition exchangeability. It says the counterfactual outcome *Y*<sup>*a*</sup> is independent of the actual treatment (A) given the same covariates (L).

An example
==========

Now if we had a logistic regression model of the outcome with the counterfactual outcome and covariates as predictors:

*l**o**g**i**t**P**r*\[*A* = 1|*Y*<sup>*a* = 0</sup>, *L*\]=*θ*<sub>0</sub> + *θ*<sub>1</sub>*Y*<sup>*a* = 0</sup> + *θ*<sub>2</sub>*L*
We can never actually fit this model because we do not know *Y*<sup>*a* = 0</sup> for all participants (we do know it for *some* participants, but other participants received the treatment and therefore *a* = 1 for them).

Because we know that *Y*<sup>*a* = 0</sup> should be independent of A (given L) then we know that *θ*<sub>1</sub> should be equal to 0. Therefore, we need to find a value for *Y*<sup>*a* = 0</sup> where *θ*<sub>1</sub> = 0.

Finding *θ*<sub>1</sub> = 0
===========================

*E*\[*Y*<sup>*a*</sup> − *Y*<sup>*a* = 0</sup>|*A* = *a*, *L*\]=*β*<sub>1</sub>*a* *E*\[*Y*<sup>*a*</sup> − *Y*<sup>*a* = 0</sup>|*A*<sub>1</sub>*L*\]=*β*<sub>1</sub>*a*

Again this appears to be complicated but it's just a statement of the average causal effect in a structural nested mean model. The assumption is that the treatment effect *β*<sub>1</sub> will be the same for observations with the same *L*.

This equation is for the study population--it's the average causal effect, but we can write it for an individual too:

*Y*<sup>*a*</sup> − *Y*<sup>*a* = 0</sup> = *γ*<sub>1</sub>*a*

Using this formula we can use basic algebra to rewrite it:

*Y*<sup>*a* = 0</sup> = *Y*<sup>*a*</sup> − *γ*<sub>1</sub>*a*
*Y*<sup>*a* = 0</sup> = *Y* − *γ*<sub>1</sub>*A*

We don't know *γ*<sub>1</sub> though. This is the counterfactual outcome for an observation so we can't really ever know it.

*H*(*γ*<sub>1</sub> = 0)=*Y* − 0 \* *A*
Systematically plugin values for *γ* until *H*(*γ*)=0.
