Contents Menu Expand Light mode Dark mode Auto light/dark mode Auto light/dark, in light mode Auto light/dark, in dark mode
Hide navigation sidebar
Hide table of contents sidebar
[Skip to content](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/ghosts/exercises.html#furo-main-content)
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


[ Back to top ](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/ghosts/exercises.html)
Toggle Light / Dark / Auto color theme
Toggle table of contents sidebar
# 4.5. Ghost exercises[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/ghosts/exercises.html#ghost-exercises "Link to this heading")
## Simple voting contract[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/ghosts/exercises.html#simple-voting-contract "Link to this heading")
This exercise refers to the simple [Voting](https://github.com/Certora/tutorials-code/blob/master/lesson4_invariants/simple_voting/Voting.sol) contract.
  1. Use a ghost and an invariant to prove that if `_hasVoted` changed then the `vote` method was called.
  2. Use a ghost and an invariant to prove that the values of `_hasVoted` can only change from false to true.
  3. Write a _complete spec_ for the [Voting](https://github.com/Certora/tutorials-code/blob/master/lesson4_invariants/simple_voting/Voting.sol) contract, using ghosts, invariants and rules.
  4. Check that your spec passes without violations on [Voting](https://github.com/Certora/tutorials-code/blob/master/lesson4_invariants/simple_voting/Voting.sol) and also catches the bugs in the five buggy implementations:
     * [VotingBug1.sol](https://github.com/Certora/tutorials-code/blob/master/lesson4_invariants/simple_voting/VotingBug1.sol)
     * [VotingBug2.sol](https://github.com/Certora/tutorials-code/blob/master/lesson4_invariants/simple_voting/VotingBug2.sol)
     * [VotingBug3.sol](https://github.com/Certora/tutorials-code/blob/master/lesson4_invariants/simple_voting/VotingBug3.sol)
     * [VotingBug4.sol](https://github.com/Certora/tutorials-code/blob/master/lesson4_invariants/simple_voting/VotingBug4.sol)
     * [VotingBug5.sol](https://github.com/Certora/tutorials-code/blob/master/lesson4_invariants/simple_voting/VotingBug5.sol)
  5. Check that your spec catches all mutations generated by [Gambit](https://docs.certora.com/en/latest/docs/gambit/index.html) (see [Using Gambit to test your spec](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/ghosts/exercises.html#lesson4-using-gambit) below, which provides an example using [Gambit](https://docs.certora.com/en/latest/docs/gambit/index.html)).


### Hints[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/ghosts/exercises.html#hints "Link to this heading")
Solution
The full solution is at [Voting_solution.spec](https://github.com/Certora/tutorials-code/blob/master/solutions/lesson4_invariants/simple_voting/Voting_solution.spec).
### Using Gambit to test your spec[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/ghosts/exercises.html#using-gambit-to-test-your-spec "Link to this heading")
[Gambit](https://docs.certora.com/en/latest/docs/gambit/index.html) is a Certora tool that automatically generates random mutations (bugs) in the code. This is useful for testing the coverage of your spec. See the [Mutant generation](https://docs.certora.com/en/latest/docs/gambit/gambit.html) page for Gambit installation instructions.
Gambit can be used with the Certora Prover to automatically run your spec on _all generated mutations_. This is explained in detail in [Using Gambit with the Prover](https://docs.certora.com/en/latest/docs/gambit/mutation-verifier.html). Here, we provide an example that runs [Voting.spec](https://github.com/Certora/tutorials-code/blob/master/lesson4_invariants/simple_voting/Voting.spec) on all mutations.
#### Gambit example[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/ghosts/exercises.html#gambit-example "Link to this heading")
  1. To run the Prover on all mutations we need a Prover configuration file (see [Using config files](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/config_files.html#sec-using-config-files)) with a mutations object.
  2. [Voting.conf](https://github.com/Certora/tutorials-code/blob/master/lesson4_invariants/simple_voting/Voting.conf) includes a simple mutations object. It simply specifies the file to be mutated as [Voting.sol](https://github.com/Certora/tutorials-code/blob/master/lesson4_invariants/simple_voting/Voting.sol).
  3. From the [lesson4_invariants/simple_voting/](https://github.com/Certora/tutorials-code/tree/master/lesson4_invariants/simple_voting) folder run the following command:
```
certoraMutateVoting.conf

```

This will run the [Voting.spec](https://github.com/Certora/tutorials-code/blob/master/lesson4_invariants/simple_voting/Voting.spec) on all mutations (asynchronously), sending jobs to the server.
  4. After all the verification jobs have been sent to the cloud, you can follow the progress of your test at the [Mutation Tests Dashboard](https://prover.certora.com/mutations).
![Mutation tests dashboard](https://docs.certora.com/projects/tutorials/en/latest/_images/mutation_test_started_dashboard.png)
Mutation tests dashboard[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/ghosts/exercises.html#id3 "Link to this image")
  5. View the report on the provided link once the test is completed. Below is an example of a mutation test report.
![Mutation test report example](https://docs.certora.com/projects/tutorials/en/latest/_images/mutation_testing.png)
Mutation test report example[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/ghosts/exercises.html#id4 "Link to this image")


## English auction[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/ghosts/exercises.html#english-auction "Link to this heading")
This exercise is about the [EnglishAuction.sol](https://github.com/Certora/tutorials-code/blob/master/lesson4_invariants/auction/EnglishAuction.sol) contract. We’ve met this contract before in the [English auction basic exercise](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/invariants/auction.html#lesson4-english-auction-basic). To make it harder, we abandon the assumption that `address(0)` cannot place a bid.
  1. Use a ghost and a hook to indicate that someone placed some bid.
  2. Prove that `highestBid` is **strictly greater** than all other bids, provided someone has placed a bid.


### Setup note[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/ghosts/exercises.html#setup-note "Link to this heading")
The [EnglishAuction](https://github.com/Certora/tutorials-code/blob/master/lesson4_invariants/auction/EnglishAuction.sol) contract calls other contracts. For example, it calls `ERC721Mock.transferFrom`. If the Prover is not _certain_ what code is called, it will over-approximate by assuming anything can happen. In particular, this can cause ghost variables to have arbitrary values. We will learn more about this in the next lesson.
For now, to avoid such issues, ensure you config file contains the following lines:
```
{
"files":[
// Declare all three contracts
"lesson4_invariants/auction/EnglishAuction.sol:EnglishAuction",
"lesson4_invariants/auction/EnglishAuction.sol:ERC721Mock",
"lesson4_invariants/auction/EnglishAuction.sol:ERC20Mock"
],
"link":[
// Link EnglishAuction storage variables to contracts
"EnglishAuction:nft=ERC721Mock",
"EnglishAuction:token=ERC20Mock"
],

```

These lines will tell the Prover to _always_ associate the `EnglishAuction` variables `nft` and `token` with the contracts `ERC721Mock` and `ERC20Mock` respectively.
### Hints[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/ghosts/exercises.html#id1 "Link to this heading")
Solution
The full solution is at [EnglishAuction_strict.spec](https://github.com/Certora/tutorials-code/blob/master/solutions/lesson4_invariants/auction/EnglishAuction_strict.spec).
## Funds managers[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/ghosts/exercises.html#funds-managers "Link to this heading")
This exercise is for the [Manager.sol](https://github.com/Certora/tutorials-code/blob/master/lesson4_invariants/manager/Manager.sol) contract, which we’ve met in [Funds managers exercise](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/invariants/preserved.html#lesson4-invariants-funds-manages-preserved). The exercise now is to prove that every active manager manages a fund. Use a ghost when writing the invariants and verify them using the Certora Prover.
### Hints[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/ghosts/exercises.html#id2 "Link to this heading")
Solution
The full solution is at [Manager_ghost.spec](https://github.com/Certora/tutorials-code/blob/master/solutions/lesson4_invariants/manager/Manager_ghost.spec).
[ Previous 4.4. Ghosts and hooks ](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/ghosts/basics.html)
Copyright © 2023, Certora, Inc 
Made with [Sphinx](https://www.sphinx-doc.org/) and [@pradyunsg](https://pradyunsg.me)'s [Furo](https://github.com/pradyunsg/furo)
On this page 
  * [4.5. Ghost exercises](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/ghosts/exercises.html)
    * [Simple voting contract](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/ghosts/exercises.html#simple-voting-contract)
      * [Hints](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/ghosts/exercises.html#hints)
      * [Using Gambit to test your spec](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/ghosts/exercises.html#using-gambit-to-test-your-spec)
        * [Gambit example](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/ghosts/exercises.html#gambit-example)
    * [English auction](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/ghosts/exercises.html#english-auction)
      * [Setup note](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/ghosts/exercises.html#setup-note)
      * [Hints](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/ghosts/exercises.html#id1)
    * [Funds managers](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/ghosts/exercises.html#funds-managers)
      * [Hints](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/ghosts/exercises.html#id2)


