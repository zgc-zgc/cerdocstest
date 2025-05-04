[ Certora Prover Documentation ![Logo](https://docs.certora.com/en/latest/_static/Certora_Logo_Black.svg) ](https://docs.certora.com/en/latest/index.html)
Contents
  * [Certora User’s Guide](https://docs.certora.com/en/latest/docs/user-guide/index.html)
    * [Installation](https://docs.certora.com/en/latest/docs/user-guide/install.html)
    * [Installing an EVM compiler and VS Code Extension](https://docs.certora.com/en/latest/docs/user-guide/install_evm_compiler.html)
    * [Tutorial and Workshops](https://docs.certora.com/en/latest/docs/user-guide/tutorials.html)
      * [Tutorial](https://docs.certora.com/en/latest/docs/user-guide/tutorials.html#tutorial)
      * [Examples](https://docs.certora.com/en/latest/docs/user-guide/tutorials.html#examples)
      * [Stanford DeFi Security Summit](https://docs.certora.com/en/latest/docs/user-guide/tutorials.html#stanford-defi-security-summit)
      * [EthCC Paris](https://docs.certora.com/en/latest/docs/user-guide/tutorials.html#ethcc-paris)
      * [Aave Community Day](https://docs.certora.com/en/latest/docs/user-guide/tutorials.html#aave-community-day)
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
  * Tutorial and Workshops
  * [ View page source](https://docs.certora.com/en/latest/_sources/docs/user-guide/tutorials.md.txt)


# Tutorial and Workshops[](https://docs.certora.com/en/latest/docs/user-guide/tutorials.html#tutorial-and-workshops "Link to this heading")
## Tutorial[](https://docs.certora.com/en/latest/docs/user-guide/tutorials.html#tutorial "Link to this heading")
The Certora Tutorial is a series of guided lessons that covers installation and basic usage of the Certora Prover.
It is available [here](https://docs.certora.com/projects/tutorials).
The Tutorial is organized as a series of lessons and exercises. You are encouraged to clone the [git repository](https://github.com/Certora/tutorials-code) and work through the exercises yourself.
## Examples[](https://docs.certora.com/en/latest/docs/user-guide/tutorials.html#examples "Link to this heading")
A set of examples featuring CVL are available on [github](https://github.com/Certora/Examples).
## Stanford DeFi Security Summit[](https://docs.certora.com/en/latest/docs/user-guide/tutorials.html#stanford-defi-security-summit "Link to this heading")
[The Stanford DeFi Security Summit, August 2022](https://www.youtube.com/playlist?list=PLKtu7wuOMP9Wp_O8kylKbtFYgM8HVTGIA) is a recorded 2-day workshop that covers basic Prover usage with several hands-on examples. It covers the following topics:
Video | Slides  
---|---  
[Overview ](https://youtu.be/1bbI-i2Y0BA) |   
[Installation and setup ](https://youtu.be/siEDkMNbl5o) | ([`slides`](https://docs.certora.com/en/latest/_downloads/5b01f3549271d3828006c2a611e29c4e/02-setup.pdf))  
[Writing basic rules ](https://youtu.be/siEDkMNbl5o?t=1076) | ([`slides`](https://docs.certora.com/en/latest/_downloads/268bf797ccddc7df3b4a7393e150cee3/03-rules.pdf))  
[Writing parametric rules ](https://youtu.be/siEDkMNbl5o?t=2840) | ([`slides`](https://docs.certora.com/en/latest/_downloads/0b224e7bf801b01ec6405fd16e85b86e/04-parametric.pdf))  
[Invariants ](https://youtu.be/gkK3KeD7AQw) | ([`slides`](https://docs.certora.com/en/latest/_downloads/dfde1c098cbf5480a6c7c3b4c7c254bd/05-invariants.pdf))  
Ghosts and hooks ([part 1](https://youtu.be/gkK3KeD7AQw?t=2993), [part 2](https://youtu.be/fHHVoRNocdE)) | ([`slides`](https://docs.certora.com/en/latest/_downloads/5c9e390835b183a0f181aa9f4345b353/06-ghosts.pdf))  
[Hyperproperties ](https://youtu.be/DcbBSab3s3E?t=80) | ([`slides`](https://docs.certora.com/en/latest/_downloads/b03ef9216c924c7d43ace2cbfb9c5d44/07-hyperproperties.pdf))  
[Designing specifications ](https://youtu.be/DcbBSab3s3E?t=374) | ([`slides`](https://docs.certora.com/en/latest/_downloads/261821f49e09d1527573ae9858995527/08-design.pdf))  
[The Certora Prover pipeline](https://youtu.be/vg6da3A7lSs) | ([`slides`](https://docs.certora.com/en/latest/_downloads/7ef350bb9818a0b10467fa47e9e22877/09-pipeline.pdf))  
[SMT solvers ](https://youtu.be/9QuS_8cL91w) | ([`slides`](https://docs.certora.com/en/latest/_downloads/c76664d62417cfcd2e962a8ab82f8d0f/10-smt.pdf))  
The covered examples are available in the [CVL examples repository](https://github.com/Certora/Examples).
## EthCC Paris[](https://docs.certora.com/en/latest/docs/user-guide/tutorials.html#ethcc-paris "Link to this heading")
[EthCC Paris, July 2022](https://www.youtube.com/playlist?list=PLKtu7wuOMP9XHbjAevkw2nL29YMubqEFj) is an earlier 3-day workshop in a similar style that covers the same material and a few additional topics:
Video | Notes  
---|---  
[Overview ](https://www.youtube.com/watch?v=sdEfc-58CUE&amp;list=PLKtu7wuOMP9XHbjAevkw2nL29YMubqEFj&amp;index=1&amp;t=1s) |   
[Installation and setup ](https://www.youtube.com/watch?v=CwCX0TuDfTE&amp;list=PLKtu7wuOMP9XHbjAevkw2nL29YMubqEFj&amp;index=2&amp;t=2s) |   
[Writing basic rules ](https://www.youtube.com/watch?v=66Gjzgl87L8&amp;list=PLKtu7wuOMP9XHbjAevkw2nL29YMubqEFj&amp;index=3&amp;t=21s) |   
[Writing parametric rules ](https://www.youtube.com/watch?v=gMjELxgMY30&amp;list=PLKtu7wuOMP9XHbjAevkw2nL29YMubqEFj&amp;index=4&amp;t=534s) |   
[Invariants ](https://www.youtube.com/watch?v=VqboepMVbg4&amp;list=PLKtu7wuOMP9XHbjAevkw2nL29YMubqEFj&amp;index=5&amp;t=2s) |   
[Multicontract verification ](https://www.youtube.com/watch?v=WR8eAQZzd8Y&amp;list=PLKtu7wuOMP9XHbjAevkw2nL29YMubqEFj&amp;index=6) | Not covered in Stanford workshop  
[The Certora Prover pipeline ](https://www.youtube.com/watch?v=jAiBUebBs88&amp;list=PLKtu7wuOMP9XHbjAevkw2nL29YMubqEFj&amp;index=7) |   
[Designing specifications ](https://www.youtube.com/watch?v=f3K-68k7vig&amp;list=PLKtu7wuOMP9XHbjAevkw2nL29YMubqEFj&amp;index=8) |   
[Liquidity pool example ](https://www.youtube.com/watch?v=GLGXQSaE5b4&amp;list=PLKtu7wuOMP9XHbjAevkw2nL29YMubqEFj&amp;index=9) | Not covered in Stanford workshop  
[Checking the spec ](https://www.youtube.com/watch?v=csTe6ub3Jwg&amp;list=PLKtu7wuOMP9XHbjAevkw2nL29YMubqEFj&amp;index=10) | Not covered in Stanford workshop  
[Ghosts and hooks ](https://www.youtube.com/watch?v=NQ1ZQnlYFOQ&amp;list=PLKtu7wuOMP9XHbjAevkw2nL29YMubqEFj&amp;index=11) |   
The last day of the workshop was devoted to an extended exercise verifying the version 3 of the Aave Token:
Video  
---  
[Aave token overview ](https://www.youtube.com/watch?v=BGdHsvQMmy8&amp;list=PLKtu7wuOMP9XHbjAevkw2nL29YMubqEFj&amp;index=12&amp;t=1618s)  
[Aave token properties ](https://www.youtube.com/watch?v=_YW-uReng44&amp;list=PLKtu7wuOMP9XHbjAevkw2nL29YMubqEFj&amp;index=13&amp;t=25s)  
[Aave token setup ](https://www.youtube.com/watch?v=Epe90JSmNqc&amp;list=PLKtu7wuOMP9XHbjAevkw2nL29YMubqEFj&amp;index=14)  
[Aave token exercise ](https://www.youtube.com/watch?v=IPasjUOFUdA&amp;list=PLKtu7wuOMP9XHbjAevkw2nL29YMubqEFj&amp;index=15)  
## Aave Community Day[](https://docs.certora.com/en/latest/docs/user-guide/tutorials.html#aave-community-day "Link to this heading")
[Aave Community Day, April 2022](https://www.youtube.com/playlist?list=PLKtu7wuOMP9WOLJNPafbrd0lehfc7yxso) is a condensed 3-hour workshop with fewer exercises.
[ Previous](https://docs.certora.com/en/latest/docs/user-guide/install_evm_compiler.html "Installing an EVM compiler and VS Code Extension") [Next ](https://docs.certora.com/en/latest/docs/user-guide/running.html "Running the Certora Prover")
© Copyright 2025, Certora, Inc.
Built with [Sphinx](https://www.sphinx-doc.org/) using a [theme](https://github.com/readthedocs/sphinx_rtd_theme) provided by [Read the Docs](https://readthedocs.org). 
