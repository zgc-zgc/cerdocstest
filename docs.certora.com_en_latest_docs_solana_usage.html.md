[ Certora Prover Documentation ![Logo](https://docs.certora.com/en/latest/_static/Certora_Logo_Black.svg) ](https://docs.certora.com/en/latest/index.html)
Contents
  * [Certora User’s Guide](https://docs.certora.com/en/latest/docs/user-guide/index.html)
  * [The Certora Verification Language](https://docs.certora.com/en/latest/docs/cvl/index.html)
  * [The Certora Prover](https://docs.certora.com/en/latest/docs/prover/index.html)
  * [Sunbeam: Verification for Soroban](https://docs.certora.com/en/latest/docs/sunbeam/index.html)
  * [The Certora Solana Prover](https://docs.certora.com/en/latest/docs/solana/index.html)
    * [Get started with the Solana Certora Prover](https://docs.certora.com/en/latest/docs/solana/installation.html)
    * [Using the Solana Certora Prover](https://docs.certora.com/en/latest/docs/solana/usage.html)
      * [Overview](https://docs.certora.com/en/latest/docs/solana/usage.html#overview)
      * [Project Structure](https://docs.certora.com/en/latest/docs/solana/usage.html#project-structure)
      * [Configuration Formats](https://docs.certora.com/en/latest/docs/solana/usage.html#configuration-formats)
        * [Verifying Pre-Built Contracts](https://docs.certora.com/en/latest/docs/solana/usage.html#verifying-pre-built-contracts)
        * [Running from Sources](https://docs.certora.com/en/latest/docs/solana/usage.html#running-from-sources)
      * [Execution Examples](https://docs.certora.com/en/latest/docs/solana/usage.html#execution-examples)
        * [Running from Sources](https://docs.certora.com/en/latest/docs/solana/usage.html#id1)
        * [Verifying Pre-Built Contracts](https://docs.certora.com/en/latest/docs/solana/usage.html#id2)
      * [Building the Project](https://docs.certora.com/en/latest/docs/solana/usage.html#building-the-project)
        * [Using the Build Script or Command](https://docs.certora.com/en/latest/docs/solana/usage.html#using-the-build-script-or-command)
        * [Build Script or Command Inputs and Outputs](https://docs.certora.com/en/latest/docs/solana/usage.html#build-script-or-command-inputs-and-outputs)
    * [Certora Verification Language for Rust (CVLR)](https://docs.certora.com/en/latest/docs/solana/speclanguage.html)
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
  * Using the Solana Certora Prover
  * [ View page source](https://docs.certora.com/en/latest/_sources/docs/solana/usage.md.txt)


# Using the Solana Certora Prover[](https://docs.certora.com/en/latest/docs/solana/usage.html#using-the-solana-certora-prover "Link to this heading")
## Overview[](https://docs.certora.com/en/latest/docs/solana/usage.html#overview "Link to this heading")
This document provides a guide on how to use the Solana Certora Prover. It details configuration formats, the build process, and how to execute verification locally and remotely.
## Project Structure[](https://docs.certora.com/en/latest/docs/solana/usage.html#project-structure "Link to this heading")
A typical Solana project integrated with the Solana Certora Prover includes:
  * A Solana smart contract written in Rust.
  * Configurations for running the Certora Prover: the Prover can be executed either by starting from source files or by verifying pre-compiled code.
  * An executable build script or command for compiling the project and preparing it for verification. This is required only if the code has not already been pre-compiled.


The [Certora Solana Examples](https://github.com/Certora/SolanaExamples) repository contains a collection of example projects.
## Configuration Formats[](https://docs.certora.com/en/latest/docs/solana/usage.html#configuration-formats "Link to this heading")
### Verifying Pre-Built Contracts[](https://docs.certora.com/en/latest/docs/solana/usage.html#verifying-pre-built-contracts "Link to this heading")
This configuration mode explicitly specifies the pre-built files required for verification:
```
{
"files":[
"solana_contract.so"
],
"solana_inlining":"../../cvt_inlining.txt",
"solana_summaries":"../../cvt_summaries.txt",
"process":"sbf",
"optimistic_loop":false,
"rule":"rule_solvency"
}

```
Copy to clipboard
### Running from Sources[](https://docs.certora.com/en/latest/docs/solana/usage.html#running-from-sources "Link to this heading")
This configuration mode uses a `build_script` or executable command for dynamic project building and eliminates hardcoded file paths:
```
{
"build_script":"./certora_build.py",
"solana_inlining":"../../cvt_inlining.txt",
"solana_summaries":"../../cvt_summaries.txt",
"cargo_features":"<feature1> <feature2> <feature3>",
"process":"sbf",
"optimistic_loop":false,
"rule":"rule_solvency"
}

```
Copy to clipboard
**Key Differences:**
  * **Verifying Pre-Built Contracts** : Uses pre-compiled `.so` files for verification.
  * **Running from Sources** : Automates the build process through the `certora_build.py` script or another executable command. See [here](https://github.com/Certora/SolanaExamples/blob/main/cvlr_by_example/first_example/certora_build.py) for an example of such a script.


## Execution Examples[](https://docs.certora.com/en/latest/docs/solana/usage.html#execution-examples "Link to this heading")
### Running from Sources[](https://docs.certora.com/en/latest/docs/solana/usage.html#id1 "Link to this heading")
To run the Certora Prover using the “running from sources” configuration:
```
certoraSolanaProversources_config.conf

```
Copy to clipboard
**Expected Output:**
```
INFO: Building from script ./certora_build.py
Connecting to server...
Job submitted to server.
Manage your jobs at <https://prover.certora.com>.
Follow your job and see verification results at <https://prover.certora.com/output/{job_id}/{unique_key}>.

```
Copy to clipboard
### Verifying Pre-Built Contracts[](https://docs.certora.com/en/latest/docs/solana/usage.html#id2 "Link to this heading")
To run the Certora Prover using the “verifying pre-built contracts” configuration:
```
certoraSolanaProverprebuilt_config.conf

```
Copy to clipboard
**Expected Output:**
```
Connecting to server...
Job submitted to server.
Manage your jobs at <https://prover.certora.com>.
Follow your job and see verification results at <https://prover.certora.com/output/{job_id}/{unique_key}>.

```
Copy to clipboard
## Building the Project[](https://docs.certora.com/en/latest/docs/solana/usage.html#building-the-project "Link to this heading")
### Using the Build Script or Command[](https://docs.certora.com/en/latest/docs/solana/usage.html#using-the-build-script-or-command "Link to this heading")
The `certora_build.py` script or an equivalent executable command handles project compilation and prepares it for verification. Execute it as follows:
```
python3certora_build.py

```
Copy to clipboard
This ensures the `.so` file is up-to-date and ready for verification.
### Build Script or Command Inputs and Outputs[](https://docs.certora.com/en/latest/docs/solana/usage.html#build-script-or-command-inputs-and-outputs "Link to this heading")
The script or command connects the project to the Certora Prover by:
  1. Compiling the project.
  2. Returning a JSON object with project details.
  3. Handling build failures appropriately.


#### Inputs[](https://docs.certora.com/en/latest/docs/solana/usage.html#inputs "Link to this heading")
  * `-o/--output`: Specifies the output JSON file path.
  * `--json`: Dumps JSON to the console.
  * `-l/--log`: Displays build logs.
  * `-v/--verbose`: Enables verbose mode.


#### Outputs[](https://docs.certora.com/en/latest/docs/solana/usage.html#outputs "Link to this heading")
**Using`--json`** Prints a JSON structure to `stdout`:
```
{
"project_directory":"<path>",
"sources":["src/**/*.rs","Cargo.toml"],
"executables":"target/release/solana_contract.so",
"success":true,
"return_code":0,
"log":{
"stdout":"path/to/stdout",
"stderr":"path/to/stderr"
}
}

```
Copy to clipboard
**Using`--output`** Saves the JSON structure to the file specified by the `--output` flag.
**Without`--json` or `--output`** Returns `0` if the build is successful and `1` otherwise.
[ Previous](https://docs.certora.com/en/latest/docs/solana/installation.html "Get started with the Solana Certora Prover") [Next ](https://docs.certora.com/en/latest/docs/solana/speclanguage.html "Certora Verification Language for Rust \(CVLR\)")
© Copyright 2025, Certora, Inc.
Built with [Sphinx](https://www.sphinx-doc.org/) using a [theme](https://github.com/readthedocs/sphinx_rtd_theme) provided by [Read the Docs](https://readthedocs.org). 
