<!DOCTYPE html><html class="writer-html5" lang="en" data-content_root="../../../"><head>
  <meta charset="utf-8"><meta name="viewport" content="width=device-width, initial-scale=1">

  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Timeouts in Certora Prover - Theoretical Background — Certora Prover Documentation 0.0 documentation</title>
      <link rel="stylesheet" type="text/css" href="../../../_static/pygments.css?v=80d5e7a1">
      <link rel="stylesheet" type="text/css" href="../../../_static/css/theme.css?v=19f00094">
      <link rel="stylesheet" type="text/css" href="../../../_static/copybutton.css?v=76b2166b">
      <link rel="stylesheet" type="text/css" href="../../../_static/custom.css?v=098d337b">
      <link rel="stylesheet" type="text/css" href="../../../_static/sphinx-design.min.css?v=87e54e7c">

  
  <!--[if lt IE 9]>
    <script src="../../../_static/js/html5shiv.min.js"></script>
  <![endif]-->
  
        <script src="../../../_static/jquery.js?v=5d32c60e"></script>
        <script src="../../../_static/_sphinx_javascript_frameworks_compat.js?v=2cd50e6c"></script>
        <script src="../../../_static/documentation_options.js?v=837179f8"></script>
        <script src="../../../_static/doctools.js?v=9a2dae69"></script>
        <script src="../../../_static/sphinx_highlight.js?v=dc90522c"></script>
        <script src="../../../_static/clipboard.min.js?v=a7894cd8"></script>
        <script src="../../../_static/copybutton.js?v=f281be69"></script>
        <script src="../../../_static/design-tabs.js?v=f930bc37"></script>
    <script src="../../../_static/js/theme.js"></script>
    <link rel="index" title="Index" href="../../../genindex.html">
    <link rel="search" title="Search" href="../../../search.html">
    <link rel="next" title="Understanding gaps between high and low level code" href="../gaps.html">
    <link rel="prev" title="Timeouts" href="timeout.html"> 
</head>

<body class="wy-body-for-nav"> 
  <div class="wy-grid-for-nav">
    <nav data-toggle="wy-nav-shift" class="wy-nav-side">
      <div class="wy-side-scroll">
        <div class="wy-side-nav-search">

          
          
          <a href="../../../index.html" class="icon icon-home">
            Certora Prover Documentation
              <img src="../../../_static/Certora_Logo_Black.svg" class="logo" alt="Logo" width="646" height="188">
          </a>
<div role="search">
  <form id="rtd-search-form" class="wy-form" action="../../../search.html" method="get">
    <input type="text" name="q" placeholder="Search docs" aria-label="Search docs">
    <input type="hidden" name="check_keywords" value="yes">
    <input type="hidden" name="area" value="default">
  </form>
</div>
        </div><div class="wy-menu wy-menu-vertical" data-spy="affix" role="navigation" aria-label="Navigation menu">
              <p class="caption" role="heading"><span class="caption-text">Contents</span></p>
<ul class="current" aria-expanded="true">
<li class="toctree-l1 current" aria-expanded="true"><a class="reference internal" href="../index.html"><button class="toctree-expand" title="Open/close menu"></button>Certora User’s Guide</a><ul class="" aria-expanded="false">
<li class="toctree-l2"><a class="reference internal" href="../install.html">Installation</a></li>
<li class="toctree-l2"><a class="reference internal" href="../install_evm_compiler.html">Installing an EVM compiler and VS Code Extension</a></li>
<li class="toctree-l2"><a class="reference internal" href="../tutorials.html">Tutorial and Workshops</a></li>
<li class="toctree-l2"><a class="reference internal" href="../running.html">Running the Certora Prover</a></li>
<li class="toctree-l2"><a class="reference internal" href="../properties/index.html">Designing Good Specifications</a></li>
<li class="toctree-l2"><a class="reference internal" href="../satisfy.html">Producing Positive Examples</a></li>
<li class="toctree-l2"><a class="reference internal" href="../invariants.html">Invariants</a></li>
<li class="toctree-l2"><a class="reference internal" href="../parametric.html">Parametric rules</a></li>
<li class="toctree-l2"><a class="reference internal" href="../ghosts.html">Tracking changes with ghosts and hooks</a></li>
<li class="toctree-l2"><a class="reference internal" href="../patterns/index.html">Specification Design Patterns</a></li>
<li class="toctree-l2"><a class="reference internal" href="../opcodes.html">Using Opcode Hooks</a></li>
<li class="toctree-l2"><a class="reference internal" href="../multicontract/index.html">Working with Multiple Contracts</a></li>
<li class="toctree-l2 current" aria-expanded="true"><a class="reference internal" href="index.html"><button class="toctree-expand" title="Open/close menu"></button>Managing Timeouts and Out of Memory Problems</a><ul class="" aria-expanded="false">
<li class="toctree-l3"><a class="reference internal" href="memout.html">Out of memory problems</a></li>
<li class="toctree-l3"><a class="reference internal" href="timeout.html">Timeouts</a></li>
<li class="toctree-l3 current" aria-expanded="true"><a class="reference internal current" href="#" aria-expanded="true"><button class="toctree-expand" title="Open/close menu"></button>Timeouts in Certora Prover - Theoretical Background</a><ul>
<li class="toctree-l4"><a class="reference internal" href="#complexity-of-the-smt-problem">Complexity of the SMT problem</a></li>
<li class="toctree-l4"><a class="reference internal" href="#usefulness-of-worst-case-intractable-problems">Usefulness of worst-case intractable problems</a></li>
<li class="toctree-l4"><a class="reference internal" href="#further-reading">Further reading</a></li>
</ul>
</li>
</ul>
</li>
<li class="toctree-l2"><a class="reference internal" href="../gaps.html">Understanding gaps between high and low level code</a></li>
<li class="toctree-l2"><a class="reference internal" href="../checking.html">Checking Specifications</a></li>
<li class="toctree-l2"><a class="reference internal" href="../ci.html">CI Configuration</a></li>
<li class="toctree-l2"><a class="reference internal" href="../github_highlighting.html">Syntax Highlighting on GitHub</a></li>
<li class="toctree-l2"><a class="reference internal" href="../glossary.html">Glossary</a></li>
</ul>
</li>
<li class="toctree-l1"><a class="reference internal" href="../../cvl/index.html">The Certora Verification Language</a></li>
<li class="toctree-l1"><a class="reference internal" href="../../prover/index.html">The Certora Prover</a></li>
<li class="toctree-l1"><a class="reference internal" href="../../sunbeam/index.html">Sunbeam: Verification for Soroban</a></li>
<li class="toctree-l1"><a class="reference internal" href="../../solana/index.html">The Certora Solana Prover</a></li>
<li class="toctree-l1"><a class="reference internal" href="../../gambit/index.html">Gambit: Mutation Generator for Solidity</a></li>
</ul>
<p class="caption" role="heading"><span class="caption-text">Additional information</span></p>
<ul>
<li class="toctree-l1"><a class="reference internal" href="../../equiv-check/index.html">The Certora Equivalence Checker</a></li>
<li class="toctree-l1"><a class="reference internal" href="../../whitepaper/index.html">Certora Technology White Paper</a></li>
</ul>
<ul>
<li class="toctree-l1"><a class="reference internal" href="../../../genindex.html">Index</a></li>
</ul>

        </div>
      </div>
    </nav>

    <section data-toggle="wy-nav-shift" class="wy-nav-content-wrap"><nav class="wy-nav-top" aria-label="Mobile navigation menu">
          <i data-toggle="wy-nav-top" class="fa fa-bars"></i>
          <a href="../../../index.html">Certora Prover Documentation</a>
      </nav>

      <div class="wy-nav-content">
        <div class="rst-content">
          <div role="navigation" aria-label="Page navigation">
  <ul class="wy-breadcrumbs">
      <li><a href="../../../index.html" class="icon icon-home" aria-label="Home"></a></li>
          <li class="breadcrumb-item"><a href="../index.html">Certora User’s Guide</a></li>
          <li class="breadcrumb-item"><a href="index.html">Managing Timeouts and Out of Memory Problems</a></li>
      <li class="breadcrumb-item active">Timeouts in Certora Prover - Theoretical Background</li>
      <li class="wy-breadcrumbs-aside">
            <a href="../../../_sources/docs/user-guide/out-of-resources/timeout-theory.md.txt" rel="nofollow"> View page source</a>
      </li>
  </ul>
  <hr>
</div>
          <div role="main" class="document" itemscope="itemscope" itemtype="http://schema.org/Article">
           <div itemprop="articleBody">
             
  <section id="timeouts-in-certora-prover-theoretical-background">
<span id="timeouts-background"></span><h1>Timeouts in Certora Prover - Theoretical Background<a class="headerlink" href="#timeouts-in-certora-prover-theoretical-background" title="Link to this heading"></a></h1>
<p>This section will discuss some theoretical background of timeouts in the
Certora Prover. We try to answer questions like “Why do you build a tool that
times out?” and “Will there be an automatic program verifier that never times
out?”. For more practical advice on timeout prevention, please consult the other
parts of our documentation on <a class="reference internal" href="index.html"><span class="std std-doc">managing timeouts</span></a>.</p>
<section id="complexity-of-the-smt-problem">
<h2>Complexity of the SMT problem<a class="headerlink" href="#complexity-of-the-smt-problem" title="Link to this heading"></a></h2>
<p>As the <a class="reference internal" href="../../whitepaper/index.html#white-paper"><span class="std std-ref">white paper</span></a> describes, the Certora Prover is
roughly similar in architecture to a compiler. However, instead of executables,
the Certora Prover outputs <a class="reference internal" href="../glossary.html#term-SMT"><span class="xref std std-term">SMT</span></a> formulas. These formulas are then sent to an
SMT solver, and the result is translated back to a counterexample call trace or
a “Not Violated” result.</p>
<p>All SMT solvers share a general architecture. At the center of an SMT solver,
there is a SAT solver. The SAT solver operates on a Boolean abstraction of the
input formula, and communicates with theory solvers to refine the abstraction
according to the theories used by the formula. The problem of solving
propositional formulas (aka SAT) is famously NP-complete. In practice, this means
that there are classes of propositional formulas for which all known SAT solvers
show exponential run-time behavior. Exponential running time is usually equated
with intractability (“we have an algorithm, but it’s impractical because it runs
too long”). Most of the theories involved are at least NP-complete, already in
their conjunctive fragments (which SMT theory solvers use). In fact, with the
addition of nonlinear integer arithmetic, the SMT problem is undecidable, meaning
that there is no algorithm that can correctly solve all possible formulas.</p>
</section>
<section id="usefulness-of-worst-case-intractable-problems">
<h2>Usefulness of worst-case intractable problems<a class="headerlink" href="#usefulness-of-worst-case-intractable-problems" title="Link to this heading"></a></h2>
<p>When seeing the complexity results of the previous section, it is easy to give
up on the problems of SAT and SMT. Indeed, there were long periods in computer
science history when SAT was considered unsolvable. However, it is important to
understand that these complexity results describe the worst case behavior. It
turns out that there is a large class of formulas where SAT is tractable, even
on inputs with millions of variables, and SAT solvers have been used with great
success in industries like chip design for decades now.</p>
<p>This means that timeouts can happen when using Certora Prover,
but there are often slight variations on the input that do not
impact the property being proven and make the problem tractable.
This practice is likely to
require experience, which we collect in the <a class="reference internal" href="timeout.html#timeout-prevention"><span class="std std-ref">Timeout prevention</span></a> section.</p>
<p>We can use the parts of an SMT solver that we discussed before for some
intuition on different kinds of complexity explosions.</p>
<div class="wy-table-responsive"><table class="docutils align-default">
<thead>
<tr class="row-odd"><th class="head"><p>Difficulty</p></th>
<th class="head"><p>Solver parts</p></th>
</tr>
</thead>
<tbody>
<tr class="row-even"><td><p>Path count</p></td>
<td><p>SAT</p></td>
</tr>
<tr class="row-odd"><td><p>Storage/memory</p></td>
<td><p>SAT</p></td>
</tr>
<tr class="row-even"><td><p>Arithmetic</p></td>
<td><p>LIA / NIA</p></td>
</tr>
</tbody>
</table></div>
<p>Since control flow is encoded into Boolean logic by the Certora Prover, it
weighs most heavily on the SAT-solving part of the SMT solver. Storage or Memory
accesses lead to case splits, which are also Boolean in nature. On the other
hand, arithmetic is resolved by specialized solvers; different algorithms are
required for the linear and the nonlinear cases.</p>
</section>
<section id="further-reading">
<h2>Further reading<a class="headerlink" href="#further-reading" title="Link to this heading"></a></h2>
<p>There is a large body of literature on the topics of logic, complexity, and SMT.
Here are some links as an entry point for further reading:</p>
<p>The Wikipedia articles on
<a class="reference external" href="https://en.wikipedia.org/wiki/Satisfiability_modulo_theories">SMT</a> and the
more basic problem known as
<a class="reference external" href="https://en.wikipedia.org/wiki/Boolean_satisfiability_problem">SAT</a> give an
overview of the fundamentals of these problems and the existing solving
algorithms.</p>
<p><a class="reference external" href="https://theory.stanford.edu/~nikolaj/programmingz3.html">Programming Z3</a>
provides a guide to the z3 SMT solver and a good overview of its architecture
and components, including some algorithms and further references.</p>
</section>
</section>


           </div>
          </div>
          <footer><div class="rst-footer-buttons" role="navigation" aria-label="Footer">
        <a href="timeout.html" class="btn btn-neutral float-left" title="Timeouts" accesskey="p" rel="prev"><span class="fa fa-arrow-circle-left" aria-hidden="true"></span> Previous</a>
        <a href="../gaps.html" class="btn btn-neutral float-right" title="Understanding gaps between high and low level code" accesskey="n" rel="next">Next <span class="fa fa-arrow-circle-right" aria-hidden="true"></span></a>
    </div>

  <hr>

  <div role="contentinfo">
    <p>© Copyright 2025, Certora, Inc.</p>
  </div>

  Built with <a href="https://www.sphinx-doc.org/">Sphinx</a> using a
    <a href="https://github.com/readthedocs/sphinx_rtd_theme">theme</a>
    provided by <a href="https://readthedocs.org">Read the Docs</a>.
   

</footer>
        </div>
      </div>
    </section>
  </div>
  <script>
      jQuery(function () {
          SphinxRtdTheme.Navigation.enable(true);
      });
  </script> 


</body></html>