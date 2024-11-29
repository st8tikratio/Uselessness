---
title: Module 2 (Token Engineering Process - Discovery Phase)
tags: [TE Notes & Links]

---

---
title: Module 2 (Token Engineering Process - Discovery Phase)
tags: TE Notes & Links
---

# Module 2 (Token Engineering Process: Discovery Phase)

## Introduction to AMMs (Automated Market Makers)
### Key Compenents of an AMM
- Liquidity Pools
    - A liquidity pool holds cryptocurrencies or tokens such as Bitcoin, Ethereum, USDC, etc. In an AMM, users trade with the liquidity pool by sending and receiving tokens.
- Liquidity Providers
    - Liquidity providers are users who put tokens in a liquidity pool on an AMM protocol. In exchange, they receive pool tokens which represent partial ownership of the pool's assets. 
- Traders
    - Traders are users who want to exchange tokens they own for another type of token. They can do this on an AMM through a Liquidity Pool that contains both types of tokens. A trader will send one type of token to a Liquidity Pool, and receive a different type of token from the Pool.
- Arbitrageurs
    - An arbitrageur is a particular type of trader. Arbitrageurs profit from price mismatches across different markets, buy buying a token at a cheaper price on one market and selling it at a higher price on another market.
        - Arbitrageurs play a crucial role in AMMs, since their trades drive token price towards their true market value.

### Four Tokens Found in an AMM
- Risk Assets
    - assets that are traded through the AMM (e.g. ETH, DOT, BTC in any DEX) These are typically assets that originate outside the protocol, which liquidity providers bring in to pools.
- Base Assets
    - type of standard token that a protocol may require in all of its pools. Not all protocols use base assets, but some do.
    - For instance, Bancor is a decentralized exchange with an AMM that uses its own native Bancor Network Token (BNT) token as the base asset. 
        - This makes it so the Liquidity Provider only needs to contribute the risk asset, while also strengthening the value of the BNT token .
    - Uniswap V1 instead used ETH as the base asset for its pools. In the next version of Uniswap, it was possible for pools to contain two ERC20 tokens without using ETH as a base asset.
- Pool Shares
    - Known as pool tokens, LP token, LP shares, etc.
    - These shares are minted (created) to the Liquidity Provider based on the fraction of the total pool assets which the LP has provided. 
    - Pool shares serve as proof of ownership of a portion of the pool. 
    - These shares also represent the amount of the fee revenues for which the LP is eligible. At any point in time, the LP can decide to burn (destroy) their pool shares to withdraw their liquidity from the pool.
- Protocol Tokens
    - Or governance tokens represent voting rights and serve as a democratic instrument in the system. 
    - These tokens provide a governance structure where participants may be involved in decision making about aspects of a cryptoeconomic system.
    - Governance tokens can have an economic value themselves and are often traded on markets, which makes them attractive and further encourages participation in the ecosystem.

### Types of Rewards an AMM Might Offer
- Liquidity Rewards
    - Assigned to LPs for locking up their funds in a pool. The most common type of liquidity rewards are pool fees and interest from staking.
    - The pool shares that an LP owns entitle the LP to a percentage of the pool’s trading fees, proportional to the percentage of shares the LP owns.
    - In addition, some AMMs offer the option for users to stake their funds, earning interest on the tokens provided as time goes on. The idea of staking is similar to a savings account or certificate of deposit in a traditional bank - interest is earned in exchange for keeping funds in the pool for a certain period of time. 
- Protocol (Governance) Tokens
    - Representing governance power and allow liquidity providers to participate in decision making, e.g. by voting on issues related to the protocol.
- Security Rewards
    - Given to those who help maintain security in a network. Many protocols offer monetary rewards for services  such as writing needed code or finding bugs in the system. A “bug bounty” program allows users to report potential security issues, in the hopes hat the resulting money and reputation will sufficiently incentivize people  to report the vulnerability rather than  exploit it for their own profit.

### Risks, Trade-offs, and Costs
- **Explicit Costs**
    - Part of the system
    - *Liquidity Withdrawal Penalties*
        - Liquidity withdrawal penalties are used to discourage people from withdrawing their assets,since such withdrawals negatively impact the system. 
        - While such a penalty discourages exit, it could also create a barrier for entry as a Liquidity Provider may not know when they will need to withdraw their assets.
    - *Swap Fees*
        - A swap fee is charged to an individual trader on each exchange they make in the liquidity pool. This serves as compensation for those who have provided liquidity.
    - *Gas Fees*
        - Gas fees  are the reward given to nodes for validating transactions on the blockchain. 
        - The gas fee can vary considerably, since it is determined by the supply and demand for verifications. A wise trader considers the gas fee before implementing a trade.
- **Implciits Costs**
    - Emerge through market activities
    - *Slippage*
        - The difference between a trader's requested price and the actual price at which the trade is executed. Slippage occurs due to the actual mechanics of AMMs, which we will discuss in detail later.
        - As a trader makes larger trades, they will get fewer tokens out than they might expect.
        - Here are a few important facts to know about slippage:
            1. Traders prefer to have less of it.
            2. Smaller pools will have more of it.
            3. Smaller trades will have less of it. 
    - *Impermanent Loss*
        - Often surprises liquidity providers is known as impermanent loss or divergent loss. 
        - Impermanent loss is the difference between the amount a Liquidity Provider earns  from providing liquidity to a pool, versus to what the value of the same assets would have been if simply kept in their wallet.
    - *Security Risks*
        - Like anything else on the Internet, there exists a possibility that data will be hacked, breached, or compromised. Unlike traditional banks, users of Automatic Market Makers may not be able to receive compensation for funds lost due to security issues. 
        - Although the loss of funds due to a hack typically occurs in one large event rather than on each trade, it is still a potential cost that users need to take into account. 

## Introduction to Discovery Phase
First step in Token Engineering is the Discovery Phase
- Seven steps of the discovery phase
    1. Defining the System Goals
    2. Defining the System Requirements
    3. Stakeholder Definition and Analysis
    4. Definition of Interactions and Value Transfers
    5. Metrics Definition and Analysis
    6. Causal Relationships and Systems Thinking
    7. Identification of Stocks and Flows in the System

## Step 1 - Defininig The System Goals
After the a defined objective has been reached
### Process
- Define specific goals
    - Helps make **objective(s)** concrete and measurable
    - There may be several system goals that are at tension with each other
        - locate the goals in various categories2
    - May not be simultaneously optimizable
- Locate the goals in various categories
    - Leads to recommendations
    - Guides decision makers
    - Allows for observation of parallel activities exisiting in **other** projects or domains and possibly **borrowing ideas** from these systems
    - Examples
        - technical
        - economic
        - etc
- Token engineers must:
    - have strong communication skills
        - be able to clearly define the clients project needs/wants
    - build models that accurately translate ideas to models that are used to build a working system
    - have a clear mental model of component interaction(s)
        - there are a wide range of tools to help build system-level understanding
            - diagrams
            - mathematical formulas
            - etc.
### Design Objective
- crucial first step
- in crptoeconomic systems the objective is to build economic interactions between agents so the system will achieve the objectives of of all participants over its full-life cycle
- Individual projects share key questions but the answers will vary:
    - what does good mean?
    - what is the purpose of the system?
    - what is the economic transaction?
    - who are the agents?
- **the objective has to guide the project in the right direction and make it aligned with the system’s mission or purpose**
- there may be many anaologies to traditional economics
- consider similarities and differences to existing projects to prevent critical failures
    - *it is cheaper to learn from someone else's mistake*

### System Goals
- more concrete than the overall objective which is often abstract
- there may be several system goals that may be at tension with each other
- putting goals into various categories helps understand trade-offs between them
> Cryptoeconomic systems are cyberphysical systems that connect humans and technology
- **two natural categories** are below but many others are possible
    - *technical goals*
        - have to do with an ecosystem’s functionality, interoperability, and technical infrastructure. A cryptoeconomic system will have limitations based on both hardware or software components, including things like computing precision in different coding languages, as well as the physical restrictions of memory on various storage devices. Here the main target is to guarantee that the technical infrastructure of the system can support the mission over the full life cycle of its components. Sometimes these issues will be of a very technical nature, requiring a high degree of intensive troubleshooting.
            - **For example**, working on Ethereum, we have limited storage space for single variables. In Ethereum, numbers can be stored as uint256, that is, positive integer numbers up to 2256−1. If the system we are building overshoots this limit, it can cause serious problems. Engineering will work to avoid or mitigate this issue.
    - *economic goals*
        - Related to the financial aspects of the system. A **system has to be affordable in its operation** compared to market alternatives (cf. costs of cash payments vs digital transactions),. The system it has to be economically appealing to all its participants.
        - First, it is a good idea to look at **what economic incentives and foundations will attract what participants**. As the same parameters and its properties will affect different participants differently, a balance has to be found for where the accumulated utility is the highest (which imposes the questions **what is aggregated utility and who gets to decide this?** This is related to the idea of *Economic theory on social choice*).
            - **For instance**, in an automated market maker, we would want to have a stable trading fee which will engage liquidity providers while not scaring off traders. Liquidity providers might even see lower trading fees as an advantage, since a larger trading volume will generate more returns.
        - Second, the **business economics of the system need to be calculated in order to see how much it costs to operate the system**. Each interaction on the blockchain incurs gas fees, since calculations have to be performed and smart contracts have to be executed. A state update that requires more sophisticated calculations will be more costly. It is possible for a small token swap to be extremely costly  due to multiple complicated calculations that are required to change the conditions in the pool and the agents’ holdings. In other words, each line of code is expensive. These costs have to be reasonable, as they are born by the agents.
        - **Stability** is another economic goal
            - systems reacting strongly to marker conditions and shocks become unusable over time.
                - there should be **control policicies** to compensate for this
- A firm understanding of the **system goals**, the business requirements, and the technical restrictions allows to optimize for different parameters in the design phase and in the deployment phase.
- When setting goals we must determine how and when the goals are met.
    - **KPIs** are common and are numerical values that allow us to measure if goals are tracking with the system design
- Clearly **defined and continuously monitored goals** reduce the risk of major deviation from system intent
> Economic and technical goals that we define at the project’s outset will guide and inform all decisions regarding design, policy, and governance of the system
- **Goals can change over time** that may be due to factrs below requiring the system to have a well-designed **governance policy**
    - market forces
    - regulation
    - objectives no longer align with the systems original intent

### How to Determinine System Goals
**Under**


## Links
- [Balancer Hacked Through Known Exploit](https://cointelegraph.com/news/defi-protocol-balancer-hacked-through-exploit-it-seemingly-knew-about)