[ Certora Prover Documentation ![Logo](https://docs.certora.com/en/latest/_static/Certora_Logo_Black.svg) ](https://docs.certora.com/en/latest/index.html)
Contents
  * [Certora User’s Guide](https://docs.certora.com/en/latest/docs/user-guide/index.html)
  * [The Certora Verification Language](https://docs.certora.com/en/latest/docs/cvl/index.html)
  * [The Certora Prover](https://docs.certora.com/en/latest/docs/prover/index.html)
    * [Introduction](https://docs.certora.com/en/latest/docs/prover/intro.html)
    * [Installation](https://docs.certora.com/en/latest/docs/user-guide/install.html)
    * [Prover Approximations](https://docs.certora.com/en/latest/docs/prover/approx/index.html)
    * [Techniques Used by the Certora Prover](https://docs.certora.com/en/latest/docs/prover/techniques/index.html)
    * [Diagnostic Tools](https://docs.certora.com/en/latest/docs/prover/diagnosis/index.html)
    * [Checking Specifications](https://docs.certora.com/en/latest/docs/prover/checking/index.html)
      * [Rule Sanity Checks](https://docs.certora.com/en/latest/docs/prover/checking/sanity.html)
      * [Coverage Info](https://docs.certora.com/en/latest/docs/prover/checking/coverage-info.html)
        * [Examples](https://docs.certora.com/en/latest/docs/prover/checking/coverage-info.html#examples)
        * [Basic vs. advanced mode](https://docs.certora.com/en/latest/docs/prover/checking/coverage-info.html#basic-vs-advanced-mode)
        * [Completeness](https://docs.certora.com/en/latest/docs/prover/checking/coverage-info.html#completeness)
      * [Bug Injection](https://docs.certora.com/en/latest/docs/prover/checking/injection.html)
      * [Mutation Testing](https://docs.certora.com/en/latest/docs/prover/checking/mutation.html)
    * [Certora Prover CLI](https://docs.certora.com/en/latest/docs/prover/cli/index.html)
    * [Using the Certora Portal](https://docs.certora.com/en/latest/docs/prover/portal/using.html)
    * [Changelogs](https://docs.certora.com/en/latest/docs/prover/changelog/index.html)
  * [Sunbeam: Verification for Soroban](https://docs.certora.com/en/latest/docs/sunbeam/index.html)
  * [The Certora Solana Prover](https://docs.certora.com/en/latest/docs/solana/index.html)
  * [Gambit: Mutation Generator for Solidity](https://docs.certora.com/en/latest/docs/gambit/index.html)


Additional information
  * [The Certora Equivalence Checker](https://docs.certora.com/en/latest/docs/equiv-check/index.html)
  * [Certora Technology White Paper](https://docs.certora.com/en/latest/docs/whitepaper/index.html)


  * [Index](https://docs.certora.com/en/latest/genindex.html)


[Certora Prover Documentation](https://docs.certora.com/en/latest/index.html)
  * [](https://docs.certora.com/en/latest/index.html)
  * [The Certora Prover](https://docs.certora.com/en/latest/docs/prover/index.html)
  * [Checking Specifications](https://docs.certora.com/en/latest/docs/prover/checking/index.html)
  * Coverage Info
  * [ View page source](https://docs.certora.com/en/latest/_sources/docs/prover/checking/coverage-info.md.txt)


# Coverage Info[](https://docs.certora.com/en/latest/docs/prover/checking/coverage-info.html#coverage-info "Link to this heading")
The [coverage_info](https://docs.certora.com/en/latest/docs/prover/cli/options.html#coverage-info) flag enables automatic computation of coverage information for a verification run. In particular, using this flag can help you answer questions such as:
  * _Are all solidity functions from the input involved in proving my rules?_
  * _Are all solidity commands from the input involved in proving my rules?_
  * _Supposing an`assert` in my rule is not reachable, what is the reason for the unreachability?_
  * _Do I really need all hooks that are defined in my`.spec` file(s)?_
  * _Do I really need all`require` statements in my rule?_
  * _Do I really need to initialize a CVL variable in my rule?_
  * _Do I really need all of the preserved blocks in my CVL`invariant`?_


To answer the above questions, the Certora Prover identifies a minimal subset of the commands in the input `.sol` and `.spec` files that are relevant for proving the CVL properties. If some of the input `.sol` commands are not relevant for deriving the proof, it might indicate that the specification does not cover all behavior implemented in the smart contract. If some of the input `.spec` commands are irrelevant (typically unnecessary `require` statements or variable initializations), it indicates that the CVL rules/invariants can be made stronger.
You can access the coverage visualization via `Job Info -> Coverage Info page` buttons:
![Coverage Info Button](https://docs.certora.com/en/latest/_images/coverage-info-button.png)
## Examples[](https://docs.certora.com/en/latest/docs/prover/checking/coverage-info.html#examples "Link to this heading")
### Tautology example[](https://docs.certora.com/en/latest/docs/prover/checking/coverage-info.html#tautology-example "Link to this heading")
Consider the following CVL rule called `tautology`:
```
ruletautology(uint256fundId,methodf){
enve;
addressmanager=getCurrentManager(fundId);
addressother;
requireother!=manager&&other!=e.msg.sender;
calldataargargs;
f(e,args);
addressnewManager=getCurrentManager(fundId);
assertnewManager!=other||newManager!=manager;
}

```
Copy to clipboard
Notice that we required that `other != manager` and hence the `assert` is necessarily `true` (see the concept of a [tautology](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-tautology)). The executions of `getCurrentManager(...)` and `f(...)` are completely irrelevant.
The coverage visualization is shown below. It consists of two _panes_ :
  1. The left pane shows _per-line_ visualization.
  2. The right pane shows detailed info about individual visualized lines.


![Example Coverage Info Visualization](https://docs.certora.com/en/latest/_images/tautology-sol-and-spec-cropped.png)
In particular, in the left pane, we highlight lines from individual `.sol` and `.spec` files. Every line may optionally have a green, yellow, or red background color. No background means we have no information about this line, i.e. it might or might not be needed for the proof. Green, red or yellow background means we have some information about values of commands on the line:
  1. Green means that all of the values on the line are relevant for proving the property.
  2. Red means that none of the values on the line is relevant for proving the property. In particular, you can arbitrary change the values and the property would still hold.
  3. Yellow means that some of the values on the line are relevant and some are not.


Furthermore, if we have multiple rules/invariants or a parametric rule (such as our `tautology`), we can also have multiple rules/invariants mapping to a single `.sol` or `.spec` line. In such a case, a yellow line means that some of the values on the line are relevant for proving some of the rules/methods/invariants and some of the values are not relevant. If you want to generate coverage visualization for a single rule or method, use [rule](https://docs.certora.com/en/latest/docs/prover/cli/options.html#rule) or [method](https://docs.certora.com/en/latest/docs/prover/cli/options.html#method).
The right pane provides detailed information about individual values mapped to the lines grouped by the rule/method/invariant name (denoted _rule_). For instance, in the Tautology example, we can see that the value of the command `other != manager` on line `11` matters, whereas the value of `other != e.msg.sender` is irrelevant for the proof. Also, note that the pane shows e.g. both `other != manager` and `other == manager`; this is due our internal representation of the input where we encode `other != manager` as `!(other == manager)`.
## Basic vs. advanced mode[](https://docs.certora.com/en/latest/docs/prover/checking/coverage-info.html#basic-vs-advanced-mode "Link to this heading")
The `--coverage_info` flag takes three possible values: `none`, `basic` and `advanced`:
  1. `none` means no coverage analysis,
  2. `basic` means relatively fast but possibly very imprecise analysis (i.e. can claim that some values are not relevant even if they are, and also vice versa),
  3. and `advanced` means possibly slow but more precise analysis.


## Completeness[](https://docs.certora.com/en/latest/docs/prover/checking/coverage-info.html#completeness "Link to this heading")
We perform the coverage analysis on our internal [SMT](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-SMT) representation of the [verification condition](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-verification-condition), and then map the results of the analysis to the `.sol` and `.spec` files. Unfortunately, due to the compilation of the solidity code to EVM bytecode, we cannot maintain a complete mapping between commands from solidity and commands in our SMT representation. Consequently, the visualization on `.sol` files can be very limited.
[ Previous](https://docs.certora.com/en/latest/docs/prover/checking/sanity.html "Rule Sanity Checks") [Next ](https://docs.certora.com/en/latest/docs/prover/checking/injection.html "Bug Injection")
© Copyright 2025, Certora, Inc.
Built with [Sphinx](https://www.sphinx-doc.org/) using a [theme](https://github.com/readthedocs/sphinx_rtd_theme) provided by [Read the Docs](https://readthedocs.org). 
