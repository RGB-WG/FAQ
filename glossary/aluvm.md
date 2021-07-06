# AluVM

**AluVM** - \(algorithmic logic unit VM\) is a pure functional RISC virtual machine designed for deterministic portable computing tasks. It was designed & implemented by [Dr Maxim Orlovsky](https://dr.orlovsky.ch/) at [Pandora Core AG](https://pandoracore.com/) and maintained by [LNP/BP Standards Association](https://lnp-bp.org/).

### Why do we need a virtual machine?

Without a virtual machine one would not be able to develop advanced forms of smart contracts which are critically important for use cases like creating algorithmical stablecoins on RGB, recreating liquidity pools, DeFi etc. While these use cases are absolutely possible from the client-side validation perspective, without a virtual machine one would be restricted by very simple embedded procedures of validating the client-side data and the only way of changing that would be to release a new protocol \(which would be incompatible with the previous one\).

Unlike many other virtual machines, AluVM is register-based and does not allow random memory access. This makes AluVM perfectly suited for such domains as smart contracts, remote code execution, distributed & edge computing because of AluVM determinism combined with unprecedented robustness and possibility of formal code analysis.

### Key characteristics

* Exceptionless
* Portability
* Sandboxing
* Security
* Extensibility

Instruction set architecture \(ISA\) supports extensions, which allows creation of runtime environments targeting different use cases.

AluVM is a pure functional register-based highly deterministic & exception-less instruction set architecture \(ISA\) and virtual machine \(VM\) without random memory access, capable of performing arithmetic operations, including operations on elliptic curves. The AluVM ISA can be extended by the environment running the virtual machine \(host environment\), providing ability to load data to the VM registers and support application-specific instructions \(like SIMD\).

The main purpose for ALuVM is to be used in distributed systems whether robustness, platform-independent determinism are more important than the speed of computation. The main area of AluVM applications \(using appropriate ISA extensions\) is blockchain environments, consensus-critical computations, edge computing, multiparty computing \(including deterministic machine learning\), client-side-validation, sandboxed Internet2 computing and genetic algorithms.

### History

* The need for AluVM recognized as a part of RGB project on March, the 24 & 31st, 2021 \(see the [YouTube video](https://www.youtube.com/watch?v=JmKNyOMv68I) from the [developers call](https://www.rgbfaq.com/community/developer-calls#2021-03-31)\)
* Concept was presented on 19th of May 2021 \([check the recoding](https://youtu.be/Mma0oyiVbSE)\)
* v0.1 release of Rust AluVM implementation on the 28th of May 2021 \([ISA & API docs](https://docs.rs/aluvm/0.1.0/alure/)\)
* v0.2 release with multiple enhancements on the 9 Jun 2021

  \([ISA & API docs](https://docs.rs/aluvm/0.2.1/aluvm/)\) – see presentation

  on [Youtube](https://www.youtube.com/watch?v=brfWta7XXFQ) or read [slides](https://github.com/LNP-BP/presentations/blob/master/Presentation%20slides/RGB%20VM%20%26%20scripting.pdf)

### Comparison of AluVM and other VMs & scripting solutions

![](../.gitbook/assets/comparison.png)

### For more information check:

* documentation [in Rust crates](https://docs.rs/aluvm/0.3.0/aluvm/)
* Rust reference implementation [repository](https://github.com/internet2-org/rust-aluvm) on GitHub
* YouTube videos [one](https://www.youtube.com/watch?v=brfWta7XXFQ) and [two](https://www.youtube.com/watch?v=Mma0oyiVbSE)
* Presentation slides [one](https://github.com/LNP-BP/presentations/blob/master/Presentation%20slides/AluVM.pdf) and [two](https://github.com/LNP-BP/presentations/blob/master/Presentation%20slides/RGB%20VM%20%26%20scripting.pdf)

