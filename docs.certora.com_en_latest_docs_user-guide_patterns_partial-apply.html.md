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
  * [Specification Design Patterns](https://docs.certora.com/en/latest/docs/user-guide/patterns/index.html)
  * Partially Parametric Rules
  * [ View page source](https://docs.certora.com/en/latest/_sources/docs/user-guide/patterns/partial-apply.md.txt)


# Partially Parametric Rules[](https://docs.certora.com/en/latest/docs/user-guide/patterns/partial-apply.html#partially-parametric-rules "Link to this heading")
The provided code snippet illustrates a partially parametric rule in CVL that defines specific behavior based on the method invoked (`f`) and its arguments (`calldataarg`). Let’s break down the example for better understanding:
```
rulepartially_parametric_rule(enve,methodf,calldataargargs)
{
if(f.selector==sig:withdraw(uint256,address).selector){
uint256shares;
addressto;
requiree.msg.sender!=currentContract;
requireshares==totalSupply();
withdraw(e,shares,to);
assertbalanceOf(to)>=balanceOf(currentContract);
}
elseif(f.selector==sig:deposit(uint256,address).selector){
uint256depositedAmount=balanceOf(e.msg.sender);
addressto;
requiree.msg.sender!=currentContract;
deposit(e,depositedAmount,to);
assertbalanceOf(to)>=balanceOf(e.msg.sender);
}
else{
uint256currentContract_balance_before=balanceOf(currentContract);
f(e,args);
assertbalanceOf(currentContract)==currentContract_balance_before;
}
}

```
Copy to clipboard
  1. **Withdrawal Case:**
     * If the invoked method (`f`) corresponds to the `withdraw` function with arguments of type `uint256` and `address`, the rule checks certain conditions:
       * Ensures that the sender is not the current contract (`currentContract`).
       * Requires that the variable `shares` is equal to the total supply.
       * Invokes the `withdraw` function with specified parameters (`e`, `shares`, `to`).
       * Asserts that the balance of the recipient (`to`) is greater than or equal to the balance of the current contract.
  2. **Deposit Case:**
     * If the invoked method (`f`) corresponds to the `deposit` function with arguments of type `uint256` and `address`, the rule checks similar conditions:
       * Ensures that the sender is not the current contract (`currentContract`).
       * Computes the `depositedAmount` as the balance of the sender (`e.msg.sender`).
       * Invokes the `deposit` function with specified parameters (`e`, `depositedAmount`, `to`).
       * Asserts that the balance of the recipient (`to`) is greater than or equal to the balance of the sender.
  3. **Default Case:**
     * For any other method, the rule captures the state of the current contract’s balance before the method (`f`) execution in the variable `currentContract_balance_before`.
     * Invokes the method (`f`) with its corresponding arguments (`args`).
     * Asserts that the balance of the current contract after the method execution is equal to the recorded `currentContract_balance_before`.


This partially parametric rule demonstrates conditional logic based on the type of method invoked, allowing for specific actions and assertions tailored to different scenarios within the smart contract.
[ Previous](https://docs.certora.com/en/latest/docs/user-guide/patterns/sums.html "Tracking Sums") [Next ](https://docs.certora.com/en/latest/docs/user-guide/patterns/safe-assum.html "Listing Safe Assumptions")
© Copyright 2025, Certora, Inc.
Built with [Sphinx](https://www.sphinx-doc.org/) using a [theme](https://github.com/readthedocs/sphinx_rtd_theme) provided by [Read the Docs](https://readthedocs.org). 
