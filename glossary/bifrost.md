# Bifrost

**Bifrost** is an extension to the LN peer-to-peer protocol, which would allow you to send client-side validation data using the LN itself, make RGB-20 payments over the LN and unable more advanced things in the future: DEX, decentralized storage, DeFi, advanced smart contracts etc.   
  
To emphasise once again, Bifrost is not a part of RGB, it's an additional protocol that makes it possible for mobile RGB wallets to work on LN. One of the features of this protocol can be imagined as an improved version of Watchtowers currently present in LN and not breaking the backwards compatibility.  
  
From the programming standpoint, unlike RGB or client-side validation technologies, Bifrost is much more flexible, meaning that we can start with rolling out a simple version of it \(a few methods are already written in code, so we just need to extend it a bit more to cover the use case of sending over the client-side validated data\) and then update it with new functionality further down the road, potentially maybe even becoming a part of LN itself.  
  
From user perspective Bifrost is needed to be finalized before the RGB release both as a protocol and as a code that can be put into mobile wallets  thus also showcasing how RGB over LN transfers can be used from a mobile device.

From a more technical point of view, Bifrost also acts as a public key-value storage for keeping information on client-validated data in encrypted way. You can think about it as a generalization of Watchtower concept, which will allow any node to implement the following functionality:

* Store & propagate information about RGB schema and assets \(enabling RGB P2P infrastructure\)
* Store public/disclosed parts of RGB history from issuers \(like the ones related to pruning\)
* Store encrypted information about RGB payments \(consignments\) - for a fee \(“RGB watchtower”\)
* Run DEX on LN with RGB
* Can be used by RGB users to receive payments when they are offline \(i.e. it will store the data for them, in encrypted form\)
* It will have its own API \(RPC\), which will be done with LNP

The original idea was to do it as a standalone node with the same name, however since all of this functionality will be part of lightning P2P protocols, it will require LN node next to it anyway, so for now we are planning to just add “Bifrost protocol support” to the existing LNP Node as a compilation flag/extension/plugin - so other nodes will be also able to add this features later. It is not the same as RGB node, because it is a public service \(while RGB is a private thing keeping your **stash** unencrypted\).

So, Bifrost to RGB is something like Watchtowers are to LN node \(but more functional\). As for the normal lightning watchtowers, the BOLT-12 protocol draft is there, so it will not be a part of Bitfrost protocol spec - but will also be implemented in the LNP Node.

