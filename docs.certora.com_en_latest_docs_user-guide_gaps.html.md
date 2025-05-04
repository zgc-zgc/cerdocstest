[ Certora Prover Documentation ![Logo](https://docs.certora.com/en/latest/_static/Certora_Logo_Black.svg) ](https://docs.certora.com/en/latest/index.html)
Contents
  * [Certora User’s Guide](https://docs.certora.com/en/latest/docs/user-guide/index.html)
    * [Installation](https://docs.certora.com/en/latest/docs/user-guide/install.html)
    * [Installing an EVM compiler and VS Code Extension](https://docs.certora.com/en/latest/docs/user-guide/install_evm_compiler.html)
    * [Tutorial and Workshops](https://docs.certora.com/en/latest/docs/user-guide/tutorials.html)
    * [Running the Certora Prover](https://docs.certora.com/en/latest/docs/user-guide/running.html)
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
      * [Loops](https://docs.certora.com/en/latest/docs/user-guide/gaps.html#loops)
        * [Determining the number of needed iterations](https://docs.certora.com/en/latest/docs/user-guide/gaps.html#determining-the-number-of-needed-iterations)
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
  * Understanding gaps between high and low level code
  * [ View page source](https://docs.certora.com/en/latest/_sources/docs/user-guide/gaps.md.txt)


# Understanding gaps between high and low level code[](https://docs.certora.com/en/latest/docs/user-guide/gaps.html#understanding-gaps-between-high-and-low-level-code "Link to this heading")
The Certora Prover analyzes low-level code, such as the EVM bytecode. However, the CVL specification, Rule Report, and Call Trace usually present information in terms of a high-level language (e.g., Solidity).
In this document, we describe how some of the gaps between the high-level source and the low-level bytecode can affect our understanding of the Prover’s outputs and recommended solutions.
## Loops[](https://docs.certora.com/en/latest/docs/user-guide/gaps.html#loops "Link to this heading")
### Determining the number of needed iterations[](https://docs.certora.com/en/latest/docs/user-guide/gaps.html#determining-the-number-of-needed-iterations "Link to this heading")
The Prover deals with loops by unrolling them a constant number of times (see [loop_iter](https://docs.certora.com/en/latest/docs/prover/cli/options.html#loop-iter)). Furthermore, it can add an assertion that the number of unrolled iterations was sufficient to fully capture all of the loop’s behavior, which is usually useful in loops that are known to have a constant number of iterations. Otherwise, the user can opt-in to assume the unroll bound was sufficient (see [optimistic_loop](https://docs.certora.com/en/latest/docs/prover/cli/options.html#optimistic-loop)).
This approach works well for common simple loops such as:
```
uintx;
for(uinti=0;i<3;i++){
x++;
}

```
Copy to clipboard
Note
For trivial loops such as the above, the Prover automatically infers the required number of iterations is 3, even if a lower `--loop_iter` is provided.
The natural loop condition determining whether we enter the body of the loop or exit is clearly `i < 3`, thus 3 iterations are sufficient to fully unroll the loop and render the loop condition false. If `--loop_iter 3` is defined, the Prover unrolls the loop 3 times, and evaluates the loop exit condition one more time (a total of 4 evaluations of the loop exit condition). The resulting code would behave like the following Solidity snippet:
```
uintx;
uinti=0;
if(i<3){// iteration #1
i++;
x++;
if(i<3){// iteration #2
i++;
x++;
if(i<3){// iteration #3
i++;
x++;
assert(i<3)// exit condition evaluation
// require(i < 3) if `--optimistic_loop` is set
}
}
}

```
Copy to clipboard
However, for less trivial cases, the definition is not so clear:
```
uintx;// global state variable
uinti=0;
while(true){
x++;// if x overflows, we exit the loop and revert. But is this the loop condition?
if(i>=3){
break;
}
i+=1;
}

```
Copy to clipboard
Running the builtin sanity rule for the above code with `--loop_iter` of 2 or less results in sanity violation (can find no paths reaching the end of the loop), as is expected. Sanity is passing with `--loop_iter 3`.
However, running with `--loop_iter 3` actually shows 4 loop iterations in the Call Trace output. The reason for that is that in cases the Prover cannot detect an exit condition in the loop’s head, it unrolls one extra time to evaluate a potential exit condition in the loop’s body. In our case, the bytecode representation shows that the loop’s head is ending with a non-conditional jump. The equivalent Solidity-like version of the unrolled code would look as follows (`c`-style `goto` and `label` commands were added for clarity):
```
uintx;// global state variable
uinti=0;
// iteration #1
x++;
if(i>=3){
gotoafter_original_while_loop_end;
}
i+=1;
// iteration #2
x++;
if(i>=3){
gotoafter_original_while_loop_end;
}
i+=1;
// iteration #3
x++;
if(i>=3){
gotoafter_original_while_loop_end;
}
i+=1;
// iteration #4
x++;
if(i>=3){
gotoafter_original_while_loop_end;
}
i+=1;
assert(false);// require(false) if `--optimistic_loop` is set
after_original_while_loop_end:...

```
Copy to clipboard
[ Previous](https://docs.certora.com/en/latest/docs/user-guide/out-of-resources/timeout-theory.html "Timeouts in Certora Prover - Theoretical Background") [Next ](https://docs.certora.com/en/latest/docs/user-guide/checking.html "Checking Specifications")
© Copyright 2025, Certora, Inc.
Built with [Sphinx](https://www.sphinx-doc.org/) using a [theme](https://github.com/readthedocs/sphinx_rtd_theme) provided by [Read the Docs](https://readthedocs.org). 
