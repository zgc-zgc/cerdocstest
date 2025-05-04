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
        * [Example:](https://docs.certora.com/en/latest/docs/prover/approx/harnessing.html#example)
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
  * [Prover Approximations](https://docs.certora.com/en/latest/docs/prover/approx/index.html)
  * Harnessing
  * [ View page source](https://docs.certora.com/en/latest/_sources/docs/prover/approx/harnessing.md.txt)


# Harnessing[](https://docs.certora.com/en/latest/docs/prover/approx/harnessing.html#harnessing "Link to this heading")
Occasionally, CVL lacks a feature that is necessary for a complete verification of a contract. We are working to extend the feature set of CVL to cover these cases, but in the mean time we have developed a set of workarounds that we refer to as “harnesses”.
## Example:[](https://docs.certora.com/en/latest/docs/prover/approx/harnessing.html#example "Link to this heading")
Consider a scenario where we want to write a unit test for an internal functions of a contract. The contract serves as a workaround, allowing us to call original functions rather than relying on summarized implementations.
```
contractExampleHarnessingisExampleHarnessingGetter{
constructor(Configurationmemoryconfig)ExampleHarnessingGetter(config){}
// External wrapper for accrueInternal
functioncall_accrueInternal()external{
returnsuper.accrueInternal();
}
// External wrapper for getNowInternal
functioncall_getNowInternal()externalviewreturns(uint40){
returnsuper.getNowInternal();
}
// Compute the n-th power of 10
functionpowerOfTen(uint8n)publicpurereturns(uint64){
returnuint64(uint64(10)**n);
}
}

```
Copy to clipboard
for more details checkout the [source code](https://github.com/Certora/comet/blob/certora/certora/harness/CometHarnessWrappers.sol)
Here’s a brief overview:
### unit test internal functions[](https://docs.certora.com/en/latest/docs/prover/approx/harnessing.html#unit-test-internal-functions "Link to this heading")
`call_accrueInternal` and `call_getNowInternal`: External wrappers facilitating access to internal functions like `accrueInternal` and `getNowInternal`.
### define complex functionally (view/pure)[](https://docs.certora.com/en/latest/docs/prover/approx/harnessing.html#define-complex-functionally-view-pure "Link to this heading")
`powerOfTen`: A utility function to compute the n-th power of 10.
[ Previous](https://docs.certora.com/en/latest/docs/prover/approx/summarization.html "Method Summarization") [Next ](https://docs.certora.com/en/latest/docs/prover/approx/hashing.html "Modeling of Hashing in the Certora Prover")
© Copyright 2025, Certora, Inc.
Built with [Sphinx](https://www.sphinx-doc.org/) using a [theme](https://github.com/readthedocs/sphinx_rtd_theme) provided by [Read the Docs](https://readthedocs.org). 
