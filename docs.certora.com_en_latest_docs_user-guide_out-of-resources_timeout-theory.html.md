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
      * [Out of memory problems](https://docs.certora.com/en/latest/docs/user-guide/out-of-resources/memout.html)
      * [Timeouts](https://docs.certora.com/en/latest/docs/user-guide/out-of-resources/timeout.html)
      * [Timeouts in Certora Prover - Theoretical Background](https://docs.certora.com/en/latest/docs/user-guide/out-of-resources/timeout-theory.html)
        * [Complexity of the SMT problem](https://docs.certora.com/en/latest/docs/user-guide/out-of-resources/timeout-theory.html#complexity-of-the-smt-problem)
        * [Usefulness of worst-case intractable problems](https://docs.certora.com/en/latest/docs/user-guide/out-of-resources/timeout-theory.html#usefulness-of-worst-case-intractable-problems)
        * [Further reading](https://docs.certora.com/en/latest/docs/user-guide/out-of-resources/timeout-theory.html#further-reading)
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
  * [Managing Timeouts and Out of Memory Problems](https://docs.certora.com/en/latest/docs/user-guide/out-of-resources/index.html)
  * Timeouts in Certora Prover - Theoretical Background
  * [ View page source](https://docs.certora.com/en/latest/_sources/docs/user-guide/out-of-resources/timeout-theory.md.txt)


# Timeouts in Certora Prover - Theoretical Background[](https://docs.certora.com/en/latest/docs/user-guide/out-of-resources/timeout-theory.html#timeouts-in-certora-prover-theoretical-background "Link to this heading")
This section will discuss some theoretical background of timeouts in the Certora Prover. We try to answer questions like “Why do you build a tool that times out?” and “Will there be an automatic program verifier that never times out?”. For more practical advice on timeout prevention, please consult the other parts of our documentation on [managing timeouts](https://docs.certora.com/en/latest/docs/user-guide/out-of-resources/index.html).
## Complexity of the SMT problem[](https://docs.certora.com/en/latest/docs/user-guide/out-of-resources/timeout-theory.html#complexity-of-the-smt-problem "Link to this heading")
As the [white paper](https://docs.certora.com/en/latest/docs/whitepaper/index.html#white-paper) describes, the Certora Prover is roughly similar in architecture to a compiler. However, instead of executables, the Certora Prover outputs [SMT](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-SMT) formulas. These formulas are then sent to an SMT solver, and the result is translated back to a counterexample call trace or a “Not Violated” result.
All SMT solvers share a general architecture. At the center of an SMT solver, there is a SAT solver. The SAT solver operates on a Boolean abstraction of the input formula, and communicates with theory solvers to refine the abstraction according to the theories used by the formula. The problem of solving propositional formulas (aka SAT) is famously NP-complete. In practice, this means that there are classes of propositional formulas for which all known SAT solvers show exponential run-time behavior. Exponential running time is usually equated with intractability (“we have an algorithm, but it’s impractical because it runs too long”). Most of the theories involved are at least NP-complete, already in their conjunctive fragments (which SMT theory solvers use). In fact, with the addition of nonlinear integer arithmetic, the SMT problem is undecidable, meaning that there is no algorithm that can correctly solve all possible formulas.
## Usefulness of worst-case intractable problems[](https://docs.certora.com/en/latest/docs/user-guide/out-of-resources/timeout-theory.html#usefulness-of-worst-case-intractable-problems "Link to this heading")
When seeing the complexity results of the previous section, it is easy to give up on the problems of SAT and SMT. Indeed, there were long periods in computer science history when SAT was considered unsolvable. However, it is important to understand that these complexity results describe the worst case behavior. It turns out that there is a large class of formulas where SAT is tractable, even on inputs with millions of variables, and SAT solvers have been used with great success in industries like chip design for decades now.
This means that timeouts can happen when using Certora Prover, but there are often slight variations on the input that do not impact the property being proven and make the problem tractable. This practice is likely to require experience, which we collect in the [Timeout prevention](https://docs.certora.com/en/latest/docs/user-guide/out-of-resources/timeout.html#timeout-prevention) section.
We can use the parts of an SMT solver that we discussed before for some intuition on different kinds of complexity explosions.
Difficulty | Solver parts  
---|---  
Path count | SAT  
Storage/memory | SAT  
Arithmetic | LIA / NIA  
Since control flow is encoded into Boolean logic by the Certora Prover, it weighs most heavily on the SAT-solving part of the SMT solver. Storage or Memory accesses lead to case splits, which are also Boolean in nature. On the other hand, arithmetic is resolved by specialized solvers; different algorithms are required for the linear and the nonlinear cases.
## Further reading[](https://docs.certora.com/en/latest/docs/user-guide/out-of-resources/timeout-theory.html#further-reading "Link to this heading")
There is a large body of literature on the topics of logic, complexity, and SMT. Here are some links as an entry point for further reading:
The Wikipedia articles on [SMT](https://en.wikipedia.org/wiki/Satisfiability_modulo_theories) and the more basic problem known as [SAT](https://en.wikipedia.org/wiki/Boolean_satisfiability_problem) give an overview of the fundamentals of these problems and the existing solving algorithms.
[Programming Z3](https://theory.stanford.edu/~nikolaj/programmingz3.html) provides a guide to the z3 SMT solver and a good overview of its architecture and components, including some algorithms and further references.
[ Previous](https://docs.certora.com/en/latest/docs/user-guide/out-of-resources/timeout.html "Timeouts") [Next ](https://docs.certora.com/en/latest/docs/user-guide/gaps.html "Understanding gaps between high and low level code")
© Copyright 2025, Certora, Inc.
Built with [Sphinx](https://www.sphinx-doc.org/) using a [theme](https://github.com/readthedocs/sphinx_rtd_theme) provided by [Read the Docs](https://readthedocs.org). 
