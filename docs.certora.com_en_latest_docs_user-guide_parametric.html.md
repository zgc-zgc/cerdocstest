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
      * [General](https://docs.certora.com/en/latest/docs/user-guide/parametric.html#general)
      * [ERC20 example](https://docs.certora.com/en/latest/docs/user-guide/parametric.html#erc20-example)
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
  * Parametric rules
  * [ View page source](https://docs.certora.com/en/latest/_sources/docs/user-guide/parametric.rst.txt)


# Parametric rules[](https://docs.certora.com/en/latest/docs/user-guide/parametric.html#parametric-rules "Link to this heading")
## General[](https://docs.certora.com/en/latest/docs/user-guide/parametric.html#general "Link to this heading")
A [parametric rule](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-parametric-rule) is a rule that uses a `methodf` parameter. Such a rule will be tested against all possible methods `f`, including methods from other contracts in the [scene](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-0). It is possible to limit the methods tested, see [Parametric rules](https://docs.certora.com/en/latest/docs/cvl/rules.html#parametric-rules).
Parametric rules can be used to verify properties of the changes in storage values. The template for such checks is:
Parametric rule template[](https://docs.certora.com/en/latest/docs/user-guide/parametric.html#id1 "Link to this code")
```
ruleparametricExample(methodf){
// Get storage values before
uintbefore=...;
...
// Function call
enve;
calldataargargs;
f(e,args)
// Get storage values after
uintafter=...;
...
// Assert property of the change, e.g.:
assertafter-before==...;
}

```
Copy to clipboard
The main differences between parametric rules and invariants are:
  1. Invariants are also tested after the constructor.
  2. Invariants are used to assert properties of the storage (between function calls), while parametric rules are used to assert properties of _changes_ in the storage (caused by function calls).


## ERC20 example[](https://docs.certora.com/en/latest/docs/user-guide/parametric.html#erc20-example "Link to this heading")
Here is a parametric rule example from the spec file [ERC20Full.spec](https://github.com/Certora/Examples/blob/7dfc379423202c90cf284eb42800b97cf5c95d83/DEFI/ERC20/certora/specs/ERC20Full.spec) – a spec for an ERC20 implementation. The parametric rule `onlyAllowedMethodsMayChangeBalance` asserts two things:
  1. A user’s balance can increase only by calls to `mint`, `transfer`, and `transferFrom`.
  2. A user’s balance can decrease only by calls to `burn`, `transfer`, and `transferFrom`.


It follows that all other functions do not change balances. The rule is shown below, with the lines for getting the storage value before and after the function call highlighted. The two helper functions used in the rule are explained below the rule.
[onlyAllowedMethodsMayChangeBalance](https://github.com/Certora/Examples/blob/7dfc379423202c90cf284eb42800b97cf5c95d83/DEFI/ERC20/certora/specs/ERC20Full.spec)[](https://docs.certora.com/en/latest/docs/user-guide/parametric.html#id2 "Link to this code")
```
ruleonlyAllowedMethodsMayChangeBalance(enve){
requireInvarianttotalSupplyIsSumOfBalances();
methodf;
calldataargargs;
addressholder;
uint256balanceBefore=balanceOf(holder);
f(e,args);
uint256balanceAfter=balanceOf(holder);

assertbalanceAfter>balanceBefore=>canIncreaseBalance(f);
assertbalanceAfter<balanceBefore=>canDecreaseBalance(f);
}

```
Copy to clipboard
  * The function `canIncreaseBalance(f)` returns true if `f` is one of the functions `mint`, `transfer`, or `transferFrom`.
  * Similarly, `canDecreaseBalance(f)` returns true if `f` is one of `burn`, `transfer`, or `transferFrom`.

The helper functions `canIncreaseBalance` and `canDecreaseBalance`
```
definitioncanIncreaseBalance(methodf)returnsbool=
f.selector==sig:mint(address,uint256).selector||
f.selector==sig:transfer(address,uint256).selector||
f.selector==sig:transferFrom(address,address,uint256).selector;
definitioncanDecreaseBalance(methodf)returnsbool=
f.selector==sig:burn(address,uint256).selector||
f.selector==sig:transfer(address,uint256).selector||
f.selector==sig:transferFrom(address,address,uint256).selector;

```
Copy to clipboard
See also
There is more information about parametric rules in [Parametric rules](https://docs.certora.com/en/latest/docs/cvl/rules.html#parametric-rules).
[ Previous](https://docs.certora.com/en/latest/docs/user-guide/invariants.html "Invariants") [Next ](https://docs.certora.com/en/latest/docs/user-guide/ghosts.html "Tracking changes with ghosts and hooks")
© Copyright 2025, Certora, Inc.
Built with [Sphinx](https://www.sphinx-doc.org/) using a [theme](https://github.com/readthedocs/sphinx_rtd_theme) provided by [Read the Docs](https://readthedocs.org). 
