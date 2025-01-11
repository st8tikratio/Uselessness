# Cardano Wallet Info
###### From C.H. video on 10 Jan 2025 - [source](https://x.com/IOHK_Charles/status/1877887901956292760)
###### Note: Full-client v. full-node are different systems

### "States of Maturity"

#### Current Wallet Builders (mentioned)
- Blinklabs - Go based walelt
- TxPipe - RUST based wallet
- Harmonic - Typescipt
- Reference - Haskell

```
Full Node -> IPC -> Cardano Wallet -> Wallet UI
                                   ^
      json RPC, Rest, GraphQL    _/ 
```
- IPC uses Ouroborous Mini Protocols (exotic & "what Cardano is known for")

---

### Become More Like Ethereum

- Cardano become more like Ethereum with wallet testing protocols
  - See their [Tests](https://github.com/ethereum/tests) repo
  - Regardless of backend the dev can insure the client works as intended 

#### Cardano Test Suite

- Test Suite should include Blueprints
  - Blueprints = Formal Specs (incomplete ATM)
- Some combination allows dev to validate full-client
- If a user wants to run a full-node
  - instead of downloading Daedelus
  - they would download their favorite wallet and **_`CHOOSE`_** the backend
    - can be remote and connect to the backend of a wallet provider
      - this can run on BlockFrost, Maestro, etc. etc.
    - self-hosted via a menu of options that are all certified against a standard
      - Haskell node
      - Go Node
      - etc.
- Certifying node options are within the `Validate Your Full-Client`
  - Certified against the Test Suite

---

### Discussions

- w/ ***TxPipe*** representing Pragma
  - discussed creating a working group between Intersect and Pragma to discuss `what a test suite could entail?`
  - any of the `full-node wallet builders` are welcome to participate
- the idea is to reach consensus on a Certification Concept
  - people can then `self-certify` (like "we" did)
    - `WE` refers to [Intersect, IOHK ??) wallet, `Mantis` being certified on Ethereum

---

### Idea

- any wallet user can deccide if they want to run a remote-node or self-host
- the wallet would then download chosen option accordingly

---

### Things That Must Be Improved

- Already:
  - parallel workstream -> Mithril FastSync
  - network contribution -> exists on Peer-to-Peer (P2P) side
    - relay Tx + Blocks <- `if not doing the validation`
    - whole specification on how this works
    - could be `more sophisticated things` contributed
- Data-Difusion-Layer on Cardano is above and beyond what `just the ptotocols have`
  - currently being handled in a fragmented and ad-hoc way 
- Hardware Wallet MultiSig
  - not directly stated as "improvement"
  - ridiculously hard to compromise 3/5 or 5/7 multisig wallets
    - C.H. does not beleive it has ever been done without social-engineering
     
---

### Clients & Nodes

- Full-Clients
  - provide service modules:
    - `Hydra`
    - `Proof-Server` - provides trusted execution environment
    - etc.
    - etc.
- ***`Super-Nodes`***
  - run Cardano infra + partner chain networks + other L1 chains
 
---

### Tie-in ???
- NVidia [Digits](https://www.nvidia.com/en-us/project-digits/) - ITX sized AI super-computer
  - super good at doing `Zero Knowledge Proofs (ZKPs)` with code-optimization
    - Midnight will provide the Cardano Proof Layer
  - install a full-node and self-host by running:
    - remotely through backend or app
    - locally
  - leave it running to run in a completely trustless environment 
- Iagon Pre-built Cyclone QS [Full Node](https://cyclone.iagon.com/) - Data-storage node
  - **Pro** version can be run as full-node and as `full-wallet`

---

### Goal
- People in Cardano should ***`host their own infrastructure`***
- User should decide:
  - what backend they want to run
  - what hardware they want to run for that backend
  - what services they want the hardware to provide
- Making it simple so it becomes part of your stack
- Stop using remotes servers so client is completely in control of ***`entire world`***
- Believes there is a path to "do this now that we have Intersect and Pragma in this working group"
  - certification `can be discussed` between ***`the two sides`***
- Mithril Standard must be dragged int othe Full-Node World
  - interfaces discussed
  - discussions of cryptography
  - standardize how various modules plugin
  - inter-wallet interoperability

---

### Future

#### Daedelus Wallet

- 6-9 months Daedelus will be depricated from the I/O perspective
  - will be transferred over to a ***`community-led open-source project`***

#### Lace Wallet

- I/O will work on the Lace-side building an open-standard for `how one connects a node to wallets`
  - **`try to`** work with Vespir, Eternl and other people in Cardano ecosystem and see if they will `extend` as well
- **`Dream is`** to make it really simple to download a full Mithril node and run it in their system-tray (background process) `like BitTorrent`
  - at the very least it would provide network resources
  - over time, make it easy for people to build in modules/extension to full-node for:
    - indexing
    - running Hydra
    - or whatever they so choose
- the above will be on the ***`Lace Roadmap for 2025`***
- taking an ecosystem-wide standards-driven approach
  - once solve for Lace ***`it is solved for everybody`***
  - creates a practical path to a:
    ```
    multi-node World
    ```
- will have a desktop mode that will superior to Daedelus full-node experience
- Full sync with same security features (***`"relatively speaking"`***):
  - Mithril Desktop Node - benchmarked at under an hour
  - Daedelus Full Node - takes about 3 days give or take- WTF???, 3 days?
- Dedicated team in Argentina to setup Mobile-Clients for Android and iOS
  - centralize and incentivize
- dApp store still on roadmap
- ***WILL ALWAYS LIVE IN THE BROWSER*** and needs to be on edge-devices also

#### Example Modules
- Wallet scripts - allows user to, similar to a bash/shell script, against a wallet
  - Can chain a bunch of Tx together [sounds like GCScript]
  - Ex: payroll script - hundreds of Tx at the same time

#### About Standards (near direct quote)
- It makes absolutely no sense to solve [the issues within this doc] for Lace. It makes sense to make standards for use across the ecosystem so that other wallet providers can benefit from it and not spend a lot of money or effort. Suddenly they can offer their user-base a self-host opportunity. Users should not have to migrate to get better security or something. You should have the ability to do that. Our goal is to make sure everyone is using the experience everyone likes. [Uses Nami as example feature set people enjoyed and was introduced into Lace. Nami code is very Beta. Migration ongoing.] 

#### dApp Store
- final and pivotal component of ***`Bitcoin DeFi`*** experience
  - massive competitive differentiator
  - a component theme of "all of these"

---
     
### Budgeting Process
- when alternative nodes get funding (??) part of the funding can be funding for certification against the standard
- people in Cardano have become accustom to formal methods, peer review and high-quality, high-assurance software <- we should never lose that
  - understand this is not FREE
- when alternative nodes are constructed, to ensure they have an equivalent level of quality over what the haskell node has been providing
  - user gets to decide which ONE makes more sense

---

### Questions & Observations
```
- Midnight:
  - do SPOs run Midnight alongside infra or separate nodes?
    - built-into Cardano code base? 
  - does Midnight have a separate Tx fee?
    - where does this fee go?
- Certification:
  - who determines certification criteria?
  - what makes them the certifying authority?
  - should this be voted on?
- Two Sides:
  - referring to IMBO and Pragma, IMBO and community builders, ...? Who?
- Centralization
  - concerning if IMBO or Triad are THE certifying authorities
- DREQ or DREC? What is it?
---

Typescript allows more features to be brought into the browser

```
















