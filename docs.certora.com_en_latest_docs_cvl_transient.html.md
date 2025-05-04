[ Certora Prover Documentation ![Logo](https://docs.certora.com/en/latest/_static/Certora_Logo_Black.svg) ](https://docs.certora.com/en/latest/index.html)
Contents
  * [Certora User’s Guide](https://docs.certora.com/en/latest/docs/user-guide/index.html)
  * [The Certora Verification Language](https://docs.certora.com/en/latest/docs/cvl/index.html)
    * [Specification Files](https://docs.certora.com/en/latest/docs/cvl/overview.html)
    * [Basic Syntax](https://docs.certora.com/en/latest/docs/cvl/basics.html)
    * [Types](https://docs.certora.com/en/latest/docs/cvl/types.html)
    * [Expressions](https://docs.certora.com/en/latest/docs/cvl/expr.html)
    * [Statements](https://docs.certora.com/en/latest/docs/cvl/statements.html)
    * [Import and Use Statements](https://docs.certora.com/en/latest/docs/cvl/imports.html)
    * [Using Statements](https://docs.certora.com/en/latest/docs/cvl/using.html)
    * [The Methods Block](https://docs.certora.com/en/latest/docs/cvl/methods.html)
    * [Rules](https://docs.certora.com/en/latest/docs/cvl/rules.html)
    * [Built-in Rules](https://docs.certora.com/en/latest/docs/cvl/builtin.html)
    * [Functions](https://docs.certora.com/en/latest/docs/cvl/functions.html)
    * [Invariants](https://docs.certora.com/en/latest/docs/cvl/invariants.html)
    * [Uninterpreted Sorts](https://docs.certora.com/en/latest/docs/cvl/sorts.html)
    * [Ghosts](https://docs.certora.com/en/latest/docs/cvl/ghosts.html)
    * [Definitions](https://docs.certora.com/en/latest/docs/cvl/defs.html)
    * [Hooks](https://docs.certora.com/en/latest/docs/cvl/hooks.html)
    * [Transient Storage](https://docs.certora.com/en/latest/docs/cvl/transient.html)
    * [Foundry Integration (Alpha)](https://docs.certora.com/en/latest/docs/cvl/foundry-integration.html)
    * [Changes Since CVL 1](https://docs.certora.com/en/latest/docs/cvl/index.html#changes-since-cvl-1)
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
  * [The Certora Verification Language](https://docs.certora.com/en/latest/docs/cvl/index.html)
  * Transient Storage
  * [ View page source](https://docs.certora.com/en/latest/_sources/docs/cvl/transient.md.txt)


# Transient Storage[](https://docs.certora.com/en/latest/docs/cvl/transient.html#transient-storage "Link to this heading")
[Transient storage in EVM contracts](https://eips.ethereum.org/EIPS/eip-1153) is a contract-specific key-value mapping that persists throughout a single EVM transaction. Therefore, a contract being invoked several times during a single transaction (like in reentrancy), will share the same transient storage. When a transaction completes, transient storage is nullified.
The Certora Prover currently models the transient storage as follows:
  * Each rule is assumed to run in an already active transaction, and does not assume the contracts’ transient storage is nullified at the beginning of the rule.
  * Different calls made from CVL to different contracts do not assume a new transaction starts. Similar to regular (persistent) storage, the previous transient storage saved by the previous contract call is used for the next call.
  * Reverts and havoc impact the transient storage in the same way they impact the regular storage.
  * In [invariants](https://docs.certora.com/en/latest/docs/cvl/invariants.html#invariants), only the constructor check (base-step) of the invariant assumes a nullified transient storage for the contract.
  * The usage of `at` [syntax](https://docs.certora.com/en/latest/docs/cvl/types.html#storage-type) also resets the transient storage to the values represented by the mentioned `storage` variable.
  * Different environment variables passed to calls have no effect on the transient storage. In particular, one may wish to use different starting `storage` states for calls that receive environment variables with different values of `tx.origin`.


[ Previous](https://docs.certora.com/en/latest/docs/cvl/hooks.html "Hooks") [Next ](https://docs.certora.com/en/latest/docs/cvl/foundry-integration.html "Foundry Integration \(Alpha\)")
© Copyright 2025, Certora, Inc.
Built with [Sphinx](https://www.sphinx-doc.org/) using a [theme](https://github.com/readthedocs/sphinx_rtd_theme) provided by [Read the Docs](https://readthedocs.org). 
