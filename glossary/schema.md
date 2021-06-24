# Schema

**RGB Schema** is a “blueprint”/standard for constructing RGB smart contracts. The way ERC defines token standards used for integration of Ethereum contract that issues some tokens into wallets and exchanges, Schema defines a standard for RGB assets \(fungible assets, collectibles, digital identities etc.\).

When an issuer defines some issuance contract, in order to be supported by wallets/exchanges it must stick to \(“validate against”\) particular Schema.

When wallets and exchanges get information \(data and contract\) about some asset, they need to validate it against a specific Schema, that needed to be used for creating the asset. Only if the validation against that Schema is passed, they can accept the request and start working with the asset. 

Wallets or exchanges will always use Schema-based libraries \(for example “RGB fungible assets”, “RGB collectibles”\) instead of complex & universal core RGB library.  
  
From technical standpoint, Schema describes actual requirements for the state transition validation outside of the level of Bitcoin script commitments. It allows simple updates without software modifications, so that wallets, explorers, LN nodes etc could accept new types of assets without any code changes.

## What does Schema define and describe?

1. Types of metadata and their value restrictions \(maximum length for strings, maximum value for integers etc\).
2. Types of rights \(i.e. state\) and their value restrictions.
3. How rights transfers \(state transitions\) can be organized:
   * which metadata they should provide
   * which rights can be \(or must be\) transferred jointly
   * history validation rules for each of the rights, defined using Simplicity \(such as 'the sum of outputs must be equal to the sum of inputs\).
4. How these rules can be further limited \(or extended\) at the level of genesis and individual state transitions.

### From technical perspective, RGB Schema defines the following:

* Types of state transitions
* Types of seals transitions
* Semantics for state and Simplicity scripts for validating the state
* Semantics for metadata
* Referenced Simplicity script modules
* Additional constraints on each type of state transition:
  * Which seals may be defined by the state transition
  * Which state may be associated with each seals
  * Which metadata is required, optional and prohibited
  * Which additional scripts and with which constraints may be defined



## 

