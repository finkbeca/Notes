---
title: Formal Verification
weight: 2
bookToc: true
katex: true


---

Two broad approaches for smart contract formalization: contract level and program level

- contract level considers high level details and not implementation and analysis. 
- Program level deals with modeling and analysis

program level typically deals with analysis of compiled bytecode. (Platform dependent)

Contract level deals with contracts as viewed as a black box and deals with it at a higher level only worrying about change of state, users, contract features. 

Majority of contract level are verified through model checking. 


Program level models aim to view contracts based on lower level representations like source code. 


An AST or Abstract Syntax Tree represents a smart contract source code as a hierarchial tree structure.  This can often be used for checking predefined code patterns.  An example of this is checking the compliance of a smart contract to the ERC20 standard. Furthermore, it could be use to located overflow and other pre analyses. 

AST acts as a precheck for more stringent methods.

Control Flow Graph, a graph to describe the operational semantics of a program.  Often created from bytecode, but still not an easy solution. 

Example of a CFG for ethereum is Ethainter

Program logics are a set of formla rules that allow for static ruling about a program. 

Lolisa: a formal syntax and semantics for Solidity

\mathbb{K} is a framework for design for smart contract semantics. It has been used to define formal semantics for EVM and solidity. 

### Types of Specification for Smart Contracts

Contract level specification: expressed through various types of logics for high level features of a smart contract.

- Temporal Logic: expressed properties over time.

- Linear Temporal Logic: properties of a smart contract over a certain amount of state changes to a system.

- Dynamic Logic, allows for the analysis of a system through actions. 

Program Level Specification , these mostly related to Hoare-style specifications, and events during execution. 
 - A Hoare style specification of a smart contract consists of preconditions , postconditions, and invariants for loops, functions .  Thus it can capture semantic correctness as well as general vulnerabilities. 

 An example of this might be an access check that is often checked in smart contracts through a require statement. 

 They can be used through assertions or program logic. 

 In solidity require, and assert are example of hoare-style properties that can be added directly to a smart contract through its compiled language. 

 Verisol translates a state machine policy of a smart contract into a hoare style source code assertion. 

 Possibility for prebuilt assertions for smart contracts. 


 ### Verification Techniques

 Model Checking automates the verification of a system model against its specification. Limited by the input language of a model checker, it can handle systems of interacting smart contracts and well as users. 

 Theorem Proving is verifying through encoding a system and its desired properties into mathematical logic. Then a theorem prover can try to prove this, if proven the system then works.  These systems are typically not entirely automated and rely on input, but can verify infinite systems. 

 Symbolic execution, executes a program symbolically and able to go through multiple execution paths at the same time. This system is built through traversing the CFG of a smart contract, built from its bytecode.  Cons: CFG modeling is often hard, and often hash heavy. 

 This system is used most often to find pre-analyses patterns in the contract to be corrected. 

 Program Verification:
 Automated system for verification that can check for composite security risks, semantic correctness. The biggest problem for program verification is that it relies on a well built memory and execution model. 

 Solidity and Move can both be translated to Boogie to verify Hoare style semantic properties as well as secure compilation. 

 Program verification is often seen to be a more realistic setting than model checking as modeling checking suffers from state explosion. 

 Runtime Verification, lightweight verification technique that checks the properties of a running program. Typically perform verification on chain. 

 verification technique depends on model and what specification is aimed at. 

 Program verification translates a smart contract to a verification language allowing for data and control flow to be analyzed allowing for more composite verification techniques. 


 If a programmer writes a functional correct properties for a contract the move prover can verify this.  (Hoare- verifier)


 Move has been designed with verification in mind, unlike EVM where it is not built with verification in mind. 

 All standard library modules are built to include formal specifications, with the belief that implementing the procedure from the beginning will bring rise to formal specification being used across the ecosystem. 

 IN move resources types are linear, and thus cant be created or copied or destroyed except by procedures in its declaring module. This provides for a languange secure against for accidental deletions and copies outside of the module. Besides this Move also had fewer types than many smart contract langauges, only having primitive types, vectors, and references.

 One of the notable differences between Move and Solidity is its lack of dynamic dispatch a feature that allows for the re-entrancy bugs that are common in Solidity. Overflow detection is calculated automatically on execution.

 On top of a program verification prover, Move uses a symbolic execution verifier to verify semantics before execution:
 1. Procedures / structs are well typed
 2. Modules depedencies are not circular
 3. Dependent modules exist
 4. Mutable reference has exclusive access
 5. no dangling references
 ....

 These are ran on the move bytcode and not the compiled language, if they were ran on the Move langauge, it would be possible to bypass this verifier through writing a module directly in bytecode. 


 Move contract with specification -> specfication functions seperated from contract -> Move contract compiled into bytecode -> converted to verification model for Move -> specifications are then also converted and added to this model -> model is translated to boogie where it can be verified 

 The boogie langauge is not executable but rather acts as inputs into a Boogie program which converts the model into a SMT formula which could then be solved with a SMT-solver

 Model source language in Boogie -> Translated to IVL -> inputs into a SMT problem

 