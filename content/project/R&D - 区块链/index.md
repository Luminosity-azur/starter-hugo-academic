---
title: Blockchain
subtitle: This paper is a summary of relevant theoretical research in the previous period.

# Summary for listings and search engines
summary: This paper is a summary of relevant theoretical research in the previous period.

# Link this post with a project
projects: []

# Date published
date: '2022-01-08'

# Date updated
lastmod: '2022-01-08'

# Is this an unpublished draft?
draft: false

# Show this page in the Featured widget?
featured: false

authors:
  - admin

tags: 
  - Blockchain


math: true

image:
  focal_point: Smart

---

This paper includes the basic concepts, core technology, application, development and crisis of blockchain technology.
## Basic concepts
- What is blockchain?

Blockchain is a kind of distributed ledger that can not be tampered with or forged, and is guaranteed by cryptography.
Key characteristics: Decentralization, Tamper resistance, Anonymity, Safe and trusted

<br></br>

- Blockchain architecture
1. Data Layer: It mainly describes the physical form of the blockchain system. It is a chain structure of the blockchain starting from the Genesis block, including block data, random numbers, timestamps, public and private keys and other data. It is the lowest level data structure in the entire blockchain technology.
2. Network Layer: The mechanism of distributed network is mainly realized through P2P technology, including P2P networking mechanism, data transmission mechanism and data verification mechanism.
3. Consensus Layer: It includes consensus algorithm and consensus mechanism, enabling highly decentralized nodes to reach consensus on block data efficiently in a decentralized blockchain network. It is one of the key technologies of the blockchain. Currently, the more well-known consensus mechanisms encapsulated by the consensus layer include PoW, DPoS and PoS
4. Actrator Layer: It mainly includes the issuance system and distribution system of economic incentives. Its function is to provide certain incentives, encourage nodes to participate in the verification work in the blockchain, and incorporate economic factors into the blockchain technology system.
5. Contract Layer: It mainly includes various scripts, codes, algorithm mechanisms and smart contracts, which are the basis of blockchain programmability.
6. Application Layer: It encapsulates various application scenarios and cases, similar to applications on computer operating systems.

<br></br>

- Classification of Blockchain
1. Open chain - information is open to the public and can be used and maintained by any node, such as Bitcoin network.

2. Alliance Chain - Several organizations maintain a chain together. Only nodes with permissions can access it. It is applicable to supply chain organizations.

3. Private chain - only a few managers can operate the chain, and the information is not public, which is applicable to the company.

<br></br>
<br></br>

## Core technology
1. P2P network  
The end-to-end/point-to-point network is used to broadcast and spread all kinds of messages. Nodes can be accessed at will. Any two nodes are connected (decentralized), so messages can be transmitted to each other (forming a distributed ledger), and data is difficult to tamper with.

2. Asymmetric encryption algorithm  
Asymmetric encryption is mainly used in the blockchain. After hashing the transaction record or contract and other information, use the private key to encrypt to generate a digital signature and publish it to the network. Other nodes can verify whether the message has been tampered with through the public key to ensure security.

3. Consensus mechanism  
Trust can be established between unrelated nodes to reach a consensus on the consistency of the blockchain. Common consensus mechanisms include PoW, PoS, and DPoS

4. Merkel tree  
Store hash values for transactions.
Merkle Tree can be seen as a generalization of Hash List. The main difference between Merkle Tree and Hash List is that you can directly download and immediately verify a branch of Merkle Tree. Because the file can be divided into small data blocks, if a piece of data is damaged, just download the data block again. If the file is very large, Merkle tree and Hash list are both good. However, Merkle tree can download one branch at a time, and then immediately verify the branch. If the branch verification is passed, data can be downloaded. The hash list can only be verified by downloading the entire hash list.

<br></br>
<br></br>

## Application
1. Blockchain 1.0 - Bitcoin
  The concept of Bitcoin was put forward by Nakamoto Cong in 2008 to solve the problem of centralization and double spending, which led to the birth of a new digital currency - Bitcoin, which is the first application of blockchain technology.  
  
    Characteristics:  
    a. PoW consensus mechanism  
    b. Average block out time 10min  
    c. Only Bitcoin transfers are allowed  

<img src = 'https://s3.bmp.ovh/imgs/2022/10/05/4931438a2d7e7ddd.png' >

<br></br>

2. Blockchain 2.0 - Ethereum
    Ethereum=Bitcoin+Smart Contract
  
    Characteristics:  
    a. PoW consensus mechanism
    b. Average block out time 14s
    c. Support smart contract
    d. The change of incentive mechanism and the addition of uncle reward can further stimulate the enthusiasm of miners
    e. Support various decentralized applications (DApp)
    f. Programmable

<img src = 'https://s3.bmp.ovh/imgs/2022/10/05/38553debfa553855.png' >

<br></br>
<br></br>

## Development and Crisis
- Development

<img src = 'https://s3.bmp.ovh/imgs/2022/10/05/659df04cf88bd3ba.png' >

<br></br>

- Crisis

<img src = 'https://s3.bmp.ovh/imgs/2022/10/05/05388c5ef45a2a93.png' >
