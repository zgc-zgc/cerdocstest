Contents Menu Expand Light mode Dark mode Auto light/dark mode Auto light/dark, in light mode Auto light/dark, in dark mode
Hide navigation sidebar
Hide table of contents sidebar
[Skip to content](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/invariants/simple.html#furo-main-content)
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


[ Back to top ](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/invariants/simple.html)
Toggle Light / Dark / Auto color theme
Toggle table of contents sidebar
# 4.1. Simple invariants examples[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/invariants/simple.html#simple-invariants-examples "Link to this heading")
Here are two simple examples of invariants. The second example [Ball Game](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/invariants/simple.html#ball-game-video) also highlights a subtle point of using invariants.
## A simple example[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/invariants/simple.html#a-simple-example "Link to this heading")
In the folder [simple_voting](https://github.com/Certora/tutorials-code/tree/master/lesson4_invariants/simple_voting) is a simple voting contract [Voting.sol](https://github.com/Certora/tutorials-code/blob/master/lesson4_invariants/simple_voting/Voting.sol), shown below.
Voting contract[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/invariants/simple.html#id1 "Link to this code")
```
contractVoting{
mapping(address=>bool)internal_hasVoted;
uint256public votesInFavor;
uint256public votesAgainst;
uint256public totalVotes;
functionvote(boolisInFavor)public{
require(!_hasVoted[msg.sender]);
_hasVoted[msg.sender]=true;
totalVotes+=1;
if(isInFavor){
votesInFavor+=1;
}else{
votesAgainst+=1;
}
}
functionhasVoted(addressvoter)publicviewreturns(bool){
return_hasVoted[voter];
}
}

```

A simple invariant of this contract is: `votesInFavor+votesAgainst==totalVotes`, which we express as an invariant in [Voting.spec](https://github.com/Certora/tutorials-code/blob/master/lesson4_invariants/simple_voting/Voting.spec). The spec also contains two translations of the invariant to a rule, one correct and the other wrong:
Invariant[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/invariants/simple.html#id2 "Link to this code")
```
invariantsumResultsEqualsTotalVotes()
votesInFavor()+votesAgainst()==to_mathint(totalVotes());

```

Translation to a rule of the _induction step_ of the invariant[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/invariants/simple.html#id3 "Link to this code")
```
rulesumResultsEqualsTotalVotesAsRule(methodf){
// Precondition
requirevotesInFavor()+votesAgainst()==to_mathint(totalVotes());
enve;
calldataargargs;
f(e,args);
assert(
votesInFavor()+votesAgainst()==to_mathint(totalVotes()),
"Sum of votes should equal total votes"
);
}

```

Wrong translation of the invariant to a rule[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/invariants/simple.html#id4 "Link to this code")
```
rulesumResultsEqualsTotalVotesWrong(){
assert(
votesInFavor()+votesAgainst()==to_mathint(totalVotes()),
"Sum of votes should equal total votes"
);
}

```

Running the Certora Prover verifies the invariant, and also the rule `sumResultsEqualsTotalVotesAsRule` (which is the translation of the invariant’s induction step translation to a rule). While the naive translation to a rule in `sumResultsEqualsTotalVotesWrong` fails, since it doesn’t have the necessary precondition.
Note
The invariant has another advantage over the rule besides its brevity – it also verifies the invariant holds after the constructor. In contrast, a parametric rule will not checked for the case where the parametric method is the constructor.
## Ball Game[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/invariants/simple.html#ball-game "Link to this heading")
Ball game video clip
[ Next 4.2. Basic exercises ](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/invariants/auction.html) [ Previous 4. Invariants and Ghosts ](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/index.html)
Copyright © 2023, Certora, Inc 
Made with [Sphinx](https://www.sphinx-doc.org/) and [@pradyunsg](https://pradyunsg.me)'s [Furo](https://github.com/pradyunsg/furo)
On this page 
  * [4.1. Simple invariants examples](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/invariants/simple.html)
    * [A simple example](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/invariants/simple.html#a-simple-example)
    * [Ball Game](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/invariants/simple.html#ball-game)


