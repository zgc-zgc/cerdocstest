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
      * [Detecting Vacuous Specifications](https://docs.certora.com/en/latest/docs/user-guide/checking.html#detecting-vacuous-specifications)
      * [Identifying Tautology Specifications](https://docs.certora.com/en/latest/docs/user-guide/checking.html#identifying-tautology-specifications)
      * [Conclusion](https://docs.certora.com/en/latest/docs/user-guide/checking.html#conclusion)
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
  * Checking Specifications
  * [ View page source](https://docs.certora.com/en/latest/_sources/docs/user-guide/checking.md.txt)


# Checking Specifications[](https://docs.certora.com/en/latest/docs/user-guide/checking.html#checking-specifications "Link to this heading")
Effective formal verification relies on accurate specifications. A flaw in the specification could lead to critical bugs slipping through undetected. Certora offers a set of tools to enhance the accuracy of specifications and identify potential issues. This chapter outlines these tools and demonstrates their application.
## Detecting Vacuous Specifications[](https://docs.certora.com/en/latest/docs/user-guide/checking.html#detecting-vacuous-specifications "Link to this heading")
A vacuous statement is one that is technically true but lacks meaningful content. Consider the following example:
**Contract:**
```
functionbalanceOf(addressaccount,uint256id)publicviewoverridereturns(uint256){
require(account!=address(0),"account is zero");
return_balances[id][account];
}

```
Copy to clipboard
**Specification:**
```
ruleheld_token_should_exist{
addressuser;
uint256token;
requirebalanceOf(0,token)==0;
requirebalanceOf(user,token)<=totalSupplyOf(token);
assertbalanceOf(user,token)>0=>token_exists(token);
}

```
Copy to clipboard
The specification contains a flaw; the statement `balanceOf(0, token) == 0;` will always revert due to the `require` in the contract, resulting in an empty starting state. To address such issues, Certora allows to run [Vacuity checks](https://docs.certora.com/en/latest/docs/prover/checking/sanity.html?highlight=rule%20sanity#sanity-vacuity). These checks append `assert false` to each rule, exposing vacuously proven assumptions. This ensures that every rule in the specification has at least one input that reaches all the assertions. It is a useful check, but nevertheless, it is not a good measure of coverage. For more information on coverage measures, check out [mutation testing](https://docs.certora.com/en/latest/docs/prover/checking/mutation.html?highlight=rule%20mutation#mutation-testing).
_Note: Vacuity in real-world examples often arises from combinations of requirements, not just isolated statements._
## Identifying Tautology Specifications[](https://docs.certora.com/en/latest/docs/user-guide/checking.html#identifying-tautology-specifications "Link to this heading")
Tautology, a special case of vacuity known as the “vacuous assertion,” occurs when a statement is always true regardless of the system’s state. An example is provided below:
```
rulesomething_is_always_transferred{
addressreceiver;
uint256balance_before_transfer=balanceOf(receiver);
requirebalanceOf(receiver)==0;
uint256amount;
requireamount>0;
transfer(receiver,amount);
uint256balance_after_transfer=balanceOf(receiver);
assertbalanceOf(receiver)<=balance_after_transfer;
}

```
Copy to clipboard
In this case, the `assert` statement is always true since it compares equal values, neglecting any meaningful checks related to the transfer behavior. Certora allows to run [Assert tautology checks](https://docs.certora.com/en/latest/docs/prover/checking/sanity.html?highlight=rule%20sanity#assert-tautology-checks) to address such instances. By removing preconditions and operations, these checks focus solely on the `assert` statement, revealing whether it is always true regardless of the process being examined.
## Conclusion[](https://docs.certora.com/en/latest/docs/user-guide/checking.html#conclusion "Link to this heading")
For more comprehensive examples and solutions, please refer to our [documentation](https://docs.certora.com/en/latest/docs/prover/checking/index.html). Certora’s suite of verification tools empowers developers to enhance the precision of their specifications, ensuring robust and reliable smart contract development.
[ Previous](https://docs.certora.com/en/latest/docs/user-guide/gaps.html "Understanding gaps between high and low level code") [Next ](https://docs.certora.com/en/latest/docs/user-guide/ci.html "CI Configuration")
© Copyright 2025, Certora, Inc.
Built with [Sphinx](https://www.sphinx-doc.org/) using a [theme](https://github.com/readthedocs/sphinx_rtd_theme) provided by [Read the Docs](https://readthedocs.org). 
