[ Certora Prover Documentation ![Logo](https://docs.certora.com/en/latest/_static/Certora_Logo_Black.svg) ](https://docs.certora.com/en/latest/index.html)
Contents
  * [Certora User’s Guide](https://docs.certora.com/en/latest/docs/user-guide/index.html)
  * [The Certora Verification Language](https://docs.certora.com/en/latest/docs/cvl/index.html)
    * [Specification Files](https://docs.certora.com/en/latest/docs/cvl/overview.html)
      * [Syntactic Conventions](https://docs.certora.com/en/latest/docs/cvl/overview.html#syntactic-conventions)
    * [Basic Syntax](https://docs.certora.com/en/latest/docs/cvl/basics.html)
    * [Types](https://docs.certora.com/en/latest/docs/cvl/types.html)
    * [Expressions](https://docs.certora.com/en/latest/docs/cvl/expr.html)
    * [Statements](https://docs.certora.com/en/latest/docs/cvl/statements.html)
    * [Import and Use Statements](https://docs.certora.com/en/latest/docs/cvl/imports.html)
    * [Using Statements](https://docs.certora.com/en/latest/docs/cvl/using.html)
    * [The Methods Block](https://docs.certora.com/en/latest/docs/cvl/methods.html)
    * [Rules](https://docs.certora.com/en/latest/docs/cvl/rules.html)
    * [Built-in Rules](https://docs.certora.com/en/latest/docs/cvl/builtin.html)
    * [Functions](https://docs.certora.com/en/latest/docs/cvl/functions.html)
    * [Invariants](https://docs.certora.com/en/latest/docs/cvl/invariants.html)
    * [Uninterpreted Sorts](https://docs.certora.com/en/latest/docs/cvl/sorts.html)
    * [Ghosts](https://docs.certora.com/en/latest/docs/cvl/ghosts.html)
    * [Definitions](https://docs.certora.com/en/latest/docs/cvl/defs.html)
    * [Hooks](https://docs.certora.com/en/latest/docs/cvl/hooks.html)
    * [Transient Storage](https://docs.certora.com/en/latest/docs/cvl/transient.html)
    * [Foundry Integration (Alpha)](https://docs.certora.com/en/latest/docs/cvl/foundry-integration.html)
    * [Changes Since CVL 1](https://docs.certora.com/en/latest/docs/cvl/index.html#changes-since-cvl-1)
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
  * [The Certora Verification Language](https://docs.certora.com/en/latest/docs/cvl/index.html)
  * Specification Files
  * [ View page source](https://docs.certora.com/en/latest/_sources/docs/cvl/overview.md.txt)


# Specification Files[](https://docs.certora.com/en/latest/docs/cvl/overview.html#specification-files "Link to this heading")
The Certora Prover verifies that a smart contract satisfies a set of rules written in a language called Certora Verification Language (CVL). The syntax of CVL is similar to Solidity, but CVL contains additional features that are useful for writing specifications.
A spec may contain any of the following:
  * **[Import statements](https://docs.certora.com/en/latest/docs/cvl/imports.html):** CVL files can import the contents of other CVL files.
  * **[Use statements](https://docs.certora.com/en/latest/docs/cvl/imports.html):** A `use` statement instructs the Certora Prover to check a rule that is imported from another spec or from the built-in rules.
  * **[Using statements](https://docs.certora.com/en/latest/docs/cvl/using.html):** Using statements allow a specification to reference multiple contracts.
  * **[Methods blocks](https://docs.certora.com/en/latest/docs/cvl/methods.html):** `methods` blocks contain information on how methods should be summarized by the Prover during verification.
  * **[Rules](https://docs.certora.com/en/latest/docs/cvl/rules.html#rules-main):** A rule describes the expected behavior of the methods of a contract.
  * **[Invariants](https://docs.certora.com/en/latest/docs/cvl/invariants.html#invariants):** Invariants describe facts about the state of a contract that should always be true.
  * **[Functions](https://docs.certora.com/en/latest/docs/cvl/functions.html):** CVL functions contain CVL code that can be reused throughout the spec.
  * **[Definitions](https://docs.certora.com/en/latest/docs/cvl/defs.html):** CVL definitions contain CVL expressions that can be reused throughout the spec.
  * **[Sorts](https://docs.certora.com/en/latest/docs/cvl/sorts.html):** Sorts define simple types that can be compared for equality.
  * **[Ghosts](https://docs.certora.com/en/latest/docs/cvl/ghosts.html#ghosts-doc):** Ghosts define additional variables that can be used to keep track of state changes in the contracts.
  * **[Hooks](https://docs.certora.com/en/latest/docs/cvl/hooks.html#hooks):** Hooks allow the specification to instrument the contracts being verified to insert additional CVL code when various instructions are executed.


The remainder of this chapter describes the syntax and semantics of a specification file in detail.
## Syntactic Conventions[](https://docs.certora.com/en/latest/docs/cvl/overview.html#syntactic-conventions "Link to this heading")
Many of the pages in this guide describe the syntax of parts of the Certora Verification Language using a modified version of the [EBNF format](https://en.wikipedia.org/wiki/Extended_Backus%E2%80%93Naur_form).
When reading the syntax blocks, keep the following in mind:
  * Text in double quotes is a terminal that matches the exact string. For example, `"ghost"` matches `ghost`, and `"."` matches `.`
  * Names that are not in double quotes are nonterminals that refers to other parts of the grammar. For example, `number` matches `1` or `2` or `372`.
  * Multiple items placed next to each other can be separated by whitespace. For example, `"pragma" "specify" number "." number` matches `pragma specify 1.5` and also `pragma     specify 0.3`. Note that this is different from the EBNF format described in the link above (that format would add a comma between items).
  * An item surrounded by square brackets is optional. For example, `"pragma" "specify" number [ "." number ]` matches `pragma specify 3.1` and also matches `pragma specify 3`.
  * An item surrounded by curly braces may be repeated 0 or more times. For example, `number { "." number }` matches `3` and `3.1` and `3.1.4.1.5`
  * Items separated by a vertical bar represent different alternatives. For example, `"use" "rule" id | "use" "invariant" id | "use" "builtin" "rule" id` matches `use rule foo` and also matches `use invariant bar` but does not match `use rule foo use invariant bar`.


[ Previous](https://docs.certora.com/en/latest/docs/cvl/index.html "The Certora Verification Language") [Next ](https://docs.certora.com/en/latest/docs/cvl/basics.html "Basic Syntax")
© Copyright 2025, Certora, Inc.
Built with [Sphinx](https://www.sphinx-doc.org/) using a [theme](https://github.com/readthedocs/sphinx_rtd_theme) provided by [Read the Docs](https://readthedocs.org). 
