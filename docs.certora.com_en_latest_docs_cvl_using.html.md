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
      * [Examples](https://docs.certora.com/en/latest/docs/cvl/using.html#examples)
      * [Syntax](https://docs.certora.com/en/latest/docs/cvl/using.html#syntax)
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
  * Using Statements
  * [ View page source](https://docs.certora.com/en/latest/_sources/docs/cvl/using.md.txt)


# [Using Statements](https://docs.certora.com/en/latest/docs/cvl/using.html#id1)[](https://docs.certora.com/en/latest/docs/cvl/using.html#using-statements "Link to this heading")
The `using` statement introduces a variable that can be used to call methods on contracts other than the main contract being verified.
Contents
  * [Using Statements](https://docs.certora.com/en/latest/docs/cvl/using.html#using-statements)
    * [Examples](https://docs.certora.com/en/latest/docs/cvl/using.html#examples)
    * [Syntax](https://docs.certora.com/en/latest/docs/cvl/using.html#syntax)


## [Examples](https://docs.certora.com/en/latest/docs/cvl/using.html#id2)[](https://docs.certora.com/en/latest/docs/cvl/using.html#examples "Link to this heading")
  * [Accessing additional contracts from CVL](https://docs.certora.com/en/latest/docs/user-guide/multicontract/index.html#using-example)
  * [An example for `using`](https://github.com/Certora/Examples/blob/14668d39a6ddc67af349bc5b82f73db73349ef18/CVLByExample/LiquidityPool/certora/specs/pool_link.spec#L14)


## [Syntax](https://docs.certora.com/en/latest/docs/cvl/using.html#id3)[](https://docs.certora.com/en/latest/docs/cvl/using.html#syntax "Link to this heading")
The syntax for `using` statements is given by the following [EBNF grammar](https://docs.certora.com/en/latest/docs/cvl/overview.html#ebnf-syntax):
```
using ::= "using" id "as" id

```
Copy to clipboard
See [Identifiers](https://docs.certora.com/en/latest/docs/cvl/basics.html#identifiers) for the `id` production.
[ Previous](https://docs.certora.com/en/latest/docs/cvl/imports.html "Import and Use Statements") [Next ](https://docs.certora.com/en/latest/docs/cvl/methods.html "The Methods Block")
© Copyright 2025, Certora, Inc.
Built with [Sphinx](https://www.sphinx-doc.org/) using a [theme](https://github.com/readthedocs/sphinx_rtd_theme) provided by [Read the Docs](https://readthedocs.org). 
