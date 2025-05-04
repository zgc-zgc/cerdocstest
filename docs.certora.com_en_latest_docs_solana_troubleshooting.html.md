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
    * [Troubleshooting](https://docs.certora.com/en/latest/docs/solana/troubleshooting.html)
      * [Unable to run `certoraSolanaProver`](https://docs.certora.com/en/latest/docs/solana/troubleshooting.html#unable-to-run-certorasolanaprover)
      * [Jump to Source (JTS) feature not working](https://docs.certora.com/en/latest/docs/solana/troubleshooting.html#jump-to-source-jts-feature-not-working)
      * [Prover Errors](https://docs.certora.com/en/latest/docs/solana/troubleshooting.html#prover-errors)
  * [Gambit: Mutation Generator for Solidity](https://docs.certora.com/en/latest/docs/gambit/index.html)


Additional information
  * [The Certora Equivalence Checker](https://docs.certora.com/en/latest/docs/equiv-check/index.html)
  * [Certora Technology White Paper](https://docs.certora.com/en/latest/docs/whitepaper/index.html)


  * [Index](https://docs.certora.com/en/latest/genindex.html)


[Certora Prover Documentation](https://docs.certora.com/en/latest/index.html)
  * [](https://docs.certora.com/en/latest/index.html)
  * [The Certora Solana Prover](https://docs.certora.com/en/latest/docs/solana/index.html)
  * Troubleshooting
  * [ View page source](https://docs.certora.com/en/latest/_sources/docs/solana/troubleshooting.md.txt)


# Troubleshooting[](https://docs.certora.com/en/latest/docs/solana/troubleshooting.html#troubleshooting "Link to this heading")
This section describes resolution of common issues when using the Solana Prover.
## Unable to run `certoraSolanaProver`[](https://docs.certora.com/en/latest/docs/solana/troubleshooting.html#unable-to-run-certorasolanaprover "Link to this heading")
The `certoraSolanaProver` command has been introduced in version `7.22.0` of the Certora Prover package. Run `certoraRun --version` to verify that you are using a version greater or equal to `7.22.0`. It is possible to upgrade the Certora Prover package with the following command: `pip3 install --upgrade certora-cli`. For information about how to install the Certora Prover package, refer to [Installation](https://docs.certora.com/en/latest/docs/solana/installation.html).
## Jump to Source (JTS) feature not working[](https://docs.certora.com/en/latest/docs/solana/troubleshooting.html#jump-to-source-jts-feature-not-working "Link to this heading")
Observe that the Jump to Source feature does not work if the source files are not uploaded to the cloud. For more information about how to use the Certora Prover for Solana and correctly upload the source files to the cloud, refer to [Installation](https://docs.certora.com/en/latest/docs/solana/installation.html).
By default, JTS works for assertions, and for calls to `clog!()` macro (i.e., calls without any additional arguments). In additional, source location is inferred automatically from debug information. However, the reliability of the automatic JTS depends on the optimizations performed by the compiler.
## Prover Errors[](https://docs.certora.com/en/latest/docs/solana/troubleshooting.html#prover-errors "Link to this heading")
The Solana Prover is currently under development, and some features are not supported yet. The most common source of errors from the Prover are stack-allocated arrays. Accessing an element in an array that has been allocated on the stack can result in an error. For instance, the following rule triggers a Prover error.
```
#[rule]
fnaccess_stack_element(){
letints=[0,1,2];
letindex:usize=nondet_with(|x|*x<3);
cvlr_assert!(ints[index]<3);
}

```
Copy to clipboard
The Prover will display the following error message: ![Stack Access Error](https://docs.certora.com/en/latest/_images/stack_access_error.png)
To solve this, modify the source code to move the array to the heap. For instance, in the previous example it is sufficient to modify the type of `ints` from `[i32; 3]` to `Vec<i32>`:
```
#[rule]
fnaccess_stack_element(){
letints=vec![0,1,2];
letindex:usize=nondet_with(|x|*x<3);
cvlr_assert!(ints[index]<3);
}

```
Copy to clipboard
[ Previous](https://docs.certora.com/en/latest/docs/solana/sanity.html "Rule Sanity Checks \(Solana\)") [Next ](https://docs.certora.com/en/latest/docs/gambit/index.html "Gambit: Mutation Generator for Solidity")
© Copyright 2025, Certora, Inc.
Built with [Sphinx](https://www.sphinx-doc.org/) using a [theme](https://github.com/readthedocs/sphinx_rtd_theme) provided by [Read the Docs](https://readthedocs.org). 
