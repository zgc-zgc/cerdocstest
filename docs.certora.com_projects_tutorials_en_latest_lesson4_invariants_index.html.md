Contents Menu Expand Light mode Dark mode Auto light/dark mode Auto light/dark, in light mode Auto light/dark, in dark mode
Hide navigation sidebar
Hide table of contents sidebar
[Skip to content](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/index.html#furo-main-content)
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


[ Back to top ](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/index.html)
Toggle Light / Dark / Auto color theme
Toggle table of contents sidebar
# 4. Invariants and Ghosts[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/index.html#invariants-and-ghosts "Link to this heading")
This lesson walks you through using _invariants_ in CVL specs, and using _ghost variables_ with invariants. An excellent exposition of invariants is given in the [Invariants Documentation](https://docs.certora.com/en/latest/docs/cvl/invariants.html), and the sections [Writing an invariant as a rule](https://docs.certora.com/en/latest/docs/cvl/invariants.html#writing-an-invariant-as-a-rule) and [Invariants and induction](https://docs.certora.com/en/latest/docs/cvl/invariants.html#invariants-and-induction) are particularly illuminating. For introduction to invariants read the [Invariants Overview](https://docs.certora.com/en/latest/docs/cvl/invariants.html#overview) section.
The second half of this lesson deals with _ghost variables_. Ghost variables are additional variables defined in the spec. We can use them to keep track of various actions occurring in the code. There is a basic introduction to ghost variables in the [Ghosts Documentation](https://docs.certora.com/en/latest/docs/cvl/ghosts.html).
Contents:
  1. [Simple invariants examples](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/invariants/simple.html#lesson4-invariants-simple-examples) – simple invariant examples, including the illuminating [Ball Game](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/invariants/simple.html#ball-game-video) example
  2. [Basic exercises](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/invariants/auction.html#lesson4-invariants-auction) – basic invariants exercises
  3. [Preserved blocks](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/invariants/preserved.html#lesson4-invariants-preserved) – teaches you how to use preserved blocks and `requireInvariant` statements
  4. [Ghosts and hooks](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/ghosts/basics.html#lesson4-ghosts-basics) – the basics of using ghosts with hooks, focusing on their use in invariants
  5. [Ghost exercises](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/ghosts/exercises.html#lesson4-ghost-excercises) – contains several exercises for ghosts and invariants


[ Next 4.1. Simple invariants examples ](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/invariants/simple.html) [ Previous 3.3. Reward Challenge : Missing Spec bounty ](https://docs.certora.com/projects/tutorials/en/latest/lesson3_violations/reward_challenge.html)
Copyright © 2023, Certora, Inc 
Made with [Sphinx](https://www.sphinx-doc.org/) and [@pradyunsg](https://pradyunsg.me)'s [Furo](https://github.com/pradyunsg/furo)
