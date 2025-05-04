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
        * [How CLI options are mapped to JSON](https://docs.certora.com/en/latest/docs/prover/cli/conf-file-api.html#how-cli-options-are-mapped-to-json)
        * [Generating a conf file](https://docs.certora.com/en/latest/docs/prover/cli/conf-file-api.html#generating-a-conf-file)
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
  * Configuration (Conf) Files
  * [ View page source](https://docs.certora.com/en/latest/_sources/docs/prover/cli/conf-file-api.md.txt)


# Configuration (Conf) Files[](https://docs.certora.com/en/latest/docs/prover/cli/conf-file-api.html#configuration-conf-files "Link to this heading")
Conf files are an alternative way for setting arguments for the `certoraRun` tool. In terms of functionality using conf files is identical to the use of the [CLI Options](https://docs.certora.com/en/latest/docs/prover/cli/options.html). Instead of calling `certoraRun` with a list of shell flags, some or all the flags can be stored in a JSON file (to be more precise the format is [JSON5](https://json5.org/)):
```
certoraRunmy_params.conf

```
Copy to clipboard
Conf files must use the `.conf` suffix.
## How CLI options are mapped to JSON[](https://docs.certora.com/en/latest/docs/prover/cli/conf-file-api.html#how-cli-options-are-mapped-to-json "Link to this heading")
Command-line arguments are stored as key-value pairs in the conf file. The keys are the names of the CLI options (with the leading `--` removed). For example,
```
certoraRun--verifyExample:example.spec

```
Copy to clipboard
is equivalent to running with the following conf file:
```
{"verify":"Example:example.spec"}

```
Copy to clipboard
The values in the map depend on the type of arguments:
  * The input files in the CLI API will be stored as a list under the key `files`. For example,
```
certoraRunexample.sol...

```
Copy to clipboard
will appear in the conf file as:
```
{
 ...
 "files": [ "example.sol" ], 
 ...
}

```
Copy to clipboard
  * Boolean options are options that take no arguments (for example [multi_assert_check](https://docs.certora.com/en/latest/docs/prover/cli/options.html#multi-assert-check)). In the conf file all keys must come with a value, the value for boolean options is `true`. Since the default value of boolean options is `false` there is no need to set a boolean attribute to values other than `true`. For example,
```
certoraRun--multi_assert_check

```
Copy to clipboard
would be encoded as:
```
{"multi_assert_check":true}

```
Copy to clipboard
  * Options that expect a single argument (for example [solc](https://docs.certora.com/en/latest/docs/prover/cli/options.html#solc) or [loop_iter](https://docs.certora.com/en/latest/docs/prover/cli/options.html#loop-iter)) are encoded as a JSON string. For example,
```
certoraRun--solcsolc4.25--loop_iter2

```
Copy to clipboard
would be encoded as:
```
{"solc":"solc4.25","loop_iter":"2"}

```
Copy to clipboard
Note that in conf files numbers are also encoded as strings.
  * Options that expect multiple arguments (for example [packages](https://docs.certora.com/en/latest/docs/prover/cli/options.html#packages)) are encoded as JSON lists. For example,
```
certoraRun--packages@balancer-labs/v2-solidity-utils=pkg/solidity-utils\
@balancer-labs/v2-vault=pkg/vault
wouldbeencodedas:
```json
{
"packages":[
"@balancer-labs/v2-solidity-utils=pkg/solidity-utils",
"@balancer-labs/v2-vault=pkg/vault"
]
}

```
Copy to clipboard
  * Options that are maps ([compiler_map](https://docs.certora.com/en/latest/docs/prover/cli/options.html#solc-map), [solc_optimize_map](https://docs.certora.com/en/latest/docs/prover/cli/options.html#solc-optimize-map) and [solc_evm_version_map](https://docs.certora.com/en/latest/docs/prover/cli/options.html#solc-evm-version-map)) will be stored as JSON objects. For example,
```
certoraRun--solc_mapA=solc5.11,B=solc5.9,C=solc6.8

```
Copy to clipboard
would be encoded as:


```
{
"solc_map":{
"A":"solc5.11",
"B":"solc5.9",
"C":"solc6.8"
}
}

```
Copy to clipboard
```
and 
```sh
certoraRun --solc_optimize_map A=200,B=200,C=300
```

```
Copy to clipboard
would be encoded as:
```
{
"solc_optimize_map":{
"A":"200",
"B":"200",
"C":"300"
}
}

```
Copy to clipboard
## Generating a conf file[](https://docs.certora.com/en/latest/docs/prover/cli/conf-file-api.html#generating-a-conf-file "Link to this heading")
After each successful run of `certoraRun` a conf file is generated and is stored in the file `run.conf` under the internal directory of that run. The conf file of the latest run can be found in:
```
.certora_internal/latest/run.conf

```
Copy to clipboard
Instead of generating a complete conf file from scratch, users can take one of these generated conf files as a basis for their modifications.
### Complete example[](https://docs.certora.com/en/latest/docs/prover/cli/conf-file-api.html#complete-example "Link to this heading")
The command line
```
certoraRunSolcArgs/A.solSolcArgs/A.sol:BSolcArgs/C.sol\
--verifyA:SolcArgs/Trigger.spec\
--solc_mapSolcArgs/A.sol=solc6.1,B=solc6.1,C=solc5.12\
--multi_assert_check

```
Copy to clipboard
will generate the conf file below:
```
{
"files":[
"SolcArgs/A.sol",
"SolcArgs/A.sol:B",
"SolcArgs/C.sol"
],
"multi_assert_check":true,
"solc_map":{
"B":"solc6.1",
"C":"solc5.12",
"SolcArgs/A.sol":"solc6.1"
},
"verify":"A:SolcArgs/Trigger.spec"
}

```
Copy to clipboard
[ Previous](https://docs.certora.com/en/latest/docs/prover/cli/options.html "CLI Options") [Next ](https://docs.certora.com/en/latest/docs/prover/portal/using.html "Using the Certora Portal")
© Copyright 2025, Certora, Inc.
Built with [Sphinx](https://www.sphinx-doc.org/) using a [theme](https://github.com/readthedocs/sphinx_rtd_theme) provided by [Read the Docs](https://readthedocs.org). 
