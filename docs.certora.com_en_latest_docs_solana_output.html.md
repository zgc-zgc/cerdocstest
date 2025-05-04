[ Certora Prover Documentation ![Logo](https://docs.certora.com/en/latest/_static/Certora_Logo_Black.svg) ](https://docs.certora.com/en/latest/index.html)
Contents
  * [Certora User’s Guide](https://docs.certora.com/en/latest/docs/user-guide/index.html)
  * [The Certora Verification Language](https://docs.certora.com/en/latest/docs/cvl/index.html)
  * [The Certora Prover](https://docs.certora.com/en/latest/docs/prover/index.html)
  * [Sunbeam: Verification for Soroban](https://docs.certora.com/en/latest/docs/sunbeam/index.html)
  * [The Certora Solana Prover](https://docs.certora.com/en/latest/docs/solana/index.html)
    * [Get started with the Solana Certora Prover](https://docs.certora.com/en/latest/docs/solana/installation.html)
    * [Using the Solana Certora Prover](https://docs.certora.com/en/latest/docs/solana/usage.html)
    * [Certora Verification Language for Rust (CVLR)](https://docs.certora.com/en/latest/docs/solana/speclanguage.html)
    * [Solana-Specific Options / CLI Flags](https://docs.certora.com/en/latest/docs/solana/options.html)
    * [Understanding Prover Output for Solana Programs](https://docs.certora.com/en/latest/docs/solana/output.html)
      * [Overview](https://docs.certora.com/en/latest/docs/solana/output.html#overview)
      * [Verification Tasks](https://docs.certora.com/en/latest/docs/solana/output.html#verification-tasks)
      * [Understanding Rule Results](https://docs.certora.com/en/latest/docs/solana/output.html#understanding-rule-results)
        * [Assert Statements](https://docs.certora.com/en/latest/docs/solana/output.html#assert-statements)
        * [Satisfy Statements](https://docs.certora.com/en/latest/docs/solana/output.html#satisfy-statements)
      * [Analyzing Counterexamples](https://docs.certora.com/en/latest/docs/solana/output.html#analyzing-counterexamples)
        * [Call Trace Analysis](https://docs.certora.com/en/latest/docs/solana/output.html#call-trace-analysis)
      * [Rule Sanity Checking](https://docs.certora.com/en/latest/docs/solana/output.html#rule-sanity-checking)
        * [Common Sanity Check Results](https://docs.certora.com/en/latest/docs/solana/output.html#common-sanity-check-results)
      * [Best Practices](https://docs.certora.com/en/latest/docs/solana/output.html#best-practices)
      * [Advanced Topics](https://docs.certora.com/en/latest/docs/solana/output.html#advanced-topics)
        * [Analyzing Functions Complexity](https://docs.certora.com/en/latest/docs/solana/output.html#analyzing-functions-complexity)
        * [Over-approximation Detection](https://docs.certora.com/en/latest/docs/solana/output.html#over-approximation-detection)
    * [Rule Sanity Checks (Solana)](https://docs.certora.com/en/latest/docs/solana/sanity.html)
    * [Troubleshooting](https://docs.certora.com/en/latest/docs/solana/troubleshooting.html)
  * [Gambit: Mutation Generator for Solidity](https://docs.certora.com/en/latest/docs/gambit/index.html)


Additional information
  * [The Certora Equivalence Checker](https://docs.certora.com/en/latest/docs/equiv-check/index.html)
  * [Certora Technology White Paper](https://docs.certora.com/en/latest/docs/whitepaper/index.html)


  * [Index](https://docs.certora.com/en/latest/genindex.html)


[Certora Prover Documentation](https://docs.certora.com/en/latest/index.html)
  * [](https://docs.certora.com/en/latest/index.html)
  * [The Certora Solana Prover](https://docs.certora.com/en/latest/docs/solana/index.html)
  * Understanding Prover Output for Solana Programs
  * [ View page source](https://docs.certora.com/en/latest/_sources/docs/solana/output.md.txt)


# Understanding Prover Output for Solana Programs[](https://docs.certora.com/en/latest/docs/solana/output.html#understanding-prover-output-for-solana-programs "Link to this heading")
## Overview[](https://docs.certora.com/en/latest/docs/solana/output.html#overview "Link to this heading")
This guide explains how to interpret verification results from the Certora Prover for Solana programs. It’s designed for developers familiar with Solana/Rust development and formal verification concepts.
## Verification Tasks[](https://docs.certora.com/en/latest/docs/solana/output.html#verification-tasks "Link to this heading")
A verification task consists of one or more rules that verify specific properties of your Solana program. Each rule contains at least one of the following:
  * Assert statements `cvlr_assert!`
  * Satisfy statements `cvlr_satisfy!`


## Understanding Rule Results[](https://docs.certora.com/en/latest/docs/solana/output.html#understanding-rule-results "Link to this heading")
### Assert Statements[](https://docs.certora.com/en/latest/docs/solana/output.html#assert-statements "Link to this heading")
When using `cvlr_assert`, the Prover attempts to prove that the assertion holds true for all possible program states. For example:
```
cvlr_assert!(amount>10);

```
Copy to clipboard
The Prover will return one of two results: ![A passed rule in the Certora Rule Report](https://docs.certora.com/en/latest/_images/passed.png)
  1. **PASSED** : The assertion is proven true for all possible computation paths and initial values


![A failed rule in the Certora Rule Report](https://docs.certora.com/en/latest/_images/failed.png)
  1. **FAILED** : A counterexample (CEX) was found, i.e a starting state and computation path that violates the assertion. The Prover stops at the first counterexample found, even if multiple counterexamples exist


### Satisfy Statements[](https://docs.certora.com/en/latest/docs/solana/output.html#satisfy-statements "Link to this heading")
`cvlr_satisfy` statements verify that a certain condition is reachable. For example:
```
cvlr_satisfy!(amount>10);

```
Copy to clipboard
The results can be:
  1. **PASSED** : At least one execution path exists where the condition is true
  2. **FAILED** : The condition is unreachable under any execution path


## Analyzing Counterexamples[](https://docs.certora.com/en/latest/docs/solana/output.html#analyzing-counterexamples "Link to this heading")
When a rule fails, the Prover generates a counterexample showing the execution path that led to the failure. Counterexamples can be:
  1. **Valid** : Indicating a genuine bug in the code
  2. **Spurious** : Resulting from over-approximation of possible program states


### Call Trace Analysis[](https://docs.certora.com/en/latest/docs/solana/output.html#call-trace-analysis "Link to this heading")
![A call trace example](https://docs.certora.com/en/latest/_images/call_trace_example.png)
The call trace provides detailed information about the execution path. Here’s how to interpret it:
#### Nondeterministic Values[](https://docs.certora.com/en/latest/docs/solana/output.html#nondeterministic-values "Link to this heading")
  * Appear at the beginning of the trace
  * Represent the starting state which leads to a violation
  * Format: `CVT_nondet_u64: <value>`


#### Variable Values[](https://docs.certora.com/en/latest/docs/solana/output.html#variable-values "Link to this heading")
  * The values of variables can be printed using the `clog!` macro
  * Example: `let x: u64 = nondet(); clog!(x);`


#### Method Calls[](https://docs.certora.com/en/latest/docs/solana/output.html#method-calls "Link to this heading")
  * Automatically logged
  * Show the sequence of function calls
  * To see parameter values, they have to be logged using `clog!` macro


#### Let’s look at a concrete example[](https://docs.certora.com/en/latest/docs/solana/output.html#let-s-look-at-a-concrete-example "Link to this heading")
[Prover output](https://prover.certora.com/output/1324651/741e8ee5a5754c1ab8db0aa36be39e4d?anonymousKey=ca602f5139de3bfbae17eb1fbf9c11145be3a912)
```
#[rule]
pubfnrule_fail_call_trace(){
letamount1:u64=nondet();
letamount2:u64=nondet();
cvlr_assume!(amount1>100);
cvlr_assume!(amount2!=10);
clog!(amount1,amount2);
cvlr_assert!(amount1<100);
cvlr_assert!(amount2<100);
}

```
Copy to clipboard
When this rule fails, the Prover generates a counterexample that looks like this:
![A call trace example](https://docs.certora.com/en/latest/_images/call_trace_detail.png)
Let’s analyze this counterexample:
  1. **Nondet Values** :
     * The Prover chose `101` for `amount1` and implicitly `0` for `amount2`
     * These values are chosen to demonstrate the violation of our assertions
     * `<?>` means that the value is not important for the counterexample
  2. **Variable States** :
     * `amount1` is 101, which satisfies our assumption `cvlr_assume!(amount1 > 100)`
     * `amount2` is 0, which satisfies our assumption `cvlr_assume!(amount2 != 10)`
  3. **Assertion Failure** :
     * The assertion `cvlr_assert!(amount1 < 100)` fails because we have a contradiction:
       * We previously assumed `amount1 > 100`
       * But then we assert `amount1 < 100`
     * This is impossible to satisfy, hence the counterexample


## Rule Sanity Checking[](https://docs.certora.com/en/latest/docs/solana/output.html#rule-sanity-checking "Link to this heading")
To ensure rules aren’t passing vacuously (due to contradictory assumptions), add sanity checking to your configuration:
```
{
"rule_sanity":"basic"
}

```
Copy to clipboard
This adds an implicit `cvlr_satisfy!(true)` at the end of each rule. If this assertion is unreachable, it confirms that:
  1. The assumptions are not contradictory
  2. The successful verification of the rule is meaningful


### Common Sanity Check Results[](https://docs.certora.com/en/latest/docs/solana/output.html#common-sanity-check-results "Link to this heading")
  1. **Sanity Check PASSED** : The desired outcome - confirms rule isn’t vacuously true
  2. **Sanity Check WARNING** : Warning sign - indicates contradictory assumptions


See [Rule Sanity Checks](https://docs.certora.com/en/latest/docs/solana/sanity.html) for more details.
## Best Practices[](https://docs.certora.com/en/latest/docs/solana/output.html#best-practices "Link to this heading")
  1. Always enable rule sanity checking in your configuration
  2. Review full call traces when investigating failures
  3. Validate counterexamples against your program’s expected state space


## Advanced Topics[](https://docs.certora.com/en/latest/docs/solana/output.html#advanced-topics "Link to this heading")
### Analyzing Functions Complexity[](https://docs.certora.com/en/latest/docs/solana/output.html#analyzing-functions-complexity "Link to this heading")
The Certora Solana Prover offers the Live Statistics panel to analyze the complexity of individual functions. The Live Statistics provide information, for instance, about the number of paths of a function body which may help when having difficult to solve rules. Observe that the Live Statistics panel is affected by the `solanaMinSizeForCalltrace` option. Functions with a size smaller than this threshold, measured by the number of TAC commands they correspond to, will not be displayed in the Live Statistics panel. Refer to the [Timeouts](https://docs.certora.com/en/latest/docs/user-guide/out-of-resources/timeout.html) section for further information.
### Over-approximation Detection[](https://docs.certora.com/en/latest/docs/solana/output.html#over-approximation-detection "Link to this heading")
When analyzing counterexamples, consider:
  1. Initial state feasibility: Is the starting state reachable for the code you’re analyzing?
  2. Transaction sequence validity: Does the computation path make sense? Did you overlook a certain scenario?
  3. State transition legitimacy: Do the values throughout the computation match? Are the parameters of your rule changing as expected?


If any seem impossible in your actual program, the counterexample might be due to over-approximation.
[ Previous](https://docs.certora.com/en/latest/docs/solana/options.html "Solana-Specific Options / CLI Flags") [Next ](https://docs.certora.com/en/latest/docs/solana/sanity.html "Rule Sanity Checks \(Solana\)")
© Copyright 2025, Certora, Inc.
Built with [Sphinx](https://www.sphinx-doc.org/) using a [theme](https://github.com/readthedocs/sphinx_rtd_theme) provided by [Read the Docs](https://readthedocs.org). 
