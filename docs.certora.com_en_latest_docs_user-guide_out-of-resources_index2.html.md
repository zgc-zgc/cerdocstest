<!DOCTYPE html><html class="writer-html5" lang="en" data-content_root="../../../"><head>
  <meta charset="utf-8"><meta name="viewport" content="width=device-width, initial-scale=1">

  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Managing Timeouts and Out of Memory Problems — Certora Prover Documentation 0.0 documentation</title>
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
    <link rel="next" title="Out of memory problems" href="memout.html">
    <link rel="prev" title="Working with Multiple Contracts" href="../multicontract/index.html"> 
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
<li class="toctree-l2 current" aria-expanded="true"><a class="reference internal current" href="#" aria-expanded="true"><button class="toctree-expand" title="Open/close menu"></button>Managing Timeouts and Out of Memory Problems</a><ul>
<li class="toctree-l3"><a class="reference internal" href="memout.html">Out of memory problems</a></li>
<li class="toctree-l3"><a class="reference internal" href="timeout.html">Timeouts</a></li>
<li class="toctree-l3"><a class="reference internal" href="timeout-theory.html">Timeouts in Certora Prover - Theoretical Background</a></li>
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
      <li class="breadcrumb-item active">Managing Timeouts and Out of Memory Problems</li>
      <li class="wy-breadcrumbs-aside">
            <a href="../../../_sources/docs/user-guide/out-of-resources/index.md.txt" rel="nofollow"> View page source</a>
      </li>
  </ul>
  <hr>
</div>
          <div role="main" class="document" itemscope="itemscope" itemtype="http://schema.org/Article">
           <div itemprop="articleBody">
             
  <section id="managing-timeouts-and-out-of-memory-problems">
<span id="managing-problems"></span><h1>Managing Timeouts and Out of Memory Problems<a class="headerlink" href="#managing-timeouts-and-out-of-memory-problems" title="Link to this heading"></a></h1>
<p>In this chapter, we describe how to diagnose and remedy when the Certora Prover
ran out of time or out of memory.</p>
<p>Out-of-memory problems are signified by an <code class="docutils literal notranslate"><span class="pre">Extremely</span> <span class="pre">low</span> <span class="pre">available</span> <span class="pre">memory</span></code>
message in the Global Problems tab of the Prover reports, see
<a class="reference internal" href="memout.html#memout-introduction"><span class="std std-ref">Out of memory problems</span></a> for more details. Timeouts are signified either by a
<code class="docutils literal notranslate"><span class="pre">Global</span> <span class="pre">timeout</span> <span class="pre">reached</span></code> message in the Global Problems tab, if the whole Prover
job timed out, or by an orange clock symbol next to the rule, if that
particular rule timed out, see <a class="reference internal" href="timeout.html#timeouts-introduction"><span class="std std-ref">Timeouts</span></a> for more details.</p>
<div class="toctree-wrapper compound">
<ul>
<li class="toctree-l1"><a class="reference internal" href="memout.html">Out of memory problems</a><ul>
<li class="toctree-l2"><a class="reference internal" href="memout.html#general-indicators">General indicators</a></li>
<li class="toctree-l2"><a class="reference internal" href="memout.html#reducing-memory-usage">Reducing memory usage</a><ul>
<li class="toctree-l3"><a class="reference internal" href="memout.html#high-memory-usage-of-smt-solvers">High memory usage of SMT solvers</a></li>
</ul>
</li>
</ul>
</li>
<li class="toctree-l1"><a class="reference internal" href="timeout.html">Timeouts</a><ul>
<li class="toctree-l2"><a class="reference internal" href="timeout.html#classification-of-timeouts">Classification of Timeouts</a></li>
<li class="toctree-l2"><a class="reference internal" href="timeout.html#timeout-causes">Identifying timeout causes</a><ul>
<li class="toctree-l3"><a class="reference internal" href="timeout.html#complexity-feedback-from-certora-prover">Complexity feedback from Certora Prover</a><ul>
<li class="toctree-l4"><a class="reference internal" href="timeout.html#difficulty-statistics">Difficulty statistics</a></li>
<li class="toctree-l4"><a class="reference internal" href="timeout.html#timeout-tac-reports">Timeout TAC reports</a></li>
<li class="toctree-l4"><a class="reference internal" href="timeout.html#finding-timeout-causes-through-modularization">Finding timeout causes through modularization</a><ul>
<li class="toctree-l5"><a class="reference internal" href="timeout.html#sanity-rules">Sanity rules</a></li>
<li class="toctree-l5"><a class="reference internal" href="timeout.html#library-contracts">Library contracts</a></li>
</ul>
</li>
</ul>
</li>
</ul>
</li>
<li class="toctree-l2"><a class="reference internal" href="timeout.html#timeout-prevention">Timeout prevention</a><ul>
<li class="toctree-l3"><a class="reference internal" href="timeout.html#running-rules-individually">Running rules individually</a></li>
<li class="toctree-l3"><a class="reference internal" href="timeout.html#detect-candidates-for-summarization">Detect candidates for summarization</a><ul>
<li class="toctree-l4"><a class="reference internal" href="timeout.html#example-usage">Example usage</a></li>
</ul>
</li>
<li class="toctree-l3"><a class="reference internal" href="timeout.html#dealing-with-different-kinds-of-complexity">Dealing with different kinds of complexity</a><ul>
<li class="toctree-l4"><a class="reference internal" href="timeout.html#dealing-with-a-high-path-count">Dealing with a high path count</a><ul>
<li class="toctree-l5"><a class="reference internal" href="timeout.html#path-explosion">Path explosion</a></li>
<li class="toctree-l5"><a class="reference internal" href="timeout.html#mitigation-approaches">Mitigation approaches</a></li>
</ul>
</li>
<li class="toctree-l4"><a class="reference internal" href="timeout.html#dealing-with-nonlinear-arithmetic">Dealing with nonlinear arithmetic</a></li>
<li class="toctree-l4"><a class="reference internal" href="timeout.html#dealing-with-high-memory-or-storage-complexity">Dealing with high memory (or storage) complexity</a><ul>
<li class="toctree-l5"><a class="reference internal" href="timeout.html#passing-complex-structs">Passing complex structs</a></li>
<li class="toctree-l5"><a class="reference internal" href="timeout.html#memory-and-storage-in-inline-assembly">Memory and storage in inline assembly</a></li>
</ul>
</li>
</ul>
</li>
<li class="toctree-l3"><a class="reference internal" href="timeout.html#modular-verification">Modular verification</a><ul>
<li class="toctree-l4"><a class="reference internal" href="timeout.html#library-based-systems">Library-based systems</a></li>
</ul>
</li>
<li class="toctree-l3"><a class="reference internal" href="timeout.html#command-line-options">Command line options</a><ul>
<li class="toctree-l4"><a class="reference internal" href="timeout.html#prover-args-destructiveoptimizations-enable"><code class="docutils literal notranslate"><span class="pre">--prover_args</span> <span class="pre">'-destructiveOptimizations</span> <span class="pre">enable'</span></code></a></li>
</ul>
</li>
</ul>
</li>
</ul>
</li>
<li class="toctree-l1"><a class="reference internal" href="timeout-theory.html">Timeouts in Certora Prover - Theoretical Background</a><ul>
<li class="toctree-l2"><a class="reference internal" href="timeout-theory.html#complexity-of-the-smt-problem">Complexity of the SMT problem</a></li>
<li class="toctree-l2"><a class="reference internal" href="timeout-theory.html#usefulness-of-worst-case-intractable-problems">Usefulness of worst-case intractable problems</a></li>
<li class="toctree-l2"><a class="reference internal" href="timeout-theory.html#further-reading">Further reading</a></li>
</ul>
</li>
</ul>
</div>
</section>


           </div>
          </div>
          <footer><div class="rst-footer-buttons" role="navigation" aria-label="Footer">
        <a href="../multicontract/index.html" class="btn btn-neutral float-left" title="Working with Multiple Contracts" accesskey="p" rel="prev"><span class="fa fa-arrow-circle-left" aria-hidden="true"></span> Previous</a>
        <a href="memout.html" class="btn btn-neutral float-right" title="Out of memory problems" accesskey="n" rel="next">Next <span class="fa fa-arrow-circle-right" aria-hidden="true"></span></a>
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