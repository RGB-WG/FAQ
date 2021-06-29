---
description: >-
  Description of Client-validated confidential smart contracts using bitcoin
  transaction graph for Bitcoin and Lightning Network
---

# RGB Smart contracts

RGB as a smart contract system described in the [LNPBP-11 ](https://github.com/LNP-BP/LNPBPs/blob/master/lnpbp-0011.md)standard is able to work on top of the Lightning Network and designed with confidentiality and scalability in mind. It's created & maintained by the [LNP/BP Standards Association](https://www.lnp-bp.org/). More information about the Association's activities can be found [here](https://github.com/LNP-BP).

### Abstract

**What is possible with RGB:**

* Issue digital fungible assets, like stock, bonds and other forms of securities;
* create different forms of collectibles \(non-fungible assets\);
* create and manage sovereign/decentralized identities and reputation systems;
* create and maintain provably-unique history of some events that may be used for audit with well-controlled partial disclosure of the data;
* design and run other forms of arbitrary-complex smart contracts

### Design

As a smart contract system RGB is quite different from previous approaches, both Bitcoin-based \(Colored coins, Counterparty, OMNI\) and non-bitcoin \(Ethereum, EOS and others\):

* RGB separates the concepts of smart contract **issuer**, **state owners** and **state evolution**
* RGB keeps the smart contract code and data offchain
* RGB uses blockchain as a state commitment layer and Bitcoin script as an ownership control system; while smart contract evolution is defined by off-chain **schema**

More about these concepts can be read in [this presentation](https://github.com/LNP-BP/FAQ/blob/master/Presentation%20slides/RGB%20%26%20Spectrum%20explanation%20for%20business.pdf).

Briefly, RGB smart contracts operate with **client-side validation** paradigm, meaning that all the data is kept outside of the bitcoin transactions, i.e. bitcoin blockchain or lightning channel state. This allows the system to operate on top of Lightning Network without any changes to the LN protocols and also gives a foundation for a high level of protocol scalability and privacy.

As a security mechanism RGB uses **single-use seals** defined over bitcoin transaction outputs, which provides ability for any party having smart contract state history to verify its uniqueness. In other words, RGB leverages Bitcoin script for its security model and definition of the **ownership** and **access rights**.

Each RGB smart contract is represented by some **genesis state**, created by **smart contract issuer** \(or, put simply, issuer\) and a directed acyclic graph \(DAG\) of **state transitions** kept in form of _client-validated data_ \(i.e. this data is not stored on blockchain or within LN transactions/channel state\). The state is **assigned** to unspent bitcoin transaction outputs, which defines them as _single-use seals_. The party that is able to spend corresponding transaction output is named a party **owning state**: it is a party that has the right to change the corresponding part of the smart contract state by creating a new _state transition_ and committing to it in a transaction spending the output containing previous state. This procedure represents **closing of a seal over state transition**, and a pair of spending transaction and corresponding extra-transaction data on the state transition are named **witness**.

_State transition_ **assigns** _state_ to a set of defined **single-use seals**. Each smart contract may maintain different forms of state and define different kinds of single-use seals with different validation rules. Additionally to this, state transition may contain different metadata and _Simplicity scripts_, defining parts of its business logic.

Which types of state, seals, metadata and which script extensions are allowed within state transitions is defined by **schema**. Thus, schema can be seen as validation rules for _client-side validation_; schema is always defined by the issuer in state genesis. Schema also may contain Turing-complete _Simplicity scripts_ defining parts of the business logic for _client-side validation_.

RGB operates in "shards", where each contract has a separate **state history** and data; different smart contracts never intersect in their histories directly. This allows another level of scalability; and while the therm "shard" is incorrect, we use it to demonstrate that RGB actually achieves what was planned to be achieved with "Ethereum shards".

While being separately maintained, RGB contracts may interact via **RGB DEX** protocol over the Lightning Network, allowing multiparty **coordinated state changes**, which, for instance, enables functionality like DEX over Lightning etc.

Thus, by their abilities RGB smart contracts go beyond what is possible with Ethereum-like smart contract system, providing more layered, scalable, private and safe approach, where the ownership of the smart contract state is separated from the smart contract creation.

