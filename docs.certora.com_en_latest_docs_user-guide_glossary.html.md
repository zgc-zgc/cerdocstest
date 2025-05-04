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
  * Glossary
  * [ View page source](https://docs.certora.com/en/latest/_sources/docs/user-guide/glossary.md.txt)


# Glossary[](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#glossary "Link to this heading") 

axiom[](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-axiom "Link to this term")
    
a statement accepted as true without proof. 

call trace[](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-call-trace "Link to this term")
    
A call trace is the Prover’s visualization of either a [counterexample](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-counterexample) or a [witness example](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-witness-example).
A call trace illustrates a rule execution that leads up to the violation of an `assert` statement or the fulfillment of a `satisfy` statement. The trace is a sequence of commands in the rule (or in the contracts the rule was calling into), starting at the beginning of the rule and ending with the violated `assert` or fulfilled `satisfy` statement. In addition to the commands, the call trace also does a best effort at showing information about the program state at each point in the execution. It contains information about the state of global variables at crucial points as well as the values of call parameters, return values, and more.
If a call trace exists, it can be found in the “Call Trace” tab in the report after selecting the corresponding (sub-)rule. 

CFG[](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-CFG "Link to this term")


control flow graph[](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-control-flow-graph "Link to this term")


control flow path[](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-control-flow-path "Link to this term")
    
Control flow graphs (short: CFGs) are a program representation that illustrates in which order the program’s instructions are processed during program execution. The nodes in a control flow graph represent single non-branching sequences of commands. The edges in a control flow graph represent the possibility of control passing from the last command of the source node to the first command of the target node. For instance, an `if`-statement in the program will lead to a branching, i.e., a node with two outgoing edges, in the control flow graph. A CVL rule can be seen as a program with some extra “assert” commands, thus a rule has a CFG like regular programs. The Certora Prover’s [TAC reports](https://docs.certora.com/en/latest/docs/prover/diagnosis/index.html#tac-reports) contain a control flow graph of the [TAC](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-TAC) intermediate representation of each given CVL rule. The control flow paths are the paths from source to sink in a given CFG. In general (and in practice) the number of control flow paths grows exponentially with the size of the CFG. This is known as the path explosion problem. Further reading: [Wikipedia: Control-flow graph](https://en.wikipedia.org/wiki/Control-flow_graph) [Wikipedia: Path explosion problem](https://en.wikipedia.org/wiki/Path_explosion) 

environment[](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-environment "Link to this term")
    
The environment of a method call refers to the global variables that solidity provides, including `msg`, `block`, and `tx`. CVL represents these variables in a structure of type [env](https://docs.certora.com/en/latest/docs/cvl/types.html#env). The environment does _not_ include the contract state or the state of other contracts — these are referred to as the [storage](https://docs.certora.com/en/latest/docs/cvl/types.html#storage-type). 

EVM[](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-EVM "Link to this term")


Ethereum Virtual Machine[](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-Ethereum-Virtual-Machine "Link to this term")


EVM bytecode[](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-EVM-bytecode "Link to this term")
    
EVM is short for Ethereum Virtual Machine. EVM bytecode is one of the source languages that the Certora Prover internally can take as input for verification. It is produced by the Solidity and Vyper compilers, among others. For details on what the EVM is and how it works, the following links provide good entry points. [Official documentation](https://ethereum.org/en/developers/docs/evm/), [Wikipedia](https://en.wikipedia.org/wiki/Ethereum#Virtual_machine) 

EVM memory[](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-EVM-memory "Link to this term")


EVM storage[](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-EVM-storage "Link to this term")
    
The [EVM](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-EVM) has two major concepts of memory, called _memory_ and _storage_. In brief, memory variables keep data only for the duration of a single EVM transaction, while storage variables are stored persistently in the Ethereum blockchain. [Official documentation](https://ethereum.org/en/developers/docs/smart-contracts/anatomy) 

havoc[](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-havoc "Link to this term")
    
Havoc means that variables are assigned values chosen non-deterministically. A havoc happens in two cases: the first, at the beginning of the rule all variables “havoced”. The second, during certain events when the Certora Prover should assume that some variables can change in an unknown way. For example, an external function on an unknown contract may have an arbitrary effect on the state of a third contract. In this case, we also say that the variable was “havoced”. See [Havoc summaries: HAVOC_ALL and HAVOC_ECF](https://docs.certora.com/en/latest/docs/cvl/methods.html#havoc-summary) and [Havoc Statements](https://docs.certora.com/en/latest/docs/cvl/statements.html#havoc-stmt) for more details. 

hyperproperty[](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-hyperproperty "Link to this term")
    
A hyperproperty describes a relationship between two hypothetical sequences of operations starting from the same initial state. For example, a statement like “two small deposits will have the same effect as one large deposit” is a hyperproperty. See [The storage type](https://docs.certora.com/en/latest/docs/cvl/types.html#storage-type) for more details. 

invariant[](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-invariant "Link to this term")
    
An invariant (or representation invariant) is a property of the contract state that is expected to hold between invocations of contract methods. See [Invariants](https://docs.certora.com/en/latest/docs/cvl/invariants.html#invariants). 

model[](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-model "Link to this term")


example[](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-example "Link to this term")


counterexample[](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-counterexample "Link to this term")


witness example[](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-witness-example "Link to this term")
    
We use the terms “model” and “example” interchangeably. In the context of a CVL rule, they refer to an assignment of values to all of the CVL variables and contract storage that either violates an `assert` statement or fulfills a `satisfy` statement. In the `assert` case, we also call the model a “counterexample”. In the `satisfy` case, we also call the model “witness example”. See [Overview](https://docs.certora.com/en/latest/docs/cvl/rules.html#rule-overview). In the context of [SMT solver](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-SMT-solver)s, a model is a valuation of the logical constants and uninterpreted functions in the input formula that makes the formula evaluate to `true`, also see [SAT result](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-SAT-result). 

linear arithmetic[](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-linear-arithmetic "Link to this term")


nonlinear arithmetic[](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-nonlinear-arithmetic "Link to this term")
    
An arithmetic expression is called linear if it consists only of additions, subtractions, and multiplications by constant. Division and modulo where the second parameter is a constant are also linear arithmetic. Examples for linear expressions are `x * 3`, `x / 3`, `5 * (x + 3 * y)`. Every arithmetic expression that is not linear is nonlinear. Examples for nonlinear expressions are `x * y`, `x * (1 + y)`, `x * x`, `3 / x`, `3 ^ x`. 

overapproximation[](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-overapproximation "Link to this term")


underapproximation[](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-underapproximation "Link to this term")
    
Sometimes it is useful to replace a complex piece of code with something simpler that is easier to reason about. If the approximation includes all of the possible behaviors of the original code (and possibly others), it is called an “overapproximation”; if it does not then it is called an “underapproximation”.
Example: A [NONDET](https://docs.certora.com/en/latest/docs/cvl/methods.html#view-summary) summary is an overapproximation because every possible value that the original implementation could return is considered by the Certora Prover, while an [ALWAYS](https://docs.certora.com/en/latest/docs/cvl/methods.html#view-summary) summary is an underapproximation if the summarized method could return more than one value.
Proofs on overapproximated programs are [sound](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-sound), but there may be spurious [counterexample](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-counterexample)s caused by behavior that the original code did not exhibit. Underapproximations are more dangerous because a property that is successfully verified on the underapproximation may not hold on the approximated code. 

optimistic assumptions[](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-optimistic-assumptions "Link to this term")


pessimistic assertions[](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-pessimistic-assertions "Link to this term")
    
Some input programs contain constructs that the Prover can only handle in an approximative way. This approximation entails that the Prover will disregard some specific parts of the programs behavior, like for example the behavior induced by a loop being unrolled beyond a fixed number of times. For each of these constructs the Prover provides a flag controlling whether it should handle them optimistically or pessimistically. (See the links at the end of this paragraph for examples of “optimistic” flags.)
In pessimistic mode (which is the default) _pessimistic assertions_ are inserted into the program that check whether there is any behavior that needs to be approximated, for instance whether loops are present with bounds exceeding [loop_iter](https://docs.certora.com/en/latest/docs/prover/cli/options.html#loop-iter). If this is the case, the rule will fail with a corresponding message.
In optimistic mode, instead of the assertions, _optimistic assumptions_ are introduced in each of the places where an approximation happens. Each assumption excludes the relevant behavior from checking for one occurrence of the problematic construct, e.g., for each loop.
For a list of all “optimistic” settings see [CLI Options](https://docs.certora.com/en/latest/docs/prover/cli/options.html#prover-cli-options). Examples include [optimistic_hashing](https://docs.certora.com/en/latest/docs/prover/cli/options.html#optimistic-hashing), [optimistic_loop](https://docs.certora.com/en/latest/docs/prover/cli/options.html#optimistic-loop), [optimistic_summary_recursion](https://docs.certora.com/en/latest/docs/prover/cli/options.html#optimistic-summary-recursion), and more. Also see [Prover Approximations](https://docs.certora.com/en/latest/docs/prover/approx/index.html#prover-approximations) for more background on some of the approximations. 

parametric rule[](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-parametric-rule "Link to this term")
    
A parametric rule is a rule that calls an ambiguous method, either using a method variable, or using an overloaded function name. The Certora Prover will generate a separate report for each possible instantiation of the method. See [Parametric rules](https://docs.certora.com/en/latest/docs/cvl/rules.html#parametric-rules) for more information. 

quantifier[](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-quantifier "Link to this term")


quantified expression[](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-quantified-expression "Link to this term")
    
The symbols `forall` and `exist` are sometimes referred to as _quantifiers_ , and expressions of the form `forall type v . e` and `exist type v . e` are referred to as _quantified expressions_. See [Extended logical operations](https://docs.certora.com/en/latest/docs/cvl/expr.html#logic-exprs) for details about quantifiers in CVL. 

receiveOrFallback[](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-receiveOrFallback "Link to this term")
    
A special function we introduce in every contract to model the behavior of solidity for calls with no data or that do not resolve to any contract function. It will call the receive function if present for calls with no data, and otherwise the fallback function. Shows up in the parametric rules or invariants, as well as in the call trace for such calls, written `<receiveOrFallback>()`. See also [Solidity Documentation](https://docs.soliditylang.org/en/latest/contracts.html#fallback-function). 

sanity[](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-sanity "Link to this term")


SAT[](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-SAT "Link to this term")


UNSAT[](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-UNSAT "Link to this term")


SAT result[](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-SAT-result "Link to this term")


UNSAT result[](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-UNSAT-result "Link to this term")
    
 _SAT_ and _UNSAT_ are the results that an [SMT solver](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-SMT-solver) returns on a successful run (i.e. not a timeout). SAT means that the input formula is satisfiable and a [model](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-model) has been found. UNSAT means that the input formula is unsatisfiable (and thus there is no model for it). Within the Certora Prover, what SAT means depends on the type of rule being checked: For an `assert` rule, SAT means the rule is violated and the SMT model corresponds to a counterexample. For a `satisfy` rule, SAT means the rule is not violated and the SMT model corresponds to a witness example. Conversely, UNSAT means that an `assert` is never violated or a `satisfy` never fulfilled respectively. See also [Overview](https://docs.certora.com/en/latest/docs/cvl/rules.html#rule-overview). 

(scene)=[](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-scene "Link to this term")


scene[](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-0 "Link to this term")
    
The _scene_ refers to the set of contract instances that the Certora Prover knows about. 

SMT[](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-SMT "Link to this term")


SMT solver[](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-SMT-solver "Link to this term")
    
“SMT” is short for “Satisfiability Modulo Theories”. An SMT solver takes as input a formula in predicate logic and returns whether the formula is satisfiable (short “SAT”) or unsatisfiable (short: “UNSAT”). The “Modulo Theory” part means that the solver assumes a meaning for certain symbols in the formula. For instance the theory of integer arithmetic stipulates that the symbols `+`, `-`, `*`, etc. have their regular everyday mathematical meaning. When the formula is satisfiable, the SMT solver can also return a model for the formula. I.e. an assignment of the formula’s variables that makes the formula evaluate to “true”. For instance, on the formula “x > 5 /\ x = y * y”, a solver will return SAT, and produce any valuation where x is the square of an integer and larger than 5, and y is the root of x. Further reading: [Wikipedia](https://en.wikipedia.org/wiki/Satisfiability_modulo_theories) 

sound[](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-sound "Link to this term")


unsound[](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-unsound "Link to this term")
    
Soundness means that any rule violations in the code being verified are guaranteed to be reported by the Certora Prover. Unsound approximations such as loop unrolling or certain kinds of harnessing may cause real bugs to be missed by the Prover, and should therefore be used with caution. See [Prover Approximations](https://docs.certora.com/en/latest/docs/prover/approx/index.html) for more details. 

split[](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-split "Link to this term")


split leaf[](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-split-leaf "Link to this term")


split leaves[](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-split-leaves "Link to this term")
    
Control flow splitting is a technique to speed up verification by splitting the program into smaller parts and verifying them separately. These smaller programs are called splits. Splits that cannot be split further are called split leaves. See [Control flow splitting](https://docs.certora.com/en/latest/docs/prover/techniques/index.html#control-flow-splitting). 

summary[](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-summary "Link to this term")


summarize[](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-summarize "Link to this term")
    
A method summary is a user-provided approximation of the behavior of a contract method. Summaries are useful if the implementation of a method is not available or if the implementation is too complex for the Certora Prover to analyze without timing out. See [The Methods Block](https://docs.certora.com/en/latest/docs/cvl/methods.html) for complete information on different types of method summaries. 

TAC[](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-TAC "Link to this term")
    
TAC (originally short for “three address code”) is an intermediate representation ([Wikipedia](https://en.wikipedia.org/wiki/Intermediate_representation)) used by the Certora Prover. TAC code is kept invisible to the user most of the time, so its details are not in the scope of this documentation. We provide a working understanding, which is helpful for some advanced proving tasks, in the [TAC Reports](https://docs.certora.com/en/latest/docs/prover/diagnosis/index.html#tac-reports) section. 

tautology[](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-tautology "Link to this term")
    
A tautology is a logical statement that is always true. 

vacuous[](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-vacuous "Link to this term")


vacuity[](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-vacuity "Link to this term")
    
A logical statement is _vacuous_ if it is technically true but only because it doesn’t say anything. For example, “every integer that is both greater than 5 and less than 3 is a perfect square” is technically true, but only because there are no numbers that are both greater than 5 and less than 3.
Similarly, a rule or assertion can pass, but only because the `require` statements rule out all of the [model](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-model)s. In this case, the rule doesn’t say anything about the program being verified. The [Rule Sanity Checks](https://docs.certora.com/en/latest/docs/prover/checking/sanity.html) help detect vacuous rules. 

verification condition[](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-verification-condition "Link to this term")
    
The Certora Prover works by translating a program an a specification into a single logical formula that is satisfiable if and only if the program violates the specification. This formula is called a _verification condition_. Usually, a run of the Certora Prover generates many verification conditions. For instance a verification condition is generated for every [parametric rule](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-parametric-rule), and also for each of the sanity checks triggered by [rule_sanity](https://docs.certora.com/en/latest/docs/prover/cli/options.html#rule-sanity). See also [Certora Technology White Paper](https://docs.certora.com/en/latest/docs/whitepaper/index.html#white-paper), [Certora User’s Guide](https://docs.certora.com/en/latest/docs/user-guide/index.html#user-guide). 

wildcard[](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-wildcard "Link to this term")


exact[](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-exact "Link to this term")
    
A methods block entry that explicitly uses `_` as a receiver is a _wildcard entry_ ; all other entries are called _exact entries_. See [The Methods Block](https://docs.certora.com/en/latest/docs/cvl/methods.html).
[ Previous](https://docs.certora.com/en/latest/docs/user-guide/github_highlighting.html "Syntax Highlighting on GitHub") [Next ](https://docs.certora.com/en/latest/docs/cvl/index.html "The Certora Verification Language")
© Copyright 2025, Certora, Inc.
Built with [Sphinx](https://www.sphinx-doc.org/) using a [theme](https://github.com/readthedocs/sphinx_rtd_theme) provided by [Read the Docs](https://readthedocs.org). 
