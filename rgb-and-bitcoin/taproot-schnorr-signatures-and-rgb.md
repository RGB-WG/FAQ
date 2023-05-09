# Taproot, Schnorr signatures and RGB

RGB functionality is not dependent on Taproot or Schnorr signatures deployment, though is already compatible with them.

RGB will benefit from Taproot, but it’s benefit is purely bitcoin-based benefit \(i.e. indirect\). Better multisigs, adapter-based signatures protocols, LN improvements \(PTLCs\).

Internally inside RGB there is nothing to sign \(so Schnorr's change nothing internally\) and no use for Bitcoin script \(so no use from the new Tapscript\).  

Taproot and Schnorr signatures support is held nearly automatically from the v0.3 Release of the LNP/BP Core Library. Currently we are waiting for the corresponding release of Rust Bitcoin supporting them \(we are already using the code internally but we can't put it in the release before it's released by Rust Bitcoin\) and for Bitcoin Core release with same support. With that, RGB will be one of the first projects based on Bitcoin, that would support Taproot and Schnorr signatures from day 1.   

Inside RGB Schnorr signatures are not used, we are using Bitcoin layer for that, but we will be able to assign and commit to Taproot outputs and we'll also be able to use Taproot outputs as a destination for asset transfers.
