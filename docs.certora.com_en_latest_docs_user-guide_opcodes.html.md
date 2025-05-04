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
    * [Parametric rules](https://docs.certora.com/en/latest/docs/user-guide/parametric.html)
    * [Tracking changes with ghosts and hooks](https://docs.certora.com/en/latest/docs/user-guide/ghosts.html)
    * [Specification Design Patterns](https://docs.certora.com/en/latest/docs/user-guide/patterns/index.html)
    * [Using Opcode Hooks](https://docs.certora.com/en/latest/docs/user-guide/opcodes.html)
      * [Accessing environment variables](https://docs.certora.com/en/latest/docs/user-guide/opcodes.html#accessing-environment-variables)
      * [Detecting `CALL` instructions](https://docs.certora.com/en/latest/docs/user-guide/opcodes.html#detecting-call-instructions)
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
  * Using Opcode Hooks
  * [ View page source](https://docs.certora.com/en/latest/_sources/docs/user-guide/opcodes.md.txt)


# [Using Opcode Hooks](https://docs.certora.com/en/latest/docs/user-guide/opcodes.html#id1)[](https://docs.certora.com/en/latest/docs/user-guide/opcodes.html#using-opcode-hooks "Link to this heading")
[EVM opcode hooks](https://docs.certora.com/en/latest/docs/cvl/hooks.html#opcode-hooks) are useful for reasoning about the low-level behavior of your contracts, and for accessing EVM state that is otherwise unavailable in CVL. This guide gives a few examples of how opcode hooks can be used.
Contents
  * [Using Opcode Hooks](https://docs.certora.com/en/latest/docs/user-guide/opcodes.html#using-opcode-hooks)
    * [Accessing environment variables](https://docs.certora.com/en/latest/docs/user-guide/opcodes.html#accessing-environment-variables)
    * [Detecting `CALL` instructions](https://docs.certora.com/en/latest/docs/user-guide/opcodes.html#detecting-call-instructions)


## [Accessing environment variables](https://docs.certora.com/en/latest/docs/user-guide/opcodes.html#id2)[](https://docs.certora.com/en/latest/docs/user-guide/opcodes.html#accessing-environment-variables "Link to this heading")
In CVL, you can access EVM variables like `msg.sender` using an [environment object](https://docs.certora.com/en/latest/docs/cvl/types.html#env). However, `env` objects do not contain all of the EVM state that is available to contracts.
We made this choice for a few reasons: for one, it would be annoying to have to manually specify that global constants like the chain ID are same in every transaction. Another is that we have tried to decouple CVL from EVM as much as possible.
Nevertheless, sometimes you need access to EVM variables that are not included in the `env` type, such as the `CHAINID` or `GASPRICE`. You can use opcode hooks on the corresponding instructions to restrict these values or save them in [Declaring ghost variables](https://docs.certora.com/en/latest/docs/cvl/ghosts.html#ghost-variables) for use in rules.
For example, if your contract uses `chainid()` to detect whether it is running on the Ethereum Mainnet, you could ensure that the chain ID is always 1 (which is the Ethereum Mainnet chain ID) by adding the following hook:
```
hookCHAINIDuintid{
requireid==1;
}

```
Copy to clipboard
Alternatively, you could save the chain ID in a ghost variable and then use it in your rule:
```
ghostuintchain_id;
hookCHAINIDuintid{
chain_id=id;
}
/// The contract's behavior changes appropriately when run on mainnet
rulechainid_behavior_correct{
...
if(chain_id==1){
...
}else{
...
}
}

```
Copy to clipboard
## [Detecting `CALL` instructions](https://docs.certora.com/en/latest/docs/user-guide/opcodes.html#id3)[](https://docs.certora.com/en/latest/docs/user-guide/opcodes.html#detecting-call-instructions "Link to this heading")
Suppose you want to ensure that a specific contract function never makes an external call while it is in an emergency shutdown mode. In order to verify this property, you need to know whether the contract has made a call.
You can use a hook on the `CALL` opcode to write such a rule:
```
ghostboolmade_call;
hookCALL(uintg,addressaddr,uintvalue,uintargsOffset,uintargsLength,uintretOffset,uintretLength)uintrc{
made_call=true;
}
/// While in `emergencyMode`, no function can make an external call.
ruleno_call_during_emergency{
require!made_call;
requireemergencyMode();
methodf;enve;calldataargargs;
f(e,args);
assert!made_call;
}

```
Copy to clipboard
In this example, the `made_call` variable gets set to `true` whenever the contract executes the `CALL` opcode, which is used to make external calls. The rule simply asserts that this variable is `false` (note that we required `!made_call` to avoid counterexamples where `made_call` started out set).
[ Previous](https://docs.certora.com/en/latest/docs/user-guide/patterns/require-invariants.html "Require Invariants: Proving inter-dependent invariants") [Next ](https://docs.certora.com/en/latest/docs/user-guide/multicontract/index.html "Working with Multiple Contracts")
© Copyright 2025, Certora, Inc.
Built with [Sphinx](https://www.sphinx-doc.org/) using a [theme](https://github.com/readthedocs/sphinx_rtd_theme) provided by [Read the Docs](https://readthedocs.org). 
