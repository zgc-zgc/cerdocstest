Contents Menu Expand Light mode Dark mode Auto light/dark mode Auto light/dark, in light mode Auto light/dark, in dark mode
Hide navigation sidebar
Hide table of contents sidebar
[Skip to content](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/installation.html#furo-main-content)
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


[ Back to top ](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/installation.html)
Toggle Light / Dark / Auto color theme
Toggle table of contents sidebar
# 2.1. Installation and Setup[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/installation.html#installation-and-setup "Link to this heading")
## Prover installation[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/installation.html#prover-installation "Link to this heading")
Refer to the installation instructions for the Certora Prover described in: [Installation of Certora Prover](https://docs.certora.com/en/latest/docs/user-guide/getting-started/install.html). Note you will need an appropriate _Java_ version for the local type-checking to work, refer to the [Installation of Certora Prover](https://docs.certora.com/en/latest/docs/user-guide/getting-started/install.html) instructions.
You will also need solidity compiler versions 0.7.0, 0.8.0, 0.8.1, and 0.8.13 for this course. You can either download these to a folder included in your `PATH`, or use some other tool allowing to switch between solidity compilers, such as [solc-select](https://github.com/crytic/solc-select).
## Recommended IDE[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/installation.html#recommended-ide "Link to this heading")
### VSCode[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/installation.html#vscode "Link to this heading")
If you are using [VSCode](https://code.visualstudio.com/) we recommend using the following two VSCode extensions: 

[Certora Verification Language LSP](https://marketplace.visualstudio.com/items?itemName=Certora.evmspec-lsp)
    
This extension is found in the VSCode extensions/marketplace. It provides syntactic support for the Certora Verification Language (CVL) - the language in which we will be writing specifications. 

[Ethereum Security Bundle](https://marketplace.visualstudio.com/items?itemName=tintinweb.ethereum-security-bundle)
    
This extension, by tintinweb, on is also found on the VSCode extensions/marketplace. It provides support for Solidity contracts.
### Other IDEs[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/installation.html#other-ides "Link to this heading")
As part of the everyday work, you’ll need:
  1. A convenient access to the terminal
  2. An editor for CVL, preferably one with an appropriate extension providing syntax highlighting and an LSP (Language Server Protocol) for CVL
  3. A solidity editor, also preferably with extension that has adequate support for editing solidity code.


We recommend using VSCode as it supports all the three requirements. You may however, choose to work with any other (textual) editor of your choice or split the work between several editors, however be aware that the LSP is currently only supported through VSCode.
## Course Setup[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/installation.html#course-setup "Link to this heading")
Clone our [Certora Tutorials Code repository](https://github.com/Certora/tutorials-code), this includes all the code examples used in the tutorials.
Important
Don’t forget to update your cloned repository often.
## Additional resources[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/installation.html#additional-resources "Link to this heading")
  * Register to our [Discord Server](https://discord.gg/Z9wQfRqZYY/).
  * Use the #help-desk and #tutorials-questions channels to post questions and get answers.


## Solutions[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/installation.html#solutions "Link to this heading")
We’ve added solutions to some of the more difficult exercises. You can find them in the [solutions folder](https://github.com/Certora/tutorials-code/tree/master/solutions).
[ Next 2.2. Technology Overview ](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/overview.html) [ Previous 2. Getting Started ](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/index.html)
Copyright © 2023, Certora, Inc 
Made with [Sphinx](https://www.sphinx-doc.org/) and [@pradyunsg](https://pradyunsg.me)'s [Furo](https://github.com/pradyunsg/furo)
On this page 
  * [2.1. Installation and Setup](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/installation.html)
    * [Prover installation](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/installation.html#prover-installation)
    * [Recommended IDE](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/installation.html#recommended-ide)
      * [VSCode](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/installation.html#vscode)
      * [Other IDEs](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/installation.html#other-ides)
    * [Course Setup](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/installation.html#course-setup)
    * [Additional resources](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/installation.html#additional-resources)
    * [Solutions](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/installation.html#solutions)


