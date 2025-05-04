[ Certora Prover Documentation ![Logo](https://docs.certora.com/en/latest/_static/Certora_Logo_Black.svg) ](https://docs.certora.com/en/latest/index.html)
Contents
  * [Certora User’s Guide](https://docs.certora.com/en/latest/docs/user-guide/index.html)
  * [The Certora Verification Language](https://docs.certora.com/en/latest/docs/cvl/index.html)
  * [The Certora Prover](https://docs.certora.com/en/latest/docs/prover/index.html)
    * [Introduction](https://docs.certora.com/en/latest/docs/prover/intro.html)
    * [Installation](https://docs.certora.com/en/latest/docs/user-guide/install.html)
    * [Prover Approximations](https://docs.certora.com/en/latest/docs/prover/approx/index.html)
      * [Loop Unrolling](https://docs.certora.com/en/latest/docs/prover/approx/loops.html)
      * [Method Summarization](https://docs.certora.com/en/latest/docs/prover/approx/summarization.html)
      * [Harnessing](https://docs.certora.com/en/latest/docs/prover/approx/harnessing.html)
      * [Modeling of Hashing in the Certora Prover](https://docs.certora.com/en/latest/docs/prover/approx/hashing.html)
      * [Quantifier Grounding](https://docs.certora.com/en/latest/docs/prover/approx/grounding.html)
        * [How grounding works](https://docs.certora.com/en/latest/docs/prover/approx/grounding.html#how-grounding-works)
        * [Limitations on grounding](https://docs.certora.com/en/latest/docs/prover/approx/grounding.html#limitations-on-grounding)
    * [Techniques Used by the Certora Prover](https://docs.certora.com/en/latest/docs/prover/techniques/index.html)
    * [Diagnostic Tools](https://docs.certora.com/en/latest/docs/prover/diagnosis/index.html)
    * [Checking Specifications](https://docs.certora.com/en/latest/docs/prover/checking/index.html)
    * [Certora Prover CLI](https://docs.certora.com/en/latest/docs/prover/cli/index.html)
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
  * [Prover Approximations](https://docs.certora.com/en/latest/docs/prover/approx/index.html)
  * Quantifier Grounding
  * [ View page source](https://docs.certora.com/en/latest/_sources/docs/prover/approx/grounding.md.txt)


# [Quantifier Grounding](https://docs.certora.com/en/latest/docs/prover/approx/grounding.html#id1)[](https://docs.certora.com/en/latest/docs/prover/approx/grounding.html#quantifier-grounding "Link to this heading")
[Quantified expressions](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-quantifier) are a very powerful tool for writing specifications, but they can also lead to incredibly long running times. For this reason, the Prover uses an approximation called “grounding”.
It is not possible to ground every expression perfectly. While grounding is [sound](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-sound) (i.e. it will not allow a rule to be verified if it is not true), there are cases where it may generate [counterexample](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-counterexample)s even for rules that should pass. For example, a counterexample may not obey a `require` statement that contains a quantifier.
You can prevent spurious counterexamples by turning off grounding (by passing [smt_groundQuantifiers](https://docs.certora.com/en/latest/docs/prover/cli/options.html#smt-groundquantifiers)), but without grounding the Prover may run considerably slower, and is likely to time out.
The remainder of this document explains grounding in more detail, and lists the specific kinds of quantified expressions that may lead to spurious counterexamples. We also include some suggestions for rewriting your quantified statements to avoid spurious counterexamples.
Contents
  * [Quantifier Grounding](https://docs.certora.com/en/latest/docs/prover/approx/grounding.html#quantifier-grounding)
    * [How grounding works](https://docs.certora.com/en/latest/docs/prover/approx/grounding.html#how-grounding-works)
    * [Limitations on grounding](https://docs.certora.com/en/latest/docs/prover/approx/grounding.html#limitations-on-grounding)
      * [Alternating Quantifiers](https://docs.certora.com/en/latest/docs/prover/approx/grounding.html#alternating-quantifiers)
      * [Recursion](https://docs.certora.com/en/latest/docs/prover/approx/grounding.html#recursion)
      * [Variables must be arguments](https://docs.certora.com/en/latest/docs/prover/approx/grounding.html#variables-must-be-arguments)
      * [Double Polarity](https://docs.certora.com/en/latest/docs/prover/approx/grounding.html#double-polarity)


## [How grounding works](https://docs.certora.com/en/latest/docs/prover/approx/grounding.html#id2)[](https://docs.certora.com/en/latest/docs/prover/approx/grounding.html#how-grounding-works "Link to this heading")
Quantifier grounding transforms a [quantified](https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-quantifier) statement into a series of non-quantified statements. For example, suppose a specification contains the following [ghost axiom](https://docs.certora.com/en/latest/docs/cvl/ghosts.html#ghost-axioms):
```
ghostf(uintx)returns(mathint){
init_stateaxiomforalluintx.f(x)==0
}

```
Copy to clipboard
This statement logically says that `f(0) == 0` and `f(1) == 0` and `f(2) == 0` and so on. In practice, however, the verification may only make use of a small finite number of these facts. Grounding is the process of automatically replacing the `forall` statement with the specific unquantified statements that are necessary.
For example, if the program and specification only ever access `f(2)`, `f(9)`, `f(y+3)`, and `f(z)`, then the axiom above would be automatically replaced with:
```
ghostf(uintx)returns(mathint){
init_stateaxiomf(2)==0;
init_stateaxiomf(9)==0;
init_stateaxiomf(y+3)==0;
init_stateaxiomf(z)==0;
}

```
Copy to clipboard
The Prover will also ground more complex quantified expressions, and will ground them anywhere that you can write a quantified statement (e.g. `assert` and `require` statements, ghost axioms, and invariants). Grounding also works with `exists` quantifiers.
## [Limitations on grounding](https://docs.certora.com/en/latest/docs/prover/approx/grounding.html#id3)[](https://docs.certora.com/en/latest/docs/prover/approx/grounding.html#limitations-on-grounding "Link to this heading")
In some cases, there is an easy way to rewrite your expression with fewer quantifiers. For example, the following quantified statement requires that `f(x)` is always odd, but it is written in a way that violates [one of the restrictions on quantifiers](https://docs.certora.com/en/latest/docs/prover/approx/grounding.html#grounding-arguments):
```
requireforalluintx.forallmathinty.f(x)!=2*y;

```
Copy to clipboard
However, there is a much simpler way to require that `f(x)` is odd by using `%`:
```
requireforalluintx.f(x)%2==1;

```
Copy to clipboard
This rewritten statement obeys the rules listed below, and therefore will not produce any spurious counterexamples.
The remainder of this section describes specific cases where the Prover cannot ground quantified statements, and gives advice on how to work around those limitations.
### [Alternating Quantifiers](https://docs.certora.com/en/latest/docs/prover/approx/grounding.html#id4)[](https://docs.certora.com/en/latest/docs/prover/approx/grounding.html#alternating-quantifiers "Link to this heading")
Alternating quantifiers (those containing `forall` followed by `exist` or vice-versa) complicate the process of grounding, so there are limitations to what statements you can write and which of them are grounded.
In most contexts, you may not have a `forall` expression contained inside of an `exists` statement. For example, this is allowed:
```
assertforalladdressx.foralluinty.existsuintz.existsuintw.e(x,y,z,w);

```
Copy to clipboard
but this is disallowed:
```
assertforalladdressx.existsaddressy.existsaddressz.foralladdressw.e(x,y,z,w);

```
Copy to clipboard
In the latter case, the `forall address w` is contained inside the `exists address z`.
Logical negations and `require` statements reverse the rules for `forall` and `exists` statements: in those contexts, you cannot nest an `exists` expression inside of a `forall` statement. Including another negation will again reverse the rules. For example, the following are allowed:
```
requireexistsaddressx.foralluinty.e(x,y);
assert!(existsaddressx.foralluinty.e(x,y));
require!(foralladdressx.existsuinty.e(x,y));
assert!(!(foralladdressx.existsuinty.e(x,y)));

```
Copy to clipboard
but these are disallowed:
```
requireforalladdressx.existsuinty.e(x,y);
assert!(foralladdressx.existsuinty.e(x,y));

```
Copy to clipboard
One common way to work around these limitations is by replacing `exists` expressions with concrete expressions that produce the values that should exist.
For example, suppose your contract function always returned twice its input:
```
functionf(uintx)externalreturns(uint){return2*x;}

```
Copy to clipboard
You might like to prove that if `x` is positive, then it’s possible for `f` to output something smaller than `f(x)`:
```
assertforalluintx.(x>0)=>(existsuinty.f(y)<f(x));

```
Copy to clipboard
This is clearly true; for example `f(x - 1)` is always smaller than `f(x)`, as is `f(0)`. However, to work around the nested quantifier restriction, we have to help the Prover find the correct value for `y`. We could replace this statement with either of the following two:
```
assertforalluintx.(x>0)=>f(0)<f(x);
assertforalluintx.(x>0)=>f(x-1)<f(x);

```
Copy to clipboard
### [Recursion](https://docs.certora.com/en/latest/docs/prover/approx/grounding.html#id5)[](https://docs.certora.com/en/latest/docs/prover/approx/grounding.html#recursion "Link to this heading")
Quantified statements that relate a function with itself on two different inputs may give incorrect counterexamples. For example, the following `forall` statement refers to `f` twice:
```
rule recursiveQuantifier {
  require forall uint x . f(x) > f(x-1);
  assert f(8) > f(6);
}

```
Copy to clipboard
Although we can see that the assertion must be true, we would need to combine the statements `f(8) > f(7)` and `f(7) > f(6)` to prove it, and the grounding mechanism is unable to do this.
In these cases, you may see a counterexample that doesn’t satisfy the `require` statement; in this case the best option is to disable grounding with [smt_groundQuantifiers](https://docs.certora.com/en/latest/docs/prover/cli/options.html#smt-groundquantifiers).
### [Variables must be arguments](https://docs.certora.com/en/latest/docs/prover/approx/grounding.html#id6)[](https://docs.certora.com/en/latest/docs/prover/approx/grounding.html#variables-must-be-arguments "Link to this heading")
In order for grounding to work, every variable appearing in a quantified statement must be used at least once as an argument to a ghost or contract function. For example, neither of the following examples are allowed:
```
requireforallmathintx.x*2!=y;
requireforalluintx.forallmathinty.f(x)!=2*y;

```
Copy to clipboard
In the first example, `x` is not used as an argument to a function, while in the second case, `y` is not.
Although you are allowed to call functions on complicated expressions that use quantified variables, doing so may produce spurious counterexamples. For example, the following is allowed, but is likely to produce spurious counterexamples (because `x` itself is not an argument to a function):
```
requireforalluintx.f(2*x)==0;

```
Copy to clipboard
This particular example requires that all even inputs to `f` produce `0` as output; it could be rewritten as follows:
```
requireforalluinty.(y%2==0)=>f(y)==0;

```
Copy to clipboard
If you use a quantified variable in an argument to two different functions, you may produce spurious counterexamples. For example:
```
requireforalluintx.f(x)<=g(x+1)&&g(x+1)!=0;

```
Copy to clipboard
Here, `x + 1` is used as an argument to `g`, but `x` is not; you may get counterexamples where `g(x+1) == 0` for some `x`. In that case, you can add an additional equivalent require that does use the quantified variable as an argument to `g`:
```
requireforalluintx.f(x)<g(x+1)&&g(x+1)!=0;
requireforalluintx.f(x-1)<g(x)&&g(x)!=0;

```
Copy to clipboard
This will make `x` a direct argument to `g`, so the expression will be grounded properly.
### [Double Polarity](https://docs.certora.com/en/latest/docs/prover/approx/grounding.html#id7)[](https://docs.certora.com/en/latest/docs/prover/approx/grounding.html#double-polarity "Link to this heading")
The polarity of a sub-formula is the direction of the effect it has on the output of the formula. This is best demonstrated through an example:
```
a&&(b||!c)

```
Copy to clipboard
In this example, `b` possesses a positive polarity because changing `b` from `false` to `true` can’t make the formula `false` if it wasn’t before. Informally, making `b` “more true” can only make the whole formula “more true”.
In this example, `a` also possesses positive polarity: if the formula was true when `a` was `false`, it must also be `true` when `a` is `true`.
On the other hand, `c` has a negative polarity because changing `c` from `true` to `false` can only make the statement “more false”. If can’t become `true` if it wasn’t true before.
Sub-expressions can also have double polarity. For example, consider the formula
```
a <=> b

```
Copy to clipboard
In this example, `a` has double polarity, because making `a` true could cause the formula to become `false` when it was true before, but it could also cause the formula to become `true` when it wasn’t before.
Grounding is disallowed when the quantified expression has double polarity in the rule. For example, the following is disallowed, because the `forall` statement has double polarity.
```
ruler{
...
assert(foralluintx.f(x)>0)<=>y;
}

```
Copy to clipboard
In many cases you can split a rule with a quantifier in a double-polarity position into multiple rules with single-polarity quantifiers. For example, the above assertion could be split into two rules:
```
ruler1{
...
assert(foralluintx.f(x)>0)=>y;
}
ruler2{
...
asserty=>(foralluintx.f(x)>0);
}

```
Copy to clipboard
Verifying `r1` and `r2` is logically equivalent to verifying `r`, but the quantified expression appears with single polarity in each of the two rules.
[ Previous](https://docs.certora.com/en/latest/docs/prover/approx/hashing.html "Modeling of Hashing in the Certora Prover") [Next ](https://docs.certora.com/en/latest/docs/prover/techniques/index.html "Techniques Used by the Certora Prover")
© Copyright 2025, Certora, Inc.
Built with [Sphinx](https://www.sphinx-doc.org/) using a [theme](https://github.com/readthedocs/sphinx_rtd_theme) provided by [Read the Docs](https://readthedocs.org). 
