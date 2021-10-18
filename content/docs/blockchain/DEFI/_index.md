---
title: DEFI
weight: 2
bookToc: true
---
# DEFI
---
## Links
[AAVE Documentation](https://docs.aave.com/developers/)  
[Building Smart Contracts on AAVE](https://www.chainshot.com/learn/aave) 
[AAVE Credit Delegation](https://docs.aave.com/developers/v/1.0/developing-on-aave/the-protocol/credit-delegation ) 
[AAVE Lending pool Contract](https://docs.aave.com/developers/the-core-protocol/lendingpool )
[Credit Delegation ShowCase AAVE](https://showcase.ethglobal.co/marketmake/aave-credit-delegation)

## Notes
Most popular protocols for swapping tokens use invariants. Invariants are algorithms for alp that express the relation between reserve of two distinct assets. 
- YieldSpace's [whitepaper](https://yield.is/YieldSpace.pdf) has a great section on invariants used for each protocol. 
---
##


### C.R.E.A.M Finance
- CREAM is a decentralized lending protocol for individuals and protocols to access financial services.  Users are able to lend any supported assets on the markets and use the capital as collateral to borrow another supported asset. 

- What is the Iron Bank? The iron bank offers services to both individual users and protocols, allowing a small whitelisted list of protocols to borrow from the pool of assets with little collateral.  Credit Risks are managed through a combination of smart contract security review , insurance coverage, and financial backstop.

- Assets supplied to the Iron Bank are held in separate pools from those on CREAM v1. Two different asset pools (or banks).

- Anyone can deposit into the iron bank. 

- Yields in the iron bank generally range from 20-40% APY on stable coin deposits

- THe iron bank has a higher utilization ratio then CREAM v1 meaning the ratio of borrowed assets vs total supply assets is higher leaving to lower available liquidity. 

- Protocols must be approved to be under collateralize from the Iron Bank, they are approved by the CREAM team. Protocols must of had a good reputation/ track record, security audits, insurance coverage, and liquidity. 

- Iron Bank currently uses Chainlink oracle for its assets.


### Everlasting Options

long-tem options exposure without expense of rolling positions.

a European options payoff can be calculated at any point not just expiration

One of the prior uses cases for options is to hedge against risk, as options expire, the agent heding will eventually have to roll over there positions to a further date. 

Spreads are a fee that market makers charge on trades, as they don't know who will trade with them or against them. 

Spread is especially high for options making rolling over positions a costly feat. 


Perpetual futures try to solve this problem giving future exposure as long as an agent may want it, while concentrating liquidity into unique for each asset. 

Perps work by having those who went long on a given day, pay a funding fee to those who are short. This is calculated as the price of the perp - price of the underlying. Therefore it the perp is valued at a higher price than the underlying , it will be more expensive for those who go long and thus they would most likely sell lowering the perp price. 

Everlasting options work a similar way to perpetual futures but for options, instead of the fee being mark-index, it is now mark-payoff. 

The fee is calculated again daily, but can also be rewritten to work on an hourly system instead.

Everlasting options are equiv to a constantly rolling options portfolio. 