Contents Menu Expand Light mode Dark mode Auto light/dark mode Auto light/dark, in light mode Auto light/dark, in dark mode
Hide navigation sidebar
Hide table of contents sidebar
[Skip to content](https://docs.certora.com/projects/tutorials/en/latest/lesson3_violations/reward_challenge.html#furo-main-content)
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


[ Back to top ](https://docs.certora.com/projects/tutorials/en/latest/lesson3_violations/reward_challenge.html)
Toggle Light / Dark / Auto color theme
Toggle table of contents sidebar
# 3.3. Reward Challenge : Missing Spec bounty[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson3_violations/reward_challenge.html#reward-challenge-missing-spec-bounty "Link to this heading")
## Goal[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson3_violations/reward_challenge.html#goal "Link to this heading")
Find a buggy version of Borda that is not caught by the given rules. The buggy version must implement the [IBorda](https://github.com/Certora/tutorials-code/blob/master/lesson3_violations/Borda/IBorda.sol) interface and the bug must be a _high severity bug_ so that there is an effect on the outcome of the voting.
## Challenge rules[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson3_violations/reward_challenge.html#challenge-rules "Link to this heading")
To submit a Missing Spec you will need the following:
  1. An original buggy implementation of [IBorda](https://github.com/Certora/tutorials-code/blob/master/lesson3_violations/Borda/IBorda.sol), named **BordaNewBug.sol** such that:
     * The bug in _BordaNewBug.sol_ is not caught by the current set of rules
     * The bug is not caught by previously reported missing rules
     * The bug has an impact on the voting
     * The buggy _BordaNewBug.sol_ is a full implementation of the [IBorda](https://github.com/Certora/tutorials-code/blob/master/lesson3_violations/Borda/IBorda.sol) interface and is implemented with the `_points` and `_voted` mappings as in the original [Borda.sol](https://github.com/Certora/tutorials-code/blob/master/lesson3_violations/Borda/Borda.sol)
     * The buggy _BordaNewBug.sol_ may contain additional functions and fields
  2. A rule or invariant named `BordaMissingRule`, placed in a file called _BordaMissingRule.spec_ , that:
     * Catches the bug by showing a violation on the new buggy version _BordaNewBug.sol_
     * Passes on the original [Borda.sol](https://github.com/Certora/tutorials-code/blob/master/lesson3_violations/Borda/Borda.sol) implementation, demonstrating that it is a property of a correct implementation of Borda
  3. The following reports:
     * A run of the new _BordaMissingRule.spec_ on the original [Borda.sol](https://github.com/Certora/tutorials-code/blob/master/lesson3_violations/Borda/Borda.sol) that is verified
     * A run of [Borda.spec](https://github.com/Certora/tutorials-code/blob/master/lesson3_violations/Borda/Borda.spec) on _BordaNewBug.sol_ showing the existing spec misses the bug
     * Reports of all previously acknowledged bounty specs on _BordaNewBug.sol_ , these specs will be found in the [bounty_specs](https://github.com/Certora/tutorials-code/tree/master/lesson3_violations/Borda/bounty_specs) folder
     * A run of _BordaMissingRule.spec_ on _BordaNewBug.sol_ showing your rule catches the bug


## Submission[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson3_violations/reward_challenge.html#submission "Link to this heading")
First, prepare a PR for the [Certora Tutorials Code repository](https://github.com/Certora/tutorials-code) containing the two new files _BordaNewBug.sol_ and _BordaMissingRule.spec_. Second, in create an [Issue](https://docs.github.com/en/issues) in [Certora Tutorials Code repository](https://github.com/Certora/tutorials-code) containing links to the PR and to all the report runs mentioned above.
## Rewards[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson3_violations/reward_challenge.html#rewards "Link to this heading")
  * Per original missing spec: 200 USDC
  * Total Reward: 1000 USDC (for the first five acknowledged instances)


## Update[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson3_violations/reward_challenge.html#update "Link to this heading")
This challenge has finished on Oct 2nd, 2023.
There are more than five missing rules, check your solution against [bounty_specs](https://github.com/Certora/tutorials-code/tree/master/lesson3_violations/Borda/bounty_specs) folder
[ Next 4. Invariants and Ghosts ](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/index.html) [ Previous 3.2. Borda count election ](https://docs.certora.com/projects/tutorials/en/latest/lesson3_violations/borda_bugs.html)
Copyright © 2023, Certora, Inc 
Made with [Sphinx](https://www.sphinx-doc.org/) and [@pradyunsg](https://pradyunsg.me)'s [Furo](https://github.com/pradyunsg/furo)
On this page 
  * [3.3. Reward Challenge : Missing Spec bounty](https://docs.certora.com/projects/tutorials/en/latest/lesson3_violations/reward_challenge.html)
    * [Goal](https://docs.certora.com/projects/tutorials/en/latest/lesson3_violations/reward_challenge.html#goal)
    * [Challenge rules](https://docs.certora.com/projects/tutorials/en/latest/lesson3_violations/reward_challenge.html#challenge-rules)
    * [Submission](https://docs.certora.com/projects/tutorials/en/latest/lesson3_violations/reward_challenge.html#submission)
    * [Rewards](https://docs.certora.com/projects/tutorials/en/latest/lesson3_violations/reward_challenge.html#rewards)
    * [Update](https://docs.certora.com/projects/tutorials/en/latest/lesson3_violations/reward_challenge.html#update)


