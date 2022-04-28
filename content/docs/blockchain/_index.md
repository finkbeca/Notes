---
title: Blockchain
weight: 2
bookToc: true
---

# Blockchain

## Databases
Reserach Databases of published papers: 
[Cryptoeconomic System](https://cryptoeconomicsystems.pubpub.org/vol1-1)
[Blockchain Research Network](https://www.zotero.org/groups/2216205/blockchain_research_network/items/QXNEQXJ9/library)


## Ethereum
[Ethereum Foundation](https://ethereum.org/en/)  
[More Bonding Curves](https://blog.aventus.io/more-price-functions-for-token-bonding-curves-cfb1ebb5b659)  
[Bonding Curves](https://medium.com/coinmonks/token-bonding-curves-explained-7a9332198e0e)  
[Quadratic Arithmetic Programs](https://medium.com/@VitalikButerin/quadratic-arithmetic-programs-from-zero-to-hero-f6d558cea649)  
[Lex Dao](https://lexdao.org/#/)  
[Molloch Dao](https://www.molochdao.com/)  
[Ethereum Foundation Research Goals](https://hackmd.io/Mt1zHT61RYOMuJ5OKLuHoA?view)  
[Challenges Ethereum](https://challenges.ethereum.org/)  
[Ethereum Wishlist](https://esp.ethereum.foundation/en/wishlist/)  
[Research Forum](https://ethresear.ch/)  
[Blockchain Monitior Weekly Articles](https://www.theblockchainmonitor.com/)  
[DEFI exploits and smart contract security ~ Video](https://www.youtube.com/watch?v=95_RmIAqRy0)  
[Decentralzied Credit Scoring](https://union.finance/)  
[Vyper IDE](https://vyper.online/)  
[Vyper by Example](https://vyper.readthedocs.io/en/latest/vyper-by-example.html) 
[Building Smart Contracts on AAVE](https://www.chainshot.com/learn/aave)  
[Mechanism Capital Research Articles](https://www.mechanism.capital/)
[Femboy Capital MEV Summary](https://femboy.capital/SummitSummaryPt1)
***GSN***
Uses metatransactions (collect calls) to minimize onboarding and for UX friction. It takes away the need for clients to have to have gas to pay for transaction fees. 
  
- Allows gas to be paid in any token   
- Allows gas to be paid in fiat  
- Enables more privacy for accounts  
- Reduces onboarding cost for new members  

This works as a relay server can send a user's transaction for them and pay themselves for the gas cost. Instead of signing an Ethereum transaction, users sign a message containing information about a transaction that they wish to be executed and sent ona relay server. The relay server is then refunded for the gas cost by the paymaster contract.  

Each dapp having an relay service , provides this service at-cost to each user. If one dapp's relay server would of went down then the transaction can be routed to another dapp's relay server with a premium fee. This strengthens the overall network. 

In the GSn all access and refund logic is implemented within the paymaster contract. A paymaster has a gas tank of ETH in the RelayHub and can implement logic to decide whether to accept, or reject a meta transaction. (This could because it only accepts whitelisted users, or some other contract method used for onboarding).

To use meta transactions ```msg.sender``` is replaced with ```_msgSender()```.

Relay Hub connects uses running clients, relay servers , and paymasters so that participants don;t need to trust each out. 

*** Writing a GSN-Enabled Smart Contract ***
- Inherit from BaseRelayRecipient contract
``` import "@opengsn/contracts/src/BaseRelayRecipient.sol";

contract MyContract is BaseRelayRecipient {
    ...
} ```

Use ```_msgSender() ``` instead of ```msg.sender```.

Note: If using other third party contracts they may  be unsafe to mix with BaseRelay Recipient, due to using msg.sender

In order to start paying the meta-transaction fees, a Paymaster contract is needed. This contract is inherited from BasePayMaster, and requires implementations of preRelayedCall and postRelayed Call. The contract is lastly needed to be deployed and configured with the RelayHub address. 

Paymaster will be charged for transactions after it consumes the amount of gas limited by ``` GasLimits.acceptanceBudget``` even it reverts the call. Due to this be careful how you manage transactions, and only accept transactions you trust to go through. Some ways to do this include, onboarding functions, whitelisting users, delegating this procedure of chain, or charging in tokens.

PostRelayedCall, provides measures for the paymaster contract to charge the user for the call, other book keeping methods, as well as a good estimate of the transaction cost

If a preferred relay is not configured, all transactions will be routed through third party relay servers for an extra fee.

*** Rollups ***
- A rollup can be thought of as a separate blockchain, it again has a vm to execute smart contracts, this vm would act independently to EVM, instead it would be managed by a smart contract A rollup would execute transactions and process data, and allows Ethereum to receive this information and eventually store the results. 

- The main difference between a rollup and the main chain would be how blocks are produced, rollups do not operate in terms of a majority but instead as a single monitoring party. These decisions by this party are sent back to the main net 'Ethereum' where it is approved or reject. Note that this in itself is not a security issue for decentralization. All transaction calldata is still stored on the main chain with the computation being all done on the rollup.  Keeping transaction data on chain allows for all computations to be repeated on the ethereum base layer. This can act as a review process where the base layer can review and double check rollup confirmations. 

- The review process differs whether ZK or Optimistic rollups are used but both means are much more efficient then computing on chain. 

- Rollsup main purpose is to help move computation offchain, while keeping the data on chain, and reviewing it before the blocks are finalized acts as a very to verify the rollup transactions are right. 


## SideChains
EVM Side Chains
[Avalanche](https://www.avalabs.org/)  
[Celo](https://celo.org/)  
[Solana](https://solana.com/)  
[NEAR](https://near.org/)  
[Polkadot](https://polkadot.network/)  
[Solana basics](https://2501babe.github.io/posts/solana101.html)


## Bitcoin
[Script](https://en.bitcoin.it/wiki/Script) Bitcoin Script  
[BTC](https://blockgeeks.com/guides/best-bitcoin-script-guide/)  
### BSV
Developer Links for BSV  
[Money Button](https://github.com/moneybutton/bsv) - Developer tools    
[Money Button](https://www.moneybutton.com/)  
[Scrypt](https://github.com/scrypt-sv/bsv)  
 


## Misc
[Intro to Verifiable Delay Functions](https://www.youtube.com/watch?v=3hg4GM7UQXA) 
[Penumbra](https://penumbra.zone/index.html) 

