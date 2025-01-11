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













@@ Queestions:
- Midnight:
  - do SPOs run Midnight alongside infra or separate nodes?
    - built-into Cardano code base? 
  - does Midnight have a separate Tx fee?
    - where does this fee go?
- Certification:
  - who determines certification criteria?
  - what makes them the certifying authority?
  - should this be voted on? 

















