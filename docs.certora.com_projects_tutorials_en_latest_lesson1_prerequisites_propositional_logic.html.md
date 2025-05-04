Contents Menu Expand Light mode Dark mode Auto light/dark mode Auto light/dark, in light mode Auto light/dark, in dark mode
Hide navigation sidebar
Hide table of contents sidebar
[Skip to content](https://docs.certora.com/projects/tutorials/en/latest/lesson1_prerequisites/propositional_logic.html#furo-main-content)
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


[ Back to top ](https://docs.certora.com/projects/tutorials/en/latest/lesson1_prerequisites/propositional_logic.html)
Toggle Light / Dark / Auto color theme
Toggle table of contents sidebar
# 1.2. Introduction to predicate logic[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson1_prerequisites/propositional_logic.html#introduction-to-predicate-logic "Link to this heading")
This section provides a basic introduction to predicates, propositional logic and quantifiers. These basic concepts of mathematical logic are useful when doing formal verification, and in particular when working with the Prover. If you are familiar with these concepts, feel free to skip this section. If you wish to test your knowledge, use the [Quiz](https://docs.certora.com/projects/tutorials/en/latest/lesson1_prerequisites/propositional_logic.html#propositional-logic-quiz) below.
See also
You can find further information about these subjects in:
  1. Chapter 1 of [Introduction to Logic (written by Patrick Suppes)](http://web.mit.edu/gleitz/www/Introduction%20to%20Logic%20-%20P.%20Suppes%20\(1957\)%20WW.pdf)
  2. Chapter 3.1 of [Discrete Mathematics - An Open Introduction](http://discrete.openmathbooks.org/dmoi2/sec_propositional.html)


Tip
At the end of this section there is a handy table containing the common symbols for the logical operators and quantifiers introduced here. See [Logical operators and quantifiers table](https://docs.certora.com/projects/tutorials/en/latest/lesson1_prerequisites/propositional_logic.html#logical-operators-table).
## Propositional logic[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson1_prerequisites/propositional_logic.html#propositional-logic "Link to this heading")
_Propositional logic_ is the basis of mathematical logic, dealing with boolean variables and operations.
### Propositions[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson1_prerequisites/propositional_logic.html#propositions "Link to this heading")
We can think of a _proposition_ as a function where:
  1. all inputs have type `bool`
  2. the return type is also `bool`
  3. only logical operators are allowed in the body of the function


#### Example:[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson1_prerequisites/propositional_logic.html#example "Link to this heading")
Consider the proposition \\(P\\) which is “\\(Q\\) and \\(R\\)”. In mathematical notation this is \\(P = Q \land R\\), and in CVL we can write it as:
```
functionP(boolQ,boolR)returnsbool{
returnQ&&R;
}

```

More informally, we can simply write this proposition as a boolean expression:
`boolP=Q&&R;`
Note
The definition for a proposition given here is not the classical one. However, it is equivalent and easier to explain in our context.
### The implication operator[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson1_prerequisites/propositional_logic.html#the-implication-operator "Link to this heading")
In propositional logic, the statement \\(P\\) _implies_ \\(Q\\) means that if \\(P\\) is true then \\(Q\\) is also true. Hence the statement is true when either both \\(P\\) and \\(Q\\) are true, or when \\(P\\) is false. A complete truth table is given below in [Example: Implication truth table](https://docs.certora.com/projects/tutorials/en/latest/lesson1_prerequisites/propositional_logic.html#example-implication-table).
In mathematical notation the statement is \\(P \implies Q\\), and in CVL the syntax is `P=>Q`.
### Examples[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson1_prerequisites/propositional_logic.html#examples "Link to this heading")
Here are some more examples, shown in mathematical notation and in CVL side by side.
Math
\\((Q \vee R) \implies (P \land S)\\)
CVL
`(Q||R)=>(P&&S)`
Math
\\((P \implies (Q \vee R)) \land (\neg P \implies S)\\)
CVL
`(P=>(Q||R))&&(!P=>S)`
### Truth tables[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson1_prerequisites/propositional_logic.html#truth-tables "Link to this heading")
Since the variables of a proposition are all boolean, we can enumerate them in a table and find the output for every set of inputs. This is known as a _truth table_.
#### Example: Implication truth table[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson1_prerequisites/propositional_logic.html#example-implication-truth-table "Link to this heading")
Here is the truth table for the proposition \\(A\\) defined as “\\(B\\) implies \\(C\\)”. In mathematical notation this is \\(A = \left( B \implies C \right)\\) and in CVL:
`boolA=B=>C;`.
Truth table for implication[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson1_prerequisites/propositional_logic.html#id4 "Link to this table") B | C | A  
---|---|---  
false | false | true  
false | true | true  
true | false | false  
true | true | true  
The truth table describes the action of the implication operator \\(\implies\\).
## Predicates[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson1_prerequisites/propositional_logic.html#predicates "Link to this heading")
We can think of a _predicate_ as a function whose return type is `bool`, i.e. returns either `true` or `false`.
### Example:[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson1_prerequisites/propositional_logic.html#id2 "Link to this heading")
The function _“is_ \\(n\\) _divisible by 3”_ is a predicate. Here is the function in mathematical notation:
\begin{equation} f: \mathbb{N} \to \\{ \text{true, false} \\}, \quad f(n) = \begin{cases} \text{true} & \text{if } n \vert 3 \\\ \text{false} & \text{otherwise} \end{cases} \end{equation}
In CVL it looks like this:[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson1_prerequisites/propositional_logic.html#id5 "Link to this code")
```
functionf(intn)returnsbool{
return3*(n/3)==n;
}

```

## Quantifiers[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson1_prerequisites/propositional_logic.html#quantifiers "Link to this heading")
The statement _“there exists a natural number_ \\(n\\) _which is divisible by 3”_ is an example of a _quantifier_. This statement is true, since \\(n=3\\) is indeed divisible by _3_. In general, given a predicate \\(f(x)\\) where \\(x\\) belongs to some set \\(S\\), we can use a quantifier on \\(f\\) to make a statement in one of two ways.
### Exists[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson1_prerequisites/propositional_logic.html#exists "Link to this heading")
We can claim _“there exists_ \\(x \in S\\) _such that_ \\(f(x)\\) _holds”_. This is the _exists_ quantifier, denoted \\(\exists\\). In mathematical notation this statement is:
\\[\exists x \in S. f(x)\\]
The exists quantifier can be thought of as a using the _or_ operator over all \\(x \in S\\). For example, the statement _“there exists a natural number_ \\(n\\) _which is divisible by 3”_ is the same as:
\\[(1 \vert 3) \vee (2 \vert 3) \vee (3 \vert 3) \vee (4 \vert 3) \cdots = \bigvee_{n \in \mathbb{N}} n \vert 3\\]
Solidity code realizing this is:
```
functionexistsDivisibleByThree()externalreturns(bool){
for(uint256i=1;i<type(uint256).max;i++){
if(i%3==0)returntrue;
}
returnfalse;
}

```

In CVL we have the keyword `exists`, for example:
```
require(existsuintn.(n%3)==0);

```

### For all[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson1_prerequisites/propositional_logic.html#for-all "Link to this heading")
The _forall_ quantifier requires that the predicate be satisfied by all possible inputs. An example of this is the statement: _“for all natural numbers_ \\(n\\) _either_ \\(n\\) _is even, or_ \\(n + 1\\) _is even”_. The forall quantifier is denoted \\(\forall\\), so the statement in mathematical notation is:
\\[\forall n \in \mathbb{N}. (n \vert 2) \vee (n + 1 \vert 2)\\]
In general, given a predicate \\(f(x)\\) where \\(x \in S\\), we can form the statement \\(\forall x \in S. f(x)\\). The forall quantifier is the same as using the _and_ operator on \\(f(x)\\) for all \\(x \in S\\), in mathematical notation:
\\[\forall x \in S. f(x) = \bigwedge_{x \in S} f(x)\\]
The negation of a forall statement can be given in the form of an exists statement, like this (the negation is denoted by the symbol \\(\neg\\)):
\\[\neg \left( \forall x \in S. f(x) \right) = \exists x \in S. \neg f(x)\\]
This comes in handy when writing code realizing a forall statement.
#### Example:[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson1_prerequisites/propositional_logic.html#id3 "Link to this heading")
Here is the solidity code realizing the statement _“for all_ \\(n\\) _either_ \\(n\\) _is even, or_ \\(n + 1\\) _is even”_ :
```
functionallAreEven()externalreturns(bool){
for(uint256i=1;i<type(uint256).max;i++){
if(i%2!=0&&(i+1)%2!=0)returnfalse;
}
returntrue;
}

```

In CVL we have the keyword `forall`, for example:
```
require(foralluintn.(n%2==0)||((n+1)%2==0));

```

## Vacuity[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson1_prerequisites/propositional_logic.html#vacuity "Link to this heading")
Consider the statement: _“For all_ \\(n \in \mathbb{N}\\) _if both_ \\(n\\) _and_ \\(n + 1\\) _are even, then_ \\(n = n + 2\\) _“_. In mathematical notation:
\\[\forall n \in \mathbb{N}. (n \vert 2) \land (n + 1 \vert 2) \implies (n = n + 2)\\]
Surprisingly, this statement is **true**. Because for every \\(n\\) the part \\((n \vert 2) \land (n + 1 \vert 2)\\) is always **false** , so by the [Truth table for implication](https://docs.certora.com/projects/tutorials/en/latest/lesson1_prerequisites/propositional_logic.html#truth-table-for-implication) the implication is **true**.
In general, given a statement of the form \\(\forall x \in S. f(x) \implies g(x)\\) where \\(f\\) and \\(g\\) are predicates, we say the statement _holds vacuously_ (or _is satisfied vacuously_) if \\(\forall x \in S. \neg f(x)\\). This means there is not even a single element \\(x \in S\\) for which \\(f(x)\\) holds.
While this may seem like an edge case, it can easily occur that heaping conditions on a statement ends with the statement being satisfied vacuously.
## Logical operators and quantifiers[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson1_prerequisites/propositional_logic.html#logical-operators-and-quantifiers "Link to this heading")
Logical operators and quantifiers table[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson1_prerequisites/propositional_logic.html#id6 "Link to this table") Name | Math symbol | CVL | Description  
---|---|---|---  
and | \\(\land\\) | `&&` | And operation  
or | \\(\vee\\) | `||` | Or operation  
implies | \\(\implies\\) | `=>` | Implication operation  
not | \\(\neg\\) | `!` | Negation operation  
if and only if | \\(\Longleftrightarrow\\) | `<=>` (also `==`, see below) | Equality of booleans  
forall | \\(\forall\\) | `forall` | For all elements in a set, it holds that …  
exist | \\(\exists\\) | `exist` | There exists an element in a set, such that …  
Note
The _“if and only if”_ operator is the same as euqality of booleans, meaning \\(P \Longleftrightarrow Q\\) is the same as `P==Q`.
## Quiz[¶](https://docs.certora.com/projects/tutorials/en/latest/lesson1_prerequisites/propositional_logic.html#quiz "Link to this heading")
Test your knowledge with our quiz below (additional questions can be found on the first part of the [Secureum Quiz](https://docs.google.com/document/d/19lLWqTrm_bzDdY9Uk-LpTSkgabk9WGtuCTPLDzSoraM/edit?usp=sharing)).
  1. When is the expression \\(P \implies Q\\) _false_?
    1. When \\(\neg P \land \neg Q\\) is true (i.e. when both \\(P\\) and \\(Q\\) are false)
    2. When \\(P \land Q\\) is true
    3. When \\(\neg P \land Q\\) is true
    4. None of the above
  2. When is the expression \\(P \land Q \ \implies P\\) _true_?
    1. Always (it is true in all cases)
    2. Never (it is false in all cases)
    3. True for some cases and false for others
    4. None of the above
  3. When is the expression \\(\left( P \land \left( Q \vee \neg P \right) \right) \land \neg Q\\) _true_?
    1. Always (it is true in all cases)
    2. Never (it is false in all cases)
    3. True for some cases and false for others
  4. If we know that the expression \\(P \implies \left(P \land \neg Q \right)\\) is _true_ , and that \\(P\\) is _true_ , then we can deduce that:
    1. \\(Q\\) is true
    2. \\(Q\\) is false
    3. \\(Q\\) can be either true or false (we can deduce nothing)

Answers
  1.     1. None of the above
  2.     1. Always
  3.     1. Never
  4.     1. \\(Q\\) is false


[ Next 1.3. Introduction to formal verification ](https://docs.certora.com/projects/tutorials/en/latest/lesson1_prerequisites/formal_verification.html) [ Previous 1.1. Background ](https://docs.certora.com/projects/tutorials/en/latest/lesson1_prerequisites/background.html)
Copyright © 2023, Certora, Inc 
Made with [Sphinx](https://www.sphinx-doc.org/) and [@pradyunsg](https://pradyunsg.me)'s [Furo](https://github.com/pradyunsg/furo)
On this page 
  * [1.2. Introduction to predicate logic](https://docs.certora.com/projects/tutorials/en/latest/lesson1_prerequisites/propositional_logic.html)
    * [Propositional logic](https://docs.certora.com/projects/tutorials/en/latest/lesson1_prerequisites/propositional_logic.html#propositional-logic)
      * [Propositions](https://docs.certora.com/projects/tutorials/en/latest/lesson1_prerequisites/propositional_logic.html#propositions)
        * [Example:](https://docs.certora.com/projects/tutorials/en/latest/lesson1_prerequisites/propositional_logic.html#example)
      * [The implication operator](https://docs.certora.com/projects/tutorials/en/latest/lesson1_prerequisites/propositional_logic.html#the-implication-operator)
      * [Examples](https://docs.certora.com/projects/tutorials/en/latest/lesson1_prerequisites/propositional_logic.html#examples)
      * [Truth tables](https://docs.certora.com/projects/tutorials/en/latest/lesson1_prerequisites/propositional_logic.html#truth-tables)
        * [Example: Implication truth table](https://docs.certora.com/projects/tutorials/en/latest/lesson1_prerequisites/propositional_logic.html#example-implication-truth-table)
    * [Predicates](https://docs.certora.com/projects/tutorials/en/latest/lesson1_prerequisites/propositional_logic.html#predicates)
      * [Example:](https://docs.certora.com/projects/tutorials/en/latest/lesson1_prerequisites/propositional_logic.html#id2)
    * [Quantifiers](https://docs.certora.com/projects/tutorials/en/latest/lesson1_prerequisites/propositional_logic.html#quantifiers)
      * [Exists](https://docs.certora.com/projects/tutorials/en/latest/lesson1_prerequisites/propositional_logic.html#exists)
      * [For all](https://docs.certora.com/projects/tutorials/en/latest/lesson1_prerequisites/propositional_logic.html#for-all)
        * [Example:](https://docs.certora.com/projects/tutorials/en/latest/lesson1_prerequisites/propositional_logic.html#id3)
    * [Vacuity](https://docs.certora.com/projects/tutorials/en/latest/lesson1_prerequisites/propositional_logic.html#vacuity)
    * [Logical operators and quantifiers](https://docs.certora.com/projects/tutorials/en/latest/lesson1_prerequisites/propositional_logic.html#logical-operators-and-quantifiers)
    * [Quiz](https://docs.certora.com/projects/tutorials/en/latest/lesson1_prerequisites/propositional_logic.html#quiz)


