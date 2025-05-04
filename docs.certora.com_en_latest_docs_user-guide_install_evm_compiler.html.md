[ Certora Prover Documentation ![Logo](https://docs.certora.com/en/latest/_static/Certora_Logo_Black.svg) ](https://docs.certora.com/en/latest/index.html)
Contents
  * [Certora User’s Guide](https://docs.certora.com/en/latest/docs/user-guide/index.html)
    * [Installation](https://docs.certora.com/en/latest/docs/user-guide/install.html)
    * [Installing an EVM compiler and VS Code Extension](https://docs.certora.com/en/latest/docs/user-guide/install_evm_compiler.html)
      * [Installing Solidity compiler](https://docs.certora.com/en/latest/docs/user-guide/install_evm_compiler.html#installing-solidity-compiler)
        * [Using `solc-select`](https://docs.certora.com/en/latest/docs/user-guide/install_evm_compiler.html#using-solc-select)
        * [Download binaries](https://docs.certora.com/en/latest/docs/user-guide/install_evm_compiler.html#download-binaries)
      * [Installing the Vyper compiler](https://docs.certora.com/en/latest/docs/user-guide/install_evm_compiler.html#installing-the-vyper-compiler)
      * [Installing the Certora Verification Language LSP VS Code extension](https://docs.certora.com/en/latest/docs/user-guide/install_evm_compiler.html#installing-the-certora-verification-language-lsp-vs-code-extension)
    * [Tutorial and Workshops](https://docs.certora.com/en/latest/docs/user-guide/tutorials.html)
    * [Running the Certora Prover](https://docs.certora.com/en/latest/docs/user-guide/running.html)
    * [Designing Good Specifications](https://docs.certora.com/en/latest/docs/user-guide/properties/index.html)
    * [Producing Positive Examples](https://docs.certora.com/en/latest/docs/user-guide/satisfy.html)
    * [Invariants](https://docs.certora.com/en/latest/docs/user-guide/invariants.html)
    * [Parametric rules](https://docs.certora.com/en/latest/docs/user-guide/parametric.html)
    * [Tracking changes with ghosts and hooks](https://docs.certora.com/en/latest/docs/user-guide/ghosts.html)
    * [Specification Design Patterns](https://docs.certora.com/en/latest/docs/user-guide/patterns/index.html)
    * [Using Opcode Hooks](https://docs.certora.com/en/latest/docs/user-guide/opcodes.html)
    * [Working with Multiple Contracts](https://docs.certora.com/en/latest/docs/user-guide/multicontract/index.html)
    * [Managing Timeouts and Out of Memory Problems](https://docs.certora.com/en/latest/docs/user-guide/out-of-resources/index.html)
    * [Understanding gaps between high and low level code](https://docs.certora.com/en/latest/docs/user-guide/gaps.html)
    * [Checking Specifications](https://docs.certora.com/en/latest/docs/user-guide/checking.html)
    * [CI Configuration](https://docs.certora.com/en/latest/docs/user-guide/ci.html)
    * [Syntax Highlighting on GitHub](https://docs.certora.com/en/latest/docs/user-guide/github_highlighting.html)
    * [Glossary](https://docs.certora.com/en/latest/docs/user-guide/glossary.html)
  * [The Certora Verification Language](https://docs.certora.com/en/latest/docs/cvl/index.html)
  * [The Certora Prover](https://docs.certora.com/en/latest/docs/prover/index.html)
  * [Sunbeam: Verification for Soroban](https://docs.certora.com/en/latest/docs/sunbeam/index.html)
  * [The Certora Solana Prover](https://docs.certora.com/en/latest/docs/solana/index.html)
  * [Gambit: Mutation Generator for Solidity](https://docs.certora.com/en/latest/docs/gambit/index.html)


Additional information
  * [The Certora Equivalence Checker](https://docs.certora.com/en/latest/docs/equiv-check/index.html)
  * [Certora Technology White Paper](https://docs.certora.com/en/latest/docs/whitepaper/index.html)


  * [Index](https://docs.certora.com/en/latest/genindex.html)


[Certora Prover Documentation](https://docs.certora.com/en/latest/index.html)
  * [](https://docs.certora.com/en/latest/index.html)
  * [Certora User’s Guide](https://docs.certora.com/en/latest/docs/user-guide/index.html)
  * Installing an EVM compiler and VS Code Extension
  * [ View page source](https://docs.certora.com/en/latest/_sources/docs/user-guide/install_evm_compiler.md.txt)


# [Installing an EVM compiler and VS Code Extension](https://docs.certora.com/en/latest/docs/user-guide/install_evm_compiler.html#id1)[](https://docs.certora.com/en/latest/docs/user-guide/install_evm_compiler.html#installing-an-evm-compiler-and-vs-code-extension "Link to this heading")
After completing the steps in the [Certora Prover installation guide](https://docs.certora.com/en/latest/docs/user-guide/install.html#installation), a locally installed Solidity or Vyper compiler is required to verify EVM code. This page provides instructions for installing the necessary compiler and setting up the VS Code extension for syntax checking and highlighting.
Overview
  * [Installing an EVM compiler and VS Code Extension](https://docs.certora.com/en/latest/docs/user-guide/install_evm_compiler.html#installing-an-evm-compiler-and-vs-code-extension)
    * [Installing Solidity compiler](https://docs.certora.com/en/latest/docs/user-guide/install_evm_compiler.html#installing-solidity-compiler)
      * [Using `solc-select`](https://docs.certora.com/en/latest/docs/user-guide/install_evm_compiler.html#using-solc-select)
      * [Download binaries](https://docs.certora.com/en/latest/docs/user-guide/install_evm_compiler.html#download-binaries)
    * [Installing the Vyper compiler](https://docs.certora.com/en/latest/docs/user-guide/install_evm_compiler.html#installing-the-vyper-compiler)
    * [Installing the Certora Verification Language LSP VS Code extension](https://docs.certora.com/en/latest/docs/user-guide/install_evm_compiler.html#installing-the-certora-verification-language-lsp-vs-code-extension)


## [Installing Solidity compiler](https://docs.certora.com/en/latest/docs/user-guide/install_evm_compiler.html#id2)[](https://docs.certora.com/en/latest/docs/user-guide/install_evm_compiler.html#installing-solidity-compiler "Link to this heading")
There are two ways to install the Solidity compiler (`solc`): via [solc-select](https://github.com/crytic/solc-select) or downloading the binary directly and adding its folder to your `PATH`.
### [Using `solc-select`](https://docs.certora.com/en/latest/docs/user-guide/install_evm_compiler.html#id3)[](https://docs.certora.com/en/latest/docs/user-guide/install_evm_compiler.html#using-solc-select "Link to this heading")
solc-select instructions
  * Open a terminal and install `solc-select` via `pip`:
```
pipinstallsolc-select

```
Copy to clipboard
  * Download the required compiler version. For example, if you want to install version 0.8.0, run:
```
solc-selectinstall0.8.0

```
Copy to clipboard
  * Set `solc` to point to the required compiler version. For example:
```
solc-selectuse0.8.0

```
Copy to clipboard


### [Download binaries](https://docs.certora.com/en/latest/docs/user-guide/install_evm_compiler.html#id4)[](https://docs.certora.com/en/latest/docs/user-guide/install_evm_compiler.html#download-binaries "Link to this heading")
You can download the `solc` binaries directly from [Solidity’s release page on GitHub](https://github.com/ethereum/solidity/releases).
To run the Prover, you may find it useful to add the `solc` executables folder to your `PATH`. This way you will not need to provide the Prover with the full path to the `solc` executables folder every time.
Downloading binaries
macOS
  * Open a terminal and move to the `etc/paths.d` directory from root:
```
cd/etc/paths.d

```
Copy to clipboard
  * Use root privileges to create a file with an informative name such as `SolidityCertoraProver`, and open it with your favorite text editor:
```
sudonanoSolidityCertoraProver

```
Copy to clipboard
  * Write the full path to the directory that contains the `solc` executables:
```
/full/path/to/solc/executable/folder

```
Copy to clipboard
    * If needed, more than one path can be added on a single file, just separate the path with colon a (`:`).
  * Quit the terminal to load the new addition to `$PATH`, and reopen to check that the `$PATH` was updated correctly:
```
echo$PATH

```
Copy to clipboard


Linux
  * Open a terminal and make sure you’re in the home directory:
```
cd~

```
Copy to clipboard
  * open the .profile file with your favorite text editor:
```
nano.profile

```
Copy to clipboard
  * At the bottom of the file, add to `PATH="..."` the full path to the directory that contains the solc executables. To add an additional path just separate with a colon (`:`) :
```
PATH="$PATH:/full/path/to/solc/executable/folder"

```
Copy to clipboard
  * You can make sure that the file was modified correctly by opening it again with the text editor:
```
nano.profile

```
Copy to clipboard
  * Make sure to apply the changes to the `$PATH` by executing the script:
```
source.profile

```
Copy to clipboard


## [Installing the Vyper compiler](https://docs.certora.com/en/latest/docs/user-guide/install_evm_compiler.html#id5)[](https://docs.certora.com/en/latest/docs/user-guide/install_evm_compiler.html#installing-the-vyper-compiler "Link to this heading")
[Vyper](https://github.com/vyperlang/vyper) is an EVM compatible Pythonic smart contract language. Since the Certora Prover operates on the bytecode, it can be applied to any source-level language that compiles to EVM bytecode. We recommend to install Vyper either from PyPi (i.e., `pip install vyper`) or to get a binary executable for the desired version.
## [Installing the Certora Verification Language LSP VS Code extension](https://docs.certora.com/en/latest/docs/user-guide/install_evm_compiler.html#id6)[](https://docs.certora.com/en/latest/docs/user-guide/install_evm_compiler.html#installing-the-certora-verification-language-lsp-vs-code-extension "Link to this heading")
All users of the Certora Prover can access the tool using the command line interface, or [CLI](https://docs.certora.com/en/latest/docs/prover/cli/index.html). Those who use Microsoft’s Visual Studio Code editor (VS Code) also have the option of using the [Certora Verification Language LSP](https://marketplace.visualstudio.com/items?itemName=Certora.evmspec-lsp). This will provide both syntax checking and syntax highlighting for CVL.
Congratulations! You have just completed Certora Prover’s installation and setup.
Caution
We strongly recommend trying the tool on basic examples to verify correct installation. See [Running the Certora Prover](https://docs.certora.com/en/latest/docs/user-guide/running.html) for a detailed walkthrough.
[ Previous](https://docs.certora.com/en/latest/docs/user-guide/install.html "Installation") [Next ](https://docs.certora.com/en/latest/docs/user-guide/tutorials.html "Tutorial and Workshops")
© Copyright 2025, Certora, Inc.
Built with [Sphinx](https://www.sphinx-doc.org/) using a [theme](https://github.com/readthedocs/sphinx_rtd_theme) provided by [Read the Docs](https://readthedocs.org). 
