---
title: Parameter Generation
weight: 2
bookToc: true

---

# Parameter Generation

IN zcash the circuit (transaction verifier) is fixed and thus the polynomials for the QSP are fixed which allow the setup to be prreformed only once. Varying in only the input u.

Zcash zk proofs rely on public parameters which allow users to construct and verify private transactions.

Must be set up in a set up phase, random numbers are sampled and refered to as toxic waste to construct parameters, this waste must then be destroyed

Multi-party computation ceremonies ensure that toxic waste does not come into existence through multiple step independent parties construction of a ceremony. For the final parameter to be compromised all the participants would have to be compromised.

## Sapling

Zcash second set of public parameters

### Powers of Tau

A multi-party computation ceremony which reached its conclusion in early 2018, coordinated through a public mailing list

### Sapling MPC

The Zcash Company hosted MPC for the final parameter construction.over 90 contributions were completed and the final parameter was included in the 2.0.0 release

## Overview

All participants play a similiar role having their machines randomly sample a part of the toxic waste and this part or shard to perform computations. COmmunication takes place during this period and is not seen as sensitive. However they do no communicate directly but through a coordinated server that acts as a bridge.

### Commitment Phase

Each node randomly generate their shard of the toxic waste providing random text to provide additional entropy to the Linux RNG machine. A  special key is then consturcted to verify the evaluation and bind participants.

### Stage 1/ Power of Tau

The coordination initializes the initial state and each participant performs a transformation on this state which is passed to the next participant.

### Stage 2

Similar to Stage 1 but more complex and takes much longer for each participant to complete their role.

### Stage 3

Similar but less expensive computations and faster then either previous stage.