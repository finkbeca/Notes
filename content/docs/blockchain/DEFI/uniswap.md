---
title: Uniswap
weight: 2
bookToc: true
---

# Uniswap

## Notes

- Uniswap is an noncustodial  AMM implemented on the EVM.
- AMMS pools liquidity and use a formula for pricing trades between two assets Uniswap uses y * x = k, a constant product invariant. 

- Uniswap v2's Invariant  is x * y = k, where x is the reserve balance of one currency, and y of the other, k is the constant product value. When a non- liquidity provider uses the pool to convert funds, they will move the constant product value by adding either x or y to the pool while removing the opposite respectively. In this process the constant product value is then change. In Uniswap v2 the process is simple there is a fee that is taken and this sum is taken from the trader prior to the tokens being put into the account, the remaining tokens are added to the pool. Dividing k by the reserve balance of the added currency will now give us the new reserve balance tof the currency being taken out. This is now subtracted from the starting reserve balance of the currency taken out to find the exact amount of tokens being taken out. If users continue trading one side more and more the amount of tokens they would be getting would diminish. (This means that large transfer compared to the balance of pool would be grossly more costly). This in effect causes an arbitrage opportunity correcting the price of the market. 

- Uniswap uses CFMM which are a type of AMM implemented in a smart contract that trades tokens on a permisionless blockchain. 

- Question: Uniswaps paper mentions that Curve and Yieldspace choice of alternative invariants may lead to liquidity fragmentation if lps want to provide liquidity within different ranges? 

- In Uniswap v3 there is now concentrated liquidity, liquidity bounded within some price range.

- Uniswap v3 changes the invaraint model no longer does it rely on the constant product invairant x * y =k. Instead it breaks this up into smaller ranges where the reserve only has to cover the range set. 

- LPs can provide liquidity between any two discrete ticks

- state is tracked by at a pool level, tick level, and position level.

- L = \sqrt(xy) where L equal liquidity of a pool, furthermore \sqrt(P) = \sqrt(y/x) where P is price and x y are reserve balances. 

- unused ticks are tracked in a tick bitmap where uninitialized ticks are set to 0 and initialized are set to 1.

- a LP earns transaction fees in v3 only when the price of the asset is within one of there intervals, if multiple users allocate liquidity to the same price they are rewarded proportionally to their liquidity. 