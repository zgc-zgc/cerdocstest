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
        * [Overview](https://docs.certora.com/en/latest/docs/prover/approx/summarization.html#overview)
        * [How Summarization Helps Solvers](https://docs.certora.com/en/latest/docs/prover/approx/summarization.html#how-summarization-helps-solvers)
        * [Syntax](https://docs.certora.com/en/latest/docs/prover/approx/summarization.html#syntax)
        * [Example: Summarization for a complex function](https://docs.certora.com/en/latest/docs/prover/approx/summarization.html#example-summarization-for-a-complex-function)
        * [Important Considerations](https://docs.certora.com/en/latest/docs/prover/approx/summarization.html#important-considerations)
        * [Summary](https://docs.certora.com/en/latest/docs/prover/approx/summarization.html#summary)
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
  * [Prover Approximations](https://docs.certora.com/en/latest/docs/prover/approx/index.html)
  * Method Summarization
  * [ View page source](https://docs.certora.com/en/latest/_sources/docs/prover/approx/summarization.md.txt)


# Method Summarization[](https://docs.certora.com/en/latest/docs/prover/approx/summarization.html#method-summarization "Link to this heading")
## Overview[](https://docs.certora.com/en/latest/docs/prover/approx/summarization.html#overview "Link to this heading")
**Method summarization** is a mechanism that allows the user to provide a concise, high-level description of the behavior of a method. It serves as a guide for the underlying solvers to more efficiently reason about the method’s behavior and helps to avoid timeouts, especially in cases where complex computations or undecidable problems are involved.
## How Summarization Helps Solvers[](https://docs.certora.com/en/latest/docs/prover/approx/summarization.html#how-summarization-helps-solvers "Link to this heading")
  1. **Efficiency Improvement:**
     * **Timeout Avoidance:** Summarization provides a way to guide the solver efficiently by providing a more abstract, high-level view of the method, potentially avoiding the need for detailed exploration.
     * **Faster Analysis:** By focusing on essential properties, summarization can lead to faster analysis, as the solver doesn’t need to explore every intricate detail of the method.
  2. **Abstraction of Complex Logic:**
     * **Complex Computations:** When dealing with functions involving complex mathematical operations or undecidable problems, summarization allows the user to abstract away unnecessary details, making it easier for the solver to reason about the method’s behavior.


## Syntax[](https://docs.certora.com/en/latest/docs/prover/approx/summarization.html#syntax "Link to this heading")
```
methods{
// Method summarization syntax
functionmethodName(parameters)returnsreturnType=>
summaryExpression;
}

```
Copy to clipboard
## Example: Summarization for a complex function[](https://docs.certora.com/en/latest/docs/prover/approx/summarization.html#example-summarization-for-a-complex-function "Link to this heading")
```
functionmultiply(uint256x,uint256y)returnsuint256{
returnx*y;
}
methods{
functioncomplexFunction(uint256x,uint256y)returnsbool=>
existsuint256z.z==multiply(x,y);
}
rulemyRule(uint256a,uint256b){
// Using the summarized method in a rule
requirecomplexFunction(a,b);
// ...
}

```
Copy to clipboard
In the example above, `complexFunction` involves a complex multiplication of `x` and `y`. The summarization `exists uint256 z . z == x * y;` provides a high-level description, emphasizing the existence of a product `z` that satisfies the multiplication relationship.
## Important Considerations[](https://docs.certora.com/en/latest/docs/prover/approx/summarization.html#important-considerations "Link to this heading")
  1. **Limitations of Summarization:**
     * Summarization is a trade-off between precision and efficiency. While it can significantly improve solver performance, it may introduce over- or under-approximations. over-approximation means we may use too general behaviors to prove the desired property. under-approximations means we potentially miss out on behaviors.
     * Care should be taken to ensure that the summarization captures the critical aspects of the method’s behavior.
  2. **Choosing Summarization Techniques:**
     * The choice of summarization techniques depends on the nature of the method and the specific verification goals.
     * Users may experiment with different summarization strategies to find the right balance between precision and efficiency. for more information, see [Summarization](https://docs.certora.com/en/latest/docs/cvl/methods.html).


## Summary[](https://docs.certora.com/en/latest/docs/prover/approx/summarization.html#summary "Link to this heading")
Method summarization in CVL provides a powerful tool for enhancing the efficiency of verification by guiding solvers to focus on essential aspects of a method’s behavior. By abstracting away unnecessary details, summarization helps prevent timeouts in situations involving complex computations or undecidable problems. Users should carefully design and choose summarizations that strike the right balance between precision and efficiency for their specific verification tasks.
[ Previous](https://docs.certora.com/en/latest/docs/prover/approx/loops.html "Loop Unrolling") [Next ](https://docs.certora.com/en/latest/docs/prover/approx/harnessing.html "Harnessing")
© Copyright 2025, Certora, Inc.
Built with [Sphinx](https://www.sphinx-doc.org/) using a [theme](https://github.com/readthedocs/sphinx_rtd_theme) provided by [Read the Docs](https://readthedocs.org). 
