---
title: 'Intro To Complex Systems [Study Group]'

---

# Intro To Complex Systems [Study Group]
**TE Academy**
**Instr:** ZCStar (Zane Star)
**Date/Time:** 09/16/23/30 August 2022 - 06/13/20/27 Sept 2022
**Repo:** [Intro to Complex Systems w/ Tokens Study Group](https://github.com/TokenEngineeringCommunity/cadCADStudyGroup)
**Book:** [Introduction to the Modeling and Analysis of Complex Systems](https://milneopentextbooks.org/introduction-to-the-modeling-and-analysis-of-complex-systems/)
**Q&A:** [CryptPad](https://cryptpad.fr/code/#/2/code/edit/uzqdh56RpYp8rU6k1Vxdh1tb/)
**Project Board:** [AMM on Excalidraw](https://excalidraw.com/#room=a7ca7c9de135ad67d736,yMJfwsJXYzSt1sThylADOg)
**Other Resources:**
- [3 Blue 1 Brown](https://www.3blue1brown.com) - Vectors and other mathematics
- [Excalidraw](https://excalidraw.com)
- [Uniswap v.1](https://docs.uniswap.org/protocol/V1/introduction)
    - [Working version](https://hackmd.io/@HaydenAdams/HJ9jLsfTz?type=view#DEX-inside-a-Whitepaper)
---

## Session 1

- Overview of program
- [Session recording]()

---

## Session 2

- [Session recording](https://www.youtube.com/watch?v=CoCMnMcxbvA)

---

## Session 3

- Kind of scattered. Discussed Predator/Prey model
- [A predator-prey model to explain cycles in credit-led economies](https://www.researchgate.net/publication/324151988_A_predator-prey_model_to_explain_cycles_in_credit-led_economies)
- [Session recording](https://www.youtube.com/watch?v=Xzhl0vYfWt4)

---

## Session 4

- Pol.is survey discussed [HERE](https://pol.is/report/r5vn9ruryraxnwa9dhmty)
- Discussing arbitrage and modeling
    - Liquidity Pool
    - Competing Price (Exchange)
    - Actors:
        - Community Members
        - Treasury
        - Arbitragers
        - Consumers for Utility
- Predator/Prey is easiest way to discuss zero-sum dynamics
- [Session Recording](https://www.youtube.com/watch?v=pXR_wxMZuq8)

---

## Session 5

V = change in distance x/t

population growth variables:
`initial_population_median_age_of_population`
the following can be variables or constants 
`death_rate`: 5 people/day
`birth_rate`: 2 people/day
`num_of_people`: 100

**Attractor** is the what the phase space converges to depending on the paramters.

**Phase space** axes are determined by the minimum defining model paramters

**Charting a 2-dimensional and 3-dimensional model**
![](https://i.imgur.com/ld1oCvD.jpg)

---

## Session 6

### Recap of Phase Space
- **Phase space** looks at all degrees of freedom for the system without having to perform a deep analysis.
- how is the system performing without having to calculate the varying dynamics

![](https://i.imgur.com/pNFiF7K.png)

### Discrete Time Mdoels
- Discrete time models of dynamical systems are often called **difference equations**
- Discrete because it is only one step back in time


![](https://i.imgur.com/D5nuTTK.png)
- similar to a differential equation

>:memo: Eq.(4.1) can be written as $x$ ~(t+1)~=$F(x$ ~t~ $,t)$

![](https://i.imgur.com/f8Jkzu3.png)
![](https://i.imgur.com/PCE2eoQ.png)

![](https://i.imgur.com/b1mLh3P.png)
![](https://i.imgur.com/UUUw8Je.png)

A = 1
B = -1
F_a = b_t_-1
F_b = 1 - a_t_-1
A_t = F_a(a_t_-1, b_a_-1)
B_t = F_b(a_t_-1, b_t_-1)

x_t
y_t = x_t_-1
z_t = y_t_-1

x_t = y_t_-1 + z_t_-1

### Classification of Model Equations
![](https://i.imgur.com/dRjwmhj.png)
![](https://i.imgur.com/hXbo2Vc.png)

![](https://i.imgur.com/MnzcziE.png)
![](https://i.imgur.com/fwAJ6o0.png)
![](https://i.imgur.com/hb0GcaS.png)

- **keyword:** iterative maps

![](https://i.imgur.com/wGoSMxT.png)
- **note:** nice to put things in a linear form but it is not always possible


### Simulating Discrete-Time Models with One Variable

![](https://i.imgur.com/QbqG4Kz.png)
- **a** is a model paramter
- **initialize** - set base variables
- **observer** - monitor the state
- **update** - define update values
    - defined as a $f$unction
    - when **cadCAD spits out observed data frame is is showing the observed state**

### Moving to templates of the cadCAD study group

[Simple.ipynb](https://github.com/TokenEngineeringCommunity/cadCADStudyGroup/blob/main/templates/python/simple.ipynb) - GitHub
- doesn't work within Python 3.8/3.9

**Code below** - (img)
![](https://i.imgur.com/kEevpQ4.png)
    
    
## Session 7

### Review of state variable and other topics.

![](https://i.imgur.com/qF6rz7w.png)

### Classification of Equations
- 1st Order is only one level deep
- Autonomous systems do not use time
- Non-autonomous does use time
- Non-linear (in example)
    - uses Sin
- Autonomous first-order difference equations are called **first-order maps**

### Going over Code Above
- Initialize
- Observe
    - take all inputs and all outputs so they can be mapped
- Update
    - update, apply to variables as needed
- to start simulation --> initialize()
- plt.plot (x, y)
    - can use a data frame (plotly)
    - each plotting library has its own functions

<br>

> :memo: map function can be used to map list into an array

<br>

### Simulating Discrete-Time Models with One Variable
- using simple.ipynb
- plot is exponential as is, change **r** and the decay rate is different
- >in VSCode check Jupyter variables tab in terminal window

### Discrete Time Model with Multiple-Variables [pg.46]
![](https://i.imgur.com/gazBLCz.png)
- this being the code in the book pgs 46-47


> :memo: go through the examples, problems, in the book and model them.

### Discrete-Time Models
- pg. 52 - Practical Tips for Mathematical Model Building
![](https://i.imgur.com/SZFAgyI.png)

## Session 8

Covered mostly CLDs (causal loop diagrams) - pg 58.

## Session: AMM Model Building
### Reference Text for Formulae
> T= V∗P
> Where ’T’ is the amount of base asset tokens in the vault (strategy LP tokens), ‘Y ’is the total amount of 'Vault' tokens in circulation and P is the 'price' of those vault tokens.
At the start, P=1
>
>Thus, Y=T, the amount of base asset tokens inside the vault is equal to the amount of Vault Tokens.
By keeping track of the number of Vault Tokens in circulation, and the number of tokens inside the vault (which increase the longer they are held in the vault) the price can be calculated as follows:
>
>Price of VaultToken =  (Total Base asset tokens)/ (Total Vault Tokens in circulation)
Since the amount of Vault tokens is constant relative to the amount of underlying base asset tokens (which increase due to them being deployed in strategies, unless the strategies fail), the price will increase and a depositor can burn their Vault Tokens to claim their initial deposit and profits. 
>
>Number of base tokens received = Vault tokens to be burned * Price.  
>
>For example, At time (i) (vault empty, and no Vault tokens minted) : Adam has 1000 USDC tokens and decides to invest them into a USDC/USDT dual sided LP vault.
>
>He will be zapped in and the obtained amount of strategy LP tokens will be deposited into the vault. let’s say he obtained 1000 LP tokens from the ZAP. He will receive 1000 vault tokens as the price of the Vault token will be initialized to 1 with Adam’s deposit. Thus, the Vault is as follows:   1000 LP tokens / 1000 Vault tokens, giving a price of 1. 
>
>At time (ii) (more strategy LP tokens have been generated through harvesting and compounding): The vault now has:   1050 LP tokens/ 1000 Vault Tokens, giving a price of 1.05
>
>Sara adds 1000 USDC (which when Zapped is equal to another 1000 LP tokens) and receives 952.38 vault tokens (because 1000 / 1.05), Thus the vault now has:  2050 LP tokens / 1952.38 Vault tokens, and still a price of 1.05
>
>At time (iii) (more strategy LP tokens have been generated through harvesting and compounding): The vault now has:   2100  LP tokens / 1952.38 Vault tokens, and a new price of 1.0756

>Adam burns 500 of his 1000 vault tokens and is entitled to 537.8 LP tokens back (500 * 1.0756). He can choose to receive the LP token or ZAP out into stable coins. The vault now contains: 1562.2 LP tokens / 1452.38 Vault Tokens, and still a price of 1.0756. 