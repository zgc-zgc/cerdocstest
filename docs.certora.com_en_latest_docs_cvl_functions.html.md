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
      * [Syntax](https://docs.certora.com/en/latest/docs/cvl/functions.html#syntax)
      * [Examples](https://docs.certora.com/en/latest/docs/cvl/functions.html#examples)
      * [Using CVL functions](https://docs.certora.com/en/latest/docs/cvl/functions.html#using-cvl-functions)
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
  * Functions
  * [ View page source](https://docs.certora.com/en/latest/_sources/docs/cvl/functions.md.txt)


# Functions[](https://docs.certora.com/en/latest/docs/cvl/functions.html#functions "Link to this heading")
CVL functions allow you to reuse parts of a specification, such as common assumptions, assertions, or basic calculations. Additionally they can be used for basic calculations and for [function summaries](https://github.com/Certora/Examples/blob/bf3255766c28068eea2d0513edb8daca7bcaa206/CVLByExample/function-summary/multi-contract/certora/specs/spec_with_summary.spec#L6).
## Syntax[](https://docs.certora.com/en/latest/docs/cvl/functions.html#syntax "Link to this heading")
The syntax for CVL functions is given by the following [EBNF grammar](https://docs.certora.com/en/latest/docs/cvl/overview.html#ebnf-syntax):
```
function ::= [ "override" ]
       "function" id
       [ "(" params ")" ]
       [ "returns" type ]
       block

```
Copy to clipboard
See [Basic Syntax](https://docs.certora.com/en/latest/docs/cvl/basics.html) for the `id` production, [Types](https://docs.certora.com/en/latest/docs/cvl/types.html) for the `type` production, and [Statements](https://docs.certora.com/en/latest/docs/cvl/statements.html) for the `block` production.
## Examples[](https://docs.certora.com/en/latest/docs/cvl/functions.html#examples "Link to this heading")
  * Function with a return:
```
functionabs_value_difference(uint256x,uint256y)returnsuint256{
if(x<y){
returny-x;
}else{
returnx-y;
}
}

```
Copy to clipboard
  * [CVL function with no return](https://github.com/Certora/Examples/blob/14668d39a6ddc67af349bc5b82f73db73349ef18/CVLByExample/LiquidityPool/certora/specs/pool.spec#L24)
  * [Overriding a function from imported spec](https://github.com/Certora/Examples/blob/be09cf32c55e39f5f5aa8cba1431f9e519b52365/CVLByExample/import/certora/specs/sub.spec#L38)


## Using CVL functions[](https://docs.certora.com/en/latest/docs/cvl/functions.html#using-cvl-functions "Link to this heading")
CVL Function may be called from within a rule, or from within another CVL function.
[ Previous](https://docs.certora.com/en/latest/docs/cvl/builtin.html "Built-in Rules") [Next ](https://docs.certora.com/en/latest/docs/cvl/invariants.html "Invariants")
© Copyright 2025, Certora, Inc.
Built with [Sphinx](https://www.sphinx-doc.org/) using a [theme](https://github.com/readthedocs/sphinx_rtd_theme) provided by [Read the Docs](https://readthedocs.org). 
