<!DOCTYPE html><html class="writer-html5" lang="en" data-content_root="../../../"><head>
  <meta charset="utf-8"><meta name="viewport" content="width=device-width, initial-scale=1">

  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Using the Certora Portal — Certora Prover Documentation 0.0 documentation</title>
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
    <link rel="next" title="Certora Verification Reports" href="report.html">
    <link rel="prev" title="Configuration (Conf) Files" href="../cli/conf-file-api.html"> 
</head>

<body class="wy-body-for-nav"> 
  <div class="wy-grid-for-nav">
    <nav data-toggle="wy-nav-shift" class="wy-nav-side">
      <div class="wy-side-scroll">
        <div class="wy-side-nav-search">

          
          
          <a href="../../../index.html" class="icon icon-home">
            Certora Prover Documentation
              <img src="../../../_static/Certora_Logo_Black.svg" class="logo" alt="Logo">
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
<li class="toctree-l2 current" aria-expanded="true"><a class="reference internal current" href="#" aria-expanded="true"><button class="toctree-expand" title="Open/close menu"></button>Using the Certora Portal</a><ul>
<li class="toctree-l3"><a class="reference internal" href="report.html">Certora Verification Reports</a></li>
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
      <li class="breadcrumb-item active">Using the Certora Portal</li>
      <li class="wy-breadcrumbs-aside">
            <a href="../../../_sources/docs/prover/portal/using.md.txt" rel="nofollow"> View page source</a>
      </li>
  </ul>
  <hr>
</div>
          <div role="main" class="document" itemscope="itemscope" itemtype="http://schema.org/Article">
           <div itemprop="articleBody">
             
  <section id="using-the-certora-portal">
<h1>Using the Certora Portal<a class="headerlink" href="#using-the-certora-portal" title="Link to this heading"></a></h1>
<div class="toctree-wrapper compound">
<ul>
<li class="toctree-l1"><a class="reference internal" href="report.html">Certora Verification Reports</a><ul>
<li class="toctree-l2"><a class="reference internal" href="storage-in-calltrace.html">Storage in Call Trace</a><ul>
<li class="toctree-l3"><a class="reference internal" href="storage-in-calltrace.html#introduction">Introduction</a><ul>
<li class="toctree-l4"><a class="reference internal" href="storage-in-calltrace.html#example-storage-data">Example Storage Data</a></li>
</ul>
</li>
<li class="toctree-l3"><a class="reference internal" href="storage-in-calltrace.html#how-can-the-storage-change">How Can the Storage Change?</a></li>
<li class="toctree-l3"><a class="reference internal" href="storage-in-calltrace.html#when-do-we-show-the-storage-state">When Do We Show the Storage State?</a></li>
<li class="toctree-l3"><a class="reference internal" href="storage-in-calltrace.html#what-do-we-show">What Do We Show?</a></li>
<li class="toctree-l3"><a class="reference internal" href="storage-in-calltrace.html#computational-types">Computational Types</a></li>
<li class="toctree-l3"><a class="reference internal" href="storage-in-calltrace.html#limitations-of-the-current-computational-type-resolution">Limitations of the Current “Computational Type” Resolution</a></li>
<li class="toctree-l3"><a class="reference internal" href="storage-in-calltrace.html#reverts">Reverts</a></li>
<li class="toctree-l3"><a class="reference internal" href="storage-in-calltrace.html#havocs">Havocs</a></li>
<li class="toctree-l3"><a class="reference internal" href="storage-in-calltrace.html#call-resolution">Call Resolution</a></li>
</ul>
</li>
<li class="toctree-l2"><a class="reference internal" href="report.html#understanding-counter-examples">Understanding counter-examples</a></li>
</ul>
</li>
<li class="toctree-l1"><a class="reference internal" href="secrets.html">Special Portal URLs</a><ul>
<li class="toctree-l2"><a class="reference internal" href="secrets.html#job-status">Job status</a></li>
<li class="toctree-l2"><a class="reference internal" href="secrets.html#additional-error-reports">Additional error reports</a></li>
<li class="toctree-l2"><a class="reference internal" href="secrets.html#timeout-analysis">Timeout analysis</a></li>
<li class="toctree-l2"><a class="reference internal" href="secrets.html#zip-output">Zip output</a></li>
</ul>
</li>
</ul>
</div>
</section>


           </div>
          </div>
          <footer><div class="rst-footer-buttons" role="navigation" aria-label="Footer">
        <a href="../cli/conf-file-api.html" class="btn btn-neutral float-left" title="Configuration (Conf) Files" accesskey="p" rel="prev"><span class="fa fa-arrow-circle-left" aria-hidden="true"></span> Previous</a>
        <a href="report.html" class="btn btn-neutral float-right" title="Certora Verification Reports" accesskey="n" rel="next">Next <span class="fa fa-arrow-circle-right" aria-hidden="true"></span></a>
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