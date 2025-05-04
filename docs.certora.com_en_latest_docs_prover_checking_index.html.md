[ Certora Prover Documentation ![Logo](https://docs.certora.com/en/latest/_static/Certora_Logo_Black.svg) ](https://docs.certora.com/en/latest/index.html)
Contents
  * [Certora User’s Guide](https://docs.certora.com/en/latest/docs/user-guide/index.html)
  * [The Certora Verification Language](https://docs.certora.com/en/latest/docs/cvl/index.html)
  * [The Certora Prover](https://docs.certora.com/en/latest/docs/prover/index.html)
    * [Introduction](https://docs.certora.com/en/latest/docs/prover/intro.html)
    * [Installation](https://docs.certora.com/en/latest/docs/user-guide/install.html)
    * [Prover Approximations](https://docs.certora.com/en/latest/docs/prover/approx/index.html)
    * [Techniques Used by the Certora Prover](https://docs.certora.com/en/latest/docs/prover/techniques/index.html)
    * [Diagnostic Tools](https://docs.certora.com/en/latest/docs/prover/diagnosis/index.html)
    * [Checking Specifications](https://docs.certora.com/en/latest/docs/prover/checking/index.html)
      * [Rule Sanity Checks](https://docs.certora.com/en/latest/docs/prover/checking/sanity.html)
      * [Coverage Info](https://docs.certora.com/en/latest/docs/prover/checking/coverage-info.html)
      * [Bug Injection](https://docs.certora.com/en/latest/docs/prover/checking/injection.html)
      * [Mutation Testing](https://docs.certora.com/en/latest/docs/prover/checking/mutation.html)
    * [Certora Prover CLI](https://docs.certora.com/en/latest/docs/prover/cli/index.html)
    * [Using the Certora Portal](https://docs.certora.com/en/latest/docs/prover/portal/using.html)
    * [Changelogs](https://docs.certora.com/en/latest/docs/prover/changelog/index.html)
  * [Sunbeam: Verification for Soroban](https://docs.certora.com/en/latest/docs/sunbeam/index.html)
  * [The Certora Solana Prover](https://docs.certora.com/en/latest/docs/solana/index.html)
  * [Gambit: Mutation Generator for Solidity](https://docs.certora.com/en/latest/docs/gambit/index.html)


Additional information
  * [The Certora Equivalence Checker](https://docs.certora.com/en/latest/docs/equiv-check/index.html)
  * [Certora Technology White Paper](https://docs.certora.com/en/latest/docs/whitepaper/index.html)


  * [Index](https://docs.certora.com/en/latest/genindex.html)


[Certora Prover Documentation](https://docs.certora.com/en/latest/index.html)
  * [](https://docs.certora.com/en/latest/index.html)
  * [The Certora Prover](https://docs.certora.com/en/latest/docs/prover/index.html)
  * Checking Specifications
  * [ View page source](https://docs.certora.com/en/latest/_sources/docs/prover/checking/index.md.txt)


# Checking Specifications[](https://docs.certora.com/en/latest/docs/prover/checking/index.html#checking-specifications "Link to this heading")
Verification is only as good as the specifications. Bugs in specifications can prevent the Prover from detecting bugs in the contracts. This chapter describes tools that you can use to help find bugs in your specifications.
Contents
  * [Rule Sanity Checks](https://docs.certora.com/en/latest/docs/prover/checking/sanity.html)
    * [Vacuity checks](https://docs.certora.com/en/latest/docs/prover/checking/sanity.html#vacuity-checks)
    * [Assert tautology checks](https://docs.certora.com/en/latest/docs/prover/checking/sanity.html#assert-tautology-checks)
    * [Trivial invariant checks](https://docs.certora.com/en/latest/docs/prover/checking/sanity.html#trivial-invariant-checks)
    * [Assertion structure checks](https://docs.certora.com/en/latest/docs/prover/checking/sanity.html#assertion-structure-checks)
    * [Redundant require checks](https://docs.certora.com/en/latest/docs/prover/checking/sanity.html#redundant-require-checks)
  * [Coverage Info](https://docs.certora.com/en/latest/docs/prover/checking/coverage-info.html)
    * [Examples](https://docs.certora.com/en/latest/docs/prover/checking/coverage-info.html#examples)
    * [Basic vs. advanced mode](https://docs.certora.com/en/latest/docs/prover/checking/coverage-info.html#basic-vs-advanced-mode)
    * [Completeness](https://docs.certora.com/en/latest/docs/prover/checking/coverage-info.html#completeness)
  * [Bug Injection](https://docs.certora.com/en/latest/docs/prover/checking/injection.html)
  * [Mutation Testing](https://docs.certora.com/en/latest/docs/prover/checking/mutation.html)


[ Previous](https://docs.certora.com/en/latest/docs/prover/diagnosis/index.html "Diagnostic Tools") [Next ](https://docs.certora.com/en/latest/docs/prover/checking/sanity.html "Rule Sanity Checks")
© Copyright 2025, Certora, Inc.
Built with [Sphinx](https://www.sphinx-doc.org/) using a [theme](https://github.com/readthedocs/sphinx_rtd_theme) provided by [Read the Docs](https://readthedocs.org). 
