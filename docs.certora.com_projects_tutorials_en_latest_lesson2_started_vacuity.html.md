Contents Menu Expand Light mode Dark mode Auto light/dark mode Auto light/dark, in light mode Auto light/dark, in dark mode
Hide navigation sidebar
Hide table of contents sidebar
[Skip to content](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/vacuity.html#furo-main-content)
Toggle site navigation sidebar
[Certora Prover Tutorials](https://docs.certora.com/projects/tutorials/en/latest/index.html)
Toggle Light / Dark / Auto color theme
Toggle table of contents sidebar
[ ![Light Logo](https://docs.certora.com/projects/tutorials/en/latest/_static/logo.svg) ![Dark Logo](https://docs.certora.com/projects/tutorials/en/latest/_static/logo.svg) Certora Prover Tutorials ](https://docs.certora.com/projects/tutorials/en/latest/index.html)
Contents:
  * [1. Background and Prerequisites](https://docs.certora.com/projects/tutorials/en/latest/lesson1_prerequisites/index.html)
Toggle navigation of 1. Background and Prerequisites
    * [1.1. Background](https://docs.certora.com/projects/tutorials/en/latest/lesson1_prerequisites/background.html)
    * [1.2. Introduction to predicate logic](https://docs.certora.com/projects/tutorials/en/latest/lesson1_prerequisites/propositional_logic.html)
    * [1.3. Introduction to formal verification](https://docs.certora.com/projects/tutorials/en/latest/lesson1_prerequisites/formal_verification.html)
  * [2. Getting Started](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/index.html)
Toggle navigation of 2. Getting Started
    * [2.1. Installation and Setup](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/installation.html)
    * [2.2. Technology Overview](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/overview.html)
    * [2.3. ERC20 Example - Basics](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/erc20_example.html)
    * [2.4. ERC20 Example - preconditions](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/preconditions.html)
    * [2.5. Parametric rules](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/parametric.html)
    * [2.6. Using config files](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/config_files.html)
    * [2.7. Vacuity](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/vacuity.html)
  * [3. Understanding violations](https://docs.certora.com/projects/tutorials/en/latest/lesson3_violations/index.html)
Toggle navigation of 3. Understanding violations
    * [3.1. Fixing ERC20 spec](https://docs.certora.com/projects/tutorials/en/latest/lesson3_violations/erc20_bugs.html)
    * [3.2. Borda count election](https://docs.certora.com/projects/tutorials/en/latest/lesson3_violations/borda_bugs.html)
    * [3.3. Reward Challenge : Missing Spec bounty](https://docs.certora.com/projects/tutorials/en/latest/lesson3_violations/reward_challenge.html)
  * [4. Invariants and Ghosts](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/index.html)
Toggle navigation of 4. Invariants and Ghosts
    * [4.1. Simple invariants examples](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/invariants/simple.html)
    * [4.2. Basic exercises](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/invariants/auction.html)
    * [4.3. Preserved blocks](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/invariants/preserved.html)
    * [4.4. Ghosts and hooks](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/ghosts/basics.html)
    * [4.5. Ghost exercises](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/ghosts/exercises.html)


  * [Index](https://docs.certora.com/projects/tutorials/en/latest/genindex.html)


[ Back to top ](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/vacuity.html)
Toggle Light / Dark / Auto color theme
Toggle table of contents sidebar
# 2.7. Vacuity[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/vacuity.html#vacuity "Link to this heading")
## Introduction[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/vacuity.html#introduction "Link to this heading")
A rule is called _vacuous_ if there are no computation paths satisfying the necessary requirements (excluding the rule’s assertions). The Prover can find no counter-examples for such rules, since there are no examples whatsoever for such rules. By default, the Prover will mark such rules as _verfied_ , but they are in fact meaningless.
The solution is to use the Prover’s built-in _rule sanity_. Adding `--rule_sanity basic` to the command line, or `"rule_sanity": "basic"` to the config file will cause the Prover to check if the rules being verified are vacuous.
## Simple Example[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/vacuity.html#simple-example "Link to this heading")
Here is a simple example for a vacuous rule, containing contradictory requirements.
```
rulesimpleVacuousRule(uint256x,uint256y){
// Contradictory requirement
require(x>y)&&(y>x);
assertfalse;// Should always fail
}

```

When running without `rule_sanity`, the Prover will mark this rule as _verified_ since it has no counter-example, even though the assertion can never be satisfied. When using `rule_sanity` the Prover will indicate this rule fails sanity checks.
## Reverting computation paths[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/vacuity.html#reverting-computation-paths "Link to this heading")
By default, the Prover ignores computation paths that result in a revert. So, by default the Prover considers only those computation paths where all Solidity `require` statements are satisfied. Moreover, any overflow or underflow paths are ignored (when using Solidity versions that revert on overflow and underflow).
To include computation paths that result in a revert, use the operator `@withrevert` when calling a Solidity function, e.g. `someFunction@withrevert(args)`. CVL has a builtin boolean variable `lastReverted` that is true if the _last_ Solidity function called reverted (whether it used `@withrevert` or not).
Note that if the call `someFunction@withrevert(args)` does revert, its return value will be arbitrary, and all Solidity variables will also revert.
Note
In [Ghosts and hooks](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/ghosts/basics.html#lesson4-ghosts-basics) we will learn about _ghost variables_ , which are roughly CVL global variables. When a Solidity function reverts, all ghost variables also revert.
## More examples[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/vacuity.html#more-examples "Link to this heading")
We’ll use the following simple contract, the code is found in [Vacuous.sol](https://github.com/Certora/tutorials-code/blob/master/lesson2_started/vacuity/Vacuous.sol).
```
pragma solidity^0.8.0;
/// @title Examples of vacuous rules
contractVacuous{
mapping(address=>uint256)publicamounts;
uint256public immutablemaximalAmount=1000;
functionadd(addressuser,uint256amount)publicreturns(uint256){
require(amounts[user]+amount<=maximalAmount);
amounts[user]+=amount;
returnamounts[user];
}
functionsub(addressuser,uint256amount)publicreturns(uint256){
amounts[user]-=amount;
returnamounts[user];
}
}

```

The following CVL examples are from [Vacuous.spec](https://github.com/Certora/tutorials-code/blob/master/lesson2_started/vacuity/Vacuous.spec). In the same folder there are also two config files for running this spec. One config file without `rule_sanity`: [Vacuous.conf](https://github.com/Certora/tutorials-code/blob/master/lesson2_started/vacuity/Vacuous.conf), while the other uses basic `rule_sanity`: [Vacuous_sanity.conf](https://github.com/Certora/tutorials-code/blob/master/lesson2_started/vacuity/Vacuous_sanity.conf).
### Vacuous rule[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/vacuity.html#vacuous-rule "Link to this heading")
The following rule is vacuous. It will be verified when running without `rule_sanity`.
```
rulesubtleVacuousRule(addressuser,uint256amount){
uint256userAmount=amounts(user);
requireamount>userAmount;
sub(user,amount);
assertfalse;// Should always fail
}

```

Do you understand why this rule is vacuous?
Answer
In the specified Solidity version, underflow will cause a revert. The `require` statement in the rule forces underflow in the Solidity `sub` function. In the specified Solidity compileer version, this underflow will cause a revert.
### Using withrevert[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/vacuity.html#using-withrevert "Link to this heading")
This is similar to the previous example, but here we call `sub` using the `@withrevert` operator. We assert that the function will always revert. This rule is correctly verified.
```
rulerevertingRule(addressuser,uint256amount){
uint256userAmount=amounts(user);
requireamount>userAmount;
sub@withrevert(user,amount);
assertlastReverted;
}

```

[ Next 3. Understanding violations ](https://docs.certora.com/projects/tutorials/en/latest/lesson3_violations/index.html) [ Previous 2.6. Using config files ](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/config_files.html)
Copyright © 2023, Certora, Inc 
Made with [Sphinx](https://www.sphinx-doc.org/) and [@pradyunsg](https://pradyunsg.me)'s [Furo](https://github.com/pradyunsg/furo)
On this page 
  * [2.7. Vacuity](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/vacuity.html)
    * [Introduction](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/vacuity.html#introduction)
    * [Simple Example](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/vacuity.html#simple-example)
    * [Reverting computation paths](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/vacuity.html#reverting-computation-paths)
    * [More examples](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/vacuity.html#more-examples)
      * [Vacuous rule](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/vacuity.html#vacuous-rule)
      * [Using withrevert](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/vacuity.html#using-withrevert)


