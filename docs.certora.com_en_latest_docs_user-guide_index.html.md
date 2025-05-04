[ Certora Prover Documentation ![Logo](https://docs.certora.com/en/latest/_static/Certora_Logo_Black.svg) ](https://docs.certora.com/en/latest/index.html)
Contents
  * [Certora User’s Guide](https://docs.certora.com/en/latest/docs/user-guide/index.html)
    * [Installation](https://docs.certora.com/en/latest/docs/user-guide/install.html)
    * [Installing an EVM compiler and VS Code Extension](https://docs.certora.com/en/latest/docs/user-guide/install_evm_compiler.html)
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
  * Certora User’s Guide
  * [ View page source](https://docs.certora.com/en/latest/_sources/docs/user-guide/index.md.txt)


# Certora User’s Guide[](https://docs.certora.com/en/latest/docs/user-guide/index.html#certora-user-s-guide "Link to this heading")
This User Guide contains information about the Certora Prover and Certora Verification Language. It is intended to explain how to use the Prover to verify smart contracts. It is organized by topic and focuses on the most useful features instead of including comprehensive details. For details, see the [The Certora Verification Language](https://docs.certora.com/en/latest/docs/cvl/index.html).
The Certora Prover is based on well-studied techniques from the formal verification community. _**Specifications**_ define a set of rules that call into the contract under analysis and make various assertions about its behavior. Together with the contract under analysis, these rules are compiled to a logical formula called a [verification condition](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-verification-condition), which is then proved or disproved by an [SMT solver](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-SMT-solver). If the rule is disproved, the solver also provides a concrete test case demonstrating the violation.
The rules of the specification play a crucial role in the analysis. Without adequate rules, only very basic properties can be checked (e.g., no assertions in the contract itself are violated). To effectively use Certora Prover, users must write rules that describe the high-level properties they wish to verify on their contracts. This user manual describes the different features of the specification language. Another primary goal is to help the reader learn how to think about and write high-level properties.
  * [Installation](https://docs.certora.com/en/latest/docs/user-guide/install.html)
  * [Installing an EVM compiler and VS Code Extension](https://docs.certora.com/en/latest/docs/user-guide/install_evm_compiler.html)
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


[ Previous](https://docs.certora.com/en/latest/index.html "Certora Prover Documentation") [Next ](https://docs.certora.com/en/latest/docs/user-guide/install.html "Installation")
© Copyright 2025, Certora, Inc.
Built with [Sphinx](https://www.sphinx-doc.org/) using a [theme](https://github.com/readthedocs/sphinx_rtd_theme) provided by [Read the Docs](https://readthedocs.org). 
