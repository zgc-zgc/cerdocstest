[ Certora Prover Documentation ![Logo](https://docs.certora.com/en/latest/_static/Certora_Logo_Black.svg) ](https://docs.certora.com/en/latest/index.html)
Contents
  * [Certora User’s Guide](https://docs.certora.com/en/latest/docs/user-guide/index.html)
    * [Installation](https://docs.certora.com/en/latest/docs/user-guide/install.html)
    * [Installing an EVM compiler and VS Code Extension](https://docs.certora.com/en/latest/docs/user-guide/install_evm_compiler.html)
    * [Tutorial and Workshops](https://docs.certora.com/en/latest/docs/user-guide/tutorials.html)
    * [Running the Certora Prover](https://docs.certora.com/en/latest/docs/user-guide/running.html)
      * [Usage Example with ERC20 Contract](https://docs.certora.com/en/latest/docs/user-guide/running.html#usage-example-with-erc20-contract)
      * [Results](https://docs.certora.com/en/latest/docs/user-guide/running.html#results)
      * [Using Configuration (Conf) Files](https://docs.certora.com/en/latest/docs/user-guide/running.html#using-configuration-conf-files)
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
  * Running the Certora Prover
  * [ View page source](https://docs.certora.com/en/latest/_sources/docs/user-guide/running.rst.txt)


# Running the Certora Prover[](https://docs.certora.com/en/latest/docs/user-guide/running.html#running-the-certora-prover "Link to this heading")
The `certoraRun` utility simplifies the verification process by invoking the contract compiler (e.g., Solidity) and then sending the verification job to Certora’s servers.
The most commonly used command is:
```
certoraRuncontractFile:contractName--verifycontractName:specFile

```
Copy to clipboard
If `contractFile` is named `contractName.sol`, the command can be further simplified to:
```
certoraRuncontractFile--verifycontractName:specFile

```
Copy to clipboard
A concise summary of these options can be viewed by using:
```
certoraRun--help

```
Copy to clipboard
## Usage Example with ERC20 Contract[](https://docs.certora.com/en/latest/docs/user-guide/running.html#usage-example-with-erc20-contract "Link to this heading")
To demonstrate the usage, let’s consider an ERC20 contract named [ERC20Fixed](https://github.com/Certora/Examples/blob/7dfc379423202c90cf284eb42800b97cf5c95d83/DEFI/ERC20/contracts/correct/ERC20Fixed.sol) from the [Certora Prover and CVL Examples Repository](https://github.com/Certora/Examples/tree/7dfc379423202c90cf284eb42800b97cf5c95d83/.). The corresponding spec file is named [ERC20Fixed.spec](https://github.com/Certora/Examples/blob/7dfc379423202c90cf284eb42800b97cf5c95d83/DEFI/ERC20/certora/specs/ERC20Fixed.spec). Here is a rule from this spec:
[from ERC20Fixed.spec](https://github.com/Certora/Examples/blob/7dfc379423202c90cf284eb42800b97cf5c95d83/DEFI/ERC20/certora/specs/ERC20Fixed.spec)[](https://docs.certora.com/en/latest/docs/user-guide/running.html#id1 "Link to this code")
```
/// Transfer must move `amount` tokens from the caller's account to `recipient`
ruletransferSpec{
addresssender;addressrecip;uintamount;
enve;
requiree.msg.sender==sender;
mathintbalance_sender_before=balanceOf(sender);
mathintbalance_recip_before=balanceOf(recip);
transfer(e,recip,amount);
mathintbalance_sender_after=balanceOf(sender);
mathintbalance_recip_after=balanceOf(recip);
requiresender!=recip;
assertbalance_sender_after==balance_sender_before-amount,
"transfer must decrease sender's balance by amount";
assertbalance_recip_after==balance_recip_before+amount,
"transfer must increase recipient's balance by amount";
}

```
Copy to clipboard
You can run the Certora Prover with the following command (from the [/DEFI/ERC20/](https://github.com/Certora/Examples/tree/7dfc379423202c90cf284eb42800b97cf5c95d83/DEFI/ERC20) folder in the repository):
```
certoraRuncontracts/correct/ERC20Fixed.sol--verifyERC20Fixed:certora/specs/ERC20Fixed.spec

```
Copy to clipboard
This command triggers a verification run on the `ERC20` contract from the solidity file `ERC20.sol`, checking all rules in the specification file `ERC20Fixed.spec`.
Tip
You will need to use the correct version of the Solidity compiler. Either by
  * using `solc-select` or having the compiler executable in your path (see [Installing Solidity compiler](https://docs.certora.com/en/latest/docs/user-guide/install_evm_compiler.html#selecting-solidity-compiler)),
  * or by directing the `certoraRun` to the correct path using the [solc](https://docs.certora.com/en/latest/docs/prover/cli/options.html#solc) argument.


## Results[](https://docs.certora.com/en/latest/docs/user-guide/running.html#results "Link to this heading")
While running, the Prover will print various information to the console about the run. In the end, the output will look similar to this:
```
...
Job submitted to server
Follow your job at https://prover.certora.com
Once the job is completed, the results will be available at https://prover.certora.com/...

```
Copy to clipboard
The output indicates that the Prover running the verification request, and it provides a link to view the results on the Certora platform.
## Using Configuration (Conf) Files[](https://docs.certora.com/en/latest/docs/user-guide/running.html#using-configuration-conf-files "Link to this heading")
For larger projects, managing the command line for Certora Prover can become complex. It is advisable to use configuration files (with a `.conf` extension) that hold the parameters and options for the Prover. These [JSON5](https://json5.org/) configuration files simplify the process and enhance manageability. Refer to [Configuration (Conf) Files](https://docs.certora.com/en/latest/docs/prover/cli/conf-file-api.html#conf-files) for more detailed information.
[ Previous](https://docs.certora.com/en/latest/docs/user-guide/tutorials.html "Tutorial and Workshops") [Next ](https://docs.certora.com/en/latest/docs/user-guide/properties/index.html "Designing Good Specifications")
© Copyright 2025, Certora, Inc.
Built with [Sphinx](https://www.sphinx-doc.org/) using a [theme](https://github.com/readthedocs/sphinx_rtd_theme) provided by [Read the Docs](https://readthedocs.org). 
