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
Suppose {{<katex>}}x_1 \neq x_2{{</katex>}} and {{<katex>}}y = \theta x_1 + (1- \theta)x_2 {{<katex>}} where {{</katex>}}\theta \in \mathbb{R}{{</katex>}} and the thus forms the line passing through the points {{<katex>}}x_1,x_2{{</katex>}}.

This is known as an affine set , more formally a set {{<katex>}}C \subseteq \mathbb{R}^n{{</katex>}} is known as affine if the line through two distinct points in C lies in C.

This can be expanded to any arbitrary linear combination assuming that all the points in C sum to 1.

The set of all affine is the set of all affine combinations of elements in some arbitrary set C

The affine dimension of set C is the dimension of its affine hull.

A set is convex if the line segment between two points in C lies in C. More formally {{<katex>}}\forall x_1, x_2 \in C, \theta x_1 + (1- \theta)x_2 \in C {{</katex>}}. This can be further expander to arbitrary linear combinations  {{<katex>}}\theta x_1 + ... + \theta x_k {{</katex>}} where {{<katex>}}\theta_1 + ...+ \theta_k = 1{{</katex>}}.

The convex hull is the set of all convex combination of points in c. Also referred to as the convex span over C

A set is called non-negative homogenous if for every {{<katex>}}x \in C{{</katex>}} and {{<katex>}}\theta \geq 0{{</katex>}} it follows that {{<katex>}}x\theta \in C{{</katex>}}. 

This further can be expanded to an arbitral numbered linear combination in C

A convex cone is a subset of a vector space over an ordered field that is closed under linear combinations with positive coefficients. 

A conic hull is the smallest convex cone that spans the set C.

Any subspace is affine and there it must also be affine, as any affine space is a convex set.

A hyperplane is a set of the form {{<katex>}}\{x \mid a^T x = b \}{{</katex>}} where {{<katex>}}a \in \mathbb{R^n} {{</katex>}} and {{<katex>}}b \in \mathbb{R}{{</katex>}}/

A hyperplane divides {{<katex>}}\mathbb{R^n} {{</katex>}} into two halfpsaces. Each half space are convex.

Convexity preserves intersection of convex sets.

Scaling, translations, and projects also preserve convexity.

There is not a universal definition of a proper cone but it typically refers to a cone that convex, closed, fully dimensional and pointed.

Hyperplane separation theorem
Let A and B be two disjoint nonempty convex subsets of {{<katex>}}\mathbb{R^n}{{</katex>}}. Then {{<katex>}}\exists v \in \mathbb{R_+^n}, c \in \mathbb{R}{{</katex>}} st {{<katex>}} \langle x,y \rangle \geq c,  \langle y,v \rangle \leq c \forall x \in A y \in B {{</katex>}}. In other words the hyperplane {{<katex>}} \langle \cdot, v \rangle = c{{</katex>}} where v is the normal vector separates A and B. 

Let K be a non-empty closed subset of {{<katex>}}\mathbb{R^n}{{</katex>}} then it follows there there exists some unique vector in K of minimum norm length. 

A real value function is called convex if the line segment between any two points on the graph lies above the graph of two points. 

A twice differentaible function is convex iff its second derivative is nonnegative over the entire domain. 

On an open set a strictly convex function only has one minimum (This could be generalized to infinite dimensions with additional assumptions)

Let {{<katex>}}C \subseteq \mathbb{R^n} thus f : C \rightarrow \mathbb{R}{{</katex>}} where {{<katex>}}C{{</katex>}} is a convex subset of a vector space. f is convex iff for all {{<katex>}}0 \leq t \leq 1{{</katex>}} and all {{<katex>}}c_1, c_2 \in C f(t c_1 + (1-t)c_2) \leq t f(c_1) + (1-t)f(c_2){{</katex>}}

The function f is said to be concave if {{<katex>}}-1 \cdot f{{</katex>}} is convex 

Example {{<katex>}}x^3{{</katex>}} is said to be convex when {{<katex>}}x \geq 0{{</katex>}} and concave when {{<katex>}}x \leq 0{{</katex>}}.
## Applications

- [CVXPY Convex Optimization Library](https://www.cvxpy.org/)  