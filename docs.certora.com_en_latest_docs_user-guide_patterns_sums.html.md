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
        * [Enforcing Sum of Two Balances Constraint](https://docs.certora.com/en/latest/docs/user-guide/patterns/sums.html#enforcing-sum-of-two-balances-constraint)
        * [Maintaining Equality Between Sum of Balances and Total Supply](https://docs.certora.com/en/latest/docs/user-guide/patterns/sums.html#maintaining-equality-between-sum-of-balances-and-total-supply)
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
  * Tracking Sums
  * [ View page source](https://docs.certora.com/en/latest/_sources/docs/user-guide/patterns/sums.md.txt)


# Tracking Sums[](https://docs.certora.com/en/latest/docs/user-guide/patterns/sums.html#tracking-sums "Link to this heading")
## Enforcing Sum of Two Balances Constraint[](https://docs.certora.com/en/latest/docs/user-guide/patterns/sums.html#enforcing-sum-of-two-balances-constraint "Link to this heading")
```
invariantdirectSumOfTwo(addressa,addressb)
(a!=b)=>(balanceOf(a)+balanceOf(b)<=to_mathint(totalSupply()));

```
Copy to clipboard
Ensure that the sum of balances for any two distinct addresses, `a` and `b`, does not exceed the total supply.
## Maintaining Equality Between Sum of Balances and Total Supply[](https://docs.certora.com/en/latest/docs/user-guide/patterns/sums.html#maintaining-equality-between-sum-of-balances-and-total-supply "Link to this heading")
```
ghostmathintsumBalances{
init_stateaxiomsumBalances==0;
}
hookSstorebalanceOf[KEYaddressuser]uint256newBalance(uint256oldBalance)
{
// there is no `+=` operator in CVL
sumBalances=sumBalances+newBalance-oldBalance;
}
invarianttotalIsSumBalances()
to_mathint(totalSupply())==sumBalances;

```
Copy to clipboard
Track the sum of all balances and ensure that it remains equal to the total supply. The `sumBalances` ghost variable is updated with changes in individual balances using a storage hook, ensuring accuracy and consistency in the overall sum.
for more information about the example checkout [this tutorial](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/ghosts/sum_two.html#lesson4-ghost-sum-balances).
[ Previous](https://docs.certora.com/en/latest/docs/user-guide/patterns/index.html "Specification Design Patterns") [Next ](https://docs.certora.com/en/latest/docs/user-guide/patterns/partial-apply.html "Partially Parametric Rules")
© Copyright 2025, Certora, Inc.
Built with [Sphinx](https://www.sphinx-doc.org/) using a [theme](https://github.com/readthedocs/sphinx_rtd_theme) provided by [Read the Docs](https://readthedocs.org). 
