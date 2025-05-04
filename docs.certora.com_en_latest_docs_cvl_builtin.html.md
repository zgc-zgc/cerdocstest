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
      * [Syntax](https://docs.certora.com/en/latest/docs/cvl/builtin.html#syntax)
      * [Bad loop detection — `msgValueInLoopRule`](https://docs.certora.com/en/latest/docs/cvl/builtin.html#bad-loop-detection-msgvalueinlooprule)
      * [Delegate call detection — `hasDelegateCalls`](https://docs.certora.com/en/latest/docs/cvl/builtin.html#delegate-call-detection-hasdelegatecalls)
      * [Basic setup checks — `sanity`](https://docs.certora.com/en/latest/docs/cvl/builtin.html#basic-setup-checks-sanity)
        * [How `sanity` is checked](https://docs.certora.com/en/latest/docs/cvl/builtin.html#how-sanity-is-checked)
      * [Thorough complexity checks — `deepSanity`](https://docs.certora.com/en/latest/docs/cvl/builtin.html#thorough-complexity-checks-deepsanity)
        * [How `deepSanity` is checked](https://docs.certora.com/en/latest/docs/cvl/builtin.html#how-deepsanity-is-checked)
      * [Read-only reentrancy detection — `viewReentrancy`](https://docs.certora.com/en/latest/docs/cvl/builtin.html#read-only-reentrancy-detection-viewreentrancy)
        * [How `viewReentrancy` is checked](https://docs.certora.com/en/latest/docs/cvl/builtin.html#how-viewreentrancy-is-checked)
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
  * Built-in Rules
  * [ View page source](https://docs.certora.com/en/latest/_sources/docs/cvl/builtin.md.txt)


# [Built-in Rules](https://docs.certora.com/en/latest/docs/cvl/builtin.html#id1)[](https://docs.certora.com/en/latest/docs/cvl/builtin.html#built-in-rules "Link to this heading")
The Certora Prover has built-in general-purpose rules targeted at finding common vulnerabilities. These rules can be verified on a contract without writing any contract-specific rules.
Built-in rules can be included in any spec file by writing `use builtin rule <rule-name>;`. This document describes the available built-in rules.
Contents
  * [Built-in Rules](https://docs.certora.com/en/latest/docs/cvl/builtin.html#built-in-rules)
    * [Syntax](https://docs.certora.com/en/latest/docs/cvl/builtin.html#syntax)
    * [Bad loop detection — `msgValueInLoopRule`](https://docs.certora.com/en/latest/docs/cvl/builtin.html#bad-loop-detection-msgvalueinlooprule)
    * [Delegate call detection — `hasDelegateCalls`](https://docs.certora.com/en/latest/docs/cvl/builtin.html#delegate-call-detection-hasdelegatecalls)
    * [Basic setup checks — `sanity`](https://docs.certora.com/en/latest/docs/cvl/builtin.html#basic-setup-checks-sanity)
      * [How `sanity` is checked](https://docs.certora.com/en/latest/docs/cvl/builtin.html#how-sanity-is-checked)
    * [Thorough complexity checks — `deepSanity`](https://docs.certora.com/en/latest/docs/cvl/builtin.html#thorough-complexity-checks-deepsanity)
      * [How `deepSanity` is checked](https://docs.certora.com/en/latest/docs/cvl/builtin.html#how-deepsanity-is-checked)
    * [Read-only reentrancy detection — `viewReentrancy`](https://docs.certora.com/en/latest/docs/cvl/builtin.html#read-only-reentrancy-detection-viewreentrancy)
      * [How `viewReentrancy` is checked](https://docs.certora.com/en/latest/docs/cvl/builtin.html#how-viewreentrancy-is-checked)


## [Syntax](https://docs.certora.com/en/latest/docs/cvl/builtin.html#id2)[](https://docs.certora.com/en/latest/docs/cvl/builtin.html#syntax "Link to this heading")
The syntax for rules is given by the following [EBNF grammar](https://docs.certora.com/en/latest/docs/cvl/overview.html#ebnf-syntax):
```
built_in_rule ::= "use" "builtin" "rule" built_in_rule_name ";"
built_in_rule_name ::=
  | "msgValueInLoopRule"
  | "hasDelegateCalls"
  | "sanity"
  | "deepSanity"
  | "viewReentrancy"

```
Copy to clipboard
## [Bad loop detection — `msgValueInLoopRule`](https://docs.certora.com/en/latest/docs/cvl/builtin.html#id3)[](https://docs.certora.com/en/latest/docs/cvl/builtin.html#bad-loop-detection-msgvalueinlooprule "Link to this heading")
Loops that [use `msg.value` or make delegate calls](https://trustchain.medium.com/ethereum-msg-value-reuse-vulnerability-5afd0aa2bcef) are a well-known source of security vulnerabilities.
The `msgValueInLoopRule` detects these anti-patterns. It can be enabled by including
```
usebuiltinrulemsgValueInLoopRule;

```
Copy to clipboard
in a spec file. The rule will fail on any functions that can make delegate calls or access `msg.value` inside a loop. This includes any functions that recursively call any functions that has this vulnerability.
## [Delegate call detection — `hasDelegateCalls`](https://docs.certora.com/en/latest/docs/cvl/builtin.html#id4)[](https://docs.certora.com/en/latest/docs/cvl/builtin.html#delegate-call-detection-hasdelegatecalls "Link to this heading")
The `hasDelegateCalls` built-in rule is a handy way to find delegate calls in a contract. [Contracts that use delegate calls](https://blog.solidityscan.com/security-issues-with-delegate-calls-4ae64d775b76) require proper security checking.
The `hasDelegateCalls` can be enabled by including
```
usebuiltinrulehasDelegateCalls;

```
Copy to clipboard
in a spec file. Any functions that can make delegate calls will fail the `hasDelegateCalls` rule.
## [Basic setup checks — `sanity`](https://docs.certora.com/en/latest/docs/cvl/builtin.html#id5)[](https://docs.certora.com/en/latest/docs/cvl/builtin.html#basic-setup-checks-sanity "Link to this heading")
The `sanity` rule checks that there is at least one non-reverting path through each contract function. It can be enabled by including
```
usebuiltinrulesanity;

```
Copy to clipboard
in a spec file.
The sanity rule is useful for two reasons:
  * It is an easy way to determine which contract functions take a long time to analyze. If a method takes a long time to verify the `sanity` rule (or times out), it will almost certainly time out while verifying interesting properties. This can help you quickly discover which methods may need [summarization](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-summary).
  * A method the fails the `sanity` rule will revert on every input; every rule that calls the method will therefore be [vacuous](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-vacuity). This probably indicates a problem with the Prover configuration; the most likely cause is [loop unrolling](https://docs.certora.com/en/latest/docs/prover/approx/loops.html#unrolling).


We recommend running the sanity rule at the beginning of a project to ensure that the Prover’s configuration is reasonable.
Note
The `sanity` built-in rule is unrelated to the [rule_sanity](https://docs.certora.com/en/latest/docs/prover/cli/options.html#rule-sanity) option; the built-in rule is used to check the basic setup, while `--rule_sanity` checks individual rules.
### [How `sanity` is checked](https://docs.certora.com/en/latest/docs/cvl/builtin.html#id6)[](https://docs.certora.com/en/latest/docs/cvl/builtin.html#how-sanity-is-checked "Link to this heading")
The `sanity` rule is translated into the following [parametric rule](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-parametric-rule):
```
rulesanity{
methodf;enve;
calldataargarg;
f(e,arg);
asserttrue;
satisfytrue;
}

```
Copy to clipboard
This will create two sub-rules, which will be visible in the report. One sub-rule checks the `satisfy true` statement, which is fulfilled if there is an input such that `f(e, arg)` runs to completion without reverting. The other sub-rule checks the `assert true` statement. Of course, this assertion itself is never violated, but the sub-rule contains the [pessimistic assertions](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-pessimistic-assertions) that we insert when at least one of the “optimistic” flags (e.g. [optimistic_loop](https://docs.certora.com/en/latest/docs/prover/cli/options.html#optimistic-loop), [optimistic_hashing](https://docs.certora.com/en/latest/docs/prover/cli/options.html#optimistic-hashing), etc.) is not active. Note that rules with only [satisfy statements](https://docs.certora.com/en/latest/docs/cvl/statements.html#satisfy) do not check these assertions.
## [Thorough complexity checks — `deepSanity`](https://docs.certora.com/en/latest/docs/cvl/builtin.html#id7)[](https://docs.certora.com/en/latest/docs/cvl/builtin.html#thorough-complexity-checks-deepsanity "Link to this heading")
The basic sanity rule only tries to find a _single_ input that causes each function to execute without reverting. While this check can quickly identify problems with the Prover setup, a successful `sanity` run does not guarantee that the contract methods won’t cause Prover timeouts, or that all of the contract code is reachable.
For example, consider the following method:
```
functionveryComplexFunction()returns(uint){
uintx=0;
for(uinti=0;i<array.len;i++){
x=x+complexComputation(i);
}
returnx;
}

```
Copy to clipboard
There is clearly a simple non-reverting path through the code: it will immediately return if `array.len` is `0`; the basic `sanity` can quickly find a [model](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-model) like this without even considering the implementation of `complexComputation`, so the `sanity` rule will succeed. However, verifying any property that depends on the return value of `veryComplexFunction` will require the Prover to reason about `complexComputation()`, which may cause timeouts. Moreover, portions of `complexComputation` may be unreachable, and this will not be caught by the basic `sanity` rule.
The `deepSanity` rule generalizes the basic `sanity` rule by heuristically choosing interesting statements in the contract code and ensuring that there are non-reverting [models](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-model) that execute those statements. In the above example, one of the paths chosen by `deepSanity` would go through the body of the `for` loop, forcing the Prover to find a non-reverting path through the `complexComputation` method.
The `deepSanity` rule heuristic favors the following program points:
  1. The “if” and “else” branches of a code-heavy `if` statement
  2. The beginning of an external call
  3. The beginning of the program (this is the same as the usual sanity rule)


The `deepSanity` rule can be enabled by including
```
usebuiltinruledeepSanity;

```
Copy to clipboard
in a spec file. You must also pass the [multi_assert_check](https://docs.certora.com/en/latest/docs/prover/cli/options.html#multi-assert-check) flag to the Prover.
The number of code points that are chosen can be configured with the [maxNumberOfReachChecksBasedOnDomination](https://docs.certora.com/en/latest/docs/prover/cli/options.html#maxnumberofreachchecksbasedondomination) flag; the default value is `10`.
### [How `deepSanity` is checked](https://docs.certora.com/en/latest/docs/cvl/builtin.html#id8)[](https://docs.certora.com/en/latest/docs/cvl/builtin.html#how-deepsanity-is-checked "Link to this heading")
The `deepSanity` rule works similarly to the `sanity` rule; it adds an additional variable `x_p` for each interesting program point `p`, and instruments the contract code at `p` to set `x_p` to `true`. The Prover then tries to prove that `x_p` is false after executing the function. To find a counterexample; the Prover must construct a model that passes through `p`.
## [Read-only reentrancy detection — `viewReentrancy`](https://docs.certora.com/en/latest/docs/cvl/builtin.html#id9)[](https://docs.certora.com/en/latest/docs/cvl/builtin.html#read-only-reentrancy-detection-viewreentrancy "Link to this heading")
The `viewReentrancy` built-in rule detects [read-only reentrancy vulnerabilities in a contract](https://blog.pessimistic.io/read-only-reentrancy-in-depth-6ea7e9d78e85).
The `viewReentrancy` rule can be enabled by including
```
usebuiltinruleviewReentrancy;

```
Copy to clipboard
in a spec file. Any functions that have read-only reentrancy will fail the `viewReentrancy` rule.
### [How `viewReentrancy` is checked](https://docs.certora.com/en/latest/docs/cvl/builtin.html#id10)[](https://docs.certora.com/en/latest/docs/cvl/builtin.html#how-viewreentrancy-is-checked "Link to this heading")
Reentrancy vulnerabilities can arise when a contract makes an external call with an inconsistent internal state. This behavior allows the receiver contract to make reentrant calls that exploit the inconsistency.
The `viewReentrancy` rule ensures that whenever a method `f` of [currentContract](https://docs.certora.com/en/latest/docs/cvl/expr.html#currentcontract) makes an external call, the internal state of `currentContract` is equivalent to either (1) the state of `currentContract` at the beginning of the calling function, or (2) the state of `currentContract` at the end of the calling function (by “equivalent”, we mean that all view functions return the same values). This ensures that the external call cannot observe `currentContract` in any state that it couldn’t have without being called from `currentContract`.
[ Previous](https://docs.certora.com/en/latest/docs/cvl/rules.html "Rules") [Next ](https://docs.certora.com/en/latest/docs/cvl/functions.html "Functions")
© Copyright 2025, Certora, Inc.
Built with [Sphinx](https://www.sphinx-doc.org/) using a [theme](https://github.com/readthedocs/sphinx_rtd_theme) provided by [Read the Docs](https://readthedocs.org). 
