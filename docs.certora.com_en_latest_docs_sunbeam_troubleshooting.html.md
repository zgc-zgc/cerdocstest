[ Certora Prover Documentation ![Logo](https://docs.certora.com/en/latest/_static/Certora_Logo_Black.svg) ](https://docs.certora.com/en/latest/index.html)
Contents
  * [Certora User’s Guide](https://docs.certora.com/en/latest/docs/user-guide/index.html)
  * [The Certora Verification Language](https://docs.certora.com/en/latest/docs/cvl/index.html)
  * [The Certora Prover](https://docs.certora.com/en/latest/docs/prover/index.html)
  * [Sunbeam: Verification for Soroban](https://docs.certora.com/en/latest/docs/sunbeam/index.html)
    * [Installation](https://docs.certora.com/en/latest/docs/sunbeam/installation.html)
    * [User Guide For Sunbeam](https://docs.certora.com/en/latest/docs/sunbeam/usage.html)
    * [Troubleshooting](https://docs.certora.com/en/latest/docs/sunbeam/troubleshooting.html)
      * [Unable to run `certoraSorobanProver`](https://docs.certora.com/en/latest/docs/sunbeam/troubleshooting.html#unable-to-run-certorasorobanprover)
      * [Build step of `certoraSorobanProver` is failing](https://docs.certora.com/en/latest/docs/sunbeam/troubleshooting.html#build-step-of-certorasorobanprover-is-failing)
      * [Compiler Error: “error: linking with `cc` failed: exit status: 1” on Mac](https://docs.certora.com/en/latest/docs/sunbeam/troubleshooting.html#compiler-error-error-linking-with-cc-failed-exit-status-1-on-mac)
  * [The Certora Solana Prover](https://docs.certora.com/en/latest/docs/solana/index.html)
  * [Gambit: Mutation Generator for Solidity](https://docs.certora.com/en/latest/docs/gambit/index.html)


Additional information
  * [The Certora Equivalence Checker](https://docs.certora.com/en/latest/docs/equiv-check/index.html)
  * [Certora Technology White Paper](https://docs.certora.com/en/latest/docs/whitepaper/index.html)


  * [Index](https://docs.certora.com/en/latest/genindex.html)


[Certora Prover Documentation](https://docs.certora.com/en/latest/index.html)
  * [](https://docs.certora.com/en/latest/index.html)
  * [Sunbeam: Verification for Soroban](https://docs.certora.com/en/latest/docs/sunbeam/index.html)
  * Troubleshooting
  * [ View page source](https://docs.certora.com/en/latest/_sources/docs/sunbeam/troubleshooting.rst.txt)


# Troubleshooting[](https://docs.certora.com/en/latest/docs/sunbeam/troubleshooting.html#troubleshooting "Link to this heading")
## Unable to run `certoraSorobanProver`[](https://docs.certora.com/en/latest/docs/sunbeam/troubleshooting.html#unable-to-run-certorasorobanprover "Link to this heading")
If you are unable to run `certoraSorobanProver`, we recommend trying it from within a `venv`.
  1. First, create a `venv` and make sure you are inside the `venv` by running the following:
```
cdprojectDir
python3-mvenv.venv
source.venv/bin/activate

```
Copy to clipboard
  2. Then, install all required packages like so:
```
pip3install-rrequirements.txt

```
Copy to clipboard
  3. Finally, try running `certoraRun` again:
```
certoraSorobanProverpath/to/prover_config.conf

```
Copy to clipboard


## Build step of `certoraSorobanProver` is failing[](https://docs.certora.com/en/latest/docs/sunbeam/troubleshooting.html#build-step-of-certorasorobanprover-is-failing "Link to this heading")
When you execute `certoraSorobanProver`, the project is internally build using `cargo build`. This step requires a successful build. In case `certoraSorobanProver` fails on the build step, first try to compile the project by running `cargo build --release --target wasm32-unknown-unknown` and resolve all compiler errors that you see.
## Compiler Error: “error: linking with `cc` failed: exit status: 1” on Mac[](https://docs.certora.com/en/latest/docs/sunbeam/troubleshooting.html#compiler-error-error-linking-with-cc-failed-exit-status-1-on-mac "Link to this heading")
If you are running on Mac and the build step of your project or `certoraRun` fails with the warning:
```
"error: linking with \`cc\` failed: exit status: 1"

```
Copy to clipboard
then check out the following [StackOverflow post](https://stackoverflow.com/questions/28124221/error-linking-with-cc-failed-exit-code-1).
[ Previous](https://docs.certora.com/en/latest/docs/sunbeam/usage.html "User Guide For Sunbeam") [Next ](https://docs.certora.com/en/latest/docs/solana/index.html "The Certora Solana Prover")
© Copyright 2025, Certora, Inc.
Built with [Sphinx](https://www.sphinx-doc.org/) using a [theme](https://github.com/readthedocs/sphinx_rtd_theme) provided by [Read the Docs](https://readthedocs.org). 
