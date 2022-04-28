---
title: Solana
weight: 2
bookToc: true
---

### Overview
[Solana White Paper](https://solana.com/solana-whitepaper.pdf)
Implements PoH for verifying the passage of time, that can be use along side a PoW / PoS. PoH can reduce messaging overhead for a BFT replicated state machine.  

Transaction is sent to a node leader, who orders transitions who are then sent through verifiers (a non-elected node) who verify these signature and send the computer signatures as votes for a consensus algorithm. 

### PoH
Given an crptographic hash function with some intial seed, and interval outputs of the hash output, assuming this function is collision resistant, this could act as a single clock, as any party could rerun the hashes from the beginning to get the right time, and there is no way to predict future output. This could then be added with "a combine function" combining data on -chain to verify when data was added. Verification can be done much faster via multi-core computation. 




Questions:

Does local clocks used on systems like Ethereum allow for MEV positions that would not be found on Solana? What other aspects does this break, besides security?
