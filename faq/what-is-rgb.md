# What is RGB?

**RGB** is client-side validated state and smart contracts system operating on Layer 2 and 3 of Bitcoin ecosystem. 

* RGB is **not a token protocol.** Though issuance and management of highly scalable, programmable and private assets of different sort is possible with RGB, it can be applied in many indusrtied far beyond financial world.
* Works with **Lightning Network**
* **No on-chain usage nor trackable footprint** because of client-validated paradigm
* **Scales** independently from Bitcoin timechain
* Includes **zero-knowledge** & privacy built on best research-based products
  * * Mimblewhimble: Bulletproofs by Andrew Poelstra
    * Liquid: Confidential Assets by Blockstream

## RGB main properties:

* Confidentiality
* Safety
* Scalability
* No bitcoin timechain congestion: transactions keep only homomorphic commitments which require no additional storage
* Future-ready without hardforks
* Higher censorship-resistance than in bitcoin: miners do not see that there is something going on with assets in transactions

## RGB main features:

* able to manage rich state
* uses **client-side validation** paradigm offered by [Peter Todd](https://github.com/petertodd), where the data is held by a “state owner” \(like asset owner\) and not by public consensus
* Operates on top of Bitcoin transaction graph, either from Bitcoin blockchain, or Lightning channel \(or any other kind of state channel\). Can work on top of Bitcoin as Layer 2 solution and on top of Lightning Network as Layer 3 one
* Can be scripted with Turing-complete formally-verified    Simplicity scripting language by Blockstream \(once it's released\)

Basically, **RBG is a digital rights management system**. Issuance, burning, secondary issuance, reissuance etc - are different forms of rights managed by RGB, alongside asset **ownership rights.** How these rights are structured and managed is defined by particular RGB **Schema**. Rights are controlled by Bitcoin script in Bitcoin transaction output; i.e. whoever can spend the output, has/owns the right, which was assigned to that output. **Assignments** are done with the current right owner; i.e. in case of genesis, is the issuer.

Additionally to rights \(defined by RGB but controlled by Bitcoin script\), RGB can add **state data**. Which **state** can be added to which right is again, defined by the Schema. The state can also evolve/change with each right transfer \(aka **state transition\).** The rules on how the state can evolve \(like the sum of inputs must be equal for the sum of outputs for token ownership right\) are defined by Simplicity script at the level of RGB.

## What one needs to distinguish when it comes to RGB:

1. Bitcoin data structures, for instance UTXO
2. RGB data structures, for instance state transition, genesis, owned right assignment, state data, metadata
3. RGB _concepts_, which are not always directly mapped to \(1\) and \(2\), which are “single-use-seal”, “owned right”

