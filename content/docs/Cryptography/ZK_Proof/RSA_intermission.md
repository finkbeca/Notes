---
title: RSA Intermission
weight: 2
bookToc: true

---

# RSA Intermission

a + b = c (mod n) == (a+b) mod n = c mod n

Prover comes up with 

p,q two random secret primes

n := pq

d: random number such that 1 < d < n-1

e: a number such that de congruent 1 (mod (p-1)(q-1))

c^d =  (m^e % n)^d = m^(ed) mod n

RSA is multipliacateively homorphic. Two operations are homomorphic if you can exchange their order without affect the result.

Thus the product of the encryption of the two messages is equal to the encryption of the product of the messages

The prover knows some secret numbers x and y and computers their product but only sends the encryption version such that a=E(x), b = E(y), and c = E(x,y) to the verifier. The verifier now checks that (a b) % n congruent c % n and the only thing learned is the encrypted version of the product and its correctness