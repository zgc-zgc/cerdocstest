[ Certora Prover Documentation ![Logo](https://docs.certora.com/en/latest/_static/Certora_Logo_Black.svg) ](https://docs.certora.com/en/latest/index.html)
Contents
  * [Certora User’s Guide](https://docs.certora.com/en/latest/docs/user-guide/index.html)
  * [The Certora Verification Language](https://docs.certora.com/en/latest/docs/cvl/index.html)
  * [The Certora Prover](https://docs.certora.com/en/latest/docs/prover/index.html)
  * [Sunbeam: Verification for Soroban](https://docs.certora.com/en/latest/docs/sunbeam/index.html)
    * [Installation](https://docs.certora.com/en/latest/docs/sunbeam/installation.html)
      * [Installing Sunbeam](https://docs.certora.com/en/latest/docs/sunbeam/installation.html#installing-sunbeam)
      * [Rust and Stellar CLI Setup](https://docs.certora.com/en/latest/docs/sunbeam/installation.html#rust-and-stellar-cli-setup)
    * [User Guide For Sunbeam](https://docs.certora.com/en/latest/docs/sunbeam/usage.html)
    * [Troubleshooting](https://docs.certora.com/en/latest/docs/sunbeam/troubleshooting.html)
  * [The Certora Solana Prover](https://docs.certora.com/en/latest/docs/solana/index.html)
  * [Gambit: Mutation Generator for Solidity](https://docs.certora.com/en/latest/docs/gambit/index.html)


Additional information
  * [The Certora Equivalence Checker](https://docs.certora.com/en/latest/docs/equiv-check/index.html)
  * [Certora Technology White Paper](https://docs.certora.com/en/latest/docs/whitepaper/index.html)


  * [Index](https://docs.certora.com/en/latest/genindex.html)


[Certora Prover Documentation](https://docs.certora.com/en/latest/index.html)
  * [](https://docs.certora.com/en/latest/index.html)
  * [Sunbeam: Verification for Soroban](https://docs.certora.com/en/latest/docs/sunbeam/index.html)
  * Installation
  * [ View page source](https://docs.certora.com/en/latest/_sources/docs/sunbeam/installation.rst.txt)


# Installation[](https://docs.certora.com/en/latest/docs/sunbeam/installation.html#installation "Link to this heading")
Attention
These instructions are for Linux and macOS systems. Windows users should use [WSL](https://learn.microsoft.com//install) and follow the Linux installation instructions.
## Installing Sunbeam[](https://docs.certora.com/en/latest/docs/sunbeam/installation.html#installing-sunbeam "Link to this heading")
  1. First, we will need to install the Sunbeam Prover. For that, please visit [Certora.com](https://www.certora.com/) and sign up for a free account at [Certora sign-up page](https://www.certora.com/signup).
  2. You will receive an email with a temporary password and a _Certora Key_. Use the password to login to Certora following the link in the email.
  3. Next, install Python3.8.16 or newer on your machine. If you already have Python3 installed, you can check the version: `python3 --version`. If you need to upgrade, follow these instructions in the [Python Beginners Guide](https://wiki.python.org/moin/BeginnersGuide/Download).
  4. Next, install Java. Check your Java version: `java -version`. If the version is < 11, download and install Java version 11 or later from [Oracle](https://www.oracle.com/java/technologies/downloads/).
  5. Then, install the Certora Prover: `pip3 install certora-cli-beta`.
Tip
Always use a Python virtual environment when installing packages.
  6. Recall that you received a _Certora Key_ in your email (Step 2). Use the key to set a temporary environment variable like so `export CERTORAKEY=<personal_access_key>`. Alternatively, to store the key in your profile see [Step 3 of the Prover installation](https://docs.certora.com/en/latest/docs/user-guide/install.html#installation-step-3).


## Rust and Stellar CLI Setup[](https://docs.certora.com/en/latest/docs/sunbeam/installation.html#rust-and-stellar-cli-setup "Link to this heading")
  1. We recommend installing Rust as on the [official Rust website](https://www.rust-lang.org/tools/install): `curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh`
  2. Next, install the WASM target like so: `rustup target add wasm32-unknown-unknown`
  3. We recommend setting up the Stellar CLI as shown [here](https://developers.stellar.org/docs/build/smart-contracts/getting-started/setup#install-the-stellar-cli).
  4. We also recommend installing the [wabt](https://github.com/WebAssembly/wabt) toolkit. `wasm2wat` is a useful tool for converting the WASM bytecode to a human readable format. Ensure that `wasm2wat` is executable as a command from your terminal. You will have to add `wabt/bin` to your `PATH` by running `export PATH=~/path/to/wabt/bin:$PATH`.
  5. Install just like so: `cargo install just`.
  6. Finally, install `rustfilt` like so: `cargo install rustfilt`.


With that, you should be all set for using Certora Sunbeam. Congratulations!
To learn more about using Certora Sunbeam, check out the [Sunbeam Tutorials](https://certora-sunbeam-tutorials.readthedocs-hosted.com/en/latest/).
[ Previous](https://docs.certora.com/en/latest/docs/sunbeam/index.html "Sunbeam: Verification for Soroban") [Next ](https://docs.certora.com/en/latest/docs/sunbeam/usage.html "User Guide For Sunbeam")
© Copyright 2025, Certora, Inc.
Built with [Sphinx](https://www.sphinx-doc.org/) using a [theme](https://github.com/readthedocs/sphinx_rtd_theme) provided by [Read the Docs](https://readthedocs.org). 
