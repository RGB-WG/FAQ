# Does anything need to happen in Lightning or Bitcoin to enable Lightning on RGB?

First, there is a difference between Lightning as a protocol and Lightning as an implementation of nodes. Lightning as a protocol doesn't need anything to be changed. Currently RGB can't be used in any existing Lightning nodes because of architectural limitations.

That's why we did our own implementation, which is called [LNP Node](https://github.com/LNP-BP/lnp-node) written in Rust. It doesn't per se depend on Bitcoin Core, but if you'd like to have RGB working together with Taproot in Lightning, then you will depend on Rust-bitcoin finalising Taproot support first.

