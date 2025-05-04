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
      * [CLI Options](https://docs.certora.com/en/latest/docs/prover/cli/options.html)
      * [Most frequently used options](https://docs.certora.com/en/latest/docs/prover/cli/options.html#most-frequently-used-options)
        * [`verify`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#verify)
        * [`msg`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#msg)
        * [`rule`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#rule)
        * [`exclude_rule`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#exclude-rule)
        * [`split_rules`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#split-rules)
        * [`method`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#method)
        * [`parametric_contracts`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#parametric-contracts)
        * [`wait_for_results`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#wait-for-results)
      * [Options affecting the type of verification run](https://docs.certora.com/en/latest/docs/prover/cli/options.html#options-affecting-the-type-of-verification-run)
        * [`coverage_info`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#coverage-info)
        * [`foundry`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#foundry)
        * [`independent_satisfy`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#independent-satisfy)
        * [`multi_assert_check`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#multi-assert-check)
        * [`multi_example`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#multi-example)
        * [`project_sanity`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#project-sanity)
        * [`rule_sanity`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#rule-sanity)
        * [`short_output`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#short-output)
      * [Options that control the Solidity compiler](https://docs.certora.com/en/latest/docs/prover/cli/options.html#options-that-control-the-solidity-compiler)
        * [`compiler_map`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#solc-map)
        * [`ignore_solidity_warnings`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#ignore-solidity-warnings)
        * [`packages`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#packages)
        * [`packages_path`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#packages-path)
        * [`solc`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#solc)
        * [`solc_allow_path`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#solc-allow-path)
        * [`solc_evm_version`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#solc-evm-version)
        * [`solc_evm_version_map`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#solc-evm-version-map)
        * [`solc_optimize`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#solc-optimize)
        * [`solc_optimize_map`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#solc-optimize-map)
        * [`solc_via_ir`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#solc-via-ir)
        * [`solc_via_ir_map`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#solc-via-ir-map)
        * [`vyper`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#vyper)
      * [Options regarding source code loops](https://docs.certora.com/en/latest/docs/prover/cli/options.html#options-regarding-source-code-loops)
        * [`loop_iter`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#loop-iter)
        * [`optimistic_loop`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#optimistic-loop)
      * [Options regarding summarization](https://docs.certora.com/en/latest/docs/prover/cli/options.html#options-regarding-summarization)
        * [`auto_dispatcher`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#auto-dispatcher)
        * [`nondet_difficult_funcs`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#nondet-difficult-funcs)
        * [`nondet_minimal_difficulty`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#nondet-minimal-difficulty)
        * [`optimistic_summary_recursion`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#optimistic-summary-recursion)
        * [`summary_recursion_limit`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#summary-recursion-limit)
      * [Options regarding hashing of unbounded data](https://docs.certora.com/en/latest/docs/prover/cli/options.html#options-regarding-hashing-of-unbounded-data)
        * [`optimistic_hashing`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#optimistic-hashing)
        * [`hashing_length_bound`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#hashing-length-bound)
      * [Options that help reduce the running time](https://docs.certora.com/en/latest/docs/prover/cli/options.html#options-that-help-reduce-the-running-time)
        * [`compilation_steps_only`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#compilation-steps-only)
        * [`disable_local_type_checking`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#disable-local-type-checking)
        * [`global_timeout`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#global-timeout)
        * [`method`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id37)
        * [`smt_timeout`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#smt-timeout)
      * [Options to set addresses and link contracts](https://docs.certora.com/en/latest/docs/prover/cli/options.html#options-to-set-addresses-and-link-contracts)
        * [`address`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#address)
        * [`contract_extensions`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#contract-extensions)
        * [`contract_recursion_limit`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#contract-recursion-limit)
        * [`link`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#link)
        * [`optimistic_contract_recursion`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#optimistic-contract-recursion)
        * [`optimistic_fallback`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#optimistic-fallback)
        * [`struct_link`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#struct-link)
      * [Options for job metadata and dashboard filtering](https://docs.certora.com/en/latest/docs/prover/cli/options.html#options-for-job-metadata-and-dashboard-filtering)
        * [`msg`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id46)
        * [`protocol_author`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#protocol-author)
        * [`protocol_name`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#protocol-name)
      * [Options for controlling contract creation](https://docs.certora.com/en/latest/docs/prover/cli/options.html#options-for-controlling-contract-creation)
        * [`dynamic_bound`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#dynamic-bound)
        * [`dynamic_dispatch`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#dynamic-dispatch)
        * [`prototype`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#prototype)
      * [Version options](https://docs.certora.com/en/latest/docs/prover/cli/options.html#version-options)
        * [`version`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#version)
        * [`prover_version`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#prover-version)
      * [Conf file options](https://docs.certora.com/en/latest/docs/prover/cli/options.html#conf-file-options)
        * [`override_base_config`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#override-base-config)
      * [Advanced options](https://docs.certora.com/en/latest/docs/prover/cli/options.html#advanced-options)
        * [`java_args`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#java-args)
        * [`precise_bitwise_ops`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#precise-bitwise-ops)
        * [`prover_args`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#prover-args)
        * [Control flow splitting options](https://docs.certora.com/en/latest/docs/prover/cli/options.html#control-flow-splitting-options)
      * [Configuration (Conf) Files](https://docs.certora.com/en/latest/docs/prover/cli/conf-file-api.html)
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
  * [Certora Prover CLI](https://docs.certora.com/en/latest/docs/prover/cli/index.html)
  * CLI Options
  * [ View page source](https://docs.certora.com/en/latest/_sources/docs/prover/cli/options.md.txt)


# [CLI Options](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id65)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#cli-options "Link to this heading")
The `certoraRun` utility invokes the Solidity compiler and afterwards sends the job to Certora’s servers.
The most commonly used command is:
```
certoraRuncontractFile:contractName--verifycontractName:specFile

```
Copy to clipboard
If `contractFile` is named `contractName.sol`, the run command can be simplified to
```
certoraRuncontractFile--verifycontractName:specFile

```
Copy to clipboard
A short summary of these options can be seen by invoking `certoraRun --help`
For larger projects, the command line for running the Certora Prover can become large and cumbersome. It is therefore recommended to use configuration files instead. These are [JSON5](https://json5.org/) files (with `.conf` extension) that hold the parameters and options for the Prover. See [Configuration (Conf) Files](https://docs.certora.com/en/latest/docs/prover/cli/conf-file-api.html#conf-files) for more information.
Overview
  * [CLI Options](https://docs.certora.com/en/latest/docs/prover/cli/options.html#cli-options)
  * [Most frequently used options](https://docs.certora.com/en/latest/docs/prover/cli/options.html#most-frequently-used-options)
    * [`verify`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#verify)
    * [`msg`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#msg)
    * [`rule`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#rule)
    * [`exclude_rule`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#exclude-rule)
    * [`split_rules`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#split-rules)
    * [`method`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#method)
    * [`parametric_contracts`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#parametric-contracts)
    * [`wait_for_results`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#wait-for-results)
  * [Options affecting the type of verification run](https://docs.certora.com/en/latest/docs/prover/cli/options.html#options-affecting-the-type-of-verification-run)
    * [`coverage_info`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#coverage-info)
    * [`foundry`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#foundry)
    * [`independent_satisfy`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#independent-satisfy)
    * [`multi_assert_check`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#multi-assert-check)
    * [`multi_example`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#multi-example)
    * [`project_sanity`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#project-sanity)
    * [`rule_sanity`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#rule-sanity)
    * [`short_output`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#short-output)
  * [Options that control the Solidity compiler](https://docs.certora.com/en/latest/docs/prover/cli/options.html#options-that-control-the-solidity-compiler)
    * [`compiler_map`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#solc-map)
    * [`ignore_solidity_warnings`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#ignore-solidity-warnings)
    * [`packages`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#packages)
    * [`packages_path`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#packages-path)
    * [`solc`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#solc)
    * [`solc_allow_path`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#solc-allow-path)
    * [`solc_evm_version`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#solc-evm-version)
    * [`solc_evm_version_map`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#solc-evm-version-map)
    * [`solc_optimize`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#solc-optimize)
    * [`solc_optimize_map`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#solc-optimize-map)
    * [`solc_via_ir`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#solc-via-ir)
    * [`solc_via_ir_map`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#solc-via-ir-map)
    * [`vyper`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#vyper)
  * [Options regarding source code loops](https://docs.certora.com/en/latest/docs/prover/cli/options.html#options-regarding-source-code-loops)
    * [`loop_iter`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#loop-iter)
    * [`optimistic_loop`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#optimistic-loop)
  * [Options regarding summarization](https://docs.certora.com/en/latest/docs/prover/cli/options.html#options-regarding-summarization)
    * [`auto_dispatcher`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#auto-dispatcher)
    * [`nondet_difficult_funcs`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#nondet-difficult-funcs)
    * [`nondet_minimal_difficulty`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#nondet-minimal-difficulty)
    * [`optimistic_summary_recursion`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#optimistic-summary-recursion)
    * [`summary_recursion_limit`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#summary-recursion-limit)
  * [Options regarding hashing of unbounded data](https://docs.certora.com/en/latest/docs/prover/cli/options.html#options-regarding-hashing-of-unbounded-data)
    * [`optimistic_hashing`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#optimistic-hashing)
    * [`hashing_length_bound`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#hashing-length-bound)
  * [Options that help reduce the running time](https://docs.certora.com/en/latest/docs/prover/cli/options.html#options-that-help-reduce-the-running-time)
    * [`compilation_steps_only`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#compilation-steps-only)
    * [`disable_local_type_checking`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#disable-local-type-checking)
    * [`global_timeout`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#global-timeout)
    * [`method`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id37)
    * [`smt_timeout`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#smt-timeout)
  * [Options to set addresses and link contracts](https://docs.certora.com/en/latest/docs/prover/cli/options.html#options-to-set-addresses-and-link-contracts)
    * [`address`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#address)
    * [`contract_extensions`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#contract-extensions)
    * [`contract_recursion_limit`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#contract-recursion-limit)
    * [`link`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#link)
    * [`optimistic_contract_recursion`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#optimistic-contract-recursion)
    * [`optimistic_fallback`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#optimistic-fallback)
    * [`struct_link`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#struct-link)
  * [Options for job metadata and dashboard filtering](https://docs.certora.com/en/latest/docs/prover/cli/options.html#options-for-job-metadata-and-dashboard-filtering)
    * [`msg`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id46)
    * [`protocol_author`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#protocol-author)
    * [`protocol_name`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#protocol-name)
  * [Options for controlling contract creation](https://docs.certora.com/en/latest/docs/prover/cli/options.html#options-for-controlling-contract-creation)
    * [`dynamic_bound`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#dynamic-bound)
    * [`dynamic_dispatch`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#dynamic-dispatch)
    * [`prototype`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#prototype)
  * [Version options](https://docs.certora.com/en/latest/docs/prover/cli/options.html#version-options)
    * [`version`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#version)
    * [`prover_version`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#prover-version)
  * [Conf file options](https://docs.certora.com/en/latest/docs/prover/cli/options.html#conf-file-options)
    * [`override_base_config`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#override-base-config)
  * [Advanced options](https://docs.certora.com/en/latest/docs/prover/cli/options.html#advanced-options)
    * [`java_args`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#java-args)
    * [`precise_bitwise_ops`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#precise-bitwise-ops)
    * [`prover_args`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#prover-args)
      * [`enableStorageSplitting`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#enablestoragesplitting)
      * [`maxNumberOfReachChecksBasedOnDomination`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#maxnumberofreachchecksbasedondomination)
      * [`optimisticReturnsize`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#optimisticreturnsize)
      * [`smt_groundQuantifiers`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#smt-groundquantifiers)
      * [`superOptimisticReturnsize`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#superoptimisticreturnsize)
    * [Control flow splitting options](https://docs.certora.com/en/latest/docs/prover/cli/options.html#control-flow-splitting-options)
      * [`depth`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#depth)
      * [`dontStopAtFirstSplitTimeout`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#dontstopatfirstsplittimeout)
      * [`mediumTimeout`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#mediumtimeout)
      * [`smt_initialSplitDepth`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#smt-initialsplitdepth)


# [Most frequently used options](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id66)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#most-frequently-used-options "Link to this heading")
## [`verify`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id67)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#verify "Link to this heading")
**What does it do?** It runs formal verification of properties specified in a `.spec` file on a given contract. Each contract must have been declared in the input files or have the same name as the source code file it is in.
**When to use it?** When you wish to prove properties on the source code. This is by far the most common mode of the tool.
**Example - Command line** If we have a Solidity file `Bank.sol`, with a contract named `Bank` inside it, and a specification file called `Bank.spec`, the command would be:
```
certoraRunBank.sol--verifyBank:Bank.spec

```
Copy to clipboard
**Example - Configuration file**
If we have a Solidity file with a contract named `Bank` inside it, and a specification file called `Bank.spec`, add the following line to the configuration file:
```
"verify":"Bank:Bank.spec"

```
Copy to clipboard
## [`msg`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id68)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#msg "Link to this heading")
**What does it do?** Adds a message description to your run, similar to a commit message. This message will appear in the title of the completion email sent to you.
**When to use it?** Adding a message makes it easier to track several runs on [the Prover Dashboard](https://prover.certora.com/). It is very useful if you are running many verifications simultaneously. It is also helpful to keep track of a single file verification status over time, so we recommend always providing an informative message.
**Example - Command line**
To create the message above from the command line, use:
```
certoraRunBank.sol--verifyBank:Bank.spec--msg'Removed an assertion'

```
Copy to clipboard
Note
You need to wrap your message in quotes in the command line if it contains spaces.
**Example - Configuration file**
To create the message above from the configuration file, use:
```
"msg":"Removed an assertion"

```
Copy to clipboard
## [`rule`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id69)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#rule "Link to this heading")
**What does it do?** Formally verifies one or more given properties instead of the whole specification file. An invariant can also be selected.
**When to use it?** This option saves a lot of run time. Use it whenever you care about only a specific subset of a specification’s properties. The most common case is when you add a new rule to an existing specification. The other is when code changes cause a specific rule to fail; in the process of fixing the code, updating the rule, and understanding counterexamples, you likely want to verify only that specific rule.
**Rule Name Pattern** Rule names, like all CVL identifiers, have the same format as Solidity identifiers: they consist of a combination of letters, digits, dollar signs and underscores, but cannot start with a digit (see [here](https://docs.soliditylang.org/en/v0.8.16/path-resolution.html#allowed-paths)). In addition, rule name patterns can include the wildcard `*` that can replace any sequence of valid identifier characters. For example, the rule pattern `withdraw_*` can be used instead of listing all rules that start with the string `withdraw_`.
**Examples** If `Bank.spec` includes the following properties:
```
invariantaddress_zero_cannot_become_an_account()
rulewithdraw_succeeds()
rulewithdraw_fails()

```
Copy to clipboard
If we want to verify only `withdraw_succeeds`, we run the command
```
certoraRunBank.sol--verifyBank:Bank.spec--rulewithdraw_succeeds

```
Copy to clipboard
If we want to verify both `withdraw_succeeds` and `withdraw_fails`, we run the command
```
certoraRunBank.sol--verifyBank:Bank.spec--rulewithdraw_succeedswithdraw_fails

```
Copy to clipboard
Alternatively, to verify both `withdraw_succeeds` and `withdraw_fails`, we could simply run the command
```
certoraRunBank.sol--verifyBank:Bank.spec--rulewithdraw*

```
Copy to clipboard
In the configuration file, it will look like this:
```
"rule":["withdraw_succeeds","withdraw_fails"]

```
Copy to clipboard
or
```
"rule":["withdraw_*"]

```
Copy to clipboard
## [`exclude_rule`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id70)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#exclude-rule "Link to this heading")
**What does it do?** This flag is the opposite of [rule](https://docs.certora.com/en/latest/docs/prover/cli/options.html#rule) - it allows you to specify a list of rules that _should not_ be run.
You can filter out several rules or rule patterns.
**When to use it?** Use this flag when certain rules take too long to run or require a different configuration than the current verification run.
**Rule Name Pattern** Rule name or rule name with wildcards. See detailed specifications in [rule](https://docs.certora.com/en/latest/docs/prover/cli/options.html#rule).
**Examples** If `Bank.spec` includes the following properties:
```
invariantaddress_zero_cannot_become_an_account()
rulewithdraw_succeeds()
rulewithdraw_fails()

```
Copy to clipboard
If we want to skip checking `withdraw_succeeds` and `withdraw_fails`, we could run the command:
```
certoraRunBank.sol--verifyBank:Bank.spec--exclude_rulewithdraw*

```
Copy to clipboard
or add to the conf file:
```
"exclude_rule":["withdraw_*"]

```
Copy to clipboard
## [`split_rules`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id71)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#split-rules "Link to this heading")
**What does it do?** Typically, all rules (after being filtered by [rule](https://docs.certora.com/en/latest/docs/prover/cli/options.html#rule) and [exclude_rule](https://docs.certora.com/en/latest/docs/prover/cli/options.html#exclude-rule)) are evaluated in a single Prover job. With `split_rules` the user can run specific rules on separate dedicated Prover jobs. A new job will be created and executed for each rule that matches the rule patterns in `split_rules` an additional job will be created for the rest of the rules. After launching the generated jobs, the original job will return with a link to the dashboard, listing the status of the generated jobs.
You can split several rules or rule patterns.
**When to use it?** This option is useful when some rules take a much longer time than the rest. Split the difficult rules to their own dedicated Prover jobs will give them more resources that will potentially reduce their chance to timeout and will decrease the time to get the final job result for the less computationally intensive rules.
**Rule Name Pattern** Rule name or rule name patterns. See detailed specifications in [rule](https://docs.certora.com/en/latest/docs/prover/cli/options.html#rule).
Note
When used together with the [rule](https://docs.certora.com/en/latest/docs/prover/cli/options.html#rule) option, the logic is to collect all rules that match `rule` patterns and then subtract from them all rules that match any [exclude_rule](https://docs.certora.com/en/latest/docs/prover/cli/options.html#exclude-rule) patterns.
**Examples** If `Bank.spec` includes the following properties:
```
invariantaddress_zero_cannot_become_an_account()
rulewithdraw_succeeds()
rulewithdraw_fails()

```
Copy to clipboard
If we want to run the invariant on different Prover jobs we could run the command:
```
certoraRunBank.sol--verifyBank:Bank.spec--split_rulesaddress_zero_cannot_become_an_account

```
Copy to clipboard
or add to the configuration file:
```
"split_rules":["address_zero_cannot_become_an_account"]

```
Copy to clipboard
The rest of the rules (`withdraw_succeeds` and `withdraw_fails`) will run together in a different Prover job.
## [`method`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id72)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#method "Link to this heading")
**What does it do?** Only uses functions with the given method signature when instantiating [parametric rule](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-parametric-rule)s and [invariant](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-invariant)s. The method signature is the ABI representation of the method, optionally prepended by a contract name or wildcard (`_`). If no contract is specified the primary contract is assumed, and if the wildcard is used then all methods with this signature across all contracts in the [scene](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-0) will be used.
You may provide multiple method signatures, in which case the Prover will run on each of the listed methods.
**When to use it?** This option is useful when focusing on a specific counterexample; running on a specific contract method saves time.
**Examples** Suppose we are verifying an ERC20 contract, and we have the following [parametric rule](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-parametric-rule):
```
ruler{
methodf;enve;calldataargargs;
addressowner;addressspender;
mathintallowance_before=allowance(owner,spender);
f(e,args);
mathintallowance_after=allowance(owner,spender);
assertallowance_after>allowance_before=>e.msg.sender==owner;
}

```
Copy to clipboard
If we discover a counterexample in the method `deposit(uint)` of contract `C`, and wish to change the contract or the spec to rerun, we can just rerun on the `C.deposit` method via the command:
```
certoraRun--method'C.deposit(uint)'

```
Copy to clipboard
If we discover a counterexample in several methods, we could rerun just those via the command line:
```
certoraRun--method'deposit(uint)'--method'_.transfer(address,uint256)'

```
Copy to clipboard
Note
Many shells will interpret the `(` and `)` characters specially, so the method signature argument will usually need to be quoted in the command line as in the above example.
In the configuration file we can add the following line:
```
"method":["C.deposit(uint)","_.transfer(address,uint256)"]

```
Copy to clipboard
In the last example the `transfer` method of all contracts in the scene will be used, but only the `deposit` method of the primary contract.
## [`parametric_contracts`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id73)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#parametric-contracts "Link to this heading")
Added in version 5.0: Prior to version 5, method variables and invariants were only instantiated with methods of [Special variables and fields](https://docs.certora.com/en/latest/docs/cvl/expr.html#currentcontract).
**What does it do?** Only uses methods on the specified contract when instantiating [parametric rule](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-parametric-rule)s or [invariant](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-invariant)s. The contract name must be one of the contracts included in the [scene](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-0).
**When to use it?** As with the [rule](https://docs.certora.com/en/latest/docs/prover/cli/options.html#rule) and [method](https://docs.certora.com/en/latest/docs/prover/cli/options.html#method) options, this option is used to avoid rerunning the entire verification
**Example** Suppose you are working on a multicontract verification and wish to debug a counterexample in a method of the `Underlying` contract defined in the file `Example.sol`, you can execute the command:
```
certoraRunMain:Example.solUnderlying:Example.sol--verifyMain:Example.spec\
--parametric_contractsUnderlying

```
Copy to clipboard
or add to the configuration file:
```
"parametric_contracts":["Underlying"]

```
Copy to clipboard
## [`wait_for_results`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id74)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#wait-for-results "Link to this heading")
**Parameters**
```
ALL|NONE

```
Copy to clipboard
**What does it do?** Wait for verification results after sending the verification request. By default, the program exits after the request. The return code will not be zero if the verification finds a violation.
In CI, the default behavior is different: the Prover waits for verification results, and the return code will not be zero if a violation is found. You can force the Prover not to wait for verification results by giving the parameter `NONE`. In that case, the return code will be zero if the jobs were sent successfully.
**When to use it?** Use it to receive verification results in the terminal or a wrapping script.
**Example - Command line**
```
certoraRunExample.sol--verifyExample:Example.spec--wait_for_results

```
Copy to clipboard
**Example - Configuration file**
```
"wait_for_results":"ALL"

```
Copy to clipboard
# [Options affecting the type of verification run](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id75)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#options-affecting-the-type-of-verification-run "Link to this heading")
## [`coverage_info`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id76)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#coverage-info "Link to this heading")
**Usage**
```
--coverage_info<none|basic|advanced>

```
Copy to clipboard
**What does it do?** This option enables .sol and .spec coverage analysis and visualization. The `--coverage_info` option may be followed by one of `none`, `basic`, or `advanced`; See [Coverage Info](https://docs.certora.com/en/latest/docs/prover/checking/coverage-info.html) for more information about the analysis.
**When to use it?** We suggest using this option when you have finished (a subset of) your rules and the prover verified them. The analysis tells you which parts of the solidity input are covered by the rules, and also which parts of the rules are actually needed to prove the rules.
**Example**
```
certoraRunBank.sol--verifyBank:Bank.spec--coverage_infoadvanced

```
Copy to clipboard
## [`foundry`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id77)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#foundry "Link to this heading")
**What does it do?** Collects all test files in the project (files ending with `.t.sol`), and runs the [Foundry Integration (Alpha)](https://docs.certora.com/en/latest/docs/cvl/foundry-integration.html#foundry-integration) on them (specifically, the `verifyFoundryFuzzTestsNoRevert` builtin rule). As with the [project_sanity](https://docs.certora.com/en/latest/docs/prover/cli/options.html#project-sanity) option, the search is over files in the current git repository if such exists, otherwise over all files in the tree under the current working directory.
Note
This option implicitly enables the [auto_dispatcher](https://docs.certora.com/en/latest/docs/prover/cli/options.html#auto-dispatcher) option.
**When to use it?** When we want to run all Foundry fuzz tests in the project with the Prover.
**Example**
```
certoraRun--foundry

```
Copy to clipboard
## [`independent_satisfy`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id78)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#independent-satisfy "Link to this heading")
**What does it do?** The independent satisfy mode checks each [satisfy statement](https://docs.certora.com/en/latest/docs/cvl/statements.html#satisfy) independently from all other satisfy statements that occurs in a rule. Normally, each satisfy statement will be turned into a sub-rule (similarly to the [multi_assert_check](https://docs.certora.com/en/latest/docs/prover/cli/options.html#multi-assert-check) mode), but previously encountered satisfy statements will be still considered when creating a satisfying assignment.
As an illustrative example of the default mode, consider the following rule `R` that has two satisfy statements:
```
ruleR{
boolb;
satisfyb,"R1";
satisfy!b,"R2";
}

```
Copy to clipboard
The statements for “R1” and “R2” will actually create two sub-rules equivalent to:
```
ruleR1_default{
boolb;
satisfyb,"R1";
}
ruleR2_default{
boolb;
// Previous satisfy statements are required in default mode.
requireb;// R1
// Due to requiring `b`, this satisfy statement is equivalent to 'satisfy b && !b, "R2";'
satisfy!b,"R2";
}

```
Copy to clipboard
Without turning `independent_satisfy` mode on, `R2` would have failed, as it would try to satisfy `b && !b`, an unsatisfiable contradiction. Turning on the `independent_satisfy` mode will ignore all currently unchecked satisfy statements for each sub-rule. It would also generate and check two sub-rules, but with a slight difference: `R1` where `b` is satisfied (by `b=true`) while `satisfy !b` is removed, and `R2` where `satisfy b` is removed, and `!b` is satisfied (by `b=false`).
The two `independent_satisfy` generated sub-rules will be equivalent to:
```
ruleR1_independent{
boolb;
satisfyb,"R1";
}
ruleR2_independent{
boolb;
// require b;
satisfy!b,"R2";
}

```
Copy to clipboard
**When to use it?** When you have a rule with multiple satisfy statements, and you would like to demonstrate each statement separately.
**Example**
```
certoraRunBank.sol--verifyBank:Bank.spec--independent_satisfy

```
Copy to clipboard
## [`multi_assert_check`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id79)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#multi-assert-check "Link to this heading")
**What does it do?** This mode checks each assertion statement that occurs in a rule, separately. The check is done by decomposing each rule into multiple sub-rules, each of which checks one assertion, while it assumes all preceding assertions. In addition, all assertions that originate from the Solidity code (as opposed to those from the specification), are checked together by a designated, single sub-rule.
As an illustrative example, consider the following rule `R` that has two assertions:
```
...
asserta1
...
asserta2
...

```
Copy to clipboard
The `multi_assert_check` mode would generate and check two sub-rules: `R1` where `a1` is proved while `a2` is removed, and `R2` where `a1` is assumed (i.e., transformed into a requirement statement), and `a2` is proved.
`R` passes if and only if, `R1` and `R2` both pass. In particular, in case `R1` (resp. `R2`) fails, the counter-example shows a violation of `a1` (resp. `a2`).
Caution
We suggest using this mode carefully. In general, as this mode generates and checks more rules, it may lead to worse running-time performance. Please see indications for use below.
**When to use it?** When you have a rule with multiple assertions:
  1. As a timeout mitigation strategy: checking each assertion separately may, in some cases, perform better than checking all the assertions together and consequently solve timeouts.
  2. If you wish to get multiple counter-examples in a single run of the tool, where each counter-example violates a different assertion in the rule.


**Example**
```
certoraRunBank.sol--verifyBank:Bank.spec--multi_assert_check

```
Copy to clipboard
## [`multi_example`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id80)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#multi-example "Link to this heading")
Show several counterexamples for failed assert statements and several witnesses for verified satisfy statements.
**What does it do?** By default, the Prover returns a single example per rule, either a counterexample (for assert violations) or a witness (for satisfy verification). When this flag is enabled, the Prover will attempt to generate multiple examples from different control-flow paths or logical reasons, offering a broader view of the rule’s behavior.
**When to use it?** Use this flag when debugging complex rules where multiple, distinct scenarios might lead to failure or success. Seeing several examples can help identify different edge cases and refine in the specification or implementation.
**Example**
```
certoraRunMyContract.sol--verifyMyContract:MyContract.spec--multi_example

```
Copy to clipboard
## [`project_sanity`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id81)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#project-sanity "Link to this heading")
**What does it do?** Runs the builtin sanity rule on all methods in the project. If the Prover is run from within a git project, all `.sol` files in the in the git repository are added to the scene and the [builtin sanity rule](https://docs.certora.com/en/latest/docs/cvl/builtin.html#built-in-sanity) is run on them. Otherwise, _all_ `.sol` files in the tree under the current working directory are collected.
Alternatively, a list of files can be provided in the `.conf` file and then the builtin sanity rule will run on all methods of the specified files.
Note
This option implicitly enables the [auto_dispatcher](https://docs.certora.com/en/latest/docs/prover/cli/options.html#auto-dispatcher) option.
**When to use it?** Mostly used as a first step when starting to work on a new project, in order to “get a feeling” of the complexity of the project for the tool, and what methods may be hot spots for summarization etc.
**Example**
```
certoraRun--project_sanity

```
Copy to clipboard
## [`rule_sanity`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id82)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#rule-sanity "Link to this heading")
**Usage**
```
--rule_sanity<none|basic|advanced>

```
Copy to clipboard
**What does it do?** This option enables sanity checking for rules. The `--rule_sanity` option may be followed by one of `none`, `basic`, or `advanced`; See [Rule Sanity Checks](https://docs.certora.com/en/latest/docs/prover/checking/sanity.html) for more information about sanity checks.
**When to use it?** We suggest using this option routinely while developing rules. It is also a useful check if you notice rules passing surprisingly quickly or easily.
**Example**
```
certoraRunBank.sol--verifyBank:Bank.spec--rule_sanitybasic

```
Copy to clipboard
## [`short_output`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id83)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#short-output "Link to this heading")
**What does it do?** Reduces the verbosity of the tool.
**When to use it?** When we do not care much for the output. It is recommended when running the tool in continuous integration.
**Example**
```
certoraRunBank.sol--verifyBank:Bank.spec--short_output

```
Copy to clipboard
# [Options that control the Solidity compiler](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id84)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#options-that-control-the-solidity-compiler "Link to this heading")
## [`compiler_map`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id85)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#solc-map "Link to this heading")
**Usage**
```
--compiler_map<contract>=<version>,...

```
Copy to clipboard
**What does it do?** Compiles every smart contract with a different compiler executable (Solidity version or Vyper). All used contracts must be listed.
**When to use it?** When different contracts have to be compiled for different Solidity versions.
**Example**
```
certoraRunBank.solExchange.solToken.vy--verifyBank:Bank.spec--compiler_mapBank=solc4.25,Exchange=solc6.7,Token=vyper0.3.10

```
Copy to clipboard
## [`ignore_solidity_warnings`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id86)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#ignore-solidity-warnings "Link to this heading")
**What does it do?** This flag turns off the default behavior of treating certain Solidity compiler warnings as errors. When enabled, the tool will allow verification to proceed even if the Solidity compiler emits warnings.
**When to use it?** Use this flag if your contracts trigger non-critical compiler warnings you want to suppress during verification. This is especially useful for warnings irrelevant to formal verification or when using older code bases with known stylistic issues.
A common example is error 6321: `Unnamed return variable can remain unassigned`. The Solidity compiler versions 0.7.6 and up emit this warning, which can be safely ignored in many contexts.
**Example**
```
certoraRunToken.sol--verifyToken:Token.spec--ignore_solidity_warnings

```
Copy to clipboard
## [`packages`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id87)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#packages "Link to this heading")
**Usage**
```
--packages<name>=<path>...

```
Copy to clipboard
**What does it do?** For each package, gets the path to a directory including that Solidity package.
**When to use it?** By default we look for the packages in `$NODE_PATH`. If there are packages are in several different directories, use `--packages`.
**Example**
```
certoraRunBank.sol--verifyBank:Bank.spec--packagesds-stop=$PWD/lib/ds-token/lib/ds-stop/srcds-note=$PWD/lib/ds-token/lib/ds-stop/lib/ds-note/src

```
Copy to clipboard
Note
In Solidity projects, information about packages’ location is usually stored in `remappings.txt` file.
## [`packages_path`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id88)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#packages-path "Link to this heading")
**Usage**
```
--packages_path<path>

```
Copy to clipboard
**What does it do?** Gets the path to a directory including the Solidity packages.
**When to use it?** By default, we look for the packages in `$NODE_PATH`. If the packages are in any other directory, you must use `--packages_path`.
**Example**
```
certoraRunBank.sol--verifyBank:Bank.spec--packages_pathSolidity/packages

```
Copy to clipboard
## [`solc`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id89)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#solc "Link to this heading")
**Usage**
```
--solc<solc_executable>

```
Copy to clipboard
**What does it do?** This attribute tells the Prover which Solidity compiler to use. You may pass either:
  * A full path to the compiler executable, e.g., `/usr/local/bin/solc8.19`, or
  * Just the executable’s name, e.g., `solc8.19`, in which case the tool will search for it in your system’s `$PATH`.


This behavior mimics the shell’s resolution of commands (similar to how `which solc8.19` works).
**When to use it?** Use this option if your system has multiple Solidity versions installed and you want to select one explicitly. This is particularly useful when working with legacy contracts or caring about specific compiler version behaviors.
**Example**
```
# Use a compiler version from $PATH
certoraRunBank.sol--verifyBank:Bank.spec--solcsolc8.19
# Use full path to the compiler
certoraRunBank.sol--verifyBank:Bank.spec--solc/usr/local/bin/solc8.19

```
Copy to clipboard
## [`solc_allow_path`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id90)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#solc-allow-path "Link to this heading")
**Usage**
```
--solc_allow_path<path>

```
Copy to clipboard
**What does it do?** Passes the value of this option as is to the solidity compiler’s option `--allow-paths`. See [–allow-path specification](https://docs.soliditylang.org/en/v0.8.16/path-resolution.html#allowed-paths)
**When to use it?** When we want to add an additional location the Solidity compiler to load sources from
**Example**
```
certoraRunBank.sol--verifyBank:Bank.spec--solc_allow_path~/Projects/Bank

```
Copy to clipboard
## [`solc_evm_version`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id91)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#solc-evm-version "Link to this heading")
**Usage**
```
--solc_evm_version<version>

```
Copy to clipboard
**What does it do?** Passes the value of this option to the solidity compiler’s option `--evm-version`.
**When to use it?** When we want to select the Solidity compiler EVM version
**Example**
```
certoraRunBank.sol--verifyBank:Bank.spec--solc_evm_versionIstanbul

```
Copy to clipboard
## [`solc_evm_version_map`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id92)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#solc-evm-version-map "Link to this heading")
**Usage**
```
--solc_evm_version_map<contract>=<version>,...

```
Copy to clipboard
**What does it do?** Set EVM version values when different files run with different EVM versions Passes the value of this option as is to the solidity compiler’s option `--evm-version`.
**When to use it?** When different contracts have to be compiled with different Solidity EVM versions.
**Example**
```
certoraRunBank.sol--verifyBank:Bank.spec--solc_evm_version_mapBank=prague,Exchange=cancun

```
Copy to clipboard
## [`solc_optimize`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id93)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#solc-optimize "Link to this heading")
**Usage**
```
--solc_optimize<n>

```
Copy to clipboard
**What does it do?** Passes the value of this option as is to the solidity compiler’s option `--optimize` and `--optimize-runs`.
**When to use it?** When we want to activate in the solidity compiler the opcode-based optimizer for the generated bytecode and control the number of times the optimizer will be activated (if no value is set, the compiler’s default is 200 runs)
**Example**
```
certoraRunBank.sol--verifyBank:Bank.spec--solc_optimize300

```
Copy to clipboard
## [`solc_optimize_map`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id94)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#solc-optimize-map "Link to this heading")
**Usage**
```
--solc_optimize_map<contract>=<n>,...

```
Copy to clipboard
**What does it do?** Set optimize values when different files run with different number of runs Passes the value of this option as is to the solidity compiler’s option `--optimize` and `--optimize-runs`.
**When to use it?** When we want to activate in the solidity compiler the opcode-based optimizer for the generated bytecode and control the number of times the optimizer will be activated (if no value is set, the compiler’s default is 200 runs)
**Example**
```
certoraRunBank.sol--verifyBank:Bank.spec--solc_optimize_mapBank=200,Exchange=300

```
Copy to clipboard
## [`solc_via_ir`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id95)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#solc-via-ir "Link to this heading")
**What does it do?** Passes the value of this option to the solidity compiler’s option `--via-ir`.
**When to use it?** When we want to enable the IR-based code generator
**Example**
```
certoraRunBank.sol--verifyBank:Bank.spec--solc_via_ir

```
Copy to clipboard
## [`solc_via_ir_map`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id96)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#solc-via-ir-map "Link to this heading")
**Usage**
```
--solc_via_ir_map<contract>=<true|false>,...

```
Copy to clipboard
**What does it do?** This flag configures whether the Solidity compiler should enable the IR-based code generator per contract. It allows different contracts in the same project to be compiled with or without the `via-ir` option. This overrides [solc_via_ir](https://docs.certora.com/en/latest/docs/prover/cli/options.html#solc-via-ir) on a per-contract basis.
**When to use it?** Use this when different contracts require different compilation pipelines. For instance, if one contract benefits from the IR pipeline (e.g., improved output or different optimization behavior) but another fails to compile with the IR pipeline, this flag lets you mix modes safely.
**Note** If [solc_via_ir](https://docs.certora.com/en/latest/docs/prover/cli/options.html#solc-via-ir) is not set globally, no contracts will be compiled `via-ir` unless explicitly specified in this map.
**Example**
```
certoraRunA.solB.sol--verifyA:A.spec\
--solc_via_ir_mapA=true,B=false

```
Copy to clipboard
In this example, contract A is compiled with the `--via-ir` flag, while contract B is compiled without it.
## [`vyper`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id97)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#vyper "Link to this heading")
**Usage**
```
--vyper<vyper_executable>

```
Copy to clipboard
**What does it do?** This attribute tells the Prover which Vyper compiler to use. You may pass either:
  * A full path to the compiler executable, e.g., `/usr/local/bin/vyper0.3.10`, or
  * Just the executable’s name, e.g., `vyper0.3.10`, in which case the tool will search for it in your system’s `$PATH`.


This behavior mimics the shell’s resolution of commands (similar to how `which vyper0.3.10` works).
**When to use it?** Use this option if your system has multiple Vyper versions installed and you want to select one explicitly. This is particularly useful when working with legacy contracts or caring about specific compiler version behaviors.
**Example**
```
# Use a compiler version from $PATH
certoraRunBank.sol--verifyBank:Bank.spec--vypervyper0.3.10
# Use full path to the compiler
certoraRunBank.sol--verifyBank:Bank.spec--vyper/usr/local/bin/vyper0.3.10

```
Copy to clipboard
# [Options regarding source code loops](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id98)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#options-regarding-source-code-loops "Link to this heading")
## [`loop_iter`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id99)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#loop-iter "Link to this heading")
**Usage**
```
--loop_iter<n>

```
Copy to clipboard
**What does it do?** Sets the maximal number of loop iterations we verify for. The way the Certora Prover handles loops is by unrolling them - if the loop should be executed three times, it will copy the code inside the loop three times. This option sets the number of unrolls. Be aware that the run time grows exponentially by the number of loop iterations.
**When to use it?** The default number of loop iterations we unroll is one. However, in many cases, bugs only occur when there are several iterations. Common scenarios include iteration over list elements. Two, or in some cases three, is usually the most you will ever need to uncover bugs.
**Example**
```
certoraRunBank.sol--verifyBank:Bank.spec--loop_iter2

```
Copy to clipboard
## [`optimistic_loop`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id100)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#optimistic-loop "Link to this heading")
**What does it do?** The Certora Prover unrolls loops - if the loop should be executed three times, it will copy the code inside the loop three times. After we finish the loop’s iterations, we add an assertion to verify we have actually finished running the loop. For example, in a `while (a < b)` loop, after the loop’s unrolling, we add `assert a >= b`. We call this assertion the _loop unwind condition_. This option changes the assertions of the loop unwind condition to requirements (in the case above `require a >= b`). That means, we ignore all the cases where the loop unwind condition does not hold, instead of considering them as a failure.
**When to use it?** When you have loops in your code and are getting a counterexample labeled `loop unwind condition`. In general, you need this flag whenever the number of loop iterations varies. It is usually a necessity if using [loop_iter](https://docs.certora.com/en/latest/docs/prover/cli/options.html#loop-iter).
Caution
`--optimistic_loop` could cause [vacuous rules](https://docs.certora.com/en/latest/docs/prover/cli/options.html#rule-sanity).
**Example**
```
certoraRunBank.sol--verifyBank:Bank.spec--optimistic_loop

```
Copy to clipboard
# [Options regarding summarization](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id101)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#options-regarding-summarization "Link to this heading")
## [`auto_dispatcher`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id102)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#auto-dispatcher "Link to this heading")
**What does it do?** In case a call’s callee cannot be precomputed but the called method’s sighash can be (e.g. `MyInterface(addr).foo()` in solidity, where `addr` is some `address` typed variable), the default behavior of the Prover in this case is to Havoc. In this case the user can specify a [DISPATCHER summaries](https://docs.certora.com/en/latest/docs/cvl/methods.html#dispatcher) summary in the [The Methods Block](https://docs.certora.com/en/latest/docs/cvl/methods.html#methods-block) so that the prover will inline all methods in the scene that have this sighash.
This option will cause all such unknown callee with known sighash cases to behave as if an `DISPATCHER(optimistic=true)` was added for that method in the methods block.
One important difference from manually placing the `DISPATCHER` summary in the methods block is that when it’s manually written there with `optimistic=true` and no such function is found in the scene the Prover will exit with an error, but when using the flag it will fall back to the default havoc.
**When to use it?** When there are many unresolved callee methods, or as a first step to solve call resolution failures.
**Example**
```
certoraRunBank.sol--verifyBank:Bank.spec--auto_dispatcher

```
Copy to clipboard
## [`nondet_difficult_funcs`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id103)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#nondet-difficult-funcs "Link to this heading")
**What does it do?** When this option is set, the Prover will auto-summarize view or pure internal functions that return a value type and are currently not summarized, and that are found to be heuristically difficult for the Prover.
For more information, see [Detect candidates for summarization](https://docs.certora.com/en/latest/docs/user-guide/out-of-resources/timeout.html#detect-candidates-for-summarization).
**When to use it?** Using this option is recommended when beginning to work on a large code base that includes functions that could be difficult for the Prover. It can help the user get faster feedback, both in the form of faster verification results, as well as highlighting potentially difficult functions.
**Example**
```
certoraRunBank.sol--verifyBank:Bank.spec--nondet_difficult_funcs

```
Copy to clipboard
## [`nondet_minimal_difficulty`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id104)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#nondet-minimal-difficulty "Link to this heading")
**Usage**
```
--nondet_minimal_difficulty<n>

```
Copy to clipboard
**What does it do?** This option sets the minimal difficulty threshold for the auto-summarization mode enabled by [nondet_difficult_funcs](https://docs.certora.com/en/latest/docs/prover/cli/options.html#nondet-difficult-funcs).
**When to use it?** If the results of an initial run with [nondet_difficult_funcs](https://docs.certora.com/en/latest/docs/prover/cli/options.html#nondet-difficult-funcs) were unsatisfactory, one can adjust the default threshold to apply the auto-summarization to potentially more or fewer internal functions.
The notification in the rule report that contains the applied summaries will present the current threshold used by the Prover.
**Example**
```
certoraRunBank.sol--verifyBank:Bank.spec--nondet_difficult_funcs--nondet_minimal_difficulty20

```
Copy to clipboard
## [`optimistic_summary_recursion`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id105)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#optimistic-summary-recursion "Link to this heading")
**What does it do?** In case there’s a call to some Solidity function within a summary, we may end up with recursive calls to this summary. For example, if in the summary of `foo` we call the Solidity function `bar`, and `bar`’s Solidity code contains a call to `foo`, we’ll summarize `foo` again, which will lead to another call to `bar` etc. In this case if this flag is set to `false` we may get an assertion failure with a message along the lines of
```
Recursion limit (...) for calls to ..., reached during compilation of summary ...

```
Copy to clipboard
Such recursion can also happen with [dispatcher summaries](https://docs.certora.com/en/latest/docs/cvl/methods.html#dispatcher) — if a contract method `f` makes an unresolved external call to a different method `f`, and if `f` is summarized with a `DISPATCHER` summary, then the Prover will consider paths where `f` recursively calls itself. Without `--optimistic_summary_recursion`, the Prover may report a rule violation with the following assert message:
```
When summarizing a call with dispatcher, found we already have it in the stack: ... consider removing its dispatcher summary.

```
Copy to clipboard
The default behavior in this case is to assert that the recursion limit is not reached (the limit is controlled by the [summary_recursion_limit](https://docs.certora.com/en/latest/docs/prover/cli/options.html#summary-recursion-limit) flag). With `--optimistic_summary_recursion`, the Prover will instead assume that the limit is never reached.
**When to use it?** Use this flag when there is recursion due to summaries calling Solidity functions, and this causes an undesired assertion failure. In this case one can either make the limit larger (via [summary_recursion_limit](https://docs.certora.com/en/latest/docs/prover/cli/options.html#summary-recursion-limit)) or set this flag to `true`.
**Example**
```
certoraRunBank.sol--verifyBank:Bank.spec--optimistic_summary_recursion

```
Copy to clipboard
Caution
This flag could cause unsoundness - even if such recursion _could_ actually happen in the deployed contract, this code-path won’t be verified.
## [`summary_recursion_limit`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id106)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#summary-recursion-limit "Link to this heading")
**Usage**
```
--summary_recursion_limit<n>

```
Copy to clipboard
**What does it do?** Summaries can cause recursion (see [optimistic_summary_recursion](https://docs.certora.com/en/latest/docs/prover/cli/options.html#optimistic-summary-recursion)). This option sets the summary recursion level, which is the number of recursive calls that the Prover will consider.
If the Prover finds an execution in which a function is called recursively more than the contract recursion limit, the Prover will report an assertion failure (unless [optimistic_summary_recursion](https://docs.certora.com/en/latest/docs/prover/cli/options.html#optimistic-summary-recursion) is set, in which case the execution will be ignored). The default value is zero (i.e. no recursion is allowed).
**When to use it?**
  1. Use this option when there is recursion due to summaries calling Solidity functions, and this leads to an assertion failure. In this case one can either make the limit larger or set (via [optimistic_summary_recursion](https://docs.certora.com/en/latest/docs/prover/cli/options.html#optimistic-summary-recursion)) flag to `true`.
  2. Use it if you get the following assertion failure, and disabling [optimistic fallback](https://docs.certora.com/en/latest/docs/prover/cli/options.html#optimisticfallback) is not possible:


```
When inlining a fallback function, found it was already on the stack. Consider disabling optimistic fallback mode.

```
Copy to clipboard
**Example**
```
certoraRunBank.sol--verifyBank:Bank.spec--summary_recursion_limit3

```
Copy to clipboard
# [Options regarding hashing of unbounded data](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id107)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#options-regarding-hashing-of-unbounded-data "Link to this heading")
## [`optimistic_hashing`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id108)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#optimistic-hashing "Link to this heading")
**What does it do?**
When hashing data of potentially unbounded length (including unbounded arrays, like `bytes`, `uint[]`, etc.):
  1. If `optimistic_hashing` is set the Proves _assumes_ the data’s length is bounded by the `--hashing_length_bound` option.
  2. If `optimistic_hashing` is not set, the Prover will check whether the data’s length can exceed the `hashing_length_bound`, and report an assertion violation if it can.


See [Hashing of unbounded data](https://docs.certora.com/en/latest/docs/prover/approx/hashing.html#hashing-unbounded) for more details.
**When to use it?**
When the assertion regarding unbounded hashing is thrown, but it is acceptable for the Prover to ignore cases where the length hashed values exceeds the current bound.
**Example**
```
certoraRunBank.sol--verifyBank:Bank.spec--optimistic_hashing

```
Copy to clipboard
## [`hashing_length_bound`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id109)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#hashing-length-bound "Link to this heading")
**Usage**
```
--hashing_length_bound<n>

```
Copy to clipboard
**What does it do?**
Constraint on the maximal length of otherwise unbounded data chunks that are being hashed. This constraint is either assumed or checked by the Prover, depending on whether `--optimistic_hashing` has been set. The bound is specified as a number of bytes.
The default value of this option is 224 (224 bytes correspond to 7 EVM machine words as 7 * 32 == 224).
**When to use it?** Reason to lower this value:
Lowering potentially improves SMT performance, especially if there are many occurrences of unbounded hashing in the program.
Reasons to raise this value:
  * when `--optimistic_hashing` is not set: avoid the assertion being violated when the hashed values are actually bounded, but by a bound that is higher than the default value (in case of `--optimistic_hashing` being not set)
  * when `--optimistic_hashing` is set: find bugs that rely on a hashed array being at least of that length. (Optimistic hashing excludes all cases from the scope of verification where something being hashed is longer than this bound.)


**Example**
```
certoraRunBank.sol--verifyBank:Bank.spec--hashing_length_bound128

```
Copy to clipboard
# [Options that help reduce the running time](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id110)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#options-that-help-reduce-the-running-time "Link to this heading")
## [`compilation_steps_only`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id111)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#compilation-steps-only "Link to this heading")
**What does it do?** Exits the program after source code and spec compilation without sending a verification request to the cloud.
**When to use it?** Use it to check if the spec has correct syntax but do not wish to send a verification request and wait for its results.
Here are a few example scenarios:
  1. When writing hooks, ghosts, summaries, or CVL functions, you can verify the spec before continuing to write rules.
  2. In CI, you can check CVL correctness after every PR but run the expensive and long verification only on nightly runs.
  3. When you have no internet connection but still want to develop spec offline.


**Example**
```
certoraRunExample.sol--verifyExample:Example.spec--compilation_steps_only

```
Copy to clipboard
## [`disable_local_type_checking`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id112)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#disable-local-type-checking "Link to this heading")
**What does it do?**
This flag disables the local syntax and type checking of your CVL specifications before they are sent to the cloud for verification. When used, simple syntax or type errors will not be caught locally and will only become visible during the cloud run, potentially causing unnecessary delays and confusion.
**When to use it?**
This flag should only be used in rare cases when you believe the local syntax or type checking has produced an incorrect error, and you are confident that the specification is valid. Before using this flag, it is recommended to first attempt reinstalling the Prover by following the instructions in the [Installation](https://docs.certora.com/en/latest/docs/user-guide/install.html#installation) section. Using this flag is **strongly discouraged** as it bypasses an essential layer of error detection, increasing the likelihood of issues being encountered later during the verification process.
**Example**
```
certoraRunMyContract.sol--verifyMyContract:MySpec--disable_local_typechecking

```
Copy to clipboard
Caution
Avoid using this flag unless absolutely necessary. It is always better to fix syntax or type issues locally to ensure a smoother verification process.
## [`global_timeout`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id113)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#global-timeout "Link to this heading")
**Usage**
```
--global_timeout<seconds>

```
Copy to clipboard
**What does it do?**
Sets the maximal timeout for the Prover. Gets an integer input, which represents seconds.
The Certora Prover is bound to run a maximal time of 2 hours (7200 seconds). Users may opt to set this number lower to facilitate faster iteration on specifications. Values larger than two hours (7200 seconds) are ignored.
Jobs that exceed the global timeout will simply be terminated, so the result reports may not be generated.
The global timeout is different from the [smt_timeout](https://docs.certora.com/en/latest/docs/prover/cli/options.html#smt-timeout) option: the `--smt_timeout` flag constrains the amount of time allocated to the processing of each individual rule, while the `--global_timeout` flag constrains the processing of the entire job, including static analysis and other preprocessing.
**When to use it?** When running on just a few rules, or when willing to make faster iterations on specs without waiting too long for the entire set of rules to complete.
Note
Even if in the shorter running time not all rules were processed, a second run may pull some results from cache, and therefore more results will be available.
**Example**
```
certoraRunBank.sol--verifyBank:Bank.spec--global_timeout60

```
Copy to clipboard
## [`method`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id114)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id37 "Link to this heading")
See [method](https://docs.certora.com/en/latest/docs/prover/cli/options.html#method)
## [`smt_timeout`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id115)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#smt-timeout "Link to this heading")
**Usage**
```
--smt_timeout<seconds>

```
Copy to clipboard
**What does it do?** Sets the maximal timeout for all the [SMT solvers](https://en.wikipedia.org/wiki/Satisfiability_modulo_theories). Gets an integer input, which represents seconds.
The Certora Prover generates a logical formula from the specification and source code. Then, it passes it on to an array of SMT solvers. The time it can take for the SMT solvers to solve the equation is highly variable, and could potentially be infinite. This is why they must be limited in run time.
The SMT timeout applies separately to each individual rule (or each method for parametric rules). To set the global timeout, see [global_timeout](https://docs.certora.com/en/latest/docs/prover/cli/options.html#global-timeout).
Note
While this is the most prominent timeout, this is not the only timeout that applies to SMT solvers, for details see [mediumTimeout](https://docs.certora.com/en/latest/docs/prover/cli/options.html#mediumtimeout) and [Control flow splitting](https://docs.certora.com/en/latest/docs/prover/techniques/index.html#control-flow-splitting).
**When to use it?** The default time out for the solvers is 300 seconds. There are two use cases for this option. One is to decrease the timeout. This is useful for simple rules, that are solved quickly by the SMT solvers. Here, it is beneficial to reduce the timeout, so that when a new code breaks the specification, the tool will fail quickly. This is the more common use case. The second use is when the solvers can prove the property, they just need more time. Usually, if the rule isn’t solved in 600 seconds, it will not be solved in 2,000 either. It is better to concentrate your efforts on simplifying the rule, the source code, add more summaries, or use other time-saving options. The prime causes for an increase of `--smt_timeout` are rules that are solved quickly, but time out when you add a small change, such as a requirement, or changing a strict inequality to a weak inequality.
**Example**
```
certoraRunBank.sol--verifyBank:Bank.spec--smt_timeout300

```
Copy to clipboard
# [Options to set addresses and link contracts](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id116)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#options-to-set-addresses-and-link-contracts "Link to this heading")
## [`address`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id117)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#address "Link to this heading")
**Usage**
```
--address<contract>:<address>

```
Copy to clipboard
**What does it do?** Sets the address of a contract to a given address.
**When to use it?** When we have an external contract with a constant address. By default, the Python script assigns addresses as it sees fit to contracts.
**Example**
If we wish the `Oracle` contract to be at address 12, we use
```
certoraRunBank.solOracle.sol--verifyBank:Bank.spec--addressOracle:12

```
Copy to clipboard
## [`contract_extensions`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id118)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#contract-extensions "Link to this heading")
**What does it do?** In order to support extendability and upgradeability of smart contracts, the proxy pattern is used. In this patterns there is a base contract (the proxy) which delegate-calls into “extension” contracts (read this [explanation](https://docs.openzeppelin.com/upgrades-plugins/1.x/proxies) for more details). This flag allows specifying that some contract is actually an extension of another one, to help the Prover analyze low-level calls and resolve them correctly in this case. In practice the Prover “moves” all the external function implementations from the extension contract into the base contract, which means that to access them from CVL one should use the _base_ contract as the receiver, and not the extension contract.
**When to use it?** If you use the proxy pattern in your smart contracts.
**Example** Say we have a base contract `A` that uses an extension contract `B`. Since in this pattern the storage of the two contracts may “overlap”, let’s also assume they both have some `uint public n`. In the .conf file one should add
```
"contract_extensions":{
"A":[
{
"extension":"B",
"exclude":["n"]
}
]
}

```
Copy to clipboard
This tells the prover that `B` is an extension contract of `A`, but that it shouldn’t “transfer” the getter for n from the extension into the base contract (since the base contract already has such a function and this would cause a conflict).
[For a more detailed example click here.](https://github.com/Certora/Examples/tree/master/CVLByExample/ExtensionContracts)
## [`contract_recursion_limit`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id119)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#contract-recursion-limit "Link to this heading")
**Usage**
```
--contract_recursion_limit<n>

```
Copy to clipboard
**What does it do?** Contract inlining can cause recursion (see [optimistic_contract_recursion](https://docs.certora.com/en/latest/docs/prover/cli/options.html#optimistic-contract-recursion)). This option sets the contract recursion level, which is the number of recursive calls that the Prover will consider when inlining contracts linked using, e.g., `--link` or `--struct_link`.
Note
In this context, recursion refers to the state where the same _external_ function appears twice in the call stack. Contracts can also exhibit recursive behavior due to recursive calls to _internal_ functions, which is unrelated to this option.
If a counterexample causes a function to be called recursively more than the contract recursion limit, it will report an assertion failure (unless [optimistic_contract_recursion](https://docs.certora.com/en/latest/docs/prover/cli/options.html#optimistic-contract-recursion) is set, in which case the counterexample will be ignored). The default value is zero (i.e., no recursion is allowed).
**When to use it?** Use this option when after linking the resulting program may have paths with recursive calls to external Solidity functions, and this leads to a recursion-specific assertion failure, showing the message `Contract recursion limit reached`. In this case one can either make the limit larger or set `--optimistic_contract_recursion` flag to `true`.
Note
Increasing the limit is not always sufficient, as the code may in fact allow theoretically unbounded recursion.
**Example**
```
certoraRunBank.sol--verifyBank:Bank.spec--contract_recursion_limit3

```
Copy to clipboard
## [`link`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id120)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#link "Link to this heading")
**Usage**
```
--struct_link<contract>:<slot>=<address>

```
Copy to clipboard
**What does it do?** Links a slot in a contract with another contract.
**When to use it?** Many times a contract includes the address of another contract as one of its fields. If we do not use `--link`, it will be interpreted as any possible address, resulting in many nonsensical counterexamples.
**Example** Assume we have the contract `Bank.sol` with the following code snippet: `IERC20 public underlyingToken;`
We have a contract `BankToken.sol`, and `underlyingToken` should be its address. To do that, we use:
```
certoraRunBank.solBankToken.sol--verifyBank:Bank.spec--linkBank:underlyingToken=BankToken

```
Copy to clipboard
## [`optimistic_contract_recursion`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id121)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#optimistic-contract-recursion "Link to this heading")
**What does it do?** Contract linking can cause recursion (see also [contract_recursion_limit](https://docs.certora.com/en/latest/docs/prover/cli/options.html#contract-recursion-limit)). This option sets the Prover to optimistically assume that recursion cannot go beyond what is defined by [contract_recursion_limit](https://docs.certora.com/en/latest/docs/prover/cli/options.html#contract-recursion-limit), but only if [contract_recursion_limit](https://docs.certora.com/en/latest/docs/prover/cli/options.html#contract-recursion-limit) is set to a number higher than 0.
**When to use it?**
  1. When the recursion due to contract linking is unbounded.
  2. When we are interested only in a limited recursion depth due to contract linking.


Caution
This flag could be another cause for unsoundness - even if such recursion _could_ actually happen in the deployed contract, this code-path won’t be verified beyond the specified recursion limit ([contract_recursion_limit](https://docs.certora.com/en/latest/docs/prover/cli/options.html#contract-recursion-limit)).
**Example**
```
certoraRunBank.sol--verifyBank:Bank.spec--optimistic_contract_recursiontrue--contract_recursion_limit1

```
Copy to clipboard
## [`optimistic_fallback`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id122)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#optimistic-fallback "Link to this heading")
**What does it do?**
This option controls how the Prover handles unresolved external calls with an empty input buffer (length 0). By default, such calls will havoc all storage state of external contracts. When `--optimistic_fallback` is enabled, these calls will instead:
  * Execute the fallback function in the specified contract (if it exists).
  * Revert if no fallback function is available.
  * Execute a transfer if applicable.


This modifies the behavior of [AUTO summaries](https://docs.certora.com/en/latest/docs/cvl/methods.html#auto-summary) by preventing unnecessary state havoc for empty input calls.
**When to use it?**
Enable this option to avoid spurious counter examples for external calls with empty input buffers.
**Example**
```
certoraRunBank.sol--verifyBank:Bank.spec--optimistic_fallback

```
Copy to clipboard
## [`struct_link`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id123)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#struct-link "Link to this heading")
**Usage**
```
--struct_link<contract>:<slot>=<address>

```
Copy to clipboard
**What does it do?** Links a slot in a struct with another contract. To do that you must calculate the slot number of the field you wish to replace.
**When to use it?** Many times a contract includes the address of another contract inside a field of one of its structs. If we do not use `--struct_link`, it will be interpreted as any possible address, resulting in many nonsensical counterexamples.
**Example** Assume we have the contract `Bank.sol` with the following code snippet: `TokenPair public tokenPair;`
Where `TokenPair` is
```
structTokenPair{
IERC20tokenA;
IERC20tokenB;
}

```
Copy to clipboard
We have two contracts `BankToken.sol` and `LoanToken.sol`. We want `tokenA` of the `tokenPair` to be `BankToken`, and `tokenB` to be `LoanToken`. Addresses take up only one slot. We assume `tokenPair` is the first field of Bank (so it starts at slot zero). To do that, we use:
```
certoraRunBank.solBankToken.solLoanToken.sol--verifyBank:Bank.spec--struct_linkBank:0=BankTokenBank:1=LoanToken

```
Copy to clipboard
# [Options for job metadata and dashboard filtering](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id124)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#options-for-job-metadata-and-dashboard-filtering "Link to this heading")
This section includes flags that annotate verification runs with additional metadata. These options don’t affect verification results but make it easier to track jobs, filter them in the [dashboard](https://prover.certora.com/), or manage runs across multiple protocols.
## [`msg`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id125)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id46 "Link to this heading")
See [msg](https://docs.certora.com/en/latest/docs/prover/cli/options.html#msg).
## [`protocol_author`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id126)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#protocol-author "Link to this heading")
**Usage**
```
--protocol_author<name>

```
Copy to clipboard
**What does it do?** This option adds an author name to the job metadata, allowing you to filter or group verification runs by the protocol author in the [dashboard](https://prover.certora.com/).
If not explicitly provided, the Prover will attempt to extract the author from the author field in your `package.json` file (if it exists).
**When to use it?** Use this flag to help track who owns or has submitted each verification run, particularly in verification projects with multiple authors.
**Example**
```
certoraRunBank.sol--verifyBank:Bank.spec--protocol_author"OpenDeFi Labs"

```
Copy to clipboard
## [`protocol_name`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id127)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#protocol-name "Link to this heading")
**Usage**
```
--protocol_name<name>

```
Copy to clipboard
**What does it do?** Sets the protocol name associated with the verification job. This name will appear in the [Prover dashboard](https://prover.certora.com/) and can be used to filter or group related jobs. If this flag is not explicitly provided, the tool will attempt to use the name field from `package.json` if available.
**When to use it?** Use this flag to clearly label your jobs. This is especially useful when verifying multiple projects in parallel.
**Example**
```
certoraRunVault.sol--verifyVault:Vault.spec--protocol_nameMyDeFiProtocol

```
Copy to clipboard
# [Options for controlling contract creation](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id128)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#options-for-controlling-contract-creation "Link to this heading")
## [`dynamic_bound`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id129)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#dynamic-bound "Link to this heading")
**Usage**
```
--dynamic_bound<n>

```
Copy to clipboard
**What does it do?** If set to zero (the default), contract creation (via the `new` statement or the `create`/`create2` instructions) will result in a havoc, like any other unresolved external call. If non-zero, then dynamic contract creation will be modeled with cloning, where each contract will be cloned at most n times.
**When to use it?** When you wish to model contract creation, that is, simulating the actual creation of the contract. Without it, `create` and `create2` commands simply return a fresh address; the Prover does not model their storage, code, constructors, immutables, etc. Any interaction with these generated addresses is modeled imprecisely with conservative havoc.
**Example** Suppose a contract `C` creates a new instance of a contract `Foo`, and you wish to inline the constructor of `Foo` at the creation site.
```
certoraRunC.solFoo.sol--verifyC:C.spec--dynamic_bound1

```
Copy to clipboard
## [`dynamic_dispatch`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id130)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#dynamic-dispatch "Link to this heading")
**What does it do?** By default, contract method invocations on newly created instances remain unresolved, requiring explicit [ DISPATCHER](https://docs.certora.com/en/latest/docs/cvl/methods.html#dispatcher) summaries for all such method calls. With this option, the Prover will automatically apply the `DISPATCHER` summary on a best-effort basis for call sites where the receiver is proven to be a newly created contract.
**Limitations**
  * This option only applies when the Prover can prove that the callee is a created contract.
  * If a contract instance is assigned from both a newly created contract and another source (e.g., storage), calls will remain unresolved. For example:


```
MyFoof;
if(*){
f=newMyFoo(...);
}else{
f=storageStruct.myFoo;
}
f.bar();

```
Copy to clipboard
**When to use it?** Use this flag when you prefer not to manually add explicit `DISPATCHER` summaries for methods invoked by the created contract.
**Example** Suppose a contract `C` creates a new instance of a contract `Foo`, and you wish to inline the constructor of `Foo` at the creation site, and `Foo` calls some method `m()` which you wish to automatically link to the newly created contract.
```
certoraRunC.solFoo.sol--verifyC:C.spec--dynamic_bound1--dynamic_dispatch

```
Copy to clipboard
Note
You must also use the [dynamic_bound](https://docs.certora.com/en/latest/docs/prover/cli/options.html#dynamic-bound) option.
## [`prototype`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id131)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#prototype "Link to this heading")
**Usage**
```
--prototype<hexstring>=<contract>

```
Copy to clipboard
**What does it do?** Instructs the Prover to use a specific contract type for the return value from a call to `create` or `create2` on the given hexadecimal string as a prefix. The hexadecimal string represents proxy code that forwards calls to another contract. As we are using the prototype flag to skip calls to the proxy, no constructor code is being simulated for these contract creation resolutions.
**When to use it?** If you are verifying a contract creation that uses low level calls to `create` or `create2` for contract creation.
**Example** Suppose you have a contract `C` that creates another contract `Foo` like this:
```
assembly{
letptr:=mload(0x40)
mstore(ptr,0x3d602d80600a3d3981f3363d3d373d3d3d363d73000000000000000000000000)
mstore(add(ptr,0x14),shl(0x60,implementation))
mstore(add(ptr,0x28),0x5af43d82803e903d91602b57fd5bf30000000000000000000000000000000000)
instance:=create(0,ptr,0x37)
}

```
Copy to clipboard
Then you can set the string `3d602d80600a3d3981f3363d3d373d3d3d363d73` appearing in the first `mstore` after the `0x` prefix as a “prototype” for `Foo`. The Prover will then be able to create a new instance of `Foo` at the point where the code creates it:
```
certoraRunC.solFoo.sol--verifyC:C.spec--prototype3d602d80600a3d3981f3363d3d373d3d3d363d73=Foo--dynamic_bound1

```
Copy to clipboard
Note
This argument has no effect if the [dynamic bound](https://docs.certora.com/en/latest/docs/prover/cli/options.html#dynamic-bound) is zero.
Note
The hex string must be:
  * A strict prefix of the memory region passed to the create command.
  * Must be unique within each invocation of the tool.
  * Must not contain gaps, e.g., `3d602d80600a3d3981f3363d3d373d3d3d363d730000` in the above example will not work (those last four bytes will be overwritten) but `3d602d80600a3d3981f3363d3d373d3d3d363d` will.


# [Version options](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id132)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#version-options "Link to this heading")
## [`version`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id133)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#version "Link to this heading")
**What does it do?** Shows the version of the local installation of `certora-cli` you have.
**When to use it?** When you suspect you have an old installation. To install the newest version, use `pip install --upgrade certora-cli`.
**Example**
```
certoraRun--version

```
Copy to clipboard
## [`prover_version`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id134)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#prover-version "Link to this heading")
**Usage**
```
--prover_version<branch_name>

```
Copy to clipboard
**What does it do?** This option lets you select a specific version of the Certora Prover by providing the name of a Git branch from the Prover repository. It does not accept individual commit hashes.
**When to use it?** Use this flag to reproduce behavior from an earlier version of the Prover, which is especially useful when features have been changed or deprecated in newer releases. The most common use case is specifying one of the release branches (e.g., release/10April2025) to match the behavior of a known version.
# [Conf file options](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id135)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#conf-file-options "Link to this heading")
## [`override_base_config`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id136)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#override-base-config "Link to this heading")
**What does it do?** Allows you to import flags from another conf file. The `--override_base_config` gets as a value a path to the imported conf file. If the path is relative, it is relative to the current working directory, regardless of the original conf file’s location. Flags in the imported conf file will be overridden if the same flag appears also in the original conf file or in the command line. It is only possible to import from a single conf file and the imported conf file cannot import from yet another conf file.
**When to use it?** When you want to use the same flags for multiple runs, but with some small changes. For example, you can have a base config file with all the flags you need, and then create a new conf file that imports the base one and overrides only the flags you want to change.
Using a base configuration file saves you from repeatedly writing the same flags in the command line or other configuration files.
**Example**
```
certoraRunproj.conf--override_base_configconfs/base_settings.conf

```
Copy to clipboard
**Example** To run verification using the Prover version from the April 10, 2025 release:
```
certoraRunMyContract.sol--verifyMyContract:MySpec.spec--prover_versionrelease/10April2025

```
Copy to clipboard
# [Advanced options](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id137)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#advanced-options "Link to this heading")
## [`java_args`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id138)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#java-args "Link to this heading")
**What does it do?**
Allows setting configuring the underlying JVM.
**When to use it?**
Upon instruction from the Certora team.
**Example**
`--java_args '"-Dcvt.default.parallelism=2"'` - will set the number of “tasks” that can run in parallel to 2.
## [`precise_bitwise_ops`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id139)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#precise-bitwise-ops "Link to this heading")
**What does it do?** This option models bitwise operations exactly, instead of using the default [overapproximation](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-overapproximation). It is useful when the Prover reports a counterexample caused by incorrect modeling of bitwise operations, but enabling this option can significantly increase verification time.
**Limitations**
  * This encoding does not model `mathint` precisely.
  * The maximum supported integer value is 2256−1, effectively restricting `mathint` to a `uint256`.
  * There is currently no encoding that precisely models both bitwise operations and `mathint` simultaneously.


**When to use it?** Use this option if a counterexample suggests that incorrect modeling of bitwise operations is affecting verification results.
**Example**
```
certoraRunBank.sol--verifyBank:Bank.spec--precise_bitwise_ops

```
Copy to clipboard
## [`prover_args`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id140)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#prover-args "Link to this heading")
The `--prover_args` option allows you to provide fine-grained tuning options to the Prover. `--prover_args` receives a string containing Prover-specific options, and will be sent as-is to the Prover. `--prover_args` cannot set Prover options that are set by standalone `certoraRun` options (e.g. the Prover option `--t` is set by `--smt_timeout` therefore cannot appear in `--prover_args`). `--prover_args` value must be quoted.
### [`enableStorageSplitting`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id141)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#enablestoragesplitting "Link to this heading")
This option disables the storage splitting optimization.
**Usage**
```
--prover_args'-enableStorageSplitting false'

```
Copy to clipboard
### [`maxNumberOfReachChecksBasedOnDomination`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id142)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#maxnumberofreachchecksbasedondomination "Link to this heading")
This option sets the number of program points to test with the `deepSanity` built-in rule. See [Thorough complexity checks — deepSanity](https://docs.certora.com/en/latest/docs/cvl/builtin.html#built-in-deep-sanity).
**Usage**
```
--prover_args'-maxNumberOfReachChecksBasedOnDomination <n>'

```
Copy to clipboard
### [`optimisticReturnsize`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id143)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#optimisticreturnsize "Link to this heading")
This option determines whether [havoc summaries](https://docs.certora.com/en/latest/docs/cvl/methods.html#havoc-summary) assume that the called method returns the correct number of return values. It will set the value returned by the `RETURNSIZE` EVM instruction according to the called method.
Note
Certain conditions should hold in order for the option to take effect. Namely, if there is a single candidate method in the havoc site, and all instances of this method in the [scene](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-0) have exactly the same expected number of return values, then the `RETURNSIZE` value will be set to the expected size matching the methods in the scene. Otherwise, `RETURNSIZE` will remain non-deterministic.
**Usage**
```
--prover_args'-optimisticReturnsize true'

```
Copy to clipboard
### [`smt_groundQuantifiers`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id144)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#smt-groundquantifiers "Link to this heading")
This option disables quantifier grounding. See [Quantifier Grounding](https://docs.certora.com/en/latest/docs/prover/approx/grounding.html#grounding) for more information.
**Usage**
```
--prover_args'-smt_groundQuantifiers false'

```
Copy to clipboard
### [`superOptimisticReturnsize`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id145)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#superoptimisticreturnsize "Link to this heading")
This option determines whether [havoc summaries](https://docs.certora.com/en/latest/docs/cvl/methods.html#havoc-summary) assume that the called method returns the correct number of return values. It will set the value returned by the `RETURNSIZE` EVM instruction to the size of the output buffer as specified by the summarized `CALL` instruction.
**Usage**
```
--prover_args'-superOptimisticReturnsize true'

```
Copy to clipboard
## [Control flow splitting options](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id146)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#control-flow-splitting-options "Link to this heading")
See [here](https://docs.certora.com/en/latest/docs/prover/techniques/index.html#control-flow-splitting) for an explanation of control flow splitting.
### [`depth`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id147)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#depth "Link to this heading")
**Usage**
```
--prover_args'-depth <number>'

```
Copy to clipboard
**What does it do?**
Sets the maximum splitting depth.
**When to use it?**
When the deepest [split](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-split)s are too heavy to solve, but not too high in number, increasing this will lead to smaller, but more numerous [split leaves](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-split-leaves), which run at the full SMT timeout (as set by [smt_timeout](https://docs.certora.com/en/latest/docs/prover/cli/options.html#smt-timeout)). Conversely, if run time is too high because there are too many splits, decreasing this number means that more time is spent on fewer, but bigger split leaves. The default value for this option is 10.
**Example**
```
certoraRunBank.sol--verifyBank:bank.spec--prover_args'-depth 5'

```
Copy to clipboard
### [`dontStopAtFirstSplitTimeout`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id148)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#dontstopatfirstsplittimeout "Link to this heading")
**Usage**
```
--prover_args'-dontStopAtFirstSplitTimeout <true/false>'

```
Copy to clipboard
**What does it do?**
We can tell the Certora Prover to continue even when the a [split](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-split) has had a maximum-depth timeout. Note that this is only useful when there exists a [counterexample](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-counterexample) for the rule under verification, since in order to prove the absence of counterexamples (i.e. correctness), all splits need to be counterexample-free. (In case of a rule using `satisfy` rather than `assert`, the corresponding statements hold for [witness example](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-witness-example)s. In that case, this option is only useful if the rule is correct.)
**When to use it?**
When looking for a SAT result and observing an [SMT-type timeout](https://docs.certora.com/en/latest/docs/user-guide/out-of-resources/timeout.html#timeouts-introduction). The default value for this option is `false`.
**Example**
```
certoraRunBank.sol--verifyBank:bank.spec--prover_args'-dontStopAtFirstSplitTimeout true'

```
Copy to clipboard
### [`mediumTimeout`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id149)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#mediumtimeout "Link to this heading")
The “medium timeout” determines how much time the SMT solver gets for checking a [split](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-split) that is not a [split leaf](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-split-leaf). (For split leaves, the full [smt_timeout](https://docs.certora.com/en/latest/docs/prover/cli/options.html#smt-timeout) is used.)
**Usage**
```
--prover_args'-mediumTimeout <seconds>'

```
Copy to clipboard
**What does it do?**
Sets the time that non-leaf splits get before being split again.
**When to use it?**
When a little more time can close some splitting subtrees early, this can save a lot of time, since the subtree’s size is exponential in the remaining depth. On the other hand, if something will be split further anyway, this can save the run time spent on intermediate “TIMEOUT” results. Use [smt_initialSplitDepth](https://docs.certora.com/en/latest/docs/prover/cli/options.html#smt-initialsplitdepth) to eliminate that time investment altogether up to a given depth.
**Example**
```
certoraRunBank.sol--verifyBank:bank.spec--prover_args'-mediumTimeout 20'

```
Copy to clipboard
### [`smt_initialSplitDepth`](https://docs.certora.com/en/latest/docs/prover/cli/options.html#id150)[](https://docs.certora.com/en/latest/docs/prover/cli/options.html#smt-initialsplitdepth "Link to this heading")
With this option, the splitting can be configured to skip the SMT solver-based checks at low splitting levels, thus generating sub-[split](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-split)s up to a given depth immediately.
**Usage**
```
--prover_args'-smt_initialSplitDepth <number>'

```
Copy to clipboard
**What does it do?**
The first `<number>` split levels are not checked with the SMT solver, but rather split immediately.
**When to use it?**
When there is a lot of overhead induced by processing and trying to solve splits that are very hard, and thus run into a timeout anyway.
Note
The number of splits generated here is equal to 2n where `n` is the initial splitting depth (assuming the program has enough branching points, which is usually the case); thus, low numbers are advisable. For instance setting this to 5 means that the Prover will immediately produce 32 splits.
Note
The [depth](https://docs.certora.com/en/latest/docs/prover/cli/options.html#depth) setting has precedence over this setting. I.e., if `-depth` is set to a lower value than `-smt_initialSplitDepth`, the initial splitting will only proceed up to the splitting depth given via `-depth`.
**Example**
```
certoraRunBank.sol--verifyBank:bank.spec--prover_args'-smt_initialSplitDepth 3'

```
Copy to clipboard
[ Previous](https://docs.certora.com/en/latest/docs/prover/cli/index.html "Certora Prover CLI") [Next ](https://docs.certora.com/en/latest/docs/prover/cli/conf-file-api.html "Configuration \(Conf\) Files")
© Copyright 2025, Certora, Inc.
Built with [Sphinx](https://www.sphinx-doc.org/) using a [theme](https://github.com/readthedocs/sphinx_rtd_theme) provided by [Read the Docs](https://readthedocs.org). 
