---
title: "Weather Derivatives"
weight: 1
bookFlatSection: false
bookToc: true
bookHidden: false
bookCollapseSection: false
#bookComments: false
---
# Weather Derivatives

[Artemis Disaster product forum](https://www.artemis.bm/)
- Weather derivatives are financial products use to hedge risk of future weather conditions, typically pointed at a single index: temp (HDD), rainfall, AQI, sunlight per hour, etc.


## Crypto
- Vulcan is the most recent exchange built to provide a market for crypto native weather derivatives.  Using chainlink as an oracle, Vulcan is get real time weather data from NOAA and other sources. At the start Vulcan is starting out in NY focusing on Heating degree days, which is a measure how cold the temperature was on a given day or a period of days from 65 degrees. 

Example of HDD: Suppose a day had a mean temperature of 50 degree then the HDD would be 15 for that day, if the next day was then 60 then over the two day total the HDD would be 20.

- A weather derivative may buy a payoff given a certain HDD over a set amount of days as a way to manage risk of unforseen weather. While Vulcan plans to start with HDD they plan to move forward with rainfail products as well. 


### Arbol
Parametric insurance guarantees a direct payout against some predefined trigger event.  Arbol is a coverage platform allowing business to create custom coverage programs with on-chain weather data. 

This on-chain weather data is now a separate marketplace called DClimate, that provides all the weather data for Arbol through integration with Chainlink's oracle network and neutral weather data providers like NOAA. 

A weather option has the following parameters:
1. Contract type 
2. Contract period
3. Underlying index (HDD or CDD)
4. Official weather station
5. Strike level
6. Tick size
7. Maximum payout

payoff of HDDS and CDDS:

Let the contract go over $n$ days where $\alpha$ is the tick size it follows that the number of HDDS or CDD for the given period is $H_n = \sum_{i=1}^nHDD_i$ and $C_n = \sum_{i = 1}^nCDD_i. Therefore the payout of an uncapped HDD call is equal to $\alpha \max\{ H_n - K, 0\}$ HDD puts and CDD calls are defined the same way. 

Weather swaps, are contracts in which two parties exchange risks during a predetermined period of time. Cash-flows can then be swapped even if at different expirations. 

Insurance contracts have to prove financial loss while a derivaitive is actionable with an event. 
