[ Certora Prover Documentation ![Logo](https://docs.certora.com/en/latest/_static/Certora_Logo_Black.svg) ](https://docs.certora.com/en/latest/index.html)
Contents
  * [Certora User’s Guide](https://docs.certora.com/en/latest/docs/user-guide/index.html)
  * [The Certora Verification Language](https://docs.certora.com/en/latest/docs/cvl/index.html)
  * [The Certora Prover](https://docs.certora.com/en/latest/docs/prover/index.html)
    * [Introduction](https://docs.certora.com/en/latest/docs/prover/intro.html)
    * [Installation](https://docs.certora.com/en/latest/docs/user-guide/install.html)
    * [Prover Approximations](https://docs.certora.com/en/latest/docs/prover/approx/index.html)
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
  * The Certora Prover
  * [ View page source](https://docs.certora.com/en/latest/_sources/docs/prover/index.md.txt)


# The Certora Prover[](https://docs.certora.com/en/latest/docs/prover/index.html#the-certora-prover "Link to this heading")
Note
The reference manual is currently being heavily edited and reorganized. Where possible, we have included links to the best existing documentation for each topic.
Contents
  * [Introduction](https://docs.certora.com/en/latest/docs/prover/intro.html)
  * [Installation](https://docs.certora.com/en/latest/docs/user-guide/install.html)
    * [Step 1: Prerequisites](https://docs.certora.com/en/latest/docs/user-guide/install.html#step-1-prerequisites)
    * [Step 2: Install the Certora Prover package](https://docs.certora.com/en/latest/docs/user-guide/install.html#step-2-install-the-certora-prover-package)
    * [Installing the beta version (optional)](https://docs.certora.com/en/latest/docs/user-guide/install.html#installing-the-beta-version-optional)
    * [Step 3: Set the personal access key as an environment variable](https://docs.certora.com/en/latest/docs/user-guide/install.html#step-3-set-the-personal-access-key-as-an-environment-variable)
    * [Step 4 (for GitHub users): Configure Syntax Highlighting](https://docs.certora.com/en/latest/docs/user-guide/install.html#step-4-for-github-users-configure-syntax-highlighting)
  * [Prover Approximations](https://docs.certora.com/en/latest/docs/prover/approx/index.html)
    * [Loop Unrolling](https://docs.certora.com/en/latest/docs/prover/approx/loops.html)
    * [Method Summarization](https://docs.certora.com/en/latest/docs/prover/approx/summarization.html)
    * [Harnessing](https://docs.certora.com/en/latest/docs/prover/approx/harnessing.html)
    * [Modeling of Hashing in the Certora Prover](https://docs.certora.com/en/latest/docs/prover/approx/hashing.html)
    * [Quantifier Grounding](https://docs.certora.com/en/latest/docs/prover/approx/grounding.html)
  * [Techniques Used by the Certora Prover](https://docs.certora.com/en/latest/docs/prover/techniques/index.html)
    * [Control flow splitting](https://docs.certora.com/en/latest/docs/prover/techniques/index.html#control-flow-splitting)
    * [Analysis of EVM storage and EVM memory](https://docs.certora.com/en/latest/docs/prover/techniques/index.html#analysis-of-evm-storage-and-evm-memory)
  * [Diagnostic Tools](https://docs.certora.com/en/latest/docs/prover/diagnosis/index.html)
    * [TAC Reports](https://docs.certora.com/en/latest/docs/prover/diagnosis/index.html#tac-reports)
  * [Checking Specifications](https://docs.certora.com/en/latest/docs/prover/checking/index.html)
    * [Rule Sanity Checks](https://docs.certora.com/en/latest/docs/prover/checking/sanity.html)
    * [Coverage Info](https://docs.certora.com/en/latest/docs/prover/checking/coverage-info.html)
    * [Bug Injection](https://docs.certora.com/en/latest/docs/prover/checking/injection.html)
    * [Mutation Testing](https://docs.certora.com/en/latest/docs/prover/checking/mutation.html)
  * [Certora Prover CLI](https://docs.certora.com/en/latest/docs/prover/cli/index.html)
    * [CLI Options](https://docs.certora.com/en/latest/docs/prover/cli/options.html)
    * [Most frequently used options](https://docs.certora.com/en/latest/docs/prover/cli/options.html#most-frequently-used-options)
    * [Options affecting the type of verification run](https://docs.certora.com/en/latest/docs/prover/cli/options.html#options-affecting-the-type-of-verification-run)
    * [Options that control the Solidity compiler](https://docs.certora.com/en/latest/docs/prover/cli/options.html#options-that-control-the-solidity-compiler)
    * [Options regarding source code loops](https://docs.certora.com/en/latest/docs/prover/cli/options.html#options-regarding-source-code-loops)
    * [Options regarding summarization](https://docs.certora.com/en/latest/docs/prover/cli/options.html#options-regarding-summarization)
    * [Options regarding hashing of unbounded data](https://docs.certora.com/en/latest/docs/prover/cli/options.html#options-regarding-hashing-of-unbounded-data)
    * [Options that help reduce the running time](https://docs.certora.com/en/latest/docs/prover/cli/options.html#options-that-help-reduce-the-running-time)
    * [Options to set addresses and link contracts](https://docs.certora.com/en/latest/docs/prover/cli/options.html#options-to-set-addresses-and-link-contracts)
    * [Options for job metadata and dashboard filtering](https://docs.certora.com/en/latest/docs/prover/cli/options.html#options-for-job-metadata-and-dashboard-filtering)
    * [Options for controlling contract creation](https://docs.certora.com/en/latest/docs/prover/cli/options.html#options-for-controlling-contract-creation)
    * [Version options](https://docs.certora.com/en/latest/docs/prover/cli/options.html#version-options)
    * [Conf file options](https://docs.certora.com/en/latest/docs/prover/cli/options.html#conf-file-options)
    * [Advanced options](https://docs.certora.com/en/latest/docs/prover/cli/options.html#advanced-options)
    * [Configuration (Conf) Files](https://docs.certora.com/en/latest/docs/prover/cli/conf-file-api.html)
  * [Using the Certora Portal](https://docs.certora.com/en/latest/docs/prover/portal/using.html)
    * [Certora Verification Reports](https://docs.certora.com/en/latest/docs/prover/portal/report.html)
    * [Special Portal URLs](https://docs.certora.com/en/latest/docs/prover/portal/secrets.html)
  * [Changelogs](https://docs.certora.com/en/latest/docs/prover/changelog/index.html)
    * [Prover Release Notes](https://docs.certora.com/en/latest/docs/prover/changelog/prover_changelog.html)
    * [GUI Release Notes](https://docs.certora.com/en/latest/docs/prover/changelog/gui_changelog.html)


[ Previous](https://docs.certora.com/en/latest/docs/cvl/v5-changes.html "Certora CLI 5.0 Changes") [Next ](https://docs.certora.com/en/latest/docs/prover/intro.html "Introduction")
© Copyright 2025, Certora, Inc.
Built with [Sphinx](https://www.sphinx-doc.org/) using a [theme](https://github.com/readthedocs/sphinx_rtd_theme) provided by [Read the Docs](https://readthedocs.org). 
