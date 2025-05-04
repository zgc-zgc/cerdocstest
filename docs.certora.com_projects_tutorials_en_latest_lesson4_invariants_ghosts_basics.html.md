Contents Menu Expand Light mode Dark mode Auto light/dark mode Auto light/dark, in light mode Auto light/dark, in dark mode
Hide navigation sidebar
Hide table of contents sidebar
[Skip to content](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/ghosts/basics.html#furo-main-content)
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


[ Back to top ](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/ghosts/basics.html)
Toggle Light / Dark / Auto color theme
Toggle table of contents sidebar
# 4.4. Ghosts and hooks[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/ghosts/basics.html#ghosts-and-hooks "Link to this heading")
## Ghost variables[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/ghosts/basics.html#ghost-variables "Link to this heading")
Ghost variables are variables defined in CVL that behave like the verified contract’s storage data. For example, they revert when the storage reverts, and they can be set to specific values after the constructor. They can be directly accessed from the spec, both to read and to write.
### Examples[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/ghosts/basics.html#examples "Link to this heading")
Defining a ghost variables of different types[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/ghosts/basics.html#id1 "Link to this code")
```
ghostmathintnumVoted;
ghostmapping(address=>uint256)balanceGhost;

```

### Setting initial state[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/ghosts/basics.html#setting-initial-state "Link to this heading")
To set the initial value of a ghost variable (i.e. its value after the constructor), we use the following syntax:
Defining a ghost variable’s initial state as zero[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/ghosts/basics.html#id2 "Link to this code")
```
ghostmathintsomeGhost{
init_stateaxiomsomeGhost==0;
}

```

The expression `init_stateaxiom<booleancondition>;` ensures that immediately after the constructor, the boolean condition would be true. Note, however, that at any other time its value is not constrained.
Important
The `<booleancondition>` expression may not contain calls to solidity functions.
Here is another simple example:
```
ghostboolboolGhost{
init_stateaxiom!boolGhost;
}

```

The example below sets the value of `func(x)` to be `x` whenever `x` is even:
```
ghostmapping(uint256=>uint256)func{
init_stateaxiomforalluint256x.(x%2==0)=>(func(x)==x);
}

```

## Storage hooks[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/ghosts/basics.html#storage-hooks "Link to this heading")
Storage hooks allow us to inject CVL code whenever a storage variable is accessed, whether for read or write. The syntax is detailed in the [Hooks](https://docs.certora.com/en/latest/docs/cvl/hooks.html) documentation. One use for storage hooks is to update ghost variables.
### Example[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/ghosts/basics.html#example "Link to this heading")
Consider the simple voting contract from [Voting.sol](https://github.com/Certora/tutorials-code/blob/master/lesson4_invariants/simple_voting/Voting.sol) shown below.
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

We want to prove that the number of times `_hasVoted` is updated equals `totalVotes`. To do this we define a ghost variable `numVoted` that is updated every time the `_hasVoted` mapping is modified. This allows us to count the number of times values in `_hasVoted` changed from false to true.
```
ghostmathintnumVoted{
// No votes at start
init_stateaxiomnumVoted==0;
}
hookSstore_hasVoted[KEYaddressvoter]
boolnewVal(boololdVal){
numVoted=numVoted+1;
}
/// @title Total voted intergrity
invariantsumResultsEqualsTotalVotes()
to_mathint(totalVotes())==numVoted;

```

To be precise, the invariant `sumResultsEqualsTotalVotes` means that `totalVotes` equals the number of times a value has changed from false to true in `_hasVoted`.
[ Next 4.5. Ghost exercises ](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/ghosts/exercises.html) [ Previous 4.3. Preserved blocks ](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/invariants/preserved.html)
Copyright © 2023, Certora, Inc 
Made with [Sphinx](https://www.sphinx-doc.org/) and [@pradyunsg](https://pradyunsg.me)'s [Furo](https://github.com/pradyunsg/furo)
On this page 
  * [4.4. Ghosts and hooks](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/ghosts/basics.html)
    * [Ghost variables](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/ghosts/basics.html#ghost-variables)
      * [Examples](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/ghosts/basics.html#examples)
      * [Setting initial state](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/ghosts/basics.html#setting-initial-state)
    * [Storage hooks](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/ghosts/basics.html#storage-hooks)
      * [Example](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/ghosts/basics.html#example)


