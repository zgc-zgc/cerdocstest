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
      * [Syntax](https://docs.certora.com/en/latest/docs/cvl/rules.html#syntax)
      * [Overview](https://docs.certora.com/en/latest/docs/cvl/rules.html#overview)
      * [Parametric rules](https://docs.certora.com/en/latest/docs/cvl/rules.html#parametric-rules)
      * [Filters](https://docs.certora.com/en/latest/docs/cvl/rules.html#filters)
      * [Multiple assertions](https://docs.certora.com/en/latest/docs/cvl/rules.html#multiple-assertions)
      * [Rule descriptions](https://docs.certora.com/en/latest/docs/cvl/rules.html#rule-descriptions)
      * [How rules are verified](https://docs.certora.com/en/latest/docs/cvl/rules.html#how-rules-are-verified)
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
  * Rules
  * [ View page source](https://docs.certora.com/en/latest/_sources/docs/cvl/rules.md.txt)


# [Rules](https://docs.certora.com/en/latest/docs/cvl/rules.html#id2)[](https://docs.certora.com/en/latest/docs/cvl/rules.html#rules "Link to this heading")
Rules (along with [Invariants](https://docs.certora.com/en/latest/docs/cvl/invariants.html)) are the main entry points for the Prover. A rule defines a sequence of [commands](https://docs.certora.com/en/latest/docs/cvl/statements.html) that should be simulated during verification.
When the Prover is invoked with the [verify](https://docs.certora.com/en/latest/docs/prover/cli/options.html#verify) option, it generates a report for each rule and invariant present in the spec file (as well as any [imported rules](https://docs.certora.com/en/latest/docs/cvl/imports.html#use)).
You can find examples for rules in the [Certora Prover and CVL Examples Repository](https://github.com/Certora/Examples/). For example, the specs in [/CVLByExample/Teams/](https://github.com/Certora/Examples/tree/7dfc379423202c90cf284eb42800b97cf5c95d83/CVLByExample/Teams) demonstrate some of these features.
Contents
  * [Rules](https://docs.certora.com/en/latest/docs/cvl/rules.html#rules)
    * [Syntax](https://docs.certora.com/en/latest/docs/cvl/rules.html#syntax)
    * [Overview](https://docs.certora.com/en/latest/docs/cvl/rules.html#overview)
    * [Parametric rules](https://docs.certora.com/en/latest/docs/cvl/rules.html#parametric-rules)
    * [Filters](https://docs.certora.com/en/latest/docs/cvl/rules.html#filters)
    * [Multiple assertions](https://docs.certora.com/en/latest/docs/cvl/rules.html#multiple-assertions)
    * [Rule descriptions](https://docs.certora.com/en/latest/docs/cvl/rules.html#rule-descriptions)
    * [How rules are verified](https://docs.certora.com/en/latest/docs/cvl/rules.html#how-rules-are-verified)


## [Syntax](https://docs.certora.com/en/latest/docs/cvl/rules.html#id3)[](https://docs.certora.com/en/latest/docs/cvl/rules.html#syntax "Link to this heading")
The syntax for rules is given by the following [EBNF grammar](https://docs.certora.com/en/latest/docs/cvl/overview.html#ebnf-syntax):
```
rule ::= [ "rule" ]
     id
     [ "(" [ params ] ")" ]
     [ "filtered" "{" id "->" expression { "," id "->" expression } "}" ]
     [ "description" string ]
     [ "good_description" string ]
     block
params ::= cvl_type [ id ] { "," cvl_type [ id ] }

```
Copy to clipboard
See [Basic Syntax](https://docs.certora.com/en/latest/docs/cvl/basics.html) for the `id` and `string` productions; see [Expressions](https://docs.certora.com/en/latest/docs/cvl/expr.html) for the `expression` production; see [Types](https://docs.certora.com/en/latest/docs/cvl/types.html) for the `cvl_type` production.
## [Overview](https://docs.certora.com/en/latest/docs/cvl/rules.html#id4)[](https://docs.certora.com/en/latest/docs/cvl/rules.html#overview "Link to this heading")
A rule defines a sequence of commands that should be simulated during verification. These commands may be non-deterministic: they may contain [unassigned variables](https://docs.certora.com/en/latest/docs/cvl/statements.html#declarations) whose value is not specified. The state of storage at the beginning of a rule is also unspecified. Rules may also be declared with a set of parameters; these parameters are treated the same way as undeclared variables.
In principal, the Prover will generate every possible combination of values for the undefined variables, and simulate the commands in the rule using those values. A particular combination of values is referred to as an [example](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-example) or a [model](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-model). There are often an infinite number of models for a given rule; see [How rules are verified](https://docs.certora.com/en/latest/docs/cvl/rules.html#verification) for a brief explanation of how the Prover considers all of them.
If a rule contains a `require` statement that fails on a particular example, the example is ignored. Of the remaining examples, the Prover checks that all of the `assert` statements evaluate to true. If all of the `assert` statements evaluate to true on every example, the rule passes. Otherwise, the Prover will output a specific counterexample that causes the assertions to fail.
  * [simple rule example](https://github.com/Certora/Examples/blob/14668d39a6ddc67af349bc5b82f73db73349ef18/CVLByExample/LiquidityPool/certora/specs/pool.spec#L54)
```
/// `deposit` must increase the pool's underlying asset balance
ruleintegrityOfDeposit{
mathintbalance_before=underlyingBalance();

enve;uint256amount;
safeAssumptions(_,e);
deposit(e,amount);
mathintbalance_after=underlyingBalance();
assertbalance_after==balance_before+amount,
"deposit must increase the underlying balance of the pool";
}

```
Copy to clipboard


Caution
`assert` statements in contract code are handled differently from `assert` statements in rules.
An `assert` statement in Solidity causes the transaction to revert, in the same way that a `require` statement in Solidity would. By default, examples that cause contract functions to revert are [ignored by the prover](https://docs.certora.com/en/latest/docs/cvl/expr.html#with-revert), and these examples will _not_ be reported as counterexamples.
The [multi_assert_check](https://docs.certora.com/en/latest/docs/prover/cli/options.html#multi-assert-check) option causes assertions in the contract code to be reported as counterexamples.
## [Parametric rules](https://docs.certora.com/en/latest/docs/cvl/rules.html#id5)[](https://docs.certora.com/en/latest/docs/cvl/rules.html#parametric-rules "Link to this heading")
Rules that contain undefined `method` variables are sometimes called [parametric rule](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-parametric-rule)s. See [The method and calldataarg types](https://docs.certora.com/en/latest/docs/cvl/types.html#method-type) for more details about how to use method variables.
Undefined variables of the `method` type are treated slightly differently from undefined variables of other types. If a rule uses one or more undefined `method` variables, the Prover will generate a separate report for each method (or combination of methods).
In particular, the Prover will generate a separate counterexample for each method that violates the rule, and will indicate if some contract methods always satisfy the rule.
You can request that the Prover only run with specific methods using the [method](https://docs.certora.com/en/latest/docs/prover/cli/options.html#method) and [parametric_contracts](https://docs.certora.com/en/latest/docs/prover/cli/options.html#parametric-contracts) command line arguments. The set of methods can also be restricted using [rule filters](https://docs.certora.com/en/latest/docs/cvl/rules.html#rule-filters). The Prover will automatically skip any methods that have [ `DELETE` summaries](https://docs.certora.com/en/latest/docs/cvl/methods.html#delete-summary).
If you wish to only invoke methods on a certain contract, you can call the `method` variable with an explicit receiver contract. The receiver must be a contract variable (either [currentContract](https://docs.certora.com/en/latest/docs/cvl/expr.html#currentcontract) or a variable introduced with a `using` statement). For example, the following will only verify the rule `r` on methods of the contract `example`:
```
usingExampleasexample;
ruler{
methodf;enve;calldataargargs;
example.f(e,args);
...
}

```
Copy to clipboard
It is an error to call the same `method` variable on two different contracts.
```
rulesanity(methodf){
enve;
calldataargargs;
f(e,args);
assertfalse;
}

```
Copy to clipboard
  * [parameteric rule example](https://github.com/Certora/Examples/blob/14668d39a6ddc67af349bc5b82f73db73349ef18/CVLByExample/structs/BankAccounts/certora/specs/Bank.spec#L94)


## [Filters](https://docs.certora.com/en/latest/docs/cvl/rules.html#id6)[](https://docs.certora.com/en/latest/docs/cvl/rules.html#filters "Link to this heading")
A rule declaration may have a `filtered` block after the rule parameters. Rule filters allow you to prevent verification of parametric rules on certain methods. This can be less computationally expensive than using a `require` statement to ignore counterexamples for a method.
The `filtered` block consists of zero or more filters of the form `var -> expr`. `var` must match one of the `method` parameters to the rule, and `expr` must be a boolean expression that may refer to the variable `var`. The filter expression may not refer to other method parameters or any variables defined in the rule.
Before verifying that a method `m` satisfies a parametric rule, the `expr` is evaluated with `var` bound to a `method` object. This allows `expr` to refer to the fields of `var`, such as `var.selector` and `var.isView`. See [The method and calldataarg types](https://docs.certora.com/en/latest/docs/cvl/types.html#method-type) for a list of the fields available on `method` objects.
For example, the following rule has two filters. The rule will only be verified with `f` instantiated by a view method, and `g` instantiated by a method other than `exampleMethod(uint,uint)` or `otherExample(address)`:
  * [filters example](https://github.com/Certora/Examples/blob/14668d39a6ddc67af349bc5b82f73db73349ef18/CVLByExample/Reentrancy/certora/spec/Reentrancy.spec#L29C9-L29C9)


```
ruler(methodf,methodg)filtered{
f->f.isView,
g->g.selector!=exampleMethod(uint,uint).selector
&&g.selector!=otherExample(address).selector
}{
// rule body
...
}

```
Copy to clipboard
See [The method and calldataarg types](https://docs.certora.com/en/latest/docs/cvl/types.html#method-type) for a list of the fields of the `method` type.
## [Multiple assertions](https://docs.certora.com/en/latest/docs/cvl/rules.html#id7)[](https://docs.certora.com/en/latest/docs/cvl/rules.html#multiple-assertions "Link to this heading")
Rules may contain multiple assertions. By default, if any assertion fails, the Prover will report that the entire rule failed and give a counterexample that causes one of the assertions to fail.
Occasionally it is useful to consider different assert statements in a rule separately. With the [multi_assert_check](https://docs.certora.com/en/latest/docs/prover/cli/options.html#multi-assert-check) option, the Prover will try to generate separate counterexamples for each `assert` statement. The counterexamples generated for a particular `assert` statement will pass all earlier `assert` statements.
## [Rule descriptions](https://docs.certora.com/en/latest/docs/cvl/rules.html#id8)[](https://docs.certora.com/en/latest/docs/cvl/rules.html#rule-descriptions "Link to this heading")
Rules may be annotated by writing `description` and/or `good_description` before the method body, followed by a string. These strings are displayed in the verification report.
## [How rules are verified](https://docs.certora.com/en/latest/docs/cvl/rules.html#id9)[](https://docs.certora.com/en/latest/docs/cvl/rules.html#how-rules-are-verified "Link to this heading")
While verifying a rule, the Prover does not actually enumerate every possible example and run the rule on the example. Instead, the Prover translates the contract code and the rule into a logical formula with logical variables representing the unspecified variables from the rule.
The logical formula is designed so that if a particular example satisfies the requirements and also causes an assertion to fail, then the formula will evaluate to `true` on that example; otherwise the formula will evaluate to false.
The Prover then uses off-the-shelf software called an SMT solver to determine whether there are any examples that cause the formula to evaluate to true. If there are, the SMT solver provides an example to the Prover, which then translates it into an example for the user. If the SMT solver reports that the formula is unsatisfiable, then we are guaranteed that whenever the `require` statements are true, the `assert` statements are also true.
[ Previous](https://docs.certora.com/en/latest/docs/cvl/methods.html "The Methods Block") [Next ](https://docs.certora.com/en/latest/docs/cvl/builtin.html "Built-in Rules")
© Copyright 2025, Certora, Inc.
Built with [Sphinx](https://www.sphinx-doc.org/) using a [theme](https://github.com/readthedocs/sphinx_rtd_theme) provided by [Read the Docs](https://readthedocs.org). 
