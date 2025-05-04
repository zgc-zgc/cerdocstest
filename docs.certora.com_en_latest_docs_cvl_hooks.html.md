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
    * [Definitions](https://docs.certora.com/en/latest/docs/cvl/defs.html)
    * [Hooks](https://docs.certora.com/en/latest/docs/cvl/hooks.html)
      * [Syntax](https://docs.certora.com/en/latest/docs/cvl/hooks.html#syntax)
      * [Examples](https://docs.certora.com/en/latest/docs/cvl/hooks.html#examples)
      * [Load and store hooks](https://docs.certora.com/en/latest/docs/cvl/hooks.html#load-and-store-hooks)
        * [Access paths](https://docs.certora.com/en/latest/docs/cvl/hooks.html#access-paths)
        * [Access path caveats](https://docs.certora.com/en/latest/docs/cvl/hooks.html#access-path-caveats)
        * [Hooking on all storage loads or stores](https://docs.certora.com/en/latest/docs/cvl/hooks.html#hooking-on-all-storage-loads-or-stores)
      * [EVM opcode hooks](https://docs.certora.com/en/latest/docs/cvl/hooks.html#evm-opcode-hooks)
        * [Call hooks](https://docs.certora.com/en/latest/docs/cvl/hooks.html#call-hooks)
        * [Known inter-dependencies and common pitfalls](https://docs.certora.com/en/latest/docs/cvl/hooks.html#known-inter-dependencies-and-common-pitfalls)
      * [Hook bodies](https://docs.certora.com/en/latest/docs/cvl/hooks.html#hook-bodies)
        * [Keywords available in hook bodies](https://docs.certora.com/en/latest/docs/cvl/hooks.html#keywords-available-in-hook-bodies)
        * [Reentrant hooks](https://docs.certora.com/en/latest/docs/cvl/hooks.html#reentrant-hooks)
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
  * Hooks
  * [ View page source](https://docs.certora.com/en/latest/_sources/docs/cvl/hooks.md.txt)


# [Hooks](https://docs.certora.com/en/latest/docs/cvl/hooks.html#id5)[](https://docs.certora.com/en/latest/docs/cvl/hooks.html#hooks "Link to this heading")
Hooks are used to attach CVL code to certain low-level operations, such as loads and stores to specific storage variables.
Each hook contains a pattern that describes what operations cause the hook to be invoked, and a block of code that is executed when the contract performs those operations.
The remainder of this document describes the operation of hooks in detail. For examples of idiomatic hook usage, see [Tracking changes with ghosts and hooks](https://docs.certora.com/en/latest/docs/user-guide/ghosts.html#tracking-changes) and [Using Opcode Hooks](https://docs.certora.com/en/latest/docs/user-guide/opcodes.html#using-opcodes).
Contents
  * [Hooks](https://docs.certora.com/en/latest/docs/cvl/hooks.html#hooks)
    * [Syntax](https://docs.certora.com/en/latest/docs/cvl/hooks.html#syntax)
    * [Examples](https://docs.certora.com/en/latest/docs/cvl/hooks.html#examples)
    * [Load and store hooks](https://docs.certora.com/en/latest/docs/cvl/hooks.html#load-and-store-hooks)
      * [Access paths](https://docs.certora.com/en/latest/docs/cvl/hooks.html#access-paths)
      * [Access path caveats](https://docs.certora.com/en/latest/docs/cvl/hooks.html#access-path-caveats)
      * [Hooking on all storage loads or stores](https://docs.certora.com/en/latest/docs/cvl/hooks.html#hooking-on-all-storage-loads-or-stores)
        * [Notes on transient storage.](https://docs.certora.com/en/latest/docs/cvl/hooks.html#notes-on-transient-storage)
    * [EVM opcode hooks](https://docs.certora.com/en/latest/docs/cvl/hooks.html#evm-opcode-hooks)
      * [Call hooks](https://docs.certora.com/en/latest/docs/cvl/hooks.html#call-hooks)
      * [Known inter-dependencies and common pitfalls](https://docs.certora.com/en/latest/docs/cvl/hooks.html#known-inter-dependencies-and-common-pitfalls)
    * [Hook bodies](https://docs.certora.com/en/latest/docs/cvl/hooks.html#hook-bodies)
      * [Keywords available in hook bodies](https://docs.certora.com/en/latest/docs/cvl/hooks.html#keywords-available-in-hook-bodies)
      * [Reentrant hooks](https://docs.certora.com/en/latest/docs/cvl/hooks.html#reentrant-hooks)


## [Syntax](https://docs.certora.com/en/latest/docs/cvl/hooks.html#id6)[](https://docs.certora.com/en/latest/docs/cvl/hooks.html#syntax "Link to this heading")
The syntax for hooks is given by the following EBNF grammar:
```
hook ::= "hook" pattern block
pattern ::= "Sstore" access_path param [ "(" param ")" ]
     | "Sload" param access_path
     | opcode  [ "(" params ")" ] [ param ]
access_path ::= id
       | [ id "." ] "(" "slot" number ")"
       | access_path "." id
       | access_path "[" "KEY"  basic_type id "]"
       | access_path "[" "INDEX" basic_type id "]"
       | access_path "." "(" "offset" number ")"
opcode ::= "ALL_SLOAD" | "ALL_SSTORE" | "ALL_TLOAD" | "ALL_TSTORE" | ...
param ::= evm_type id

```
Copy to clipboard
See [EVM opcode hooks](https://docs.certora.com/en/latest/docs/cvl/hooks.html#opcode-hooks) below for the list of available opcodes.
See [Statements](https://docs.certora.com/en/latest/docs/cvl/statements.html) for information about the `statement` production; see [Types](https://docs.certora.com/en/latest/docs/cvl/types.html) for the `evm_type` production; see [Basic Syntax](https://docs.certora.com/en/latest/docs/cvl/basics.html) for the `number` production.
It is prohibited to have multiple hooks with the same hook pattern. Two hooks have the same hook pattern if both are `Sstore` hooks with the same access path, both are `Sload` hooks with the same access path, or both are opcode hooks with the same opcode. Doing so will result in an error like this: `The declared hook pattern <second hook> duplicates the hook pattern <first hook> at <spec file>. A hook pattern may only be used once.` Note that two access paths are considered to be “the same” if they resolve to the same storage address. Syntactically different access paths can alias, e.g., when accessing a member by name (`contract.member`) or by slot (`contract.(slot n)`).
## [Examples](https://docs.certora.com/en/latest/docs/cvl/hooks.html#id7)[](https://docs.certora.com/en/latest/docs/cvl/hooks.html#examples "Link to this heading")
  * [store hook example](https://github.com/Certora/Examples/blob/14668d39a6ddc67af349bc5b82f73db73349ef18/CVLByExample/ERC20/certora/specs/ERC20.spec#L117)
  * [load hook example](https://github.com/Certora/Examples/blob/14668d39a6ddc67af349bc5b82f73db73349ef18/CVLByExample/structs/BankAccounts/certora/specs/Bank.spec#L141)


See [Using Opcode Hooks](https://docs.certora.com/en/latest/docs/user-guide/opcodes.html#using-opcodes) and [Tracking changes with ghosts and hooks](https://docs.certora.com/en/latest/docs/user-guide/ghosts.html#tracking-changes) for additional examples.
## [Load and store hooks](https://docs.certora.com/en/latest/docs/cvl/hooks.html#id8)[](https://docs.certora.com/en/latest/docs/cvl/hooks.html#load-and-store-hooks "Link to this heading")
Load hooks are executed before a read from a specific location in storage, while store hooks are executed before a write to a specific location in storage.
The locations to be matched are given by an access path, such as a contract variable, array index, or a slot number. See [Access paths](https://docs.certora.com/en/latest/docs/cvl/hooks.html#access-paths) below for information on the available access paths.
A load pattern contains the keyword `Sload`, followed by the type and name of a variable that will hold the loaded value, followed by an access path indicating the location that is read.
For example, here is a load hook that will execute whenever a contract reads the value of `C.owner`:
```
hookSloadaddressoC.owner{...}

```
Copy to clipboard
Inside the body of this hook, the variable `o` will be bound to the value that was read.
A store pattern contains the keyword `Sstore`, followed by an access path indicating the location that is being written to, followed by the type and name of a variable to hold the value that is being stored. Optionally, the pattern may also include the type and name of a variable to store the previous value that is being overwritten.
For example, here is a store hook that will execute whenever a contract writes the value of `C.totalSupply`:
```
hookSstoreC.totalSupplyuintts(uintold_ts){...}

```
Copy to clipboard
Inside the body of this hook, the variable `ts` will be bound to the value that is being written to the `totalSupply` variable, while `old_ts` is bound to the value that was stored there previously.
If you do not need to refer to the old value, you can omit the variable declaration for it. For example, the following hook only binds the new value of `C.totalSupply`:
```
hookSstoreC.totalSupplyuintts{...}

```
Copy to clipboard
Note
A hook will **not** be triggered by CVL code, including access to solidity storage from CVL.
### [Access paths](https://docs.certora.com/en/latest/docs/cvl/hooks.html#id9)[](https://docs.certora.com/en/latest/docs/cvl/hooks.html#access-paths "Link to this heading")
The patterns for load and store hooks are fine-grained; they allow you to hook on accesses to specific contract variables or specific array, struct, or mapping accesses.
Storage locations are designated by “access paths”. An access path starts with either the name of a contract field, or a [slot number](https://docs.soliditylang.org/en/v0.8.17/internals/layout_in_storage.html).
Contract fields may be qualified by the contract that defines them (e.g. `Contract.field`). If the contract name is omitted, it defaults to `currentContract`. The contract name may either be an instance variable introduced by a [using statement][using] or the name of a contract on the [scene](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-0).
Note
If a contract inherits multiple variables with the same name, you cannot use that variable as an access path.
If the indicated location holds a struct, you can refer to a specific field of the struct by appending `.<field-name>` to the path. For example, the following hook will execute on every store to the `balance` field of the struct `C.owner`:
```
hookSstoreC.owner.balanceuintb{...}

```
Copy to clipboard
If the indicated location holds an array, you can refer to an arbitrary element of the array by appending `[INDEX uint <variable>]`. This pattern will match any store to an element of the array, and will bind the named variable to the index of the access. For example, the following hook will execute on any write to the array `C.entries` and will update the corresponding entry of the ghost mapping `_entries` to match:
```
hookSstoreC.entries[INDEXuinti]uinte{
_entries[i]=e;
}

```
Copy to clipboard
Additionally, if the indicated location holds a _dynamic_ array, you can refer to accesses to the length of the array with `.length`:
```
hookSstoreC.entries.lengthuintlen{
_len=len;// updates a ghost variable `_len` with the length is written to storage.
}

```
Copy to clipboard
Similarly, if the indicated location holds a mapping, you can refer to an arbitrary entry by appending `[KEY <type> <variable>]`. This pattern will match any write to the mapping, and will bind the named variable to the key. For example, the following hook will execute on any write to the mapping `C.balances`, and will update the `_balances` ghost accordingly:
```
hookSstoreC.balances[KEYaddressuser]uintbalance{
_balances[user]=balance;
}

```
Copy to clipboard
Finally, there is the low-level access pattern `<base>.(offset <n>)` for matching loads and stores that are a specific number of bytes from the base. For example, the following hook will match writes to the third or fourth byte of slot 1 (these two bytes are matched because the type of the variable is `uint16`:
```
hookSstore(slot1).(offset2)uint16b{...}

```
Copy to clipboard
These different kinds of paths can be combined, subject to restrictions listed below. For example, the following hook will execute whenever the contract writes to the `balance` field of a struct in the `users` mapping of contract `C`:
```
hookC.users[KEYaddressuser].balanceuintv(uintold_value){...}

```
Copy to clipboard
Inside the body of the hook, the variable `user` will refer to the address that was used as the key into the mapping `C.users`; the variable `v` will contain the value that is written, and the variable `old_value` will contain the value that was previously stored there.
There are a few restrictions on the available combinations of low-level and high-level access paths:
  * You cannot access struct fields on access paths that contain `slot` or `offset` components, because the struct type is not known.
  * You can only use `KEY` and `INDEX` patterns on word-aligned access paths (i.e. any `offset` components must be multiples of 32).


Note
The only available access paths for `solc` versions 5.17 and older are `slot` and `offset` paths.
### [Access path caveats](https://docs.certora.com/en/latest/docs/cvl/hooks.html#id10)[](https://docs.certora.com/en/latest/docs/cvl/hooks.html#access-path-caveats "Link to this heading")
In order to apply hooks correctly, the Prover must analyze the contract’s use of storage. In some cases, especially in the presence of inline assembly `sload` and `sstore` instructions, the analysis will fail. In this case, hooks may not be applied.
If storage analysis fails, you will see a message indicating the failure in the global problems view of the rule report. See [Analysis of EVM storage and EVM memory](https://docs.certora.com/en/latest/docs/prover/techniques/index.html#storage-and-memory-analysis) for more details.
### [Hooking on all storage loads or stores](https://docs.certora.com/en/latest/docs/cvl/hooks.html#id11)[](https://docs.certora.com/en/latest/docs/cvl/hooks.html#hooking-on-all-storage-loads-or-stores "Link to this heading")
Load and store hooks apply to reads and writes to specific storage locations. In some cases, it is useful to instrument every load or store, regardless of the location.
The `ALL_SLOAD` and `ALL_SSTORE` opcode hooks are used for this purpose; they will be executed on every load and store instruction (in all contracts) respectively. See [EVM opcode hooks](https://docs.certora.com/en/latest/docs/cvl/hooks.html#opcode-hooks) below for the general syntax of opcode hooks.
The `ALL_SLOAD` opcode hook takes one input `uint` argument containing the slot number of the load instruction, and has one `uint` output containing the value that is loaded from the slot. For example:
```
hookALL_SLOAD(uintslot)uintval{...}

```
Copy to clipboard
The `ALL_SSTORE` opcode hook takes two input `uint` arguments; the first is the slot number of the store instruction, and the second is the value being stored. For example:
```
hookALL_SSTORE(uintslot,uintval){...}

```
Copy to clipboard
Note
The storage splitting optimization must be disabled using the [enableStorageSplitting](https://docs.certora.com/en/latest/docs/prover/cli/options.html#enablestoragesplitting) option in order to use the `ALL_SLOAD` or `ALL_SSTORE` hooks.
If a load instruction matches an `Sload` hook pattern and there is also an `ALL_SLOAD` hook, then both hooks will be executed; the `Sload` hook will apply first, and then the `ALL_SLOAD` hook.
Similarly, if a store would trigger both an `Sstore` pattern and an `ALL_SSTORE` pattern, the `Sstore` hook would be executed, followed by the `ALL_SSTORE` hook.
Note
Just like the usual opcode hooks, the raw storage hooks are applied on all contracts. This means that a storage access on _any_ contract will trigger the hook. Therefore, in a rule that models calls to multiple contracts, if two contracts are accessing the same slot the same hook code will be called with the same slot number.
#### [Notes on transient storage.](https://docs.certora.com/en/latest/docs/cvl/hooks.html#id12)[](https://docs.certora.com/en/latest/docs/cvl/hooks.html#notes-on-transient-storage "Link to this heading")
In a similar vein to `ALL_SLOAD` and `ALL_SSTORE` hooks, CVL also allows to hook on `TLOAD` and `TSTORE` instructions for updating the transient storage, using the `ALL_TLOAD` and `ALL_TSTORE` hooks. The hooks for transient storage access share the syntax of their regular storage counterparts.
Given that Solidity only allows (as of v0.8.25) access to transient storage via inline-assembly, and has no notion of structure to transient storage, Prover currently does not expose access-path based access like for the regular storage hooks.
For more information on how the Prover models transient storage, please refer to the relevant section on [transient storage](https://docs.certora.com/en/latest/docs/cvl/transient.html#transient-storage).
## [EVM opcode hooks](https://docs.certora.com/en/latest/docs/cvl/hooks.html#id13)[](https://docs.certora.com/en/latest/docs/cvl/hooks.html#evm-opcode-hooks "Link to this heading")
Opcode hooks are executed just after[[1]](https://docs.certora.com/en/latest/docs/cvl/hooks.html#before-hooks) a contract executes a specific [EVM opcode](https://ethereum.org/en/developers/docs/evm/opcodes/). An opcode hook pattern consists of the name of the opcode, followed by the inputs to the opcode (if any), followed by the type and variable name for the output (if any).
For example, the following hook will execute immediately after any contract executes the `EXTCODESIZE` instruction:
```
hookEXTCODESIZE(addressaddr)uintv{...}

```
Copy to clipboard
Within the body of the hook, the `addr` variable will be bound to the address argument to the opcode, and the variable `v` will be bound to the returned value of the opcode.
Note
Opcode hooks are applied to _all_ contracts, not just the main contract under verification.
Opcode hooks have the same names, arguments, and return values as the corresponding [EVM opcodes](https://ethereum.org/en/developers/docs/evm/opcodes/), with the exception of the `CREATE1` hook, which corresponds to the `CREATE` opcode.
Below is the set of supported opcode hook patterns:
```
hookADDRESSaddressv
hookBALANCE(addressaddr)uintv
hookORIGINaddressv
hookCALLERaddressv
hookCALLVALUEuintv
hookCODESIZEuintv
hookCODECOPY(uintdestOffset,uintoffset,uintlength)
hookGASPRICEuintv
hookEXTCODESIZE(addressaddr)uintv
hookEXTCODECOPY(addressb,uintdestOffset,uintoffset,uintlength)
hookEXTCODEHASH(addressa)bytes32hash
hookBLOCKHASH(uintn)bytes32hash
hookCOINBASEaddressv
hookTIMESTAMPuintv
hookNUMBERuintv
hookDIFFICULTYuintv
hookGASLIMITuintv
hookCHAINIDuintv
hookSELFBALANCEuintv
hookBASEFEEuintv
hookMSIZEuintv
hookGASuintv
hookLOG0(uintoffset,uintlength)
hookLOG1(uintoffset,uintlength,bytes32t1)
hookLOG2(uintoffset,uintlength,bytes32t1,bytes32t2)
hookLOG3(uintoffset,uintlength,bytes32t1,bytes32t2,bytes32t3)
hookLOG4(uintoffset,uintlength,bytes32t1,bytes32t2,bytes32t3,bytes32t4)
hookCREATE1(uintvalue,uintoffset,uintlength)addressv
hookCREATE2(uintvalue,uintoffset,uintlength,bytes32salt)addressv
hookCALL(uintg,addressaddr,uintvalue,uintargsOffset,uintargsLength,uintretOffset,uintretLength)uintrc
hookCALLCODE(uintg,addressaddr,uintvalue,uintargsOffset,uintargsLength,uintretOffset,uintretLength)uintrc
hookDELEGATECALL(uintg,addressaddr,uintargsOffset,uintargsLength,uintretOffset,uintretLength)uintrc
hookSTATICCALL(uintg,addressaddr,uintargsOffset,uintargsLength,uintretOffset,uintretLength)uintrc
hookREVERT(uintoffset,uintsize)
hookBLOBHASH(uintn)bytes32hash
hookSELFDESTRUCT(addressa)

```
Copy to clipboard
### [Call hooks](https://docs.certora.com/en/latest/docs/cvl/hooks.html#id14)[](https://docs.certora.com/en/latest/docs/cvl/hooks.html#call-hooks "Link to this heading")
We provide hooks for all four call opcodes: [`CALL`](https://www.evm.codes/#f1), [`CALLCODE`](https://www.evm.codes/#f2), [`DELEGATECALL`](https://www.evm.codes/#f4), and [`STATICCALL`](https://www.evm.codes/#fa). The hook parameters match the stack inputs of the respective opcodes.
The arguments for the call arguments and return values (`argsOffset`, `argsSize`, `retOffset`, and `retSize`) mostly exist for future use. Their values can be consumed, but currently they cannot be used to read data stored in memory before or after the call.
These hooks can be very useful to establish sensible security invariants. As an example, suppose no external code should gain write access to the data of the current contract. Both `CALLCODE` and `DELEGATECALL` have the potential to do exactly that by calling into another contract but keeping the current context. Note that there are exceptions to this property whenever _trusted_ 3rd party libraries are used. It might also be necessary to restrict these checks to the contract of interest.
```
hookCALLCODE(uintg,addressaddr,uintvalue,uintargsOffset,uintargsLength,uintretOffset,uintretLength)uintrc{
// using CALLCODE is generally not expected in this contract
assert(executingContract!=currentContract,"we should not use `callcode`");
}
hookDELEGATECALL(uintg,addressaddr,uintargsOffset,uintargsLength,uintretOffset,uintretLength)uintrc{
// DELEGATECALL is used in this contract, but it only ever calls into itself
assert(executingContract!=currentContract||addr==currentContract,
"we should only `delegatecall` into ourselves"
);
}

```
Copy to clipboard
### [Known inter-dependencies and common pitfalls](https://docs.certora.com/en/latest/docs/cvl/hooks.html#id15)[](https://docs.certora.com/en/latest/docs/cvl/hooks.html#known-inter-dependencies-and-common-pitfalls "Link to this heading")
Hooks are instrumented for every appearance of the matching instruction in the bytecode, as generated by a high-level source compiler such as the Solidity compiler. The behavior of the bytecode may sometimes be surprising. For example, every Solidity method call to a non-payable function will contain an early call to `CALLVALUE` to check that it is 0. This means that every time a non-payable Solidity function is invoked, the `CALLVALUE` hook will be triggered.
## [Hook bodies](https://docs.certora.com/en/latest/docs/cvl/hooks.html#id16)[](https://docs.certora.com/en/latest/docs/cvl/hooks.html#hook-bodies "Link to this heading")
The body of a hook may contain almost any CVL code, including calls to other Solidity functions. The only exception is that hooks may not contain parametric method calls. Expressions in hook bodies may reference variables bound by the hook pattern.
### [Keywords available in hook bodies](https://docs.certora.com/en/latest/docs/cvl/hooks.html#id17)[](https://docs.certora.com/en/latest/docs/cvl/hooks.html#keywords-available-in-hook-bodies "Link to this heading")
Hook bodies may refer to the special CVL variable `executingContract`, which contains the address of the contract whose code triggered the hook.
The call opcodes (`CALL`, `CALLCODE`, `STATICCALL` and `DELEGATECALL`) may also refer to a special CVL variable `selector`, which can be used to compare to a specific method signature selector. For example, here the hook body will assert that the native token value passed in the call is 0, only for a `transfer(address,uint)` call:
```
hookCALL(uintg,addressaddr,uintvalue,uintargsOffs,uintargLength,uintretOffset,uintretLength)uintrc{
if(selector==sig:transfer(address,uint).selector){
assertvalue==0;
}
}

```
Copy to clipboard
Note
In case the size of the input to the call is less than 4 bytes, the value of `selector` is 0. This can be checked by comparing the `argLength` argument of the hook to 4.
### [Reentrant hooks](https://docs.certora.com/en/latest/docs/cvl/hooks.html#id18)[](https://docs.certora.com/en/latest/docs/cvl/hooks.html#reentrant-hooks "Link to this heading")
While a hook is executing, additional hooks are skipped. If a hook calls a contract function which would normally cause another hook to execute, the inner hook will not execute.
For example, suppose the contract function `updateX()` always assigned to the value `x`, and consider the following hook (see [`HookReentrancy.spec` here](https://github.com/Certora/Examples/tree/28cb774fc03767e8aeaf00ea1bb0fac7db595fc9/ReferenceManual/HookReentrancy) for the complete example):
```
 1/// the number of stores to `x`
 2ghostmathintxStoreCount;
 3
 4/// increment xStoreCount and recursively update `x`
 5hookSstorexuintv{
 6xStoreCount=xStoreCount+1;
 7if(xStoreCount<5){
 8updateX();
 9}
10}
11
12/// This rule will pass because hooks are not recursively applied
13rulecheckStoreCount{
14requirexStoreCount==0;
15updateX();
16assertxStoreCount==1;
17}

```
Copy to clipboard
In this example, the rule `checkStoreCount` calls `updateX` on line 15, which updates `x`, triggering the hook on line 5. The hook then calls `updateX` again on line 8. The recursive call to `updateX` will then update `x` a second time.
At this point, you may expect that the hook will be triggered a second time, but because there is already a hook executing, this second update to `x` will not trigger the hook. Therefore the `xStoreCount` ghost will _not_ be updated a second time, so its final value will be `1`.
[[1](https://docs.certora.com/en/latest/docs/cvl/hooks.html#id3)]
For halting instructions such as `REVERT` and `SELFDESTRUCT`, the hook is executed before the instruction instead of after.
[ Previous](https://docs.certora.com/en/latest/docs/cvl/defs.html "Definitions") [Next ](https://docs.certora.com/en/latest/docs/cvl/transient.html "Transient Storage")
© Copyright 2025, Certora, Inc.
Built with [Sphinx](https://www.sphinx-doc.org/) using a [theme](https://github.com/readthedocs/sphinx_rtd_theme) provided by [Read the Docs](https://readthedocs.org). 
