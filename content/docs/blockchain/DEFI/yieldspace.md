---
title: YieldSpace
weight: 2
bookToc: true
---

# YieldSpace
- fyTokens a synthetic token that is redeemable for a target asset after a fixed maturity date.  
- Price variants by uniswap and other alp are not optimized for fytokens, especially close to maturity.   
- The marginal interest rate of fyDai that is offered by a pool at any time is equal to the ratio of fyDai reserves to the Dai minus 1

- Uniswaps Invariant is x * y = k, where x is the reserve balance of one currency, and y of the other, k is the constant product value. When a non- liquidity provider uses the pool to convert funds, they will move the constant product value by adding either x or y to the pool while removing the opposite respectively. In this process the constant product value is then changed. In Uniswap v2 the process is simple, there is a fee that is taken and this sum is taken from the trader prior to the tokens being put into the account, the remaining tokens are added to the pool. Dividing k by the reserve balance of the added currency will now give us the new reserve balance tof the currency being taken out. This is now subtracted from the starting reserve balance of the currency taken out to find the exact amount of tokens being taken out. If users continue trading one side more and more the amount of tokens they would be getting would diminish. (This means that large transfers compared to the balance of the pool would be grossly more costly). This in effect causes an arbitrage opportunity correcting the price of the market. 

- yield space introduces time into its invariant, with it being x^{1-t} + y^{1-t} = k where 0 \leq t < 1 and t = 1 when the yield dollar is close to the initialization.

- This should be thought of as a pricing formula for yield space, and it has the unique property that its interest rate, r, at any time is r = y/x - 1 where y is a fytoken and x is token

- arbitrage opportunities should only arise when interest rates change? Why does this matter?

- Uniswap / bancor/ Curve / Mstable, are implement different invariants with differing purposes however all lack certain needs of a time sensitive interest bearing tokne like fyToken, that is where the constant power sum formula comes in