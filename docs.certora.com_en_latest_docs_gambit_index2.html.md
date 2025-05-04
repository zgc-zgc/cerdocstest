<!DOCTYPE html><html class="writer-html5" lang="en" data-content_root="../../"><head>
  <meta charset="utf-8"><meta name="viewport" content="width=device-width, initial-scale=1">

  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Gambit: Mutation Generator for Solidity — Certora Prover Documentation 0.0 documentation</title>
      <link rel="stylesheet" type="text/css" href="../../_static/pygments.css?v=80d5e7a1">
      <link rel="stylesheet" type="text/css" href="../../_static/css/theme.css?v=19f00094">
      <link rel="stylesheet" type="text/css" href="../../_static/copybutton.css?v=76b2166b">
      <link rel="stylesheet" type="text/css" href="../../_static/custom.css?v=098d337b">
      <link rel="stylesheet" type="text/css" href="../../_static/sphinx-design.min.css?v=87e54e7c">

  
  <!--[if lt IE 9]>
    <script src="../../_static/js/html5shiv.min.js"></script>
  <![endif]-->
  
        <script src="../../_static/jquery.js?v=5d32c60e"></script>
        <script src="../../_static/_sphinx_javascript_frameworks_compat.js?v=2cd50e6c"></script>
        <script src="../../_static/documentation_options.js?v=837179f8"></script>
        <script src="../../_static/doctools.js?v=9a2dae69"></script>
        <script src="../../_static/sphinx_highlight.js?v=dc90522c"></script>
        <script src="../../_static/clipboard.min.js?v=a7894cd8"></script>
        <script src="../../_static/copybutton.js?v=f281be69"></script>
        <script src="../../_static/design-tabs.js?v=f930bc37"></script>
    <script src="../../_static/js/theme.js"></script>
    <link rel="index" title="Index" href="../../genindex.html">
    <link rel="search" title="Search" href="../../search.html">
    <link rel="next" title="Using Gambit with the Prover" href="mutation-verifier.html">
    <link rel="prev" title="Troubleshooting" href="../solana/troubleshooting.html"> 
</head>

<body class="wy-body-for-nav"> 
  <div class="wy-grid-for-nav">
    <nav data-toggle="wy-nav-shift" class="wy-nav-side">
      <div class="wy-side-scroll">
        <div class="wy-side-nav-search">

          
          
          <a href="../../index.html" class="icon icon-home">
            Certora Prover Documentation
              <img src="../../_static/Certora_Logo_Black.svg" class="logo" alt="Logo">
          </a>
<div role="search">
  <form id="rtd-search-form" class="wy-form" action="../../search.html" method="get">
    <input type="text" name="q" placeholder="Search docs" aria-label="Search docs">
    <input type="hidden" name="check_keywords" value="yes">
    <input type="hidden" name="area" value="default">
  </form>
</div>
        </div><div class="wy-menu wy-menu-vertical" data-spy="affix" role="navigation" aria-label="Navigation menu">
              <p class="caption" role="heading"><span class="caption-text">Contents</span></p>
<ul class="current" aria-expanded="true">
<li class="toctree-l1"><a class="reference internal" href="../user-guide/index.html">Certora User’s Guide</a></li>
<li class="toctree-l1"><a class="reference internal" href="../cvl/index.html">The Certora Verification Language</a></li>
<li class="toctree-l1"><a class="reference internal" href="../prover/index.html">The Certora Prover</a></li>
<li class="toctree-l1"><a class="reference internal" href="../sunbeam/index.html">Sunbeam: Verification for Soroban</a></li>
<li class="toctree-l1"><a class="reference internal" href="../solana/index.html">The Certora Solana Prover</a></li>
<li class="toctree-l1 current" aria-expanded="true"><a class="reference internal current" href="#" aria-expanded="true"><button class="toctree-expand" title="Open/close menu"></button>Gambit: Mutation Generator for Solidity</a><ul>
<li class="toctree-l2"><a class="reference internal" href="mutation-verifier.html">Using Gambit with the Prover</a></li>
<li class="toctree-l2"><a class="reference internal" href="gambit.html">Gambit: Mutant Generation for Solidity</a></li>
</ul>
</li>
</ul>
<p class="caption" role="heading"><span class="caption-text">Additional information</span></p>
<ul>
<li class="toctree-l1"><a class="reference internal" href="../equiv-check/index.html">The Certora Equivalence Checker</a></li>
<li class="toctree-l1"><a class="reference internal" href="../whitepaper/index.html">Certora Technology White Paper</a></li>
</ul>
<ul>
<li class="toctree-l1"><a class="reference internal" href="../../genindex.html">Index</a></li>
</ul>

        </div>
      </div>
    </nav>

    <section data-toggle="wy-nav-shift" class="wy-nav-content-wrap"><nav class="wy-nav-top" aria-label="Mobile navigation menu">
          <i data-toggle="wy-nav-top" class="fa fa-bars"></i>
          <a href="../../index.html">Certora Prover Documentation</a>
      </nav>

      <div class="wy-nav-content">
        <div class="rst-content">
          <div role="navigation" aria-label="Page navigation">
  <ul class="wy-breadcrumbs">
      <li><a href="../../index.html" class="icon icon-home" aria-label="Home"></a></li>
      <li class="breadcrumb-item active">Gambit: Mutation Generator for Solidity</li>
      <li class="wy-breadcrumbs-aside">
            <a href="../../_sources/docs/gambit/index.md.txt" rel="nofollow"> View page source</a>
      </li>
  </ul>
  <hr>
</div>
          <div role="main" class="document" itemscope="itemscope" itemtype="http://schema.org/Article">
           <div itemprop="articleBody">
             
  <section id="gambit-mutation-generator-for-solidity">
<span id="gambit-intro"></span><h1>Gambit: Mutation Generator for Solidity<a class="headerlink" href="#gambit-mutation-generator-for-solidity" title="Link to this heading"></a></h1>
<p>This chapter describes how Certora uses ideas from
mutation testing to evaluate and improve CVL specifications.</p>
<p>Mutation testing is a technique for evaluating and improving
test suites.
Mutants are identical copies of the tested program with a single random change.
The objective is to assess how well a test suite can identify and detect faulty
logic in these mutants.
The more mutants a test suite detects, or <em>kills</em>, the better the test suite is.
<em>Live</em> mutants — those that pass all tests in the test suite — are indications
of potential shortcomings in the test suite and can be used as test goals to
improve the test suite.</p>
<p>At Certora, we use mutation testing to evaluate and
improve formal specifications used in automated verification.
We built <a class="reference external" href="https://github.com/Certora/gambit">Gambit</a>,
an open-source mutation generator for Solidity.
We use the mutants generated by Gambit to assess the CVL specifications
written for a verification task.
Gambit is a general-purpose mutation generation tool that can be used with many
kinds of verifiers or testing tools.
<a class="reference internal" href="mutation-verifier.html"><span class="doc">Using Gambit with the Prover</span></a> describes how to use Gambit with the Certora Prover to
evaluate specifications,
while <a class="reference internal" href="gambit.html"><span class="doc">Gambit: Mutant Generation for Solidity</span></a> describes how Gambit can be used to generate mutants for use with any tool.</p>
<div class="toctree-wrapper compound">
<ul>
<li class="toctree-l1"><a class="reference internal" href="mutation-verifier.html">Using Gambit with the Prover</a><ul>
<li class="toctree-l2"><a class="reference internal" href="mutation-verifier.html#installation">Installation</a></li>
<li class="toctree-l2"><a class="reference internal" href="mutation-verifier.html#running-the-mutation-verifier">Running the Mutation Verifier</a></li>
<li class="toctree-l2"><a class="reference internal" href="mutation-verifier.html#mutation-configuration">Mutation Configuration</a></li>
<li class="toctree-l2"><a class="reference internal" href="mutation-verifier.html#mutation-sources">Mutation Sources</a></li>
<li class="toctree-l2"><a class="reference internal" href="mutation-verifier.html#original-verification-run">Original Verification Run</a></li>
<li class="toctree-l2"><a class="reference internal" href="mutation-verifier.html#the-mutations-dashboard">The Mutations Dashboard</a></li>
<li class="toctree-l2"><a class="reference internal" href="mutation-verifier.html#mutation-test-report">Mutation Test Report</a></li>
<li class="toctree-l2"><a class="reference internal" href="mutation-verifier.html#cli-options">CLI Options</a></li>
<li class="toctree-l2"><a class="reference internal" href="mutation-verifier.html#troubleshooting">Troubleshooting</a></li>
</ul>
</li>
<li class="toctree-l1"><a class="reference internal" href="gambit.html">Gambit: Mutant Generation for Solidity</a><ul>
<li class="toctree-l2"><a class="reference internal" href="gambit.html#requirements">Requirements</a></li>
<li class="toctree-l2"><a class="reference internal" href="gambit.html#installation">Installation</a></li>
<li class="toctree-l2"><a class="reference internal" href="gambit.html#usage">Usage</a></li>
<li class="toctree-l2"><a class="reference internal" href="gambit.html#examples">Examples</a></li>
<li class="toctree-l2"><a class="reference internal" href="gambit.html#configuration-files">Configuration Files</a></li>
<li class="toctree-l2"><a class="reference internal" href="gambit.html#results-directory">Results Directory</a></li>
<li class="toctree-l2"><a class="reference internal" href="gambit.html#cli-options">CLI Options</a></li>
<li class="toctree-l2"><a class="reference internal" href="gambit.html#mutation-operators">Mutation Operators</a></li>
</ul>
</li>
</ul>
</div>
</section>


           </div>
          </div>
          <footer><div class="rst-footer-buttons" role="navigation" aria-label="Footer">
        <a href="../solana/troubleshooting.html" class="btn btn-neutral float-left" title="Troubleshooting" accesskey="p" rel="prev"><span class="fa fa-arrow-circle-left" aria-hidden="true"></span> Previous</a>
        <a href="mutation-verifier.html" class="btn btn-neutral float-right" title="Using Gambit with the Prover" accesskey="n" rel="next">Next <span class="fa fa-arrow-circle-right" aria-hidden="true"></span></a>
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