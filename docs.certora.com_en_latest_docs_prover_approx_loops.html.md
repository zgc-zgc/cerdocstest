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
  * [Prover Approximations](https://docs.certora.com/en/latest/docs/prover/approx/index.html)
  * Loop Unrolling
  * [ View page source](https://docs.certora.com/en/latest/_sources/docs/prover/approx/loops.md.txt)


# Loop Unrolling[](https://docs.certora.com/en/latest/docs/prover/approx/loops.html#loop-unrolling "Link to this heading")
One of the approximations applied by the Certora Prover is loop unrolling. Loops in the contract are replaced by multiple copies of their bodies. if the Prover detects that a loop has a constant number of iterations, this loop is unrolled as many times as the constant.
For example, for the loop:
```
for(uinti=0;i<3;i++)
j++;

```
Copy to clipboard
the Prover can determine that the loop always runs 3 times, so the loop will be replaced by
```
j++;
j++;
j++;

```
Copy to clipboard
If the Prover cannot easily determine the number of loop iterations, it will unroll it a fixed number of times. The default number is 1, but it can be configured using the [loop_iter](https://docs.certora.com/en/latest/docs/prover/cli/options.html#loop-iter) flag.
For example, consider the following solidity function:
```
/// @notice: `slow_copy(n)` always returns `n`
functionslow_copy(uintn)returnsuint{
uintj=0;
for(uinti=0;i<n;i++)
j++;
returnj;
}

```
Copy to clipboard
With `--loop_iter 2`, the loop in `slow_copy` will be approximated by two copies of its body:
```
functionslow_copy_unrolled(uintn)returnsuint{
uintj=0;
uinti=0;
if(i<n){
j++;
i++;
if(i<n){
j++;
i++;
}
}
returnj;
}

```
Copy to clipboard
If a particular example would cause the loop to run more than twice, then the loop guard (`i < n` in the example) would still be true at the end of the loop.
The Prover has two options for handling examples that would execute the loop too many times:
  * In **pessimistic mode** (the default), the Prover will report an example that executes the loop too many times as a violation of the “loop unwinding condition” rule. In pessimistic mode, any rule run on `slow_copy(n)` would report a violation with `n = 3`.
Pessimistic mode is [sound](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-sound), because there may be rule violations in the original code that only occur when the loop runs more than 3 times, and loop unrolling would cause those violations to be missed. For example, the original function `slow_copy` should not satisfy the following rule:
```
rulebogus_rule(uintn){
assertslow_copy(n)<5,"slow_copy always returns something less than 5";
}

```
Copy to clipboard
but any violation would require 5 or more iterations of the loop. The loop unwinding violation notifies the user that this rule might not hold.
  * In **optimistic mode** (enabled by passing the [optimistic_loop](https://docs.certora.com/en/latest/docs/prover/cli/options.html#optimistic-loop) option), the Prover _ignores_ any examples that would cause the loop to execute too many times. In optimistic mode, the rule `bogus_rule` above would be reported as passing.
Caution
Optimistic mode is [unsound](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-unsound) since it may miss counterexamples like these. It should be used with care since it may hide bugs.
Despite the unsoundness, optimistic mode is quite useful in practice. For example, it allows us to document that `slow_copy` satisfies the specification given in its documentation:
```
ruleslow_copy_correct(uintn){
assertslow_copy(n)==n,"slow_copy(n) always returns n";
}

```
Copy to clipboard
In optimistic mode, this rule will pass (as it should), but in pessimistic mode it will fail if `n > 2`.


[ Previous](https://docs.certora.com/en/latest/docs/prover/approx/index.html "Prover Approximations") [Next ](https://docs.certora.com/en/latest/docs/prover/approx/summarization.html "Method Summarization")
© Copyright 2025, Certora, Inc.
Built with [Sphinx](https://www.sphinx-doc.org/) using a [theme](https://github.com/readthedocs/sphinx_rtd_theme) provided by [Read the Docs](https://readthedocs.org). 
