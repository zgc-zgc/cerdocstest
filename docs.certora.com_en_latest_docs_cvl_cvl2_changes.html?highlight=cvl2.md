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
    * [Transient Storage](https://docs.certora.com/en/latest/docs/cvl/transient.html)
    * [Foundry Integration (Alpha)](https://docs.certora.com/en/latest/docs/cvl/foundry-integration.html)
    * [Changes Since CVL 1](https://docs.certora.com/en/latest/docs/cvl/index.html#changes-since-cvl-1)
      * [Changes Introduced in CVL 2](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html)
        * [Superficial syntax changes](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#superficial-syntax-changes)
        * [Changes to methods block entries](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#changes-to-methods-block-entries)
        * [Changes to integer types](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#changes-to-integer-types)
        * [Changes to the fallback function](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#changes-to-the-fallback-function)
        * [Removed features](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#removed-features)
        * [Changes to the Command Line Interface (CLI)](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#changes-to-the-command-line-interface-cli)
      * [CVL2 Migration Guide](https://docs.certora.com/en/latest/docs/cvl/cvl2/migration.html)
      * [Certora CLI 5.0 Changes](https://docs.certora.com/en/latest/docs/cvl/v5-changes.html)
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
  * Changes Introduced in CVL 2
  * [ View page source](https://docs.certora.com/en/latest/_sources/docs/cvl/cvl2/changes.md.txt)


# [Changes Introduced in CVL 2](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#id2)[](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#changes-introduced-in-cvl-2 "Link to this heading")
CVL 2 is a major overhaul to the type system of CVL. Though many of the changes are internal, we wanted to take this opportunity to introduce a few improvements to the syntax. The general goal of these changes is to make the behavior of CVL more explicit and predictable, and to bring the syntax more in line with Solidity’s syntax.
This document summarizes the changes to CVL syntax introduced by CVL 2.
The `CVLMigration` repository contains examples demonstrating each of the changes; the `cvl1` branch contains the examples in valid CVL 1 syntax, while the `cvl2` branch contains the same examples in CVL 2 syntax. You can see the differences [here](https://github.com/Certora/CVL2Migration/compare/cvl1..cvl2?diff=split), our you can clone [the repository](https://github.com/Certora/CVL2Migration) and compare the `cvl1` and `cvl2` branches using your favorite tools.
Contents
  * [Changes Introduced in CVL 2](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#changes-introduced-in-cvl-2)
    * [Superficial syntax changes](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#superficial-syntax-changes)
      * [`function` and `;` required for methods block entries](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#function-and-required-for-methods-block-entries)
      * [Required `;` in more places](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#required-in-more-places)
      * [Method literals require `sig:`](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#method-literals-require-sig)
      * [Use of contract name instead of `using` variable](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#use-of-contract-name-instead-of-using-variable)
      * [Rules must start with `rule`](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#rules-must-start-with-rule)
    * [Changes to methods block entries](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#changes-to-methods-block-entries)
      * [Most Solidity types allowed as arguments](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#most-solidity-types-allowed-as-arguments)
      * [Required `internal` or `external` annotation](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#required-internal-or-external-annotation)
      * [`optional` methods block entries](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#optional-methods-block-entries)
      * [Required `calldata`, `memory`, or `storage` annotations for reference types](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#required-calldata-memory-or-storage-annotations-for-reference-types)
      * [Summaries only apply to one contract by default](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#summaries-only-apply-to-one-contract-by-default)
      * [Requirements on `returns`](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#requirements-on-returns)
    * [Changes to integer types](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#changes-to-integer-types)
      * [Mathematical operations return `mathint`](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#mathematical-operations-return-mathint)
      * [Implicit and explicit casting](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#implicit-and-explicit-casting)
      * [Casting enums to integer types](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#casting-enums-to-integer-types)
      * [Casting addresses to bytes32](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#casting-addresses-to-bytes32)
      * [Modulo operator `%` always returns non-negative values](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#modulo-operator-always-returns-non-negative-values)
      * [Support for `bytes1`…`bytes32`](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#support-for-bytes1-bytes32)
      * [Changes for bitwise operations](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#changes-for-bitwise-operations)
    * [Changes to the fallback function](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#changes-to-the-fallback-function)
    * [Removed features](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#removed-features)
      * [Methods entries for sighashes](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#methods-entries-for-sighashes)
      * [`invoke`, `sinvoke`, and `call`](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#invoke-sinvoke-and-call)
      * [`static_assert` and `static_require`](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#static-assert-and-static-require)
      * [`invoke_fallback` and `certorafallback()`](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#invoke-fallback-and-certorafallback)
      * [`invoke_whole`](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#invoke-whole)
      * [Havocing local variables](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#havocing-local-variables)
      * [Destructuring syntax for struct returns](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#destructuring-syntax-for-struct-returns)
      * [`bytes[]` and `string[]`](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#bytes-and-string)
      * [`pragma`](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#pragma)
      * [`events`](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#events)
    * [Changes to the Command Line Interface (CLI)](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#changes-to-the-command-line-interface-cli)
      * [Flags Renaming](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#flags-renaming)
      * [`Prover Args`](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#prover-args)
      * [`Solidity Compiler Args`](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#solidity-compiler-args)
      * [Enhanced server support](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#enhanced-server-support)


## [Superficial syntax changes](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#id3)[](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#superficial-syntax-changes "Link to this heading")
There are several simple changes to the syntax to make specs more uniform and consistent, and to reduce the superficial differences with Solidity.
### [`function` and `;` required for methods block entries](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#id4)[](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#function-and-required-for-methods-block-entries "Link to this heading")
In CVL 2, methods block entries must now start with `function` and end with `;` (semicolons were optional in CVL 1). For example ([CVL 1](https://github.com/Certora/CVL2Migration/blob/cvl1/certora/spec/MethodsEntries.spec), [CVL 2](https://github.com/Certora/CVL2Migration/blob/cvl2/certora/spec/MethodsEntries.spec), [diff](https://github.com/Certora/CVL2Migration/compare/cvl1..cvl2?diff=split#diff-9cd1ae6f2c8146e323568cb25c79d4f6671fcb690872dce33591bd514759fc24)):
```
transferFrom(address,address,uint)returns(bool)envfree

```
Copy to clipboard
will become
```
functiontransferFrom(address,address,uint)externalreturns(bool)envfree;

```
Copy to clipboard
(note also the addition of `external`, [described below](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#cvl2-visibility)).
This is also true for entries with summaries:
```
balanceOf(address)returns(uint256)=>ALWAYS(3)

```
Copy to clipboard
will become
```
functionbalanceOf(address)externalreturns(uint256)=>ALWAYS(3);

```
Copy to clipboard
If you do not change this, you will get an error message like the following:
```
CRITICAL: [main] ERROR ALWAYS - certora/spec/MethodsEntries.spec:4:5: Syntax error: unexpected token near ID(transferFrom)
CRITICAL: [main] ERROR ALWAYS - certora/spec/MethodsEntries.spec:4:5: Couldn't repair and continue parse unexpected token near ID(transferFrom)

```
Copy to clipboard
### [Required `;` in more places](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#id5)[](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#required-in-more-places "Link to this heading")
`using`, `import`, `use`, and `invariant` statements all require a `;` at the end. For example ([CVL 1](https://github.com/Certora/CVL2Migration/blob/cvl1/certora/spec/Semicolons.spec), [CVL 2](https://github.com/Certora/CVL2Migration/blob/cvl2/certora/spec/Semicolons.spec), [diff](https://github.com/Certora/CVL2Migration/compare/cvl1..cvl2?diff=split#diff-15fb1ef5e6524f8a661d83ae5160b6b072840c5c54bf8d07733aab32b9da73f7)):
```
invariantbalanceOfZeroIsZero()
balanceOf(0)==0

```
Copy to clipboard
becomes
```
invariantbalanceOfZeroIsZero()
balanceOf(0)==0;

```
Copy to clipboard
`use` and `invariant` statements do not require (and may not have) a semicolon if they are followed by a `preserved` or `filtered` block. For example, the following is valid in both CVL 1 and CVL 2:
```
invarianttotalSupplyBoundsBalance(addressa)
balanceOf(a)<=totalSupply()
{preserved{requirefalse;}}

```
Copy to clipboard
If you do not change this, you will see an error like the following:
```
CRITICAL: [main] ERROR ALWAYS - certora/spec/Semicolons.spec:5:1: Syntax error: unexpected token near using
CRITICAL: [main] ERROR ALWAYS - certora/spec/Semicolons.spec:5:1: Couldn't repair and continue parse unexpected token near using

```
Copy to clipboard
### [Method literals require `sig:`](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#id6)[](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#method-literals-require-sig "Link to this heading")
In some places in CVL, you can refer to a contract method by its name and argument types. For example, you might write ([CVL 1](https://github.com/Certora/CVL2Migration/blob/cvl1/certora/spec/MethodLiterals.spec), [CVL 2](https://github.com/Certora/CVL2Migration/blob/cvl2/certora/spec/MethodLiterals.spec), [diff](https://github.com/Certora/CVL2Migration/compare/cvl1..cvl2?diff=split#diff-41df8240fa5faa12531baa82863891b94abf3fb3b859bdd10bafde73b60eda5d)):
```
f.selector==approve(address,uint).selector

```
Copy to clipboard
In this example, `approve(address,uint)` is a _method literal_. In CVL 2, these methods literals must now start with `sig:`. For example, the above would become:
```
f.selector==sig:approve(address,uint).selector

```
Copy to clipboard
If you do not change this, you will see the following error:
```
Error: Error in spec file (MethodLiterals.spec:14:5): Variable address is undefined (first instance only reported)
Error: Error in spec file (MethodLiterals.spec:14:5): Variable uint is undefined (first instance only reported)
Error: Error in spec file (MethodLiterals.spec:15:34): could not type expression "address", message: unknown variable "address"
Error: Error in spec file (MethodLiterals.spec:15:43): could not type expression "uint", message: unknown variable "uint"

```
Copy to clipboard
### [Use of contract name instead of `using` variable](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#id7)[](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#use-of-contract-name-instead-of-using-variable "Link to this heading")
In CVL 1, the only way to refer to a contract in the [scene](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-0) was to first introduce a contract instance variable with a `using` statement, and then use that variable. For example, to access a struct type `S` defined in `PrimaryContract.sol`, you would need to write ([CVL 1](https://github.com/Certora/CVL2Migration/blob/cvl1/certora/spec/ContractNames.spec), [CVL 2](https://github.com/Certora/CVL2Migration/blob/cvl2/certora/spec/ContractNames.spec), [diff](https://github.com/Certora/CVL2Migration/compare/cvl1..cvl2?diff=split#diff-a6a2974b81074e87d755753c2e84ef1b0cb553bfdeb729827959e0c63f0d02d7)):
```
usingPrimaryContractasprimary;
rulestructExample{
primary.Sx;
...
}

```
Copy to clipboard
In CVL 2, you must now use the name of the contract, rather than the instance variable, when referring to user-defined types. The above example would now be written
```
rulestructExample{
PrimaryContract.Sx;
...
}

```
Copy to clipboard
There is no need for a `using` statement in this example.
If you don’t change this, you will an error like the following:
```
Error: Error in spec file (ContractNames.spec:12:19): Contract name primary does not exist in the scene. Make sure you are using a contract name and not a contract instance name.

```
Copy to clipboard
Calling methods on secondary contracts still requires using a contract instance variable:
```
usingSecondaryContractassecondary;
rulemulticontractExample{
...
secondary.balanceOf(0);
...
}

```
Copy to clipboard
Entries in the `methods` block may use either the contract name or an instance variable:
```
usingSecondaryContractassecondary;
methods{
//// both are valid (and the effect is the same):
secondary.balanceOf(address)returns(uint)envfree
SecondaryContract.transfer(address,uint)returns(bool)envfree
}

```
Copy to clipboard
Using the contract name in the methods block currently has the same effect as using an instance variable; this may change in future versions of CVL.
### [Rules must start with `rule`](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#id8)[](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#rules-must-start-with-rule "Link to this heading")
In CVL 1, you could omit the keyword `rule` when writing rules ([CVL 1](https://github.com/Certora/CVL2Migration/blob/cvl1/certora/spec/RuleKeyword.spec), [CVL 2](https://github.com/Certora/CVL2Migration/blob/cvl2/certora/spec/RuleKeyword.spec), [diff](https://github.com/Certora/CVL2Migration/compare/cvl1..cvl2?diff=split#diff-b39a57bffd39f86bc1f9555a487af389f501eab9e66a1c3059a89691319da248)):
```
transferReverts{
...
}

```
Copy to clipboard
In CVL 2, the `rule` keyword is no longer optional:
```
ruletransferReverts{
...
}

```
Copy to clipboard
If you don’t change this, you will receive an error like the following:
```
CRITICAL: [main] ERROR ALWAYS - certora/spec/RuleKeyword.spec:3:1: Syntax error: unexpected token near ID(transferReverts)

```
Copy to clipboard
## [Changes to methods block entries](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#id9)[](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#changes-to-methods-block-entries "Link to this heading")
In addition to the superficial changes listed above, there are some changes to the way that methods block entries can be written (there are also a [few instances](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#cvl2-wildcards) where the meanings of entries has changed). In CVL 1, `methods` block entries often had several different functions and meanings:
  * They were used to indicate targets for summarization
  * They were used to write generic specs that could apply to contracts with missing methods
  * They were used to declare targets `envfree`


The changes described in this section make these different uses more explicit:
  * [Most Solidity types allowed as arguments](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#most-solidity-types-allowed-as-arguments)
  * [Required `internal` or `external` annotation](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#required-internal-or-external-annotation)
  * [`optional` methods block entries](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#optional-methods-block-entries)
  * [Required `calldata`, `memory`, or `storage` annotations for reference types](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#required-calldata-memory-or-storage-annotations-for-reference-types)
  * [Summaries only apply to one contract by default](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#summaries-only-apply-to-one-contract-by-default)
  * [Requirements on `returns`](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#requirements-on-returns)


### [Most Solidity types allowed as arguments](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#id41)[](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#most-solidity-types-allowed-as-arguments "Link to this heading")
CVL 1 had some restrictions on the types of arguments allowed in `methods` block entries. For example, user-defined types (such as enums and structs) were not fully supported.
CVL 2 `methods` block entries may use any Solidity types for arguments and return values, except for [function types](https://docs.soliditylang.org/en/v0.8.17/types.html#function-types) and contract or interface types.
To work around the missing types, CVL 1 allowed users to encode some user-defined types as primitive types in the `methods` block; these workarounds are no longer allowed in CVL 2. For example, consider the following [solidity function](https://TODO/):
```
contractExample{
enumPermission{READ,WRITE};
functionf(Permissionp)internal{...}
}

```
Copy to clipboard
In CVL 1, a methods block entry for `f` would need to declare that it takes a `uint8` argument:
```
methods{
f(uint8permission)=>NONDET
}

```
Copy to clipboard
In CVL 2, the methods block entry should use the same type as the Solidity implementations[^contract-types] ([compare files](https://github.com/Certora/CVL2Migration/compare/cvl1..cvl2?diff=split#diff-5b1b684b999817bab176753b548b9ca548c8e9a1b7ce72d355030a8e03f498d8)), except for function types and contract or interface types:
```
methods{
functionf(Example.Permissionp)internal=>NONDET;
}

```
Copy to clipboard
The method can be called from CVL as follows:
```
ruleexample{
f(Example.Permission.READ);
}

```
Copy to clipboard
Contract functions that take or return contract or interface types should instead use `address` in the `methods` block declaration. For example, if the contract contains the following function:
```
functionlistToken(IERC20token)internal{...}

```
Copy to clipboard
the `methods` block should use `address` for the `token` argument:
```
methods{
functionlistToken(addresstoken)internal;
}

```
Copy to clipboard
Contract functions that take or return function types are not currently supported.
### [Required `internal` or `external` annotation](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#id42)[](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#required-internal-or-external-annotation "Link to this heading")
Every methods block entry must be marked either `internal` or `external`. The annotation must come after the argument list and before the `returns` clause.
If a function is declared `public` in Solidity, then the Solidity compiler creates an internal implementation method, and an external wrapper method that calls the internal implementation. Therefore, you can summarize a `public` method by marking the summarization `internal`.
Warning
The behavior of `internal` vs. `external` summarization for public methods can be confusing, especially because functions called directly from CVL are not summarized. See [Visibility modifiers](https://docs.certora.com/en/latest/docs/cvl/methods.html#methods-visibility).
### [`optional` methods block entries](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#id43)[](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#optional-methods-block-entries "Link to this heading")
In CVL 1, you could write an entry in the methods block for a method that does not exist in the contract; rules that would call the non-existent method were skipped during verification.
This behavior can lead to confusion, because typos or name changes could silently cause a rule to be skipped.
In CVL 2, this behavior is still available, but the methods entry must contain the keyword `optional` somewhere after the `returns` clause and before the summarization (if any).
### [Required `calldata`, `memory`, or `storage` annotations for reference types](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#id44)[](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#required-calldata-memory-or-storage-annotations-for-reference-types "Link to this heading")
In CVL 2, methods block entries for internal functions must contain either `calldata`, `memory`, or `storage` annotations for all arguments with reference types (such as arrays).
For methods block entries of external functions the location annotation must be omitted unless it’s the `storage` annotation on an external library function, in which case it is required (the reasoning here is to have the information required in order to correctly calculate a function’s sighash).
### [Summaries only apply to one contract by default](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#id45)[](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#summaries-only-apply-to-one-contract-by-default "Link to this heading")
In CVL 1, a summary in the `methods` block applied to all methods with the given signature.
In CVL 2, summaries only apply to a single contract, unless the old behavior is explicitly requested by using `_` as the receiver. If no contract is specified, the default is `currentContract`.
Note
The receiver contract must be the contract where the method is defined. If a contract inherits a method defined in a supercontract, the receiver must be the supercontract, rather than the inheriting contract.
Entries that use `_` as the receiver are called [wildcard entries](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-wildcard), summaries that do not are called [exact entries](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-exact).
Consider the following example:
```
usingCasc;
methods{
functionf(uint)internal=>NONDET;
functionc.g(uint)internal=>ALWAYS(4);
functionh(uint)internal=>ALWAYS(1);
function_.h(uint)internal=>NONDET;
}

```
Copy to clipboard
In this example, the internal function `currentContract.f` has a `NONDET` summary, `c.g` has an `ALWAYS` summary, a call to `currentContact.h` has an `ALWAYS` summary and a call to `h(uint)` on any other contract will use a `NONDET` summary.
Summaries for specific contract methods (including the default `currentContract`) always override wildcard summaries.
Wildcard entries cannot be declared `optional` or `envfree`, since these annotations only make sense for specific contract methods.
Warning
The meaning of your summarizations will change from CVL 1 to CVL 2. In CVL 2, any entry without an `_` will only apply to a single contract!
### [Requirements on `returns`](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#id46)[](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#requirements-on-returns "Link to this heading")
In CVL 1, the `returns` clause on methods block entries was optional. CVL 2 has stricter requirements on the declared return types.
Entries that apply to specific contracts (i.e. those that don’t use the `_.f` [syntax](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#cvl2-wildcards)) must include a `returns` clause if the contract method returns a value. A specific-contract entry may only omit the `returns` clause if the contract method does not return a value.
The Prover will report an error if the contract method’s return type differs from the type declared in the `methods` block entry.
Wildcard entries must not declare return types, because they may apply to multiple methods that return different types. If a wildcard entry is summarized with a ghost or function summary, the summary must include an `expect` clause; see [Expression summaries](https://docs.certora.com/en/latest/docs/cvl/methods.html#expression-summary) for more details.
## [Changes to integer types](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#id16)[](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#changes-to-integer-types "Link to this heading")
In CVL 1, the rules for casting between integer types were complex; CVL 2 simplifies them.
The general rule of thumb is that you should use `mathint` whenever possible; only use `uint` or `int` types for data that will be passed as input to contract functions.
It is now impossible for CVL math expressions to cause overflow - all integer operations are exact. The remainder of this section describes the changes in detail.
### [Mathematical operations return `mathint`](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#id17)[](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#mathematical-operations-return-mathint "Link to this heading")
In CVL 2, the results of all arithmetic operators have type `mathint`, regardless of the input types. Arithmetic operators include `+`, `*`, `-`, `/`, `^`, and `%`, but not bitwise operators like `<<`, `xor`, and `|` (changes to bitwise operators are described [below](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#cvl2-bitwise)).
The primary impact of this change is that you may need to declare more of your variables as `mathint` instead of `uint`. If you are passing the results of arithmetic operations to contract functions, you will need to be more explicit about the overflow behavior by using the [new casting operators](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#cvl2-casting).
### [Implicit and explicit casting](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#id18)[](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#implicit-and-explicit-casting "Link to this heading")
If every number that can be represented by one type can also be represented by another type, then we say that the first type is a _subtype_ of the second type.
For example, a `uint8` variable could have any value between `0` and `2^8-1`, and all of these values can be stored in a `uint16` variable, so `uint8` is a subtype of `uint16`. An `int16` can also store any value between `0` and `2^8-1`, so `uint8` is also a subtype of `int16`.
All integer types are subtypes of `mathint`, since any integer can be represented by a `mathint`.
In CVL 1, the rules for converting between supertypes and subtypes were complicated; they depended not only on the types involved, but on the context in which the conversion happened. CVL 2 simplifies these rules and improves the clarity and predictability of casts.
In CVL 2, you can always use a subtype whenever the supertype is accepted. For example, you can always use a `uint8` where an `int16` is expected. We say that the subtype can be “implicitly cast” to the supertype.
In order to convert from a supertype to a subtype, you must use an explicit cast. In CVL 1, only a few casting operators (such as `to_uint256`) were supported.
CVL 2 replaces these casting operators with two new casting operators: _assert casts_ such as `assert_uint8(x)` or `assert_int256(x)`, and _require casts_ such as `require_uint8(x)` or `require_int256(x)`. Each of these casts checks that the value is in range; the `assert` cast will report a counterexample if the value is out of range, while the `require` cast will ignore counterexamples where the cast value is out of range.
Warning
As with normal `require` statements, require casts can cause vacuity and should be used with care.
CVL 2 supports assert and require casts on all numeric types.
Casts from `address` or `bytes1`…`bytes32` to integer types are not supported (see [Support for bytes1…bytes32](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#bytesn-support) regarding casting in the other direction, and [Casting enums to integer types](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#enum-casting) for information on casting enums).
`require` and `assert` casts are not allowed anywhere inside of a [quantified statement](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-quantifier). You can work around this limitation by adding a second variable. For example, the following axiom is invalid because `x+1` is not a `uint`:
```
ghostmapping(uint=>uint)a{
axiomforalluintx.a[x+1]==0
}

```
Copy to clipboard
However, it can be replaced with the following:
```
ghostmapping(uint=>uint)a{
axiomforalluintx.foralluinty.(to_mathint(y)==x+1)=>a[y]==0
}

```
Copy to clipboard
### [Casting enums to integer types](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#id19)[](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#casting-enums-to-integer-types "Link to this heading")
In CVL2 enums are not directly comparable to the corresponding integer type (`uint8`). Instead one must use one of the new cast operators. For example
```
uint8x=MyContract.MyEnum.VAL;// will fail typechecking
uint8x=assert_uint8(MyContract.MyEnum.VAL);// good
mathintx=to_mathint(MyContract.MyEnum.VAL);// good

```
Copy to clipboard
Casting integer types to an enum is not supported.
### [Casting addresses to bytes32](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#id20)[](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#casting-addresses-to-bytes32 "Link to this heading")
CVL2 supports casting from the `address` type to the `bytes32` type. For example:
```
addressa=0xa44f5d3d624DfD660ecc11FF777587AD0a19606d;
bytes32b=to_bytes32(a);

```
Copy to clipboard
The cast from `address` to `bytes32` behaves equivalently to the Solidity code:
```
addressa=0xa44f5d3d624DfD660ecc11FF777587AD0a19606d;
bytes32b=bytes32(uint256(uint160(a)));

```
Copy to clipboard
Among other things, this behavior means that the resulting `bytes32` value is right-aligned and zero-padded to the left.
CVL2 also supports casting from the `bytes32` type to the `address` type using either the `require_address()` or `assert_address()` cast functions.
```
bytes32b=to_bytes32(0xa44f5d3d624DfD660ecc11FF777587AD0a19606d);
addressa=assert_address(b);

```
Copy to clipboard
Note that `require_address()` will silently allow a cast to continue when the `bytes32` variable contains a value that lies in the range `2^160 < var < 2^256`. The `assert_address()` cast function will fail when the `bytes32` variable contains a value in that same range.
```
bytes32b=to_bytes32(0xa44f5d3d624DfD660ecc11FF777587AD0a19606d0e);// Note this contains one extra byte
addressa=require_address(b);// Silently does the cast.

```
Copy to clipboard
While when using `assert_address`:
```
bytes32b=to_bytes32(0xa44f5d3d624DfD660ecc11FF777587AD0a19606d0e);// Note this contains one extra byte
addressa=assert_address(b);// This will fail.

```
Copy to clipboard
Casting from `bytes32` to `address` behaves equivalently to the Solidity code:
```
bytes32b=bytes32(0xa44f5d3d624DfD660ecc11FF777587AD0a19606d);
addressa=address(uint160(uint256(b)));

```
Copy to clipboard
### [Modulo operator `%` always returns non-negative values](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#id21)[](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#modulo-operator-always-returns-non-negative-values "Link to this heading")
The modulo operator `%` follows the semantics of Solidity’s unsigned modulo and always returns non-negative values, regardless of the signs of its operands.
### [Support for `bytes1`…`bytes32`](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#id22)[](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#support-for-bytes1-bytes32 "Link to this heading")
CVL 2 supports the types `bytes1`, `bytes2`, …, `bytes32`, as in Solidity. Number literals must be explicitly cast to these types using `to_bytesN`; for example:
```
bytes32x=to_bytes32(0);

```
Copy to clipboard
Unlike Solidity, `bytes1`…`bytes32` literals do not need to be written in hex or padded to the correct length.
The only conversion between integer types and these types is from `uint<i*8>` to `bytes<i>` (i.e. unsigned integers with the same bitwidth as the target `bytes<i>` type); For example:
```
uint24u;
bytes3x=to_bytes3(u);// This is OK
bytes4y=to_bytes4(u);// This will fail

```
Copy to clipboard
### [Changes for bitwise operations](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#id23)[](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#changes-for-bitwise-operations "Link to this heading")
In CVL1, the exact details for bitwise operations (such as `&`, `|`, and `<<`) were not completely specified, especially for negative integers.
In CVL 2, all bitwise operations (`&`, `|`, `~`, `>>`, `>>>`, `<<`, and `xor`) on integer types first convert to a 256 bit word, then perform the operations on the full 256-bit word, then convert back to the expected type. Signed integer types use twos-complement encoding.
The two right-shifts differ in how they treat signed integers. `>>` is an arithmetic shift; it preserves the sign bit. `>>>` is a logical shift; it pads the shifted word with zero.
Bitwise operations cannot be performed on `mathint` values.
Note
By default, bitwise operators are [overapproximated](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-overapproximation) (in both CVL 1 and CVL 2), so you may see counterexamples that incorrectly compute the results of bitwise operations. The approximations are still [sound](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-sound): the Prover will not report a rule as verified if the original code does not satisfy the rule.
The [precise_bitwise_ops](https://docs.certora.com/en/latest/docs/prover/cli/options.html#precise-bitwise-ops) flag makes the Prover’s reasoning about bitwise operations more precise, but this flag is experimental in CVL 2.
## [Changes to the fallback function](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#id24)[](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#changes-to-the-fallback-function "Link to this heading")
In CVL 1, you could determine whether a `method` object was the fallback function by comparing its selector to `certorafallback().selector`:
```
assertf.selector==certorafallback().selector,
"f must be the fallback";

```
Copy to clipboard
In CVL 2, `certorafallback()` is no longer valid. Instead, you can use the new field `f.isFallback` to detect the fallback method:
```
assertf.isFallback,
"f must be the fallback";

```
Copy to clipboard
## [Removed features](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#id25)[](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#removed-features "Link to this heading")
As we transit to CVL 2, we have removed several language features that are no longer used.
We have removed these features because we think they are no longer used and no longer useful. If you find that you do need one of these features, contact Certora support.
### [Methods entries for sighashes](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#id26)[](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#methods-entries-for-sighashes "Link to this heading")
In CVL 1, you could write a sighash instead of a method identifier in the `methods` block. This feature is no longer supported. You will need to have the name and argument types of the called method in order to provide an entry.
### [`invoke`, `sinvoke`, and `call`](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#id27)[](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#invoke-sinvoke-and-call "Link to this heading")
Older versions of CVL had special syntax for calling contract and CVL functions:
  * `invoke f(args);` should be replaced with `f@withrevert(args);`.
  * `sinvoke f(args);` should be replaced with `f(args);`.
  * `call f(args)` should be replaced with `f(args)`.


### [`static_assert` and `static_require`](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#id28)[](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#static-assert-and-static-require "Link to this heading")
These deprecated aliases for `assert` and `require` are being removed; replace them with `assert` and `require` respectively.
### [`invoke_fallback` and `certorafallback()`](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#id29)[](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#invoke-fallback-and-certorafallback "Link to this heading")
The `invoke_fallback` syntax is no longer supported; there is no longer a way to directly invoke the fallback method. You can work around this limitation by writing a parametric rule and filtering on `f.isFallback`. See [Changes to the fallback function](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#cvl2-fallback-changes).
### [`invoke_whole`](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#id30)[](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#invoke-whole "Link to this heading")
The `invoke_whole` keyword is no longer supported.
### [Havocing local variables](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#id31)[](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#havocing-local-variables "Link to this heading")
In CVL 1, you could write the following:
```
calldataargargs;enve;
f(e,args);
havocargs;
g(e,args);

```
Copy to clipboard
In CVL 2, you can only `havoc` ghost variables and ghost functions. Instead of havocing a local variable, replace the havoced variable with a new variable. For example, you should replace the above with
```
calldataargargs;enve;
f(e,args);
calldataargargs2;
g(e,args2);

```
Copy to clipboard
### [Destructuring syntax for struct returns](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#id32)[](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#destructuring-syntax-for-struct-returns "Link to this heading")
In CVL 1, if a contract function returned a struct, you could use a destructuring syntax to get the return value in your spec. For example, consider the following contract:
```
contractExample{
structS{
uintfirstField;
uintsecondField;
boolthirdField;
}
functionf()returns(S){...}
functiong()returns(uint,uint){...}
}

```
Copy to clipboard
To access the return value of `f` in CVL 1, you could write the following:
```
uintx;uinty;boolz;
x,y,z=f();

```
Copy to clipboard
This syntax is no longer supported. Instead, you should declare a variable with the struct type:
```
Example.Sresult=f();
uintx=result.firstField;

```
Copy to clipboard
Destructuring assignments are still allowed for functions that return multiple values; the following is valid:
```
uintx;uinty;
x,y=g();

```
Copy to clipboard
### [`bytes[]` and `string[]`](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#id33)[](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#bytes-and-string "Link to this heading")
In CVL 1, you could declare variables of type `string[]` and `bytes[]`. You can no longer use these types in CVL.
You can still declare contract methods that use these types in the `methods` block. However, you can only call methods that take one of these types as an argument by passing a `calldataarg` variable, and you cannot access the return value of a method that returns one of these types.
### [`pragma`](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#id34)[](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#pragma "Link to this heading")
CVL 1 had a `pragma` command for specifying the CVL version, but this feature was not used and has been removed in CVL 2.
### [`events`](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#id35)[](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#events "Link to this heading")
CVL 1 had syntax for an `events` block, but it did nothing and has been removed.
## [Changes to the Command Line Interface (CLI)](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#id36)[](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#changes-to-the-command-line-interface-cli "Link to this heading")
As part of the transition to CVL 2 changes were made to enhanced clarity, uniformity, and readability on the Command-Line Interface (CLI). The complete CLI specification can be found [here](https://docs.certora.com/en/latest/docs/prover/cli/options.html)
Note
The changes will take effect starting v4.3.1 of `certora-cli`.
Note
To opt-out of the new CLI, one can set an environment variable `CERTORA_OLD_API` to `1`, e.g.: `export CERTORA_OLD_API=1`. **The old CLI will not be available in versions released after August 31st, 2023**
### [Flags Renaming](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#id37)[](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#flags-renaming "Link to this heading")
In CVL 2 some flags were renamed:
  1. flags with names that are generic or wrong
  2. flags that do not match their corresponding key in the `conf` file
  3. flags that do not follow the snake case format


This is the list of the flags that were renamed:
CVL 1 | CVL 2  
---|---  
`--settings` | `--prover_args`  
`--path` | `--solc_allow_path`  
`--optimize` | `--solc_optimize`  
`--optimize_map` | `--solc_optimize_map`  
`--structLink` | `--struct_link`  
`--javaArgs` | `--java_args`  
### [`Prover Args`](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#id38)[](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#prover-args "Link to this heading")
`Prover args` are CLI flags that are sent to the Prover. `Prover args` can be set in one of two ways:
  1. Using specific CLI flags (e.g. `--loop_iter`)
  2. As parameters to the `--prover_args` (`--settings` in CVL 1)


Unlike CVL 1, if a `prover arg` is set using a specific CLI flag it cannot be set using `--prover_args`. In addition, the value commas and equal signs separators that were used in `--settings` were replaced with white-spaces in `--prover_args`.
Example:
Consider this call to `certoraRun` using CVL 1 syntax
```
certoraRunCompound.sol\
--verifyCompound:Compound.spec\
--solcsolc8.13\
--settings-smt_bitVectorTheory=true,-smt_hashingScheme=plainInjectivity,-assumeUnwindCond

```
Copy to clipboard
In order to convert this call to CVL 2 we:
  1. renamed `--settings` to `--prover_args`
  2. replaced `-assumeUnwindCond` with the flag `--optimistic_loop`
  3. removed the comma and equal sign separators


```
certoraRunCompound.sol\
--verifyCompound:Compound.spec\
--solcsolc8.13\
--optimistic_loop\
--prover_args'-smt_bitVectorTheory true -smt_hashingScheme plainInjectivity'

```
Copy to clipboard
### [`Solidity Compiler Args`](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#id39)[](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#solidity-compiler-args "Link to this heading")
The `Solidity Compiler Args` are CLI flags that are sent to the Solidity compiler. The behavior of the `Solidity Args` is similar to `Prover Args`. The flag `--solc_args` can only be used if there is no CLI flag that sets the Solidity flag and the value of `--solc_args` is a string that is sent as is to the Solidity compiler.
Example:
Consider this call to `certoraRun` using CVL 1 syntax
```
certoraRunCompound.sol\
--verifyCompound:Compound.spec\
--solcsolc8.13\
--solc_args"['--optimize', '--optimize-runs', '200', '--experimental-via-ir']"

```
Copy to clipboard
In CVL 2 calling optimize is using `--solc_optimize`
```
certoraRunCompound.sol\
--verifyCompound:Compound.spec\
--solcsolc8.13\
--solc_optimize200\
--solc_args"--experimental-via-ir"

```
Copy to clipboard
### [Enhanced server support](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#id40)[](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#enhanced-server-support "Link to this heading")
In CVL 1, two server platforms were supported:
  1. `staging` was set using the flag `--staging [Branch/hotfix]`
  2. `production` was set using the flag `--cloud [Branch/hotfix]`


In CVL 2 the flag `--server` was added to replace `--staging` `--cloud` and to allow adding additional server platforms. `--server` gets as a parameter the platform name. `--prover_version` is a new flag in CVL 2 For setting the Branch/hot-fix
[ Previous](https://docs.certora.com/en/latest/docs/cvl/foundry-integration.html "Foundry Integration \(Alpha\)") [Next ](https://docs.certora.com/en/latest/docs/cvl/cvl2/migration.html "CVL2 Migration Guide")
© Copyright 2025, Certora, Inc.
Built with [Sphinx](https://www.sphinx-doc.org/) using a [theme](https://github.com/readthedocs/sphinx_rtd_theme) provided by [Read the Docs](https://readthedocs.org). 
