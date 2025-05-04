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
      * [Tracking Sums](https://docs.certora.com/en/latest/docs/user-guide/patterns/sums.html)
      * [Partially Parametric Rules](https://docs.certora.com/en/latest/docs/user-guide/patterns/partial-apply.html)
      * [Listing Safe Assumptions](https://docs.certora.com/en/latest/docs/user-guide/patterns/safe-assum.html)
        * [Context:](https://docs.certora.com/en/latest/docs/user-guide/patterns/safe-assum.html#context)
        * [Importance of Listing Safe Assumptions:](https://docs.certora.com/en/latest/docs/user-guide/patterns/safe-assum.html#importance-of-listing-safe-assumptions)
      * [Require Invariants: Proving inter-dependent invariants](https://docs.certora.com/en/latest/docs/user-guide/patterns/require-invariants.html)
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
  * [Specification Design Patterns](https://docs.certora.com/en/latest/docs/user-guide/patterns/index.html)
  * Listing Safe Assumptions
  * [ View page source](https://docs.certora.com/en/latest/_sources/docs/user-guide/patterns/safe-assum.md.txt)


# Listing Safe Assumptions[](https://docs.certora.com/en/latest/docs/user-guide/patterns/safe-assum.html#listing-safe-assumptions "Link to this heading")
The “Listing Safe Assumptions” design pattern introduces a structured approach to document and validate essential assumptions. Let’s delve into the importance of this design pattern using the provided example.
```
methods{
functionisSigned(address_addr,bytes32msgHash,uint8v,bytes32r,bytes32s)externalreturns(bool)envfree;
functionexecuteMyFunctionFromSignature(uint8v,bytes32r,bytes32s,addressowner,uint256myParam,uint256deadline)external;
functiongetHash(addressowner,uint256myParam,uint256deadline)externalreturns(bytes32)envfree;
}
/*** # ecrecover properties:
# 1. zero value:
    ecrecover(0, v, r, s) == 0
# 2. deterministic 
    ecrecover(msgHash, v, r, s) == _addr on different calls. 
# 3. uniqueness of signature
    ecrecover(msgHash, v, r, s) != 0 => ecrecover(msgHash', v, r, s) == 0
    where msgHash' != msgHash
# 4. Dependency on r and s
    ecrecover(msgHash, v, r, s) != 0 => ecrecover(msgHash, v, r', s) == 0
    where r' != r
    ecrecover(msgHash, v, r, s) != 0 => ecrecover(msgHash, v, r, s') == 0
    where s' != s
**/
functionecrecoverAxioms(){
// zero value:
require(foralluint8v.forallbytes32r.forallbytes32s.ecrecover(to_bytes32(0),v,r,s)==0);
// uniqueness of signature
require(foralluint8v.forallbytes32r.forallbytes32s.forallbytes32h1.forallbytes32h2.
h1!=h2=>ecrecover(h1,v,r,s)!=0=>ecrecover(h2,v,r,s)==0);
// dependency on r and s
require(forallbytes32h.foralluint8v.forallbytes32s.forallbytes32r1.forallbytes32r2.
r1!=r2=>ecrecover(h,v,r1,s)!=0=>ecrecover(h,v,r2,s)==0);
require(forallbytes32h.foralluint8v.forallbytes32r.forallbytes32s1.forallbytes32s2.
s1!=s2=>ecrecover(h,v,r,s1)!=0=>ecrecover(h,v,r,s2)==0);
}
ruleownerSignatureIsUnique(){
ecrecoverAxioms();
bytes32msgHashA;bytes32msgHashB;
uint8v;bytes32r;bytes32s;
addressaddr;
requiremsgHashA!=msgHashB;
requireaddr!=0;
assertisSigned(addr,msgHashA,v,r,s)=>!isSigned(addr,msgHashB,v,r,s);
}
invariantzero_message(uint8v,bytes32r,bytes32s)
ecrecover(to_bytes32(0),v,r,s)==0;
{
preserved{
ecrecoverAxioms();
}
}

```
Copy to clipboard
## Context:[](https://docs.certora.com/en/latest/docs/user-guide/patterns/safe-assum.html#context "Link to this heading")
In the example, we focus on the `ecrecover` function used for signature verification. The objective is to articulate and validate key assumptions associated with this function to bolster the security of smart contracts.
## Importance of Listing Safe Assumptions:[](https://docs.certora.com/en/latest/docs/user-guide/patterns/safe-assum.html#importance-of-listing-safe-assumptions "Link to this heading")
  1. **Clarity and Documentation:**
     * The design pattern begins by explicitly listing assumptions related to the `ecrecover` function. This serves as clear documentation for developers, auditors, and anyone reviewing the spec. Clarity in assumptions enhances the understanding of expected behavior.
  2. **Preventing Unexpected Behavior:**
     * The axioms established in the example, such as the zero message axiom and uniqueness of signature axiom, act as preventive measures against unexpected behavior. They set clear expectations for how the `ecrecover` function should behave under different circumstances, neglect all the counter-examples that are not relevant to the function intended behavior.
  3. **Easy To Use:**
     * By encapsulating assumptions within the CVL function, this design pattern allow us to easily use those assumptions in any rule or invariant we desire.


In conclusion, the “Listing Safe Assumptions” design pattern, exemplified through the `ecrecover` function in the provided example, serves a broader purpose in specs writing. It systematically documents assumptions, prevents unexpected behaviors, and offers ease of use throughout the rules and invariants.
[ Previous](https://docs.certora.com/en/latest/docs/user-guide/patterns/partial-apply.html "Partially Parametric Rules") [Next ](https://docs.certora.com/en/latest/docs/user-guide/patterns/require-invariants.html "Require Invariants: Proving inter-dependent invariants")
© Copyright 2025, Certora, Inc.
Built with [Sphinx](https://www.sphinx-doc.org/) using a [theme](https://github.com/readthedocs/sphinx_rtd_theme) provided by [Read the Docs](https://readthedocs.org). 
