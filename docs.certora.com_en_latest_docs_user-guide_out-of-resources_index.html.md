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
  * Managing Timeouts and Out of Memory Problems
  * [ View page source](https://docs.certora.com/en/latest/_sources/docs/user-guide/out-of-resources/index.md.txt)


# Managing Timeouts and Out of Memory Problems[](https://docs.certora.com/en/latest/docs/user-guide/out-of-resources/index.html#managing-timeouts-and-out-of-memory-problems "Link to this heading")
In this chapter, we describe how to diagnose and remedy when the Certora Prover ran out of time or out of memory.
Out-of-memory problems are signified by an `Extremely low available memory` message in the Global Problems tab of the Prover reports, see [Out of memory problems](https://docs.certora.com/en/latest/docs/user-guide/out-of-resources/memout.html#memout-introduction) for more details. Timeouts are signified either by a `Global timeout reached` message in the Global Problems tab, if the whole Prover job timed out, or by an orange clock symbol next to the rule, if that particular rule timed out, see [Timeouts](https://docs.certora.com/en/latest/docs/user-guide/out-of-resources/timeout.html#timeouts-introduction) for more details.
  * [Out of memory problems](https://docs.certora.com/en/latest/docs/user-guide/out-of-resources/memout.html)
    * [General indicators](https://docs.certora.com/en/latest/docs/user-guide/out-of-resources/memout.html#general-indicators)
    * [Reducing memory usage](https://docs.certora.com/en/latest/docs/user-guide/out-of-resources/memout.html#reducing-memory-usage)
      * [High memory usage of SMT solvers](https://docs.certora.com/en/latest/docs/user-guide/out-of-resources/memout.html#high-memory-usage-of-smt-solvers)
  * [Timeouts](https://docs.certora.com/en/latest/docs/user-guide/out-of-resources/timeout.html)
    * [Classification of Timeouts](https://docs.certora.com/en/latest/docs/user-guide/out-of-resources/timeout.html#classification-of-timeouts)
    * [Identifying timeout causes](https://docs.certora.com/en/latest/docs/user-guide/out-of-resources/timeout.html#timeout-causes)
      * [Complexity feedback from Certora Prover](https://docs.certora.com/en/latest/docs/user-guide/out-of-resources/timeout.html#complexity-feedback-from-certora-prover)
        * [Difficulty statistics](https://docs.certora.com/en/latest/docs/user-guide/out-of-resources/timeout.html#difficulty-statistics)
        * [Timeout TAC reports](https://docs.certora.com/en/latest/docs/user-guide/out-of-resources/timeout.html#timeout-tac-reports)
        * [Finding timeout causes through modularization](https://docs.certora.com/en/latest/docs/user-guide/out-of-resources/timeout.html#finding-timeout-causes-through-modularization)
          * [Sanity rules](https://docs.certora.com/en/latest/docs/user-guide/out-of-resources/timeout.html#sanity-rules)
          * [Library contracts](https://docs.certora.com/en/latest/docs/user-guide/out-of-resources/timeout.html#library-contracts)
    * [Timeout prevention](https://docs.certora.com/en/latest/docs/user-guide/out-of-resources/timeout.html#timeout-prevention)
      * [Running rules individually](https://docs.certora.com/en/latest/docs/user-guide/out-of-resources/timeout.html#running-rules-individually)
      * [Detect candidates for summarization](https://docs.certora.com/en/latest/docs/user-guide/out-of-resources/timeout.html#detect-candidates-for-summarization)
        * [Example usage](https://docs.certora.com/en/latest/docs/user-guide/out-of-resources/timeout.html#example-usage)
      * [Dealing with different kinds of complexity](https://docs.certora.com/en/latest/docs/user-guide/out-of-resources/timeout.html#dealing-with-different-kinds-of-complexity)
        * [Dealing with a high path count](https://docs.certora.com/en/latest/docs/user-guide/out-of-resources/timeout.html#dealing-with-a-high-path-count)
          * [Path explosion](https://docs.certora.com/en/latest/docs/user-guide/out-of-resources/timeout.html#path-explosion)
          * [Mitigation approaches](https://docs.certora.com/en/latest/docs/user-guide/out-of-resources/timeout.html#mitigation-approaches)
        * [Dealing with nonlinear arithmetic](https://docs.certora.com/en/latest/docs/user-guide/out-of-resources/timeout.html#dealing-with-nonlinear-arithmetic)
        * [Dealing with high memory (or storage) complexity](https://docs.certora.com/en/latest/docs/user-guide/out-of-resources/timeout.html#dealing-with-high-memory-or-storage-complexity)
          * [Passing complex structs](https://docs.certora.com/en/latest/docs/user-guide/out-of-resources/timeout.html#passing-complex-structs)
          * [Memory and storage in inline assembly](https://docs.certora.com/en/latest/docs/user-guide/out-of-resources/timeout.html#memory-and-storage-in-inline-assembly)
      * [Modular verification](https://docs.certora.com/en/latest/docs/user-guide/out-of-resources/timeout.html#modular-verification)
        * [Library-based systems](https://docs.certora.com/en/latest/docs/user-guide/out-of-resources/timeout.html#library-based-systems)
      * [Command line options](https://docs.certora.com/en/latest/docs/user-guide/out-of-resources/timeout.html#command-line-options)
        * [`--prover_args '-destructiveOptimizations enable'`](https://docs.certora.com/en/latest/docs/user-guide/out-of-resources/timeout.html#prover-args-destructiveoptimizations-enable)
  * [Timeouts in Certora Prover - Theoretical Background](https://docs.certora.com/en/latest/docs/user-guide/out-of-resources/timeout-theory.html)
    * [Complexity of the SMT problem](https://docs.certora.com/en/latest/docs/user-guide/out-of-resources/timeout-theory.html#complexity-of-the-smt-problem)
    * [Usefulness of worst-case intractable problems](https://docs.certora.com/en/latest/docs/user-guide/out-of-resources/timeout-theory.html#usefulness-of-worst-case-intractable-problems)
    * [Further reading](https://docs.certora.com/en/latest/docs/user-guide/out-of-resources/timeout-theory.html#further-reading)


[ Previous](https://docs.certora.com/en/latest/docs/user-guide/multicontract/index.html "Working with Multiple Contracts") [Next ](https://docs.certora.com/en/latest/docs/user-guide/out-of-resources/memout.html "Out of memory problems")
© Copyright 2025, Certora, Inc.
Built with [Sphinx](https://www.sphinx-doc.org/) using a [theme](https://github.com/readthedocs/sphinx_rtd_theme) provided by [Read the Docs](https://readthedocs.org). 
