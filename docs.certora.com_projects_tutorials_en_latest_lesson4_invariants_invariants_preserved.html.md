Contents Menu Expand Light mode Dark mode Auto light/dark mode Auto light/dark, in light mode Auto light/dark, in dark mode
Hide navigation sidebar
Hide table of contents sidebar
[Skip to content](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/invariants/preserved.html#furo-main-content)
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


[ Back to top ](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/invariants/preserved.html)
Toggle Light / Dark / Auto color theme
Toggle table of contents sidebar
# 4.3. Preserved blocks[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/invariants/preserved.html#preserved-blocks "Link to this heading")
Sometimes invariants need additional assumptions or other invariants for the Prover to successfully verify them. [Preserved blocks](https://docs.certora.com/en/latest/docs/cvl/invariants.html#preserved-blocks) allow us to add these assumptions to the invariants.
## Worked example[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/invariants/preserved.html#worked-example "Link to this heading")
Here is an example explaining the need for preserved blocks and their use. The file [DebtToken.sol](https://github.com/Certora/tutorials-code/blob/master/lesson4_invariants/partial_debt_token/DebtToken.sol) contains a partial implementation of a debt token. The contract keeps track of both the balances of the users and the values of their collaterals. Most importantly, the contract should ensure that a user’s balance _never exceeds_ their collateral value.
### Failed spec[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/invariants/preserved.html#failed-spec "Link to this heading")
To verify this property, we write a short spec [FailedDebtToken.spec](https://github.com/Certora/tutorials-code/blob/master/lesson4_invariants/partial_debt_token/FailedDebtToken.spec) with a single invariant shown below
FailedDebtToken.spec[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/invariants/preserved.html#id2 "Link to this code")
```
methods{
functionbalanceOf(address)externalreturns(uint256)envfree;
functioncollateralOf(address)externalreturns(uint256)envfree;
}

/// @title Collateral is never less than the balance
invariantcollateralCoversBalance(addressaccount)
collateralOf(account)>=balanceOf(account);

```

Running this spec (using [FailedDebtToken.conf](https://github.com/Certora/tutorials-code/blob/master/lesson4_invariants/partial_debt_token/FailedDebtToken.conf) ) results in a violation. Try to understand the violation for yourself.
#### Violation[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/invariants/preserved.html#violation "Link to this heading")
The violation occurs in the “induction step” for the function `transferDebt`.
  1. At the onset (the _pre-state_) we have two addresses: `account` for which we are proving the invariant, and another address named `another`. These are their values at the _pre-state_ :
Storage at _pre-state_[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/invariants/preserved.html#id3 "Link to this table") `address` | `balanceOf` | `_collateralValue`  
---|---|---  
`account` | `1` | `2`  
`another` | `2` | `0`  
  2. The invariant obviously holds in this _pre-state_ :
```
2==collateralOf(account)>=balanceOf(account)==1

```

  3. Execute `transferDebt(account)` where `msg.sender` is `another`.
  4. The final state after executing `transferDebt(account)` is:
Storage after `transferDebt`[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/invariants/preserved.html#id4 "Link to this table") `address` | `balanceOf` | `_collateralValue`  
---|---|---  
`account` | `3` | `2`  
`another` | `0` | `0`  


The final state clearly violates the invariant since:
```
2==collateralOf(account)<balanceOf(account)==3

```

### Correct invariant[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/invariants/preserved.html#correct-invariant "Link to this heading")
The problem with the [Violation](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/invariants/preserved.html#debt-invariant-violation) above is that the address `another` does not satisfy the invariant at start, i.e. at the pre-state. We need require that it satisfies the invariant at the start as well. Here is the syntax to do so, from [DebtToken.spec](https://github.com/Certora/tutorials-code/blob/master/lesson4_invariants/partial_debt_token/DebtToken.spec):
DebtToken.spec[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/invariants/preserved.html#id5 "Link to this code")
```
/// @title Collateral is never less than the balance
invariantcollateralCoversBalance(addressaccount)
collateralOf(account)>=balanceOf(account)
{
preservedtransferDebt(addressrecipient)with(enve)
{
requireInvariantcollateralCoversBalance(e.msg.sender);
}
}

```

Run this spec using [DebtToken.conf](https://github.com/Certora/tutorials-code/blob/master/lesson4_invariants/partial_debt_token/DebtToken.conf), and you will find the rule is verified.
### Important notes[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/invariants/preserved.html#important-notes "Link to this heading") 

Why not use `require`?
    
Using a `requireInvariant` statement is sound, provided we prove the required invariant. On the other hand, a `require` statement can be a source of _unsoundness_ , meaning it can cause us to miss violations. 

Isn’t `requireInvariantcollateralCoversBalance...` using what you’re trying to prove?
    
The answer is no. We’re basically using the induction assumption for another address. The section [Invariants and induction](https://docs.certora.com/en/latest/docs/cvl/invariants.html#invariants-and-induction) expounds on that. 

What is the `enve` doing here?
    
The function `transferDebt` is not `envfree`, so when the Certora Prover calls `transferDebt` it uses some environment. The syntax `with(enve)` allows us to access and use this environment inside the preserved block. For more information, see [Preserved blocks](https://docs.certora.com/en/latest/docs/cvl/invariants.html#preserved-blocks).
### Default preserved block[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/invariants/preserved.html#default-preserved-block "Link to this heading")
One can add a general preserved block, that will be applied by default (i.e. if no other preserved block holds). The syntax is simple:
```
invariantsomeInvariant()
// Invariant condition
{
preserved{
// Default preserved block
}
// Additional preserved blocks
}

```

## Funds managers exercise[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/invariants/preserved.html#funds-managers-exercise "Link to this heading")
This is an exercise for using preserved blocks and `requireInvariant` statements in invariants.
### Background[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/invariants/preserved.html#background "Link to this heading")
The [IManager](https://github.com/Certora/tutorials-code/blob/master/lesson4_invariants/manager/IManager.sol) is a rudimentary interface for keeping track of managers for funds, where:
  * A _manager_ is simply an `address`
  * A _fund_ is identified by `uint256fundId`
  * Every fund must have a _unique_ manager
  * To change managers:
    1. The current manager must set their successor as the _pending manager_.
    2. The pending manager must then _claim management_ using the `claimManagement` method.


### Exercises[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/invariants/preserved.html#exercises "Link to this heading")
In the folder [manager](https://github.com/Certora/tutorials-code/tree/master/lesson4_invariants/manager) are three implementations of the [IManager](https://github.com/Certora/tutorials-code/blob/master/lesson4_invariants/manager/IManager.sol) interface. One is correct and the others are buggy.
  * Write an invariant verifying that no two funds have the same manager.
  * Make sure your invariant is sound. Remember `requireInvariant` in preserved blocks is sound (provided you also prove the required invariant). See [Invariants and induction](https://docs.certora.com/en/latest/docs/cvl/invariants.html#invariants-and-induction).
  * Test your invariant by running it on the implementations and finding the bugs.


### Hints[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/invariants/preserved.html#hints "Link to this heading")
Hint
You may need to prove that a fund’s manager is active.
Hint
The additional invariants you’ll need may require the invariant you’re trying to prove. This is ok when done correctly, see [Invariants and induction](https://docs.certora.com/en/latest/docs/cvl/invariants.html#invariants-and-induction).
Solution
A full solution is available in [Manager_unique.spec](https://github.com/Certora/tutorials-code/blob/master/solutions/lesson4_invariants/manager/Manager_unique.spec).
[ Next 4.4. Ghosts and hooks ](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/ghosts/basics.html) [ Previous 4.2. Basic exercises ](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/invariants/auction.html)
Copyright © 2023, Certora, Inc 
Made with [Sphinx](https://www.sphinx-doc.org/) and [@pradyunsg](https://pradyunsg.me)'s [Furo](https://github.com/pradyunsg/furo)
On this page 
  * [4.3. Preserved blocks](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/invariants/preserved.html)
    * [Worked example](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/invariants/preserved.html#worked-example)
      * [Failed spec](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/invariants/preserved.html#failed-spec)
        * [Violation](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/invariants/preserved.html#violation)
      * [Correct invariant](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/invariants/preserved.html#correct-invariant)
      * [Important notes](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/invariants/preserved.html#important-notes)
      * [Default preserved block](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/invariants/preserved.html#default-preserved-block)
    * [Funds managers exercise](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/invariants/preserved.html#funds-managers-exercise)
      * [Background](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/invariants/preserved.html#background)
      * [Exercises](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/invariants/preserved.html#exercises)
      * [Hints](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/invariants/preserved.html#hints)


