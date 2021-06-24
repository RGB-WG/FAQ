# Is RGB a new blockchain?

No.  
  
Even taking into account the fact that RGB is based on bitcoin transaction graph \(which, in turn, is based on bitcoin timechain\), RGB itself is not a 'blockchain'. It’s a form of a DAG, where you don’t have the data on a complete state of the network, ever.  
From the moment you create a smart contract and transfer the state to some other party, you have neither the control over that state \(only the new state owner has it\), nor the information on how that state actually evolved.

For example, **as an asset issuer you will never know, who are the owners of your issued assets**. When you assign the state of the asset to some bitcoin transaction output, you don’t know which output it is, because the party that receives that data, provides you with the information about transaction output, blinded with random data. Taking into account that you don’t know that random data used for blinding, you can’t say which output you are paying to or transferring some rights to.

This is very different from the blockchain-based smart-contract paradigm, where you store the complete history of the blockchain. This is why we say that RGB is a **partial-state smart-contract system** \(the first of its kind\). It is still globally consistent, not contradicting the fact of this state partiality, due to the usage of single-use seals that enable reaching consensus on state validation.  
As a user, whenever I receive some state into my ownership and even without knowing the whole state of the system, I am still able to validate:   
- that this state of the system was not faked  
- that it has been uniquely committed  
- that there were no double spending events \(even up to genesis of the asset issuer\).

**Social consensus** on the client-side validation rules also makes it possible to be sure that every further owner of the asset will apply the same validation rules as I do. How? Every asset/state validation rules are defined by Schema at genesis level, meaning that every further owner of the asset still uses the same Schema to validate the history against. Thus, here **Schema is actually the means to guarantee the social consensus on the validation.**

