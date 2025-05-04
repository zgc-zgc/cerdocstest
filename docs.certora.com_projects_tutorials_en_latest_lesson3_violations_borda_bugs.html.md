Contents Menu Expand Light mode Dark mode Auto light/dark mode Auto light/dark, in light mode Auto light/dark, in dark mode
Hide navigation sidebar
Hide table of contents sidebar
[Skip to content](https://docs.certora.com/projects/tutorials/en/latest/lesson3_violations/borda_bugs.html#furo-main-content)
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


[ Back to top ](https://docs.certora.com/projects/tutorials/en/latest/lesson3_violations/borda_bugs.html)
Toggle Light / Dark / Auto color theme
Toggle table of contents sidebar
# 3.2. Borda count election[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson3_violations/borda_bugs.html#borda-count-election "Link to this heading")
This example of a [Borda count election](https://en.wikipedia.org/wiki/Borda_count) is found in the [Borda folder](https://github.com/Certora/tutorials-code/tree/master/lesson3_violations/Borda). In the [IBorda.sol](https://github.com/Certora/tutorials-code/blob/master/lesson3_violations/Borda/IBorda.sol) file, you will find a description of the system and the interface that should be implemented by the contracts.
Read [Borda.sol](https://github.com/Certora/tutorials-code/blob/master/lesson3_violations/Borda/Borda.sol) and [Borda.spec](https://github.com/Certora/tutorials-code/blob/master/lesson3_violations/Borda/Borda.spec) to understand the system and the properties. You might encounter new features of CVL which later lessons address. The goal in this lesson is to practice understanding violations.
Tip
The bugs are relatively simple and can easily be found manually. Avoid looking for bugs manually before running the Prover. Instead, follow the Prover’s counter-examples to locate the bugs. Counter-examples may vary from one run to the other, we provide links and hints to a run which may differ from your own run.
Look at the following links (or run the provided conf files) of four faulty implementations and understand the violation.
  1. Results of verification [Borda Bug1 Report](https://prover.certora.com/output/40726/c4d95ca85e5a40459fe0dd79d8b0c501/?anonymousKey=ac4dcc3c47656256210635dbb91666def249c1a5) , run with [BordaBug1.conf](https://github.com/Certora/tutorials-code/blob/master/lesson3_violations/Borda/BordaBug1.conf)
  2. Results of verification [Borda Bug2 Report](https://prover.certora.com/output/40726/524ab91545cb4922b58cf8828bc5a520/?anonymousKey=b3c2f343ab6fb5784449cf291b6db8cc62f000a6) , run with [BordaBug2.conf](https://github.com/Certora/tutorials-code/blob/master/lesson3_violations/Borda/BordaBug2.conf)
  3. Results of verification [Borda Bug3 Report](https://prover.certora.com/output/40726/e55818685ef548ce84598140f547dd33/?anonymousKey=3ebd1c35d8ce0c6a545d99bc60582474a7a54c8a) , run with [BordaBug3.conf](https://github.com/Certora/tutorials-code/blob/master/lesson3_violations/Borda/BordaBug3.conf)
  4. Results of verification [Borda Bug4 Report](https://prover.certora.com/output/40726/05d705362db141318e5cbae1dca763f7/?anonymousKey=1421d1e2b4702a538a8cc3690dd6160046527094) , run with [BordaBug4.conf](https://github.com/Certora/tutorials-code/blob/master/lesson3_violations/Borda/BordaBug4.conf)


Tip
Use the file tree view (third icon on the left panel) to view the files in this verification run to check your conclusions.
## Hints for Borda[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson3_violations/borda_bugs.html#hints-for-borda "Link to this heading")
Hint for BordaBug1.sol
Start with the failing assert of `integrityPoints`, find the term that is false:
> ![../_images/BordaBug1Step1.png](https://docs.certora.com/projects/tutorials/en/latest/_images/BordaBug1Step1.png)
Next, look at the values before the call to `vote()` either in the Global State of the initial state the rule started with, or follow the return values from the calls to `points()` before the call to `vote()`.
![../_images/BordaBug1Step2.jpg](https://docs.certora.com/projects/tutorials/en/latest/_images/BordaBug1Step2.jpg)
Have you noticed the values of `s` and `f`? Use the variables value view at the right hand side.
Hint for BordaBug2.sol
Multiple rules fail on this version of the code. Take a look at `noEffect`, a parametric rule, which has an entry for each checked method. The rule fails on `vote()`. Notice the unexpected change to `points`. You can drill into the execution of `vote()`. See `store` and `load` operations as well as internal function calls. Does anything look unexpected from a correct implementation of vote()?
![../_images/BordaBug2Step1.jpg](https://docs.certora.com/projects/tutorials/en/latest/_images/BordaBug2Step1.jpg)
Hint for BordaBug3.sol
Understanding reverting condition might be tricky, as some of them are compiler-generated. The Prover provides as much information as possible. Here it is clear.
![../_images/BordaBug3.jpg](https://docs.certora.com/projects/tutorials/en/latest/_images/BordaBug3.jpg)
Hint for BordaBug4.sol
One of the nice features of the Certora Prover is that parametric rules and invariants are checked against all external functions. A newly added function is checked without any modification of the spec.
The best way to understand the coverage of the spec is via bug injection. Our [CertoraMutate and Gambit](https://docs.certora.com/en/latest/docs/gambit/index.html) tools help performing this task. According to the [Borda mutation report](https://mutation-testing.certora.com/?id=8f778b32-ecd8-4ebd-9e6a-d39904873cfa&anonymousKey=4e8e7f60-43f5-4e8b-8edc-0d8867195477) the coverage is 100%, which means that all mutants were caught by at least one rule. However, the type of mutants Gambit generates is limited and there might be an injected bug that will point at a missing rule.
[ Next 3.3. Reward Challenge : Missing Spec bounty ](https://docs.certora.com/projects/tutorials/en/latest/lesson3_violations/reward_challenge.html) [ Previous 3.1. Fixing ERC20 spec ](https://docs.certora.com/projects/tutorials/en/latest/lesson3_violations/erc20_bugs.html)
Copyright © 2023, Certora, Inc 
Made with [Sphinx](https://www.sphinx-doc.org/) and [@pradyunsg](https://pradyunsg.me)'s [Furo](https://github.com/pradyunsg/furo)
On this page 
  * [3.2. Borda count election](https://docs.certora.com/projects/tutorials/en/latest/lesson3_violations/borda_bugs.html)
    * [Hints for Borda](https://docs.certora.com/projects/tutorials/en/latest/lesson3_violations/borda_bugs.html#hints-for-borda)


