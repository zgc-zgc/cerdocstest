[ Certora Prover Documentation ![Logo](https://docs.certora.com/en/latest/_static/Certora_Logo_Black.svg) ](https://docs.certora.com/en/latest/index.html)
Contents
  * [Certora User’s Guide](https://docs.certora.com/en/latest/docs/user-guide/index.html)
    * [Installation](https://docs.certora.com/en/latest/docs/user-guide/install.html)
    * [Installing an EVM compiler and VS Code Extension](https://docs.certora.com/en/latest/docs/user-guide/install_evm_compiler.html)
    * [Tutorial and Workshops](https://docs.certora.com/en/latest/docs/user-guide/tutorials.html)
    * [Running the Certora Prover](https://docs.certora.com/en/latest/docs/user-guide/running.html)
    * [Designing Good Specifications](https://docs.certora.com/en/latest/docs/user-guide/properties/index.html)
    * [Producing Positive Examples](https://docs.certora.com/en/latest/docs/user-guide/satisfy.html)
    * [Invariants](https://docs.certora.com/en/latest/docs/user-guide/invariants.html)
    * [Parametric rules](https://docs.certora.com/en/latest/docs/user-guide/parametric.html)
    * [Tracking changes with ghosts and hooks](https://docs.certora.com/en/latest/docs/user-guide/ghosts.html)
    * [Specification Design Patterns](https://docs.certora.com/en/latest/docs/user-guide/patterns/index.html)
    * [Using Opcode Hooks](https://docs.certora.com/en/latest/docs/user-guide/opcodes.html)
    * [Working with Multiple Contracts](https://docs.certora.com/en/latest/docs/user-guide/multicontract/index.html)
    * [Managing Timeouts and Out of Memory Problems](https://docs.certora.com/en/latest/docs/user-guide/out-of-resources/index.html)
    * [Understanding gaps between high and low level code](https://docs.certora.com/en/latest/docs/user-guide/gaps.html)
    * [Checking Specifications](https://docs.certora.com/en/latest/docs/user-guide/checking.html)
    * [CI Configuration](https://docs.certora.com/en/latest/docs/user-guide/ci.html)
    * [Syntax Highlighting on GitHub](https://docs.certora.com/en/latest/docs/user-guide/github_highlighting.html)
    * [Glossary](https://docs.certora.com/en/latest/docs/user-guide/glossary.html)
  * [The Certora Verification Language](https://docs.certora.com/en/latest/docs/cvl/index.html)
  * [The Certora Prover](https://docs.certora.com/en/latest/docs/prover/index.html)
  * [Sunbeam: Verification for Soroban](https://docs.certora.com/en/latest/docs/sunbeam/index.html)
  * [The Certora Solana Prover](https://docs.certora.com/en/latest/docs/solana/index.html)
  * [Gambit: Mutation Generator for Solidity](https://docs.certora.com/en/latest/docs/gambit/index.html)


Additional information
  * [The Certora Equivalence Checker](https://docs.certora.com/en/latest/docs/equiv-check/index.html)
  * [Certora Technology White Paper](https://docs.certora.com/en/latest/docs/whitepaper/index.html)


  * [Index](https://docs.certora.com/en/latest/genindex.html)


[Certora Prover Documentation](https://docs.certora.com/en/latest/index.html)
  * [](https://docs.certora.com/en/latest/index.html)
  * [Certora User’s Guide](https://docs.certora.com/en/latest/docs/user-guide/index.html)
  * CI Configuration
  * [ View page source](https://docs.certora.com/en/latest/_sources/docs/user-guide/ci.rst.txt)


# CI Configuration[](https://docs.certora.com/en/latest/docs/user-guide/ci.html#ci-configuration "Link to this heading")
Follow these steps to configure CI for GitHub Actions on your repository:
  * 

Step 1:
    
Add the Certora CLI key [as a secret](https://docs.github.com/en/actions/security-guides/using-secrets-in-github-actions#creating-secrets-for-a-repository) to your repository, the secret name is CERTORAKEY and the value is the key provided.
  * 

Step 2:
    
Create a `certora_verification.yml` file under `.github` directory and use the following .yaml example as a template you can use to start running certora-cli.


```
name:certora-verification
on:
push:
branches:
-main
pull_request:
branches:
-main
workflow_dispatch:
jobs:
verify:
runs-on:ubuntu-latest
steps:
-uses:actions/checkout@v4
with:
submodules:recursive
-name:Install python
uses:actions/setup-python@v2
with:{ python-version:3.9}
-name:Install java
uses:actions/setup-java@v1
with:{ java-version:"11", java-package:jre}
# It's recommended to pin the latest certora-cli version available in https://pypi.org/project/certora-cli/
-name:Install certora cli
run:pip install certora-cli==7.3.0
-name:Install solc
run:|
pip install solc-select
solc-select install 0.8.23
solc-select use 0.8.23
# If your project depends on compiling with multiple solc versions, you can install and differentiate them using these commands.
# wget https://github.com/ethereum/solidity/releases/download/v0.8.23/solc-static-linux
# chmod +x solc-static-linux
# sudo mv solc-static-linux /usr/local/bin/solc8.23
-name:Verify ${{ matrix.rule }}
env:
CERTORAKEY:${{ secrets.CERTORAKEY }}
run:certoraRun ${{ matrix.rule }}
strategy:
fail-fast:false
max-parallel:16
matrix:
rule:
-path-to-conf1.conf --rule rule1# https://docs.certora.com/en/latest/docs/prover/cli/options.html#rule-rule-name
-path-to-conf1.conf --exclude_rule rule2# https://docs.certora.com/en/latest/docs/prover/cli/options.html#exclude-rule-rule-name-pattern
-path-to-conf2.conf# run the entire conf

```
Copy to clipboard
[ Previous](https://docs.certora.com/en/latest/docs/user-guide/checking.html "Checking Specifications") [Next ](https://docs.certora.com/en/latest/docs/user-guide/github_highlighting.html "Syntax Highlighting on GitHub")
© Copyright 2025, Certora, Inc.
Built with [Sphinx](https://www.sphinx-doc.org/) using a [theme](https://github.com/readthedocs/sphinx_rtd_theme) provided by [Read the Docs](https://readthedocs.org). 
