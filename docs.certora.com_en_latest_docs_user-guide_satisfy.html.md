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
  * [Certora User’s Guide](https://docs.certora.com/en/latest/docs/user-guide/index.html)
  * Producing Positive Examples
  * [ View page source](https://docs.certora.com/en/latest/_sources/docs/user-guide/satisfy.md.txt)


# Producing Positive Examples[](https://docs.certora.com/en/latest/docs/user-guide/satisfy.html#producing-positive-examples "Link to this heading")
Sometimes it is useful to produce examples of an expected behavior instead of counterexamples that demonstrate unexpected behavior. You can do this by writing a rule that uses [satisfy statements](https://docs.certora.com/en/latest/docs/cvl/statements.html#satisfy) instead of the `assert` command. For each `satisfy` command in a rule, the Prover will produce an example that makes the condition true, or report an error.
The purpose of the `satisfy` statement is to produce examples that demonstrate some execution of the code. Not every example is interesting — users should inspect the example to ensure that it demonstrates the expected behavior.
For [example](https://github.com/Certora/Examples/blob/7dfc379423202c90cf284eb42800b97cf5c95d83/DEFI/ConstantProductPool/certora/spec/ConstantProductPool.spec), we may be interested in showing that it is possible for someone to deposit some assets into a pool and then immediately withdraw them. The following rule demonstrates this scenario:
Positive example[](https://docs.certora.com/en/latest/docs/user-guide/satisfy.html#id1 "Link to this code")
```
rulepossibleToFullyWithdraw(addresssender,uint256amount){
enveT0;
enveM;
setup(eM);
addresstoken;
requiretoken==_token0||token==_token1;
uint256balanceBefore=token.balanceOf(eT0,sender);
requireeM.msg.sender==sender;
requireeT0.msg.sender==sender;
requireamount>0;
token.transfer(eT0,currentContract,amount);
uint256amountOut0=mint(eM,sender);
// immediately withdraw 
burnSingle(eM,_token0,amountOut0,sender);
satisfy(balanceBefore==token.balanceOf(eT0,sender));
}

```
Copy to clipboard
The Prover will produce an example that satisfies this condition. Sometimes the example will be uninteresting, such as having `amount==0` in the example for `possibleToFullyWithdraw`. In such cases we need to strengthen the conditions in order to produce more interesting examples. In `possibleToFullyWithdraw` we added a `requireamount>0;` statement to prevent such a case.
Alternatively, we could have strengthened the `satisfy` condition by adding
```
satisfy(amount>0)&&...

```
Copy to clipboard
[ Previous](https://docs.certora.com/en/latest/docs/user-guide/properties/index.html "Designing Good Specifications") [Next ](https://docs.certora.com/en/latest/docs/user-guide/invariants.html "Invariants")
© Copyright 2025, Certora, Inc.
Built with [Sphinx](https://www.sphinx-doc.org/) using a [theme](https://github.com/readthedocs/sphinx_rtd_theme) provided by [Read the Docs](https://readthedocs.org). 
