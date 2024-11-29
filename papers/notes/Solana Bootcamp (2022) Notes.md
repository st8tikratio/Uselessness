---
title: Solana Bootcamp (2022) Notes
tags: [solana]

---

---
title: Solana Bootcamp (2022) Notes
tags: solana
---

# Solana Bootcamp (2022) Notes

## Intro to Solana
### Links
- [Video]((https://youtu.be/O0uhZEfVPt8))
- [Install Solana Tool Suite](https://docs.solana.com/cli/install-solana-cli-tools)
- [Solana Mint Account Demo]()
### The goal of Solana programming
- take user input
- modify onchain state
### Basic Architecture of Interaction
1. Client program
    - web app or CLI
    - **makes request to JSON RPC**
    - language agnostic
        - C++, Rust, etc.
2. JSON RPC
    - **routes request** to some program onchain
    - done through transactions (Tx)
    - **Endpoints**
        - gets information from the blockchain
        - most useful command is
            - [getAccountInfo](https://docs.solana.com/developing/clients/jsonrpc-api#getaccountinfo)
                - pass in input and receive data back to the **client side**
            
>*Onchain starts here - steps 3 & 4*

3. Solana program
    - **writes to accounts** (or objects)
    - modifies the state of some account
4. Accounts
    - can **request data from JSON RPC**

### Keys
- **Public key (pubkey)**
    - 32 byte string
    - letters & numbers
    - **account address**
        - similar to file name
    - **half** of a **key pair**
    - used to access **data buffers**
- **Key pair**
    - 64 byte object
    - organized as
        - first 32 bytes are **private** or secret **key**
            - **SK**
        - last 32 bytes are public key
            - **PK**
    - SK maps uniquely to PK
        - SK --> PK
    - hash is the signature on some message with the secret key
        - hash = sig (msg, SK)
        - **verify** can be called on the **hash** and returns true only if the keys match
            - verify (hash, PK) = True if SK signs
    - usings keypairs allows **ownership**

:memo: When working in Rust the most common interaction is with the **AccountInfo** object

### Account
- Owner - PK
    - represents the program that has write access to the account
- Data - byte array
    - raw bytes the aaccount contains
    - contains all of the content of the account
    - adding data requires Lamports
- Lamports
    - smallest denomination of SOL
    - 8-byte integer
        - U64
    - 1 billion Lamports / 1 SOL
- Executable Flag
    - Boolean (bool)
    - Determines whether the account **is a program or not**
        - Is this a program?

:memo: Everything on Solana is represented as an account. Programs are a special kind of account with an executable file and executable flag is set to **True**. For accounts that are purely data the owner of those accounts will be set to the ProgramID (= PubKey or PK).

- Rent
    - data requires Lamports
    - paying for space with SOL