---
title: Blockchain
weight: 2
bookToc: true
---

# Blockchain

 A topic I have been  passionate about for some time now. 

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

***GSN***
Uses metatransactions (collect calls) to minimize onboarding and for UX friction. It takes away the need for clients to have to have gas to pay for transaction fees. 
  
- Allows gas to be paid in any token   
- Allows gas to be paid in fiat  
- Enables more privacy for accounts  
- Reduces onboarding cost for new members  

This works as a relay server can send a user's transaction for them and pay themselves for the gas cost. Instead of signing an Ethereum trasaction, users sign a message containing information about a transaction that they wish to be executed and sent ona relay server. The relay server is then refunded for the gas cost by the paymaster contract.  

Each dapp having an relay service , provides this service at-cost to each user. If one dapp's relay server would of went down then the transactios can be routed to another dapp's relay server with a premenium fee. This stregthens the overall network. 

In the GSn all acesss and refund logic is implemented within the paymaster contract. A paymaster has a gas tank of ETH in the RelayHub and can implement logic to decide whether to accept, or reject a meta transaction. (This could because it only accepts whitelisted users, or some other contract method used for onboarding).

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

Paymaster will be charged for tranactions after it consumes the amount of gas limited by ``` GasLimits.acceptanceBudget``` even it reverts the call. Due to this be careful how you manage transactions, and only accept transactions you trust to go through. Some ways to do this include, onboarding functions, whitelisting users, delegating this procedure of chain, or charging in tokens.

PostRelayedCall, provides mesasures for the paymaster contract to charge the user for the call, other book keeping methods, as well as a good estimate of the transaction cost

If a preferred relay is not configured, all transactions will be routed through third party relay servers for an extra fee.



## SideChains
EVM Side Chains
[Avalanche](https://www.avalabs.org/)  
[Celo](https://celo.org/)  
[Solana](https://solana.com/)  
[NEAR](https://near.org/)  
[Polkadot](https://polkadot.network/)  
[Findora](https://findora.org/)  

## Bitcoin
[Script](https://en.bitcoin.it/wiki/Script) Bitcoin Script  
[BTC](https://blockgeeks.com/guides/best-bitcoin-script-guide/)  
### BSV
Developer Links for BSV  
[Money Button](https://github.com/moneybutton/bsv) - Developer tools    
[Money Button](https://www.moneybutton.com/)  
[Scrypt](https://github.com/scrypt-sv/bsv)  
[Uniwriter](https://coingeek.com/unwriter-unveils-bitpic-for-bitcoin-sv-blockchain/) - BSV Developer  


## Misc
[Intro to Verifiable Delay Functions](https://www.youtube.com/watch?v=3hg4GM7UQXA) 
[Penumbra](https://penumbra.zone/index.html) 

