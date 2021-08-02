---
title: Snarks
weight: 2
bookToc: true

---


# Snarks

## Notes

### Homomorphic hiding
(This is intro knowledge and not typically used for SNARKS)
- An HH (Homomorphic hiding) E(X) of a number x is a function that satisfies:
1. for most x given E(x), x is hard to find  
2. Injectivity  
3. If someone knows E(x) and E(y) we can generate the HH of arithmic expressions in x and y (i.e they can compute E(x + y))  
- This leads the checker to being able to check that E(x + y) = E(expected result) given E(x) and E(y) without knowing x or y

- HH are constructed in the set {{<katex>}}Z\mathbb{Z}_p^*{{</katex>}} which has the properties of multiplication mod p and addition mod p. Where p is some prime.
- {{<katex>}}\mathbb{Z}_p^*{{</katex>}} is a cycclic group meaning that some element g in this group such that all elements of the group can be written as {{<katex>}}{g^a{{</katex>}}.
- Note: the discrete log problem is believed to be hard in this group meaning given a large p and an element h in said group it would be hard to compute {{<katex>}}g^a = h \mod p{{</katex>}}
- Exponents add when elements are multiplied

-Within {{<katex>}}\mathbb{Z}_{p-1}^*{{</katex>}} we can now construct an HH where x is an element of this group and {{<katex>}}{E(x)= g^x{{</katex>}}
- Note HH are a weaker version of computationally hiding commitment, and only hides most xs

- HH are also closed under linear combination, it is a common approach known as blind evaluation where the verifier may have a correct polynomial in mind and will send components of a random linear combination (E(1), E(S), ... ) to the prover to be computed together under a secret function P. 

- Using the extended version of the Knowledge of Coefficient Assumption we can add verifiability of E(P(x)) to our protocol's solution. 
- In general when she is sent multiple a pairs the verifier will be able to create a linear relation between each pair sent and the new found pair.
- A more formal version of this was introduced by Groth and is known as the d-KCA.

### QAP
- QAP known as Quadratic Arithmetic program is a way for computations to be turned into polynomials. 

- An arithmetic circuit consists of gates computing arithmetic operations like addition and multiplication, with wires connecting the gates. Generally bottom wires are input and the top wire is the output.

- A legal assignment for the circuit is an assignment of values to a labeled wire where the output value of each multiplication gate is indeed the product of corresponding inputs. (exp  let the form be {{<katex>}}(c_1, ... c_5){{</katex>}} where {{<katex>}}c_4 = c_1 \cdot c_2{{</katex>}} and {{<katex>}}c_5 = c_4 \cdot (c_1 + c_3)  {{</katex>}}

-  Next step would be to reduce the circuit to a QAP.

- Firstly, associate each multiplication gate with a field element {{<katex>}}g_1, g_2{{</katex>}} where the first is associated with 1 and the latter with 2. These are known as target points.  Next we define a set of left wire polynomials, right wire polynomials and output wire polynomials

- The key point to QAP is that the set {{<katex>}}(c_1, ... c_5){{</katex>}} is only a legal assignment iff P vanishes on all the target points.