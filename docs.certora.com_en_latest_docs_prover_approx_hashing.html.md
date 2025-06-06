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
        * [Introduction](https://docs.certora.com/en/latest/docs/prover/approx/hashing.html#introduction)
        * [Modeling the Keccak function (bounded case)](https://docs.certora.com/en/latest/docs/prover/approx/hashing.html#modeling-the-keccak-function-bounded-case)
        * [Hashing of unbounded data](https://docs.certora.com/en/latest/docs/prover/approx/hashing.html#hashing-of-unbounded-data)
        * [Background: The Solidity Storage Model](https://docs.certora.com/en/latest/docs/prover/approx/hashing.html#background-the-solidity-storage-model)
        * [Conclusion](https://docs.certora.com/en/latest/docs/prover/approx/hashing.html#conclusion)
      * [Quantifier Grounding](https://docs.certora.com/en/latest/docs/prover/approx/grounding.html)
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
  * Modeling of Hashing in the Certora Prover
  * [ View page source](https://docs.certora.com/en/latest/_sources/docs/prover/approx/hashing.md.txt)


# Modeling of Hashing in the Certora Prover[](https://docs.certora.com/en/latest/docs/prover/approx/hashing.html#modeling-of-hashing-in-the-certora-prover "Link to this heading")
In this document we present how the Keccak hash function is modeled in the Certora Prover and how that impacts smart contract verification.
## Introduction[](https://docs.certora.com/en/latest/docs/prover/approx/hashing.html#introduction "Link to this heading")
The Keccak hash function is used heavily by Solidity smart contracts in an implicit way. Most prominently, all unbounded data structures in storage (arrays, mappings) receive their storage addresses as values of the Keccak function. It is also possible to call the Keccak hash function explicitly, both through a solidity built in function and through inline assembly.
The Certora Prover does not operate with an actual implementation of the Keccak hash function, since this would make most verification intractable and provide no practical benefits. Instead, the Certora Prover models the properties of the Keccak hash function that are crucial for the function of the smart contracts under verification while abstracting away from implementation details of the actual hash function.
## Modeling the Keccak function (bounded case)[](https://docs.certora.com/en/latest/docs/prover/approx/hashing.html#modeling-the-keccak-function-bounded-case "Link to this heading")
The Certora Prover models the Keccak hash function as an arbitrary function that is _injective with large gaps_.
The hash function `hash` being injective with large gaps means that on distinct inputs `x` and `y`
  * the hashes `hash(x)` and `hash(y)` are also distinct, and
  * the gap between `hash(x)` and `hash(y)` is large enough that every additive term `hash(x) + i` that occurs in the program is also distinct from `hash(y)`.


Furthermore, the initial storage slots and large constants that appear in the code are reserved. I.e., we make sure that no hash value ends up colliding with slots 0 to 10000 nor with any constant that is explicitly given in the source code. (The latter constraint is necessary to avoid collisions with hashes that the solidity compiler has precompiled.)
These constraints are enough for the Solidity storage model to work as expected. However, this modeling allows the Certora Prover to pick hash functions that show different behavior from the actual Keccak function. For instance, it is unlikely that the individual numeric values or their ordering matches that of the Keccak function. We present some examples in the following subsection. We have not observed a practical use case yet where the numeric values of the hash function play a role, thus we chose this modeling for tractability reasons.
See the later subsection [Background: The Solidity Storage Model](https://docs.certora.com/en/latest/docs/prover/approx/hashing.html#background-the-solidity-storage-model) for details on why this property is an adequate model for maintaining integrity of solidity’s storage operations.
### Examples (Imprecision of Modeling)[](https://docs.certora.com/en/latest/docs/prover/approx/hashing.html#examples-imprecision-of-modeling "Link to this heading")
We illustrate the implications of our modeling decisions using a few examples.
### Modeling does not account for individual values of the Keccak function[](https://docs.certora.com/en/latest/docs/prover/approx/hashing.html#modeling-does-not-account-for-individual-values-of-the-keccak-function "Link to this heading")
The Keccak256-hash of the string `hello` is `0x1c8aff950685c2ed4bc3174f3472287b56d9517b9c948127319a09a7a36deac8`. However, due to our modeling, the Certora Prover cannot prove that fact. the rule `hashOf17Eq` will show as “violated” since the Prover can pick a function for `keccak256` that assigns `hello` differently. For the same reason the Prover also does not disprove that the hash of `17` is `0x1c8aff950685c2ed4bc3174f3472287b56d9517b9c948127319a09a7a36deac8`, since we allow it to choose `keccak256` appropriately.
```
// CVL:
methods{hash(uint)returns(uint)envfree;}
rulehashOf17Eq{
assert(hash("hello")==0x1c8aff950685c2ed4bc3174f3472287b56d9517b9c948127319a09a7a36deac8);
}
rulehashOf17Neq{
assert(hash("hello")!=0x1c8aff950685c2ed4bc3174f3472287b56d9517b9c948127319a09a7a36deac8);
}
// solidity:
contractC{
functionhash(stringx)publicreturns(bytes32){
returnkeccak256(bytes(x));
}
}

```
Copy to clipboard
### Modeling does not account for ordering[](https://docs.certora.com/en/latest/docs/prover/approx/hashing.html#modeling-does-not-account-for-ordering "Link to this heading")
Whichever distinct values we chose for `x` and `y` in the example below, on the real Keccak function, one rule would be violated and one rule would not. In the modeling of the Certora Prover, both rules are violated, since the Prover is allowed to “invent” a hash function for each rule and will choose one that violates the property whenever there is such a function (as long as that function fulfills the “injectivity with large gaps” property).
```
// CVL:
methods{hash(uint)returns(uint)envfree;}
definitionx():uint=12345678
definitiony():uint=87654321
rulehashXLowerOrEqualToHashY{
asserthash(x())<=hash(y());
}
rulehashXLargerThanHashY{
assert(hash(x())>hash(y()));
}
// solidity:
contractC{
functionhash(uintx)publicreturns(bytes32){
// we're assuming presence of some to_bytes function here; it's 
// practical implementation is not relevant here
returnkeccak256(to_bytes(x));
}
}

```
Copy to clipboard
### Constants in code vs hashes[](https://docs.certora.com/en/latest/docs/prover/approx/hashing.html#constants-in-code-vs-hashes "Link to this heading")
A special case in Certora Prover’s modeling of hashing is the treatment of constants that appear in the code: The Prover implicitly assumes that the hash function never outputs one of these constants on any of the concrete inputs it gets in that program.
For an example, consider this rule and spec:
```
// CVL:
methods {
  function readAtSlotAddress() external returns (uint) envfree;
  function updateMap(uint k, uint v) external envfree;
}
rule foo {
	uint v1 = readAtSlotAddress();
	uint preImage;
	uint x; 
	updateMap(preImage, x);
	uint v2 = readAtSlotAddress();
	assert(v1 == v2);
}
// solidity
contract C {
	uint constant slotAddress = 1000000;
	mapping(uint => uint) map;
	function updateMap(uint k, uint v) public {
		map[k] = v;
	}
	function readAtSlotAddress() public returns (uint r) {
		assembly {
			r := sload(slotAddress)
		}
	}
}

```
Copy to clipboard
The function `readAtSlotAddress` reads from storage at the slot with the number 1000000. The function `updateMap` updates a mapping; this means it updates storage at a hash computed from its identifier (here 1, since it is the second field in the contract) and the key `k`. Now, if `k` is chosen such that `keccak(1, k)` equals 1000000, the map update would overwrite that storage slot, and thus the assertion in the rule `foo` would be violated.
However, the Certora Prover will return “not violated” for this assertion, since it assumes that no hash ever collides with the constant 1000000, which occurs in the program.
On the other hand, if we change the contract to leave `slotAddress` uninitialized, then Certora Prover will return a violation, since then it can choose the values such that `keccak(2, preImage)` == `slotAddress`.
Also see this [example run](https://prover.certora.com/output/91772/e02fc5c0f57c4404b6fe28f237ecab07?anonymousKey=9e9e40a985a82d55446b0cdc2c75a7540ca696bc) for a further illustration of both cases.
Note
The reader may wonder at first whether this means that the Certora Prover computes the inverse value of the Keccak function for some image value (which would be a challenging task in and of itself). This is not the case, in practice the Prover makes up any arbitrary function that fulfills the previously described axioms and also maps that single input to an output accordingly.
## Hashing of unbounded data[](https://docs.certora.com/en/latest/docs/prover/approx/hashing.html#hashing-of-unbounded-data "Link to this heading")
In the discussion so far we only considered hashes of data whose length is already known before program execution (e.g. a `uint` variable always has 256 bits). Hashing of unbounded data (typically unbounded arrays, like `bytes`, `uint[]`, etc.) requires some extra measures, since their implementation requires loops and the Certora Prover [internally eliminates all loops](https://docs.certora.com/en/latest/docs/prover/approx/loops.html) in order to achieve better tractability.
The Certora Prover models unbounded hashing similar to how it eliminates loops. The user specifies an upper length bound up to which unbounded hashing should be modeled precisely (using the CLI option [hashing_length_bound](https://docs.certora.com/en/latest/docs/prover/cli/options.html#hashing-length-bound)) as well as whether this bound is to be assumed or to be verified (using the CLI option [optimistic_hashing](https://docs.certora.com/en/latest/docs/prover/cli/options.html#optimistic-hashing)).
We demonstrate how these flags work using the following program snippet:
```
contractC{
mapping(bytes=>uint)m;
bytesb1,b2,b3;
uintu,v,w;
// ...
requireb1.length<224;
m[b1]=u;
// ...
// no constraints on b2.length
m[b2]=v;
// ...
// no constraints on b3.length
m[b3]=v;
assert(b3.length<300,"b3 is more than 300 bytes long, unexpectedly")
// ...
}

```
Copy to clipboard
Let us assume that the `--hashing_length_bound` flag is set to 224 (which corresponds to 7 machine words).
Then, the first hash operation, triggered by the mapping access `m[b1]`, behaves like the hash of a bounded data chunk. The `--optimstic_hashing` flag has no impact on this hash operation.
The behavior of the second hash operation, triggered by the mapping access `m[b2]`, depends on whether `--optimistic_hashing` is set.
  * If the `--optimistic_hashing` flag is not set, the violation of an internal assertion will be reported by the Prover, stating that a chunk of data is being hashed that may exceed the given bound of 224. The reported message will look like this:


```
Trying to hash a non-constant length array whose length may exceed the bound 
(set in option "--hashing_length_bound", current value is 224). 
Optimistic unbounded hashing is currently deactivated (can be activated via 
option "--optimistic_hashing").

```
Copy to clipboard
  * If the `--optimistic_hashing` flag is set, the Prover will internally make an assumption (equivalent to a `require` statement) on `b2` stating that its length cannot exceed 224 bytes.


The third operation, triggered by the mapping access `m[b3]` behaves like the second, since no length constraint on `b3` is made by the program. However, we can see the impact of the `--optimistic_hashing` flag on the `assert` command that follows the hash operation: When the flag is set, the assertion will be shown as not violated even though nothing in the program itself prevents `b3` from being longer than 300 bytes. This is an example of unsoundness coming from “optimistic” assumptions. (When `--optimistic_hashing` is not set, then we get a violation from any or all assertions, depending on the configuration of the Certora Prover.)
### Examples for Unbounded Hashing[](https://docs.certora.com/en/latest/docs/prover/approx/hashing.html#examples-for-unbounded-hashing "Link to this heading")
The following collection snippet illustrates the most common use cases for hashing of data that has unbounded length.
```
contractC{
mapping(bytes=>uint)m;
uintx,y,z,start,len;
// ... 
m[b]=v
// ... 
keccak256(abi.encode(x,y,z))
// ... 
keccak256(abi.encodePacked(x,y,z))
// ...
assembly{
keccak(start,len)
}
// ...
}

```
Copy to clipboard
Probably the most common use case is the use of mappings whose keys are an unbounded array (`bytes`, `string`, `uint[]`, etc.); any access to such a mapping induces a hash of the corresponding array whose length is often unknown and unbounded.
Further use cases include direct calls of the Keccak function, either directly on Solidity or inside an inline assembly snippet.
Note that the Certora Prover’s static analysis is aware of the ABI encoder. Thus, in many cases, it can figure out that when `x, y, z` are scalars that `keccak256(abi.encode(x, y, z))` is actually a bounded hash of the form `hash(x, y, z)` as opposed to an unbounded hash of the `bytes` array that is the result of the `encode` function.
## Background: The Solidity Storage Model[](https://docs.certora.com/en/latest/docs/prover/approx/hashing.html#background-the-solidity-storage-model "Link to this heading")
In this subsection we illustrate the consequences on storage integrity if the “injectivity with large gaps” property is not maintained.
For instance consider this contract:
```
// solidity
contractC{
uinti;// slot 0
uint[]a;// slot 1
mapping(uint=>uint)m;// slot 2
/** Always returns writeToArray (unless hashing is broken). */
functionfoo(uintwriteToArray,uintwriteToMap)publicreturns(uint){
i=u;// sstore(0, u)
a[j]=writeToArray;// sstore(hash(1) + j, writeToArray)
m[k]=writeToMap;// sstore(hash(2, k), writeToMap)
returna[j];
}
}
// CVL
methods{foo(uint,uint)return(uint);};
rulestorageIntegrity{
uintwriteToArray,writeToMap;
requirewriteToArray!=writeToMap;
uintres=foo(writeToArray,writeToMap)
assert(res==writeToArray);
}

```
Copy to clipboard
The comments of the function `foo` illustrate how storage is laid out by Solidity. The occurrences of `sstore(x, y)` in the line comments above denote a storage update of storage address `x` to value `y`. The scalar `i` is stored at storage address `0`, which is derived from its slot number in the contract (slots are numbered in order of appearance in the source code). The array `a` is stored contiguously, starting from slot `hash(1)`. The entries of mapping `m` are spread out over storage; their locations are computed as the hash of the mapping’s storage slot and the key at which the mapping is being accessed; thus the storage slot used for the entry of `m` under key `k` is computed as `hash(2, k)`.
We can see that non-collision of hashes is essential for storage integrity. E.g., if `hash(1) + j` was equal to `hash(2, k)` then the operations on `a` and `m` would interfere with each other, and `foo` would return the value of `writeToMap` rather than the value of `writeToArray`.
## Conclusion[](https://docs.certora.com/en/latest/docs/prover/approx/hashing.html#conclusion "Link to this heading")
To summarize, the Certora Prover handles hashing in a way that behaves as expected for most hashes.
However, it is good to be aware of limitations of the modeling; i.e. that not all properties of the actual Keccak function are preserved but only the ones that are crucial for practical use cases, which are covered by the “injectivity with large gaps” property.
Furthermore, special attention may be necessary when hashing of unbounded data is required. For this case, Certora Prover relies on user-controlled approximations that are analogous to its handling of loops.
[ Previous](https://docs.certora.com/en/latest/docs/prover/approx/harnessing.html "Harnessing") [Next ](https://docs.certora.com/en/latest/docs/prover/approx/grounding.html "Quantifier Grounding")
© Copyright 2025, Certora, Inc.
Built with [Sphinx](https://www.sphinx-doc.org/) using a [theme](https://github.com/readthedocs/sphinx_rtd_theme) provided by [Read the Docs](https://readthedocs.org). 
