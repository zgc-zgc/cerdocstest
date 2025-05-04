Contents Menu Expand Light mode Dark mode Auto light/dark mode Auto light/dark, in light mode Auto light/dark, in dark mode
Hide navigation sidebar
Hide table of contents sidebar
[Skip to content](https://docs.certora.com/projects/tutorials/en/latest/lesson3_violations/erc20_bugs.html#furo-main-content)
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


[ Back to top ](https://docs.certora.com/projects/tutorials/en/latest/lesson3_violations/erc20_bugs.html)
Toggle Light / Dark / Auto color theme
Toggle table of contents sidebar
# 3.1. Fixing ERC20 spec[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson3_violations/erc20_bugs.html#fixing-erc20-spec "Link to this heading")
Writing specifications is as challenging as writing code, and may contain errors. Let’s continue with the [ERC20](https://ethereum.org/en/developers/docs/standards/tokens/erc-20/) example, which can be found in the [ERC20 folder](https://github.com/Certora/tutorials-code/tree/master/lesson3_violations/ERC20). In this folder you will find:
  * [ERC20.spec](https://github.com/Certora/tutorials-code/blob/master/lesson3_violations/ERC20/ERC20.spec) - the spec file to fix
  * [ERC20.sol](https://github.com/Certora/tutorials-code/blob/master/lesson3_violations/ERC20/ERC20.sol) - a well known implementation of ERC20
  * [IERC20.sol](https://github.com/Certora/tutorials-code/blob/master/lesson3_violations/ERC20/IERC20.sol) - the main interface and description of the ERC20 standard
  * [IERC20Metadata.sol](https://github.com/Certora/tutorials-code/blob/master/lesson3_violations/ERC20/IERC20Metadata.sol) - an interface for ERC20 metadata


Use the Certora Prover’s results to find the mistakes in the faulty implementations of the spec and fix the rules. Run `certoraRun ERC20.conf` and understand the violations, then fix the spec to get all the rules passing
## Important: Optimistic loop[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson3_violations/erc20_bugs.html#important-optimistic-loop "Link to this heading")
When running the spec [ERC20.spec](https://github.com/Certora/tutorials-code/blob/master/lesson3_violations/ERC20/ERC20.spec) you must add `"optimistic_loop": true` to your config file, or use `--optimistic_loop` flag if running from command line. Otherwise, you will get a violation whenever the Prover encounters the getters `name()` and `symbol()`. The violation occurs because the Prover uses loops to handle strings, or any dynamic array. Loops require special care and handling which we will address in a later lesson. For now, simply use this flag whenever you have a string.
## Hints for ERC20[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson3_violations/erc20_bugs.html#hints-for-erc20 "Link to this heading")
Hint for `integrityOfTransferFrom`
Prover takes into account all cases, including a non-typical one. Look at the arguments to `transferFrom`. The spec must cover all cases either by adding another requirement that excludes those particular cases or weakening the assert to hold onto those cases
Hint for `balanceChangesFromCertainFunctions`
This rule fails for only one function. What is missing in the assert?
Hint for `onlyOwnersMayChangeTotalSupply`
If a rule fails for multiple functions choose the simplest function and look at the violation. Look at the assert statement and remember the definition of implication.
Hint 1 for `doesNotAffectAThirdPartyBalance`
Violations can occur on a specific set of values. Look for variables that have the same value.
Hint 2 for `doesNotAffectAThirdPartyBalance`
`thirdParty` is not constrained to be different than the `from` argument in transfer.
Hint
A fixed `ERC20` spec can be found in the solutions folder at [ERC20Fixed.sol](https://github.com/Certora/tutorials-code/blob/master/solutions/lesson3_violations/ERC20/ERC20Fixed.spec).
[ Next 3.2. Borda count election ](https://docs.certora.com/projects/tutorials/en/latest/lesson3_violations/borda_bugs.html) [ Previous 3. Understanding violations ](https://docs.certora.com/projects/tutorials/en/latest/lesson3_violations/index.html)
Copyright © 2023, Certora, Inc 
Made with [Sphinx](https://www.sphinx-doc.org/) and [@pradyunsg](https://pradyunsg.me)'s [Furo](https://github.com/pradyunsg/furo)
On this page 
  * [3.1. Fixing ERC20 spec](https://docs.certora.com/projects/tutorials/en/latest/lesson3_violations/erc20_bugs.html)
    * [Important: Optimistic loop](https://docs.certora.com/projects/tutorials/en/latest/lesson3_violations/erc20_bugs.html#important-optimistic-loop)
    * [Hints for ERC20](https://docs.certora.com/projects/tutorials/en/latest/lesson3_violations/erc20_bugs.html#hints-for-erc20)


