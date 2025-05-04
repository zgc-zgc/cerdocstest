[ Certora Prover Documentation ![Logo](https://docs.certora.com/en/latest/_static/Certora_Logo_Black.svg) ](https://docs.certora.com/en/latest/index.html)
Contents
  * [Certora User’s Guide](https://docs.certora.com/en/latest/docs/user-guide/index.html)
  * [The Certora Verification Language](https://docs.certora.com/en/latest/docs/cvl/index.html)
    * [Specification Files](https://docs.certora.com/en/latest/docs/cvl/overview.html)
    * [Basic Syntax](https://docs.certora.com/en/latest/docs/cvl/basics.html)
    * [Types](https://docs.certora.com/en/latest/docs/cvl/types.html)
      * [Syntax](https://docs.certora.com/en/latest/docs/cvl/types.html#syntax)
      * [Solidity Types](https://docs.certora.com/en/latest/docs/cvl/types.html#solidity-types)
        * [Integer types](https://docs.certora.com/en/latest/docs/cvl/types.html#integer-types)
        * [Array access](https://docs.certora.com/en/latest/docs/cvl/types.html#array-access)
        * [User-defined types](https://docs.certora.com/en/latest/docs/cvl/types.html#user-defined-types)
      * [Additional CVL types](https://docs.certora.com/en/latest/docs/cvl/types.html#additional-cvl-types)
        * [The `mathint` type](https://docs.certora.com/en/latest/docs/cvl/types.html#the-mathint-type)
        * [The `env` type](https://docs.certora.com/en/latest/docs/cvl/types.html#the-env-type)
        * [The `method` and `calldataarg` types](https://docs.certora.com/en/latest/docs/cvl/types.html#the-method-and-calldataarg-types)
        * [The `storage` type](https://docs.certora.com/en/latest/docs/cvl/types.html#the-storage-type)
        * [Uninterpreted sorts](https://docs.certora.com/en/latest/docs/cvl/types.html#uninterpreted-sorts)
      * [Conversions between CVL and Solidity types](https://docs.certora.com/en/latest/docs/cvl/types.html#conversions-between-cvl-and-solidity-types)
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
  * Types
  * [ View page source](https://docs.certora.com/en/latest/_sources/docs/cvl/types.md.txt)


# [Types](https://docs.certora.com/en/latest/docs/cvl/types.html#id6)[](https://docs.certora.com/en/latest/docs/cvl/types.html#types "Link to this heading")
Like Solidity, CVL is a statically typed language. There is overlap between the types supported by Solidity and the types supported by CVL, but CVL has some additional types and is also missing support for some Solidity types.
The additional CVL types are:
  * [The mathint type](https://docs.certora.com/en/latest/docs/cvl/types.html#mathint) is an arbitrary precision integer that cannot overflow
  * [The method and calldataarg types](https://docs.certora.com/en/latest/docs/cvl/types.html#method-type) are used to represent arbitrary methods and arguments of the contract under verification
  * [The storage type](https://docs.certora.com/en/latest/docs/cvl/types.html#storage-type) is used to represent a snapshot of the entire EVM storage
  * [The env type](https://docs.certora.com/en/latest/docs/cvl/types.html#env) is used to represent the Solidity global variables `msg`, `block`, and `tx`
  * [Uninterpreted sorts](https://docs.certora.com/en/latest/docs/cvl/types.html#sort) are used to represent unknown types


Contents
  * [Types](https://docs.certora.com/en/latest/docs/cvl/types.html#types)
    * [Syntax](https://docs.certora.com/en/latest/docs/cvl/types.html#syntax)
    * [Solidity Types](https://docs.certora.com/en/latest/docs/cvl/types.html#solidity-types)
      * [Integer types](https://docs.certora.com/en/latest/docs/cvl/types.html#integer-types)
      * [Array access](https://docs.certora.com/en/latest/docs/cvl/types.html#array-access)
      * [User-defined types](https://docs.certora.com/en/latest/docs/cvl/types.html#user-defined-types)
    * [Additional CVL types](https://docs.certora.com/en/latest/docs/cvl/types.html#additional-cvl-types)
      * [The `mathint` type](https://docs.certora.com/en/latest/docs/cvl/types.html#the-mathint-type)
      * [The `env` type](https://docs.certora.com/en/latest/docs/cvl/types.html#the-env-type)
      * [The `method` and `calldataarg` types](https://docs.certora.com/en/latest/docs/cvl/types.html#the-method-and-calldataarg-types)
      * [The `storage` type](https://docs.certora.com/en/latest/docs/cvl/types.html#the-storage-type)
      * [Uninterpreted sorts](https://docs.certora.com/en/latest/docs/cvl/types.html#uninterpreted-sorts)
    * [Conversions between CVL and Solidity types](https://docs.certora.com/en/latest/docs/cvl/types.html#conversions-between-cvl-and-solidity-types)


## [Syntax](https://docs.certora.com/en/latest/docs/cvl/types.html#id7)[](https://docs.certora.com/en/latest/docs/cvl/types.html#syntax "Link to this heading")
The syntax for types in CVL is given by the following [EBNF grammar](https://docs.certora.com/en/latest/docs/cvl/overview.html#ebnf-syntax):
```
basic_type ::= "int*" | "uint*" | "address" | "bool"
       | "string" | "bytes*"
       | basic_type "[" [ number ] "]"
       | id "." id
evm_type ::= basic_type
      | "(" evm_type { "," evm_type } ")"
      | evm_type "[" [ number ] "]"
cvl_type ::= basic_type
      | "mathint" | "calldataarg" | "storage" | "env" | "method"
      | id

```
Copy to clipboard
See [Basic Syntax](https://docs.certora.com/en/latest/docs/cvl/basics.html) for the `id` and `number` productions.
## [Solidity Types](https://docs.certora.com/en/latest/docs/cvl/types.html#id8)[](https://docs.certora.com/en/latest/docs/cvl/types.html#solidity-types "Link to this heading")
You can declare variables in CVL of any of the following [solidity types](https://docs.soliditylang.org/en/v0.8.11/types.html):
  * `int`, `uint`, and the sized variants such as `uint256` and `int8`
  * `bool`, `address`, and the sized `bytes` variants (`bytes1` through `bytes32`)
  * `string` and `bytes`
  * [Single-dimensional arrays](https://docs.certora.com/en/latest/docs/cvl/types.html#arrays) (both statically- and dynamically-sized)
  * [Enum types, struct types, and type aliases](https://docs.certora.com/en/latest/docs/cvl/types.html#user-types) that are defined in Solidity contracts.


The following are not directly supported in CVL, although you can interact with contracts that use them (see [Conversions between CVL and Solidity types](https://docs.certora.com/en/latest/docs/cvl/types.html#type-conversions)):
  * Function types
  * Multi-dimensional arrays
  * Mappings


### [Integer types](https://docs.certora.com/en/latest/docs/cvl/types.html#id9)[](https://docs.certora.com/en/latest/docs/cvl/types.html#integer-types "Link to this heading")
CVL integer types are mostly identical to Solidity integer types. See [Basic operations](https://docs.certora.com/en/latest/docs/cvl/expr.html#math-ops) for details.
### [Array access](https://docs.certora.com/en/latest/docs/cvl/types.html#id10)[](https://docs.certora.com/en/latest/docs/cvl/types.html#array-access "Link to this heading")
Array accesses in CVL behave slightly differently from Solidity accesses. In Solidity, an out-of-bounds array access will result in an exception, causing the transaction to revert.
By contrast, out-of-bounds array accesses in CVL are treated as undefined values: if `i > a.length` then the Prover considers every possible value for `a[i]` when constructing counterexamples.
CVL arrays also have the following limitations:
  * Only single dimensional arrays are supported
  * The `push` and `pop` methods are not supported. You can use [harnessing](https://docs.certora.com/en/latest/docs/prover/approx/harnessing.html) to work around these limitations.


### [User-defined types](https://docs.certora.com/en/latest/docs/cvl/types.html#id11)[](https://docs.certora.com/en/latest/docs/cvl/types.html#user-defined-types "Link to this heading")
Specifications can use structs, enums, or user-defined value types that are defined in Solidity contracts.
Struct types have the following limitations:
  * Assignment to struct fields is unsupported. You can achieve the same effect using a [require](https://docs.certora.com/en/latest/docs/cvl/statements.html#require) statement. For example, instead of `s.f = x;` you can write `require s.f == x;`. However, be aware that `require` statements can introduce [vacuity](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-vacuity) if there are multiple conflicting constraints.


All user-defined type names (structs, enums, and user-defined values) must be explicitly qualified by the contract name that contains them.
  * For types defined within a contract, the named contract must be the contract containing the type definition. Note that if a contract inherits a type from a supertype, the contract that actually contains the type must be named, not the inheriting contract.
  * For types defined at the file level, the named contract can be any contract in the [scene](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-0) from which the type is visible.


Warning
If you do not qualify the type name with a contract name, the type name will be misinterpreted as a [sort](https://docs.certora.com/en/latest/docs/cvl/types.html#sort).
For example, consider the files `parent.sol` and `child.sol`, defined as follows:
parent.sol[](https://docs.certora.com/en/latest/docs/cvl/types.html#id3 "Link to this code")
```
typeParentFileTypeisuint64;
contractParent{
enumParentContractType{member1,member2}
}

```
Copy to clipboard
child.sol[](https://docs.certora.com/en/latest/docs/cvl/types.html#id4 "Link to this code")
```
import'parent.sol';
typeChildFileTypeisbool;
contractChildisParent{
typealiasChildContractTypeisuint128;
}

```
Copy to clipboard
Given these definitions, types can be named as follows:
child.spec[](https://docs.certora.com/en/latest/docs/cvl/types.html#id5 "Link to this code")
```
// valid types
Parent.ParentFileTypevalid1;
Child.ChildFileTypevalid2;
Parent.ParentContractTypevalid3;
// invalid types
Child.ParentContractTypeinvalid1;// user-defined types are not inherited
Child.ParentFileTypeinvalid2;// user-defined types are not inherited
Parent.ChildFileTypeinvalid3;// ChildFileType is not visible in Parent

```
Copy to clipboard
## [Additional CVL types](https://docs.certora.com/en/latest/docs/cvl/types.html#id12)[](https://docs.certora.com/en/latest/docs/cvl/types.html#additional-cvl-types "Link to this heading")
### [The `mathint` type](https://docs.certora.com/en/latest/docs/cvl/types.html#id13)[](https://docs.certora.com/en/latest/docs/cvl/types.html#the-mathint-type "Link to this heading")
Arithmetic overflow and underflow are difficult to reason about and often lead to bugs. To avoid this complexity, CVL provides the `mathint` type that can represent an integer of any size; operations on `mathint`s can never overflow or underflow.
See [Basic operations](https://docs.certora.com/en/latest/docs/cvl/expr.html#math-ops) for details on mathematical operations and casting between `mathint` and Solidity integer types.
### [The `env` type](https://docs.certora.com/en/latest/docs/cvl/types.html#id14)[](https://docs.certora.com/en/latest/docs/cvl/types.html#the-env-type "Link to this heading")
Rules often reason about the effects of multiple transactions. In different transactions, the global [Solidity variables](https://docs.soliditylang.org/en/v0.8.11/units-and-global-variables.html#special-variables-and-functions) (such as `msg.sender` or `block.timestamp`) may have different values.
To support reasoning about multiple transactions, CVL groups some of the solidity global variables into an “environment”: an object of the special type `env`. Environments must be passed as the first argument of a call from CVL into a contract function (unless the contract function is declared [envfree](https://docs.certora.com/en/latest/docs/cvl/methods.html#envfree)).
For example, to call a Solidity function `deposit(uint amount)`, a spec must explicitly pass in an additional environment argument:
```
rulecheck_deposit(){
enve;
uintamount;
deposit(e,amount);// increases e.msg.sender's balance by `amount`
}

```
Copy to clipboard
The value of the Solidity global variables can be extracted from the `env` object using a field-like syntax. The following fields are available on an environment `e`:
  * `e.msg.sender` - address of the sender of the message
  * `e.msg.value` - number of Wei sent with the message
  * `e.block.number` - current block number
  * `e.block.timestamp` - current block’s time stamp
  * `e.block.basefee` - current block’s base fee
  * `e.block.coinbase` - current block’s coinbase
  * `e.block.difficulty` - current block’s difficulty
  * `e.block.gaslimit` - current block’s gas limit
  * `e.tx.origin` - original message sender


The remaining solidity global variables are not accessible from CVL.
### [The `method` and `calldataarg` types](https://docs.certora.com/en/latest/docs/cvl/types.html#id15)[](https://docs.certora.com/en/latest/docs/cvl/types.html#the-method-and-calldataarg-types "Link to this heading")
Changed in version 5.0: Formerly, parametric method calls would only call methods of `currentContract`; now they call methods of all contracts. This version also introduced the `f.contract` field.
An important feature of CVL is the ability to reason about the effects of an arbitrary method called with arbitrary arguments. To support this, CVL provides the `method` type to represent an arbitrary method, and the `calldataarg` type to represent an arbitrary set of arguments.
For example, the following rule checks that _no method_ can decrease the user’s balance:
```
rulebalance_increasing(){
addressuser;
uintbalance_before=balance(user);
methodf;
enve;
calldataargargs;
f(e,args);
uintbalance_after=balance(user);
assertbalance_after>=balance_before,"balance must be increasing";
}

```
Copy to clipboard
Since `f`, `e`, and `args` are not given values, the Prover will consider every possible assignment. This means that when evaluating the call to `f(e,args)`, the Prover will check the rule on every method of every contract on the [scene](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-0), with every possible set of method arguments.
See [Parametric rules](https://docs.certora.com/en/latest/docs/cvl/rules.html#parametric-rules) for more information about how rules that declare method variables are verified.
Variables of type `method` can only be declared as an argument to the rule or directly in the body of a rule. They may not be nested inside of `if` statements or declared in CVL functions. They may be passed as arguments to CVL functions.
Properties of methods can be extracted from `method` variables using a field-like syntax. The following fields are available on a method `m`:
  * `m.selector` - the ABI signature of the method
  * `m.isPure` - true when m is declared with the pure attribute
  * `m.isView` - true when m is declared with the view attribute
  * `m.isFallback` - true when `m` is the fallback function
  * `m.numberOfArguments` - the number of arguments to method m
  * `m.contract` - the receiver contract for the method


There is no way to examine the contents of a `calldataarg` variable, because the type of its contents vary depending on which method the Prover is checking. The only thing you can do with it is pass it as an argument to a contract method call. It is possible to work around this limitation; see [Partially Parametric Rules](https://docs.certora.com/en/latest/docs/user-guide/patterns/partial-apply.html#partially-parametric-rules) for further details.
### [The `storage` type](https://docs.certora.com/en/latest/docs/cvl/types.html#id16)[](https://docs.certora.com/en/latest/docs/cvl/types.html#the-storage-type "Link to this heading")
The Certora Prover can compare different hypothetical transactions starting from the same state and compare their results. For example, checking a property like “if you stake more, you earn more” requires comparing the earnings after two possible transactions starting in the same initial state: one where you stake less, and one where you stake more.
Properties that compare the results of different hypothetical executions are sometimes called hyperproperties.
CVL supports this kind of specification using the special `storage` type. A variable of type `storage` represents a snapshot of the EVM storage and the state of [ghosts](https://docs.certora.com/en/latest/docs/cvl/ghosts.html#ghost-functions) at a given point in time.
The EVM storage can be reset to a saved storage value `s` by appending `at s` to the end of a function call. For example, the following rule checks that “if you stake more, you earn more”:
```
rulebigger_stake_more_earnings(){
storageinitial=lastStorage;
enve;
uintless;uintmore;
requireless<more;
// stake less
stake(e,less)atinitial;
earnings_less=earnings(e);
// stake more
stake(e,more)atinitial;
earnings_more=earnings(e);
assertearnings_less<earnings_more,"if you stake more, you earn more";
}

```
Copy to clipboard
The `lastStorage` variable contains the state of the EVM after the most recent contract function call.
Variables of `storage` type can also be compared for equality, allowing simple rules that check the equivalence of different functions. See [Comparing storage](https://docs.certora.com/en/latest/docs/cvl/expr.html#storage-comparison) for details.
### [Uninterpreted sorts](https://docs.certora.com/en/latest/docs/cvl/types.html#id17)[](https://docs.certora.com/en/latest/docs/cvl/types.html#uninterpreted-sorts "Link to this heading")
## [Conversions between CVL and Solidity types](https://docs.certora.com/en/latest/docs/cvl/types.html#id18)[](https://docs.certora.com/en/latest/docs/cvl/types.html#conversions-between-cvl-and-solidity-types "Link to this heading")
When a specification calls a contract function, the Prover must convert the arguments from their CVL types to the corresponding Solidity types, and must convert the return values from Solidity back to CVL. The Prover must also apply these conversions when inlining [hooks](https://docs.certora.com/en/latest/docs/cvl/hooks.html#hooks) and [function summaries](https://docs.certora.com/en/latest/docs/cvl/methods.html#expression-summary).
There are restrictions on what types can be converted from CVL to Solidity and vice-versa. In general, if a contract uses a type that is not convertible, you can still interact with it, but you cannot access the corresponding values. For example, if a contract function returns a type that isn’t convertible to CVL, you can call the function from CVL but you cannot access its return type. Similarly, if the function accepts an argument of a type that is not representable in CVL, you can still call the function from CVL, but only by providing it a generic [ `calldataarg` argument](https://docs.certora.com/en/latest/docs/cvl/types.html#calldataarg).
The following restrictions apply when converting between CVL types and Solidity types:
  * The type must be a [valid CVL type](https://docs.certora.com/en/latest/docs/cvl/types.html#solidity-types) (except for contract or interface types, which are represented by `address`).
  * Reference types (arrays and structs) can only be passed to Solidity functions that expect `calldata` or `memory` arguments; there is no way to pass `storage` arrays.
  * Arrays returned from Solidity can only be converted to CVL if their elements have [value types](https://docs.soliditylang.org/en/v0.8.11/types.html#value-types) that are representable in CVL.


There are additional restrictions on the types for arguments and return values for internal function summaries; see [Expression summaries](https://docs.certora.com/en/latest/docs/cvl/methods.html#expression-summary).
[ Previous](https://docs.certora.com/en/latest/docs/cvl/basics.html "Basic Syntax") [Next ](https://docs.certora.com/en/latest/docs/cvl/expr.html "Expressions")
© Copyright 2025, Certora, Inc.
Built with [Sphinx](https://www.sphinx-doc.org/) using a [theme](https://github.com/readthedocs/sphinx_rtd_theme) provided by [Read the Docs](https://readthedocs.org). 
