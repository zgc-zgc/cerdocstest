[ Certora Prover Documentation ![Logo](https://docs.certora.com/en/latest/_static/Certora_Logo_Black.svg) ](https://docs.certora.com/en/latest/index.html)
Contents
  * [Certora User’s Guide](https://docs.certora.com/en/latest/docs/user-guide/index.html)
  * [The Certora Verification Language](https://docs.certora.com/en/latest/docs/cvl/index.html)
    * [Specification Files](https://docs.certora.com/en/latest/docs/cvl/overview.html)
    * [Basic Syntax](https://docs.certora.com/en/latest/docs/cvl/basics.html)
    * [Types](https://docs.certora.com/en/latest/docs/cvl/types.html)
    * [Expressions](https://docs.certora.com/en/latest/docs/cvl/expr.html)
    * [Statements](https://docs.certora.com/en/latest/docs/cvl/statements.html)
      * [Syntax](https://docs.certora.com/en/latest/docs/cvl/statements.html#syntax)
      * [Variable declarations](https://docs.certora.com/en/latest/docs/cvl/statements.html#variable-declarations)
      * [`assert` and `require`](https://docs.certora.com/en/latest/docs/cvl/statements.html#assert-and-require)
        * [Examples](https://docs.certora.com/en/latest/docs/cvl/statements.html#examples)
      * [`satisfy` statements](https://docs.certora.com/en/latest/docs/cvl/statements.html#satisfy-statements)
      * [`requireInvariant` statements](https://docs.certora.com/en/latest/docs/cvl/statements.html#requireinvariant-statements)
      * [Havoc Statements](https://docs.certora.com/en/latest/docs/cvl/statements.html#havoc-statements)
        * [Syntax](https://docs.certora.com/en/latest/docs/cvl/statements.html#id1)
        * [Usage](https://docs.certora.com/en/latest/docs/cvl/statements.html#usage)
        * [Two-State Contexts: `@old` and `@new`](https://docs.certora.com/en/latest/docs/cvl/statements.html#two-state-contexts-old-and-new)
        * [Advanced Usage: `havoc assuming`](https://docs.certora.com/en/latest/docs/cvl/statements.html#advanced-usage-havoc-assuming)
        * [Conclusion](https://docs.certora.com/en/latest/docs/cvl/statements.html#conclusion)
      * [Solidity-like Statements](https://docs.certora.com/en/latest/docs/cvl/statements.html#solidity-like-statements)
        * [1. Assert Statement](https://docs.certora.com/en/latest/docs/cvl/statements.html#assert-statement)
        * [2. Require Statement](https://docs.certora.com/en/latest/docs/cvl/statements.html#require-statement)
        * [3. Modeling Reverts in Solidity Calls](https://docs.certora.com/en/latest/docs/cvl/statements.html#modeling-reverts-in-solidity-calls)
        * [4. Return Statement](https://docs.certora.com/en/latest/docs/cvl/statements.html#return-statement)
        * [Conclusion](https://docs.certora.com/en/latest/docs/cvl/statements.html#id16)
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
  * Statements
  * [ View page source](https://docs.certora.com/en/latest/_sources/docs/cvl/statements.md.txt)


# [Statements](https://docs.certora.com/en/latest/docs/cvl/statements.html#id17)[](https://docs.certora.com/en/latest/docs/cvl/statements.html#statements "Link to this heading")
The bodies of [rules](https://docs.certora.com/en/latest/docs/cvl/rules.html), [functions](https://docs.certora.com/en/latest/docs/cvl/functions.html), and [hooks](https://docs.certora.com/en/latest/docs/cvl/hooks.html) in CVL are made up of statements. Statements describe the steps that are simulated by the Prover when evaluating a rule.
Statements in CVL are similar to statements in Solidity, although there are some differences; see [Solidity-like Statements](https://docs.certora.com/en/latest/docs/cvl/statements.html#control-flow). This document lists the available CVL commands.
Contents
  * [Statements](https://docs.certora.com/en/latest/docs/cvl/statements.html#statements)
    * [Syntax](https://docs.certora.com/en/latest/docs/cvl/statements.html#syntax)
    * [Variable declarations](https://docs.certora.com/en/latest/docs/cvl/statements.html#variable-declarations)
    * [`assert` and `require`](https://docs.certora.com/en/latest/docs/cvl/statements.html#assert-and-require)
      * [Examples](https://docs.certora.com/en/latest/docs/cvl/statements.html#examples)
    * [`satisfy` statements](https://docs.certora.com/en/latest/docs/cvl/statements.html#satisfy-statements)
    * [`requireInvariant` statements](https://docs.certora.com/en/latest/docs/cvl/statements.html#requireinvariant-statements)
    * [Havoc Statements](https://docs.certora.com/en/latest/docs/cvl/statements.html#havoc-statements)
      * [Syntax](https://docs.certora.com/en/latest/docs/cvl/statements.html#id1)
      * [Usage](https://docs.certora.com/en/latest/docs/cvl/statements.html#usage)
        * [Basic Havoc](https://docs.certora.com/en/latest/docs/cvl/statements.html#basic-havoc)
          * [Example:](https://docs.certora.com/en/latest/docs/cvl/statements.html#example)
        * [Havoc with Condition](https://docs.certora.com/en/latest/docs/cvl/statements.html#havoc-with-condition)
          * [Example:](https://docs.certora.com/en/latest/docs/cvl/statements.html#id2)
      * [Two-State Contexts: `@old` and `@new`](https://docs.certora.com/en/latest/docs/cvl/statements.html#two-state-contexts-old-and-new)
        * [Example:](https://docs.certora.com/en/latest/docs/cvl/statements.html#id3)
      * [Advanced Usage: `havoc assuming`](https://docs.certora.com/en/latest/docs/cvl/statements.html#advanced-usage-havoc-assuming)
        * [Example:](https://docs.certora.com/en/latest/docs/cvl/statements.html#id4)
      * [Conclusion](https://docs.certora.com/en/latest/docs/cvl/statements.html#conclusion)
    * [Solidity-like Statements](https://docs.certora.com/en/latest/docs/cvl/statements.html#solidity-like-statements)
      * [1. Assert Statement](https://docs.certora.com/en/latest/docs/cvl/statements.html#assert-statement)
        * [Syntax:](https://docs.certora.com/en/latest/docs/cvl/statements.html#id5)
        * [Usage:](https://docs.certora.com/en/latest/docs/cvl/statements.html#id6)
          * [Example:](https://docs.certora.com/en/latest/docs/cvl/statements.html#id7)
      * [2. Require Statement](https://docs.certora.com/en/latest/docs/cvl/statements.html#require-statement)
        * [Syntax:](https://docs.certora.com/en/latest/docs/cvl/statements.html#id8)
        * [Usage:](https://docs.certora.com/en/latest/docs/cvl/statements.html#id9)
          * [Example:](https://docs.certora.com/en/latest/docs/cvl/statements.html#id10)
      * [3. Modeling Reverts in Solidity Calls](https://docs.certora.com/en/latest/docs/cvl/statements.html#modeling-reverts-in-solidity-calls)
        * [Syntax:](https://docs.certora.com/en/latest/docs/cvl/statements.html#id11)
          * [Example:](https://docs.certora.com/en/latest/docs/cvl/statements.html#id12)
      * [4. Return Statement](https://docs.certora.com/en/latest/docs/cvl/statements.html#return-statement)
        * [Syntax:](https://docs.certora.com/en/latest/docs/cvl/statements.html#id13)
        * [Usage:](https://docs.certora.com/en/latest/docs/cvl/statements.html#id14)
          * [Example:](https://docs.certora.com/en/latest/docs/cvl/statements.html#id15)
      * [Conclusion](https://docs.certora.com/en/latest/docs/cvl/statements.html#id16)


## [Syntax](https://docs.certora.com/en/latest/docs/cvl/statements.html#id18)[](https://docs.certora.com/en/latest/docs/cvl/statements.html#syntax "Link to this heading")
The syntax for statements in CVL is given by the following [EBNF grammar](https://docs.certora.com/en/latest/docs/cvl/overview.html#ebnf-syntax):
```
block ::= statement { statement }
statement ::= type id [ "=" expr ] ";"
      | "require" expr ";"
      | "assert" expr [ "," string ] ";"
      | "satisfy" expr [ "," string ] ";"
      | "requireInvariant" id "(" exprs ")" ";"
      | lhs "=" expr ";"
      | "if" expr statement [ "else" statement ]
      | "{" block "}"
      | "return" [ expr ] ";"
      | function_call ";"
      | "reset_storage" expr ";"
      | "havoc" id [ "assuming" expr ] ";"
lhs ::= id [ "[" expr "]" ] [ "," lhs ]

```
Copy to clipboard
See [Basic Syntax](https://docs.certora.com/en/latest/docs/cvl/basics.html) for the `id` and `string` productions. See [Types](https://docs.certora.com/en/latest/docs/cvl/types.html) for the `type` production. See [Expressions](https://docs.certora.com/en/latest/docs/cvl/expr.html) for the `expr` and `function_call` productions.
## [Variable declarations](https://docs.certora.com/en/latest/docs/cvl/statements.html#id19)[](https://docs.certora.com/en/latest/docs/cvl/statements.html#variable-declarations "Link to this heading")
Unlike undefined variables in most programming languages, undefined variables in CVL are a centrally important language feature. If a variable is declared but not defined, the Prover will generate [models](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-model) with every possible value of the undefined variable.
Undefined variables in CVL behave the same way as [rule parameters](https://docs.certora.com/en/latest/docs/cvl/rules.html#rule-overview).
When the Prover reports a counterexample that violates a rule, the values of the variables declared in the rule are displayed in the report. Variables declared in CVL functions are not currently visible in the report.
## [`assert` and `require`](https://docs.certora.com/en/latest/docs/cvl/statements.html#id20)[](https://docs.certora.com/en/latest/docs/cvl/statements.html#assert-and-require "Link to this heading")
The `assert` and `require` commands are similar to the corresponding statements in Solidity. The `require` statement is used to specify the preconditions for a rule, while the `assert` statement is used to specify the expected behavior of contract functions.
During verification, the Prover will ignore any [model](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-model) that causes the `require` expressions to evaluate to false. Unlike Solidity, the `require` statement does not contain a descriptive message, because the Prover will never consider an example where the `require` statement evaluates to `false`.
The `assert` statements define the expected behavior of contract functions. If it is possible to generate a model that causes the `assert` expression to evaluate to `false`, the Prover will construct one of them and report a violation.
Assert conditions may be followed by a message string describing the condition; this message will be included in the reported violation.
Note
Unlike Solidity’s `assert` and `require`, the CVL syntax for `assert` and `require` does not require parentheses around the expression and message.
### [Examples](https://docs.certora.com/en/latest/docs/cvl/statements.html#id21)[](https://docs.certora.com/en/latest/docs/cvl/statements.html#examples "Link to this heading")
```
rulewithdraw_succeeds{
enve;// env represents the bytecode environment passed on every call
// invoke function withdraw and assume that it does not revert
boolsuccess=withdraw(e);// e is passed as an additional argument
assertsuccess,"withdraw must succeed";// verify that withdraw succeeded
}
ruletotalFundsAfterDeposit(uint256amount){
enve;
deposit(e,amount);
uint256userFundsAfter=getFunds(e,e.msg.sender);
uint256totalAfter=getTotalFunds(e);
// Verify that the total funds of the system is at least the current funds of the msg.sender.
asserttotalAfter>=userFundsAfter;
}

```
Copy to clipboard
  * [`assert` example](https://github.com/Certora/Examples/blob/14668d39a6ddc67af349bc5b82f73db73349ef18/CVLByExample/ConstantProductPool/certora/spec/ConstantProductPool.spec#L75)
  * [`require` example](https://github.com/Certora/Examples/blob/14668d39a6ddc67af349bc5b82f73db73349ef18/CVLByExample/ConstantProductPool/certora/spec/ConstantProductPool.spec#L44)


## [`satisfy` statements](https://docs.certora.com/en/latest/docs/cvl/statements.html#id22)[](https://docs.certora.com/en/latest/docs/cvl/statements.html#satisfy-statements "Link to this heading")
A `satisfy` statement is used to check that the rule can be executed in such a way that the `satisfy` statement is reached and that its condition is fulfilled.
We require that each rule ends with either a `satisfy` statement or an `assert` statement.
See [Producing Positive Examples](https://docs.certora.com/en/latest/docs/user-guide/satisfy.html#producing-examples) for an example demonstrating the `satisfy` command.
For each `satisfy` statement that is checked successfully, the Certora verifier will produce a witness for a valid execution of the rule. It will show an execution trace containing values for each input variable and each state variable where all `require` and `satisfy` statements are executed successfully. In case there is no such execution, for example if the `require` statements are already inconsistent or if a Solidity function always reverts, the rule will show as “Violated”.
If the rule contains multiple `satisfy` statements, then all executed `satisfy` statements must hold. However, a `satisfy` statement on a conditional branch that is not executed does not need to hold.
If at least one `satisfy` statement is not satisfiable, an error is reported. If all `satisfy` statements can be fulfilled on at least one path, the rule succeeds.
Note
A success only guarantees that there is some satisfying execution starting in some arbitrary state. It is not possible to check that every possible starting state has an execution that satisfies the condition.
Note
`satisfy` statements are never checked in the same sub-rule with `assert` statements, and they are always checked under [optimistic assumptions](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-optimistic-assumptions). This means that rules without any explicit `assert` statements will not check the [pessimistic assertions](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-pessimistic-assertions), i.e., the implicit assertions that we insert in rules with `assert` statements when at least one of the “optimistic” flags is not set. In order to trigger creation of a sub-rule that contains these checks, users can insert an `assert true` statement into the rule. This assert itself will never be violated, but the sub-rule we create for it will contain all the pessimistic assertions for the program.
  * [`satisfy` example](https://github.com/Certora/Examples/blob/14668d39a6ddc67af349bc5b82f73db73349ef18/CVLByExample/ConstantProductPool/certora/spec/ConstantProductPool.spec#L243)


## [`requireInvariant` statements](https://docs.certora.com/en/latest/docs/cvl/statements.html#id23)[](https://docs.certora.com/en/latest/docs/cvl/statements.html#requireinvariant-statements "Link to this heading")
`requireInvariant` is shorthand for `require` of the expression of the invariant where the invariant parameters have to be substituted with the values/ variables for which the invariant should hold.
  * [`requireInvariant` example](https://github.com/Certora/Examples/blob/14668d39a6ddc67af349bc5b82f73db73349ef18/CVLByExample/ConstantProductPool/certora/spec/ConstantProductPool.spec#L178)


Note
`requireInvariant` is always safe for invariants that have been proved, even in `preserved` blocks; see [Invariants and induction](https://docs.certora.com/en/latest/docs/cvl/invariants.html#invariant-induction) for a detailed explanation.
## [Havoc Statements](https://docs.certora.com/en/latest/docs/cvl/statements.html#id24)[](https://docs.certora.com/en/latest/docs/cvl/statements.html#havoc-statements "Link to this heading")
Havoc statements introduce non-determinism into the contract execution, allowing the SMT solver to choose random values for specific variables. Havoc statements are helpful for modeling uncertainty and verifying a wider range of possible scenarios.
### [Syntax](https://docs.certora.com/en/latest/docs/cvl/statements.html#id25)[](https://docs.certora.com/en/latest/docs/cvl/statements.html#id1 "Link to this heading")
The syntax for a `havoc` statement is as follows:
```
havocidentifier[assumingcondition];

```
Copy to clipboard
  * **`identifier`:** The variable or expression for which non-deterministic values will be chosen.
  * **`condition`:** An optional condition that restricts the possible values for the havoc variable.


### [Usage](https://docs.certora.com/en/latest/docs/cvl/statements.html#id26)[](https://docs.certora.com/en/latest/docs/cvl/statements.html#usage "Link to this heading")
#### [Basic Havoc](https://docs.certora.com/en/latest/docs/cvl/statements.html#id27)[](https://docs.certora.com/en/latest/docs/cvl/statements.html#basic-havoc "Link to this heading")
The basic use of a havoc statement involves introducing non-deterministic values for a specific variable. This is useful when the exact value of a variable is unknown or when exploring various scenarios.
##### [Example:](https://docs.certora.com/en/latest/docs/cvl/statements.html#id28)[](https://docs.certora.com/en/latest/docs/cvl/statements.html#example "Link to this heading")
```
uint256x;
havocx;

```
Copy to clipboard
In this example, the value of variable `x` is chosen randomly by the SMT solver. **Note:** The havoc statement is not really necessary as unassigned values are havoc by default.
#### [Havoc with Condition](https://docs.certora.com/en/latest/docs/cvl/statements.html#id29)[](https://docs.certora.com/en/latest/docs/cvl/statements.html#havoc-with-condition "Link to this heading")
Havoc statements can include a condition that restricts the possible values for the havoc variable. This allows for more fine-grained control over the non-deterministic choices made by the SMT solver.
##### [Example:](https://docs.certora.com/en/latest/docs/cvl/statements.html#id30)[](https://docs.certora.com/en/latest/docs/cvl/statements.html#id2 "Link to this heading")
```
uint256y;
havocyassumingy>10;

```
Copy to clipboard
In this example, the havoc statement introduces non-deterministic values for variable `y`, but only values greater than 10 are considered valid.
**Note:** The above is equivalent to:
```
uint256y;
requirey>0;

```
Copy to clipboard
### [Two-State Contexts: `@old` and `@new`](https://docs.certora.com/en/latest/docs/cvl/statements.html#id31)[](https://docs.certora.com/en/latest/docs/cvl/statements.html#two-state-contexts-old-and-new "Link to this heading")
Two-state contexts, denoted by `@old` and `@new`, are essential when dealing with havoc statements. They provide a mechanism to reference the old and new states of a variable within the havoc statement, allowing for more nuanced control over the non-deterministic choices.
#### [Example:](https://docs.certora.com/en/latest/docs/cvl/statements.html#id32)[](https://docs.certora.com/en/latest/docs/cvl/statements.html#id3 "Link to this heading")
```
havocsumAllBalanceassumingsumAllBalance@new()==sumAllBalance@old()+balance-old_balance;

```
Copy to clipboard
In the given example, the havoc statement introduces non-deterministic values for the variable `sumAllBalance`. The assuming clause adds a condition: the new state of `sumAllBalance` should be the old state plus the change in the balance variable.
`sumAllBalance@new()`: Value in the updated state. `sumAllBalance@old()`: Value in the previous state. `balance - old_balance`: Change in the balance variable.
Note
[Hooks](https://docs.certora.com/en/latest/docs/cvl/hooks.html) will not be triggered for havoc statements. That is, if there is a hook defined on load, or store, of the `sumAllBalance` variable, it will not be triggered from the havoc statement.
### [Advanced Usage: `havoc assuming`](https://docs.certora.com/en/latest/docs/cvl/statements.html#id33)[](https://docs.certora.com/en/latest/docs/cvl/statements.html#advanced-usage-havoc-assuming "Link to this heading")
The `havoc assuming` construct allows introducing non-deterministic choices for variables while imposing specific conditions. This can be particularly useful for modeling complex scenarios where certain constraints must be satisfied.
#### [Example:](https://docs.certora.com/en/latest/docs/cvl/statements.html#id34)[](https://docs.certora.com/en/latest/docs/cvl/statements.html#id4 "Link to this heading")
```
ghostuint256a;
ghostuint256b;
ruleexample(){
havocaassuminga@new<b;
havocbassuminga+b@new==100;
asserta<b&&a+b==100;
}

```
Copy to clipboard
In this example, havoc statements are used to introduce non-deterministic values for ghosts `a` and `b` while ensuring that `a` is less than `b` and their sum is equal to 100.
### [Conclusion](https://docs.certora.com/en/latest/docs/cvl/statements.html#id35)[](https://docs.certora.com/en/latest/docs/cvl/statements.html#conclusion "Link to this heading")
Havoc statements play a critical role in making CVL specifications more expressive and capable of handling uncertainty. They widen the coverage of possible contract behaviors making verification more robust and comprehensive. Understanding two-state contexts (`@old` and `@new`) and the `havoc assuming` construct is useful for harnessing the full power of CVL, in particular when combined with ghosts.
## [Solidity-like Statements](https://docs.certora.com/en/latest/docs/cvl/statements.html#id36)[](https://docs.certora.com/en/latest/docs/cvl/statements.html#solidity-like-statements "Link to this heading")
Solidity-like statements provide a familiar syntax for expressing conditions and behaviors similar to Solidity, These statements enhance the readability and ease of writing specifications by adopting a syntax that resembles Solidity.
### [1. Assert Statement](https://docs.certora.com/en/latest/docs/cvl/statements.html#id37)[](https://docs.certora.com/en/latest/docs/cvl/statements.html#assert-statement "Link to this heading")
#### [Syntax:](https://docs.certora.com/en/latest/docs/cvl/statements.html#id38)[](https://docs.certora.com/en/latest/docs/cvl/statements.html#id5 "Link to this heading")
```
assertcondition;

```
Copy to clipboard
#### [Usage:](https://docs.certora.com/en/latest/docs/cvl/statements.html#id39)[](https://docs.certora.com/en/latest/docs/cvl/statements.html#id6 "Link to this heading")
The `assert` statement is used to assert a condition that must be true during the execution of the contract. If the condition evaluates to false, it will trigger a verification failure.
##### [Example:](https://docs.certora.com/en/latest/docs/cvl/statements.html#id40)[](https://docs.certora.com/en/latest/docs/cvl/statements.html#id7 "Link to this heading")
```
uint256balance;
assertbalance>0;

```
Copy to clipboard
In this example, the `assert` statement ensures that the balance variable is positive.
### [2. Require Statement](https://docs.certora.com/en/latest/docs/cvl/statements.html#id41)[](https://docs.certora.com/en/latest/docs/cvl/statements.html#require-statement "Link to this heading")
#### [Syntax:](https://docs.certora.com/en/latest/docs/cvl/statements.html#id42)[](https://docs.certora.com/en/latest/docs/cvl/statements.html#id8 "Link to this heading")
```
requirecondition;

```
Copy to clipboard
#### [Usage:](https://docs.certora.com/en/latest/docs/cvl/statements.html#id43)[](https://docs.certora.com/en/latest/docs/cvl/statements.html#id9 "Link to this heading")
The `require` statement is similar to the `assert` statement but is used for expressing preconditions that must be satisfied for the execution to continue. Values that make the condition evaluate to false will not be considered as violations of a later `assert` statement or witnesses to a later `satisfy` statement.
##### [Example:](https://docs.certora.com/en/latest/docs/cvl/statements.html#id44)[](https://docs.certora.com/en/latest/docs/cvl/statements.html#id10 "Link to this heading")
```
uint256amount;
requireamount>0;
satisfyamount>=0;

```
Copy to clipboard
Here, the `require` statement ensures that the `amount` must be greater than zero. This means there cannot be a witness of the `satisfy` command with `amount` equal to zero.
### [3. Modeling Reverts in Solidity Calls](https://docs.certora.com/en/latest/docs/cvl/statements.html#id45)[](https://docs.certora.com/en/latest/docs/cvl/statements.html#modeling-reverts-in-solidity-calls "Link to this heading")
The default method of calling Solidity functions within CVL is to assume they do not revert. This behavior can be adjusted with the `@withrevert` modifier. After every Solidity call, even if it is not marked with `@withrevert`, a builtin variable called `lastReverted` is updated according to whether the Solidity call reverted or not.
Note: For calls without `@withrevert`, `lastReverted` is automatically set to to false.
#### [Syntax:](https://docs.certora.com/en/latest/docs/cvl/statements.html#id46)[](https://docs.certora.com/en/latest/docs/cvl/statements.html#id11 "Link to this heading")
```
f@withrevert(args);
assert!lastReverted;

```
Copy to clipboard
In this example, we call to `f` without pruning the reverting paths, and then we assert that the call to `f` did not revert on any given input.
##### [Example:](https://docs.certora.com/en/latest/docs/cvl/statements.html#id47)[](https://docs.certora.com/en/latest/docs/cvl/statements.html#id12 "Link to this heading")
```
uint256limit=100;
uint256value;
requirevalue>limit;
Deposit@withrevert(value);
assertlastReverted,"Expected revert when value exceeds limit";

```
Copy to clipboard
In this example, the `@withrevert` modifier is applied to the `Deposit` function call, which is expected to revert if the `value` exceeds the specified `limit`. The `assert` statement checks whether `lastReverted` is true, ensuring that the contract execution does revert as anticipated when the condition is violated. The error message in the `assert` provides additional context about the expectation.
### [4. Return Statement](https://docs.certora.com/en/latest/docs/cvl/statements.html#id48)[](https://docs.certora.com/en/latest/docs/cvl/statements.html#return-statement "Link to this heading")
#### [Syntax:](https://docs.certora.com/en/latest/docs/cvl/statements.html#id49)[](https://docs.certora.com/en/latest/docs/cvl/statements.html#id13 "Link to this heading")
```
returnexpression;

```
Copy to clipboard
#### [Usage:](https://docs.certora.com/en/latest/docs/cvl/statements.html#id50)[](https://docs.certora.com/en/latest/docs/cvl/statements.html#id14 "Link to this heading")
The `return` statement is used to terminate the execution of a function and return a value. It can only be used in functions to specify the value to be returned.
##### [Example:](https://docs.certora.com/en/latest/docs/cvl/statements.html#id51)[](https://docs.certora.com/en/latest/docs/cvl/statements.html#id15 "Link to this heading")
```
functioncalculateSum(uint256a,uint256b)returns(uint256){
returna+b;
}

```
Copy to clipboard
This example defines a function `calculateSum` that takes two parameters and returns their sum.
### [Conclusion](https://docs.certora.com/en/latest/docs/cvl/statements.html#id52)[](https://docs.certora.com/en/latest/docs/cvl/statements.html#id16 "Link to this heading")
Solidity-like statements in CVL simplify the process of writing specifications by using a syntax that closely resembles Solidity. These statements align with the familiar patterns and structures used in Solidity smart contracts, making it easier for developers and auditors to express and verify the desired behaviors and conditions in a contract. Understanding and using these statements contributes to more readable and expressive CVL specifications.
[ Previous](https://docs.certora.com/en/latest/docs/cvl/expr.html "Expressions") [Next ](https://docs.certora.com/en/latest/docs/cvl/imports.html "Import and Use Statements")
© Copyright 2025, Certora, Inc.
Built with [Sphinx](https://www.sphinx-doc.org/) using a [theme](https://github.com/readthedocs/sphinx_rtd_theme) provided by [Read the Docs](https://readthedocs.org). 
