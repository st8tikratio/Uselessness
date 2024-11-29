---
title: Notes & Links from TE Fundamentals Course

---

# Notes & Links from TE Fundamentals Course

# [Towards a Practice of Token Engineering - Methodology, Patterns & Tools. TE Series Part II](https://blog.oceanprotocol.com/towards-a-practice-of-token-engineering-b02feeeff7ca)

>:memo: [Video Discussion of Article](https://www.youtube.com/watch?v=Zf-WlBl1dAA&feature=youtu.be&t=3152)

### Token Design Patterns : A Starting Point
Every mature engineering field has its corpus of building blocks .We have books for design patterns in architecture, software, analog circuits and, yes, optimizers. But, no one’s written the book on token design patterns, yet.

However, building blocks are starting to emerge. Some have seen popularity explode quickly (e.g. TCRs). The paragraphs below explore these blocks. Sometimes they form core token mechanics; sometimes they get bolted in to solve particular problems. This list is just a starting point.

### Curation
Binary membership: Token Curated Registry (TCR), e.g. to maintain a list of good actors. A sub-block of TCRs is risk-staking to reduce onboarding friction. Discrete-valued membership: Stake Machines, e.g. for promoting an actor. Continuous-valued membership: Curation Markets (CM) for popularity of an asset, defined by its bonding curve with design guidelines here. Hierarchical membership: each label gets a TCR (like here). Work tied to membership: Curated Proofs Market Market (CPM). Curation on non-fungible tokens: Re-Fungible Tokens (RFT).
1. [Token Curation Registry](https://medium.com/@ilovebagels/token-curated-registries-1-0-61a232f8dac7)
2. [Ocean Protocol Whitepaper](https://github.com/oceanprotocol/whitepaper/raw/master/whitepaper.pdf)
3. [Curated Governance Stake Machines](https://medium.com/@DimitriDeJonghe/curated-governance-with-stake-machines-8ae290a709b4)
4. [Introducing Curation Markets: Trade Popularity of Memes & Information (with code)!](https://medium.com/@simondlr/introducing-curation-markets-trade-popularity-of-memes-information-with-code-70bf6fed9881)
5. [Simple Rationality For Bonding Curves](https://hackernoon.com/the-simple-rationality-of-token-bonding-curves)
6. [Re-Fungible Token: RFT](https://medium.com/@billyrennekamp/re-fungible-token-rft-297003592769)

### Identity
Lower level: public key, decentralized identifiers (DIDs). 

Medium level: TCR.

Higher level: e.g. uPort, Civic, Sovrin, Authenteq, Taqanu, Estonia E-Residency. Identity of machines: e.g. Spherity

 1. [DIDs](https://w3c-ccg.github.io/did-spec)
 2. [uPort](https://www.uport.me/)
 3. [Civic](https://www.civic.com/)
 4. [Sovrin](https://sovrin.org/)
 5. [Authenteq](https://authenteq.com/)
 6. [Taganu](https://www.taqanu.com/)
 7. [Estonia E-Residency](https://e-resident.gov.ee/)
 8. [Spherity](http://spherity.com/)

### Reputation. 
Reputation systems are at the intersection of curation and identity.

### Governance / software updates. 
This can be a mix of ZeppelinOS, Aragon, Colony, and more. Maybe eventually automated?
1. [Zepplin OS](https://zeppelinos.org/)
2. [Aragon](https://aragon.one/)
3. [Colony](https://colony.io/)
4. [Deep Dreams of Global Machines](https://medium.com/@miles2045/deep-dreams-of-gödel-machines-16c85cf9697f)

### Third-party arbitration. E.g. Mattereum.
1. [Mattereum](https://mattereum.com/)

### Proofs of human or compute “work”
For data, compute, and more. This the evaluation of the objective function. It can be can human work like in Steemit or Augur, or machine work like in most other systems. Machine work may be solving an (arguably) less-useful puzzle like in Bitcoin, or more “useful” work like FileCoin’s Proof of Space-Time. Here’s a breakdown of useful work (“service integrity”) grouped by data and computation (from here).
1. [Steemit's Breakthrough: Subjective Proof of Work](https://steemit.com/steemit/@alwillis/steemit-s-breakthrough-subjective-proof-of-work)
2. [Augur](http://www.augur.net/)
3. [Filecoin's Proof of Space & Time](https://filecoin.io/filecoin.pdf)
4. [Collection of Useful Work](http://www.oceanprotocol.com/#papers)

![](https://i.imgur.com/6QGB2F5.png)

## Other ways to frame or group building blocks include:

### Distribution:
This includes releasing coins for “work”, according to a controlled supply schedule; 100% pre-mining; burn-and-mint; bounty ICOs; and more.

1. [Controlled Supply](https://en.bitcoin.it/wiki/Controlled_supply)
2. [Burn and Mint](https://medium.com/@kylesamani/new-models-for-utility-tokens-d26c12ec00c5)
3. [Bounty ICOs](https://medium.com/@jjmstark/bounty-icos-61232e73370b)

### ETH Token Standards
1. [ERC-20 Fungible Tokens](https://github.com/ethereum/eips/issues/20)
2. [ERC-721 Non-fungible Tokens](https://github.com/ethereum/eips/issues/721)
3. [Token Lexicon](https://medium.com/@billyrennekamp/token-lexicon-b4ed9a4ce363)

### Valuing Tokens
As a means of exchange, store of value, and unit of account

`Book` - Cryptoassets: The Innovative Investor's Guide to Bitcoin and Beyond

### Gatekeepers
For gatekeeping, arbitrage, or resource transaction
1. [Keepers — Workers that Maintain Blockchain Networks](https://rzurrer.medium.com/keepers-workers-that-maintain-blockchain-networks-a40182615b66)

### How The Compute Stack Is Organized
1. [The dApp Developer Stack: The Blockchain Industry Barometer](https://medium.com/@FEhrsam/the-dapp-developer-stack-the-blockchain-industry-barometer-8d55ec1c7d4)
2. [Blockchain Infrastructure Landscape: A First Principles Framing -- Manifesting Storage, Computation, and Communications](https://medium.com/@trentmc0/blockchain-infrastructure-landscape-a-first-principles-framing-92cc5549bafe)
3. [Won't Load](https://blog.oceanprotocol.com/towards-a-practice-of-token-engineering-b02feeeff7ca)

### Level-1, level-2, level-N infrastructure
The core chain is level 1. The higher levels are to help scale without having to reconcile the main chain on every transaction
1. [Making Sense of Ethereum’s Layer 2 Scaling Solutions: State Channels, Plasma, and Truebit](https://medium.com/l4-media/making-sense-of-ethereums-layer-2-scaling-solutions-state-channels-plasma-and-truebit-22cb40dcc2f4)

### Cryptographic Primitives
Another label for token design patterns or building blocks.
1. [The Emergence of Cryptoeconomic Primitives](https://blog.coinbase.com/the-emergence-of-cryptoeconomic-primitives-14ef3300cc10)

## Tools We Need to Design

### Tools to simulate tokenized ecosystems. 
Simulators measure performance metrics of a given design. One starting point is the agent-based modeling that’s coming out of the fields of complexity science and artificial general intelligence. Another is the simulators for networks already used for consensus algorithm design. Another is modeling as a set of differential equations (DEs), then solving with a DE solver like SPICE.
1. [Introduction to Agent Based Modeling](https://www.santafe.edu/engage/learn/courses/introduction-agent-based-modeling)
2. [Artificial General Intelligence](https://opencog.org/)
3. [SPICE - wikipedia](https://en.wikipedia.org/wiki/SPICE)

### Tools to verify tokenized ecosystems
These verify that a design can work (according to its performance metrics) despite uncontrollable variables that impact performance. An uncontrollable variable follows (a) a range where the design must perform well at any of the variable’s values, or (b) a probability distribution where the design must perform well in >x% of scenarios. These are “worst-case performance” and “n-sigma performance” respectively. “n-sigma” is a unit to express failure rate, just like “% work” or “% fail”; typically designs aim for 2-sigma (works 95% of the time), 3-sigma (works 99.7% of the time), or 6 sigma (fails about 1 in a billion times).

### Tools for design space exploration
These help the designer explore the design space, i.e. give insight into what happens to worst-case/n-sigma performance when controllable variables get changed.

## Limitations of Tools
One option is to not try modeling black swans, but simply minimize potential negative impacts if they do occur.
- `book` The Black Swan: Second Edition: The Impact of the Highly Improbable: With a new section: "On Robustness and Fragility" 

Or, we could have humans in the loop as part of the “simulator” where they are incentivized to come up with attacks. This formalizes an existing practice: people doing token design get their friends to dream up new attacks, then they update the constraints list then the design accordingly. I’ve found myself in dozens of such conversations.

We should ensure that the system itself is evolvable, towards the intent of the community. The tools for this are governance, staking, and more. Governance may be as simple as hard forks, for example to change the objective function or add constraints. Staking helps convert zero sum to positive sum for the community of token holders.

## Intrinsic v. Extrinsic Motivation
Extrensic motivation can be dangerous in some places. Let’s say you’re building a decentralized reputation system. Directly tokenizing reputation would incentivize people to game their reputation for money, leading to all sorts of poor behavior.

One possible answer is for the system to support intrinsic motivation rather than extrinsic. In the classroom, this means tactics like: provide choices, minimize pressure, allow alternative solutions, encourage originality, and promote success. Some of these might translate to token design. One example is to simply filter out the bad actors with economic stake, e.g. with a TCR. Or, we could promote success via stake machines.

1. [Intrinsic v. Extrnsic Motivation](https://healthcare.utah.edu/wellness/pdfs/intrinsic-motivation.pdf)
2. [Intrinsic and extrinsic motivation from a self-determination theory perspective: Definitions, theory, practices, and future directions](https://hackmd.io/Se-kVUvRSEuYWsidJnbH3g)


---

# [Token Engineering Case Studies - Analysis of Bitcoin, Design of Ocean Protocol. TE Series Part III](https://blog.oceanprotocol.com/token-engineering-case-studies-b44267e68f4)

>:memo:[Video Discussion of Article](https://www.youtube.com/watch?v=Sm8j0u5NuGQ)

## Analysis of Bitcoin
Its objective function is: maximize the security of its network.

###  The formula for the objective function

On the left side is the amount of token rewards R in a block interval that actor i can expect. The right side of the equation is proportional (α) to the left, and is the product of compute power (hash rate) of actor i and number of tokens dispensed every block T. The latter value is currently 12.5 BTC every ten minutes. Every four years that value halves.

![](https://i.imgur.com/UBQYXah.png)

<br>

1. [Orchid Protocol Whitepaper](https://orchidprotocol.com/whitepaper.pdf)

## Case Study of Ocean Protocol

### Define the possible stakeholders or system agents
The following table outlines the key ones for Ocean token dynamics.

![](https://i.imgur.com/TklrsDd.png)

### Objective Function
Objective function. After the iterations described above, we arrived at an objective function of: maximize the supply of relevant AI data & services.

### Constraints
In the iterations described above, used this checklist when considering various designs. Roughly speaking, we can think of these as constraints.
- For priced data, is there incentive for supplying more? Referring? Good spam prevention?
- For commons (free) data, is there incentive for supplying more? Referring? Good spam prevention?
- Does the token give higher marginal value to users of the network versus external investors?

We continually polled others about possible attacks; added each new concern to the list of constraints to solve for (including a memorable name); and updated the design to handle it. 

---

# Other Links

1. [Optimization Videos](https://www.youtube.com/watch?v=Sm8j0u5NuGQ)
2. [Complex System Videos](https://medium.com/abq-blockchain-community/talking-blockchain-ai-complex-systems-3c5a33676f85)
3. [Algorithmic Game Theory - Full Course](http://timroughgarden.org/f13/f13.html))

