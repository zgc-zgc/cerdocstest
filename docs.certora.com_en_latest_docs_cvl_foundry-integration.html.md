[ Certora Prover Documentation ![Logo](https://docs.certora.com/en/latest/_static/Certora_Logo_Black.svg) ](https://docs.certora.com/en/latest/index.html)
Contents
  * [Certora User’s Guide](https://docs.certora.com/en/latest/docs/user-guide/index.html)
  * [The Certora Verification Language](https://docs.certora.com/en/latest/docs/cvl/index.html)
    * [Specification Files](https://docs.certora.com/en/latest/docs/cvl/overview.html)
    * [Basic Syntax](https://docs.certora.com/en/latest/docs/cvl/basics.html)
    * [Types](https://docs.certora.com/en/latest/docs/cvl/types.html)
    * [Expressions](https://docs.certora.com/en/latest/docs/cvl/expr.html)
    * [Statements](https://docs.certora.com/en/latest/docs/cvl/statements.html)
    * [Import and Use Statements](https://docs.certora.com/en/latest/docs/cvl/imports.html)
    * [Using Statements](https://docs.certora.com/en/latest/docs/cvl/using.html)
    * [The Methods Block](https://docs.certora.com/en/latest/docs/cvl/methods.html)
    * [Rules](https://docs.certora.com/en/latest/docs/cvl/rules.html)
    * [Built-in Rules](https://docs.certora.com/en/latest/docs/cvl/builtin.html)
    * [Functions](https://docs.certora.com/en/latest/docs/cvl/functions.html)
    * [Invariants](https://docs.certora.com/en/latest/docs/cvl/invariants.html)
    * [Uninterpreted Sorts](https://docs.certora.com/en/latest/docs/cvl/sorts.html)
    * [Ghosts](https://docs.certora.com/en/latest/docs/cvl/ghosts.html)
    * [Definitions](https://docs.certora.com/en/latest/docs/cvl/defs.html)
    * [Hooks](https://docs.certora.com/en/latest/docs/cvl/hooks.html)
    * [Transient Storage](https://docs.certora.com/en/latest/docs/cvl/transient.html)
    * [Foundry Integration (Alpha)](https://docs.certora.com/en/latest/docs/cvl/foundry-integration.html)
      * [Usage (Automatic Setup)](https://docs.certora.com/en/latest/docs/cvl/foundry-integration.html#usage-automatic-setup)
      * [Usage (Manual Setup)](https://docs.certora.com/en/latest/docs/cvl/foundry-integration.html#usage-manual-setup)
      * [Key differences vs. Foundry fuzz testing](https://docs.certora.com/en/latest/docs/cvl/foundry-integration.html#key-differences-vs-foundry-fuzz-testing)
      * [Known Limitations](https://docs.certora.com/en/latest/docs/cvl/foundry-integration.html#known-limitations)
    * [Changes Since CVL 1](https://docs.certora.com/en/latest/docs/cvl/index.html#changes-since-cvl-1)
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
  * [The Certora Verification Language](https://docs.certora.com/en/latest/docs/cvl/index.html)
  * Foundry Integration (Alpha)
  * [ View page source](https://docs.certora.com/en/latest/_sources/docs/cvl/foundry-integration.md.txt)


# Foundry Integration (Alpha)[](https://docs.certora.com/en/latest/docs/cvl/foundry-integration.html#foundry-integration-alpha "Link to this heading")
Certora’s Foundry Integration allows formally verifying [Foundry fuzz tests](https://book.getfoundry.sh/forge/fuzz-testing) with the Certora Prover instead of writing specifications in CVL.
The Prover will yield higher guarantees of correctness than Foundry as all inputs will be evaluated. While fuzzing is not as complete as formal verification (a fuzzer might “miss” some inputs that would expose a bug), writing fuzz tests via Foundry is often easier since it uses Solidity.
Caution
This feature of the Certora Prover is in alpha state, so issues/unimplemented features are expected. Please contact us if you encounter any issue.
## Usage (Automatic Setup)[](https://docs.certora.com/en/latest/docs/cvl/foundry-integration.html#usage-automatic-setup "Link to this heading")
In Prover version 7.25.1, the flag [foundry](https://docs.certora.com/en/latest/docs/prover/cli/options.html#foundry) was introduced. This flag automatically collects all test files (`.t.sol`) in the current directory and executes the Prover in Foundry mode.
To execute use: `certoraRun --foundry`
If you are facing issues with the automatic setup, for instance, when too many contracts that are being analyzed, it is recommended to perform a manual setup instead.
## Usage (Manual Setup)[](https://docs.certora.com/en/latest/docs/cvl/foundry-integration.html#usage-manual-setup "Link to this heading")
There is a minimum of 2 required files to get the Prover to verify Foundry fuzz tests: A `.spec` file (written in CVL), and a `.conf` file.
  * First, we need a `.spec` file written in CVL to tell the Prover what to verify. The file is very simple, and in the minimal case has exactly one line:\


```
usebuiltinruleverifyFoundryFuzzTests;

```
Copy to clipboard
  * Second, you need a `.conf` file that will provide the Prover the information of which contract to verify, and what `.spec` file to use. A minimal `.conf` file will look like this:\


```
{
"files":[
"path/to/file/with/Foundry/fuzz/tests.sol:<name_of_contract_containing_the_tests>",
],
"verify":"name_of_contract_containing_the_tests:path/to/spec/file.spec",
"foundry_tests_mode":true,
}

```
Copy to clipboard
  * Now, to run the tests, execute: `certoraRun path/to/conf/file.conf`
  * You will receive a link to a report containing the results of the run.


For a full running example, please also see our [Foundry Integration Examples](https://github.com/Certora/Examples/tree/master/FoundryIntegration).
## Key differences vs. Foundry fuzz testing[](https://docs.certora.com/en/latest/docs/cvl/foundry-integration.html#key-differences-vs-foundry-fuzz-testing "Link to this heading")
In Foundry, fuzz tests start with a blank state as the initial state (i.e. all storage fields are explicitly set to `0`), and one can implement a `setUp()` function in order to bring the state to whatever initial state one wants to run the tests in. In contrast, the Prover starts with an arbitrary initial state and does _not_ assume all storage fields to be initialized with 0 by default. This could cause the Prover to find spurious counter examples. For example, a fuzz test may assume that a storage value of `balance` is zero for all addresses and the Prover may choose some other initial state violating this basic assumption of the test.
To restrict the Prover’s search space to match the setup of the Foundry test, it’s possible write a special CVL function `init_fuzz_tests` that acts as a setup in CVL. This function may or may not be required depending on how the fuzz tests are setup.
```
overridefunctioninit_fuzz_tests(methodf,enve){
// your initial state assumptions here
}

```
Copy to clipboard
Depending on your fuzz test, you may need to use the `reset_storage` command in the `init_fuzz_tests` function. This will explicitly set all storage fields of a contract to `0` before running the test. Alternatively, one could try to add a call to the `setUp()` function in the `init_fuzz_tests` function - please note that the `init_fuzz_tests` is an empty method by default.
## Known Limitations[](https://docs.certora.com/en/latest/docs/cvl/foundry-integration.html#known-limitations "Link to this heading")
  * Foundry’s [Invariant testing](https://book.getfoundry.sh/forge/invariant-testing) is not supported, i.e. forge tests prefixed with `invariant` are not formally verified. Under the hood, the built-in rule `verifyFoundryFuzzTests` is a parametric rule that picks up all methods that start in `test*` and will use these to formally verify them.
  * One of the usual usages of the `setUp()` function is to create new contract instances for testing. When setting up the Prover run, the way to handle such storage references to other contracts is to use linking. If, for example, we have the following test code\


```
contractTestContractisTest{
MyContractmyContract;
functionsetUp()external{
myContract=newMyContract();
}
...
}

```
Copy to clipboard
then add to the `.conf` file:\
```
"files":[
"...",
"path/to/MyContract.sol"
],
"link":[
"...",
"TestContract:myContract=MyContract"
]

```
Copy to clipboard
This way when the Prover encounters `myContract.foo()` it knows what the implementation of `foo` is and is able to inline it.
  * Only a subset of the Foundry cheatcodes are currently implemented. The implemented cheatcodes include `vm.assume`, all `assert*` cheatcodes, `vm.expectRevert`, `prank`, `startPrank`, `stopPrank`, `warp`, and `deal`. Some other cheatcodes are irrelevant and are ignored, and many cheatcodes are not yet supported. One can recognize these by checking the **Contracts Call Resolutions** tab of the report - unimplemented cheatcodes will appear there as unresolved calls (which will usually lead to [havocs](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-havoc) and therefore spurious counter examples). In this case, please contact Certora so we can implement the required cheatcode.
  * In cases where no explicit revert is expected, and the goal is to verify values or state using `assert*` cheatcodes, you can use `verifyFoundryFuzzTestsNoRevert`. This ignores all code paths that lead to a revert while still verifying the `assert*` cheatcodes.
  * In Foundry, the `vm.expectRevert` cheatcode can optionally take a specific revert reason. Foundry verifies both that the test function reverted and that it reverted with the specified reason. In contrast, the Prover does not analyze the revert reason. As a result, if the test function reverts for a reason other than the expected one, the test will still be marked as successful.


[ Previous](https://docs.certora.com/en/latest/docs/cvl/transient.html "Transient Storage") [Next ](https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html "Changes Introduced in CVL 2")
© Copyright 2025, Certora, Inc.
Built with [Sphinx](https://www.sphinx-doc.org/) using a [theme](https://github.com/readthedocs/sphinx_rtd_theme) provided by [Read the Docs](https://readthedocs.org). 
