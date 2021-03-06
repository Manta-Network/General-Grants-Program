# General Grant Proposal

* **Project:** Manta Network

## Project Overview :page_facing_up: 
Manta Network is the first privacy-preserving DeFi stack powered by zkSNARK. 
It includes the Decentralized Anonymous Payment (DAP) and Decentralzied Anonymous eXchange (DAX). 
Decentralized Anonymous Payment (DAP) is a decentralized anonymous payment scheme for Polkadot and Parachain assets (including wrapped assets and stablecoins). 
Decentralzied Anonymous eXchange (DAX) is a decentralized anonymous exchange scheme based on AMM and zkSNARK.

### Overview

[Manta Network](www.manta.network) team aims to develop a private preserving decentralized exchange on Polkadot eco-system using zkSNARK. Below is an overview of Manta platform:

![image of manta-platform](https://github.com/Manta-Network/Manta-Whitepaper/raw/main/manta-platform.png)

The cryptographic construction paper can be found [here](https://github.com/Manta-Network/Manta-Whitepaper/blob/main/manta-whitepaper.pdf). Below is the Manta architecture:

    ----------------------------------------------------
    | Decentralzied Anonymous eXchange (DAX)           |  <---- Future plan
    ----------------------------------------------------
    | Decentralized Anonymous Payment (DAP)            |  <---- This grant
    ----------------------------------------------------
    | Polkadot and Parachain Assets (e.g stable coins) |
    ----------------------------------------------------

The details of Manta DAP and DAX schemes can be found section 3, and section 4 of 
[Manta White Paper](https://github.com/Manta-Network/Manta-Whitepaper/blob/main/manta-whitepaper.pdf). It will based on the following cryptographic primitives:
* A statiscally-hidding non-interative commitment scheme, we are planning to use Pedersen hash in the actual construction.
* zkSNARK, we are planning to use [arkworks snark construction](https://github.com/arkworks-rs/snark) based on Groth16.
* Public key encryption, we are planning to use the ZK friendly ElGamal scheme.

### Project Details 
We expect the teams to already have a solid idea about the project's expected final state.

Therefore, we ask the teams to submit (where relevant):
* Mockups/designs of any UI components
* API specifications of the core functionality
* An overview of the technology stack to be used
* Documentation of core components, protocols, architecture etc. to be deployed
* PoC/MVP or other relevant prior work or research on the topic

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

* Zhenfei Zhang: Zhenfei obtained his Ph.D. in computer science at University of Wollongong, Australia. He was the director of cryptographic research at OnBoard Security, and a cryptographic engineer at Algorand. Dr. Zhang has published over 25 papers in cryptography; contributed to multiple proposals to NIST post-quantum cryptography competition; and co-drafted the BLS IETF Internet-draft.


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

This section should break out the development roadmap into a number of milestones. Since the milestones will appear in the grant contract, it helps to describe the functionality we should expect, plus how we can check that such functionality exists in the product. Whenever milestones are delivered, we refer to the contract to ensure that everything has been delivered as expected.

Below we provide an **example roadmap**. In the descriptions it should be clear how the project is related to Substrate and/or Polkadot. We recommend that the scope of the work can fit within a 3 month period and that teams structure their roadmap as 1 month = 1 milestone. 

For each milestone:
* Please be sure to include a specification of the software. The level of detail must be enough so that we are able to verify that the software meets the specification.
* Please include total amount of funding requested per milestone.
* Please note that we require documentation (e.g. tutorials, API specifications, architecture details) in each milestone. This ensures that the code can be widely used by the community.
* Please provide a test suite, comprising unit and integration tests, along with a guide on how to run these.
* Please commit to providing a dockerfiles for the delivery of your project. 
* Please indicate the milestone duration, as well as number of Full-Time Employees working on each milestone, and include the number of days along with their cost per day.

### Overview
* **Total Estimated Duration:** Duration of the whole project
* **Full-time equivalent (FTE):**  Workload of an employed person ([see](https://en.wikipedia.org/wiki/Full-time_equivalent)) 
* **Total Costs:** Amount of Payment for the whole project. The total amount of funding needs to be below $100k.

### Milestone 1 Example — Implement Substrate Modules 
* **Estimated Duration:** 1 month
* **FTE:**  1
* **Costs:** $5,000

| Number | Deliverable | Specification |
| ------------- | ------------- | ------------- |
| 0a. | License | Apache 2.0 / MIT / Unlicense |
| 0b. | Documentation | We will provide both inline documentation of the code and a basic tutorial that explains how a user can (for example) spin up one of our Substrate nodes. Once the node is up, it will be possible to send test transactions that will show how the new functionality works. |
| 0c. | Testing Guide | The code will have proper unit-test coverage (e.g. 90%) to ensure functionality and robustness. In the guide we will describe how to run these tests | 
| 1. | Substrate module: X | We will create a Substrate module that will... (Please list the functionality that will be coded for the first milestone) |  
| 2. | Substrate module: Y | We will create a Substrate module that will... |  
| 3. | Substrate module: Z | We will create a Substrate module that will... |  
| 4. | Substrate chain | Modules X, Y & Z of our custom chain will interact in such a way... (Please describe the deliverable here as detailed as possible) |  
| 5. | Docker | We will provide a dockerfile to demonstrate the full functionality of our chain |

### Milestone 2 Example — Additional features
...

### Community engagement

Our co-founder Victor Ji is the chair of Harvard Kennedy School Blockchain and Cryptocurrency PIC, which is one of the largest blockchain community in eastern America. He can reach the local tech communities since he organized many Hackathons for the ETH foundation and Dorahacks in Boston. 

Meanwhile, as a famous investor and columnist at top-tier Chinese blockchain media, Victor can engage with China investors and communities based on his connection. So we can build our communities in both US and China for Polkadot and Manta based on our previous experiences and resources. 

We already created the Twitter, WeChat, telegram and medium channels for the Manta Network. In next step, we will work with our investors and partners to widespread it. Moreover, we will select investors to choose those with strong media and community resources. 

Besides, we are actively engaging with Polkadot ecosystem projects like Acala, Equilibrium, Moonbeam, Stafi, Sora and Reef to find opportunities to work together in research, development and community building.
## Future Plans
Please include the team's long-term plans and intentions.

## Additional Information :heavy_plus_sign: 
Any additional information that you think is relevant to this application that hasn't already been included.

Possible additional information to include:
* What work has been done so far?
* Are there are any teams who have already contributed (financially) to the project?
* Have you applied for other grants so far?
