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
      * [Tracking Sums](https://docs.certora.com/en/latest/docs/user-guide/patterns/sums.html)
      * [Partially Parametric Rules](https://docs.certora.com/en/latest/docs/user-guide/patterns/partial-apply.html)
      * [Listing Safe Assumptions](https://docs.certora.com/en/latest/docs/user-guide/patterns/safe-assum.html)
      * [Require Invariants: Proving inter-dependent invariants](https://docs.certora.com/en/latest/docs/user-guide/patterns/require-invariants.html)
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
  * Specification Design Patterns
  * [ View page source](https://docs.certora.com/en/latest/_sources/docs/user-guide/patterns/index.md.txt)


# Specification Design Patterns[](https://docs.certora.com/en/latest/docs/user-guide/patterns/index.html#specification-design-patterns "Link to this heading")
Certain patterns often occur in specification files. This chapter describes some of these patterns.
  * [Tracking Sums](https://docs.certora.com/en/latest/docs/user-guide/patterns/sums.html)
    * [Enforcing Sum of Two Balances Constraint](https://docs.certora.com/en/latest/docs/user-guide/patterns/sums.html#enforcing-sum-of-two-balances-constraint)
    * [Maintaining Equality Between Sum of Balances and Total Supply](https://docs.certora.com/en/latest/docs/user-guide/patterns/sums.html#maintaining-equality-between-sum-of-balances-and-total-supply)
  * [Partially Parametric Rules](https://docs.certora.com/en/latest/docs/user-guide/patterns/partial-apply.html)
  * [Listing Safe Assumptions](https://docs.certora.com/en/latest/docs/user-guide/patterns/safe-assum.html)
    * [Context:](https://docs.certora.com/en/latest/docs/user-guide/patterns/safe-assum.html#context)
    * [Importance of Listing Safe Assumptions:](https://docs.certora.com/en/latest/docs/user-guide/patterns/safe-assum.html#importance-of-listing-safe-assumptions)
  * [Require Invariants: Proving inter-dependent invariants](https://docs.certora.com/en/latest/docs/user-guide/patterns/require-invariants.html)
    * [Importance of Require Invariants:](https://docs.certora.com/en/latest/docs/user-guide/patterns/require-invariants.html#importance-of-require-invariants)


[ Previous](https://docs.certora.com/en/latest/docs/user-guide/ghosts.html "Tracking changes with ghosts and hooks") [Next ](https://docs.certora.com/en/latest/docs/user-guide/patterns/sums.html "Tracking Sums")
© Copyright 2025, Certora, Inc.
Built with [Sphinx](https://www.sphinx-doc.org/) using a [theme](https://github.com/readthedocs/sphinx_rtd_theme) provided by [Read the Docs](https://readthedocs.org). 
