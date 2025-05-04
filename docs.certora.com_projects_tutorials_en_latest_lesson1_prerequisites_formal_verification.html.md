Contents Menu Expand Light mode Dark mode Auto light/dark mode Auto light/dark, in light mode Auto light/dark, in dark mode
Hide navigation sidebar
Hide table of contents sidebar
[Skip to content](https://docs.certora.com/projects/tutorials/en/latest/lesson1_prerequisites/formal_verification.html#furo-main-content)
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


[ Back to top ](https://docs.certora.com/projects/tutorials/en/latest/lesson1_prerequisites/formal_verification.html)
Toggle Light / Dark / Auto color theme
Toggle table of contents sidebar
# 1.3. Introduction to formal verification[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson1_prerequisites/formal_verification.html#introduction-to-formal-verification "Link to this heading")
Formal verification is about _proving_ [correctness](https://en.wikipedia.org/wiki/Correctness_\(computer_science\)) of algorithms using _formal methods_. You can read more about this on [Wikipedia - Formal verification](https://en.wikipedia.org/wiki/Formal_verification). Here we will instead show an example.
Example:
Consider the Birth Months riddle (from [Braingle](https://www.braingle.com/)), reproduced below, we will use formal verification to find a solution, and also to prove that this solution is unique.
```
Four sisters, Sara, Ophelia, Nora, and Dawn, were each born in a different one of
the months September, October, November, and December.
"This is terrible," said Ophelia one day. "None of us have an initial that matches
the initial of her birth month."
"I don't mind at all," replied the girl who was born in September.
"That's easy for you to say," said Nora. "It would at least be cool if the initial
of my birth month was a vowel, but no."
In which month was each girl born?

```

## Finding a solution[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson1_prerequisites/formal_verification.html#finding-a-solution "Link to this heading")
### Step 1[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson1_prerequisites/formal_verification.html#step-1 "Link to this heading")
The first step is to translate the riddle into a more formal form. Here is a description of the months as numbers in CVL:
```
// The months
definitionSeptember()returnsuint8=9;
definitionOctober()returnsuint8=10;
definitionNovember()returnsuint8=11;
definitionDecember()returnsuint8=12;

```

We use the sisters’ names as parameters (whose value is the birth month of that sister):
```
rulesistersBirthMonths(
uint8Sara,
uint8Ophelia,
uint8Nora,
uint8Dawn
){

```

### Step 2[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson1_prerequisites/formal_verification.html#step-2 "Link to this heading")
We add all the data in the riddle. For example, saying that Sarah was born in either September, October, November or December is:
```
requireSara>=September()&&Sara<=December();

```

Each sister was born in one of the four months:
```
requireSara>=September()&&Sara<=December();
requireOphelia>=September()&&Ophelia<=December();
requireNora>=September()&&Nora<=December();
requireDawn>=September()&&Dawn<=December();

```

Each sister’s initial is different from the initial of her birth month:
```
require(
Sara!=September()&&
Ophelia!=October()&&
Nora!=November()&&
Dawn!=December()
);

```

Clues about Ophelia and Nora:
```
// Ophelia is not the girl who was born in September
requireOphelia!=September();
// Nora is not the girl who was born in September
requireNora!=September();
// Nora's birth month does not start with a vowel
requireNora!=October();

```

The sisters were born on different months:
```
require(
Sara!=Ophelia&&
Sara!=Nora&&
Sara!=Dawn&&
Ophelia!=Nora&&
Ophelia!=Dawn&&
Nora!=Dawn
);

```

### Step 3[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson1_prerequisites/formal_verification.html#step-3 "Link to this heading")
We ask for a solution that satisfies all these requirements, using the CVL statement:
```
satisfytrue;

```

### Step 4[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson1_prerequisites/formal_verification.html#step-4 "Link to this heading")
The entire rule is found in [sisters.spec](https://github.com/Certora/tutorials-code/blob/master/lesson1_prerequisites/formal_verification/sisters.spec). Running the Certora Prover on this rule would provide a solution (if one exists). You will learn about running the Certora Prover in Lesson 2 [Getting Started](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/index.html#lesson2-started), in particular in Section [Running the Prover](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/erc20_example.html#sec-running-the-prover). For now we will provide the answer given by the Certora Prover, which looks like this:
```
*----------------------------------- ... --------------*
|Rule name     |Verified   |    |Local vars |
|-------------------|-------------|- ... --|-----------|
|sistersBirthMonths |Not violated |    |Dawn=9   |
|          |       |    |Nora=12  |
|          |       |    |Ophelia=11 |
|          |       |    |Sara=10  |
|          |       |    | ...    |
*----------------------------------- ... --------------*

```

So, Sara was born in October, Ophelia was born in November, Nora was born in December, and Dawn was born in September.
If you want to run the Certora Prover yourself
Go to the folder [lesson1_prerequisites/formal_verification/](https://github.com/Certora/tutorials-code/tree/master/lesson1_prerequisites/formal_verification) and enter:
```
certoraRunEmpty.sol--verifyEmpty:sisters.spec--solcsolc8.0--rulesistersBirthMonths

```

## Proving the solution is unique[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson1_prerequisites/formal_verification.html#proving-the-solution-is-unique "Link to this heading")
To prove the solution is unique, we build another rule, called `solutionIsUnique`, containing all the requirements above. However, instead of the `satisfytrue;` statement we add the assertion that the only solution is the one we found:
```
assert(
Sara==October()&&
Ophelia==November()&&
Nora==December()&&
Dawn==September()
);

```

If the assertion is violated, the Prover will provide a counter-example to the assertion. Such a counter-example would be another solution, showing the previous solution is not unique.
Running the Certora Prover on this new rule simply returns:
```
*---------------------------------- ...
|Rule name    |Verified   |
|-----------------|-------------|-- ...
|solutionIsUnique |Not violated |

```

Which proves the solution is unique.
To run the Certora Prover on this rule
Go to the folder [lesson1_prerequisites/formal_verification/](https://github.com/Certora/tutorials-code/tree/master/lesson1_prerequisites/formal_verification) and enter:
```
certoraRunEmpty.sol--verifyEmpty:sisters.spec--solcsolc8.0--rulesolutionIsUnique

```

This rule is also found at [sisters.spec](https://github.com/Certora/tutorials-code/blob/master/lesson1_prerequisites/formal_verification/sisters.spec). Here is the complete rule:
```
/// @title Verify that the solution is unique
rulesolutionIsUnique(
uint8Sara,
uint8Ophelia,
uint8Nora,
uint8Dawn
){
// Each sister was born in one of the four months
requireSara>=September()&&Sara<=December();
requireOphelia>=September()&&Ophelia<=December();
requireNora>=September()&&Nora<=December();
requireDawn>=September()&&Dawn<=December();
// "None of us have an initial that matches the initial of her birth month."
require(
Sara!=September()&&
Ophelia!=October()&&
Nora!=November()&&
Dawn!=December()
);
// Ophelia is not the girl who was born in September
requireOphelia!=September();
// Nora is not the girl who was born in September
requireNora!=September();
// Nora's birth month does not start with a vowel
requireNora!=October();
// The sisters were born on different months
require(
Sara!=Ophelia&&
Sara!=Nora&&
Sara!=Dawn&&
Ophelia!=Nora&&
Ophelia!=Dawn&&
Nora!=Dawn
);
assert(
Sara==October()&&
Ophelia==November()&&
Nora==December()&&
Dawn==September()
);
}

```

[ Next 2. Getting Started ](https://docs.certora.com/projects/tutorials/en/latest/lesson2_started/index.html) [ Previous 1.2. Introduction to predicate logic ](https://docs.certora.com/projects/tutorials/en/latest/lesson1_prerequisites/propositional_logic.html)
Copyright © 2023, Certora, Inc 
Made with [Sphinx](https://www.sphinx-doc.org/) and [@pradyunsg](https://pradyunsg.me)'s [Furo](https://github.com/pradyunsg/furo)
On this page 
  * [1.3. Introduction to formal verification](https://docs.certora.com/projects/tutorials/en/latest/lesson1_prerequisites/formal_verification.html)
    * [Finding a solution](https://docs.certora.com/projects/tutorials/en/latest/lesson1_prerequisites/formal_verification.html#finding-a-solution)
      * [Step 1](https://docs.certora.com/projects/tutorials/en/latest/lesson1_prerequisites/formal_verification.html#step-1)
      * [Step 2](https://docs.certora.com/projects/tutorials/en/latest/lesson1_prerequisites/formal_verification.html#step-2)
      * [Step 3](https://docs.certora.com/projects/tutorials/en/latest/lesson1_prerequisites/formal_verification.html#step-3)
      * [Step 4](https://docs.certora.com/projects/tutorials/en/latest/lesson1_prerequisites/formal_verification.html#step-4)
    * [Proving the solution is unique](https://docs.certora.com/projects/tutorials/en/latest/lesson1_prerequisites/formal_verification.html#proving-the-solution-is-unique)


