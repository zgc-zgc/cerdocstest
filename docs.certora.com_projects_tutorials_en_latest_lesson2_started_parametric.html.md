Contents Menu Expand Light mode Dark mode Auto light/dark mode Auto light/dark, in light mode Auto light/dark, in dark mode
Hide navigation sidebar
Hide table of contents sidebar
[Skip to content](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/parametric.html#furo-main-content)
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


[ Back to top ](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/parametric.html)
Toggle Light / Dark / Auto color theme
Toggle table of contents sidebar
# 2.5. Parametric rules[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/parametric.html#parametric-rules "Link to this heading")
We continue with our [ERC20](https://github.com/Certora/tutorials-code/blob/master/lesson2_started/erc20/ERC20.sol) example, to demonstrate _parametric rules_.
## The need[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/parametric.html#the-need "Link to this heading")
Many properties can be generalized for all the contract’s functions. For example, consider the property: 

Allowance integrity:
    
_The_ `allowance` _can only be changed by the owner._
This property should hold regardless of the contract method called. To do so, we introduce the notion of _parametric rules_.
## Usage[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/parametric.html#usage "Link to this heading")
### Applying[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/parametric.html#applying "Link to this heading")
To simulate the execution of all functions in the main contract we use a method variable `methodf`, either as a parameter to the rule, or as a local variable. The most common usage is to simulate any method on any arguments, using the following syntax:
```
rulesomeParametricRule(methodf){
...
enve;// The env for f
calldataargargs;// Any possible arguments for f
f(e,args);// Calling the contract method f
...
}

```

Different functions in the contract might have different number or types of parameters. Using a variable of CVL type `calldataarg` solves this problem and ensures that each simulated contract method gets valid input parameters.
### Referring to particular methods[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/parametric.html#referring-to-particular-methods "Link to this heading")
At times, we need to handle particular methods differently. For example we sometimes wish to exclude certain methods from the rule. To differentiate between methods (or values of `methodf`) use `selector` and `sig`, like so:
```
f.selector==sig:approve(address,uint).selector

```

The above evaluates to `true` when `f` is the method `approve` _with the specified signature_.
Here is a more complete example from [Parametric.spec](https://github.com/Certora/tutorials-code/blob/master/lesson2_started/erc20/Parametric.spec):
```
// Assert that if the allowance changed then `approve` or `increaseAllowance` was called.
assert(
allowance_after>allowance_before=>
(
f.selector==sig:approve(address,uint).selector||
f.selector==sig:increaseAllowance(address,uint).selector
)
),
"only approve and increaseAllowance can increase allowances";
}

```

## Example[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/parametric.html#example "Link to this heading")
Run the parametric rule from [Parametric.spec](https://github.com/Certora/tutorials-code/blob/master/lesson2_started/erc20/Parametric.spec):
```
certoraRunERC20.sol--verifyERC20:Parametric.spec--solcsolc8.0--msg"Parametric rule"

```

The rule would have a check mark (i.e. passed verification) only if it was verified on _all contract methods_. An inner rule is created for every function in the main contract, as you can see in the report page. Click on the function name to see its counter-example.
This rule uncovers a bug in `decreaseAllowance` method. Can you understand the counter-example?
## Conclusion[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/parametric.html#conclusion "Link to this heading")
Parametric rules enable expressing reusable and concise [correctness](https://en.wikipedia.org/wiki/Correctness_\(computer_science\)) conditions. Note that they are _not dependent on the implementation_. So you can integrate them easily into the CI to verify changes to the code, including signature changes, new functions, and implementation changes.
[ Next 2.6. Using config files ](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/config_files.html) [ Previous 2.4. ERC20 Example - preconditions ](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/preconditions.html)
Copyright © 2023, Certora, Inc 
Made with [Sphinx](https://www.sphinx-doc.org/) and [@pradyunsg](https://pradyunsg.me)'s [Furo](https://github.com/pradyunsg/furo)
On this page 
  * [2.5. Parametric rules](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/parametric.html)
    * [The need](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/parametric.html#the-need)
    * [Usage](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/parametric.html#usage)
      * [Applying](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/parametric.html#applying)
      * [Referring to particular methods](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/parametric.html#referring-to-particular-methods)
    * [Example](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/parametric.html#example)
    * [Conclusion](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/parametric.html#conclusion)


