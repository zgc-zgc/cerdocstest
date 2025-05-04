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
        * [Importance of Require Invariants:](https://docs.certora.com/en/latest/docs/user-guide/patterns/require-invariants.html#importance-of-require-invariants)
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
  * Require Invariants: Proving inter-dependent invariants
  * [ View page source](https://docs.certora.com/en/latest/_sources/docs/user-guide/patterns/require-invariants.md.txt)


# Require Invariants: Proving inter-dependent invariants[](https://docs.certora.com/en/latest/docs/user-guide/patterns/require-invariants.html#require-invariants-proving-inter-dependent-invariants "Link to this heading")
The`requireInvariant` statements can be used to establish crucial conditions that must persist throughout the execution of a smart contract. Let’s explore the usefulness of the `requireInvariant` statement and illustrate its application using the provided example.
```
invarianttotalSharesLessThanDepositedAmount()
totalSupply()<=depositedAmount();
invarianttotalSharesLessThanUnderlyingBalance()
totalSupply()<=underlying.balanceOf(currentContract)
{
preservedwith(enve){
requiree.msg.sender!=currentContract;
requireInvarianttotalSharesLessThanDepositedAmount();
requireInvariantdepositedAmountLessThanContractUnderlyingAsset();
}
}
rulesharesRoundingTripFavoursContract(enve){
uint256clientSharesBefore=balanceOf(e.msg.sender);
uint256contractSharesBefore=balanceOf(currentContract);
requireInvarianttotalSharesLessThanDepositedAmount();
requiree.msg.sender!=currentContract;
uint256depositedAmount=depositedAmount();
uint256clientAmount=withdraw(e,clientSharesBefore);
uint256clientSharesAfter=deposit(e,clientAmount);
uint256contractSharesAfter=balanceOf(currentContract);
assert(clientAmount==depositedAmount)=>clientSharesBefore<=clientSharesAfter;
// all other states
assert(clientAmount<depositedAmount)=>clientSharesBefore>=clientSharesAfter;
assertcontractSharesBefore<=contractSharesAfter;
}

```
Copy to clipboard
## Importance of Require Invariants:[](https://docs.certora.com/en/latest/docs/user-guide/patterns/require-invariants.html#importance-of-require-invariants "Link to this heading")
  1. **Ensuring Invariant Consistency:**
     * The `totalSharesLessThanUnderlyingBalance` invariant expands the validation scope to include the underlying balance of the current contract. By utilizing the previously established `totalSharesLessThanDepositedAmount` invariant as a prerequisite, the specification writer ensures that the total shares in the contract remain within the limits of the underlying asset balance. This `requireInvariant` approach effectively eliminates counterexamples in states that have already been proven to be unattainable.
  2. **Validation Through Rules:**
     * The `sharesRoundingTripFavoursContract` rule showcases the application of require invariants to verify the behavior of share transactions. Similarly to the invariant example, the `requireInvariant` statements enable the specification writer to disregard counterexamples in states that are not relevant to the intended behavior.


In conclusion, the “Require Invariants” design pattern, as demonstrated through the provided example, offers a systematic methodology to define, validate, and uphold critical conditions within smart contract specifications. for more information, please visit the [documentation](https://docs.certora.com/en/latest/docs/cvl/statements.html).
[ Previous](https://docs.certora.com/en/latest/docs/user-guide/patterns/safe-assum.html "Listing Safe Assumptions") [Next ](https://docs.certora.com/en/latest/docs/user-guide/opcodes.html "Using Opcode Hooks")
© Copyright 2025, Certora, Inc.
Built with [Sphinx](https://www.sphinx-doc.org/) using a [theme](https://github.com/readthedocs/sphinx_rtd_theme) provided by [Read the Docs](https://readthedocs.org). 
