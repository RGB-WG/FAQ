# Bifrost

**Bifrost** is a server that acts as a public key-value storage for keeping information on client-validated data in encrypted way. You can think about it as a generalization of Watchtower concept, as a sort of add-on protocol to the lightning network p2p one, which will allow any node to implement the following functionality:

* Store & propagate information about RGB schema and assets \(enabling RGB P2P infrastructure\)
* Store public/disclosed parts of RGB history from issuers \(like the ones related to pruning\)
* Store encrypted information about RGB payments \(consignments\) - for a fee \(“RGB watchtower”\)
* Run DEX on LN with RGB
* Can be used by RGB users to receive payments when they are offline \(i.e. it will store the data for them, in encrypted form\)
* It will have its own API \(RPC\), which will be done with LNP

The original idea was to do it as a standalone node with the same name, however since all of this functionality will be part of lightning P2P protocols, it will require LN node next to it anyway, so for now we are planning to just add “Bifrost protocol support” to the existing LNP Node as a compilation flag/extension/plugin - so other nodes will be also able to add this features later. It is not the same as RGB node, because it is a public service \(while RGB is a private thing keeping your **stash** unencrypted\).

So, Bifrost to RGB is something like Watchtowers are to LN node \(but more functional\). As for the normal lightning watchtowers, the BOLT-12 protocol draft is there, so it will not be a part of Bitfrost protocol spec - but will also be implemented in the LNP Node.

