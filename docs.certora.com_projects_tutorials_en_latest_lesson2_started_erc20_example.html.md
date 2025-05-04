Contents Menu Expand Light mode Dark mode Auto light/dark mode Auto light/dark, in light mode Auto light/dark, in dark mode
Hide navigation sidebar
Hide table of contents sidebar
[Skip to content](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/erc20_example.html#furo-main-content)
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


[ Back to top ](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/erc20_example.html)
Toggle Light / Dark / Auto color theme
Toggle table of contents sidebar
# 2.3. ERC20 Example - Basics[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/erc20_example.html#erc20-example-basics "Link to this heading")
We show how to run a spec and how to interpret the results.
## ERC20[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/erc20_example.html#erc20 "Link to this heading")
Let’s take as an example a straightforward simple [ERC20](https://ethereum.org/en/developers/docs/standards/tokens/erc-20/) implementation: [ERC20.sol](https://github.com/Certora/tutorials-code/blob/master/lesson2_started/erc20/ERC20.sol) (found in folder: [ERC20 lesson](https://github.com/Certora/tutorials-code/tree/master/lesson2_started/erc20)). The contract has a mapping from users to their balance and the total supply. The primary operations are `transfer`, `mint`, `burn` and `approve`. Here is a diagram of the contracts and interfaces:
![digraph {
   graph \[
   bgcolor=gray10 color=gold fontcolor=bisque label="ERC20 Implementation"
   labelloc=t margin=0 rankdir=BT
 \]
   ERC20 \[
   label="{ERC20 | ~onlyOwner\\l | increaseAllowance\\l | decreaseAllowance\\l |
   deposit\\l | withdraw\\l}"
   color=gold fontcolor=bisque fontname="DejaVu Sans Mono" fontsize=8 shape=Mrecord
   tooltip="ERC20.sol"
 \]
   IERC20 \[
   label="{IERC20 | totalSupply\\l | balanceOf\\l | transfer\\l | allowance\\l |
   approve\\l | transferFrom\\l | mint\\l | burn\\l}"
   color=greenyellow fontcolor=bisque fontname="DejaVu Sans Mono" fontsize=8
   shape=Mrecord tooltip="IERC20.sol"
 \]
   IERC20Metadata \[
   label="{IERC20Metadata | name\\l | symbol\\l | decimals\\l}"
   color=greenyellow fontcolor=bisque fontname="DejaVu Sans Mono" fontsize=8
   shape=Mrecord tooltip="IERC20Metadata.sol"
 \]
   IERC20Metadata -> IERC20 \[
   arrowhead=normal color=gold fontcolor=bisque fontname="DejaVu Sans Mono"
   fontsize=8 style=solid
 \]
   ERC20 -> IERC20Metadata \[
   arrowhead=normal color=gold fontcolor=bisque fontname="DejaVu Sans Mono"
   fontsize=8 style=solid
 \]
}](https://docs.certora.com/projects/tutorials/en/latest/_images/graphviz-c1f021da59157e2b4e855b16d93794144b6975db.png)
## A simple rule[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/erc20_example.html#a-simple-rule "Link to this heading")
Thinking about the function `transfer`, a basic property would be: 

**Correct transfer functionality:**
    
_The balance of the beneficiary is increased appropriately._
The rule `transferSpec` in [ERC20.spec](https://github.com/Certora/tutorials-code/blob/master/lesson2_started/erc20/ERC20.spec) (shown below) verifies this property. In fact, it verifies that the `transfer` operation both decreases the balance of `msg.sender` by the transferred amount, and increases the balance of the beneficiary.
```
/** @title Transfer must move `amount` tokens from the caller's
 * account to `recipient`
 */
ruletransferSpec(addressrecipient,uintamount){
enve;
// `mathint` is a type that represents an integer of any size
mathintbalance_sender_before=balanceOf(e.msg.sender);
mathintbalance_recip_before=balanceOf(recipient);
transfer(e,recipient,amount);
mathintbalance_sender_after=balanceOf(e.msg.sender);
mathintbalance_recip_after=balanceOf(recipient);
// Operations on mathints can never overflow nor underflow
assertbalance_sender_after==balance_sender_before-amount,
"transfer must decrease sender's balance by amount";
assertbalance_recip_after==balance_recip_before+amount,
"transfer must increase recipient's balance by amount";
}

```

Note
Formal verification can provide complete coverage of the input space, giving guarantees beyond what is possible from testing alone. All possible inputs to the transfer function (all possible recipients and all possible amounts) are taken into account. Additionally, all possible calling contexts are considered. The Certora Prover represents the calling context through the struct variable `env`. Declaring a single variable `e` of type `env` suffices to capture all aspects of the calling contexts. They can also be addressed individually, some example aspects of the calling context are:
  * “Who is the transfer from?” (`e.msg.sender`)
  * “In which block does the deposit occur?” (`e.block.number`)
  * “At which time does the deposit occur?” (`e.block.timestamp`)


Warning
Every call to a contract function must receive an argument of type `env` as its first parameter. We will later see that we can declare certain functions as entirely independent of the environment (using the `envfree` keyword). This will allow us to call such functions without an `env` type parameter.
## Running the Prover[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/erc20_example.html#running-the-prover "Link to this heading")
Run the following command line (from the [ERC20 lesson](https://github.com/Certora/tutorials-code/tree/master/lesson2_started/erc20) folder):
```
certoraRunERC20.sol--verifyERC20:ERC20.spec--solcsolc8.0

```

This command triggers a verification run on the contract `ERC20` from the solidity file [ERC20.sol](https://github.com/Certora/tutorials-code/blob/master/lesson2_started/erc20/ERC20.sol), checking all rules in the specification file [ERC20.spec](https://github.com/Certora/tutorials-code/blob/master/lesson2_started/erc20/ERC20.spec).
Note
It is recommended to use config files for running the Prover, see [Using config files](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/config_files.html#sec-using-config-files). Use the command line only for simple cases such as this example.
The command proceeds in two steps:
### First step[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/erc20_example.html#first-step "Link to this heading")
The solidity files are compiled with the specified solidity compiler, in this case 0.8.0, and the specification file is checked for syntax errors. This step happens on the local machine for fast feedback. The `--solc` argument is optional (see [Options that control the Solidity compiler](https://docs.certora.com/en/latest/docs/prover/cli/options.html?highlight=--solc#options-that-control-the-solidity-compiler)) You can also use this option to provide a path to the Solidity compiler executable file. The default is `solc` executable. You may also omit the `--solc`, if you use [solc-select](https://github.com/crytic/solc-select), e.g.
```
solc-selectuse0.8.0

```

### Second step[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/erc20_example.html#second-step "Link to this heading")
All necessary files are compressed and sent to Certora’s web server for verification. Verification tasks can be very heavy, so running them on the cloud can save time and resources.
Tip
To learn more about the syntax of the `certoraRun` command and its different options use the `--help` flag:
```
certoraRun--help

```

Tip
If you are using MacOS and get a `Bad CPU type in executable` error, you can fix it by installing Rosetta. Do this by executing the following in your terminal:
```
softwareupdate--install-rosetta

```

### Results[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/erc20_example.html#results "Link to this heading")
While running, the Prover will print various information to the console about the run. In the end, the output will look similar to this:
```
...
[INFO]: Process returned with 100
Job is completed! View the results at https://prover.certora.com/...
Finished verification request
ERROR: Prover found violations:
ERROR: [rule] transferSpec

```

This indicates the Prover found a violation in the rule `transferSpec`. This violation is a counter example to the rule, and can be viewed in the given link. Alternatively, you can go to [prover.certora.com](https://prover.certora.com/) and select this job’s link from the list of your recent jobs. In the link you’ll see the verification report, which looks like this:
![Report page](https://docs.certora.com/projects/tutorials/en/latest/_images/erc20_example_results.png)
## Understanding rule violations[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/erc20_example.html#understanding-rule-violations "Link to this heading")
### Viewing the counter example[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/erc20_example.html#viewing-the-counter-example "Link to this heading")
The Certora Prover helps understand violations of properties by providing concrete counter examples. To see the counter example, click the violated rule name in the report page. You will see something like this:
![Rule counter-example](https://docs.certora.com/projects/tutorials/en/latest/_images/understnding_rule_violations.png)
The counter-example shows values of the rule’s parameters and variables (on the right hand side), and a call trace (in the middle). You can investigate the call trace to see which functions were called, by clicking on the `>` symbol to open a detailed view.
### So, what is the bug?[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/erc20_example.html#so-what-is-the-bug "Link to this heading")
Notice that the value of `recipient` is the same as the value of `e.msg.sender`. We conclude that:
The rule does not hold when a user transfers to himself
Indeed, when a user transfers balance to themselves, their balance should stay the same. So there is an issue with the rule.
### Fixing and re-running[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/erc20_example.html#fixing-and-re-running "Link to this heading")
Let’s fix the rule and see if this solves the issue. We already have a fixed version in [ERC20Fixed.spec](https://github.com/Certora/tutorials-code/blob/master/lesson2_started/erc20/ERC20Fixed.spec), so we need only run it to see if it fixes the issue. Run:
```
certoraRunERC20.sol--verifyERC20:ERC20Fixed.spec--solcsolc8.0

```

## Exercise[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/erc20_example.html#exercise "Link to this heading")
Here is the _fixed rule_. Do you understand why it passes, while the previous failed?
```
/// @title Transfer must move `amount` tokens from the caller's account to `recipient`
ruletransferSpec(addressrecipient,uintamount){
enve;
// `mathint` is a type that represents an integer of any size
mathintbalance_sender_before=balanceOf(e.msg.sender);
mathintbalance_recip_before=balanceOf(recipient);
transfer(e,recipient,amount);
mathintbalance_sender_after=balanceOf(e.msg.sender);
mathintbalance_recip_after=balanceOf(recipient);
addresssender=e.msg.sender;// A convenient alias
// Operations on mathints can never overflow or underflow. 
assertrecipient!=sender=>balance_sender_after==balance_sender_before-amount,
"transfer must decrease sender's balance by amount";
assertrecipient!=sender=>balance_recip_after==balance_recip_before+amount,
"transfer must increase recipient's balance by amount";
assertrecipient==sender=>balance_sender_after==balance_sender_before,
"transfer must not change sender's balancer when transferring to self";
}

```

[ Next 2.4. ERC20 Example - preconditions ](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/preconditions.html) [ Previous 2.2. Technology Overview ](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/overview.html)
Copyright © 2023, Certora, Inc 
Made with [Sphinx](https://www.sphinx-doc.org/) and [@pradyunsg](https://pradyunsg.me)'s [Furo](https://github.com/pradyunsg/furo)
On this page 
  * [2.3. ERC20 Example - Basics](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/erc20_example.html)
    * [ERC20](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/erc20_example.html#erc20)
    * [A simple rule](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/erc20_example.html#a-simple-rule)
    * [Running the Prover](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/erc20_example.html#running-the-prover)
      * [First step](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/erc20_example.html#first-step)
      * [Second step](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/erc20_example.html#second-step)
      * [Results](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/erc20_example.html#results)
    * [Understanding rule violations](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/erc20_example.html#understanding-rule-violations)
      * [Viewing the counter example](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/erc20_example.html#viewing-the-counter-example)
      * [So, what is the bug?](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/erc20_example.html#so-what-is-the-bug)
      * [Fixing and re-running](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/erc20_example.html#fixing-and-re-running)
    * [Exercise](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/erc20_example.html#exercise)


