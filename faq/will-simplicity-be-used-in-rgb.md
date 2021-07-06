# Will Simplicity be used in RGB?

The initial development plan was to use Simplicity in RGB, thus we did everything to make it compatible from day 1. However, unfortunately, looking at the speed of the progress of its development, we understood that we couldn't rely on it because no one is able to say when or even if it's going to be released, thus - if it's going to be included in the RGB release that is being prepared now.   
  
When we understood that there is no decent time table on the Simplicity release, we started anaylising the alternatives \(WASM, EVM \(as a joke\), IELE etc\) but eventually understood that we have no other option than to develop our own virtual machine that will be used by RGB instead of Simplicity. This is how we made a decision to create **AluVM** - pure functional, highly-portable Rust-based virtual machine for client-side-validated smart contracts \(RGB\),  Lightning Network, deterministic distributed & edge computing. More details on it can be found in the corresponding [repository](https://github.com/internet2-org/rust-aluvm), documentation is located at [Rust crates.](https://docs.rs/aluvm/0.3.0/aluvm/)

