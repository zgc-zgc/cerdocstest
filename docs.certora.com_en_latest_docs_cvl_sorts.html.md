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
      * [Syntax for Uninterpreted Sorts](https://docs.certora.com/en/latest/docs/cvl/sorts.html#syntax-for-uninterpreted-sorts)
      * [Example Usage](https://docs.certora.com/en/latest/docs/cvl/sorts.html#example-usage)
      * [Using Uninterpreted Sorts with Ghosts](https://docs.certora.com/en/latest/docs/cvl/sorts.html#using-uninterpreted-sorts-with-ghosts)
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
  * Uninterpreted Sorts
  * [ View page source](https://docs.certora.com/en/latest/_sources/docs/cvl/sorts.md.txt)


# Uninterpreted Sorts[](https://docs.certora.com/en/latest/docs/cvl/sorts.html#uninterpreted-sorts "Link to this heading")
CVL specifications support both Solidity primitives (`uint256`, `address`, etc.) and custom types (e.g., `mathint`). Solidity types are _interpreted_ , meaning they have specific semantics, such as arithmetic or comparison operations. However, in some cases, it is beneficial to use _uninterpreted sorts_ , which do not carry the semantics associated with interpretation.
## Syntax for Uninterpreted Sorts[](https://docs.certora.com/en/latest/docs/cvl/sorts.html#syntax-for-uninterpreted-sorts "Link to this heading")
To declare an uninterpreted sort in CVL, use the following syntax:
```
sortMyUninterpSort;
sortFoo;

```
Copy to clipboard
These uninterpreted sorts can be utilized in various ways within a CVL specification:
  1. **Declare Variables:**
```
Foox;

```
Copy to clipboard
  2. **Test Equality:**
```
Foox;
Fooy;
assertx==y;

```
Copy to clipboard
  3. **Use in Signatures:**
```
ghostmyGhost(uint256,Foo)returnsFoo;

```
Copy to clipboard


## Example Usage[](https://docs.certora.com/en/latest/docs/cvl/sorts.html#example-usage "Link to this heading")
Consider the following example:
```
sortFoo;
ghostbar(Foo,Foo)returnsFoo;
rulemyRule{
Foox;
Fooy;
Fooz=bar(x,y);
assertx==y&&y==z;
}

```
Copy to clipboard
This example demonstrates the use of an uninterpreted sort `Foo`. The `bar` ghost function takes two arguments of type `Foo` and returns a value of the same type. The `myRule` rule declares variables `x`, `y`, and `z`, and asserts that they are all equal.
## Using Uninterpreted Sorts with Ghosts[](https://docs.certora.com/en/latest/docs/cvl/sorts.html#using-uninterpreted-sorts-with-ghosts "Link to this heading")
Uninterpreted sorts can also be employed in ghosts, as shown in the following example:
```
ghostmapping(uint256=>Node)toNode;
ghostmapping(Node=>mapping(Node=>bool))reach{
// Axioms for reachability relation
axiomforallNodeX.reach[X][X];
axiomforallNodeX.forallNodeY.
reach[X][Y]&&reach[Y][X]=>X==Y;
axiomforallNodeX.forallNodeY.forallNodeZ.
reach[X][Y]&&reach[Y][Z]=>reach[X][Z];
axiomforallNodeX.forallNodeY.forallNodeZ.
reach[X][Y]&&reach[X][Z]=>(reach[Y][Z]||reach[Z][Y]);
}
definitionisSucc(Nodea,Nodeb)returnsbool=
// Definition for successor relationship
reach[a][b]&&a!=b&&
(forallNodeX.reach[a][X]&&reach[X][b]=>(a==X||b==X));
rulecheckGetSucc{
uint256key;
uint256afterKey=getSucc(key);
assertreach[toNode[key]][toNode[afterKey]];
}

```
Copy to clipboard
This example demonstrates the use of uninterpreted sorts (`Node`) in ghost mappings and functions, emphasizing their application in specifying relationships and properties without being bound by specific interpretations.
In summary, uninterpreted sorts in CVL provide a versatile tool for declaring abstract types and relationships, allowing for greater expressiveness in specification design.
[ Previous](https://docs.certora.com/en/latest/docs/cvl/invariants.html "Invariants") [Next ](https://docs.certora.com/en/latest/docs/cvl/ghosts.html "Ghosts")
© Copyright 2025, Certora, Inc.
Built with [Sphinx](https://www.sphinx-doc.org/) using a [theme](https://github.com/readthedocs/sphinx_rtd_theme) provided by [Read the Docs](https://readthedocs.org). 
