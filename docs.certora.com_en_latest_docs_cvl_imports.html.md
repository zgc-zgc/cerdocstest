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
      * [Examples](https://docs.certora.com/en/latest/docs/cvl/imports.html#examples)
      * [Syntax](https://docs.certora.com/en/latest/docs/cvl/imports.html#syntax)
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
  * Import and Use Statements
  * [ View page source](https://docs.certora.com/en/latest/_sources/docs/cvl/imports.md.txt)


# Import and Use Statements[](https://docs.certora.com/en/latest/docs/cvl/imports.html#import-and-use-statements "Link to this heading")
Contents of additional spec files can be imported using the `import` command. Some parts of the imported spec files are implicitly included in the importing spec file, while others such as rules and invariants must be explicitly `use`d. Functions, definitions, filters, and preserved blocks of the imported spec can be overridden by the importing spec. If a spec defines a function and uses it (e.g. in a rule or function), and another spec imports it and overrides it, uses in the imported spec use the new version.
## Examples[](https://docs.certora.com/en/latest/docs/cvl/imports.html#examples "Link to this heading")
  * [Example for `import`](https://github.com/Certora/Examples/blob/be09cf32c55e39f5f5aa8cba1431f9e519b52365/CVLByExample/import/certora/specs/sub.spec#L1)
  * [`use rule`](https://github.com/Certora/Examples/blob/61ac29b1128c68aff7e8d1e77bc80bfcbd3528d6/CVLByExample/import/certora/specs/sub.spec#L24)
  * [`use rule` with filters](https://github.com/Certora/Examples/blob/be09cf32c55e39f5f5aa8cba1431f9e519b52365/CVLByExample/import/certora/specs/sub.spec#L3)
  * [overriding imported filters](https://github.com/Certora/Examples/blob/be09cf32c55e39f5f5aa8cba1431f9e519b52365/CVLByExample/import/certora/specs/sub.spec#L3)
  * [`use invariant`](https://github.com/Certora/Examples/blob/be09cf32c55e39f5f5aa8cba1431f9e519b52365/CVLByExample/import/certora/specs/sub.spec#L8)
    * [overriding imported `preserved`](https://github.com/Certora/Examples/blob/be09cf32c55e39f5f5aa8cba1431f9e519b52365/CVLByExample/import/certora/specs/sub.spec#L10)
    * [adding a `preserved` block](https://github.com/Certora/Examples/blob/be09cf32c55e39f5f5aa8cba1431f9e519b52365/CVLByExample/import/certora/specs/sub.spec#L14)


## Syntax[](https://docs.certora.com/en/latest/docs/cvl/imports.html#syntax "Link to this heading")
The syntax for `import` and `use` statements is given by the following [EBNF grammar](https://docs.certora.com/en/latest/docs/cvl/overview.html#ebnf-syntax):
```
import ::= "import" string
use ::= "use" "rule" id
    [ "filtered" "{" id "->" expression { "," id "->" expression } "}" ]
   | "use" "builtin" "rule" id
   | "use" "invariant" id [ "filtered" "{" id "->" expression "}" ] [ "{" { preserved_block } "}" ]

```
Copy to clipboard
See [Basic Syntax](https://docs.certora.com/en/latest/docs/cvl/basics.html) for the `string` and `id` productions, [Expressions](https://docs.certora.com/en/latest/docs/cvl/expr.html) for the `expression` production, and [Invariants](https://docs.certora.com/en/latest/docs/cvl/invariants.html) for the `filtered` and `preserved_block` production.
[ Previous](https://docs.certora.com/en/latest/docs/cvl/statements.html "Statements") [Next ](https://docs.certora.com/en/latest/docs/cvl/using.html "Using Statements")
© Copyright 2025, Certora, Inc.
Built with [Sphinx](https://www.sphinx-doc.org/) using a [theme](https://github.com/readthedocs/sphinx_rtd_theme) provided by [Read the Docs](https://readthedocs.org). 
