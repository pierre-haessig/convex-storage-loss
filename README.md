# Convex storage loss modeling

This repository contains research documents and code by Pierre Haessig
on the topic of _convex storage loss modeling_.
In particular the relaxation of losses as being _greater or equal_ than
(rather than equal to) a convex expression.

Pierre Haessig, 2020

License: Creative Commons Attribution 4.0 International ([CC BY 4.0](https://creativecommons.org/licenses/by/4.0)), covering all the text and the small pieces of code.

## Content

Index of the content (partial):

- Notebook [Energy_management_Convex_losses.ipynb](Energy_management_Convex_losses.ipynb)
  - comparison of several loss models on some simple example
- Notebook [Relaxation_failure_example.ipynb](Relaxation_failure_example.ipynb)
  - example where the relaxation fails (negative price + full storage event)
- Document [Literature_review.md](Literature_review.md)
  - analysis of previous work related to the topic

Notebook code is in Julia, using [JuMP](https://jump.dev/)
for optimization modeling and Ipopt or ECOS as solvers.
