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
      * [CVL2 Migration Guide](https://docs.certora.com/en/latest/docs/cvl/cvl2/migration.html)
        * [Step 0: Install CVL 2](https://docs.certora.com/en/latest/docs/cvl/cvl2/migration.html#step-0-install-cvl-2)
        * [Step 1: Skim CVL 2 changes](https://docs.certora.com/en/latest/docs/cvl/cvl2/migration.html#step-1-skim-cvl-2-changes)
        * [Step 2: Run the migration script](https://docs.certora.com/en/latest/docs/cvl/cvl2/migration.html#step-2-run-the-migration-script)
        * [Step 3: Fix type errors](https://docs.certora.com/en/latest/docs/cvl/cvl2/migration.html#step-3-fix-type-errors)
        * [Step 4: Review your `methods` blocks](https://docs.certora.com/en/latest/docs/cvl/cvl2/migration.html#step-4-review-your-methods-blocks)
        * [Step 5: Profit!](https://docs.certora.com/en/latest/docs/cvl/cvl2/migration.html#step-5-profit)
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
  * CVL2 Migration Guide
  * [ View page source](https://docs.certora.com/en/latest/_sources/docs/cvl/cvl2/migration.md.txt)


# CVL2 Migration Guide[](https://docs.certora.com/en/latest/docs/cvl/cvl2/migration.html#cvl2-migration-guide "Link to this heading")
This section gives a step-by-step process for migrating your specs from CVL 1 to CVL 2. It only addresses the changes that are most likely to arise; for full details see [Changes Introduced in CVL 2](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html).
Here is an outline of the migration process:
  * [Step 0: Install CVL 2](https://docs.certora.com/en/latest/docs/cvl/cvl2/migration.html#step-0-install-cvl-2)
  * [Step 1: Skim CVL 2 changes](https://docs.certora.com/en/latest/docs/cvl/cvl2/migration.html#step-1-skim-cvl-2-changes)
  * [Step 2: Run the migration script](https://docs.certora.com/en/latest/docs/cvl/cvl2/migration.html#step-2-run-the-migration-script)
  * [Step 3: Fix type errors](https://docs.certora.com/en/latest/docs/cvl/cvl2/migration.html#step-3-fix-type-errors)
  * [Step 4: Review your `methods` blocks](https://docs.certora.com/en/latest/docs/cvl/cvl2/migration.html#step-4-review-your-methods-blocks)
  * [Step 5: Profit!](https://docs.certora.com/en/latest/docs/cvl/cvl2/migration.html#step-5-profit)


If you have any questions, please [ask for help](https://docs.certora.com/en/latest/index.html#contact)!
## [Step 0: Install CVL 2](https://docs.certora.com/en/latest/docs/cvl/cvl2/migration.html#id3)[](https://docs.certora.com/en/latest/docs/cvl/cvl2/migration.html#step-0-install-cvl-2 "Link to this heading")
The `certora-cli` python package will use CVL 2 starting with version 4.0.0.
If you aren’t ready to migrate your specs yet, Certora will continue supporting CVL 1 for three months after the official release of CVL 2. You can keep using CVL 1 after the release of `certora-cli-4.0.0` by pinning your `certora-cli` package to version `3.6.5`:
```
pip install 'certora-cli<4.0.0'

```
Copy to clipboard
If you want to switch between the two versions, see the instructions for setting up a virtual environment in [Installing the beta version (optional)](https://docs.certora.com/en/latest/docs/user-guide/install.html#beta-install).
## [Step 1: Skim CVL 2 changes](https://docs.certora.com/en/latest/docs/cvl/cvl2/migration.html#id4)[](https://docs.certora.com/en/latest/docs/cvl/cvl2/migration.html#step-1-skim-cvl-2-changes "Link to this heading")
We recommend at least skimming [Changes Introduced in CVL 2](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html) to familiarize yourself with the changes introduced by CVL 2.
## [Step 2: Run the migration script](https://docs.certora.com/en/latest/docs/cvl/cvl2/migration.html#id5)[](https://docs.certora.com/en/latest/docs/cvl/cvl2/migration.html#step-2-run-the-migration-script "Link to this heading")
Certora has written a simple script to aid in the conversion from CVL 1 to CVL 2. You can download the script [here](https://gist.github.com/shellygr/c054a0ad569397ef4e19ec1d1d5afcdb).
The script will automatically modify all `.spec` files in a directory. The script will modify the files in place, so make sure that you commit your files before running it.
To run the script, place it in a file called `CVL1_to_CVL2.0_syntax_update.py` and run it using the following command:
```
python3 CVL1_to_CVL2.0_syntax_update.py -d <path> -r

```
Copy to clipboard
Run `python3 CVL1_to_CVL2.0_syntax_update.py --help` for further instructions.
The migration script only handles simple cases, and is not guaranteed to work. Some manual work and adjustment may be needed after running the script. The script may also make odd mistakes.
The script will attempt to make the following changes:
  * replace `sinvoke f(...)` with `f(...)`
  * replace `invoke f(...)` with `f@withrevert(...)`
  * replace `f(...).selector` with `sig:f(...).selector`
  * ensure that rules start with `rule`
  * replace `static_assert` with `assert`
  * replace `static_require` with `require`
  * add `;` to the end of `pragma`, `import`, `using`, and `use` statements
  * add a `;` to the end of a methods block entry if it doesn’t seem to continue to the next line
  * add `function` to the beginning of a methods block entry
  * add `external` to unsummarized or `DISPATCHER` methods block entries
  * change `function f(...)` to `function _.f(...)` for summarized external functions


In particular, as the script only consumes spec files, there are decisions that it cannot make, as they are based on the Solidity code. Some of those are listed here.
## [Step 3: Fix type errors](https://docs.certora.com/en/latest/docs/cvl/cvl2/migration.html#id6)[](https://docs.certora.com/en/latest/docs/cvl/cvl2/migration.html#step-3-fix-type-errors "Link to this heading")
This is a good time to try running `certoraRun` on your spec. The command-line interface to `certoraRun` has not changed in CVL 2, so you should try to verify your contract the same way you usually would.
If your spec verifies without errors, move on to [Step 4: Review your methods blocks](https://docs.certora.com/en/latest/docs/cvl/cvl2/migration.html#cvl2-migration-summaries)! If `certoraRun` reports errors, you will need to fix them manually. Here are some of the more common errors that you may come across:
  * [Syntax errors introduced by the migration script](https://docs.certora.com/en/latest/docs/cvl/cvl2/migration.html#syntax-errors-introduced-by-the-migration-script)
  * [Type errors in arithmetic and casts](https://docs.certora.com/en/latest/docs/cvl/cvl2/migration.html#type-errors-in-arithmetic-and-casts)
  * [`using` statements](https://docs.certora.com/en/latest/docs/cvl/cvl2/migration.html#using-statements)
  * [Problems with `certorafallback` or `invoke_fallback`](https://docs.certora.com/en/latest/docs/cvl/cvl2/migration.html#problems-with-certorafallback-or-invoke-fallback)


This section contains specific advice for these situations; if you come across problems that are not covered here, consult the [Changes Introduced in CVL 2](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html) or ask!
### [Syntax errors introduced by the migration script](https://docs.certora.com/en/latest/docs/cvl/cvl2/migration.html#id9)[](https://docs.certora.com/en/latest/docs/cvl/cvl2/migration.html#syntax-errors-introduced-by-the-migration-script "Link to this heading")
The migration script is not perfect, and can make syntax mistakes in some cases, such as adding an extra semicolon or omitting a keyword. We hope these will be easy to identify and fix, but if you have syntax errors you can’t understand, consult [Superficial syntax changes](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#cvl2-superficial-syntax-changes).
### [Type errors in arithmetic and casts](https://docs.certora.com/en/latest/docs/cvl/cvl2/migration.html#id10)[](https://docs.certora.com/en/latest/docs/cvl/cvl2/migration.html#type-errors-in-arithmetic-and-casts "Link to this heading")
CVL 2 is more careful about converting between different integer types. See [Changes to integer types](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#cvl2-integer-types) in the changes guide for complete details and examples.
If you have errors that indicate problems with number types, try the following:
  * Try to change most of your integers to `mathint`. The only integers that should _not_ be `mathint` are those that you are passing as arguments to contract functions.
  * If you have a type error in a `havoc ... assuming` statement, consider using the [newer ghost variable syntax](https://docs.certora.com/en/latest/docs/cvl/ghosts.html#ghost-variables). This can avoid potential vacuity pitfalls caused by mixing `to_mathint` and `havoc ... assuming`.
  * If you need to modify the output of one contract function and pass it to another contract function, you will need to think carefully about how you want to handle overflow. If you think the computation won’t go out of bounds, you can use an `assert_` cast to assert that the value is in bounds. If you want to ignore cases where the value goes out of bounds, you can use a `require_` cast (but think twice first: `require_` casts are dangerous!). See [Changes to integer types](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#cvl2-integer-types) for more details.


Warning
Use `assert_` and `require_` casts sparingly! `assert_` casts can lead to unnecessary counterexamples, and `require_` casts can hide bugs in your contracts (just as any `require` statement can).
  * You cannot use `assert_` and `require_` casts inside [quantified statements](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-quantifier). To solve that issue, you can introduce an additional universally quantified variable of type `uint256`, and require it to be equal to the expression using an upcast to `mathint`.
For example, if there is a ghost array access `forall uint x. a[x+1] == 0`, rewrite it as follows:
```
foralluintx.foralluinty.to_mathint(y)==x+1=>a[y]==0

```
Copy to clipboard


### [`using` statements](https://docs.certora.com/en/latest/docs/cvl/cvl2/migration.html#id11)[](https://docs.certora.com/en/latest/docs/cvl/cvl2/migration.html#using-statements "Link to this heading")
Multi-contract declaration using `using` statements are not imported. If you have a spec `a.spec` importing `b.spec`, with `b.spec` declaring a multicontract contract usage, which you need in `a.spec`, repeat the declaration from `b.spec`, and rename the alias.
_The next minor version of CVL2 will improve this behavior._
### [Problems with `certorafallback` or `invoke_fallback`](https://docs.certora.com/en/latest/docs/cvl/cvl2/migration.html#id12)[](https://docs.certora.com/en/latest/docs/cvl/cvl2/migration.html#problems-with-certorafallback-or-invoke-fallback "Link to this heading")
CVL2 does not allow you to refer to the fallback function explicitly as it was seldom used and not well-defined. The most common use case for having to refer to the fallback was to check if a parametric method is the fallback function. For that, one can use the `.isFallback` field of any variable of type `method`.
See [Changes to the fallback function](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#cvl2-fallback-changes) for examples.
## [Step 4: Review your `methods` blocks](https://docs.certora.com/en/latest/docs/cvl/cvl2/migration.html#id7)[](https://docs.certora.com/en/latest/docs/cvl/cvl2/migration.html#step-4-review-your-methods-blocks "Link to this heading")
CVL 2 changes the requirements for and meanings of methods block entries; you should manually review all of your methods block entries to make sure they have the intended meanings. Here are the things to consider:
  * [`internal` and `external` methods](https://docs.certora.com/en/latest/docs/cvl/cvl2/migration.html#internal-and-external-methods)
  * [Receiver contracts](https://docs.certora.com/en/latest/docs/cvl/cvl2/migration.html#receiver-contracts)


The remainder of this section describes these considerations. See [Changes to methods block entries](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#cvl2-methods-blocks) for more details.
If you have complex methods blocks, we encourage you to examine the call resolution tab on the rule report to double-check that your summaries are applied as you expect them to be.
### [`internal` and `external` methods](https://docs.certora.com/en/latest/docs/cvl/cvl2/migration.html#id13)[](https://docs.certora.com/en/latest/docs/cvl/cvl2/migration.html#internal-and-external-methods "Link to this heading")
In CVL 2, you must mark `methods` block entries as either `internal` or `external`. Unlike Solidity, you cannot mark entries as `private` or `public`.
The Prover does not distinguish between `private` and `internal` methods; if you want to summarize a `private` method, use `internal` in the `methods` block.
To understand how to work with public Solidity methods, it is important to understand how Solidity compiles public functions. When a contract contains a public method, the Solidity compiler generates an internal method that executes the code, and an external method that calls the internal method.
You can add methods block entries for either (or both) of those methods, and they will have different effects. See [Required internal or external annotation](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#cvl2-visibility) for the details.
### [Receiver contracts](https://docs.certora.com/en/latest/docs/cvl/cvl2/migration.html#id14)[](https://docs.certora.com/en/latest/docs/cvl/cvl2/migration.html#receiver-contracts "Link to this heading")
In CVL 1, method summaries applied to all methods in all contracts that match the specified signature. In CVL 2, summaries only apply to one contract by default.
You specify the receiver contract just before the method name. For example, to refer to the `exampleMethod` method of the `ExampleContract` contract, you would write:
```
methods{
functionExampleContract.exampleMethod(uint)externalreturns(uint);
}

```
Copy to clipboard
If no contract is specified, the default contract is `currentContract`.
If you want to write an entry that applies to methods in all contracts with the given signature, you can use the special `_` receiver:
```
methods{
function_.exampleMethod(uint)external=>NONDET;
}

```
Copy to clipboard
Wildcard entries cannot specify return types. If you summarize them with a CVL function or ghost, you will need to supply an `expect` clause. See [Summaries only apply to one contract by default](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html#cvl2-wildcards) for details.
## [Step 5: Profit!](https://docs.certora.com/en/latest/docs/cvl/cvl2/migration.html#id8)[](https://docs.certora.com/en/latest/docs/cvl/cvl2/migration.html#step-5-profit "Link to this heading")
Hopefully this guide has helped you successfully migrate to CVL 2. Although the functional changes in CVL 2.0 are relatively small, the internal changes lay the groundwork for many exciting features. We promise that the effort involved in migration will pay off in the next few releases!
[ Previous](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html "Changes Introduced in CVL 2") [Next ](https://docs.certora.com/en/latest/docs/cvl/v5-changes.html "Certora CLI 5.0 Changes")
© Copyright 2025, Certora, Inc.
Built with [Sphinx](https://www.sphinx-doc.org/) using a [theme](https://github.com/readthedocs/sphinx_rtd_theme) provided by [Read the Docs](https://readthedocs.org). 
