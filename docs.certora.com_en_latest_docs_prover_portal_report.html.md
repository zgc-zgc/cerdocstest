[ Certora Prover Documentation ![Logo](https://docs.certora.com/en/latest/_static/Certora_Logo_Black.svg) ](https://docs.certora.com/en/latest/index.html)
Contents
  * [Certora User’s Guide](https://docs.certora.com/en/latest/docs/user-guide/index.html)
  * [The Certora Verification Language](https://docs.certora.com/en/latest/docs/cvl/index.html)
  * [The Certora Prover](https://docs.certora.com/en/latest/docs/prover/index.html)
    * [Introduction](https://docs.certora.com/en/latest/docs/prover/intro.html)
    * [Installation](https://docs.certora.com/en/latest/docs/user-guide/install.html)
    * [Prover Approximations](https://docs.certora.com/en/latest/docs/prover/approx/index.html)
    * [Techniques Used by the Certora Prover](https://docs.certora.com/en/latest/docs/prover/techniques/index.html)
    * [Diagnostic Tools](https://docs.certora.com/en/latest/docs/prover/diagnosis/index.html)
    * [Checking Specifications](https://docs.certora.com/en/latest/docs/prover/checking/index.html)
    * [Certora Prover CLI](https://docs.certora.com/en/latest/docs/prover/cli/index.html)
    * [Using the Certora Portal](https://docs.certora.com/en/latest/docs/prover/portal/using.html)
      * [Certora Verification Reports](https://docs.certora.com/en/latest/docs/prover/portal/report.html)
        * [Storage in Call Trace](https://docs.certora.com/en/latest/docs/prover/portal/storage-in-calltrace.html)
        * [Understanding counter-examples](https://docs.certora.com/en/latest/docs/prover/portal/report.html#understanding-counter-examples)
      * [Special Portal URLs](https://docs.certora.com/en/latest/docs/prover/portal/secrets.html)
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
  * [Using the Certora Portal](https://docs.certora.com/en/latest/docs/prover/portal/using.html)
  * Certora Verification Reports
  * [ View page source](https://docs.certora.com/en/latest/_sources/docs/prover/portal/report.md.txt)


# Certora Verification Reports[](https://docs.certora.com/en/latest/docs/prover/portal/report.html#certora-verification-reports "Link to this heading")
  * [Storage in Call Trace](https://docs.certora.com/en/latest/docs/prover/portal/storage-in-calltrace.html)
    * [Introduction](https://docs.certora.com/en/latest/docs/prover/portal/storage-in-calltrace.html#introduction)
      * [Example Storage Data](https://docs.certora.com/en/latest/docs/prover/portal/storage-in-calltrace.html#example-storage-data)
    * [How Can the Storage Change?](https://docs.certora.com/en/latest/docs/prover/portal/storage-in-calltrace.html#how-can-the-storage-change)
    * [When Do We Show the Storage State?](https://docs.certora.com/en/latest/docs/prover/portal/storage-in-calltrace.html#when-do-we-show-the-storage-state)
    * [What Do We Show?](https://docs.certora.com/en/latest/docs/prover/portal/storage-in-calltrace.html#what-do-we-show)
    * [Computational Types](https://docs.certora.com/en/latest/docs/prover/portal/storage-in-calltrace.html#computational-types)
    * [Limitations of the Current “Computational Type” Resolution](https://docs.certora.com/en/latest/docs/prover/portal/storage-in-calltrace.html#limitations-of-the-current-computational-type-resolution)
    * [Reverts](https://docs.certora.com/en/latest/docs/prover/portal/storage-in-calltrace.html#reverts)
    * [Havocs](https://docs.certora.com/en/latest/docs/prover/portal/storage-in-calltrace.html#havocs)
    * [Call Resolution](https://docs.certora.com/en/latest/docs/prover/portal/storage-in-calltrace.html#call-resolution)


## Understanding counter-examples[](https://docs.certora.com/en/latest/docs/prover/portal/report.html#understanding-counter-examples "Link to this heading")
There could be many reasons for false counterexamples, but here are a few common ones.
A counterexample that looks fishy does not rule out a potential bug that the rule can uncover.
  1. **External call havocs.** Look for warnings in the Call Resolution table - this could indicate  _havocs_. Havocs are a common cause of counterexamples that seem to come out of nowhere!
  2. **Links are not applied as expected.** Note that if you use `--link` to link, you may sometimes need to require that the field is equal to the linked-to contract’s address within the rule itself. (Dispatcher links do not have this issue.)
  3. **Bitwise operations.** By default, the tool will overapproximate bitwise operations applied in a non-standard way (xor, or, and non 2^n-1 masks for and). Try to look over the dump and look for red-background lines. You may be able to solve these by passing the `--precise_bitwise_ops` option on the command line
  4. **Aliasing.** Be on the lookout if your environment’s `msg.sender` is the same as `currentContract` or any linked contract. The tool should report these more clearly but read the call trace carefully. Also, note trivial assignments like 0.
  5. **Correct storage modeling.** Suppose you have a rule that calls some getter, then you call a function that’s expected to affect the results of that getter, but in the counterexample it stays the same. It could be that the code invoked is not reaching the expected write to the relevant storage slot, or it computed the slot’s address differently. The deepest level in the call trace for stores and loads will show the actual number used for the slot’s address, so you can find-in-page the slot number from the getter and see if you find any match for it inside the function.


[ Previous](https://docs.certora.com/en/latest/docs/prover/portal/using.html "Using the Certora Portal") [Next ](https://docs.certora.com/en/latest/docs/prover/portal/storage-in-calltrace.html "Storage in Call Trace")
© Copyright 2025, Certora, Inc.
Built with [Sphinx](https://www.sphinx-doc.org/) using a [theme](https://github.com/readthedocs/sphinx_rtd_theme) provided by [Read the Docs](https://readthedocs.org). 
