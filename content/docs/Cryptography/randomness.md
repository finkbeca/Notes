---
title: Randomness
weight: 2
bookToc: true
math: true
---


# Randomness

## Pseudorandom Random Number Generators

class of algorithms for generating a sequence of numbers whose properties approximate the properties of sequences of random number. 

Determined by an initial value called the seed. 

Uses:
- Monte Carlo method
- Cryptography
- Gaming

It is still a central topic if there is a reasonable and notable difference between a truly random number generator and a PRNG.

### CPRNG
Cryptographically secure pseudo-random number generators
These are random number generators that are secure enough to be used in cryptographic applications.

Uses: 
- Key generation
- nonces
- salts

Randomness is not the same, some solutions will require more entropy. 

Requirements:
- Pass statistical randomness tests
- Secure system even when state is known. 

Every CPRNG should satisfy that no poly-time algo could predict the next bit better than 50%


### VRF
- Chainlink is currently using a variable random function to provide pseudo random number generator on chain

### Hardware RNG
 This is known as a true random number generator and basics number generation on physical process.

 - Widely used in encryption protocols like Transport Layer security.

- Unpredictable macroscopic proccesses like lottery machines could be used as well as micro level hardware components. 


PoS based hardware random generator. 

Cardano using their PoS system for a random number generator.   
[Drand](https://research.protocol.ai/talks/drand-distributed-bias-resistant-unpredictable-and-publicly-verifiable-randomness/)  
