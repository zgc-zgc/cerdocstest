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
      * [Using Configuration (Conf) Files](https://docs.certora.com/en/latest/docs/solana/options.html#using-configuration-conf-files)
      * [Modes of Operation](https://docs.certora.com/en/latest/docs/solana/options.html#modes-of-operation)
        * [`--build_script`](https://docs.certora.com/en/latest/docs/solana/options.html#build-script)
      * [Most Frequently Used Options](https://docs.certora.com/en/latest/docs/solana/options.html#most-frequently-used-options)
        * [`--rule`](https://docs.certora.com/en/latest/docs/solana/options.html#rule)
        * [`--solana_inlining`](https://docs.certora.com/en/latest/docs/solana/options.html#solana-inlining)
        * [`--solana_summaries`](https://docs.certora.com/en/latest/docs/solana/options.html#solana-summaries)
        * [`--cargo_features`](https://docs.certora.com/en/latest/docs/solana/options.html#cargo-features)
        * [`--msg`](https://docs.certora.com/en/latest/docs/solana/options.html#msg)
        * [`--rule_sanity`](https://docs.certora.com/en/latest/docs/solana/options.html#rule-sanity)
      * [`--multi_assert_check`](https://docs.certora.com/en/latest/docs/solana/options.html#multi-assert-check)
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
  * Solana-Specific Options / CLI Flags
  * [ View page source](https://docs.certora.com/en/latest/_sources/docs/solana/options.md.txt)


# Solana-Specific Options / CLI Flags[](https://docs.certora.com/en/latest/docs/solana/options.html#solana-specific-options-cli-flags "Link to this heading")
This page documents Solana-specific Certora Prover options, which include CLI flags or `prover_args` flags.
The `certoraSolanaProver` utility invokes the Rust compiler and then sends the job to Certora’s servers.
The most commonly used command is:
```
certoraSolanaProver--build_script<path_to_build_script>--rule<rule_name>

```
Copy to clipboard
If a precompiled execution is desired, the run command can skip the compilation step by executing:
```
certoraSolanaProver<path_to_binary_file>--rule<rule_name>

```
Copy to clipboard
A short summary of these options can be seen by invoking:
```
certoraSolanaProver--help

```
Copy to clipboard
## Using Configuration (Conf) Files[](https://docs.certora.com/en/latest/docs/solana/options.html#using-configuration-conf-files "Link to this heading")
For larger projects, the command line for running the Certora Prover can become large and cumbersome. It is therefore recommended to use configuration files instead. These files are in [JSON5](https://json5.org/) format and use a `.conf` extension. They hold the parameters and options for the Prover. For more details, see [Conf File](https://docs.certora.com/en/latest/docs/prover/cli/conf-file-api.html#conf-files).
## Modes of Operation[](https://docs.certora.com/en/latest/docs/solana/options.html#modes-of-operation "Link to this heading")
The Certora Solana Prover has two modes of operation, using a build script, or passing a precompiled binary directly. These modes are mutually exclusive - you cannot run the tool with more than one mode at a time. Both modes require the user to specify which rules must be verified by using the `--rule` option.
### `--build_script`[](https://docs.certora.com/en/latest/docs/solana/options.html#build-script "Link to this heading")
**What does it do?**
Specifies the location of the script that has to be called to compile the Rust project. The build script should output 0 on success and 1 on failure unless it’s being executed using the `--json` flag. In this case, the build script should output the following:
  * `project_directory`: Path to the project root directory.
  * `sources`: List of source files or directories used or imported in the program. Source files should be relative to the `project_directory` with support of wildcards. All files declared in this list will be uploaded as sources to the cloud and displayed in the rule report. Source files are required, for instance, for the jump to source feature to work.
  * `executables`: List of compiled binary files, which are the target of the Rust program.
  * `success`: Boolean flag indicating if the build phase passed successfully.
  * `return_code`: The return code of the script.
  * `log`: Optionally provided paths to files for `stdout` and `stderr` of the build logs.
  * `solana_inlining`: List of paths to [inlining](https://docs.certora.com/en/latest/docs/solana/options.html#solana-inlining) files for Solana programs.
  * `solana_summaries`: List of paths to [summaries](https://docs.certora.com/en/latest/docs/solana/options.html#solana-summaries) files for Solana programs.


See an example of a [build script](https://github.com/Certora/SolanaExamples/blob/main/cvlr_by_example/first_example/certora_build.py) and refer to the [usage](https://docs.certora.com/en/latest/docs/solana/usage.html) section for more information about it.
**When to use it?**
Use this mode to prove properties on source code while providing an automatic compilation method. This is especially useful during development when files are modified frequently.
**Example**
```
certoraSolanaProver--build_script<path_to_build_script>--rule<rule_name>

```
Copy to clipboard
Note: If you want to skip compilation process and run on a precompiled Rust project it’s possible to provide a path to the binary target file instead
```
certoraSolanaProver<path_to_binary_file>--rule<rule_name>

```
Copy to clipboard
## Most Frequently Used Options[](https://docs.certora.com/en/latest/docs/solana/options.html#most-frequently-used-options "Link to this heading")
### `--rule`[](https://docs.certora.com/en/latest/docs/solana/options.html#rule "Link to this heading")
**What does it do?**
Formally verifies one or more specified rules.
**When to use it?**
This option is always required to specify which rules the Prover should verify.
**Example**
If a Rust module includes the following:
```
#[rule]
fnrule_withdraw_succeeds(){
...
}
#[rule]
fnrule_withdraw_fails(){
...
}

```
Copy to clipboard
To verify only `rule_withdraw_succeeds`, run:
```
certoraSolanaProver--build_script<path_to_build_script>--rulerule_withdraw_succeeds

```
Copy to clipboard
To verify both `rule_withdraw_succeeds` and `rule_withdraw_fails`, run:
```
certoraSolanaProver--build_script<path_to_build_script>--rulerule_withdraw_succeedsrule_withdraw_fails

```
Copy to clipboard
### `--solana_inlining`[](https://docs.certora.com/en/latest/docs/solana/options.html#solana-inlining "Link to this heading")
**What does it do?**
Provides the Prover with a list of paths to inlining files for Solana programs. These files are parsed and used to prove properties. See an [example](https://github.com/Certora/SolanaExamples/blob/main/cvlr_by_example/first_example/certora/inlining.txt).
**When to use it?**
This option is currently required for every project. It can be provided to the Prover by passing this list as a flag or by retrieving it from the build script.
**Example**
```
certoraSolanaProver--build_script<path_to_build_script>--solana_inlining<path_to_inlining_file>--rule<rule_name>

```
Copy to clipboard
### `--solana_summaries`[](https://docs.certora.com/en/latest/docs/solana/options.html#solana-summaries "Link to this heading")
**What does it do?**
Provides the Prover with a list of paths to summary files for Solana contracts. These files are parsed and used to prove properties. See an [example](https://github.com/Certora/SolanaExamples/blob/main/cvlr_by_example/first_example/certora/summaries.txt).
**When to use it?**
This option is currently required for every project. It can be provided to the Prover by passing this list as a flag or by retrieving it from the build script.
**Example**
```
certoraSolanaProver--build_script<path_to_build_script>--solana_summaries<path_to_summaries_file>--rule<rule_name>

```
Copy to clipboard
### `--cargo_features`[](https://docs.certora.com/en/latest/docs/solana/options.html#cargo-features "Link to this heading")
**What does it do?**
Provides the Prover with a whitespace-separated list of extra [Cargo features](https://doc.rust-lang.org/cargo/reference/features.html) passed to the build script. These features are then passed to `cargo` to build the project.
**When to use it?**
Use it when there is a need to enable a specific [Cargo feature](https://doc.rust-lang.org/cargo/reference/features.html) to compile the source code.
**Example**
```
certoraSolanaProver--build_script<path_to_build_script>--cargo_features<feature_1><feature_2>--rule<rule_name>

```
Copy to clipboard
### `--msg`[](https://docs.certora.com/en/latest/docs/solana/options.html#msg "Link to this heading")
**What does it do?**
Adds a description message to your run, similar to a commit message. This message appears on the Prover dashboard and in the rule report. Note that you need to wrap your message in quotes if it contains spaces.
**When to use it?**
Adding a message makes it easier to track several runs on [the Prover Dashboard](https://prover.certora.com/). It is very useful if you are running many verifications simultaneously. It is also helpful to keep track of a single file verification status over time, so we recommend always providing an informative message.
**Example**
```
certoraSolanaProver--build_script<path_to_build_script>--msg'Removed an assertion'--rule<rule_name>

```
Copy to clipboard
### `--rule_sanity`[](https://docs.certora.com/en/latest/docs/solana/options.html#rule-sanity "Link to this heading")
**What does it do?**
When used with `--rule_sanity: basic`, this flag executes a job in sanity mode which performs a vacuity check for a rule.
**When to use it?**
Sanity mode is helpful to check for the correctness of a rule. For details, see also [Rule Sanity Checks](https://docs.certora.com/en/latest/docs/solana/sanity.html).
**Example**
```
certoraSolanaProver--build_script<path_to_build_script>--rule_sanitybasic

```
Copy to clipboard
## `--multi_assert_check`[](https://docs.certora.com/en/latest/docs/solana/options.html#multi-assert-check "Link to this heading")
**What does it do?** This flags translates each assertion statement in a rule into a separate verification task. All preceding assertions are assumed to be true - they are hence translated into assume statements. An example can be found [here](https://github.com/Certora/SolanaExamples/blob/66c1f406755893db5a081f39ca5cdd583a6f9991/cvlr_by_example/first_example/certora/conf/MultiAssertMode.conf).
Caution
We suggest using this mode carefully. In general, as this mode generates generates one verification task per assert, it may lead to worse running-time performance. Please see indications for use below.
**When to use it?** When you have a rule with multiple assertions:
  1. As a timeout mitigation strategy: checking each assertion separately may, in some cases, perform better than checking all the assertions together and consequently solve timeouts. For instance, you can identify complex to verify asserts in a rule.
  2. If you wish to get multiple counter-examples in a single run of the tool, where each counter-example violates a different assertion in the rule.


**Example**
```
certoraSolanaProver--build_script<path_to_build_script>--multi_assert_check

```
Copy to clipboard
[ Previous](https://docs.certora.com/en/latest/docs/solana/speclanguage.html "Certora Verification Language for Rust \(CVLR\)") [Next ](https://docs.certora.com/en/latest/docs/solana/output.html "Understanding Prover Output for Solana Programs")
© Copyright 2025, Certora, Inc.
Built with [Sphinx](https://www.sphinx-doc.org/) using a [theme](https://github.com/readthedocs/sphinx_rtd_theme) provided by [Read the Docs](https://readthedocs.org). 
