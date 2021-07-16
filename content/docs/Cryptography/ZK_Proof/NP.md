---
title: NP and Complexity-Theoretic Reduction
weight: 2
bookToc: true

---
# NP and Complexity-Theoretic Reduction

zkSNARKS only work for specific problems about polynomials.

Let us a function that only ouputs 0 or 1 is called a problem.

Measuring the complexity to solve a given function we can measure the machine implementation M of a mathematical function f, ie, count the number of steps it takes to compute f on a specific input x.

Known as the runtime of M on x. Thus a n^2 program is a program that takes n^2 steps on input size n.

## Two main class of problems in complexity theory are P and NP

P is a class of problems L that have polynomial time programs

There are zkSNARKS for all problems in the class NP. All problems in NP always have a certain structure.

NP is the class of problems L that have a polynomial-time program V that can be used to verify a fact given a polynomially sized witness. L(x) = 1 iff there exists some polynomially sized string such that V(x,w) =1 

For any NP-problem L there is a so-called reduction function computable in polynomial time such that L(x) = SAT(f(x))

i.e a compiler taking source code from one language and transforming it into a equivalent language is a reduction function. think high level language to assembly.