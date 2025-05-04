<!DOCTYPE html><html class="writer-html5" lang="en" data-content_root="../../../"><head>
  <meta charset="utf-8"><meta name="viewport" content="width=device-width, initial-scale=1">

  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Storage in Call Trace — Certora Prover Documentation 0.0 documentation</title>
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
    <link rel="next" title="Special Portal URLs" href="secrets.html">
    <link rel="prev" title="Certora Verification Reports" href="report.html"> 
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
<li class="toctree-l1"><a class="reference internal" href="../../user-guide/index.html">Certora User’s Guide</a></li>
<li class="toctree-l1"><a class="reference internal" href="../../cvl/index.html">The Certora Verification Language</a></li>
<li class="toctree-l1 current" aria-expanded="true"><a class="reference internal" href="../index.html"><button class="toctree-expand" title="Open/close menu"></button>The Certora Prover</a><ul class="" aria-expanded="false">
<li class="toctree-l2"><a class="reference internal" href="../intro.html">Introduction</a></li>
<li class="toctree-l2"><a class="reference internal" href="../../user-guide/install.html">Installation</a></li>
<li class="toctree-l2"><a class="reference internal" href="../approx/index.html">Prover Approximations</a></li>
<li class="toctree-l2"><a class="reference internal" href="../techniques/index.html">Techniques Used by the Certora Prover</a></li>
<li class="toctree-l2"><a class="reference internal" href="../diagnosis/index.html">Diagnostic Tools</a></li>
<li class="toctree-l2"><a class="reference internal" href="../checking/index.html">Checking Specifications</a></li>
<li class="toctree-l2"><a class="reference internal" href="../cli/index.html">Certora Prover CLI</a></li>
<li class="toctree-l2 current" aria-expanded="true"><a class="reference internal" href="using.html"><button class="toctree-expand" title="Open/close menu"></button>Using the Certora Portal</a><ul class="" aria-expanded="false">
<li class="toctree-l3 current" aria-expanded="true"><a class="reference internal" href="report.html"><button class="toctree-expand" title="Open/close menu"></button>Certora Verification Reports</a><ul class="" aria-expanded="false">
<li class="toctree-l4 current" aria-expanded="true"><a class="reference internal current" href="#" aria-expanded="true">Storage in Call Trace</a></li>
<li class="toctree-l4"><a class="reference internal" href="report.html#understanding-counter-examples">Understanding counter-examples</a></li>
</ul>
</li>
<li class="toctree-l3"><a class="reference internal" href="secrets.html">Special Portal URLs</a></li>
</ul>
</li>
<li class="toctree-l2"><a class="reference internal" href="../changelog/index.html">Changelogs</a></li>
</ul>
</li>
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
          <li class="breadcrumb-item"><a href="../index.html">The Certora Prover</a></li>
          <li class="breadcrumb-item"><a href="using.html">Using the Certora Portal</a></li>
          <li class="breadcrumb-item"><a href="report.html">Certora Verification Reports</a></li>
      <li class="breadcrumb-item active">Storage in Call Trace</li>
      <li class="wy-breadcrumbs-aside">
            <a href="../../../_sources/docs/prover/portal/storage-in-calltrace.md.txt" rel="nofollow"> View page source</a>
      </li>
  </ul>
  <hr>
</div>
          <div role="main" class="document" itemscope="itemscope" itemtype="http://schema.org/Article">
           <div itemprop="articleBody">
             
  <section id="storage-in-call-trace">
<h1>Storage in Call Trace<a class="headerlink" href="#storage-in-call-trace" title="Link to this heading"></a></h1>
<section id="introduction">
<h2>Introduction<a class="headerlink" href="#introduction" title="Link to this heading"></a></h2>
<p>When exploring the counterexample to an assertion in a CVL (Certora Verification Language) specification, the Prover provides a Call Trace that includes information about the state of the contracts. This trace contains details about the storage values at the beginning of the rule and tracks updates to the storage during the execution of the contracts’ functions.</p>
<section id="example-storage-data">
<h3>Example Storage Data<a class="headerlink" href="#example-storage-data" title="Link to this heading"></a></h3>
<p><img alt="Example Storage Data" src="../../../_images/storage-calltrace1.png" width="708" height="204"></p>
</section>
</section>
<section id="how-can-the-storage-change">
<h2>How Can the Storage Change?<a class="headerlink" href="#how-can-the-storage-change" title="Link to this heading"></a></h2>
<p>While specific storage slots or fields can be assigned new values, it is also possible for the storage of the entire contract to revert to the previous state. This can occur due to the failure of a Solidity require statement, an explicit Solidity revert statement, the restoration of storage to a previously saved state in CVL (e.g., <code class="docutils literal notranslate"><span class="pre">func()</span> <span class="pre">at</span> <span class="pre">init</span></code>), or the application of havoc (invoking functions that havoc the state of contracts).</p>
</section>
<section id="when-do-we-show-the-storage-state">
<h2>When Do We Show the Storage State?<a class="headerlink" href="#when-do-we-show-the-storage-state" title="Link to this heading"></a></h2>
<p>In the Call Trace section, the storage state is presented in three key places:</p>
<ol class="arabic simple">
<li><p>At the beginning of the execution.</p></li>
<li><p>Right after the failed assert.</p></li>
<li><p>After internal function calls.</p></li>
</ol>
<p>The presentation of the storage state can be toggled on or off using a button highlighted in red, as shown below:</p>
<p><img alt="Example Storage Toggle" src="../../../_images/storage-calltrace2.png" width="737" height="62"></p>
</section>
<section id="what-do-we-show">
<h2>What Do We Show?<a class="headerlink" href="#what-do-we-show" title="Link to this heading"></a></h2>
<p>For each contract in the specification, the Call Trace displays all storage access paths instantiated with concrete indices (as determined by the counterexample) used during the execution trace.
The information provided for each access path includes:</p>
<ul class="simple">
<li><p>Source-code name</p></li>
<li><p>Value (if known, represented as <code class="docutils literal notranslate"><span class="pre">*</span></code> if unknown)</p></li>
<li><p>Computational type</p></li>
<li><p>Whether it was changed since the previous time the storage was shown</p></li>
</ul>
</section>
<section id="computational-types">
<h2>Computational Types<a class="headerlink" href="#computational-types" title="Link to this heading"></a></h2>
<p>There are four computational types:</p>
<ol class="arabic simple">
<li><p><strong>Concrete:</strong> The value of this variable is explicitly set in the spec or contract, making it the same in all counterexamples.</p></li>
<li><p><strong>Don’t Care:</strong> The value of this variable is not used before it is written, so its initial value is not relevant.</p></li>
<li><p><strong>Havoc:</strong> The SMT solver chooses a random value.</p></li>
<li><p><strong>Havoc Dependent:</strong> The value results from some computation involving another havoc or havoc-dependent variable. Unlike havoc variables, if the values of all havoc variables are known, this value can be calculated.</p></li>
</ol>
<p>If the type cannot be determined, it is displayed as Unknown.</p>
</section>
<section id="limitations-of-the-current-computational-type-resolution">
<h2>Limitations of the Current “Computational Type” Resolution<a class="headerlink" href="#limitations-of-the-current-computational-type-resolution" title="Link to this heading"></a></h2>
<p>The current resolution for “computational types” has limitations:</p>
<ul class="simple">
<li><p>Only assignments and storage changes (store, havoc, restore) are considered.</p></li>
<li><p>Requires or values that cause revert are not considered in the type resolution.</p></li>
<li><p>Strings or bytes keys of maps are not supported in the Call Trace display.</p></li>
</ul>
</section>
<section id="reverts">
<h2>Reverts<a class="headerlink" href="#reverts" title="Link to this heading"></a></h2>
<p>When a contract execution encounters an issue that violates a require statement or explicitly invokes a revert, the entire state changes may be reverted to the previous state. This is crucial for understanding and debugging issues in contracts.
The call trace provides a clear view of the revert reason and the path that caused the revert as present in the following picture.
<img alt="Example Revert" src="../../../_images/storage-calltrace3.png"></p>
</section>
<section id="havocs">
<h2>Havocs<a class="headerlink" href="#havocs" title="Link to this heading"></a></h2>
<p>Havoc operations introduce non-determinism into the contract execution, allowing the SMT solver to choose a random value. Identifying and understanding havoc points in the Call Trace is essential for comprehending the unpredictable aspects of the contract’s behavior.
Havoc values are displayed in the Call Trace like the following picture.
<img alt="Example Havoc" src="../../../_images/storage-calltrace4.png"></p>
</section>
<section id="call-resolution">
<h2>Call Resolution<a class="headerlink" href="#call-resolution" title="Link to this heading"></a></h2>
<p>A Call Resolution is a representation that correlates the summarization called during the execution trace with the corresponding storage changes. This helps in understanding the flow of the contract execution and associating storage modifications with specific summarization calls.
The Call Resolution is displayed in the Call Trace like the following picture.
<img alt="Example Call Resolution" src="../../../_images/storage-calltrace5.png"></p>
</section>
</section>


           </div>
          </div>
          <footer><div class="rst-footer-buttons" role="navigation" aria-label="Footer">
        <a href="report.html" class="btn btn-neutral float-left" title="Certora Verification Reports" accesskey="p" rel="prev"><span class="fa fa-arrow-circle-left" aria-hidden="true"></span> Previous</a>
        <a href="secrets.html" class="btn btn-neutral float-right" title="Special Portal URLs" accesskey="n" rel="next">Next <span class="fa fa-arrow-circle-right" aria-hidden="true"></span></a>
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