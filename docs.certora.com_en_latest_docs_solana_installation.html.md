[ Certora Prover Documentation ![Logo](https://docs.certora.com/en/latest/_static/Certora_Logo_Black.svg) ](https://docs.certora.com/en/latest/index.html)
Contents
  * [Certora User’s Guide](https://docs.certora.com/en/latest/docs/user-guide/index.html)
  * [The Certora Verification Language](https://docs.certora.com/en/latest/docs/cvl/index.html)
  * [The Certora Prover](https://docs.certora.com/en/latest/docs/prover/index.html)
  * [Sunbeam: Verification for Soroban](https://docs.certora.com/en/latest/docs/sunbeam/index.html)
  * [The Certora Solana Prover](https://docs.certora.com/en/latest/docs/solana/index.html)
    * [Get started with the Solana Certora Prover](https://docs.certora.com/en/latest/docs/solana/installation.html)
      * [Installing Solana Certora Prover](https://docs.certora.com/en/latest/docs/solana/installation.html#installing-solana-certora-prover)
      * [Rust, Solana, and Certora Platform Tools Setup](https://docs.certora.com/en/latest/docs/solana/installation.html#rust-solana-and-certora-platform-tools-setup)
    * [Using the Solana Certora Prover](https://docs.certora.com/en/latest/docs/solana/usage.html)
    * [Certora Verification Language for Rust (CVLR)](https://docs.certora.com/en/latest/docs/solana/speclanguage.html)
    * [Solana-Specific Options / CLI Flags](https://docs.certora.com/en/latest/docs/solana/options.html)
    * [Understanding Prover Output for Solana Programs](https://docs.certora.com/en/latest/docs/solana/output.html)
    * [Rule Sanity Checks (Solana)](https://docs.certora.com/en/latest/docs/solana/sanity.html)
    * [Troubleshooting](https://docs.certora.com/en/latest/docs/solana/troubleshooting.html)
  * [Gambit: Mutation Generator for Solidity](https://docs.certora.com/en/latest/docs/gambit/index.html)


Additional information
  * [The Certora Equivalence Checker](https://docs.certora.com/en/latest/docs/equiv-check/index.html)
  * [Certora Technology White Paper](https://docs.certora.com/en/latest/docs/whitepaper/index.html)


  * [Index](https://docs.certora.com/en/latest/genindex.html)


[Certora Prover Documentation](https://docs.certora.com/en/latest/index.html)
  * [](https://docs.certora.com/en/latest/index.html)
  * [The Certora Solana Prover](https://docs.certora.com/en/latest/docs/solana/index.html)
  * Get started with the Solana Certora Prover
  * [ View page source](https://docs.certora.com/en/latest/_sources/docs/solana/installation.md.txt)


# Get started with the Solana Certora Prover[](https://docs.certora.com/en/latest/docs/solana/installation.html#get-started-with-the-solana-certora-prover "Link to this heading")
## Installing Solana Certora Prover[](https://docs.certora.com/en/latest/docs/solana/installation.html#installing-solana-certora-prover "Link to this heading")
Begin by following the steps in the [Certora Prover installation guide](https://docs.certora.com/en/latest/docs/user-guide/install.html#installation).
## Rust, Solana, and Certora Platform Tools Setup[](https://docs.certora.com/en/latest/docs/solana/installation.html#rust-solana-and-certora-platform-tools-setup "Link to this heading")
  1. We recommend installing Rust as on the official [Rust website](https://www.rust-lang.org/tools/install):
`curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh`
It is useful to have Rust versions 1.75, 1.79, and 1.81 or above installed.
```
rustup toolchain install 1.79
rustup toolchain install 1.75
rustup toolchain install 1.81

```
Copy to clipboard
  2. Install `certora-sbf` cargo sub-command
`cargo +1.81 install cargo-certora-sbf`
Note that a minimal version of Rust required to install `certora-sbf` is v1.81.
  3. Test the installation by using `certora-sbf` to download and install Certora Platform Tools
`cargo certora-sbf --no-build`
  4. It is strongly recommended to install VSCode and the rust-analyzer extension.


Congratulations! You have just completed Solana Certora Prover’s installation and setup.
Caution
We strongly recommend trying the tool on basic examples to verify correct installation. See [Using the Solana Certora Prover](https://docs.certora.com/en/latest/docs/solana/usage.html#solana-usage) for a detailed walkthrough.
[ Previous](https://docs.certora.com/en/latest/docs/solana/index.html "The Certora Solana Prover") [Next ](https://docs.certora.com/en/latest/docs/solana/usage.html "Using the Solana Certora Prover")
© Copyright 2025, Certora, Inc.
Built with [Sphinx](https://www.sphinx-doc.org/) using a [theme](https://github.com/readthedocs/sphinx_rtd_theme) provided by [Read the Docs](https://readthedocs.org). 
