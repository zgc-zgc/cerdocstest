Contents Menu Expand Light mode Dark mode Auto light/dark mode Auto light/dark, in light mode Auto light/dark, in dark mode
Hide navigation sidebar
Hide table of contents sidebar
[Skip to content](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/preconditions.html#furo-main-content)
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


[ Back to top ](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/preconditions.html)
Toggle Light / Dark / Auto color theme
Toggle table of contents sidebar
# 2.4. ERC20 Example - preconditions[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/preconditions.html#erc20-example-preconditions "Link to this heading")
We demonstrate how sometimes preconditions are needed to avoid unwanted over-approximation. We use the same [ERC20.sol](https://github.com/Certora/tutorials-code/blob/master/lesson2_started/erc20/ERC20.sol) contract as before.
## Total supply rule[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/preconditions.html#total-supply-rule "Link to this heading")
Consider the following property: _The total supply of the token_ \\(\geq\\) _the balance of any single user._
This property is asserted in the rule `totalSupplyAfterMint` of [TotalGreaterThanUser.spec](https://github.com/Certora/tutorials-code/blob/master/lesson2_started/erc20/TotalGreaterThanUser.spec). In this case the assertion is only that the property holds after `mint`:
```
/// @title Total supply after mint is at least the balance of the receiving account
ruletotalSupplyAfterMint(addressaccount,uint256amount){
enve;
mint(e,account,amount);
uint256userBalanceAfter=balanceOf(account);
uint256totalAfter=totalSupply();
// Verify that the total supply of the system is at least the current balance of the account.
asserttotalAfter>=userBalanceAfter,"total supply is less than a user's balance";
}

```

Let’s run this rule:
```
certoraRunERC20.sol--verifyERC20:TotalGreaterThanUser.spec--solcsolc8.0--ruletotalSupplyAfterMint

```

Tip
The `--rule` argument allows running one specific rule from the entire spec file.
## Helper variables[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/preconditions.html#helper-variables "Link to this heading")
As you discovered, the Prover finds that the rule is violated. Understanding the counter-example in this case can be difficult. Adding additional variables to the rule can help understand the counter-example.
Try adding the _helper variables_ `userBalanceBefore` and `totalBefore` before calling `mint`. Re-run the rule and see if you now understand the counter-example.
Hint
Try adding the following lines before calling `mint`:
```
uint256userBalanceBefore=balanceOf(account);
uint256totalBefore=totalSupply();

```

## Over-approximation[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/preconditions.html#over-approximation "Link to this heading")
The Prover assumes _all possible input values_ as a starting state, even those that can never be reached. In other words, the Prover _over-approximates_ the possible states of the system. This over-approximation protects the Prover from erroneously claiming that a rule passes. But it may result sometimes in wrong violations, like this case.
Here, the rule is violated when the initial state’s `totalSupply` is less than the current balance of `account`. Even though such a state is unreachable by any route of action by any user, the tool still considers this initial state as a valid state.
This is not a mistake but a designed behavior of the Certora Prover. It’s designed to over-approximate states to avoid missing paths that lead to bugs (false positives). However, doing so leads to evaluating states that might not be reachable (false negatives), as shown in this example. In the upcoming lessons, we will learn how to prove that such states are never feasible.
## Preconditions[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/preconditions.html#preconditions "Link to this heading")
By adding _preconditions_ , one can eliminate infeasible states and put constraints on values. The Rule `totalSupplyAfterMintWithPrecondition` is a copy of `totalSupplyAfterMint` with an additional constraint, shown in emphasis below:
```
/** @title Total supply after mint is at least the balance of the receiving account, with
 * precondition.
 */
ruletotalSupplyAfterMintWithPrecondition(addressaccount,uint256amount){
enve;
// Assume that in the current state before calling mint, the total supply of the 
// system is at least the user balance.
uint256userBalanceBefore=balanceOf(account);
uint256totalBefore=totalSupply();
requiretotalBefore>=userBalanceBefore;
mint(e,account,amount);
uint256userBalanceAfter=balanceOf(account);
uint256totalAfter=totalSupply();
// Verify that the total supply of the system is at least the current balance of the account.
asserttotalAfter>=userBalanceAfter,"total supply is less than a user's balance ";
}

```

The Prover will now assume that in the initial state, i.e. before calling `mint()`, the total supply is at least the user’s balance. Now run the rule `totalSupplyAfterMintWithPrecondition`:
```
certoraRunERC20.sol--verifyERC20:TotalGreaterThanUser.spec--solcsolc8.0--ruletotalSupplyAfterMintWithPrecondition--msg"running with precondition"

```

Tip
The `--msg` flag adds a message description to your run. It can help you recognize a specific run. You will see the message in the run results, and in the jobs list ([prover.certora.com](https://prover.certora.com/)).
## A note on CVL variables[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/preconditions.html#a-note-on-cvl-variables "Link to this heading")
Unlike Solidity, in CVL an uninitialized variable can have _any_ value, though its possible values are constrained by CVL `require` statements in the rule. Additionally, CVL variables are _immutable_ , so they cannot be changed in the course of the rule.
We will later meet another kind of variables in CVL which can be modified. These are called _ghost_ variables and we will meet them in [Invariants and Ghosts](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/index.html#lesson4-invariants).
[ Next 2.5. Parametric rules ](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/parametric.html) [ Previous 2.3. ERC20 Example - Basics ](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/erc20_example.html)
Copyright © 2023, Certora, Inc 
Made with [Sphinx](https://www.sphinx-doc.org/) and [@pradyunsg](https://pradyunsg.me)'s [Furo](https://github.com/pradyunsg/furo)
On this page 
  * [2.4. ERC20 Example - preconditions](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/preconditions.html)
    * [Total supply rule](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/preconditions.html#total-supply-rule)
    * [Helper variables](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/preconditions.html#helper-variables)
    * [Over-approximation](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/preconditions.html#over-approximation)
    * [Preconditions](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/preconditions.html#preconditions)
    * [A note on CVL variables](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/preconditions.html#a-note-on-cvl-variables)


