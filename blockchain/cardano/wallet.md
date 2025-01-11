# Cardano Wallet Info
###### From C.H. video on 10 Jan 2025

### "States of Maturity"
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

### Cardano Test Suite
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
      - No Node
- Certifying node options are within the `Validate Your Full-Client`
  - Certified against the Test Suite

### Discussions
- W/ ***TxPipe*** representing Pragma
  - discussed creating a working group between Intersect and Pragma to discuss `what a test suite could entail?`
