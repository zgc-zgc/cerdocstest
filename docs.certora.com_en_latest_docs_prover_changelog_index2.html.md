<!DOCTYPE html><html class="writer-html5" lang="en" data-content_root="../../../"><head>
  <meta charset="utf-8"><meta name="viewport" content="width=device-width, initial-scale=1">

  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Changelogs — Certora Prover Documentation 0.0 documentation</title>
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
    <link rel="next" title="Prover Release Notes" href="prover_changelog.html">
    <link rel="prev" title="Special Portal URLs" href="../portal/secrets.html"> 
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
<li class="toctree-l2"><a class="reference internal" href="../portal/using.html">Using the Certora Portal</a></li>
<li class="toctree-l2 current" aria-expanded="true"><a class="reference internal current" href="#" aria-expanded="true"><button class="toctree-expand" title="Open/close menu"></button>Changelogs</a><ul>
<li class="toctree-l3"><a class="reference internal" href="prover_changelog.html">Prover Release Notes</a></li>
<li class="toctree-l3"><a class="reference internal" href="gui_changelog.html">GUI Release Notes</a></li>
</ul>
</li>
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
      <li class="breadcrumb-item active">Changelogs</li>
      <li class="wy-breadcrumbs-aside">
            <a href="../../../_sources/docs/prover/changelog/index.md.txt" rel="nofollow"> View page source</a>
      </li>
  </ul>
  <hr>
</div>
          <div role="main" class="document" itemscope="itemscope" itemtype="http://schema.org/Article">
           <div itemprop="articleBody">
             
  <section id="changelogs">
<h1>Changelogs<a class="headerlink" href="#changelogs" title="Link to this heading"></a></h1>
<div class="toctree-wrapper compound">
<p class="caption" role="heading"><span class="caption-text">Contents</span></p>
<ul>
<li class="toctree-l1"><a class="reference internal" href="prover_changelog.html">Prover Release Notes</a><ul>
<li class="toctree-l2"><a class="reference internal" href="prover_changelog.html#april-10-2025">7.28.0 (April 10, 2025)</a></li>
<li class="toctree-l2"><a class="reference internal" href="prover_changelog.html#mar-13-2025">7.26.0 (Mar 13, 2025)</a></li>
<li class="toctree-l2"><a class="reference internal" href="prover_changelog.html#feb-19-2025">7.25.2 (Feb 19, 2025)</a></li>
<li class="toctree-l2"><a class="reference internal" href="prover_changelog.html#jan-12-2025">7.22.2 (Jan 12, 2025)</a></li>
<li class="toctree-l2"><a class="reference internal" href="prover_changelog.html#december-12-2024">7.21.1 (December 12, 2024)</a></li>
<li class="toctree-l2"><a class="reference internal" href="prover_changelog.html#november-20-2024">7.20.1 (November 20, 2024)</a></li>
<li class="toctree-l2"><a class="reference internal" href="prover_changelog.html#october-8-2024">7.17.2 (October 8, 2024)</a></li>
<li class="toctree-l2"><a class="reference internal" href="prover_changelog.html#september-2-2024">7.14.2 (September 2, 2024)</a></li>
<li class="toctree-l2"><a class="reference internal" href="prover_changelog.html#july-25-2024">7.10.1 (July 25, 2024)</a></li>
<li class="toctree-l2"><a class="reference internal" href="prover_changelog.html#may-15-2024">7.6.3 (May 15, 2024)</a></li>
<li class="toctree-l2"><a class="reference internal" href="prover_changelog.html#april-11-2024">7.3.0 (April 11, 2024)</a></li>
<li class="toctree-l2"><a class="reference internal" href="prover_changelog.html#march-15-2024">7.0.7 (March 15, 2024)</a></li>
<li class="toctree-l2"><a class="reference internal" href="prover_changelog.html#february-2-2024">6.3.1 (February 2, 2024)</a></li>
<li class="toctree-l2"><a class="reference internal" href="prover_changelog.html#january-11-2024">6.1.3 (January 11, 2024)</a></li>
<li class="toctree-l2"><a class="reference internal" href="prover_changelog.html#november-21-2023">5.0.5 (November 21, 2023)</a></li>
<li class="toctree-l2"><a class="reference internal" href="prover_changelog.html#september-26-2023">4.13.1 (September 26, 2023)</a></li>
<li class="toctree-l2"><a class="reference internal" href="prover_changelog.html#september-17-2023">4.12.1 (September 17, 2023)</a></li>
<li class="toctree-l2"><a class="reference internal" href="prover_changelog.html#august-21-2023">4.10.1 (August 21, 2023)</a></li>
<li class="toctree-l2"><a class="reference internal" href="prover_changelog.html#august-13-2023">4.8.0 (August 13, 2023)</a></li>
<li class="toctree-l2"><a class="reference internal" href="prover_changelog.html#july-15-2023">4.5.1 (July 15, 2023)</a></li>
<li class="toctree-l2"><a class="reference internal" href="prover_changelog.html#july-2-2023">4.3.1 (July 2, 2023)</a></li>
<li class="toctree-l2"><a class="reference internal" href="prover_changelog.html#june-7-2023-cvl-2">4.0.5 (June 7, 2023) CVL 2</a></li>
</ul>
</li>
<li class="toctree-l1"><a class="reference internal" href="gui_changelog.html">GUI Release Notes</a><ul>
<li class="toctree-l2"><a class="reference internal" href="gui_changelog.html#apr-10-2025">4.3.0 (Apr 10, 2025)</a></li>
<li class="toctree-l2"><a class="reference internal" href="gui_changelog.html#mar-13-2025">4.0.2 (Mar 13, 2025)</a></li>
<li class="toctree-l2"><a class="reference internal" href="gui_changelog.html#feb-19-2025">4.0.0 (Feb 19, 2025)</a></li>
<li class="toctree-l2"><a class="reference internal" href="gui_changelog.html#jan-12-2025">3.1.1 (Jan 12, 2025)</a></li>
<li class="toctree-l2"><a class="reference internal" href="gui_changelog.html#nov-18-2024">3.0.2 (Nov 18, 2024)</a></li>
<li class="toctree-l2"><a class="reference internal" href="gui_changelog.html#nov-6-2024">2.4.4 (Nov 6, 2024)</a></li>
<li class="toctree-l2"><a class="reference internal" href="gui_changelog.html#oct-6-2024">2.4.1 (Oct 6, 2024)</a></li>
<li class="toctree-l2"><a class="reference internal" href="gui_changelog.html#sep-2-2024">2.3.2 (Sep 2, 2024)</a></li>
<li class="toctree-l2"><a class="reference internal" href="gui_changelog.html#jul-24-2024">2.2.0 (Jul 24, 2024)</a></li>
<li class="toctree-l2"><a class="reference internal" href="gui_changelog.html#jul-8-2024">2.1.6 (Jul 8, 2024)</a></li>
<li class="toctree-l2"><a class="reference internal" href="gui_changelog.html#may-15-2024">2.0.1 (May 15, 2024)</a></li>
<li class="toctree-l2"><a class="reference internal" href="gui_changelog.html#apr-11-2024">1.0.0 (Apr 11, 2024)</a></li>
<li class="toctree-l2"><a class="reference internal" href="gui_changelog.html#mar-11-2024">0.8.0 (Mar 11, 2024)</a></li>
<li class="toctree-l2"><a class="reference internal" href="gui_changelog.html#feb-12-2024">0.7.0 (Feb 12, 2024)</a></li>
<li class="toctree-l2"><a class="reference internal" href="gui_changelog.html#jan-31-2024">0.6.0 (Jan 31, 2024)</a></li>
<li class="toctree-l2"><a class="reference internal" href="gui_changelog.html#nov-26-2023">0.5.7 (Nov 26, 2023)</a></li>
<li class="toctree-l2"><a class="reference internal" href="gui_changelog.html#feb-11-2024">0.5.62 (Feb 11, 2024)</a></li>
<li class="toctree-l2"><a class="reference internal" href="gui_changelog.html#october-24-2023">0.5.6 (October 24, 2023)</a></li>
</ul>
</li>
</ul>
</div>
</section>


           </div>
          </div>
          <footer><div class="rst-footer-buttons" role="navigation" aria-label="Footer">
        <a href="../portal/secrets.html" class="btn btn-neutral float-left" title="Special Portal URLs" accesskey="p" rel="prev"><span class="fa fa-arrow-circle-left" aria-hidden="true"></span> Previous</a>
        <a href="prover_changelog.html" class="btn btn-neutral float-right" title="Prover Release Notes" accesskey="n" rel="next">Next <span class="fa fa-arrow-circle-right" aria-hidden="true"></span></a>
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