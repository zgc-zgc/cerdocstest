Contents Menu Expand Light mode Dark mode Auto light/dark mode Auto light/dark, in light mode Auto light/dark, in dark mode
Hide navigation sidebar
Hide table of contents sidebar
[Skip to content](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/config_files.html#furo-main-content)
Toggle site navigation sidebar
[Certora Prover Tutorials](https://docs.certora.com/projects/tutorials/en/latest/index.html)
Toggle Light / Dark / Auto color theme
Toggle table of contents sidebar
[ ![Light Logo](https://docs.certora.com/projects/tutorials/en/latest/_static/logo.svg) ![Dark Logo](https://docs.certora.com/projects/tutorials/en/latest/_static/logo.svg) Certora Prover Tutorials ](https://docs.certora.com/projects/tutorials/en/latest/index.html)
Contents:
  * [1. Background and Prerequisites](https://docs.certora.com/projects/tutorials/en/latest/lesson1_prerequisites/index.html)
Toggle navigation of 1. Background and Prerequisites
    * [1.1. Background](https://docs.certora.com/projects/tutorials/en/latest/lesson1_prerequisites/background.html)
    * [1.2. Introduction to predicate logic](https://docs.certora.com/projects/tutorials/en/latest/lesson1_prerequisites/propositional_logic.html)
    * [1.3. Introduction to formal verification](https://docs.certora.com/projects/tutorials/en/latest/lesson1_prerequisites/formal_verification.html)
  * [2. Getting Started](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/index.html)
Toggle navigation of 2. Getting Started
    * [2.1. Installation and Setup](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/installation.html)
    * [2.2. Technology Overview](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/overview.html)
    * [2.3. ERC20 Example - Basics](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/erc20_example.html)
    * [2.4. ERC20 Example - preconditions](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/preconditions.html)
    * [2.5. Parametric rules](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/parametric.html)
    * [2.6. Using config files](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/config_files.html)
    * [2.7. Vacuity](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/vacuity.html)
  * [3. Understanding violations](https://docs.certora.com/projects/tutorials/en/latest/lesson3_violations/index.html)
Toggle navigation of 3. Understanding violations
    * [3.1. Fixing ERC20 spec](https://docs.certora.com/projects/tutorials/en/latest/lesson3_violations/erc20_bugs.html)
    * [3.2. Borda count election](https://docs.certora.com/projects/tutorials/en/latest/lesson3_violations/borda_bugs.html)
    * [3.3. Reward Challenge : Missing Spec bounty](https://docs.certora.com/projects/tutorials/en/latest/lesson3_violations/reward_challenge.html)
  * [4. Invariants and Ghosts](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/index.html)
Toggle navigation of 4. Invariants and Ghosts
    * [4.1. Simple invariants examples](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/invariants/simple.html)
    * [4.2. Basic exercises](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/invariants/auction.html)
    * [4.3. Preserved blocks](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/invariants/preserved.html)
    * [4.4. Ghosts and hooks](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/ghosts/basics.html)
    * [4.5. Ghost exercises](https://docs.certora.com/projects/tutorials/en/latest/lesson4_invariants/ghosts/exercises.html)


  * [Index](https://docs.certora.com/projects/tutorials/en/latest/genindex.html)


[ Back to top ](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/config_files.html)
Toggle Light / Dark / Auto color theme
Toggle table of contents sidebar
# 2.6. Using config files[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/config_files.html#using-config-files "Link to this heading")
## Introduction[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/config_files.html#introduction "Link to this heading")
For larger projects, the command line for running the Certora Prover can become large and cumbersome. It is therefore recommended to use _configuration files_ instead. These are [JSON5](https://json5.org/) files (with `.conf` extension) that hold the parameters and options for the Prover. Here is an example config file:
```
{
"files":[
"ERC20.sol"
],
"verify":"ERC20:ERC20.spec",
"wait_for_results":"all",
"rule_sanity":"basic",
// Note: json5 supports comments!
"msg":"First run using .conf file"
}

```

This is a config file for running the [ERC20.spec](https://github.com/Certora/tutorials-code/blob/master/lesson2_started/erc20/ERC20.spec), and it is found in the same folder, in [sample_conf.conf](https://github.com/Certora/tutorials-code/blob/master/lesson2_started/erc20/sample_conf.conf). Using this file we can run the Certora Prover by simply entering:
```
certoraRunsample_conf.conf

```

Note
In this case the working directory should be the same folder where both files are placed.
There are other reasons to prefer configuration files over directly using CLI:
  1. They are easier to read and sometimes friendlier to edit
  2. Since the configuration files are [JSON5](https://json5.org/), they _support comments_
  3. We can include them in our git repository for version control


## Some config file fields[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/config_files.html#some-config-file-fields "Link to this heading") 

`files`
    
A list of the files containing the contracts needed. If a file contains several contracts and you wish to verify one of them, write it as `contractFile:contractName`. 

`verify`
    
This is the same as the `--verify` argument for the `certoraRun` script, so it accepts a string of the form `<contract name>:<path to spec>`. 

`wait_for_results`
    
If the value is `"all"`, then the Prover will wait for the cloud job to complete, and display the log and results in the meantime. 

`solc`
    
Path to the solidity compiler, this is the same as the `--solc` argument for the `certoraRun` script. 

`msg`
    
The same as the `--msg` argument for the script. 

`rule_sanity`
    
Check rules for vacuity, triviality and similar conditions. _Vacuity_ means the rule passes because there are no computation paths satisfying the requirements. See [Vacuity](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/vacuity.html#sec-vacuity) for more information. _Triviality_ means the invariant always holds, even without the pre-condition. Possible values for `rule_sanity` are `"none"`, `"basic"` and `"advanced"`. See [Rule Sanity Checks](https://docs.certora.com/en/latest/docs/prover/checking/sanity.html) for more information.
Warning
Always use `"rule_sanity": "basic"` or `"rule_sanity": "advanced"` when running the Prover, as it is very easy to write vacuous rules without noticing.
[ Next 2.7. Vacuity ](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/vacuity.html) [ Previous 2.5. Parametric rules ](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/parametric.html)
Copyright © 2023, Certora, Inc 
Made with [Sphinx](https://www.sphinx-doc.org/) and [@pradyunsg](https://pradyunsg.me)'s [Furo](https://github.com/pradyunsg/furo)
On this page 
  * [2.6. Using config files](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/config_files.html)
    * [Introduction](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/config_files.html#introduction)
    * [Some config file fields](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/config_files.html#some-config-file-fields)


