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
    <link rel="next" title="Gambit: Mutation Generator for Solidity" href="../gambit/index.html">
    <link rel="prev" title="Rule Sanity Checks (Solana)" href="sanity.html"> 
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
<li class="toctree-l2"><a class="reference internal" href="installation.html">Get started with the Solana Certora Prover</a></li>
<li class="toctree-l2"><a class="reference internal" href="usage.html">Using the Solana Certora Prover</a></li>
<li class="toctree-l2"><a class="reference internal" href="speclanguage.html">Certora Verification Language for Rust (CVLR)</a></li>
<li class="toctree-l2"><a class="reference internal" href="options.html">Solana-Specific Options / CLI Flags</a></li>
<li class="toctree-l2"><a class="reference internal" href="output.html">Understanding Prover Output for Solana Programs</a></li>
<li class="toctree-l2"><a class="reference internal" href="sanity.html">Rule Sanity Checks (Solana)</a></li>
<li class="toctree-l2 current" aria-expanded="true"><a class="reference internal current" href="#" aria-expanded="true"><button class="toctree-expand" title="Open/close menu"></button>Troubleshooting</a><ul>
<li class="toctree-l3"><a class="reference internal" href="#unable-to-run-certorasolanaprover">Unable to run <code class="docutils literal notranslate"><span class="pre">certoraSolanaProver</span></code></a></li>
<li class="toctree-l3"><a class="reference internal" href="#jump-to-source-jts-feature-not-working">Jump to Source (JTS) feature not working</a></li>
<li class="toctree-l3"><a class="reference internal" href="#prover-errors">Prover Errors</a></li>
</ul>
</li>
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
      <li class="breadcrumb-item active">Troubleshooting</li>
      <li class="wy-breadcrumbs-aside">
            <a href="../../_sources/docs/solana/troubleshooting.md.txt" rel="nofollow"> View page source</a>
      </li>
  </ul>
  <hr>
</div>
          <div role="main" class="document" itemscope="itemscope" itemtype="http://schema.org/Article">
           <div itemprop="articleBody">
             
  <section id="troubleshooting">
<h1>Troubleshooting<a class="headerlink" href="#troubleshooting" title="Link to this heading"></a></h1>
<p>This section describes resolution of common issues when using the Solana Prover.</p>
<section id="unable-to-run-certorasolanaprover">
<h2>Unable to run <code class="docutils literal notranslate"><span class="pre">certoraSolanaProver</span></code><a class="headerlink" href="#unable-to-run-certorasolanaprover" title="Link to this heading"></a></h2>
<p>The <code class="docutils literal notranslate"><span class="pre">certoraSolanaProver</span></code> command has been introduced in version <code class="docutils literal notranslate"><span class="pre">7.22.0</span></code> of
the Certora Prover package.
Run <code class="docutils literal notranslate"><span class="pre">certoraRun</span> <span class="pre">--version</span></code> to verify that you are using a version greater or
equal to <code class="docutils literal notranslate"><span class="pre">7.22.0</span></code>.
It is possible to upgrade the Certora Prover package with the following command:
<code class="docutils literal notranslate"><span class="pre">pip3</span> <span class="pre">install</span> <span class="pre">--upgrade</span> <span class="pre">certora-cli</span></code>.
For information about how to install the Certora Prover package, refer to
<a class="reference internal" href="installation.html"><span class="std std-doc">Installation</span></a>.</p>
</section>
<section id="jump-to-source-jts-feature-not-working">
<h2>Jump to Source (JTS) feature not working<a class="headerlink" href="#jump-to-source-jts-feature-not-working" title="Link to this heading"></a></h2>
<p>Observe that the Jump to Source feature does not work if the source files are
not
uploaded to the cloud.
For more information about how to use the Certora Prover for Solana and
correctly upload the source files to the cloud, refer to
<a class="reference internal" href="installation.html"><span class="std std-doc">Installation</span></a>.</p>
<p>By default, JTS works for assertions, and for calls to <code class="docutils literal notranslate"><span class="pre">clog!()</span></code> macro (i.e., calls without any additional arguments). In additional, source location is inferred automatically from debug information. However, the reliability of the automatic JTS depends on the optimizations performed by the compiler.</p>
</section>
<section id="prover-errors">
<h2>Prover Errors<a class="headerlink" href="#prover-errors" title="Link to this heading"></a></h2>
<p>The Solana Prover is currently under development, and some features are not
supported yet.  The most common source of errors from the Prover are
stack-allocated arrays.  Accessing an element in an array that has been
allocated on the stack can result in an error.  For instance, the following rule
triggers a Prover error.</p>
<div class="highlight-rust notranslate"><div class="highlight"><pre id="codecell0"><span></span><span class="cp">#[rule]</span>
<span class="k">fn</span><span class="w"> </span><span class="nf">access_stack_element</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kd">let</span><span class="w"> </span><span class="n">ints</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="p">[</span><span class="mi">0</span><span class="p">,</span><span class="w"> </span><span class="mi">1</span><span class="p">,</span><span class="w"> </span><span class="mi">2</span><span class="p">];</span>
<span class="w">    </span><span class="kd">let</span><span class="w"> </span><span class="n">index</span><span class="p">:</span><span class="w"> </span><span class="kt">usize</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">nondet_with</span><span class="p">(</span><span class="o">|</span><span class="n">x</span><span class="o">|</span><span class="w"> </span><span class="o">*</span><span class="n">x</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="mi">3</span><span class="p">);</span>
<span class="w">    </span><span class="n">cvlr_assert</span><span class="o">!</span><span class="p">(</span><span class="n">ints</span><span class="p">[</span><span class="n">index</span><span class="p">]</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="mi">3</span><span class="p">);</span>
<span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell0">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>The Prover will display the following error message:
<img alt="Stack Access Error" src="../../_images/stack_access_error.png" width="847" height="406"></p>
<p>To solve this, modify the source code to move the array to the heap.
For instance, in the previous example it is sufficient to modify the type of
<code class="docutils literal notranslate"><span class="pre">ints</span></code> from <code class="docutils literal notranslate"><span class="pre">[i32;</span> <span class="pre">3]</span></code> to <code class="docutils literal notranslate"><span class="pre">Vec&lt;i32&gt;</span></code>:</p>
<div class="highlight-rust notranslate"><div class="highlight"><pre id="codecell1"><span></span><span class="cp">#[rule]</span>
<span class="k">fn</span><span class="w"> </span><span class="nf">access_stack_element</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kd">let</span><span class="w"> </span><span class="n">ints</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="fm">vec!</span><span class="p">[</span><span class="mi">0</span><span class="p">,</span><span class="w"> </span><span class="mi">1</span><span class="p">,</span><span class="w"> </span><span class="mi">2</span><span class="p">];</span>
<span class="w">    </span><span class="kd">let</span><span class="w"> </span><span class="n">index</span><span class="p">:</span><span class="w"> </span><span class="kt">usize</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">nondet_with</span><span class="p">(</span><span class="o">|</span><span class="n">x</span><span class="o">|</span><span class="w"> </span><span class="o">*</span><span class="n">x</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="mi">3</span><span class="p">);</span>
<span class="w">    </span><span class="n">cvlr_assert</span><span class="o">!</span><span class="p">(</span><span class="n">ints</span><span class="p">[</span><span class="n">index</span><span class="p">]</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="mi">3</span><span class="p">);</span>
<span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell1">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
</section>


           </div>
          </div>
          <footer><div class="rst-footer-buttons" role="navigation" aria-label="Footer">
        <a href="sanity.html" class="btn btn-neutral float-left" title="Rule Sanity Checks (Solana)" accesskey="p" rel="prev"><span class="fa fa-arrow-circle-left" aria-hidden="true"></span> Previous</a>
        <a href="../gambit/index.html" class="btn btn-neutral float-right" title="Gambit: Mutation Generator for Solidity" accesskey="n" rel="next">Next <span class="fa fa-arrow-circle-right" aria-hidden="true"></span></a>
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