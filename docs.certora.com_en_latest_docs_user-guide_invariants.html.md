[ Certora Prover Documentation ![Logo](https://docs.certora.com/en/latest/_static/Certora_Logo_Black.svg) ](https://docs.certora.com/en/latest/index.html)
Contents
  * [Certora User’s Guide](https://docs.certora.com/en/latest/docs/user-guide/index.html)
    * [Installation](https://docs.certora.com/en/latest/docs/user-guide/install.html)
    * [Installing an EVM compiler and VS Code Extension](https://docs.certora.com/en/latest/docs/user-guide/install_evm_compiler.html)
    * [Tutorial and Workshops](https://docs.certora.com/en/latest/docs/user-guide/tutorials.html)
    * [Running the Certora Prover](https://docs.certora.com/en/latest/docs/user-guide/running.html)
    * [Designing Good Specifications](https://docs.certora.com/en/latest/docs/user-guide/properties/index.html)
    * [Producing Positive Examples](https://docs.certora.com/en/latest/docs/user-guide/satisfy.html)
    * [Invariants](https://docs.certora.com/en/latest/docs/user-guide/invariants.html)
      * [Teams example](https://docs.certora.com/en/latest/docs/user-guide/invariants.html#teams-example)
      * [Simple invariants](https://docs.certora.com/en/latest/docs/user-guide/invariants.html#simple-invariants)
        * [No team for address zero](https://docs.certora.com/en/latest/docs/user-guide/invariants.html#no-team-for-address-zero)
        * [The leader is part of the team](https://docs.certora.com/en/latest/docs/user-guide/invariants.html#the-leader-is-part-of-the-team)
      * [Using preserved blocks inside invariants](https://docs.certora.com/en/latest/docs/user-guide/invariants.html#using-preserved-blocks-inside-invariants)
        * [A team not created has no players](https://docs.certora.com/en/latest/docs/user-guide/invariants.html#a-team-not-created-has-no-players)
        * [A team has at most three players](https://docs.certora.com/en/latest/docs/user-guide/invariants.html#a-team-has-at-most-three-players)
    * [Parametric rules](https://docs.certora.com/en/latest/docs/user-guide/parametric.html)
    * [Tracking changes with ghosts and hooks](https://docs.certora.com/en/latest/docs/user-guide/ghosts.html)
    * [Specification Design Patterns](https://docs.certora.com/en/latest/docs/user-guide/patterns/index.html)
    * [Using Opcode Hooks](https://docs.certora.com/en/latest/docs/user-guide/opcodes.html)
    * [Working with Multiple Contracts](https://docs.certora.com/en/latest/docs/user-guide/multicontract/index.html)
    * [Managing Timeouts and Out of Memory Problems](https://docs.certora.com/en/latest/docs/user-guide/out-of-resources/index.html)
    * [Understanding gaps between high and low level code](https://docs.certora.com/en/latest/docs/user-guide/gaps.html)
    * [Checking Specifications](https://docs.certora.com/en/latest/docs/user-guide/checking.html)
    * [CI Configuration](https://docs.certora.com/en/latest/docs/user-guide/ci.html)
    * [Syntax Highlighting on GitHub](https://docs.certora.com/en/latest/docs/user-guide/github_highlighting.html)
    * [Glossary](https://docs.certora.com/en/latest/docs/user-guide/glossary.html)
  * [The Certora Verification Language](https://docs.certora.com/en/latest/docs/cvl/index.html)
  * [The Certora Prover](https://docs.certora.com/en/latest/docs/prover/index.html)
  * [Sunbeam: Verification for Soroban](https://docs.certora.com/en/latest/docs/sunbeam/index.html)
  * [The Certora Solana Prover](https://docs.certora.com/en/latest/docs/solana/index.html)
  * [Gambit: Mutation Generator for Solidity](https://docs.certora.com/en/latest/docs/gambit/index.html)


Additional information
  * [The Certora Equivalence Checker](https://docs.certora.com/en/latest/docs/equiv-check/index.html)
  * [Certora Technology White Paper](https://docs.certora.com/en/latest/docs/whitepaper/index.html)


  * [Index](https://docs.certora.com/en/latest/genindex.html)


[Certora Prover Documentation](https://docs.certora.com/en/latest/index.html)
  * [](https://docs.certora.com/en/latest/index.html)
  * [Certora User’s Guide](https://docs.certora.com/en/latest/docs/user-guide/index.html)
  * Invariants
  * [ View page source](https://docs.certora.com/en/latest/_sources/docs/user-guide/invariants.rst.txt)


# Invariants[](https://docs.certora.com/en/latest/docs/user-guide/invariants.html#invariants "Link to this heading")
An [invariant](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-invariant) is a property of the contract’s storage state that should hold between calls to the contract. For example, in some ERC20 contracts the balance of `address(0)` is always zero.
Below, we provide examples of using invariants. You can read more about invariants in [Invariants (from The Certora Verification Language)](https://docs.certora.com/en/latest/docs/cvl/invariants.html#invariants).
## Teams example[](https://docs.certora.com/en/latest/docs/user-guide/invariants.html#teams-example "Link to this heading")
The [ITeams](https://github.com/Certora/Examples/blob/7dfc379423202c90cf284eb42800b97cf5c95d83/CVLByExample/Teams/ITeams.sol) interface, shown below, is an interface for managing teams consisting of two players and a team leader.
[ITeams interface](https://github.com/Certora/Examples/blob/7dfc379423202c90cf284eb42800b97cf5c95d83/CVLByExample/Teams/ITeams.sol)
```
interfaceITeams{
/// @return The team id of the player
/// @notice Return value of 0 means the player has not been assigned to a team
functionteamOf(addressplayer)externalviewreturns(uint8);
/// @return The team leader
/// @notice Return value of zero means the team has not been created
functionleaderOf(uint8teamId)externalviewreturns(address);
/// @dev Players must not be assigned to any team
/// @dev The team must not exist before the call
functioncreateTeam(
addressleader,
addressplayerA,
addressplayerB,
uint8teamId
)external;
/// @notice Change the team's leader
/// @dev Only the current leader may call this function
/// @dev The new leader must be a member of the tem
functionchangeLeader(addressnewLeader)external;
}

```
Copy to clipboard
A contract implementing this interface should satisfy the following properties:
  1. Each team has three _different_ players, one of which is the team leader.
  2. Each player can belong only to one team.
  3. A team is identified by a unique id between 1 and 255.
  4. A player having team-id 0 indicates this player has no assigned team.
  5. Address zero cannot be part of a team.
  6. If a team has not been created yet, it will have `address(0)` as a team leader.


Next we translate these properties to CVL invariants. You can find the entire spec in [The team of zero is zero](https://github.com/Certora/Examples/blob/7dfc379423202c90cf284eb42800b97cf5c95d83/CVLByExample/Teams/Teams.spec).
  * To run the spec on a correct implementation of `ITeams` use [correct.conf](https://github.com/Certora/Examples/blob/7dfc379423202c90cf284eb42800b97cf5c95d83/CVLByExample/Teams/correct.conf), which will use the implementation in [Teams.sol](https://github.com/Certora/Examples/blob/7dfc379423202c90cf284eb42800b97cf5c95d83/CVLByExample/Teams/Teams.sol).
  * To see the spec discover bugs, use [buggy.conf](https://github.com/Certora/Examples/blob/7dfc379423202c90cf284eb42800b97cf5c95d83/CVLByExample/Teams/buggy.conf). This will run the spec against the buggy implementation in [TeamsBugs.sol](https://github.com/Certora/Examples/blob/7dfc379423202c90cf284eb42800b97cf5c95d83/CVLByExample/Teams/TeamsBugs.sol).


## Simple invariants[](https://docs.certora.com/en/latest/docs/user-guide/invariants.html#simple-invariants "Link to this heading")
### No team for address zero[](https://docs.certora.com/en/latest/docs/user-guide/invariants.html#no-team-for-address-zero "Link to this heading")
We can readily deduce from the properties that `teamOf(address(0))` must be zero. Here it is written as an invariant:
[The team of zero is zero](https://github.com/Certora/Examples/blob/7dfc379423202c90cf284eb42800b97cf5c95d83/CVLByExample/Teams/Teams.spec)[](https://docs.certora.com/en/latest/docs/user-guide/invariants.html#id2 "Link to this code")
```
methods{
functionteamOf(address)externalreturns(uint8)envfree;
functionleaderOf(uint8)externalreturns(address)envfree;
}
/// @title Address zero is not in any team
invariantaddressZeroNotPlayer()
teamOf(0)==0;

```
Copy to clipboard
We declared the functions `teamOf` and `leaderOf` as `envfree` to remove the need for an `env` type argument.
### The leader is part of the team[](https://docs.certora.com/en/latest/docs/user-guide/invariants.html#the-leader-is-part-of-the-team "Link to this heading")
Another invariant property is that the team-id of the leader of team x is x. This only holds if x is not zero and the leader is not `address(0)`. Here is the property written as an invariant:
[The team’s leader is part of the team](https://github.com/Certora/Examples/blob/7dfc379423202c90cf284eb42800b97cf5c95d83/CVLByExample/Teams/Teams.spec)[](https://docs.certora.com/en/latest/docs/user-guide/invariants.html#id3 "Link to this code")
```
/// @title The team's leader is part of the team
invariantleaderBelongsToTeam(uint8teamId)
(teamId!=0&&leaderOf(teamId)!=0)=>teamOf(leaderOf(teamId))==teamId;

```
Copy to clipboard
## Using preserved blocks inside invariants[](https://docs.certora.com/en/latest/docs/user-guide/invariants.html#using-preserved-blocks-inside-invariants "Link to this heading")
Sometimes additional conditions are needed to prove invariants. These additional conditions are given using preserved blocks, see [Preserved blocks](https://docs.certora.com/en/latest/docs/cvl/invariants.html#preserved). Here are two examples using preserved blocks.
### A team not created has no players[](https://docs.certora.com/en/latest/docs/user-guide/invariants.html#a-team-not-created-has-no-players "Link to this heading")
Before team `i` is created, `leaderOf(i)` must be `address(0)`. In such a case, there should be no players in team `i`. We can write this condition as:
[nonExistTeamHasNoPlayers without preserved block](https://github.com/Certora/Examples/blob/7dfc379423202c90cf284eb42800b97cf5c95d83/CVLByExample/Teams/NoPreserved.spec)[](https://docs.certora.com/en/latest/docs/user-guide/invariants.html#id4 "Link to this code")
```
/** @title If a team does not exist it has not players
 * This invariant cannot be proven without a preserved block.
 */
invariantnonExistTeamHasNoPlayers(uint8teamId,addressplayer)
(teamId!=0&&leaderOf(teamId)==0)=>teamOf(player)!=teamId;

```
Copy to clipboard
Running this rule, the Prover will find the following violation, which you can see in this rule report [nonExistTeamHasNoPlayers violation report](https://prover.certora.com/output/98279/65d0cd795ba640d6bdd7877074fca175?anonymousKey=55ad7f5a7130e367993082addf32fc7898494db3). The function called is `changeLeader(address(0))`, changing the leader from address `a` (where `a` is not zero) to zero. Before the call `address(0)` is a member of team `i`, where `i>0`. After the call the left hand side of the invariant condition holds true: `i!=0&&leaderOf(i)==0`. But the right hand side is false for `player=a`, since `teamOf(a)=i`. The violation is expressed in the following table, showing the change in state.
| Pre call state | Post call state  
---|---|---  
`leaderOf(i)` | `a` | `0`  
`teamOf(a)` | `i` | `i`  
`teamOf(0)` | `i` | `i`  
In order for the invariant to be proved, we need to require that the team of `address(0)` is zero. We’ll do that using a preserved block. Since we already proved this in [No team for address zero](https://docs.certora.com/en/latest/docs/user-guide/invariants.html#no-team-for-address-zero), we can simply require that the invariant `addressZeroNotPlayer` holds, like so:
[Non created team has no players](https://github.com/Certora/Examples/blob/7dfc379423202c90cf284eb42800b97cf5c95d83/CVLByExample/Teams/Teams.spec)[](https://docs.certora.com/en/latest/docs/user-guide/invariants.html#id5 "Link to this code")
```
/// @title If a team does not exist it has not players
invariantnonExistTeamHasNoPlayers(uint8teamId,addressplayer)
(teamId!=0&&leaderOf(teamId)==0)=>teamOf(player)!=teamId
{
preserved{
requireInvariantaddressZeroNotPlayer();
}
}

```
Copy to clipboard
See also
To read more on `requireInvariant` and its soundness, see [Invariants and induction](https://docs.certora.com/en/latest/docs/cvl/invariants.html#invariant-induction).
### A team has at most three players[](https://docs.certora.com/en/latest/docs/user-guide/invariants.html#a-team-has-at-most-three-players "Link to this heading")
Here is how we phrase this property:
> Let `a`, `b`, `c` and `d` be four different addresses, and suppose that `a`, `b` and `c` are all on the same non-zero team `i`. Then `d` does not belong to team `i`.
#### Helper functions[](https://docs.certora.com/en/latest/docs/user-guide/invariants.html#helper-functions "Link to this heading")
To enhance readability we’ll define two helper functions:
  1. A function checking that four addresses are different, called `fourDifferentAddresses`.
  2. A function checking that three addresses are on the same team, called `sameTeam`.


Their definitions are given below.
[fourDifferentAddresses](https://github.com/Certora/Examples/blob/7dfc379423202c90cf284eb42800b97cf5c95d83/CVLByExample/Teams/Teams.spec)
```
/// @return If the four addresses are all different from each other
functionfourDifferentAddresses(
addressa,
addressb,
addressc,
addressd
)returnsbool{
return(
a!=b&&a!=c&&a!=d&&
b!=c&&b!=d&&
c!=d
);
}

```
Copy to clipboard
[sameTeam](https://github.com/Certora/Examples/blob/7dfc379423202c90cf284eb42800b97cf5c95d83/CVLByExample/Teams/Teams.spec)
```
/// @return If all players are on the same team
functionsameTeam(addressa,addressb,addressc)returnsbool{
returnteamOf(a)==teamOf(b)&&teamOf(b)==teamOf(c);
}

```
Copy to clipboard
#### The rule[](https://docs.certora.com/en/latest/docs/user-guide/invariants.html#the-rule "Link to this heading")
Here is the complete rule.
[A team has at most three players](https://github.com/Certora/Examples/blob/7dfc379423202c90cf284eb42800b97cf5c95d83/CVLByExample/Teams/Teams.spec)[](https://docs.certora.com/en/latest/docs/user-guide/invariants.html#id6 "Link to this code")
```
/// @title A team has at most three players
invariantteamHasMaxThreePlayers(addressa,addressb,addressc,addressd)
(
teamOf(a)!=0&&
fourDifferentAddresses(a,b,c,d)&&
sameTeam(a,b,c)
=>teamOf(d)!=teamOf(a)
)
{
preservedcreateTeam(
addressleader,
addressplayerA,
addressplayerB,
uint8teamId
)with(enve){
requireInvariantnonExistTeamHasNoPlayers(teamId,a);
requireInvariantnonExistTeamHasNoPlayers(teamId,b);
requireInvariantnonExistTeamHasNoPlayers(teamId,c);
requireInvariantnonExistTeamHasNoPlayers(teamId,d);
}
}

```
Copy to clipboard
As you can see, we used a different preserved block here. This preserved block adds a pre-condition only when verifying the invariant on the function `createTeam` using environment `enve`. Without this preserved block, the Prover may assume that the team had players _before it was created_.
See also
You can find out more about preserved blocks in [Preserved blocks](https://docs.certora.com/en/latest/docs/cvl/invariants.html#preserved) section.
[ Previous](https://docs.certora.com/en/latest/docs/user-guide/satisfy.html "Producing Positive Examples") [Next ](https://docs.certora.com/en/latest/docs/user-guide/parametric.html "Parametric rules")
© Copyright 2025, Certora, Inc.
Built with [Sphinx](https://www.sphinx-doc.org/) using a [theme](https://github.com/readthedocs/sphinx_rtd_theme) provided by [Read the Docs](https://readthedocs.org). 
