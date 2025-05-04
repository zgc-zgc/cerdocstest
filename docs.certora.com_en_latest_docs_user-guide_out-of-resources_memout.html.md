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
        * [General indicators](https://docs.certora.com/en/latest/docs/user-guide/out-of-resources/memout.html#general-indicators)
        * [Reducing memory usage](https://docs.certora.com/en/latest/docs/user-guide/out-of-resources/memout.html#reducing-memory-usage)
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
  * [Managing Timeouts and Out of Memory Problems](https://docs.certora.com/en/latest/docs/user-guide/out-of-resources/index.html)
  * Out of memory problems
  * [ View page source](https://docs.certora.com/en/latest/_sources/docs/user-guide/out-of-resources/memout.md.txt)


# Out of memory problems[](https://docs.certora.com/en/latest/docs/user-guide/out-of-resources/memout.html#out-of-memory-problems "Link to this heading")
In this section, we show how to diagnose and remedy out-of-memory problems. Since the remediation of these problems is often similar to that of certain kinds of timeouts, this section is kept short and links to the corresponding places in the documentation on timeout prevention.
## General indicators[](https://docs.certora.com/en/latest/docs/user-guide/out-of-resources/memout.html#general-indicators "Link to this heading")
When the free memory drops below a certain threshold, the Prover issues the following warning to the “General Problems” panel: `Extremely low available memory`.
This warning might occasionally not be conclusive: the JVM is sometimes able to clean up enough memory on-demand to avert any crashes, or the memory might be just enough. It might also not show up although the job fails due to insufficient memory, e.g., if a single allocation that is greater than the warning threshold fails. Both cases are expected to be rare.
## Reducing memory usage[](https://docs.certora.com/en/latest/docs/user-guide/out-of-resources/memout.html#reducing-memory-usage "Link to this heading")
In most cases, high memory usage and long running times go hand in hand and thus [Timeouts](https://docs.certora.com/en/latest/docs/user-guide/out-of-resources/timeout.html#timeouts-introduction) is applicable for out-of-memory issues as well.
There are a number of ways that can help avoiding memory exhaustion, either by
  * [checking fewer rules](https://docs.certora.com/en/latest/docs/user-guide/out-of-resources/timeout.html#timeout-single-rule),
  * [modularizing the verification](https://docs.certora.com/en/latest/docs/user-guide/out-of-resources/timeout.html#library-timeouts), or
  * fine-tuning [which SMT solvers are run](https://docs.certora.com/en/latest/docs/user-guide/out-of-resources/memout.html#memout-smt-portfolio).


Furthermore, there is a number of [heuristic options](https://docs.certora.com/en/latest/docs/user-guide/out-of-resources/timeout.html#timeout-cli-options) that sometimes help to in reducing memory usage in some way or another.
### High memory usage of SMT solvers[](https://docs.certora.com/en/latest/docs/user-guide/out-of-resources/memout.html#high-memory-usage-of-smt-solvers "Link to this heading")
As discussed in [Dealing with nonlinear arithmetic](https://docs.certora.com/en/latest/docs/user-guide/out-of-resources/timeout.html#high-nonlinear-op-count), using different SMT solvers or changing their order is sometimes beneficial. It is important to keep in mind that for out-of-memory issues, simply removing some solvers rarely helps, as the maximum memory usage needs to be reduced. Roughly speaking, this technique only helps if there are fewer calls to the SMT solvers than there are CPU cores available or if a particular solver or solver configuration uses much more memory than the other solvers in this case. Otherwise, reducing the portfolio enables the Prover to run more rules in parallel only when the number of solvers running - and competing for memory - at any given time remains the same.
[ Previous](https://docs.certora.com/en/latest/docs/user-guide/out-of-resources/index.html "Managing Timeouts and Out of Memory Problems") [Next ](https://docs.certora.com/en/latest/docs/user-guide/out-of-resources/timeout.html "Timeouts")
© Copyright 2025, Certora, Inc.
Built with [Sphinx](https://www.sphinx-doc.org/) using a [theme](https://github.com/readthedocs/sphinx_rtd_theme) provided by [Read the Docs](https://readthedocs.org). 
