# General Grant Proposal

* **Project:** Manta Network

## Project Overview :page_facing_up: 
Manta Network is the first privacy-preserving DeFi stack powered by zkSNARK. 
It includes the Decentralized Anonymous Payment (DAP) and Decentralzied Anonymous eXchange (DAX). 
Decentralized Anonymous Payment (DAP) is a decentralized anonymous payment scheme for Polkadot and Parachain assets (including wrapped assets and stablecoins). 
Decentralzied Anonymous eXchange (DAX) is a decentralized anonymous exchange scheme based on AMM and zkSNARK.

### Overview

[Manta Network](www.manta.network) team aims to develop a private preserving decentralized exchange on Polkadot eco-system using zkSNARK. Below is an overview of Manta platform:

![image of manta-platform](https://github.com/Manta-Network/Manta-Documentations/raw/main/manta-platform.png)

The cryptographic construction paper can be found [here](https://github.com/Manta-Network/Manta-Documentations/blob/main/manta-whitepaper.pdf). 
An abstracted work flow is also available [here](https://github.com/Manta-Network/Manta-Documentations/blob/main/manta_workflow.pdf).
Below is the Manta architecture:

    ----------------------------------------------------
    | Decentralzied Anonymous eXchange (DAX)           |  <---- This grant
    ----------------------------------------------------
    | Decentralized Anonymous Payment (DAP)            |  <---- W3F open grants program receipent
    ----------------------------------------------------
    | Polkadot and Parachain Assets (e.g stable coins) |
    ----------------------------------------------------

The details of Manta DAP and DAX schemes can be found section 3, and section 4 of 
[Manta White Paper](https://github.com/Manta-Network/Manta-Whitepaper/blob/main/manta-whitepaper.pdf). It will be based on the following cryptographic primitives:
* A statiscally-hidding non-interative commitment scheme, we are planning to use Pedersen hash in the actual construction.
* zkSNARK, we are planning to use [arkworks snark construction](https://github.com/arkworks-rs/snark) based on Groth16.
* Public key encryption, we are using a variant of the ephemral Diffie-Hellman system.

### Project Details 

#### Manta DAP

Manta DAP has support two kinds transactions:
* `tx_mint`: mint private coins from public coins (base coins).
* `tx_transfer`: transfer private coins to private/public coins.

(Please see section 3 of [the white paper](https://github.com/Manta-Network/Manta-Whitepaper/blob/main/manta-whitepaper.pdf) for more details.)

##### Mint private coins from base coins

To mint a new private coin, a user `u` needs to initiate a coin minting transaction
`tx_mint` with the deposit of base coin, more specically:
1. `u` samples a random number, which is a secret value that determines the private coins serial number (Note: `tx_mint` didn't include this number).
2. `u` commits her public key `a_pk`, the value of the coin `v`, and the random secret `s` that she sampled in the last step in a two stage commitments.
3. `u` thus mint a private coin and only put the value, the first stage commitment, the random secret for the second stage commitment, and the final commitment.
4. The ledger verifies that the `u` indeed deposits base coin of value `v` and add the final commitment to the merkle tree that represent ledger state.

##### Transfer private coins

Private coins can be spent and transferred by `tx_transfer`, which takes a set of input private coins to be consumed, and transfers their total value to a set of output coins: which could be either private or public.

To transfer a private coin, a user need to provide a zero knowledge proof of she knows 
the old coins, new coins, and the secret key of old coin such that:
1. both the new coins and old coins are well formed
2. the address secret key matches the public key
3. the old coin's commitment appears as a leaf of the merkle tree representing ledger state
4. The set of old coins and the set of new coins have the same total value (minus transaction fee).

The new coin will be posted on chain using public key encryption.

#### Manta DAX

Manta Decentralized Anonymous eXchange scheme is based on zkSNARK and AMM. The overall design intuition is that the ledger maintains `x*y = k` (or using some more sophiscated curve) invariant for an exchange pair. The validation logic requires that trader provide an zero-knowledge proof of the fulfillment of this invariant after trading. Below is a simplified architecture of Manta DAX:

<img src="https://github.com/Manta-Network/Manta-Documentations/raw/main/manta-workflow.png" width="800">

(Please see section 4 of [the white paper](https://github.com/Manta-Network/Manta-Documentations/blob/main/manta-whitepaper.pdf)  and
the [workflow](https://github.com/Manta-Network/Manta-Documentations/blob/main/manta_workflow.pdf)
for more details.)


### Ecosystem Fit 
The current ecentralized exchanges scheme lack privacy, anti surveillance interoperability, and anonymous cryptocurrencies’ lack of price stability. As the first decentralized anonymous payment that could support existing assets, Manta DAP will be a great addition to Polkadot eco-system since Polkadot and Parachain assets such as aUSDT and wrapped BTC can be transferred and spent privately. We already talked to Polkadot eco-system members such as Acala and Equilibrium. They showed strong interests of integrating with Manta. Also, Manta DAP will be the an important building block for Manta DAX (Decentralized Anonymous eXchange) scheme that enables privacy preserving AMM style decentralized exchange using zkSNARK.
## Team :busts_in_silhouette:

### Team members
* Shumo C.
* Kenny L., Victor J.,  Qiudong X.,	Zhenfei Z.,

### Team Website	
* https://manta.network

### Legal Structure 
Manta Network Ltd., a British Virgin Islands corporation

### Team's experience

* Shumo Chu: Shumo is an assistant professor at UCSB. He obtained a Ph.D. in Computer Science and Engineering from University of Washington. Before UCSB, he served as a research scientist in a crypto startup Algorand. He helped algorand developed [PyTeal](https://github.com/algorand/pyteal), a smart contract DSL in Python. He published more than 10 peer-reviewed papers in top conferences in database systems and programming languages such as SIGMOD, VLDB, and PLDI and won the SIGMOD Best Demo Award.

* Kenny Li: Kenny is an entrepreneur that has started, advised, and invested in startups for over seven years. His initial business exposure in the cryptocurrency space was an advisory role for a Bitcoin options trading platform in 2014. He is a frequent writer on blockchain topics and operates a fund. He is the teaching assistant for Blockchain Lab and MBA graduate at MIT Sloan.

* Victor Ji: Victor is a Harvard University Economics Master. Binance Evangelist. Advisor to Unifi Protocol. He previously served as the Chair of Harvard Kennedy School Blockchain and Cryptocurrency PIC. He is a columnist of Chainnews, 8Btc, Mars finance. Before Harvard, he was the executive partner of BitBlock Capital and worked at Ontology.

* Qiudong Xia, Crypto System Engineer: Master student at University of Science and Technology of China. Qiudong has been working actively on access control and security of networking systems and published papers in top networking conferences and journals such as IEEE INFOCOM, ACM Trans. Networking, and ICC.

* Zhenfei Zhang: Zhenfei obtained his Ph.D. in computer science at University of Wollongong, Australia. He was the director of cryptographic research at OnBoard Security, and a cryptographic engineer at Algorand. Zhenfei has published over 30 papers in cryptography in top conferences such as Crypto and ACM CCS; contributed to multiple proposals to NIST post-quantum cryptography competition; and co-drafted the BLS IETF Internet-draft.


### Team Code Repos
* https://github.com/Manta-Network/pallet-manta-dap
* https://github.com/Manta-Network/manta-node
* https://github.com/Manta-Network/manta-front-end

### Team LinkedIn Profiles
* https://www.linkedin.com/in/shumo-chu-a1722416/
* https://www.linkedin.com/in/kennymuli/
* https://www.linkedin.com/in/canghai-victor-ji-cpa-37688a5b/
* https://www.linkedin.com/in/zhenfeizhang/

## Development Roadmap :nut_and_bolt: 




### Overview
* **Total Estimated Duration:** 36 weeks
* **Full-time equivalent (FTE):**  XXX
* **Total Costs:** __XXXX__

### Notes

* Manta's decentralized anonymous payment (DAP) protocol, a receipant of W3F Open Grants Program. Components: [Manta-DAP-runtime](https://github.com/Manta-Network/manta-node),
[Manta-DAP-pallet](https://github.com/Manta-Network/pallet-manta-dap); fully compatible with `rococo-v1` release.

* This grant application will focus on the second stage of Manta Protocol, namely, the decentralized anonymous exchange protocol (DAX). 

### Milestone 1 — Prototye Implementation of Substrate Modules 

* **Estimated Duration:** 12 weeks
* **FTE:**  __TBD__
* **Costs:** __TBD__

| Number | Deliverable | Specification |
| ------------- | ------------- | ------------- |
| 0. | License | Apache 2.0 / MIT / Unlicense |
| 1. | Substrate module: __manta-dax-pallet__ | We will create a Substrate module that implements the exchange logics |  
| 2. | Substrate module: __manta-dax-crypto__ | We will create a Substrate module that implements backend zero-knowledge proofs and other neccessary cryptographic components |  
| 3. | Documentation | We will provide an inline documentation of the code; and a demo of the prototype |
| 4. | Testing | The code will have a __functional__ unit-test coverage (e.g. __70%__) to ensure functionality; test will be conducted against pre-computed data set | 

* Verifiable by:
  * 1, 2 : Investigating GitHub repository; CI build and test status.
  * 3, 4: running tests locally from the source code to deploy and test a local chain;  `grcov` for test coverage.

### Milestone 2 — Parachain implementaion and integration

* **Estimated Duration:** 12 weeks
* **FTE:**  __TBD__
* **Costs:** __TBD__

| Number | Deliverable | Specification |
| ------------- | ------------- | ------------- |
| 0. | License | Apache 2.0 / MIT / Unlicense |
| 1. | Substrate module: __manta-dax-runtime__ | We will create a Substrate runtime module that hooks up the DAX to a parachain |  
| 2. | Substrate chain | manta-dax-crypto -> manta-dax-pallet -> manta-dax-runtime -> parachain node |  
| 3. | Rococo integration | Integrate __manta-dax__ parachain to rococo testnet |
| 4. | Client | we will provide a client CLI to generate dax package |
| 5. | Documentation | We will provide both inline documentation of the code and a basic tutorial that explains how a user can (for example) spin up one of our Substrate nodes. Once the node is up, it will be possible to send test transactions that will show how the new functionality works _within the local manta parachain_. |
| 6. | Testing Guide | The code will have __proper__ unit-test coverage (e.g. __80%__) to ensure functionality and robustness. In the guide we will describe how to run these tests. The tests are run against run-time generated dataset from the Client CLI. | 


* Verifiable by:
  * 1, 2, 3, 4: Investigating GitHub repository; CI build and test status.
  * 5, 6: running tests locally from the source code to deploy and test a local chain;  `grcov` for test coverage.

### Milestone 3 — Cross chain functionality

* **Estimated Duration:** 12 weeks
* **FTE:**  __TBD__
* **Costs:** __TBD__

| Number | Deliverable | Specification |
| ------------- | ------------- | ------------- |
| 0. | License | Apache 2.0 / MIT / Unlicense |
| 1. | Substrate module: __manta-dax-crosschain__ | We will create a crosschain module using XCMP and ORML |   
| 2. | Rococo integration | Integrate __manta-dax-crosschain__ to rococo testnet |
| 3. | Client | we will provide a client CLI to generate dax package for crosschain messages |
| 4. | Documentation | We will provide both inline documentation of the code and a basic tutorial that explains how a user can (for example) spin up one of our Substrate nodes. Once the node is up, it will be possible to send test transactions that will show how the new functionality works _across different parachains_. |
| 5. | Testing Guide | The code will have __proper__ unit-test coverage (e.g. __90%__) to ensure functionality and robustness; and with proper edge case tests and stress tests. In the guide we will describe how to run these tests. The tests are run against run-time generated dataset from the Client CLI. | 
| 6. | Docker | We will provide a dockerfile to demonstrate the full functionality of our chain |

* Verifiable by:
  * 1, 2, 3: Investigating GitHub repository; CI build and test statuse.
  * 4, 5: running tests locally from the source code to deploy and test a local chain; `grcov` for test coverage.
  * 6: running tests locally from the docker to deploy and test a local chain.

### Community engagement

Our co-founder Victor Ji is the chair of Harvard Kennedy School Blockchain and Cryptocurrency PIC, which is one of the largest blockchain community in eastern America. He can reach the local tech communities since he organized many Hackathons for the ETH foundation and Dorahacks in Boston. 

Meanwhile, as a famous investor and columnist at top-tier Chinese blockchain media, Victor can engage with China investors and communities based on his connection. So we can build our communities in both US and China for Polkadot and Manta based on our previous experiences and resources. 

We already created the Twitter, WeChat, telegram and medium channels for the Manta Network. In next step, we will work with our investors and partners to widespread it. Moreover, we will select investors to choose those with strong media and community resources. 

Besides, we are actively engaging with Polkadot ecosystem projects like Acala, Equilibrium, Moonbeam, Stafi, Sora and Reef to find opportunities to work together in research, development and community building.
## Future Plans
Manta DAX is the second part of [Manta](https://manta.network) project. The future plan of Manta includes:
* A ceremony tool to do decentralized trusted setup using MPC (secure multi-party computation).
* A community effort to create a open standard for DApp using zkSNARK on Polkadot, so that ZK based applications can be composed together more easily.
* Expanding more use cases to business, and supporting more assets. 
* We are also looking to build a decentralized anonymous saving & lending platform, synthetic private investments, and other DeFi adoption.


## Additional Information :heavy_plus_sign: 

### Achievement so far:
* Tech design completed
* Manta-DAP POC implementation complete
* W3F-Open-Grants milestone 1 submitted

<!-- We finished the cryptographic scheme design of Manta, see [Manta White Paper](https://github.com/Manta-Network/Manta-Documentations/blob/main/manta-whitepaper.pdf). We are still quickly iterating and refining the engineering details of Manta.  -->


### Contacts

Email: contact@manta.network

Website: https://manta.network/

Whitepaper: https://github.com/Manta-Network/Manta-Documentations/

Github: https://github.com/Manta-Network

Twitter: https://twitter.com/mantanetwork?s=21

Medium: https://medium.com/@mantanetwork

Telegram: https://t.me/mantanetwork
