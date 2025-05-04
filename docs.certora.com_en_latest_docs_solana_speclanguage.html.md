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
      * [Assertions](https://docs.certora.com/en/latest/docs/solana/speclanguage.html#assertions)
      * [Assumptions](https://docs.certora.com/en/latest/docs/solana/speclanguage.html#assumptions)
      * [Nondeterministic Values](https://docs.certora.com/en/latest/docs/solana/speclanguage.html#nondeterministic-values)
      * [CVLR Rules](https://docs.certora.com/en/latest/docs/solana/speclanguage.html#cvlr-rules)
    * [Solana-Specific Options / CLI Flags](https://docs.certora.com/en/latest/docs/solana/options.html)
    * [Understanding Prover Output for Solana Programs](https://docs.certora.com/en/latest/docs/solana/output.html)
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
  * Certora Verification Language for Rust (CVLR)
  * [ View page source](https://docs.certora.com/en/latest/_sources/docs/solana/speclanguage.md.txt)


# Certora Verification Language for Rust (CVLR)[](https://docs.certora.com/en/latest/docs/solana/speclanguage.html#certora-verification-language-for-rust-cvlr "Link to this heading")
CVLR stands for Certora Verification Language for Rust. It is pronounced like “cavalier”. CVLR provides the basic primitives for writing verification rules that specify pre- and post-conditions for client code. Unlike CVL for Solidity, CVLR is embedded in Rust. It is compiled by the Rust compiler and has simple operational semantics.
CVLR is deployed to [crates.io](https://crates.io/crates/cvlr). The development version can be found at https://github.com/Certora/cvlr. Please note that CVLR is independent from the Solana ecosystem, specific CVLR features for Solana are maintained as part of the [cvlr-solana](https://crates.io/crates/cvlr-solana) package.
## Assertions[](https://docs.certora.com/en/latest/docs/solana/speclanguage.html#assertions "Link to this heading")
The simplest feature of CVLR is assertions. An assertion is written as `cvlr_assert!(cond)`, where `cond` is the condition being asserted. The semantics is the same as traditional asserts in Rust – an assertion is violated if there is (a panic-free) execution that reaches `cvlr_assert!(cond)` and in the current execution state `cond` is false.
For example, `cvlr_assert!(true)` is never violated, while `cvlr_assert!(false)` is always violated when reached.
What makes `cvlr_assert!` special is that it is verified symbolically by the Certora Prover. That is, the Prover returns `Violated` if there is an input and an execution of the program that reaches that assertion and violates it.
Often, the intended meaning of an assertion is to not be violated, i.e., to hold on all possible executions. However, sometimes it is useful to check whether some execution is possible. In that case, the specification intends for the assertion to be reachable. For such cases, CVLR provides a satisfy assertion, called `cvlr_satisfy!(cond)`.
The semantics of `cvlr_satisfy!(cond)` is that it is `Violated` when it is either not reached, or when every execution that reaches it, violates the condition. For example, `cvlr_satisfy!(true)` is violated only if it is never reachable (i.e., part of dead code), and `cvlr_satisfy!(false)` is always violated.
## Assumptions[](https://docs.certora.com/en/latest/docs/solana/speclanguage.html#assumptions "Link to this heading")
Assumptions provide a way to restrict input to reflect some pre-condition. CVLR provides an assumption macro `cvlr_assume!(cond)`. If an execution reaches `cvlr_assume!(cond)`, it continues only if `cond` is true in the current program state. Otherwise, the execution aborts.
For example, `cvlr_assume!(true)` is a noop, while `cvlr_assume!(false)` blocks all executions that reach it.
A typical use of `cvlr_assume!` is to restrict a range of a value beyond the restriction afforded by its type. For example, restricting the maximum value of a variable to `100` can be done as follows:
```
letfee_bps=get_some_fee();
cvlr_assume!(fee_bps<=100)
// computation reaches here only if fee_bps is no greater than 100

```
Copy to clipboard
## Nondeterministic Values[](https://docs.certora.com/en/latest/docs/solana/speclanguage.html#nondeterministic-values "Link to this heading")
A specification must tell the Prover what are the (symbolic) inputs that the Prover has to explore. Such values are called non-deterministic. The name comes from the fact that the Prover chooses the values non-deterministically (i.e., not following any specific pre-determined exploration scheme or probability distribution). Nondet values are similar to _arbitrary_ values in property-based testing, except that they are not chosen randomly, but are explored exhaustively via symbolic reasoning.
CVLR provides a generic function `nondet()` that can generate non-deterministic values of all primitive integers. For example, `nondet::<u64>()` returns a non-deterministic `u64`, and `nondet::<u16>()` returns a non-deterministic `u16`.
## CVLR Rules[](https://docs.certora.com/en/latest/docs/solana/speclanguage.html#cvlr-rules "Link to this heading")
Specifications are written as pre- and post-conditions in rules. A rule is similar to a unit test. However, instead of being executed for some specific input, the rule is symbolically analyzed for all possible non-deterministic values.
In CVLR, rules are regular Rust functions, annotated with `#[rule]`.
A complete example of a specification with several rules is shown below. The function being verified is `compute_fee`. We have included it in the spec file for simplicity.
```
usecvlr::prelude::*;
pubfncompute_fee(amount:u64,fee_bps:u16)->Option<u64>{
ifamount==0{returnNone;}
letfee=amount.checked_mul(fee_bps).checked_div(10_000);
fee
}
#[rule]
pubfnrule_fee_sanity(){
compute_fee(nondet(),nondet()).unwrap();
cvlr_satisfy!(true);
}
#[rule]
pubfnrule_fee_assessed(){
letamt:u64=nondet();
letfee_bps:u16=nondet();
cvlr_assume!(fee_bps<=10_000);
letfee=compute_fee(amt,fee_bps).unwrap();
clog!(amt,fee_bps,fee);
cvlr_assert!(fee<=amt);
iffee_bps>0{cvlr_assert!(fee>0);}
}
#[rule]
pubfnrule_fee_liveness(){
letamt:u64=nondet();
letfee_bps:u16=nondet();
cvlr_assume!(fee_bps<=10_000);
letfee=compute_fee(amt,fee_bps);
clog!(amt,fee_bps,fee);
iffee.is_none(){cvlr_assert!(amt==0);}
}

```
Copy to clipboard
The rule `rule_fee_sanity` checks that the function under verification has at least one panic-free execution. A rule like that is called a sanity rule. It is a good practice to start a specification with such a rule.
The rule `rule_fee_assessed` checks that a fee can be computed for an arbitrary amount. It has two assertions. The first checks that the fee is never greater than the amount. The second checks that the fee is always assessed when required. The first assertion is not violated. However, the second is. Can you spot the bug? Note that we have also added calls to the log macro `clog!` that is similar to the `dbg!` macro in Rust. The `clog!` macro will instruct the Prover to produce the values of the desired variables in any violating execution.
The rule `rule_fee_liveness` checks that the fee is always computed, except when the fee rate is 0. This assertion is violated. Can you spot the bug?
[ Previous](https://docs.certora.com/en/latest/docs/solana/usage.html "Using the Solana Certora Prover") [Next ](https://docs.certora.com/en/latest/docs/solana/options.html "Solana-Specific Options / CLI Flags")
© Copyright 2025, Certora, Inc.
Built with [Sphinx](https://www.sphinx-doc.org/) using a [theme](https://github.com/readthedocs/sphinx_rtd_theme) provided by [Read the Docs](https://readthedocs.org). 
