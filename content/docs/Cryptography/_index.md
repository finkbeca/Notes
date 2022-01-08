---
title: Cryptography
weight: 2
bookToc: true
math: true
---

# Notes

- [Elanor Cryptography PHD substack](Inor.substack.com)  

- BIP32 Builds a binary tree of deterministic wallet addresses from a single key seed. 
- BIP39: The implementation of a mnemonic cod or sentence for the generation of deterministic wallets, consists of generating a mnemonic, as well as converting it into a binary seed which then uses BIP-0032 to make a binary tree to be used to create a host of deterministic wallets.  


# Fundamentals

### 2.1 Definitions
- An encryption scheme is defined by three algorithms, Gen, Enc, Dec, as well as a finite message space {{<katex>}} M {{</katex>}}, where {{<katex>}} |M| > 1 {{</katex>}}.  

- Gen is a probabilisitc algorithm that outputs a key k according to some distrubution.   

- We denote {{<katex>}} K {{</katex>}} as the finite key space, all possible keys that can be an output by Gen.   

- The encryption algorithm Enc, takes as input a {{<katex>}} k \in K{{</katex>}}  and a message {{<katex>}} m \in M {{</katex>}} and outputers a ciphertext c. We also Enc to be probablistic meaning that running Enc on m multiple times may result in different messages.    

- Let {{<katex>}} c \leftarrow Enc_k(m) {{</katex>}} denote the possibly probabilisitc process by which message m is incrypted using key k to give ciphertext c.  

- Simiarly we use {{<katex>}} x \leftarrow S{{</katex>}} to denote uniform selection of x from a set S.   

- We let C denote the set of all possible ciphertexts that can be output by {{<katex>}}Enc_k(m){{</katex>}}  for all possible k, m.  

- THe decryption algorithm Dec takes an input k and a ciphertext c and outputs a message {{<katex>}}m \in M {{</katex>}}.  

- We assume perfect correctness meaning that for all {{<katex>}} k \in K, m \in M{{</katex>}}  and any ciphertext c output by {{<katex>}} Enc_k(m){{</katex>}}, it holds that {{<katex>}} Dec_k(c)= m {{</katex>}} with probability 1.  

- the random variable K and M are assumed to be independent.  

- For a scheme to be perfectly secret, observing the ciphertext should have no effect on the knowledge regarding the actual message that was sent.  Meaning the ciphertext reveals nothing about the plaintext.  {{<katex>}} Pr[M=m | C=c] = Pr[M=m ] {{</katex>}}  given that {{<katex>}} Pr[C=c] > 0 {{</katex>}}  

- Alternatively we can define perfect secrecy as {{<katex>}}Pr[Enc_k(m) = c] = Pr[Enc_k(m') = c] {{</katex>}}. Therefore a encyrption scheme (Gen,Enc, Dec) with message space M is perfectly secret iff this holds for all {{<katex>}} m, m' \in M{{</katex>}}  and every c. 

- We define Adversarial indistinguishably as that given to messages that an adversary can not guess with more than 1/2 chance which message was encrypted, given a cipher text. 
