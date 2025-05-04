<!DOCTYPE html><html class="writer-html5" lang="en" data-content_root="../../../"><head>
  <meta charset="utf-8"><meta name="viewport" content="width=device-width, initial-scale=1">

  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Harnessing — Certora Prover Documentation 0.0 documentation</title>
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
    <link rel="next" title="Modeling of Hashing in the Certora Prover" href="hashing.html">
    <link rel="prev" title="Method Summarization" href="summarization.html"> 
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
<li class="toctree-l2 current" aria-expanded="true"><a class="reference internal" href="index.html"><button class="toctree-expand" title="Open/close menu"></button>Prover Approximations</a><ul class="" aria-expanded="false">
<li class="toctree-l3"><a class="reference internal" href="loops.html">Loop Unrolling</a></li>
<li class="toctree-l3"><a class="reference internal" href="summarization.html">Method Summarization</a></li>
<li class="toctree-l3 current" aria-expanded="true"><a class="reference internal current" href="#" aria-expanded="true"><button class="toctree-expand" title="Open/close menu"></button>Harnessing</a><ul>
<li class="toctree-l4"><a class="reference internal" href="#example">Example:</a></li>
</ul>
</li>
<li class="toctree-l3"><a class="reference internal" href="hashing.html">Modeling of Hashing in the Certora Prover</a></li>
<li class="toctree-l3"><a class="reference internal" href="grounding.html">Quantifier Grounding</a></li>
</ul>
</li>
<li class="toctree-l2"><a class="reference internal" href="../techniques/index.html">Techniques Used by the Certora Prover</a></li>
<li class="toctree-l2"><a class="reference internal" href="../diagnosis/index.html">Diagnostic Tools</a></li>
<li class="toctree-l2"><a class="reference internal" href="../checking/index.html">Checking Specifications</a></li>
<li class="toctree-l2"><a class="reference internal" href="../cli/index.html">Certora Prover CLI</a></li>
<li class="toctree-l2"><a class="reference internal" href="../portal/using.html">Using the Certora Portal</a></li>
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
          <li class="breadcrumb-item"><a href="index.html">Prover Approximations</a></li>
      <li class="breadcrumb-item active">Harnessing</li>
      <li class="wy-breadcrumbs-aside">
            <a href="../../../_sources/docs/prover/approx/harnessing.md.txt" rel="nofollow"> View page source</a>
      </li>
  </ul>
  <hr>
</div>
          <div role="main" class="document" itemscope="itemscope" itemtype="http://schema.org/Article">
           <div itemprop="articleBody">
             
  <section id="harnessing">
<h1>Harnessing<a class="headerlink" href="#harnessing" title="Link to this heading"></a></h1>
<p>Occasionally, CVL lacks a feature that is necessary for a complete verification
of a contract.  We are working to extend the feature set of CVL to cover these
cases, but in the mean time we have developed a set of workarounds that we
refer to as “harnesses”.</p>
<section id="example">
<h2>Example:<a class="headerlink" href="#example" title="Link to this heading"></a></h2>
<p>Consider a scenario where we want to write a unit test for an internal functions of a contract. The contract serves as a workaround, allowing us to call original functions rather than relying on summarized implementations.</p>
<div class="highlight-solidity notranslate"><div class="highlight"><pre id="codecell0"><span></span><span class="k">contract</span><span class="w"> </span><span class="ni">ExampleHarnessing</span><span class="w"> </span><span class="kt">is</span><span class="w"> </span>ExampleHarnessingGetter<span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kt">constructor</span><span class="p">(</span>Configuration<span class="w"> </span><span class="kt">memory</span><span class="w"> </span>config<span class="p">)</span><span class="w"> </span>ExampleHarnessingGetter<span class="p">(</span>config<span class="p">)</span><span class="w"> </span><span class="p">{</span><span class="w"> </span><span class="p">}</span>
<span class="w">    </span>
<span class="w">    </span><span class="c1">// External wrapper for accrueInternal</span>
<span class="w">    </span><span class="kt">function</span><span class="w"> </span><span class="nv">call_accrueInternal</span><span class="p">()</span><span class="w"> </span><span class="kt">external</span><span class="w"> </span><span class="p">{</span>
<span class="w">        </span><span class="kt">return</span><span class="w"> </span>super<span class="p">.</span>accrueInternal<span class="p">();</span>
<span class="w">    </span><span class="p">}</span>

<span class="w">    </span><span class="c1">// External wrapper for getNowInternal</span>
<span class="w">    </span><span class="kt">function</span><span class="w"> </span><span class="nv">call_getNowInternal</span><span class="p">()</span><span class="w"> </span><span class="kt">external</span><span class="w"> </span>view<span class="w"> </span><span class="kt">returns</span><span class="w"> </span><span class="p">(</span><span class="kt">uint40</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">        </span><span class="kt">return</span><span class="w"> </span>super<span class="p">.</span>getNowInternal<span class="p">();</span>
<span class="w">    </span><span class="p">}</span>

<span class="w">    </span><span class="c1">// Compute the n-th power of 10</span>
<span class="w">    </span><span class="kt">function</span><span class="w"> </span><span class="nv">powerOfTen</span><span class="p">(</span><span class="kt">uint8</span><span class="w"> </span><span class="nv">n</span><span class="p">)</span><span class="w"> </span><span class="kt">public</span><span class="w"> </span>pure<span class="w"> </span><span class="kt">returns</span><span class="w"> </span><span class="p">(</span><span class="kt">uint64</span><span class="p">){</span>
<span class="w">        </span><span class="kt">return</span><span class="w"> </span><span class="kt">uint64</span><span class="p">(</span><span class="kt">uint64</span><span class="p">(</span><span class="m m-Decimal">10</span><span class="p">)</span><span class="w"> </span><span class="o">**</span><span class="w"> </span>n<span class="p">);</span>
<span class="w">    </span><span class="p">}</span>
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
<p>for more details checkout the <a class="reference external" href="https://github.com/Certora/comet/blob/certora/certora/harness/CometHarnessWrappers.sol">source code</a></p>
<p>Here’s a brief overview:</p>
<section id="unit-test-internal-functions">
<h3>unit test internal functions<a class="headerlink" href="#unit-test-internal-functions" title="Link to this heading"></a></h3>
<p><code class="docutils literal notranslate"><span class="pre">call_accrueInternal</span></code> and <code class="docutils literal notranslate"><span class="pre">call_getNowInternal</span></code>: External wrappers facilitating access to internal functions like <code class="docutils literal notranslate"><span class="pre">accrueInternal</span></code> and <code class="docutils literal notranslate"><span class="pre">getNowInternal</span></code>.</p>
</section>
<section id="define-complex-functionally-view-pure">
<h3>define complex functionally  (view/pure)<a class="headerlink" href="#define-complex-functionally-view-pure" title="Link to this heading"></a></h3>
<p><code class="docutils literal notranslate"><span class="pre">powerOfTen</span></code>: A utility function to compute the n-th power of 10.</p>
</section>
</section>
</section>


           </div>
          </div>
          <footer><div class="rst-footer-buttons" role="navigation" aria-label="Footer">
        <a href="summarization.html" class="btn btn-neutral float-left" title="Method Summarization" accesskey="p" rel="prev"><span class="fa fa-arrow-circle-left" aria-hidden="true"></span> Previous</a>
        <a href="hashing.html" class="btn btn-neutral float-right" title="Modeling of Hashing in the Certora Prover" accesskey="n" rel="next">Next <span class="fa fa-arrow-circle-right" aria-hidden="true"></span></a>
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