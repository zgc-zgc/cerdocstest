[ Certora Prover Documentation ![Logo](https://docs.certora.com/en/latest/_static/Certora_Logo_Black.svg) ](https://docs.certora.com/en/latest/index.html)
Contents
  * [Certora User’s Guide](https://docs.certora.com/en/latest/docs/user-guide/index.html)
  * [The Certora Verification Language](https://docs.certora.com/en/latest/docs/cvl/index.html)
  * [The Certora Prover](https://docs.certora.com/en/latest/docs/prover/index.html)
  * [Sunbeam: Verification for Soroban](https://docs.certora.com/en/latest/docs/sunbeam/index.html)
  * [The Certora Solana Prover](https://docs.certora.com/en/latest/docs/solana/index.html)
  * [Gambit: Mutation Generator for Solidity](https://docs.certora.com/en/latest/docs/gambit/index.html)


Additional information
  * [The Certora Equivalence Checker](https://docs.certora.com/en/latest/docs/equiv-check/index.html)
    * [Installation](https://docs.certora.com/en/latest/docs/equiv-check/index.html#installation)
    * [Example](https://docs.certora.com/en/latest/docs/equiv-check/index.html#example)
    * [Usage](https://docs.certora.com/en/latest/docs/equiv-check/index.html#usage)
      * [Default mode](https://docs.certora.com/en/latest/docs/equiv-check/index.html#default-mode)
      * [Configuration mode](https://docs.certora.com/en/latest/docs/equiv-check/index.html#configuration-mode)
  * [Certora Technology White Paper](https://docs.certora.com/en/latest/docs/whitepaper/index.html)


  * [Index](https://docs.certora.com/en/latest/genindex.html)


[Certora Prover Documentation](https://docs.certora.com/en/latest/index.html)
  * [](https://docs.certora.com/en/latest/index.html)
  * The Certora Equivalence Checker
  * [ View page source](https://docs.certora.com/en/latest/_sources/docs/equiv-check/index.md.txt)


# The Certora Equivalence Checker[](https://docs.certora.com/en/latest/docs/equiv-check/index.html#the-certora-equivalence-checker "Link to this heading")
This chapter describes how one can use the Certora Prover to check the equivalence of two smart contract functions.
Note
Currently the equivalence checker only compares two `pure` functions, but we are actively working to develop an equivalence checker for non-`pure` functions as well.
The equivalence checker front-end automatically generates (1) a CVL spec to check if two functions are equivalent, and, (2) a configuration file (`.conf`) for running the Certora Prover.
## Installation[](https://docs.certora.com/en/latest/docs/equiv-check/index.html#installation "Link to this heading")
The equivalence checker is part of the `certora-cli` package; see [Installation](https://docs.certora.com/en/latest/docs/user-guide/install.html#installation).
## Example[](https://docs.certora.com/en/latest/docs/equiv-check/index.html#example "Link to this heading")
Consider two contracts, `BasicMathGood.sol` and `BasicMathBad.sol` shown below with two functions, `add` and `add_mult`.
```
contractBasicMathGood{
functionadd(uint256a,uint256b)publicpurereturns(uint256){
returna+b;
}
}
contractBasicMathBad{
functionadd_uncheck(uint256a,uint256b)publicpurereturns(uint256){
unchecked{
returna*b;
}
}
}

```
Copy to clipboard
We are interested in checking the equivalence of `add` and `add_uncheck`. While this is a simple case, you can imagine scenarios where the functions are more complex. Equivalence checking can be used to check whether two functions that may be implemented differently, are still semantically equivalent. The following sections describe how to use the tool.
## Usage[](https://docs.certora.com/en/latest/docs/equiv-check/index.html#usage "Link to this heading")
`certoraEqCheck` can be run either in default (`def`) mode, in which the user must supply all the required information as command line arguments (see below), or in a `conf` mode where the user supplies a Certora Prover `conf` file along with additional arguments.
### Default mode[](https://docs.certora.com/en/latest/docs/equiv-check/index.html#default-mode "Link to this heading")
To run the equivalence checker in default mode, use `certoraEqCheck`:
```
certoraEqCheckdef"path_to_file:contract:function:solc""path_to_file:contract:function:solc"

```
Copy to clipboard
For the functions in [Example](https://docs.certora.com/en/latest/docs/equiv-check/index.html#equivalence-checker-example), this would look as follows:
```
certoraEqCheckdefTest/EqCheck/BasicMathGood.sol:add:solc8.0Test/EqCheck/BasicMathBad.sol:add_pass:solc8.0

```
Copy to clipboard
In the above example, `solc` is the name of the executable for the Solidity compiler version you are using. The Solidity compilers do not need to be the same for both arguments to `certoraEqCheck`, it only need to be appropriate for the given contract. Also note how the contract field can be omitted if the contract name is the same the file name.
### Configuration mode[](https://docs.certora.com/en/latest/docs/equiv-check/index.html#configuration-mode "Link to this heading")
To run the equivalence checker in the configuration mode, use `certoraEqCheck` as follows:
```
certoraEqCheckconf<path_to_conf>.confcontract:functioncontract:function

```
Copy to clipboard
For the functions in [Example](https://docs.certora.com/en/latest/docs/equiv-check/index.html#equivalence-checker-example), this would be:
```
certoraEqCheckconfTest/EqCheck/testGood.confBasicMathGood:addBasicMathBad:add_mult

```
Copy to clipboard
where `testGood.conf` is the standard Certora configuration file and contains:
```
{
"disable_local_typechecking":true,
"files":["BasicMathGood.sol","BasicMathBad.sol"],
"msg":"Equivalence Check",
"optimistic_loop":true,
"loop_iter":"4",
"process":"emv",
"send_only":true,
"short_output":true,
"rule_sanity":"basic",
"solc":"solc8.0",
"solc_optimize":"200",
"server":"staging",
"prover_version":"master"
}

```
Copy to clipboard
Note
Use [precise_bitwise_ops](https://docs.certora.com/en/latest/docs/prover/cli/options.html#precise-bitwise-ops) if you are comparing functions with bitwise operations. This will slow down the tool slightly, but ensure that the results are sound.
`certoraEqCheck` produces two files that are then used to run the Certora Prover automatically. The first one is a CVL specification file, whose content in the case of the example shown here is:
```
 using BasicMathBad as B;
// sets everything but the callee the same in two environments
function e_equivalence(env e1, env e2) {
  require e1.msg.sender == e2.msg.sender;
  require e1.block.timestamp == e2.block.timestamp;
  require e1.msg.value == e2.msg.value;
  // require e1.msg.data == e2.msg.data;
}
rule equivalence_of_revert_conditions()
{
  bool add_revert;
  bool add_mult_revert;
  // using this as opposed to generating input parameters is experimental
  env e_add; calldataarg args;
  env e_add_mult;
  e_equivalence(e_add, e_add_mult);
  add@withrevert(e_add, args);
  add_revert = lastReverted;
  B.add_mult@withrevert(e_add_mult, args);
  add_mult_revert = lastReverted;
  assert(add_revert == add_mult_revert);
}
rule equivalence_of_return_value()
{
  uint256 add_uint256_out0;
  uint256 add_mult_uint256_out0;
  env e_add; calldataarg args;
  env e_add_mult;
  e_equivalence(e_add, e_add_mult);
  add_uint256_out0 = add(e_add, args);
  add_mult_uint256_out0 = B.add_mult(e_add_mult, args);
  assert(add_uint256_out0 == add_mult_uint256_out0);
}

```
Copy to clipboard
The second one is a standard Certora `conf` file:
```
{
  "disable_local_typechecking": true,
  "files": [
    "Test/EqCheck/BasicMathGood.sol",
    "Test/EqCheck/BasicMathBad.sol"
  ],
  "msg": "EquivalenceCheck of add and add_mult",
  "optimistic_loop": true,
  "loop_iter": "4",
  "process": "emv",
  "send_only": true,
  "short_output": true,
  "rule_sanity": "basic",
  "server": "staging",
  "prover_version": "master",
  "solc_optimize": "200",
  "verify": "BasicMathGood:Test/EqCheck/add_to_add_mult_equivalence.spec",
  "solc": "solc8.0"
}

```
Copy to clipboard
The script then invokes the Certora Prover using this `conf` file.
[ Previous](https://docs.certora.com/en/latest/docs/gambit/gambit.html "Gambit: Mutant Generation for Solidity") [Next ](https://docs.certora.com/en/latest/docs/whitepaper/index.html "Certora Technology White Paper")
© Copyright 2025, Certora, Inc.
Built with [Sphinx](https://www.sphinx-doc.org/) using a [theme](https://github.com/readthedocs/sphinx_rtd_theme) provided by [Read the Docs](https://readthedocs.org). 
