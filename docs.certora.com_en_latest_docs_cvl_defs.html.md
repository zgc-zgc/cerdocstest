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
      * [Basic Usage](https://docs.certora.com/en/latest/docs/cvl/defs.html#basic-usage)
        * [Example:](https://docs.certora.com/en/latest/docs/cvl/defs.html#example)
      * [Advanced Functionality](https://docs.certora.com/en/latest/docs/cvl/defs.html#advanced-functionality)
        * [Include an Application of Another Definition](https://docs.certora.com/en/latest/docs/cvl/defs.html#include-an-application-of-another-definition)
        * [Type Error circular dependency](https://docs.certora.com/en/latest/docs/cvl/defs.html#type-error-circular-dependency)
        * [Reference Ghost Functions](https://docs.certora.com/en/latest/docs/cvl/defs.html#reference-ghost-functions)
      * [Filter Example](https://docs.certora.com/en/latest/docs/cvl/defs.html#filter-example)
      * [Syntax](https://docs.certora.com/en/latest/docs/cvl/defs.html#syntax)
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
  * Definitions
  * [ View page source](https://docs.certora.com/en/latest/_sources/docs/cvl/defs.md.txt)


# Definitions[](https://docs.certora.com/en/latest/docs/cvl/defs.html#definitions "Link to this heading")
## Basic Usage[](https://docs.certora.com/en/latest/docs/cvl/defs.html#basic-usage "Link to this heading")
In CVL, **definitions** serve as type-checked macros, encapsulating commonly used expressions. They are declared at the top level of a specification and are in scope inside every rule, function, and other definitions. The basic usage involves binding parameters for use in an expression on the right-hand side, with the result evaluating to the declared return type. Definitions can take any number of arguments of any primitive types, including uninterpreted sorts, and evaluate to a single primitive type, including uninterpreted sorts.
### Example:[](https://docs.certora.com/en/latest/docs/cvl/defs.html#example "Link to this heading")
`is_even` binds the variable `x` as a `uint256`. Definitions are applied just as any function would be.
```
methods{
foo(uint256)returnsboolenvfree
}
definitionMAX_UINT256()returnsuint256=0xffffffffffffffffffffffffffffffff;
definitionis_even(uint256x)returnsbool=existsuint256y.2*y==x;
rulemy_rule(uint256x){
requireis_even(x)&&x<=MAX_UINT256();
foo@withrevert(x);
assert!lastReverted;
}

```
Copy to clipboard
## Advanced Functionality[](https://docs.certora.com/en/latest/docs/cvl/defs.html#advanced-functionality "Link to this heading")
### Include an Application of Another Definition[](https://docs.certora.com/en/latest/docs/cvl/defs.html#include-an-application-of-another-definition "Link to this heading")
Definitions can include an application of another definition, allowing for arbitrarily deep nesting. However, circular dependencies are not allowed, and the type checker will report an error if detected.
#### Example:[](https://docs.certora.com/en/latest/docs/cvl/defs.html#id1 "Link to this heading")
`is_odd` and `is_odd_no_overflow` both reference other definitions:
```
definitionMAX_UINT256()returnsuint256=0xffffffffffffffffffffffffffffffff;
definitionis_even(uint256x)returnsbool=existsuint256y.2*y==x;
definitionis_odd(uint256x)returnsbool=!is_even(x);
definitionis_odd_no_overflow(uint256x)returnsbool=
is_odd(x)&&x<=MAX_UINT256();

```
Copy to clipboard
### Type Error circular dependency[](https://docs.certora.com/en/latest/docs/cvl/defs.html#type-error-circular-dependency "Link to this heading")
The following examples would result in a type error due to a circular dependency:
```
// example 1
// cycle: is_even -> is_odd -> is_even
definitionis_even(uint256x)returnsbool=!is_odd(x);
definitionis_odd(uint256x)returnsbool=!is_even(x);
// example 2
// cycle: circular1->circular2->circular3->circular1
definitioncircular1(uintx)returnsuint=circular2(x)+5;
definitioncircular2(uintx)returnsuint=circular3(x-2)+7;
definitioncircular3(uintx)returnsuint=circular1(x)+circular1(x);

```
Copy to clipboard
### Reference Ghost Functions[](https://docs.certora.com/en/latest/docs/cvl/defs.html#reference-ghost-functions "Link to this heading")
Definitions may reference ghost functions. This means that definitions are not always “pure” and can affect ghosts, which are considered a “global” construct.
#### Example:[](https://docs.certora.com/en/latest/docs/cvl/defs.html#id2 "Link to this heading")
```
ghostfoo(uint256)returnsuint256;
definitionis_even(uint256x)returnsbool=x%2==0;
definitionfoo_is_even_at(uint256x)returnsbool=is_even(foo(x));
rulerule_assuming_foo_is_even_at(uint256x){
requirefoo_is_even_at(x);
// ...
}

```
Copy to clipboard
More interestingly, the two-context version of ghosts can be used in a definition by adding the `@new` or `@old` annotations. If a two-context version is used, the ghost must not be used without an `@new` or `@old` annotation, and the definition must be used in a two-state context for that ghost function (e.g., at the right side of a `havoc assuming` statement for that ghost).
#### Example:[](https://docs.certora.com/en/latest/docs/cvl/defs.html#id3 "Link to this heading")
```
ghostfoo(uint256)returnsuint256;
definitionis_even(uint256x)returnsbool=x%2==0;
definitionfoo_add_even(uint256x)returnsbool=is_even(foo@new(x))&&
foralluint256a.is_even(foo@old(x))=>is_even(foo@new(x));
rulerule_assuming_old_evens(uint256x){
// havoc foo, assuming all old even entries are still even, and that
// the entry at x is also even
havocfooassumingfoo_add_even(x);
// ...
}

```
Copy to clipboard
**Note:** The type checker will notify you if a two-state version of a variable is used incorrectly.
## Filter Example[](https://docs.certora.com/en/latest/docs/cvl/defs.html#filter-example "Link to this heading")
The following example introduces a definition called `filterDef`:
```
definitionfilterDef(methodf)returnsbool=f.selector==sig:someUInt().selector;

```
Copy to clipboard
This definition serves as shorthand for `f.selector == sig:someUInt().selector` and is used in the filter for the `parametricRule`:
```
ruleparametricRuleInBase(methodf)filtered{f->filterDef(f)}
{
// ...
}

```
Copy to clipboard
This is equivalent to:
```
ruleparametricRuleInBase(methodf)filtered{f->f.selector==sig:someUInt().selector}{
// ...
}

```
Copy to clipboard
## Syntax[](https://docs.certora.com/en/latest/docs/cvl/defs.html#syntax "Link to this heading")
The syntax for definitions is given by the following EBNF grammar:
```
definition ::= [ "override" ]
        "definition" id [ "(" params ")" ]
        "returns" cvl_type
        "=" expression ";"

```
Copy to clipboard
See [Types](https://docs.certora.com/en/latest/docs/cvl/types.html), [Expressions](https://docs.certora.com/en/latest/docs/cvl/expr.html), and [Identifiers](https://docs.certora.com/en/latest/docs/cvl/basics.html#identifiers) for descriptions of the `cvl_type`, `expression`, and `id` productions, respectively.
In this syntax, the `definition` keyword is followed by the definition’s identifier (`id`). Parameters can be specified in parentheses, and the return type is declared using the `returns` keyword. The body of the definition is provided after the equal sign (`=`) and should end with a semicolon (`;`).
[ Previous](https://docs.certora.com/en/latest/docs/cvl/ghosts.html "Ghosts") [Next ](https://docs.certora.com/en/latest/docs/cvl/hooks.html "Hooks")
© Copyright 2025, Certora, Inc.
Built with [Sphinx](https://www.sphinx-doc.org/) using a [theme](https://github.com/readthedocs/sphinx_rtd_theme) provided by [Read the Docs](https://readthedocs.org). 
