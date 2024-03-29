---
title: "Economics"
weight: 1
bookFlatSection: false
bookToc: true
bookHidden: false
bookCollapseSection: false
#bookComments: false
---
# Economics

## Links 
[Cryptoeconomics](https://www.youtube.com/watch?v=GQR1xjQn5Pg)  
[Tokenizing Shares](https://medium.com/coinmonks/tokenising-shares-introducing-erc-884-cc491258e413) ERC-884  
[Time Locked Tokens](https://ethresear.ch/t/time-locked-1-1-tokens-as-rudimentary-pseudo-futures/7958)  
[ETh-Options Hegic](https://www.hegic.co/)  
[Options Basics](https://hegic.gitbook.io/start/)  
[London Mathematical Laboratory](http://lml.org.uk/)  
[Eli Blog](https://eli.thegreenplace.net/)  

### Blogs
[TheMoneyIllusion](https://www.themoneyillusion.com/)  
[Enlightenmenteconomics](http://www.enlightenmenteconomics.com/blog/)  
[Greg Mankiw](https://gregmankiw.blogspot.com/)  
[Conversable Economist](https://conversableeconomist.blogspot.com/)  
[Macro Musings](https://macromusings.libsyn.com/)    

***
</br>

## Mechanism Design
[Basics](https://en.wikipedia.org/wiki/Mechanism_design#:~:text=Mechanism%20design%20is%20a%20fieldsettings%2C%20where%20players%20act%20rationally.)  

## Game Theory
 [Game Theory: An introduction](https://smile.amazon.com/Game-Theory-Introduction-Steven-Tadelis/dp/0691129088)  
 [The Art of Strategy](https://smile.amazon.com/Art-Strategy-Theorists-Success-Business/dp/0393337170/ref=pd_bxgy_img_2/131-7856020-5987520?_encoding=UTF8&pd_rd_i=0393337170&pd_rd_r=e0a39eec-b63d-4086-a979-53ebe7910cf5&pd_rd_w=tA4zq&pd_rd_wg=5ebay&pf_rd_p=fd3ebcd0-c1a2-44cf-aba2-bbf4810b3732&pf_rd_r=0E9YZATXX4F3ZB0FEWH7&psc=1&refRID=0E9YZATXX4F3ZB0FEWH7)
 [Theory of Games and Economic Behavior](https://smile.amazon.com/Theory-Games-Economic-Behavior-Commemorative/dp/1777257301/ref=pd_bxgy_img_3/131-7856020-5987520?_encoding=UTF8&pd_rd_i=1777257301&pd_rd_r=e0a39eec-b63d-4086-a979-53ebe7910cf5&pd_rd_w=tA4zq&pd_rd_wg=5ebay&pf_rd_p=fd3ebcd0-c1a2-44cf-aba2-bbf4810b3732&pf_rd_r=0E9YZATXX4F3ZB0FEWH7&psc=1&refRID=0E9YZATXX4F3ZB0FEWH7)
 [Decision Theory](https://smile.amazon.com/Introduction-Decision-Cambridge-Introductions-Philosophy/dp/0521716543/ref=sr_1_5?dchild=1&keywords=decision+theory&qid=1621385020&s=books&sr=1-5)

## Notes

- Signaling Equilibrium
- Two Factor Markets (ce. Craiglist buyers rely on sellers ; sellers rely on buyers)
- Nash Equilibrium is the change of state when everyone make their best moves from the previous nash equilibrium
- Pareto Optimum a state where it is impossible to make any change where one agent is better without making any other agents worse off
- Coordination Problem (Everyone would be better off to switch but if one person goes it is useless)
-Asymmetric information (Information where there is not validity to truth [asking if a car is a lemon; you can't trust the response even if they say no])
- Inferior Equilibrium (No one player acting poorly but the system as a whole)
- Signaling Equilibrium (A two factor market where 1 point is stabilized by two separate factors [Ivy Schools because students want to go there for high paying jobs Ivy Schools because employers know only the smart people go there])
- Regulatory Capture of occupational licensing 
- Gell-mann Amnesia Effects

### Swaps
- Simply put two parties payment streams. If one party had a bond that pays a coupon of 5% and party pays a floating rate, then the two parties can enter into a swap agreement and swap their interest streams. 
- In traditional finance swaps are denoted by there notional value. 
- Interest rate swaps come in two notes, basis swaps where two floating rates are switched  (think 6 month / 12 month)
- Sometimes swaps currently also simply exchange the currency
-LIBOR is an unsecured rate, the rate that many international banks can borrow unsecured funds with each other without collateral. This rate is agreed upon daily.  Libor is commonly used as a benchmark for swap interest rates. 
- Swaps have no market, but instead like bonds are agreed upon over the party with an agreed upon party. 
- The swap rate yield curve is used to benchmark rates of exchange.


### Options, Futures, Derivatives,

In tradfi a clearing house takes care of the credit risk by requiring each of the traders to deposit funds (margin) when acting on an future or option trade.   

A forward contract is an agreement to buy or sell an asset at a certain fixed time in the future for a specific strike price.  
One party assumes a long positions and agrees to buy the underlying asset, at a certan date and price, the other party assumes a short position agreeing to sell the asset at a fixed time and price.

payoff for a long position in a forward contract is Spot price (S_k) - k where k is the strike price  

payoff for a short position in a forward contract is k - s_k  

Forward contracts are typically OTC products

Future contracts are similiar to forward contracts but take place on an exchange. 

A call option gives the holder a right to buy an underlying at a certain price for a certain, while a put option gives the holder the right to sell the underlying at a certain price and date. This is a right not a forced action.  

Generally an option is worth more than its payoff up until a few moments before its expiration. 

There is a product called the perpetual American option that has no expiration date but with this it is incredibly expensive and very difficult to price as they face a lot of uncertainty. Because of this it is not typically traded. 

Due to many different expiration dates, there arises a liquidity fragmentation problem where market makers have to spread out there capital over these different dates, this leads to a complex system with different expirations having differing degrees of liquidity. 


