---
title: Back to Basics - TE Fundamentals

---

# Back to Basics - TE Fundamentals

**Hosts:** Stella, Mark, Rohan
**Start Date:** 10 Aug 2022, Wednesday
[Notion](https://te-academy.notion.site/Back-to-Basics-bdbe95d4042a4017b41bef624590f0fe)
[Discord Channel](https://discord.com/channels/1016433241978314913/1016433242993328134)
[Voice Channel](https://discord.com/channels/1016433241978314913/1017779144530083900)

## Day 1 - Bitcoin
Bridge course for TE Fundamentals course
Covering the Bitcoin Whitepaper abstract
- stops double spending
- decentralized public timestamped ledger
- 1 CPU - 1 vote
- Bad actors
    - selfish mining
    - collusion

Digital signatures provide part of the solution

Each person has
- public key
- private key

Double spend first successfully prevented
- David Shaum - Central server that tracks the balances

Ledger entry is
- hash
- timestamp
- trasaction

Block mints every 10 minutes
Longest chain wins - canonical truth

51% Attack
- based on hash power of network not node count
- producing a longer chain than the canonical chain
- 193.22 hexahashes (current hash power)

3 families of consensus algrotithms
- classical consensus algrotihms
    - leader election - no PoW or PoS
    - limitations
    - deterministic
- nakimoto consensus
    - can have global scale
    - throughput is limited
    - sybil protection method
        - proof of work (don't need to know anything)
- hybrid consensus
    - uses randomization to acheive scale
        - Radix
        - Avalanche
    - proof of work and proof of stake are the sybil mechnisms

Bitcoin incentivizes its own protection in expending energy in the form of computational power
- compare the US Dollar as protected by the US military
    - requires a lot of energy

Read [Can Blockchains Go Rogue](https://blog.oceanprotocol.com/can-blockchains-go-rogue-5134300ce790)

Bitcoin consensus mechanism is in the computer code
- there is a social consensus also
    - nodes can choose whether or not to run code

Consensus is a tradeoff
- what services you want to provide
- **Do you really need decentralization for a gaming app?**

One single proof of work network
- Bitcoin can be the security model and every chain taps into Bitcoin every so often.

## Day 2 Notes - Bitcoin

>showed up late (approx. 40 mins late)

**Network**

- The steps in the network are as follows:
    - new Tx are broadcast to all nodes
    - each noide collects new Tx into block
    - each node works on finding the difficult PoW for its block
    - when a node finds a PoW it broadcast the bloclk to all nodes
    - nodes accept the block only if all Tx in it are valid and do not already exist
    - nodes express their acceptance of the block b y working on creating the new block in the chain using the hash of the accepted block as the previous hash
- The longest chain always wins
- Bitcoin core are
    - bitcoin.sipa.de
    - dnsseed.bluemalt.me
    - ...

**Incentives**

- the first Tx in a block starts a new coin owned by the creator of the block
    - cna be spent after 100 blocks
    - adds an incentive for nodes to support the network
- can also be funded by the transaction fees
    - if output is less than input the difference is a Tx fee that is added to the incentive value of the block contrinaing the the Tx


>What happens when all Bitcoin are mined? Will fees be enough incentive to maintain the network?

**Reclaiming Disk Space**
- certain Tx are guaranteed at a certain point
    - just storing the block header
- merkle tree
    - hash of Tx0 and Tx1 and concatenate to Hash01

>MEV is smart contract mainly (e.g. Ethereum) but Bitcoin has a version called **selfish mining**

## Day 3 - Ethereum Blockchain

**Ethereum Blockchain**

>Presenter showed a *piggy-back contract* on Ethereum (Turing Complete). Bitcoin is **not** Turing Complete.
>
> Anyone can deposit in to this contract but only a specific address(es) can withdraw up to a certain limit.
>
>Contract currency is **gwei**

**Shared Links**
- [How does Ethereum work anyway?](https://www.preethikasireddy.com/post/how-does-ethereum-work-anyway)
- [Piggy Bank Solidity Code](https://docs.google.com/document/d/1E2NMtcC-XrKTlShMHIonXacRL5SStnuxfxbAAX14xzM/edit?usp=sharing)
- [Gwei - Investopedia](https://www.investopedia.com/terms/g/gwei-ethereum.asp#:~:text=Key%20Takeaways-,Gwei%20is%20a%20denomination%20of%20the%20cryptocurrency%20ether%20(ETH)%2C,to%20specify%20Ethereum%20gas%20prices)
- [Gwei to USD Converter](https://nomics.com/markets/gwei-gwei/usd-united-states-dollar)
- [Remix primer](https://remix-project.org/)
- [Remix](remix.ethereum.org)

**Blockchain**
Cryptographically secure transactional singleton machine with shared state.
- Cryptographically secure
    - creation of digital currency is secured by complex mathematical algorithms that are obscenely hard to break
- Transactional singelton machine
    - a single canonical instance of the machine responsible for al lthe transactions being created in the system
- With shared state
    - the state is is shared and open to everyone

**The Ethereum blockchain paradigm explained**
- For a transaction to be considered valid it must go through a process called mining
    - SHA256 hash
- Difference between Bitcoin and Ethereum is *not at the consensus layer* but at the **execution layer** or **computational layer**
- Sharded chain (Eth 2.0)
- block of transactions ~ every 10 secs
- miners must be rewarded for even working on non-canonical forks for a certain # of Tx
- GHOST
    - Greddiest Heaviest Observed Subtree
        - i.e. the highest block number

**Two types of accounts on Ethereum**
- Contract
    - controlled by their contract addresses
    - have code associated with them
    - cannot sign Tx
    - Deployment contract fees are fixed at 32000 gwei
        - ERC1155 is more expensive (??) @ 45000 gwei
    - execution/interation fees are based on the number of OPCODES in the contract
- Externally owned account (Wallet)
    - no code associated with them
    - must authorized to sign Tx
    - controlled by private keys
    - can send messages to other external and contract accts.

**Account state consists of**
- Nonce
    - if external, shows the # of transactions from the account address
    - if contract, shows the # of contracts created by the account
- balance
    - the # of WEI owned by this address
- storageRoot
    - hash of the root node of a Merkle Tree
- codeHash
    - if exteranlly owned
        - SHA256 hash of the empty strnig

**World State**

- Merkle Patricia tree
- Merkle Tree is a set of nodes that:
    1. large # of leaf nodes at the bottom
    2. intermediate nodes
        - each node is a hash of its child nodes
    3. single root node
        - formed from the hash of its two child nodes
        - forms the top of the treee
- keeps track of last 128 blocks
- hard to tell which Tx is spam, typically depends on the OPCODES

**Gas**

- measured in gwei
- a functional reason for gas to exist is: if a malicious dapp submitted an infinite loop, the transaction would eventually run out of ether and terminate, allowing the network to return to normal.

**Decentralization in PoW v. PoS**

- censoring at the protocol level is possible (and has been discussed)
    - only possible in Proof of Stake

## Day 4

#### Materials Covered
- [Ethereum Whitepaper](https://ethereum.org/en/whitepaper/)
- [Comparing Bitcoin & Ethereum](https://www.visualcapitalist.com/comparing-bitcoin-ethereum-cryptos/)
- [Slides - **May** come later, copyright issue]()

#### What is an EVM
- Ethereum's state transactions are processed by the EVM
- Global State (n) -> Transaction -> EVM -> Global State (n+1)
- Stack-based virtual machine that does bytecode
    - must remove stacks to get to a particular stack
        - called popping the stack
- Smart contracts are EVM programs
    - written in Solidity
        - compiled to bytecode for EVM execution
- Turing complete
- i.e.
    - push 1 <- IP (instruction pointer)
    - push 2 <- 
    - add

#### How is Ethereum different than a computer?
- state changes are goverened by rules of consenuss
- globally distributed
- single, globally accessible, computer
    - independent on what type of computer it is ran on
    - should extract away details

#### What makes Ethereum similar to Bitcoin?
- P2P netwrok
- Transactions repreent state transitions
- Conseneus algorithm governs transactions - nakamoto
- State machine process transactions according to consensus
- Chain of blocks
- Game Theoretic
- . . . 

#### What makes it different?
- Bitcoin
    - digital currency
    - limited scripting language
    - pwnership of coins (UTXO)
    - does T or F comparison
- Ethereum
    - world computer
    - gernal purpose scripting language
    - general purpose data store (key value pair or tuple)
    
#### What is Turing Compelte?
- system in which a program can be written that will find an answer (no guarantees on runtime or memory)
- can be used to solve any computational problem
- can be forever reprogrammed
- propoerties
    - can run forever
    - can use infintite memory
    - has random access memory
    - can simulate any other Turing machine
- can execute a stored program while reading and writing data to memory
- can technically logic in a Turing complete logic (Java) and translate it to Solidity
- if you can use loops the language is considered Turing Complete (generally speaking)

Etherscan will not tell you if the address is a contract or personal account
    - indicated by nonce

#### Ethereum being Turing Complete is a feature and a bug
- can be used to write a program we can use on a regualr computer
- any program of any complexity can be run on Ethereum -- more surface area for bugs
    - Infinite loops
    - . . .

#### A little History
- Bitcoin launched in 2009
- People wanted to move beyond cryptocurrency applications
- Limitations with Bitcoin
    - building anything sophisticated reqquired additional off-chain layers
    - Vtalik tried to extend Mastercoin
        - proposal was too radical
- December 2013 - Vtalik started sharing his whitepaper
- Gavin Wood came along - together they evolved the vision
- July 30, 2015 - first Ethereum block was minted

#### Accounts
- a mapping between address and account states
    - wallet address
    - account state (balance)
    - contract address

#### What constitutes an Ethereum State?
An Ethereum account is comprised of:
- Ether balance
- Nonce
- Account storage
    - if smart contract
- Program code
    - if smart contract

#### Account Types:
Wallet
- private key
- nmo smart contract code
Smart Contract
- No private key
- . . .

#### What's the difference
- an externally owned account can send messages to other externally owned accounts or to other contracts by creating and signing a transaction using its private key
- message between to externally owned accounts is simply a value transfer
- contract accounts can only fire a transaction based on the response to another transaction

#### EOAs set in motion all transactions
- any actions occurs on the Ethereum
- . . .

#### Transaction
- signed messaged by an externally owned account
- they are the onyl things that can trigger a state change or cause a contract to exzecute in the EVM
- are Atomic (**all or nothing**)
    - no gas fees are returned on unexecuted transactions
- must occur sequentailly
- should not depend on any parallel computation
- Two **types** of Transactions:
    - contract creation
    - message call

**Contract creation**
- create a new contract account (i.e. a new smart contract)
- intitiated by externally owned account
- externally owned accounts create new Contract Accounts through a transaction
- sent to a special destination address called the zero address
- date field - completed bytecode of the contract
    - contains logic for smart contract
- value field - starting balance

**Contracts cannot be deleted**
- must be called through a self-destruct mechanism called from another contract 
        - deletes everything from the contract (all information)
        - history will not be erased

**Message call**
- everything that is not a contract creation transaction
- takes some input data
- . . .

**Structure of a Transaction**
- nonce
- gas Limit
- gas Price
- to address (external or contract)
- value
- V R S
    - used to verify the signer
- data

> **Transactions must occure sequentially**

**Transaction Value and Data**
- the main payload of a transaction is in two fields: value and data
- only value = payment
- only data = payment and invocation
- value and data = payment and invocation
- opayment transactions behave differently depending on the destination address is an EOA or a contract
- EOA account - balance will be added to balance
- contract account - EVM wil lexecute the contract and attempot a call the function in the data payload else

**Messges**
- transaction where data (as a set of bytes) and value (Wei) is passed from one account to another as part of executing the transaction (which was involed by the EOA)
- EOA -> Tx -> contract account -> data, value (message) -> contract account -> data, value (message) -> contract account . . .

**Four Cases of Messages**
- Intiated EOA
    - sent to EOA - value transfer
    - sent to CA - i.e. creating a deposit in Uniswap
- Initiated CA
    - sent to EOA 
    - sent to CA

**Tramitting Throug The Network**
- cannot send a transaction straight from your browser
- Flood routing
    - construct transaction
    - signed transaction is validated locally
    - Tx is transmitted to Ethereum nodesthat are directly
    - if neighbors agree Tx is valid they atore a copy and propogate to their neighbors
    - transaction ripples outward, flooding across the network until all nodes in the network have a copy of the transaction

> Metamask wallet connection creates a node in Ethereum network

> Infura is a centralized node

**Nodes**
- mining nodes - requires 6/7 terrabytes
- full node - 
- archive node - 
- Bitcoin has full node and mining node

## Day 5

**Closing out Ethereum topic and moving towards TE Fundamentals**

**Reviewing EVM info from Day 4**

**Nodes**
- mining nodes - requires 6/7 terrabytes
- full node - 
- archive node - 
- Bitcoin has full node and mining node

**Block Gas Limit**
- max amount of gas
- miners decide blockgas limit
- increases over time

**Block is found**
- PoW begins
- One (or more) miner nodes solves the POW block
- Miner node(s) broadvast the valid block to the network
    - gets pais gas all gas and mining fees

**Transaction order is determined by miners**
- A - B - C - D
- if an new transaction ( E ) comes in then more gas must be paid to be included in the transaction. E - C - B - A
- Transactions can be front-run by miners
    - a form of MEV
- Sandwich attacks are another issue

**Smart contracts in a nutshell**
- written in Solidity
- compiled by bytecode that runs on the EVM
- deployed using a special contract creation transaction
- smart contracts are identified by an Ethereum address
- smart contracts don't have private keys
- smart contracts only run if they are called by a transaciton that is initieted by an EOA
- a contract can call another contract but the first contract in the chain of execution must be called by an EOA
- contracts are never executed in parallel 
    - because Ethereum is a single-threaded machine
- transactions are atomic
- smart contract code cannot change (immutable) however smart contracts can be deleted (self-destruct)

**The Nonce**
- the nonce is one of the most important and least understood components of a transaction
- a nonce is a scalar value equal to the number of transactions sent from this address
- a nonce is an attribute of the orginating address (only has menaing in the context of the sending address)
- not stored explicitly as part of an accounts state on the blockchain (calculated dynamically)
- two scenarios where it is useful
    - including transactions in order
    - transaction duplication protection
- exploring [Etherscan](https://etherscan.io)

**Gas**
- gas is fuel
- as the evm executes smart contracts it carefully accounts for every transaction
- each instruction has a cost (i.e. gas)
- each operation
    - adding 2 numbers cost 3 gas
    - calculating Keccak 256 hash cost 30 gas + 6 gas for each 256 bits of data being hashed
    - simple value transfer is 21000 gas
    - contract creation is 32000 gas
- gas is not Ether
- gas is used to control the amount of resources used
- the higher the gas price the faster the transaction will be mined
- gas limit
    - max amount of resources a transaction can use
    - transacitons set an upper gas limit
    - EVM terminates execution if the amount of gas exceeds available gas
- crucial in preventing DDoS attack

**Gas cost v. gas price**
- gas cost - measure of computation and storage used in the evm
- gas price - cost per unit of gas that the sender is willing to pay
- gas limit - the max a sender is willing to use in a transaction
- transaction fee  - total gas used x gas price
- negative costs:
    - deleteing a contract (-24000 gas)
    - chaning a storage address from a nonzero value to a zero value (-15000 gas)

**EIP-1559 changed how gas is handled**
- gas cost
- base fee (added) - targets 50% block fullness, subsequently burned
- max priority fee - optional tip to miner
- max fee per gas - absolute maximum user is willing to pay per unit of gas
- gas limit - the max sender is willing to use for that transaction
- transaction fee - . . .

**EVM**
- a global decentralized conputer

**EVM Architecture**
- stack based architecture
- all in-memory values are stored on a stack
- 256-bit word size to facilitate elliptical hash computations
- addressable data:
    - immutable program code
    - volatile memory - every location initiaized to zero
    - permanent storage

**Arithmetic Operations**
- add
- mul
- sub
- div
- sdiv - signed integer dividsipon
- mod
- smod
- addmod
- mulmod
- exp
- signextend
- sha3

**Stack Operations**
- pop
- mload
- mstore
- sload
- store
- msize
- pushx
- inclusive dupx
- swapx inclusive

**Process Flow**
- stop
- jump
- jumpi
- pc
- jumpdest

**System Operations**
- logx inclusive
- create
- call
- callcode
- return
- delegatecall
- staticcall
- revert
- invalid
- self destruct

**Logic Operations**
- lt
- gt
- slt
- sgt
- eq
- iszero
- . . .

**Environmental Operators**
- . . . 

**Block Operations**
- blockhash
- coinbase
- timestamp
- number
- difficulty
- gaslimit

**Gas accounting during execution**
- nothing covered - end of session

## Day 6

### Covering the ETH merge

- [Article](https://dune.com/sixdegree/ethereum-the-merge)
- [Follow merge in real-time](https://www.google.com/search?q=the+merge&oq=the+mer&aqs=chrome.0.69i59j69i57j69i59l2j69i61j69i65j69i61l2.3234j0j1&sourceid=chrome&ie=UTF-8)
- Merge is changing the consensus mechanism to Nakamoto consensus
- 32 ETH to be a validator
- Make a mistake and get slashed
- Issuance will reduce massively
- 2 Execution layers
    - Computation
    - Consensus
- Sharding is now implemented
- Ethereum built a parallel chain (beacon) that cloned the PoS chain
- Issuance rate
     - **formerly** 4.3% inflation per year
     - **now** *0.43%* inflation per year now
- No change in token usage
- Only full node runners needed to update/upgrade anything
    - **ETH held in personal wallet requires no actions**

### Covering the TE Fundamentals Module 1

- Will be working through one module a week.

## Day 7

### Topics
- Part 3 of Module 1 in TE Fundamentals
    - [Web 3 Sustainability Loop](https://blog.oceanprotocol.com/the-web3-sustainability-loop-b2a4097a36e)


## Slides

[Day 1](https://cdn.discordapp.com/attachments/1001806395185823814/1006972600074911844/TE_Fundamentals_-_back_to_basics.pdf)

Day 2 - local download (PDF)

Day 3 - no slides, read directly from the text

Day 4 - waiting for link (copyright issue with slide author)

## Recordings

[Day 3](https://drive.google.com/file/d/1tACAOviS39sCKEoeqfS2FgNXwdtZcA6u/view?usp=sharing)

## Links

[Token Engineering Fundamentals](https://medium.com/tokenengineering/token-engineering-fundamentals-49b15b42fa5) - Medium
[Bitcoin Whitepaper](https://bitcoin.org/en/bitcoin-paper) - Paper
[Can Blockchains Go Rogue?](https://blog.oceanprotocol.com/can-blockchains-go-rogue-5134300ce790) - Article

## Code

**Piggy Bank Solidity Code**
```
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract Bank {
    address child;
    address owner;
    uint maxWithdrawAmount;
    
    constructor(address _child, uint _maxWithdrawAmount) {
        owner = msg.sender;
        child = _child;
        maxWithdrawAmount = _maxWithdrawAmount;
    }
    
    modifier isChild() {
        require(msg.sender == child);
        _;
    }
    
    function deposit() payable public {
    }
    
    function withdraw(uint amount) public isChild() {
        require(amount <= maxWithdrawAmount, "Amount greater that maximum allowed limit");
        (bool success, ) = payable(msg.sender).call{value: amount}("");
        require(success, "Failed to send Ether");
    }
}
```
