# How is safety reached in RGB?

1.Most part of RGB is relying on Bitcoin and Lightning safety on L1.  
2.State isolation: state is isolated between different smart contracts and they can interact only through special protocols \(Spectrum\) inside channels. 

> If you have two assets issued by different issuers, these assets don't interact directly, their data is never mixed and they cannot be cross-validated.
>
> There is a way to exchange one asset for another one using _Spectrum_ protocol, but it was created as a layer on top of Lightning Network and it is not related to RGB itself. Spectrum uses LN cooperation between different transaction graphs. When you make a multihop payment with Lightning, one transaction graph of one state channel is not directly affected by the data from the transaction graph of the other channel, they all communicate through the messaging P2P onion routing protocol. Spectrum works the same way for RGB in this regard.

3.Formal verification: contract properties can be proven with formal models.

