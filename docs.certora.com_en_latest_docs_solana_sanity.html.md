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
    * [Rule Sanity Checks (Solana)](https://docs.certora.com/en/latest/docs/solana/sanity.html)
      * [Vacuity checks](https://docs.certora.com/en/latest/docs/solana/sanity.html#vacuity-checks)
    * [Troubleshooting](https://docs.certora.com/en/latest/docs/solana/troubleshooting.html)
  * [Gambit: Mutation Generator for Solidity](https://docs.certora.com/en/latest/docs/gambit/index.html)


Additional information
  * [The Certora Equivalence Checker](https://docs.certora.com/en/latest/docs/equiv-check/index.html)
  * [Certora Technology White Paper](https://docs.certora.com/en/latest/docs/whitepaper/index.html)


  * [Index](https://docs.certora.com/en/latest/genindex.html)


[Certora Prover Documentation](https://docs.certora.com/en/latest/index.html)
  * [](https://docs.certora.com/en/latest/index.html)
  * [The Certora Solana Prover](https://docs.certora.com/en/latest/docs/solana/index.html)
  * Rule Sanity Checks (Solana)
  * [ View page source](https://docs.certora.com/en/latest/_sources/docs/solana/sanity.md.txt)


# Rule Sanity Checks (Solana)[](https://docs.certora.com/en/latest/docs/solana/sanity.html#rule-sanity-checks-solana "Link to this heading")
The [rule_sanity](https://docs.certora.com/en/latest/docs/prover/cli/options.html#rule-sanity) option enables automatic checks that warn about potential problems in the specification. Currently the only supported sanity check is the one called vacuity.
Note
This is the documentation for the sanity checks for Solana. If you are looking for the Sanity checks for Solidity, please refer to [this section](https://docs.certora.com/en/latest/docs/prover/checking/sanity.html).
The `--rule_sanity` option can be set to `none` or `basic` and controls whether the sanity checks should be executed:
  * With `--rule_sanity none` or without passing `--rule_sanity`, no sanity check is performed.
  * With `--rule_sanity basic` or simply `--rule_sanity` without a mode, the sanity checks are executed.


Each sanity check adds a new child node to every rule in the rule tree of the rule report. Each check transforms the the original program into a variant where `cvlr_satisfy!(true)` is inserted at the end of the program, and all calls to `cvlr_assert` are removed. If the sanity check fails on a rule, the sanity node in the rule report is displayed as a yellow icon, and its status propagates to the parent rule’s node (see below for an example).
The remainder of this document describes the vacuity check in detail.
## Vacuity checks[](https://docs.certora.com/en/latest/docs/solana/sanity.html#vacuity-checks "Link to this heading")
The **vacuity** sanity check ensures that even when ignoring all the user-provided assertions, the end of the rule is reachable. This check ensures that the combination of `cvlr_assume!` statements and implicit panics are not contradictory. Rules that are satisfied due to contradictory assumptions are called [vacuous](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-vacuous). Since vacuous rules do not actually check any assertion, they are almost certainly incorrect.
For example, the following rule is vacuous (and is flagged by the vacuity check):
```
#[rule]
pubfnrule_vacuity_test_expect_sanity_failure(){
letamount:u64=nondet();
cvlr_assume!(amount>=2);
cvlr_assume!(amount<=1);
cvlr_assert!(amount==1);
// Expect a sanity failure here as the assumptions are conflicting
}

```
Copy to clipboard
Since the two assumes `amount >= 2` and `amount <= 1` contradict each other, this rule always passes, regardless of the content of the assertion. This is an example of a [vacuous](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-vacuous) rule — one that passes only because the preconditions are contradictory.
In the rule report, a vacuity check adds a node called `rule_not_vacuous_cvlr` to each rule. For example, see how the rule `rule_vacuity_test_expect_sanity_failure` from above is reported as failing sanity, as `rule_not_vacuous_cvlr` fails. Below you see an example of a rule without the contradicting `assume`s that does not fail vacuity.
![Screenshot of vacuity subrule](https://docs.certora.com/en/latest/_images/vacuity_check.png)
[ Previous](https://docs.certora.com/en/latest/docs/solana/output.html "Understanding Prover Output for Solana Programs") [Next ](https://docs.certora.com/en/latest/docs/solana/troubleshooting.html "Troubleshooting")
© Copyright 2025, Certora, Inc.
Built with [Sphinx](https://www.sphinx-doc.org/) using a [theme](https://github.com/readthedocs/sphinx_rtd_theme) provided by [Read the Docs](https://readthedocs.org). 
