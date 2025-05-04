<!DOCTYPE html><html class="writer-html5" lang="en" data-content_root="../../../"><head>
  <meta charset="utf-8"><meta name="viewport" content="width=device-width, initial-scale=1">

  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Method Summarization — Certora Prover Documentation 0.0 documentation</title>
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
    <link rel="next" title="Harnessing" href="harnessing.html">
    <link rel="prev" title="Loop Unrolling" href="loops.html"> 
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
<li class="toctree-l3 current" aria-expanded="true"><a class="reference internal current" href="#" aria-expanded="true"><button class="toctree-expand" title="Open/close menu"></button>Method Summarization</a><ul>
<li class="toctree-l4"><a class="reference internal" href="#overview">Overview</a></li>
<li class="toctree-l4"><a class="reference internal" href="#how-summarization-helps-solvers">How Summarization Helps Solvers</a></li>
<li class="toctree-l4"><a class="reference internal" href="#syntax">Syntax</a></li>
<li class="toctree-l4"><a class="reference internal" href="#example-summarization-for-a-complex-function">Example: Summarization for a complex function</a></li>
<li class="toctree-l4"><a class="reference internal" href="#important-considerations">Important Considerations</a></li>
<li class="toctree-l4"><a class="reference internal" href="#summary">Summary</a></li>
</ul>
</li>
<li class="toctree-l3"><a class="reference internal" href="harnessing.html">Harnessing</a></li>
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
      <li class="breadcrumb-item active">Method Summarization</li>
      <li class="wy-breadcrumbs-aside">
            <a href="../../../_sources/docs/prover/approx/summarization.md.txt" rel="nofollow"> View page source</a>
      </li>
  </ul>
  <hr>
</div>
          <div role="main" class="document" itemscope="itemscope" itemtype="http://schema.org/Article">
           <div itemprop="articleBody">
             
  <section id="method-summarization">
<h1>Method Summarization<a class="headerlink" href="#method-summarization" title="Link to this heading"></a></h1>
<section id="overview">
<h2>Overview<a class="headerlink" href="#overview" title="Link to this heading"></a></h2>
<p><strong>Method summarization</strong> is a mechanism that allows the user to provide a concise, high-level description of the behavior of a method. It serves as a guide for the underlying solvers to more efficiently reason about the method’s behavior and helps to avoid timeouts, especially in cases where complex computations or undecidable problems are involved.</p>
</section>
<section id="how-summarization-helps-solvers">
<h2>How Summarization Helps Solvers<a class="headerlink" href="#how-summarization-helps-solvers" title="Link to this heading"></a></h2>
<ol class="arabic simple">
<li><p><strong>Efficiency Improvement:</strong></p>
<ul class="simple">
<li><p><strong>Timeout Avoidance:</strong> Summarization provides a way to guide the solver efficiently by providing a more abstract, high-level view of the method, potentially avoiding the need for detailed exploration.</p></li>
<li><p><strong>Faster Analysis:</strong> By focusing on essential properties, summarization can lead to faster analysis, as the solver doesn’t need to explore every intricate detail of the method.</p></li>
</ul>
</li>
<li><p><strong>Abstraction of Complex Logic:</strong></p>
<ul class="simple">
<li><p><strong>Complex Computations:</strong> When dealing with functions involving complex mathematical operations or undecidable problems, summarization allows the user to abstract away unnecessary details, making it easier for the solver to reason about the method’s behavior.</p></li>
</ul>
</li>
</ol>
</section>
<section id="syntax">
<h2>Syntax<a class="headerlink" href="#syntax" title="Link to this heading"></a></h2>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell0"><span></span><span class="kr">methods</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="c1">// Method summarization syntax</span>
<span class="w">    </span><span class="kd">function</span><span class="w"> </span><span class="nf">methodName</span><span class="p">(</span>parameters<span class="p">)</span><span class="w"> </span><span class="kr">returns</span><span class="w"> </span>returnType<span class="w"> </span><span class="kp">=&gt;</span>
<span class="w">        </span><span class="nf">summaryExpression</span><span class="p">;</span>
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
</section>
<section id="example-summarization-for-a-complex-function">
<h2>Example: Summarization for a complex function<a class="headerlink" href="#example-summarization-for-a-complex-function" title="Link to this heading"></a></h2>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell1"><span></span><span class="kt">function</span><span class="w"> </span><span class="nf">multiply</span><span class="p">(</span><span class="kt">uint256</span><span class="w"> </span>x<span class="p">,</span><span class="w"> </span><span class="kt">uint256</span><span class="w"> </span>y<span class="p">)</span><span class="w"> </span><span class="kr">returns</span><span class="w"> </span><span class="kt">uint256</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kr">return</span><span class="w"> </span>x<span class="w"> </span><span class="o">*</span><span class="w"> </span>y<span class="p">;</span>
<span class="p">}</span>
<span class="kr">methods</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kd">function</span><span class="w"> </span><span class="nf">complexFunction</span><span class="p">(</span><span class="kt">uint256</span><span class="w"> </span>x<span class="p">,</span><span class="w"> </span><span class="kt">uint256</span><span class="w"> </span>y<span class="p">)</span><span class="w"> </span><span class="kr">returns</span><span class="w"> </span><span class="kt">bool</span><span class="w"> </span><span class="kp">=&gt;</span>
<span class="w">        </span><span class="nf">exists</span><span class="w"> </span><span class="kt">uint256</span><span class="w"> </span>z<span class="w"> </span><span class="p">.</span><span class="w"> </span>z<span class="w"> </span><span class="o">==</span><span class="w"> </span>multiply<span class="p">(</span>x<span class="p">,</span><span class="w"> </span>y<span class="p">);</span>
<span class="p">}</span>

<span class="k">rule</span><span class="w"> </span><span class="nc">myRule</span><span class="p">(</span><span class="kt">uint256</span><span class="w"> </span>a<span class="p">,</span><span class="w"> </span><span class="kt">uint256</span><span class="w"> </span>b<span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="c1">// Using the summarized method in a rule</span>
<span class="w">    </span><span class="kr">require</span><span class="w"> </span>complexFunction<span class="p">(</span>a<span class="p">,</span><span class="w"> </span>b<span class="p">);</span>
<span class="w">    </span><span class="c1">// ...</span>
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
<p>In the example above, <code class="docutils literal notranslate"><span class="pre">complexFunction</span></code> involves a complex multiplication of <code class="docutils literal notranslate"><span class="pre">x</span></code> and <code class="docutils literal notranslate"><span class="pre">y</span></code>. The summarization <code class="docutils literal notranslate"><span class="pre">exists</span> <span class="pre">uint256</span> <span class="pre">z</span> <span class="pre">.</span> <span class="pre">z</span> <span class="pre">==</span> <span class="pre">x</span> <span class="pre">*</span> <span class="pre">y;</span></code> provides a high-level description, emphasizing the existence of a product <code class="docutils literal notranslate"><span class="pre">z</span></code> that satisfies the multiplication relationship.</p>
</section>
<section id="important-considerations">
<h2>Important Considerations<a class="headerlink" href="#important-considerations" title="Link to this heading"></a></h2>
<ol class="arabic simple">
<li><p><strong>Limitations of Summarization:</strong></p>
<ul class="simple">
<li><p>Summarization is a trade-off between precision and efficiency. While it can significantly improve solver performance, it may introduce over- or under-approximations. over-approximation means we may use too general behaviors to prove the desired property. under-approximations means we potentially miss out on behaviors.</p></li>
<li><p>Care should be taken to ensure that the summarization captures the critical aspects of the method’s behavior.</p></li>
</ul>
</li>
<li><p><strong>Choosing Summarization Techniques:</strong></p>
<ul class="simple">
<li><p>The choice of summarization techniques depends on the nature of the method and the specific verification goals.</p></li>
<li><p>Users may experiment with different summarization strategies to find the right balance between precision and efficiency.
for more information, see <a class="reference internal" href="../../cvl/methods.html"><span class="std std-doc">Summarization</span></a>.</p></li>
</ul>
</li>
</ol>
</section>
<section id="summary">
<h2>Summary<a class="headerlink" href="#summary" title="Link to this heading"></a></h2>
<p>Method summarization in CVL provides a powerful tool for enhancing the efficiency of verification by guiding solvers to focus on essential aspects of a method’s behavior. By abstracting away unnecessary details, summarization helps prevent timeouts in situations involving complex computations or undecidable problems. Users should carefully design and choose summarizations that strike the right balance between precision and efficiency for their specific verification tasks.</p>
</section>
</section>


           </div>
          </div>
          <footer><div class="rst-footer-buttons" role="navigation" aria-label="Footer">
        <a href="loops.html" class="btn btn-neutral float-left" title="Loop Unrolling" accesskey="p" rel="prev"><span class="fa fa-arrow-circle-left" aria-hidden="true"></span> Previous</a>
        <a href="harnessing.html" class="btn btn-neutral float-right" title="Harnessing" accesskey="n" rel="next">Next <span class="fa fa-arrow-circle-right" aria-hidden="true"></span></a>
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