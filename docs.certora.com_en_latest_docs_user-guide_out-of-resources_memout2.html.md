<!DOCTYPE html><html class="writer-html5" lang="en" data-content_root="../../../"><head>
  <meta charset="utf-8"><meta name="viewport" content="width=device-width, initial-scale=1">

  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Out of memory problems — Certora Prover Documentation 0.0 documentation</title>
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
    <link rel="next" title="Timeouts" href="timeout.html">
    <link rel="prev" title="Managing Timeouts and Out of Memory Problems" href="index.html"> 
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
<li class="toctree-l3 current" aria-expanded="true"><a class="reference internal current" href="#" aria-expanded="true"><button class="toctree-expand" title="Open/close menu"></button>Out of memory problems</a><ul>
<li class="toctree-l4"><a class="reference internal" href="#general-indicators">General indicators</a></li>
<li class="toctree-l4"><a class="reference internal" href="#reducing-memory-usage">Reducing memory usage</a></li>
</ul>
</li>
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
          <li class="breadcrumb-item"><a href="index.html">Managing Timeouts and Out of Memory Problems</a></li>
      <li class="breadcrumb-item active">Out of memory problems</li>
      <li class="wy-breadcrumbs-aside">
            <a href="../../../_sources/docs/user-guide/out-of-resources/memout.md.txt" rel="nofollow"> View page source</a>
      </li>
  </ul>
  <hr>
</div>
          <div role="main" class="document" itemscope="itemscope" itemtype="http://schema.org/Article">
           <div itemprop="articleBody">
             
  <section id="out-of-memory-problems">
<span id="memout-introduction"></span><h1>Out of memory problems<a class="headerlink" href="#out-of-memory-problems" title="Link to this heading"></a></h1>
<p>In this section, we show how to diagnose and remedy out-of-memory problems.
Since the remediation of these problems is often similar to that of certain
kinds of  timeouts, this section is kept short and links to the corresponding
places in the documentation on timeout prevention.</p>
<section id="general-indicators">
<span id="memout-indicators"></span><h2>General indicators<a class="headerlink" href="#general-indicators" title="Link to this heading"></a></h2>
<p>When the free memory drops below a certain threshold, the Prover issues the
following warning to the “General Problems” panel: <code class="docutils literal notranslate"><span class="pre">Extremely</span> <span class="pre">low</span> <span class="pre">available</span> <span class="pre">memory</span></code>.</p>
<p>This warning might occasionally not be conclusive: the JVM is sometimes able
to clean up enough memory on-demand to avert any crashes, or the memory might be
just enough. It might also not show up although the job fails due to
insufficient memory, e.g., if a single allocation that is greater than the
warning threshold fails. Both cases are expected to be rare.</p>
</section>
<section id="reducing-memory-usage">
<span id="memout-scenarios"></span><h2>Reducing memory usage<a class="headerlink" href="#reducing-memory-usage" title="Link to this heading"></a></h2>
<p>In most cases, high memory usage and long running times go hand in hand and
thus <a class="reference internal" href="timeout.html#timeouts-introduction"><span class="std std-ref">Timeouts</span></a> is applicable for out-of-memory issues as well.</p>
<p>There are a number of ways that can help avoiding memory exhaustion, either by</p>
<ul class="simple">
<li><p><a class="reference internal" href="timeout.html#timeout-single-rule"><span class="std std-ref">checking fewer rules</span></a>,</p></li>
<li><p><a class="reference internal" href="timeout.html#library-timeouts"><span class="std std-ref">modularizing the verification</span></a>, or</p></li>
<li><p>fine-tuning <a class="reference internal" href="#memout-smt-portfolio"><span class="std std-ref">which SMT solvers are run</span></a>.</p></li>
</ul>
<p>Furthermore, there is a number of <a class="reference internal" href="timeout.html#timeout-cli-options"><span class="std std-ref">heuristic options</span></a>
that sometimes help to in reducing memory usage in some way or another.</p>
<section id="high-memory-usage-of-smt-solvers">
<span id="memout-smt-portfolio"></span><h3>High memory usage of SMT solvers<a class="headerlink" href="#high-memory-usage-of-smt-solvers" title="Link to this heading"></a></h3>
<p>As discussed in <a class="reference internal" href="timeout.html#high-nonlinear-op-count"><span class="std std-ref">Dealing with nonlinear arithmetic</span></a>, using different SMT solvers or
changing their order is sometimes beneficial. It is important to keep in mind that for out-of-memory issues, simply removing some solvers rarely helps, as the maximum memory usage needs to be reduced. Roughly speaking, this technique only helps if there are fewer calls to the SMT solvers than there are CPU cores available or if a particular solver or solver configuration uses much more memory than the other solvers in this case. Otherwise, reducing the portfolio enables the Prover to run more rules in parallel only when the number of solvers running - and competing for memory - at any given time remains the same.</p>
</section>
</section>
</section>


           </div>
          </div>
          <footer><div class="rst-footer-buttons" role="navigation" aria-label="Footer">
        <a href="index.html" class="btn btn-neutral float-left" title="Managing Timeouts and Out of Memory Problems" accesskey="p" rel="prev"><span class="fa fa-arrow-circle-left" aria-hidden="true"></span> Previous</a>
        <a href="timeout.html" class="btn btn-neutral float-right" title="Timeouts" accesskey="n" rel="next">Next <span class="fa fa-arrow-circle-right" aria-hidden="true"></span></a>
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