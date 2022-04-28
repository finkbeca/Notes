---
title: Stablecoins
weight: 2
bookToc: true
---

# Stablecoins

## CPI StableCoins

- CPI measure the price chance across a wide section of the economy in an attempt to accurately measure inflation. The purchasing power of the dollar declined by 7.5% from January 2021 to 2022. pegging a stablecoin’s value to CPI, will allow purchasing power to stay the same, thus one VOLT will go from $1 to $1.075 over 1 year under current CPI.
- Volt will use a Chainlink Oracle to obtain official CPI data.  
- Frax will use this same oracle.  
- What does a crypto native CPI standard look like?  
- What is a Peg Stability Module    
    - Allows a user to a swap a gien collateral type for a stablecoin at a fixed rate. This allows for users to swap other stablecoins for DAI at a fixed rate to aid with keeping DAI pegged to a dollar.  
    - USDC packed PSM ( a user would be able to swap 100 USDC for 100 DAI (minus fees) using the USDC backed PSM.  
    - Goal of a PSM is to keep DAI pegged close to usd when DAI demand outstrips DAI supply.  
    - PSM has increases risk as the stablecoin in a PSM are effectively owned by the Maker protocol, and may be centralized, there is the same inherent risk that the stable coin in the reserve will lose its peg.  
    - Benefits:    
        - Increased DAI stability, due to instant arbitrage.  
        - Fees are taken upfront on each swap  
        - There is no requirement to micromanage parameters.  
    - PSM cannot be interacted with if its debt ceiling is reached.  
    - PSM only makes sense being used with an asset of the same value.   
    - Maker PSM vs Curve?  
    - G-Uni allows Maker to earn stabilitiy fees on the dormant USDC sitting in the PSM, which goes towards burning MKR., G-UNI allows a fungible wrapping of a Uni V3 position between DAI and USDC to then be used to get exposure to UniV3  
    - PSM Module [https://forum.makerdao.com/t/mip29-peg-stability-module/5071](https://forum.makerdao.com/t/mip29-peg-stability-module/5071)  
    - https://github.com/makerdao/market-maker-keeper  
- How do they translate?  
- Problems with Volx?  



Proof of Replication

- How does this work?
- How is it different in Solana versus IPFS

Time Differences between Eth / Solana / L2