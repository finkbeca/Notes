---
title: "Convex Optimization"
weight: 1
bookFlatSection: false
bookToc: true
bookHidden: false
bookCollapseSection: false
#bookComments: false
---

## Notes 
Suppose $x_1 \neq x_2$ and $y = \theta x_1 + (1- \theta)x_2 $ where $\theta \in \mathbb{R}$ and the thus forms the line passing through the points $x_1,x_2$.

This is known as an affine set , more formally a set $C \subseteq \mathbb{R}^n$ is known as affine if the line through two distinct points in C lies in C.

This can be expanded to any arbitary linear combination assuming that all the points in C sum to 1.

The set of all affine is the set of all affine combinations of elements in some arbitrary set C

The affine dimension of set C is the dimension of its affine hull.

A set is convex if the line segment between two points in C lies in C. More formally $\forall x_1, x_2 \in C, \theta x_1 + (1- \theta)x_2 \in C $. This can be further expander to arbitrary linear combinations  $\theta x_1 + ... + \theta x_k $ where $\theta_1 + ...+ \theta_k = 1$.

The convex hull is the set of all convex combination of points in c. Also referred to as the convex span over C

A set is called non-negative homogenous if for every $x \in C$ and $\theta \geq 0$ it follows that $x\theta \in C$. 

This further can be expanded to an arbitral numbered linear combination in C

A convex cone is a subset of a vector space over an ordered field that is closed under linear combinations with positive coefficients. 

A conic hull is the smallest convex cone that spans the set C.

Any subspace is affine and there it must also be affine, as any affine space is a convex set.

A hyperplane is a set of the form $\{x \mid a^T x = b \}$ where $a \in \mathbb{R^n} $ and $b \in \mathbb{R}$/

A hyperplane divides $\mathbb{R^n} into two halfpsaces. Each half space are convex.

Convexity preserves intersection of convex sets.

Scaling, translations, and projects also preserve convexity.

There is not a universal definition of a proper cone but it typically refers to a cone that convex, closed, fully dimensional and pointed.

Hyperplane separation theorem
Let A and B be two disjoint nonempty convex subsets of $\mathbb{R^n}$. Then $\exists v \in \mathbb{R_+^n}, c \in \mathbb{R}$ st $<x,y> \geq c, <y,v> \leq c \forall x \in A y \in B$. In other words the hyperplane $<\cdot, v> = c$ where v is the normal vector separates A and B. 

Let K be a non-empty closed subset of $\mathbb{R^n}$ then it folows there there exists some unique vector in K of minimum norm length. 
## Applications