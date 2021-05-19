---
title: Diem
weight: 2
bookToc: true
---

## Diem Notes

[Diem Docs](https://developers.diem.com/main/docs)   


Libra core is an open source implementation of the libra protocol. 
Move is used to define core mechanisms of the blockchain such as currency and validator memberships. 

-All data in the Libra Blockchain is a single versioned database
- The ledger state represents the ground truth about the Libra ecosystem including the quantity of Libra held by each user at a given version. Each validator must know the ledger state to process new transactions. 

- Acount adresses are intiated when a transaction is sent to it, however it must also have a public/private key. This private key can then be used to authenticate future transactions from such account. 

- Move Modules contain move bytecode that declares resources type and procedures. They are attached to an address of the account, and must be uniquely named within the account. 
- Modules are immutable. 
- The ledger history stores the sequenced of committed and executed transactions as well as the associated events that were emmitted. 

- Genesis is the intial ledger state of the chain, where the modules are intialized. 

- Agreements on the database state must be reached between validators even if there are Byzantine faults. Byzantine faults are modeling worse case errors where validators act malicious and therefore protect against smaller faults like software failurue as well. 

### Transactions 

- A new transaction on diem is in fact requesting the ledger state to be updated with their transaction information.  
- A signed transaction on the blockchain contains a signature, sender address, sender public key, and a program (bytecode script; smart contract, option inputs like recipient information and amount transfered, as well as a further list of bytecode modules to pulbish), gas price, and the max gas amount  allowed to consume. Furthermore the currency code for the gas, the sequence number and the expiration time all are include in the transaction.   

- Each validator node in the blockchain must know the global state of the last version of the blockchains database.   
- The versioned database of the blockchain allows validators to execute a transaction and respond to client quereies about ledger history.   

### Validator Nodes

- A diem node is a peer entity that tracks the state of the diem blockchain.    
- two types of nodes, validator nodes and full nodes.   
- Diem payment network  uses a byzantine fault tolerance (BFT) consensus for validator nodes to agree on finalized transactions before processing them and adding them to the chain creating a new state.   
- Full nodes are external validation for complete transaction history  
- Full nodes can be run by anyone who wants to verify the state of the diem blockchain and synchrnoize to it.   

### Accounts
- An account representes some entity that can send transactions on diem, each account has an address and acts as a container for move resources and moudules.  
- The state of each account has both code and data, code is the move module where the move resources are purely data related.   
- Each account stores an authentication key used to authenticate the signed of a transaction. DPN rotates the auth key without changing the adress  
- To generate a auth key and address, a key pair is neeeded to be generated as well as te auth key to be derived fwith the account address and public key.   
- The process for a multsig account is similiar to that of creating a single signature one.   

- Every account is created with atleast two resources Roleld which grants the account a single immutable role for acess control  
- DiemAccount which holds the account's seuqnece number , auth key and event handles.  
- DPN supports account transacting in different currencies  
- Diem<Cointype> is equal to ERC20  
a zero balance of Diem<Cointype> is added when Diem<Cointype> is authroized from an account, each account stores one or more balance cointype resources. For each currency type thtat the accounts holds there will be a seperate balance resource such as balance <Diem<Coin1>> or Balance <Diem<XUS>>
- To send and receive Diem<Cointype> the receiving account must have a balance in that account which is a form of verify its approval. 
### Gas 
- Gas ensures that move program terminate and act as a tranaction fee. 
- Gas is max gas_price * max_gas_amount
- Transactions are prioritized based on the normalized gas price for the transaction. 

### Events

- Events are move data that are emitted during the execution of a transaction on the diem blockchain
-  events are grouped into event streams based on event type, like minting, burning, payments, and system operations. 
- event types has different event streams
- each event stream has a unique event key tied to the account's event stream.  
