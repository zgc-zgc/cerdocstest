<!DOCTYPE html><html class="writer-html5" lang="en" data-content_root="../../"><head>
  <meta charset="utf-8"><meta name="viewport" content="width=device-width, initial-scale=1">

  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Troubleshooting — Certora Prover Documentation 0.0 documentation</title>
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
    <link rel="next" title="The Certora Solana Prover" href="../solana/index.html">
    <link rel="prev" title="User Guide For Sunbeam" href="usage.html"> 
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
<li class="toctree-l1 current" aria-expanded="true"><a class="reference internal" href="index.html"><button class="toctree-expand" title="Open/close menu"></button>Sunbeam: Verification for Soroban</a><ul class="" aria-expanded="false">
<li class="toctree-l2"><a class="reference internal" href="installation.html">Installation</a></li>
<li class="toctree-l2"><a class="reference internal" href="usage.html">User Guide For Sunbeam</a></li>
<li class="toctree-l2 current" aria-expanded="true"><a class="reference internal current" href="#" aria-expanded="true"><button class="toctree-expand" title="Open/close menu"></button>Troubleshooting</a><ul>
<li class="toctree-l3"><a class="reference internal" href="#unable-to-run-certorasorobanprover">Unable to run <code class="docutils literal notranslate"><span class="pre">certoraSorobanProver</span></code></a></li>
<li class="toctree-l3"><a class="reference internal" href="#build-step-of-certorasorobanprover-is-failing">Build step of <code class="docutils literal notranslate"><span class="pre">certoraSorobanProver</span></code> is failing</a></li>
<li class="toctree-l3"><a class="reference internal" href="#compiler-error-error-linking-with-cc-failed-exit-status-1-on-mac">Compiler Error: “error: linking with `cc` failed: exit status: 1” on Mac</a></li>
</ul>
</li>
</ul>
</li>
<li class="toctree-l1"><a class="reference internal" href="../solana/index.html">The Certora Solana Prover</a></li>
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
          <li class="breadcrumb-item"><a href="index.html">Sunbeam: Verification for Soroban</a></li>
      <li class="breadcrumb-item active">Troubleshooting</li>
      <li class="wy-breadcrumbs-aside">
            <a href="../../_sources/docs/sunbeam/troubleshooting.rst.txt" rel="nofollow"> View page source</a>
      </li>
  </ul>
  <hr>
</div>
          <div role="main" class="document" itemscope="itemscope" itemtype="http://schema.org/Article">
           <div itemprop="articleBody">
             
  <section id="troubleshooting">
<h1>Troubleshooting<a class="headerlink" href="#troubleshooting" title="Link to this heading"></a></h1>
<section id="unable-to-run-certorasorobanprover">
<h2>Unable to run <code class="docutils literal notranslate"><span class="pre">certoraSorobanProver</span></code><a class="headerlink" href="#unable-to-run-certorasorobanprover" title="Link to this heading"></a></h2>
<p>If you are unable to run <code class="docutils literal notranslate"><span class="pre">certoraSorobanProver</span></code>, we recommend trying it from within a <code class="docutils literal notranslate"><span class="pre">venv</span></code>.</p>
<ol class="arabic">
<li><p>First, create a <code class="docutils literal notranslate"><span class="pre">venv</span></code> and make sure you are inside the <code class="docutils literal notranslate"><span class="pre">venv</span></code> by running the
following:</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell0"><span></span><span class="nb">cd</span><span class="w"> </span>projectDir
python3<span class="w"> </span>-m<span class="w"> </span>venv<span class="w"> </span>.venv
<span class="nb">source</span><span class="w"> </span>.venv/bin/activate
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
<li><p>Then, install all required packages like so:</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell1"><span></span>pip3<span class="w"> </span>install<span class="w"> </span>-r<span class="w"> </span>requirements.txt
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell1">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</li>
<li><p>Finally, try running <code class="docutils literal notranslate"><span class="pre">certoraRun</span></code> again:</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell2"><span></span>certoraSorobanProver<span class="w"> </span>path/to/prover_config.conf
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell2">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</li>
</ol>
</section>
<hr class="docutils">
<section id="build-step-of-certorasorobanprover-is-failing">
<h2>Build step of <code class="docutils literal notranslate"><span class="pre">certoraSorobanProver</span></code> is failing<a class="headerlink" href="#build-step-of-certorasorobanprover-is-failing" title="Link to this heading"></a></h2>
<p>When you execute <code class="docutils literal notranslate"><span class="pre">certoraSorobanProver</span></code>, the project is internally build using <code class="docutils literal notranslate"><span class="pre">cargo</span> <span class="pre">build</span></code>.
This step requires a successful build. In case <code class="docutils literal notranslate"><span class="pre">certoraSorobanProver</span></code> fails on the build step,
first try to compile the project by running
<code class="docutils literal notranslate"><span class="pre">cargo</span> <span class="pre">build</span> <span class="pre">--release</span> <span class="pre">--target</span> <span class="pre">wasm32-unknown-unknown</span></code>
and resolve all compiler errors that you see.</p>
</section>
<hr class="docutils">
<section id="compiler-error-error-linking-with-cc-failed-exit-status-1-on-mac">
<h2>Compiler Error: “error: linking with `cc` failed: exit status: 1” on Mac<a class="headerlink" href="#compiler-error-error-linking-with-cc-failed-exit-status-1-on-mac" title="Link to this heading"></a></h2>
<p>If you are running on Mac and the build step of your project or <code class="docutils literal notranslate"><span class="pre">certoraRun</span></code> fails
with the warning:</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell3"><span></span><span class="s2">"error: linking with \`cc\` failed: exit status: 1"</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell3">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>then check out the following <a class="reference external" href="https://stackoverflow.com/questions/28124221/error-linking-with-cc-failed-exit-code-1">StackOverflow post</a>.</p>
</section>
</section>


           </div>
          </div>
          <footer><div class="rst-footer-buttons" role="navigation" aria-label="Footer">
        <a href="usage.html" class="btn btn-neutral float-left" title="User Guide For Sunbeam" accesskey="p" rel="prev"><span class="fa fa-arrow-circle-left" aria-hidden="true"></span> Previous</a>
        <a href="../solana/index.html" class="btn btn-neutral float-right" title="The Certora Solana Prover" accesskey="n" rel="next">Next <span class="fa fa-arrow-circle-right" aria-hidden="true"></span></a>
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