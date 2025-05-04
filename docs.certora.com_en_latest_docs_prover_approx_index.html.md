[ Certora Prover Documentation ![Logo](https://docs.certora.com/en/latest/_static/Certora_Logo_Black.svg) ](https://docs.certora.com/en/latest/index.html)
Contents
  * [Certora User’s Guide](https://docs.certora.com/en/latest/docs/user-guide/index.html)
  * [The Certora Verification Language](https://docs.certora.com/en/latest/docs/cvl/index.html)
  * [The Certora Prover](https://docs.certora.com/en/latest/docs/prover/index.html)
    * [Introduction](https://docs.certora.com/en/latest/docs/prover/intro.html)
    * [Installation](https://docs.certora.com/en/latest/docs/user-guide/install.html)
    * [Prover Approximations](https://docs.certora.com/en/latest/docs/prover/approx/index.html)
      * [Loop Unrolling](https://docs.certora.com/en/latest/docs/prover/approx/loops.html)
      * [Method Summarization](https://docs.certora.com/en/latest/docs/prover/approx/summarization.html)
      * [Harnessing](https://docs.certora.com/en/latest/docs/prover/approx/harnessing.html)
      * [Modeling of Hashing in the Certora Prover](https://docs.certora.com/en/latest/docs/prover/approx/hashing.html)
      * [Quantifier Grounding](https://docs.certora.com/en/latest/docs/prover/approx/grounding.html)
    * [Techniques Used by the Certora Prover](https://docs.certora.com/en/latest/docs/prover/techniques/index.html)
    * [Diagnostic Tools](https://docs.certora.com/en/latest/docs/prover/diagnosis/index.html)
    * [Checking Specifications](https://docs.certora.com/en/latest/docs/prover/checking/index.html)
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
  * Prover Approximations
  * [ View page source](https://docs.certora.com/en/latest/_sources/docs/prover/approx/index.md.txt)


# Prover Approximations[](https://docs.certora.com/en/latest/docs/prover/approx/index.html#prover-approximations "Link to this heading")
In order to check programs in an acceptable amount of time, the Prover simplifies the code being verified. This section describes the mechanisms for simplification.
Warning
The approximations described in this section may be [underapproximation](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-underapproximation)s, meaning that they can cause real bugs to be overlooked by the Prover.
  * [Loop Unrolling](https://docs.certora.com/en/latest/docs/prover/approx/loops.html)
  * [Method Summarization](https://docs.certora.com/en/latest/docs/prover/approx/summarization.html)
    * [Overview](https://docs.certora.com/en/latest/docs/prover/approx/summarization.html#overview)
    * [How Summarization Helps Solvers](https://docs.certora.com/en/latest/docs/prover/approx/summarization.html#how-summarization-helps-solvers)
    * [Syntax](https://docs.certora.com/en/latest/docs/prover/approx/summarization.html#syntax)
    * [Example: Summarization for a complex function](https://docs.certora.com/en/latest/docs/prover/approx/summarization.html#example-summarization-for-a-complex-function)
    * [Important Considerations](https://docs.certora.com/en/latest/docs/prover/approx/summarization.html#important-considerations)
    * [Summary](https://docs.certora.com/en/latest/docs/prover/approx/summarization.html#summary)
  * [Harnessing](https://docs.certora.com/en/latest/docs/prover/approx/harnessing.html)
    * [Example:](https://docs.certora.com/en/latest/docs/prover/approx/harnessing.html#example)
      * [unit test internal functions](https://docs.certora.com/en/latest/docs/prover/approx/harnessing.html#unit-test-internal-functions)
      * [define complex functionally (view/pure)](https://docs.certora.com/en/latest/docs/prover/approx/harnessing.html#define-complex-functionally-view-pure)
  * [Modeling of Hashing in the Certora Prover](https://docs.certora.com/en/latest/docs/prover/approx/hashing.html)
    * [Introduction](https://docs.certora.com/en/latest/docs/prover/approx/hashing.html#introduction)
    * [Modeling the Keccak function (bounded case)](https://docs.certora.com/en/latest/docs/prover/approx/hashing.html#modeling-the-keccak-function-bounded-case)
      * [Examples (Imprecision of Modeling)](https://docs.certora.com/en/latest/docs/prover/approx/hashing.html#examples-imprecision-of-modeling)
      * [Modeling does not account for individual values of the Keccak function](https://docs.certora.com/en/latest/docs/prover/approx/hashing.html#modeling-does-not-account-for-individual-values-of-the-keccak-function)
      * [Modeling does not account for ordering](https://docs.certora.com/en/latest/docs/prover/approx/hashing.html#modeling-does-not-account-for-ordering)
      * [Constants in code vs hashes](https://docs.certora.com/en/latest/docs/prover/approx/hashing.html#constants-in-code-vs-hashes)
    * [Hashing of unbounded data](https://docs.certora.com/en/latest/docs/prover/approx/hashing.html#hashing-of-unbounded-data)
      * [Examples for Unbounded Hashing](https://docs.certora.com/en/latest/docs/prover/approx/hashing.html#examples-for-unbounded-hashing)
    * [Background: The Solidity Storage Model](https://docs.certora.com/en/latest/docs/prover/approx/hashing.html#background-the-solidity-storage-model)
    * [Conclusion](https://docs.certora.com/en/latest/docs/prover/approx/hashing.html#conclusion)
  * [Quantifier Grounding](https://docs.certora.com/en/latest/docs/prover/approx/grounding.html)
    * [How grounding works](https://docs.certora.com/en/latest/docs/prover/approx/grounding.html#how-grounding-works)
    * [Limitations on grounding](https://docs.certora.com/en/latest/docs/prover/approx/grounding.html#limitations-on-grounding)
      * [Alternating Quantifiers](https://docs.certora.com/en/latest/docs/prover/approx/grounding.html#alternating-quantifiers)
      * [Recursion](https://docs.certora.com/en/latest/docs/prover/approx/grounding.html#recursion)
      * [Variables must be arguments](https://docs.certora.com/en/latest/docs/prover/approx/grounding.html#variables-must-be-arguments)
      * [Double Polarity](https://docs.certora.com/en/latest/docs/prover/approx/grounding.html#double-polarity)


[ Previous](https://docs.certora.com/en/latest/docs/prover/intro.html "Introduction") [Next ](https://docs.certora.com/en/latest/docs/prover/approx/loops.html "Loop Unrolling")
© Copyright 2025, Certora, Inc.
Built with [Sphinx](https://www.sphinx-doc.org/) using a [theme](https://github.com/readthedocs/sphinx_rtd_theme) provided by [Read the Docs](https://readthedocs.org). 
