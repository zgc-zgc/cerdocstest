Contents Menu Expand Light mode Dark mode Auto light/dark mode Auto light/dark, in light mode Auto light/dark, in dark mode
Hide navigation sidebar
Hide table of contents sidebar
[Skip to content](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/invariants/auction.html#furo-main-content)
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


[ Back to top ](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/invariants/auction.html)
Toggle Light / Dark / Auto color theme
Toggle table of contents sidebar
# 4.2. Basic exercises[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/invariants/auction.html#basic-exercises "Link to this heading")
## ERC20[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/invariants/auction.html#erc20 "Link to this heading")
[ERC20.sol](https://github.com/Certora/tutorials-code/blob/master/lesson4_invariants/erc20/ERC20.sol) contains an ERC20 implementation. Write an invariant for ERC20 verifying that `address(0)` always has zero balance. Run the invariant on [ERC20.sol](https://github.com/Certora/tutorials-code/blob/master/lesson4_invariants/erc20/ERC20.sol) and discover the violation in the contract.
Important
Remember to use the `optimistic_loop` option, see [Important: Optimistic loop](https://docs.certora.com/projects/tutorials/en/latest/lesson3_violations/erc20_bugs.html#optimistic-loop-in-erc20).
### Hints[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/invariants/auction.html#hints "Link to this heading")
CVL types
You can use `balanceOf(0)` in CVL without casting it to `address`.
Solution
A solution is available in [zero.spec](https://github.com/Certora/tutorials-code/blob/master/solutions/lesson4_invariants/erc20/zero.spec).
## English auction basic exercise[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/invariants/auction.html#english-auction-basic-exercise "Link to this heading")
In [EnglishAuction.sol](https://github.com/Certora/tutorials-code/blob/master/lesson4_invariants/auction/EnglishAuction.sol), you will find the implementation of a simple [English Auction](https://en.wikipedia.org/wiki/English_auction) for selling an [NFT](https://en.wikipedia.org/wiki/Non-fungible_token). The auction process and additional features are described in the solidity file. Here is a summary of the main details:
  1. The seller of the NFT deploys the contract and sets the NFT and the token to be used.
  2. A participant can bid a certain amount to become the new highest bidder.
  3. Once the bid has ended the highest bidder gets the NFT, and the seller receives the highest bidder’s tokens.


### Exercises[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/invariants/auction.html#exercises "Link to this heading")
Write a spec for [EnglishAuction.sol](https://github.com/Certora/tutorials-code/blob/master/lesson4_invariants/auction/EnglishAuction.sol) containing the following two invariants.
  1. The `highestBid` is higher than or equal to any other bid.
  2. The bid of the `highestBidder` equals the `highestBid`. You may assume that `address(0)` cannot place a bid.


### Hints[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/invariants/auction.html#id1 "Link to this heading")
Methods block hint
You will need to define the getters as `envfree`.
Highest bidder hint
What is the initial value of the highest bidder?
Solution
A full solution is available in [EnglishAuction.spec](https://github.com/Certora/tutorials-code/blob/master/solutions/lesson4_invariants/auction/EnglishAuction.spec).
[ Next 4.3. Preserved blocks ](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/invariants/preserved.html) [ Previous 4.1. Simple invariants examples ](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/invariants/simple.html)
Copyright © 2023, Certora, Inc 
Made with [Sphinx](https://www.sphinx-doc.org/) and [@pradyunsg](https://pradyunsg.me)'s [Furo](https://github.com/pradyunsg/furo)
On this page 
  * [4.2. Basic exercises](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/invariants/auction.html)
    * [ERC20](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/invariants/auction.html#erc20)
      * [Hints](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/invariants/auction.html#hints)
    * [English auction basic exercise](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/invariants/auction.html#english-auction-basic-exercise)
      * [Exercises](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/invariants/auction.html#exercises)
      * [Hints](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/invariants/auction.html#id1)


