<!DOCTYPE html><html class="writer-html5" lang="en" data-content_root="../../"><head>
  <meta charset="utf-8"><meta name="viewport" content="width=device-width, initial-scale=1">

  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Get started with the Solana Certora Prover — Certora Prover Documentation 0.0 documentation</title>
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
    <link rel="next" title="Using the Solana Certora Prover" href="usage.html">
    <link rel="prev" title="The Certora Solana Prover" href="index.html"> 
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
<li class="toctree-l1 current" aria-expanded="true"><a class="reference internal" href="index.html"><button class="toctree-expand" title="Open/close menu"></button>The Certora Solana Prover</a><ul class="" aria-expanded="false">
<li class="toctree-l2 current" aria-expanded="true"><a class="reference internal current" href="#" aria-expanded="true"><button class="toctree-expand" title="Open/close menu"></button>Get started with the Solana Certora Prover</a><ul>
<li class="toctree-l3"><a class="reference internal" href="#installing-solana-certora-prover">Installing Solana Certora Prover</a></li>
<li class="toctree-l3"><a class="reference internal" href="#rust-solana-and-certora-platform-tools-setup">Rust, Solana, and Certora Platform Tools Setup</a></li>
</ul>
</li>
<li class="toctree-l2"><a class="reference internal" href="usage.html">Using the Solana Certora Prover</a></li>
<li class="toctree-l2"><a class="reference internal" href="speclanguage.html">Certora Verification Language for Rust (CVLR)</a></li>
<li class="toctree-l2"><a class="reference internal" href="options.html">Solana-Specific Options / CLI Flags</a></li>
<li class="toctree-l2"><a class="reference internal" href="output.html">Understanding Prover Output for Solana Programs</a></li>
<li class="toctree-l2"><a class="reference internal" href="sanity.html">Rule Sanity Checks (Solana)</a></li>
<li class="toctree-l2"><a class="reference internal" href="troubleshooting.html">Troubleshooting</a></li>
</ul>
</li>
<li class="toctree-l1"><a class="reference internal" href="../gambit/index.html">Gambit: Mutation Generator for Solidity</a></li>
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
          <li class="breadcrumb-item"><a href="index.html">The Certora Solana Prover</a></li>
      <li class="breadcrumb-item active">Get started with the Solana Certora Prover</li>
      <li class="wy-breadcrumbs-aside">
            <a href="../../_sources/docs/solana/installation.md.txt" rel="nofollow"> View page source</a>
      </li>
  </ul>
  <hr>
</div>
          <div role="main" class="document" itemscope="itemscope" itemtype="http://schema.org/Article">
           <div itemprop="articleBody">
             
  <section id="get-started-with-the-solana-certora-prover">
<h1>Get started with the Solana Certora Prover<a class="headerlink" href="#get-started-with-the-solana-certora-prover" title="Link to this heading"></a></h1>
<section id="installing-solana-certora-prover">
<h2>Installing Solana Certora Prover<a class="headerlink" href="#installing-solana-certora-prover" title="Link to this heading"></a></h2>
<p>Begin by following the steps in the <a class="reference internal" href="../user-guide/install.html#installation"><span class="std std-ref">Certora Prover installation guide</span></a>.</p>
</section>
<section id="rust-solana-and-certora-platform-tools-setup">
<h2>Rust, Solana, and Certora Platform Tools Setup<a class="headerlink" href="#rust-solana-and-certora-platform-tools-setup" title="Link to this heading"></a></h2>
<ol class="arabic">
<li><p>We recommend installing Rust as on the
official <a class="reference external" href="https://www.rust-lang.org/tools/install">Rust website</a>:</p>
<p><code class="docutils literal notranslate"><span class="pre">curl</span> <span class="pre">--proto</span> <span class="pre">'=https'</span> <span class="pre">--tlsv1.2</span> <span class="pre">-sSf</span> <span class="pre">https://sh.rustup.rs</span> <span class="pre">|</span> <span class="pre">sh</span></code></p>
<p>It is useful to have Rust versions 1.75, 1.79, and 1.81 or above installed.</p>
<div class="highlight-default notranslate"><div class="highlight"><pre id="codecell0"><span></span><span class="n">rustup</span> <span class="n">toolchain</span> <span class="n">install</span> <span class="mf">1.79</span>
<span class="n">rustup</span> <span class="n">toolchain</span> <span class="n">install</span> <span class="mf">1.75</span>
<span class="n">rustup</span> <span class="n">toolchain</span> <span class="n">install</span> <span class="mf">1.81</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell0">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</li>
<li><p>Install <code class="docutils literal notranslate"><span class="pre">certora-sbf</span></code> cargo sub-command</p>
<p><code class="docutils literal notranslate"><span class="pre">cargo</span> <span class="pre">+1.81</span> <span class="pre">install</span> <span class="pre">cargo-certora-sbf</span></code></p>
<p>Note that a minimal version of Rust required to install <code class="docutils literal notranslate"><span class="pre">certora-sbf</span></code> is
v1.81.</p>
</li>
<li><p>Test the installation by using <code class="docutils literal notranslate"><span class="pre">certora-sbf</span></code> to download and install Certora
Platform Tools</p>
<p><code class="docutils literal notranslate"><span class="pre">cargo</span> <span class="pre">certora-sbf</span> <span class="pre">--no-build</span></code></p>
</li>
<li><p>It is strongly recommended to install VSCode and the rust-analyzer extension.</p></li>
</ol>
<hr class="docutils">
<p>Congratulations! You have just completed Solana Certora Prover’s installation and setup.</p>
<div class="admonition caution">
<p class="admonition-title">Caution</p>
<p>We strongly recommend trying the tool on basic examples to verify correct installation.
See <a class="reference internal" href="usage.html#solana-usage"><span class="std std-ref">Using the Solana Certora Prover</span></a> for a detailed walkthrough.</p>
</div>
</section>
</section>


           </div>
          </div>
          <footer><div class="rst-footer-buttons" role="navigation" aria-label="Footer">
        <a href="index.html" class="btn btn-neutral float-left" title="The Certora Solana Prover" accesskey="p" rel="prev"><span class="fa fa-arrow-circle-left" aria-hidden="true"></span> Previous</a>
        <a href="usage.html" class="btn btn-neutral float-right" title="Using the Solana Certora Prover" accesskey="n" rel="next">Next <span class="fa fa-arrow-circle-right" aria-hidden="true"></span></a>
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