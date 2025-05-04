[ Certora Prover Documentation ![Logo](https://docs.certora.com/en/latest/_static/Certora_Logo_Black.svg) ](https://docs.certora.com/en/latest/index.html)
Contents
  * [Certora User’s Guide](https://docs.certora.com/en/latest/docs/user-guide/index.html)
  * [The Certora Verification Language](https://docs.certora.com/en/latest/docs/cvl/index.html)
    * [Specification Files](https://docs.certora.com/en/latest/docs/cvl/overview.html)
    * [Basic Syntax](https://docs.certora.com/en/latest/docs/cvl/basics.html)
    * [Types](https://docs.certora.com/en/latest/docs/cvl/types.html)
    * [Expressions](https://docs.certora.com/en/latest/docs/cvl/expr.html)
    * [Statements](https://docs.certora.com/en/latest/docs/cvl/statements.html)
    * [Import and Use Statements](https://docs.certora.com/en/latest/docs/cvl/imports.html)
    * [Using Statements](https://docs.certora.com/en/latest/docs/cvl/using.html)
    * [The Methods Block](https://docs.certora.com/en/latest/docs/cvl/methods.html)
    * [Rules](https://docs.certora.com/en/latest/docs/cvl/rules.html)
    * [Built-in Rules](https://docs.certora.com/en/latest/docs/cvl/builtin.html)
    * [Functions](https://docs.certora.com/en/latest/docs/cvl/functions.html)
    * [Invariants](https://docs.certora.com/en/latest/docs/cvl/invariants.html)
    * [Uninterpreted Sorts](https://docs.certora.com/en/latest/docs/cvl/sorts.html)
    * [Ghosts](https://docs.certora.com/en/latest/docs/cvl/ghosts.html)
      * [Syntax](https://docs.certora.com/en/latest/docs/cvl/ghosts.html#syntax)
      * [Declaring ghost variables](https://docs.certora.com/en/latest/docs/cvl/ghosts.html#declaring-ghost-variables)
      * [Ghost Functions](https://docs.certora.com/en/latest/docs/cvl/ghosts.html#ghost-functions)
      * [Restrictions on ghost definitions](https://docs.certora.com/en/latest/docs/cvl/ghosts.html#restrictions-on-ghost-definitions)
      * [Using ghost variables](https://docs.certora.com/en/latest/docs/cvl/ghosts.html#using-ghost-variables)
      * [Ghost axioms](https://docs.certora.com/en/latest/docs/cvl/ghosts.html#ghost-axioms)
        * [Global axioms](https://docs.certora.com/en/latest/docs/cvl/ghosts.html#global-axioms)
        * [Initial state axioms](https://docs.certora.com/en/latest/docs/cvl/ghosts.html#initial-state-axioms)
      * [Restrictions on ghost axioms](https://docs.certora.com/en/latest/docs/cvl/ghosts.html#restrictions-on-ghost-axioms)
      * [Ghosts vs. persistent ghosts](https://docs.certora.com/en/latest/docs/cvl/ghosts.html#ghosts-vs-persistent-ghosts)
        * [Persistent ghosts that survive havocs](https://docs.certora.com/en/latest/docs/cvl/ghosts.html#persistent-ghosts-that-survive-havocs)
        * [Persistent ghosts that survive reverts](https://docs.certora.com/en/latest/docs/cvl/ghosts.html#persistent-ghosts-that-survive-reverts)
    * [Definitions](https://docs.certora.com/en/latest/docs/cvl/defs.html)
    * [Hooks](https://docs.certora.com/en/latest/docs/cvl/hooks.html)
    * [Transient Storage](https://docs.certora.com/en/latest/docs/cvl/transient.html)
    * [Foundry Integration (Alpha)](https://docs.certora.com/en/latest/docs/cvl/foundry-integration.html)
    * [Changes Since CVL 1](https://docs.certora.com/en/latest/docs/cvl/index.html#changes-since-cvl-1)
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
  * [The Certora Verification Language](https://docs.certora.com/en/latest/docs/cvl/index.html)
  * Ghosts
  * [ View page source](https://docs.certora.com/en/latest/_sources/docs/cvl/ghosts.md.txt)


# [Ghosts](https://docs.certora.com/en/latest/docs/cvl/ghosts.html#id5)[](https://docs.certora.com/en/latest/docs/cvl/ghosts.html#ghosts "Link to this heading")
Ghosts are a way of defining additional variables for use during verification. These variables are often used to
  * communicate information between [Rules](https://docs.certora.com/en/latest/docs/cvl/rules.html#rules-main) and [Hooks](https://docs.certora.com/en/latest/docs/cvl/hooks.html#hooks).
  * define deterministic [expression summaries](https://docs.certora.com/en/latest/docs/cvl/methods.html#expression-summary).


Ghosts can be seen as an ‘extension’ to the state of the contracts under verification. This means that in case a call reverts, the ghost values will revert to their pre-state. Additionally, if an unresolved call is handled by a havoc, the ghost values will havoc as well. Ghosts are regarded as part of the state of the contracts, and when calls are invoked with `at storageVar` statements (see [The storage type](https://docs.certora.com/en/latest/docs/cvl/types.html#storage-type)), they are restored to their state as saved in `storageVar`. An exception to this rule are ghosts marked _persistent_. Persistent ghosts are **never** havoced, and **never** reverted. See [Ghosts vs. persistent ghosts](https://docs.certora.com/en/latest/docs/cvl/ghosts.html#persistent-ghosts) below for more details and examples.
Contents
  * [Ghosts](https://docs.certora.com/en/latest/docs/cvl/ghosts.html#ghosts)
    * [Syntax](https://docs.certora.com/en/latest/docs/cvl/ghosts.html#syntax)
    * [Declaring ghost variables](https://docs.certora.com/en/latest/docs/cvl/ghosts.html#declaring-ghost-variables)
    * [Ghost Functions](https://docs.certora.com/en/latest/docs/cvl/ghosts.html#ghost-functions)
    * [Restrictions on ghost definitions](https://docs.certora.com/en/latest/docs/cvl/ghosts.html#restrictions-on-ghost-definitions)
    * [Using ghost variables](https://docs.certora.com/en/latest/docs/cvl/ghosts.html#using-ghost-variables)
    * [Ghost axioms](https://docs.certora.com/en/latest/docs/cvl/ghosts.html#ghost-axioms)
      * [Global axioms](https://docs.certora.com/en/latest/docs/cvl/ghosts.html#global-axioms)
      * [Initial state axioms](https://docs.certora.com/en/latest/docs/cvl/ghosts.html#initial-state-axioms)
    * [Restrictions on ghost axioms](https://docs.certora.com/en/latest/docs/cvl/ghosts.html#restrictions-on-ghost-axioms)
    * [Ghosts vs. persistent ghosts](https://docs.certora.com/en/latest/docs/cvl/ghosts.html#ghosts-vs-persistent-ghosts)
      * [Persistent ghosts that survive havocs](https://docs.certora.com/en/latest/docs/cvl/ghosts.html#persistent-ghosts-that-survive-havocs)
      * [Persistent ghosts that survive reverts](https://docs.certora.com/en/latest/docs/cvl/ghosts.html#persistent-ghosts-that-survive-reverts)


## [Syntax](https://docs.certora.com/en/latest/docs/cvl/ghosts.html#id6)[](https://docs.certora.com/en/latest/docs/cvl/ghosts.html#syntax "Link to this heading")
The syntax for ghost declarations is given by the following [EBNF grammar](https://docs.certora.com/en/latest/docs/cvl/overview.html#ebnf-syntax):
```
ghost ::= "ghost" type id               (";" | "{" axioms "}")
    | "ghost" id "(" cvl_types ")" "returns" type (";" | "{" axioms "}")
persistent_ghost ::= "persistent" "ghost" type id               (";" | "{" axioms "}")
          | "persistent" "ghost" id "(" cvl_types ")" "returns" type (";" | "{" axioms "}")
type ::= basic_type
    | "mapping" "(" cvl_type "=>" type ")"
axiom ::= [ "init_state" ] "axiom" expression ";"

```
Copy to clipboard
See [Types](https://docs.certora.com/en/latest/docs/cvl/types.html) for the `type` and `cvl_type` productions, and [Expressions](https://docs.certora.com/en/latest/docs/cvl/expr.html) for the `expression` syntax.
## [Declaring ghost variables](https://docs.certora.com/en/latest/docs/cvl/ghosts.html#id7)[](https://docs.certora.com/en/latest/docs/cvl/ghosts.html#declaring-ghost-variables "Link to this heading")
Ghost variables must be declared at the top level of a specification file. A ghost variable declaration includes the keyword `ghost` followed by the type and name of the ghost variable.
The type of a ghost variable may be either a [CVL type](https://docs.certora.com/en/latest/docs/cvl/types.html) or a `mapping` type. Mapping types are similar to solidity mapping types. They must have CVL types as keys, but may contain either CVL types or mapping types as values.
For example, the following are valid ghost declarations:
```
ghostuintx;
ghostmapping(address=>mathint)balances;
ghostmapping(uint=>mapping(uint=>mathint))delegations;

```
Copy to clipboard
while the following are invalid:
```
ghost(uint,uint)x;// tuples are not CVL types
ghostmapping(mapping(uint=>uint)=>address)y;// mappings cannot be keys

```
Copy to clipboard
  * [simple `ghost` variable example](https://github.com/Certora/Examples/blob/14668d39a6ddc67af349bc5b82f73db73349ef18/CVLByExample/ERC20/certora/specs/ERC20.spec#L113)
  * This example uses an [`init_state` axiom](https://github.com/Certora/Examples/blob/14668d39a6ddc67af349bc5b82f73db73349ef18/CVLByExample/ERC20/certora/specs/ERC20.spec#L114)
  * [`ghost mapping` example](https://github.com/Certora/Examples/blob/14668d39a6ddc67af349bc5b82f73db73349ef18/CVLByExample/structs/BankAccounts/certora/specs/Bank.spec#L117)


## [Ghost Functions](https://docs.certora.com/en/latest/docs/cvl/ghosts.html#id8)[](https://docs.certora.com/en/latest/docs/cvl/ghosts.html#ghost-functions "Link to this heading")
CVL also has support for “ghost functions”. These serve a different purpose from ghost variables, although they can be used in similar ways.
Ghost functions must be declared at the top level of a specification file. A ghost function declaration includes the keyword `ghost` followed by the name and signature of the ghost function. Ghost functions should be used either:
  * when there are no updates to the ghost as the deterministic behavior and axioms are the only properties of the ghost
  * when updating the ghost - more than one entry is updated and then the havoc assuming statement is used.
    * [`ghost` function example](https://github.com/Certora/Examples/blob/14668d39a6ddc67af349bc5b82f73db73349ef18/CVLByExample/QuantifierExamples/DoublyLinkedList/certora/spec/dll-linkedcorrectly.spec#L24)


## [Restrictions on ghost definitions](https://docs.certora.com/en/latest/docs/cvl/ghosts.html#id9)[](https://docs.certora.com/en/latest/docs/cvl/ghosts.html#restrictions-on-ghost-definitions "Link to this heading")
  * A user-defined type, such as struct, array or interface is not allowed as the key or the output type of a `ghost mapping`.


## [Using ghost variables](https://docs.certora.com/en/latest/docs/cvl/ghosts.html#id10)[](https://docs.certora.com/en/latest/docs/cvl/ghosts.html#using-ghost-variables "Link to this heading")
While verifying a rule or invariant, the Prover considers every possible initial value of a ghost variable (subject to its [Ghost axioms](https://docs.certora.com/en/latest/docs/cvl/ghosts.html#ghost-axioms), see below).
Within CVL, you can read or write ghosts using the normal variable syntax. For example:
```
ghostmapping(address=>mathint)balances;
functionexample(addressuser){
balances[user]=x;
}

```
Copy to clipboard
The most common reason to use a ghost is to communicate information from a hook back to the rule that triggered it. For example, the following CVL checks that a call to the contract method `do_update(user)` changes the contract variable `userInfo[user]` and does not change `userInfo[other]` for any other user:
```
ghostmapping(address=>bool)updated;
hookSstoreuserInfo[KEYaddressu]uinti{
updated[u]=true;
}
ruleupdate_changes_user(addressuser){
updated[user]=false;
do_update(user);
assertupdated[user]==true,"do_update(user) should affect user";
}
ruleupdate_changes_no_other(addressuser,addressother){
requireuser!=other;
requireupdated[other]==false;
do_update(user);
assertupdated[other]==false;
}

```
Copy to clipboard
Here the `updated` ghost is used to communicate information from the `userInfo` hook back to the `updated_changes_user` and `updated_changes_no_other` rules.
## [Ghost axioms](https://docs.certora.com/en/latest/docs/cvl/ghosts.html#id11)[](https://docs.certora.com/en/latest/docs/cvl/ghosts.html#ghost-axioms "Link to this heading")
Ghost axioms are properties that the Prover assumes whenever it makes use of a ghost.
### [Global axioms](https://docs.certora.com/en/latest/docs/cvl/ghosts.html#id12)[](https://docs.certora.com/en/latest/docs/cvl/ghosts.html#global-axioms "Link to this heading")
Sometimes we might want to constrain the behavior of a ghost in some particular way. In CVL this is achieved by writing axioms. Axioms are simply CVL expressions that the tool will then assume are true about the ghost. For example:
```
ghostbar(uint256)returnsuint256{
axiomforalluint256x.bar(x)>10;
}

```
Copy to clipboard
In any rule that uses bar, no application of bar could ever evaluate to a number less than or equal to 10.
  * [`axiom` example](https://github.com/Certora/Examples/blob/14668d39a6ddc67af349bc5b82f73db73349ef18/CVLByExample/structs/BankAccounts/certora/specs/Bank.spec#L119)


### [Initial state axioms](https://docs.certora.com/en/latest/docs/cvl/ghosts.html#id13)[](https://docs.certora.com/en/latest/docs/cvl/ghosts.html#initial-state-axioms "Link to this heading")
When writing invariants, initial axioms are a way to express the “constructor state” of a ghost function. They are used only when checking the base step of invariants [Writing an invariant as a rule](https://docs.certora.com/en/latest/docs/cvl/invariants.html#invariant-as-rule). Before checking the initial state of an invariant, the Certora Prover adds a `require` for each `init_state` axiom. `init_state` axioms are not used in rules or the preservation check for invariants.
```
ghostmathintsumBalances{
// assuming value zero at the initial state before constructor
init_stateaxiomsumBalances==0;
}

```
Copy to clipboard
  * [initial state axiom example](https://github.com/Certora/Examples/blob/14668d39a6ddc67af349bc5b82f73db73349ef18/CVLByExample/ConstantProductPool/certora/spec/ConstantProductPool.spec#L207)


## [Restrictions on ghost axioms](https://docs.certora.com/en/latest/docs/cvl/ghosts.html#id14)[](https://docs.certora.com/en/latest/docs/cvl/ghosts.html#restrictions-on-ghost-axioms "Link to this heading")
  * A ghost axiom cannot refer to Solidity or CVL functions or to other ghosts. It can refer to the ghost itself.
  * Since the signature of a ghost contains just parameter types without names, it cannot refer to its parameters. `forall` can be used in order to refer the storage referred to by the parameters. [Example](https://github.com/Certora/Examples/blob/61ac29b1128c68aff7e8d1e77bc80bfcbd3528d6/CVLByExample/summary/ghost-summary/ghost-mapping/certora/specs/WithGhostSummary.spec#L12).


## [Ghosts vs. persistent ghosts](https://docs.certora.com/en/latest/docs/cvl/ghosts.html#id15)[](https://docs.certora.com/en/latest/docs/cvl/ghosts.html#ghosts-vs-persistent-ghosts "Link to this heading")
A `persistent ghost` is a `ghost` that will never be [havoc](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#glossary). The value of a non-persistent `ghost` will be `havoc'ed` when the Prover `havoc`s the storage, a `persistent ghost` however will keep its value when storage is havoced.
In most cases, non-persistent ghosts are the natural choice for a specification that requires extra tracking of information.
We present two examples where persistent ghosts are useful.
### [Persistent ghosts that survive havocs](https://docs.certora.com/en/latest/docs/cvl/ghosts.html#id16)[](https://docs.certora.com/en/latest/docs/cvl/ghosts.html#persistent-ghosts-that-survive-havocs "Link to this heading")
In the first example, we want to track the occurrence of a potential reentrant call[[1]](https://docs.certora.com/en/latest/docs/cvl/ghosts.html#reentrancy):
```
persistentghostboolreentrancy_happened{
init_stateaxiom!reentrancy_happened;
}
hookCALL(uintg,addressaddr,uintvalue,uintargsOffset,uintargsLength,
uintretOffset,uintretLength)uintrc{
if(addr==currentContract){
reentrancy_happened=reentrancy_happened
||executingContract==currentContract;
}
}
invariantno_reentrant_calls!reentrancy_happened;

```
Copy to clipboard
To see why a persistent ghost must be used here for the variable `reentrancy_happened`, consider the following contract:
```
contractNotReentrant{
functiontransfer1Token(IERC20a)external{
require(address(a)!=address(this));
a.transfer(msg.sender,1);
}
}

```
Copy to clipboard
If we do not apply any linking or dispatching for the call done on the target `a`, the call to `transfer` would havoc. During a havoc operation, the Prover conservatively assumes that almost any possible behavior can occur. In particular, it must assume that during the execution of the `a.transfer` call, non-persistent ghosts can be updated arbitrarily (e.g. by other contracts), and thus (assuming `reentrancy_happened` were not marked as persistent), the Prover considers the case where `reentrancy_happened` is set to `true` due to the havoc. Thus, when the `CALL` hook executes immediately after, it does so where the `reentrancy_happened` value is already `true`, and thus the value after the hook will remain `true`.
In the lower-level view of the tool, the sequence of events is as follows:
  1. A call to `a.transfer` which cannot be resolved and results in a [havoc](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#glossary) operation. Non-persistent ghosts are havoced, in particular `reentrancy_happened` if it were not marked as such.
  2. A `CALL` hook executes, updating `reentrancy_happened` based on its havoced value, meaning it can turn to true.


Therefore even if the addresses of `a` and `NotReentrant` are distinct, we could still falsely detect a reentrant call as `reentrancy_happened` was set to true due to non-determinism. The call trace would show `reentrancy_happened` as being determined to be true due to a havoc in the “Ghosts State” view under “Global State”.
### [Persistent ghosts that survive reverts](https://docs.certora.com/en/latest/docs/cvl/ghosts.html#id17)[](https://docs.certora.com/en/latest/docs/cvl/ghosts.html#persistent-ghosts-that-survive-reverts "Link to this heading")
In this example, we use persistent ghosts to determine if a revert happened with user-provided data or not. This can help distinguishing between compiler-generated reverts and user-specified reverts (but only in [Solidity versions prior to 0.8.x](https://soliditylang.org/blog/2020/10/28/solidity-0.8.x-preview/)). The idea is to set a ghost to true if a `REVERT` opcode is encountered with a positive buffer size. As in early Solidity versions the panic errors would compile to reverts with empty buffers, as well as user-provided `require`s with no message specified.
```
persistentghostboolsaw_user_defined_revert_msg;
hookREVERT(uintoffset,uintsize){
if(size>0){
saw_user_defined_revert_msg=true;
}
}
rulemark_methods_that_have_user_defined_reverts(methodf,enve,calldataargargs){
require!saw_user_defined_revert_msg;
f@withrevert(e,args);
satisfysaw_user_defined_revert_msg;
}

```
Copy to clipboard
To see why a regular ghost cannot be used to implement this rule, let’s consider the following trivial contract:
```
contractReverting{
functionnoUserDefinedRevertFlows(uinta,uintb)external{
uintc=a/b;// will see a potential division-by-zero revert
uint[]memoryarr=newuint[](1);
uintd=arr[a+b];// will see a potential out-of-bounds access revert;
}
functionuserDefinedRequireMsg(uinta)external{
require(a!=0,"a != 0");
}
functionemptyRequire(uinta)external{
require(a!=0);
}
}

```
Copy to clipboard
It is expected for the method `userDefinedRequireMsg` to satisfy the rule, and it should be the only method to satisfy it. Assuming `saw_user_defined_revert_msg` was defined as a regular, non-persistent ghost, the rule would not be satisfied for `userDefinedRequireMsg`: in case the input argument `a` is equal to 0, the contract reverts, and the value of `saw_user_defined_revert_msg` is reset to its value before the call, which must be `false` (because the rule required it before the call). In this case, after the call `saw_user_defined_revert_msg` cannot be set to true and thus the `satisfy` fails. Applying the same reasoning, it is clear that the same behavior happens for reverting behaviors of `noUserDefinedRevertFlows` and `emptyRequire`, which do not have user-defined revert messages. This means that if `saw_user_defined_revert_msg` is not marked persistent, the rule cannot distinguishing between methods that may revert with user-defined messages and methods that may not.
[[1](https://docs.certora.com/en/latest/docs/cvl/ghosts.html#id4)]
The example given here is very basic, the examples repository contains [more complete examples of reentrancy checks](https://github.com/Certora/Examples/tree/master/CVLByExample/Reentrancy)
[ Previous](https://docs.certora.com/en/latest/docs/cvl/sorts.html "Uninterpreted Sorts") [Next ](https://docs.certora.com/en/latest/docs/cvl/defs.html "Definitions")
© Copyright 2025, Certora, Inc.
Built with [Sphinx](https://www.sphinx-doc.org/) using a [theme](https://github.com/readthedocs/sphinx_rtd_theme) provided by [Read the Docs](https://readthedocs.org). 
