# Right

## What is a right in RGB?

**Right** - type of action, defined in a smart contract, that can be taken only by a party owning some part of the smart contract state.

### Rights can be:

1. To have an asset\(s\)\* - e.g. if you have shares, it gives you the right to distribute dividends, vote etc.
2. To inflate asset supply - very different from p.1, as the person who owns the asset, doesn't have the right to inflate the supply of it, only the issuer decides and defines who will have this right. It also can be transferred to other party.
3. To prune/burn assets.
4. To own/do something with identity.
5. To create child identity for identity management.

\*Thus: **Assets are actual digital rights, and they are represented as ownership rights under RGB schema.**

### Main properties of rights in RGB:

* defined
* assigned
* transferred
* owned
* validated

### Right transfer/state transition validation rules.

1. Right transfer and state validation rules are **defined by schema** using 2 main instruments:

   a\) **schema structure** - defines how rights can be divided among descendants.

   > For example, if I have 100 assets and would like to give 10 of them to Alice and 90 of them to Bob, the fact that I can divide the asset like that is a part of schema structure.

   > There also can be other rights: indivisible as in case with non-fungible assets, identity or a right to inflate: I can’t divide it and the schema must clearly say that this right is indivisible.

   b\) **Simplicity script** - defines how to validate the rights/how the state of some rights may evolve.

   > For example, when you have an initial state and the final state, simplicity script can run arbitrary complex logic to validate that the state change is correct. In case of an asset we are not just adding the sum of inputs and outputs, because we use confidential amounts, we are using zk proof constructed out of homomorphic sum of inputs and outputs and that is basically being done by the simplicity script. Also, if you want you can create an asset that would be deflationary, you can restrict the rules of the state transition validation to the fact that the sum of outputs must be 10% lower than the sum of inputs \(and this is also defined by simplicity script as a part of a schema.

2. Can be further **restricted** \(and not extended\) at the level of **genesis** and each state transitions.
3. **Validated by new owners** backwards up to genesis within a particular subgraph.
4. Violation of the rights in one smart contract ownership branch **does not affect smart contract integrity** in the other branch.

### Security measures

1. Each right \(i.e. state\) does not have direct access to the information on another state, under other rights.

> For example, you have 2 different types of rights under smasr contract \(inflationary and right to asset\). At the level of validation of the history you are unable to take into account the information on whether some inflation happened or not \(if it had been allowed by the issuer, of course\). You can still validate that if the issuer hasn’t allowed the inflation, it did not happen. But if the issuer has allowed the inflation, you cannot see whether it already happened or not, while validating the amount that you received at your disposal. So **one state is isolated from another** in smart contract. It’s very different from how it works in Ethereum and brings strong security by default.

1. If required, rights can have a **“shared state”** using metadata; schema and genesis must explicitly define whether this is allowed.

> "Shared state" can be introduced only by the issuer and has to be defined at the level of schema, not at genesis. If the schema doesn’t allow you to share the state between different rights, as an issuer you need to stick to another schema that would allow that.

1. State can be **“hidden”** \(made confidential with zero knoweldge; which state MUST be hidden is defined by schema.

> Amounts in fungible assets are always confidential and the schema can put the requirement that this state must always be confidential the way it does for fungible asset.

### 

