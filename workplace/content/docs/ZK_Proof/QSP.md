---
title: Quadratic Span Program
weight: 2
bookToc: true

---

# QSP (Quadratic Span Program)

A Quadratic Span Program consists of a set of polynomials and a task is to a find a linear combination of those that is a multiple of another given polynomial.

A QSP over a field F for inputs of length n consists of

1. a set of polynomials over the field F
2. a polynomial t over F (target polynomial)
3. an injective function

The task is roughly multiply the polynomials by factors and add them so that the sum , the linear combination is a multiple of t. For each binary input string u the function f restricts the polynomial that can be used.

The reduction from generic computations or circuits to SQP is the hard part as it has to be done in a efficient way to get it as small as possible.

## Setup detail

The setup generates the common reference string CRS the verifier chooses a random field element s and encrypts the values of the polynomials at the given point. The verifier uses some specific encryption E and publishes E(v_k(s)) and E(w_k(s)) in the CRS. The CRS also contains several other values which makes the verification more efficient and adds the zk property. The encryption E has certain homeomorphic propertyes that the prover can computer E(v(s)) without knowing v_k(s)

## Encrypted evaluation of a polynomial at secret points

Fix a group, typically an elliptic curve and a generator g. (Note that a group element is called a generator if there is a number n st the list {{<katex>}}g^0 g^1 g^{n-1} {{</katex>}}contains all elements in the group. The encryption E(x) := g^x.

The verifier chooses a secret field s and publishes as part of CRS

E(s^0), E(s^1),.... E(s^d) is the max degree of all polynomials.

S then **HAS** to be forgotten

 Using these values, the prover can computer E(f(s) for arbitrary polynomials f wihtout knowing s. Assume our polynomial is {{<katex>}}f(x) = 4x^2 + 2x +4 {{</katex>}}and we want to computer E(f(s) then we get {{<katex>}} E(f(s)) = E(4s^2 +2s+4) = g^4s^2 +2s +4 = E(s^2)^4* E(s^1)^2 * E(s^0)^4 {{</katex>}} which can be computed from CRS

Another secret field element a is needed and we need to publish {{<katex>}} E(as^0), E(as^1) E(as^d) {{</katex>}}and a is then destroyed

A prover publishes A:=E(Fs) and B:= E(af(s) and the verifier has to check that these values match. The verifier does this through a pairing function e. This has to be chosen together without the elliptic curve thus {{<katex>}} e(g^x, g^y) = e(g,g)^(xy){{</katex>}} 

{{<katex>}} e(A, g^a) = e(g^f(s), g^a) = e(g, g) ^a f(s) {{</katex>}}

{{<katex>}} e(B, g) = e(g^(af(s), g) = e(g,g)^(a,  f(s) {{</katex>}}