<!DOCTYPE html><html class="writer-html5" lang="en" data-content_root="../../../"><head>
  <meta charset="utf-8"><meta name="viewport" content="width=device-width, initial-scale=1">

  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Quantifier Grounding — Certora Prover Documentation 0.0 documentation</title>
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
    <link rel="next" title="Techniques Used by the Certora Prover" href="../techniques/index.html">
    <link rel="prev" title="Modeling of Hashing in the Certora Prover" href="hashing.html"> 
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
<li class="toctree-l2 current" aria-expanded="true"><a class="reference internal" href="index.html"><button class="toctree-expand" title="Open/close menu"></button>Prover Approximations</a><ul class="" aria-expanded="false">
<li class="toctree-l3"><a class="reference internal" href="loops.html">Loop Unrolling</a></li>
<li class="toctree-l3"><a class="reference internal" href="summarization.html">Method Summarization</a></li>
<li class="toctree-l3"><a class="reference internal" href="harnessing.html">Harnessing</a></li>
<li class="toctree-l3"><a class="reference internal" href="hashing.html">Modeling of Hashing in the Certora Prover</a></li>
<li class="toctree-l3 current" aria-expanded="true"><a class="reference internal current" href="#" aria-expanded="true"><button class="toctree-expand" title="Open/close menu"></button>Quantifier Grounding</a><ul>
<li class="toctree-l4"><a class="reference internal" href="#how-grounding-works">How grounding works</a></li>
<li class="toctree-l4"><a class="reference internal" href="#limitations-on-grounding">Limitations on grounding</a></li>
</ul>
</li>
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
      <li class="breadcrumb-item active">Quantifier Grounding</li>
      <li class="wy-breadcrumbs-aside">
            <a href="../../../_sources/docs/prover/approx/grounding.md.txt" rel="nofollow"> View page source</a>
      </li>
  </ul>
  <hr>
</div>
          <div role="main" class="document" itemscope="itemscope" itemtype="http://schema.org/Article">
           <div itemprop="articleBody">
             
  <section id="quantifier-grounding">
<span id="grounding"></span><h1><a class="toc-backref" href="#id1" role="doc-backlink">Quantifier Grounding</a><a class="headerlink" href="#quantifier-grounding" title="Link to this heading"></a></h1>
<p><a class="reference internal" href="../../user-guide/glossary.html#term-quantifier"><span class="xref std std-term">Quantified expressions</span></a> are a very powerful tool for writing
specifications, but they can also lead to incredibly long running times.  For
this reason, the Prover uses an approximation called “grounding”.</p>
<p>It is not possible to ground every expression perfectly.  While grounding is
<a class="reference internal" href="../../user-guide/glossary.html#term-sound"><span class="xref std std-term">sound</span></a> (i.e. it will not allow a rule to be verified if it is not true),
there are cases where it may generate <a class="reference internal" href="../../user-guide/glossary.html#term-counterexample"><span class="xref std std-term">counterexample</span></a>s even for rules
that should pass.  For example, a counterexample may not obey a <code class="docutils literal notranslate"><span class="pre">require</span></code>
statement that contains a quantifier.</p>
<p>You can prevent spurious counterexamples by turning off grounding (by passing
<a class="reference internal" href="../cli/options.html#smt-groundquantifiers"><span class="std std-ref">smt_groundQuantifiers</span></a>), but without grounding the Prover may run
considerably slower, and is likely to time out.</p>
<p>The remainder of this document explains grounding in more detail, and lists the
specific kinds of quantified expressions that may lead to spurious
counterexamples.  We also include some suggestions for rewriting your
quantified statements to avoid spurious counterexamples.</p>
<nav class="contents" id="contents">
<p class="topic-title">Contents</p>
<ul class="simple">
<li><p><a class="reference internal" href="#quantifier-grounding" id="id1">Quantifier Grounding</a></p>
<ul>
<li><p><a class="reference internal" href="#how-grounding-works" id="id2">How grounding works</a></p></li>
<li><p><a class="reference internal" href="#limitations-on-grounding" id="id3">Limitations on grounding</a></p>
<ul>
<li><p><a class="reference internal" href="#alternating-quantifiers" id="id4">Alternating Quantifiers</a></p></li>
<li><p><a class="reference internal" href="#recursion" id="id5">Recursion</a></p></li>
<li><p><a class="reference internal" href="#variables-must-be-arguments" id="id6">Variables must be arguments</a></p></li>
<li><p><a class="reference internal" href="#double-polarity" id="id7">Double Polarity</a></p></li>
</ul>
</li>
</ul>
</li>
</ul>
</nav>
<section id="how-grounding-works">
<h2><a class="toc-backref" href="#id2" role="doc-backlink">How grounding works</a><a class="headerlink" href="#how-grounding-works" title="Link to this heading"></a></h2>
<p>Quantifier grounding transforms a <a class="reference internal" href="../../user-guide/glossary.html#term-quantifier"><span class="xref std std-term">quantified</span></a> statement
into a series of non-quantified statements.  For example, suppose a
specification contains the following <a class="reference internal" href="../../cvl/ghosts.html#ghost-axioms"><span class="std std-ref">ghost axiom</span></a>:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell0"><span></span><span class="kd">ghost</span><span class="w"> </span><span class="nf">f</span><span class="p">(</span><span class="kt">uint</span><span class="w"> </span>x<span class="p">)</span><span class="w"> </span><span class="kr">returns</span><span class="w"> </span><span class="p">(</span><span class="kt">mathint</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kr">init_state</span><span class="w"> </span><span class="kr">axiom</span><span class="w"> </span><span class="kr">forall</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>x<span class="w"> </span><span class="p">.</span><span class="w"> </span>f<span class="p">(</span>x<span class="p">)</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="m m-Decimal">0</span>
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
<p>This statement logically says that <code class="docutils literal notranslate"><span class="pre">f(0)</span> <span class="pre">==</span> <span class="pre">0</span></code> and <code class="docutils literal notranslate"><span class="pre">f(1)</span> <span class="pre">==</span> <span class="pre">0</span></code> and <code class="docutils literal notranslate"><span class="pre">f(2)</span> <span class="pre">==</span> <span class="pre">0</span></code>
and so on.  In practice, however, the verification may only make use of a small
finite number of these facts.  Grounding is the process of automatically
replacing the <code class="docutils literal notranslate"><span class="pre">forall</span></code> statement with the specific unquantified statements that
are necessary.</p>
<p>For example, if the program and specification only ever access <code class="docutils literal notranslate"><span class="pre">f(2)</span></code>, <code class="docutils literal notranslate"><span class="pre">f(9)</span></code>,
<code class="docutils literal notranslate"><span class="pre">f(y+3)</span></code>, and <code class="docutils literal notranslate"><span class="pre">f(z)</span></code>, then the axiom above would be automatically replaced
with:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell1"><span></span><span class="kd">ghost</span><span class="w"> </span><span class="nf">f</span><span class="p">(</span><span class="kt">uint</span><span class="w"> </span>x<span class="p">)</span><span class="w"> </span><span class="kr">returns</span><span class="w"> </span><span class="p">(</span><span class="kt">mathint</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kr">init_state</span><span class="w"> </span><span class="kr">axiom</span><span class="w"> </span>f<span class="p">(</span><span class="m m-Decimal">2</span><span class="p">)</span><span class="w">   </span><span class="o">==</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">;</span>
<span class="w">    </span><span class="kr">init_state</span><span class="w"> </span><span class="kr">axiom</span><span class="w"> </span>f<span class="p">(</span><span class="m m-Decimal">9</span><span class="p">)</span><span class="w">   </span><span class="o">==</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">;</span>
<span class="w">    </span><span class="kr">init_state</span><span class="w"> </span><span class="kr">axiom</span><span class="w"> </span>f<span class="p">(</span>y<span class="o">+</span><span class="m m-Decimal">3</span><span class="p">)</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">;</span>
<span class="w">    </span><span class="kr">init_state</span><span class="w"> </span><span class="kr">axiom</span><span class="w"> </span>f<span class="p">(</span>z<span class="p">)</span><span class="w">   </span><span class="o">==</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">;</span>
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
<p>The Prover will also ground more complex quantified expressions, and will ground
them anywhere that you can write a quantified statement (e.g. <code class="docutils literal notranslate"><span class="pre">assert</span></code> and
<code class="docutils literal notranslate"><span class="pre">require</span></code> statements, ghost axioms, and invariants).  Grounding also works with
<code class="docutils literal notranslate"><span class="pre">exists</span></code> quantifiers.</p>
</section>
<section id="limitations-on-grounding">
<h2><a class="toc-backref" href="#id3" role="doc-backlink">Limitations on grounding</a><a class="headerlink" href="#limitations-on-grounding" title="Link to this heading"></a></h2>
<p>In some cases, there is an easy way to rewrite your expression with fewer
quantifiers.  For example, the following quantified statement requires that
<code class="docutils literal notranslate"><span class="pre">f(x)</span></code> is always odd, but it is written in a way that violates <a class="reference internal" href="#grounding-arguments"><span class="std std-ref">one of the restrictions on quantifiers</span></a>:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell2"><span></span><span class="kr">require</span><span class="w"> </span><span class="kr">forall</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>x<span class="w"> </span><span class="p">.</span><span class="w"> </span><span class="kr">forall</span><span class="w"> </span><span class="kt">mathint</span><span class="w"> </span>y<span class="w"> </span><span class="p">.</span><span class="w"> </span>f<span class="p">(</span>x<span class="p">)</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="m m-Decimal">2</span><span class="w"> </span><span class="o">*</span><span class="w"> </span>y<span class="p">;</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell2">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>However, there is a much simpler way to require that <code class="docutils literal notranslate"><span class="pre">f(x)</span></code> is odd by using <code class="docutils literal notranslate"><span class="pre">%</span></code>:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell3"><span></span><span class="kr">require</span><span class="w"> </span><span class="kr">forall</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>x<span class="w"> </span><span class="p">.</span><span class="w"> </span>f<span class="p">(</span>x<span class="p">)</span><span class="w"> </span><span class="o">%</span><span class="w"> </span><span class="m m-Decimal">2</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="m m-Decimal">1</span><span class="p">;</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell3">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>This rewritten statement obeys the rules listed below, and therefore will not
produce any spurious counterexamples.</p>
<p>The remainder of this section describes specific cases where the Prover cannot
ground quantified statements, and gives advice on how to work around those
limitations.</p>
<section id="alternating-quantifiers">
<span id="grounding-alternating"></span><h3><a class="toc-backref" href="#id4" role="doc-backlink">Alternating Quantifiers</a><a class="headerlink" href="#alternating-quantifiers" title="Link to this heading"></a></h3>
<p>Alternating quantifiers (those containing <code class="docutils literal notranslate"><span class="pre">forall</span></code> followed by <code class="docutils literal notranslate"><span class="pre">exist</span></code> or
vice-versa) complicate the process of grounding, so there are limitations to
what statements you can write and which of them are grounded.</p>
<p>In most contexts, you may not have a <code class="docutils literal notranslate"><span class="pre">forall</span></code> expression contained inside of an
<code class="docutils literal notranslate"><span class="pre">exists</span></code> statement.  For example, this is allowed:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell4"><span></span><span class="kr">assert</span><span class="w"> </span><span class="kr">forall</span><span class="w"> </span><span class="kt">address</span><span class="w"> </span>x<span class="w"> </span><span class="p">.</span><span class="w"> </span><span class="kr">forall</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>y<span class="w"> </span><span class="p">.</span><span class="w"> </span><span class="kr">exists</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>z<span class="w"> </span><span class="p">.</span><span class="w"> </span><span class="kr">exists</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>w<span class="w"> </span><span class="p">.</span><span class="w"> </span>e<span class="p">(</span>x<span class="p">,</span>y<span class="p">,</span>z<span class="p">,</span>w<span class="p">);</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell4">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>but this is disallowed:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell5"><span></span><span class="kr">assert</span><span class="w"> </span><span class="kr">forall</span><span class="w"> </span><span class="kt">address</span><span class="w"> </span>x<span class="w"> </span><span class="p">.</span><span class="w"> </span><span class="kr">exists</span><span class="w"> </span><span class="kt">address</span><span class="w"> </span>y<span class="w"> </span><span class="p">.</span><span class="w"> </span><span class="kr">exists</span><span class="w"> </span><span class="kt">address</span><span class="w"> </span>z<span class="w"> </span><span class="p">.</span><span class="w"> </span><span class="kr">forall</span><span class="w"> </span><span class="kt">address</span><span class="w"> </span>w<span class="w"> </span><span class="p">.</span><span class="w"> </span>e<span class="p">(</span>x<span class="p">,</span>y<span class="p">,</span>z<span class="p">,</span>w<span class="p">);</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell5">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>In the latter case, the <code class="docutils literal notranslate"><span class="pre">forall</span> <span class="pre">address</span> <span class="pre">w</span></code> is contained inside the <code class="docutils literal notranslate"><span class="pre">exists</span> <span class="pre">address</span> <span class="pre">z</span></code>.</p>
<p>Logical negations and <code class="docutils literal notranslate"><span class="pre">require</span></code> statements reverse the rules for <code class="docutils literal notranslate"><span class="pre">forall</span></code> and
<code class="docutils literal notranslate"><span class="pre">exists</span></code> statements: in those contexts, you cannot nest an <code class="docutils literal notranslate"><span class="pre">exists</span></code> expression
inside of a <code class="docutils literal notranslate"><span class="pre">forall</span></code> statement.  Including another negation will again reverse
the rules.  For example, the following are allowed:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell6"><span></span><span class="kr">require</span><span class="w">    </span><span class="kr">exists</span><span class="w"> </span><span class="kt">address</span><span class="w"> </span>x<span class="w"> </span><span class="p">.</span><span class="w"> </span><span class="kr">forall</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>y<span class="w"> </span><span class="p">.</span><span class="w"> </span>e<span class="p">(</span>x<span class="p">,</span>y<span class="p">);</span>
<span class="kr">assert</span><span class="w">   </span><span class="o">!</span><span class="p">(</span><span class="kr">exists</span><span class="w"> </span><span class="kt">address</span><span class="w"> </span>x<span class="w"> </span><span class="p">.</span><span class="w"> </span><span class="kr">forall</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>y<span class="w"> </span><span class="p">.</span><span class="w"> </span>e<span class="p">(</span>x<span class="p">,</span>y<span class="p">));</span>
<span class="kr">require</span><span class="w">  </span><span class="o">!</span><span class="p">(</span><span class="kr">forall</span><span class="w"> </span><span class="kt">address</span><span class="w"> </span>x<span class="w"> </span><span class="p">.</span><span class="w"> </span><span class="kr">exists</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>y<span class="w"> </span><span class="p">.</span><span class="w"> </span>e<span class="p">(</span>x<span class="p">,</span>y<span class="p">));</span>
<span class="kr">assert</span><span class="w"> </span><span class="o">!</span><span class="p">(</span><span class="o">!</span><span class="p">(</span><span class="kr">forall</span><span class="w"> </span><span class="kt">address</span><span class="w"> </span>x<span class="w"> </span><span class="p">.</span><span class="w"> </span><span class="kr">exists</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>y<span class="w"> </span><span class="p">.</span><span class="w"> </span>e<span class="p">(</span>x<span class="p">,</span>y<span class="p">)));</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell6">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>but these are disallowed:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell7"><span></span><span class="kr">require</span><span class="w">  </span><span class="kr">forall</span><span class="w"> </span><span class="kt">address</span><span class="w"> </span>x<span class="w"> </span><span class="p">.</span><span class="w"> </span><span class="kr">exists</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>y<span class="w"> </span><span class="p">.</span><span class="w"> </span>e<span class="p">(</span>x<span class="p">,</span>y<span class="p">);</span>
<span class="kr">assert</span><span class="w"> </span><span class="o">!</span><span class="p">(</span><span class="kr">forall</span><span class="w"> </span><span class="kt">address</span><span class="w"> </span>x<span class="w"> </span><span class="p">.</span><span class="w"> </span><span class="kr">exists</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>y<span class="w"> </span><span class="p">.</span><span class="w"> </span>e<span class="p">(</span>x<span class="p">,</span>y<span class="p">));</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell7">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>One common way to work around these limitations is by replacing <code class="docutils literal notranslate"><span class="pre">exists</span></code>
expressions with concrete expressions that produce the values that should exist.</p>
<p>For example, suppose your contract function always returned twice its input:</p>
<div class="highlight-solidity notranslate"><div class="highlight"><pre id="codecell8"><span></span><span class="kt">function</span><span class="w"> </span><span class="nv">f</span><span class="p">(</span><span class="kt">uint</span><span class="w"> </span><span class="nv">x</span><span class="p">)</span><span class="w"> </span><span class="kt">external</span><span class="w"> </span><span class="kt">returns</span><span class="p">(</span><span class="kt">uint</span><span class="p">)</span><span class="w"> </span><span class="p">{</span><span class="w"> </span><span class="kt">return</span><span class="w"> </span><span class="m m-Decimal">2</span><span class="w"> </span><span class="o">*</span><span class="w"> </span>x<span class="p">;</span><span class="w"> </span><span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell8">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>You might like to prove that if <code class="docutils literal notranslate"><span class="pre">x</span></code> is positive, then it’s possible for <code class="docutils literal notranslate"><span class="pre">f</span></code> to
output something smaller than <code class="docutils literal notranslate"><span class="pre">f(x)</span></code>:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell9"><span></span><span class="kr">assert</span><span class="w"> </span><span class="kr">forall</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>x<span class="w"> </span><span class="p">.</span><span class="w"> </span><span class="p">(</span>x<span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">)</span><span class="w"> </span><span class="o">=&gt;</span><span class="w"> </span><span class="p">(</span><span class="kr">exists</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>y<span class="w"> </span><span class="p">.</span><span class="w"> </span>f<span class="p">(</span>y<span class="p">)</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span>f<span class="p">(</span>x<span class="p">));</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell9">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>This is clearly true; for example <code class="docutils literal notranslate"><span class="pre">f(x</span> <span class="pre">-</span> <span class="pre">1)</span></code> is always smaller than <code class="docutils literal notranslate"><span class="pre">f(x)</span></code>, as
is <code class="docutils literal notranslate"><span class="pre">f(0)</span></code>.  However, to work around the nested quantifier restriction, we have
to help the Prover find the correct value for <code class="docutils literal notranslate"><span class="pre">y</span></code>.  We could replace this
statement with either of the following two:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell10"><span></span><span class="kr">assert</span><span class="w"> </span><span class="kr">forall</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>x<span class="w"> </span><span class="p">.</span><span class="w"> </span><span class="p">(</span>x<span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">)</span><span class="w"> </span><span class="o">=&gt;</span><span class="w"> </span>f<span class="p">(</span><span class="m m-Decimal">0</span><span class="p">)</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span>f<span class="p">(</span>x<span class="p">);</span>
<span class="kr">assert</span><span class="w"> </span><span class="kr">forall</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>x<span class="w"> </span><span class="p">.</span><span class="w"> </span><span class="p">(</span>x<span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">)</span><span class="w"> </span><span class="o">=&gt;</span><span class="w"> </span>f<span class="p">(</span>x<span class="o">-</span><span class="m m-Decimal">1</span><span class="p">)</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span>f<span class="p">(</span>x<span class="p">);</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell10">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
<section id="recursion">
<span id="grounding-recursion"></span><h3><a class="toc-backref" href="#id5" role="doc-backlink">Recursion</a><a class="headerlink" href="#recursion" title="Link to this heading"></a></h3>
<p>Quantified statements that relate a function with itself on two different
inputs may give incorrect counterexamples.  For example, the following <code class="docutils literal notranslate"><span class="pre">forall</span></code>
statement refers to <code class="docutils literal notranslate"><span class="pre">f</span></code> twice:</p>
<div class="highlight-default notranslate"><div class="highlight"><pre id="codecell11"><span></span><span class="n">rule</span> <span class="n">recursiveQuantifier</span> <span class="p">{</span>
    <span class="n">require</span> <span class="n">forall</span> <span class="n">uint</span> <span class="n">x</span> <span class="o">.</span> <span class="n">f</span><span class="p">(</span><span class="n">x</span><span class="p">)</span> <span class="o">&gt;</span> <span class="n">f</span><span class="p">(</span><span class="n">x</span><span class="o">-</span><span class="mi">1</span><span class="p">);</span>
    <span class="k">assert</span> <span class="n">f</span><span class="p">(</span><span class="mi">8</span><span class="p">)</span> <span class="o">&gt;</span> <span class="n">f</span><span class="p">(</span><span class="mi">6</span><span class="p">);</span>
<span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell11">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>Although we can see that the assertion must be true, we would need to combine
the statements <code class="docutils literal notranslate"><span class="pre">f(8)</span> <span class="pre">&gt;</span> <span class="pre">f(7)</span></code> and <code class="docutils literal notranslate"><span class="pre">f(7)</span> <span class="pre">&gt;</span> <span class="pre">f(6)</span></code> to prove it, and the grounding
mechanism is unable to do this.</p>
<p>In these cases, you may see a counterexample that doesn’t satisfy the <code class="docutils literal notranslate"><span class="pre">require</span></code>
statement; in this case the best option is to disable grounding with
<a class="reference internal" href="../cli/options.html#smt-groundquantifiers"><span class="std std-ref">smt_groundQuantifiers</span></a>.</p>
</section>
<section id="variables-must-be-arguments">
<span id="grounding-arguments"></span><h3><a class="toc-backref" href="#id6" role="doc-backlink">Variables must be arguments</a><a class="headerlink" href="#variables-must-be-arguments" title="Link to this heading"></a></h3>
<p>In order for grounding to work, every variable appearing in a quantified
statement must be used at least once as an argument to a ghost or contract
function.  For example, neither of the following examples are allowed:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell12"><span></span><span class="kr">require</span><span class="w"> </span><span class="kr">forall</span><span class="w"> </span><span class="kt">mathint</span><span class="w"> </span>x<span class="w"> </span><span class="p">.</span><span class="w"> </span>x<span class="w"> </span><span class="o">*</span><span class="w"> </span><span class="m m-Decimal">2</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span>y<span class="p">;</span>
<span class="kr">require</span><span class="w"> </span><span class="kr">forall</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>x<span class="w"> </span><span class="p">.</span><span class="w"> </span><span class="kr">forall</span><span class="w"> </span><span class="kt">mathint</span><span class="w"> </span>y<span class="w"> </span><span class="p">.</span><span class="w"> </span>f<span class="p">(</span>x<span class="p">)</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="m m-Decimal">2</span><span class="w"> </span><span class="o">*</span><span class="w"> </span>y<span class="p">;</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell12">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>In the first example, <code class="docutils literal notranslate"><span class="pre">x</span></code> is not used as an argument to a function, while in the
second case, <code class="docutils literal notranslate"><span class="pre">y</span></code> is not.</p>
<p>Although you are allowed to call functions on complicated expressions that use
quantified variables, doing so may produce spurious counterexamples.  For
example, the following is allowed, but is likely to produce spurious
counterexamples (because <code class="docutils literal notranslate"><span class="pre">x</span></code> itself is not an argument to a function):</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell13"><span></span><span class="kr">require</span><span class="w"> </span><span class="kr">forall</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>x<span class="w"> </span><span class="p">.</span><span class="w"> </span>f<span class="p">(</span><span class="m m-Decimal">2</span><span class="w"> </span><span class="o">*</span><span class="w"> </span>x<span class="p">)</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">;</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell13">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>This particular example requires that all even inputs to <code class="docutils literal notranslate"><span class="pre">f</span></code> produce <code class="docutils literal notranslate"><span class="pre">0</span></code> as
output; it could be rewritten as follows:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell14"><span></span><span class="kr">require</span><span class="w"> </span><span class="kr">forall</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>y<span class="w"> </span><span class="p">.</span><span class="w"> </span><span class="p">(</span>y<span class="w"> </span><span class="o">%</span><span class="w"> </span><span class="m m-Decimal">2</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">)</span><span class="w"> </span><span class="o">=&gt;</span><span class="w"> </span>f<span class="p">(</span>y<span class="p">)</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">;</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell14">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>If you use a quantified variable in an argument to two different functions,
you may produce spurious counterexamples.  For example:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell15"><span></span><span class="kr">require</span><span class="w"> </span><span class="kr">forall</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>x<span class="w"> </span><span class="p">.</span><span class="w"> </span>f<span class="p">(</span>x<span class="p">)</span><span class="w"> </span><span class="o">&lt;=</span><span class="w"> </span>g<span class="p">(</span>x<span class="o">+</span><span class="m m-Decimal">1</span><span class="p">)</span><span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span>g<span class="p">(</span>x<span class="o">+</span><span class="m m-Decimal">1</span><span class="p">)</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">;</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell15">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>Here, <code class="docutils literal notranslate"><span class="pre">x</span> <span class="pre">+</span> <span class="pre">1</span></code> is used as an argument to <code class="docutils literal notranslate"><span class="pre">g</span></code>, but <code class="docutils literal notranslate"><span class="pre">x</span></code> is not; you may get
counterexamples where <code class="docutils literal notranslate"><span class="pre">g(x+1)</span> <span class="pre">==</span> <span class="pre">0</span></code> for some <code class="docutils literal notranslate"><span class="pre">x</span></code>.  In that case, you can add an
additional equivalent require that does use the quantified variable as an argument
to <code class="docutils literal notranslate"><span class="pre">g</span></code>:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell16"><span></span><span class="kr">require</span><span class="w"> </span><span class="kr">forall</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>x<span class="w"> </span><span class="p">.</span><span class="w"> </span>f<span class="p">(</span>x<span class="p">)</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span>g<span class="p">(</span>x<span class="o">+</span><span class="m m-Decimal">1</span><span class="p">)</span><span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span>g<span class="p">(</span>x<span class="o">+</span><span class="m m-Decimal">1</span><span class="p">)</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">;</span>
<span class="kr">require</span><span class="w"> </span><span class="kr">forall</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>x<span class="w"> </span><span class="p">.</span><span class="w"> </span>f<span class="p">(</span>x<span class="o">-</span><span class="m m-Decimal">1</span><span class="p">)</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span>g<span class="p">(</span>x<span class="p">)</span><span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span>g<span class="p">(</span>x<span class="p">)</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">;</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell16">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>This will make <code class="docutils literal notranslate"><span class="pre">x</span></code> a direct argument to <code class="docutils literal notranslate"><span class="pre">g</span></code>, so the expression will be
grounded properly.</p>
</section>
<section id="double-polarity">
<span id="grounding-polarity"></span><h3><a class="toc-backref" href="#id7" role="doc-backlink">Double Polarity</a><a class="headerlink" href="#double-polarity" title="Link to this heading"></a></h3>
<p>The polarity of a sub-formula is the direction of the effect it has on the
output of the formula. This is best demonstrated through an example:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell17"><span></span>a<span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span><span class="p">(</span>b<span class="w"> </span><span class="o">||</span><span class="w"> </span><span class="o">!</span>c<span class="p">)</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell17">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>In this example, <code class="docutils literal notranslate"><span class="pre">b</span></code> possesses a positive polarity because changing <code class="docutils literal notranslate"><span class="pre">b</span></code> from <code class="docutils literal notranslate"><span class="pre">false</span></code> to <code class="docutils literal notranslate"><span class="pre">true</span></code>
can’t make the formula <code class="docutils literal notranslate"><span class="pre">false</span></code> if it wasn’t before.  Informally, making <code class="docutils literal notranslate"><span class="pre">b</span></code>
“more true” can only make the whole formula “more true”.</p>
<p>In this example, <code class="docutils literal notranslate"><span class="pre">a</span></code> also possesses positive polarity: if the formula was true when <code class="docutils literal notranslate"><span class="pre">a</span></code> was
<code class="docutils literal notranslate"><span class="pre">false</span></code>, it must also be <code class="docutils literal notranslate"><span class="pre">true</span></code> when <code class="docutils literal notranslate"><span class="pre">a</span></code> is <code class="docutils literal notranslate"><span class="pre">true</span></code>.</p>
<p>On the other hand, <code class="docutils literal notranslate"><span class="pre">c</span></code> has a negative polarity because changing <code class="docutils literal notranslate"><span class="pre">c</span></code> from <code class="docutils literal notranslate"><span class="pre">true</span></code>
to <code class="docutils literal notranslate"><span class="pre">false</span></code> can only make the statement “more false”.  If can’t become <code class="docutils literal notranslate"><span class="pre">true</span></code> if
it wasn’t true before.</p>
<p>Sub-expressions can also have double polarity.  For example, consider the
formula</p>
<div class="highlight-default notranslate"><div class="highlight"><pre id="codecell18"><span></span><span class="n">a</span> <span class="o">&lt;=&gt;</span> <span class="n">b</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell18">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>In this example, <code class="docutils literal notranslate"><span class="pre">a</span></code> has double polarity, because making <code class="docutils literal notranslate"><span class="pre">a</span></code> true could cause
the formula to become <code class="docutils literal notranslate"><span class="pre">false</span></code> when it was true before, but it could also cause
the formula to become <code class="docutils literal notranslate"><span class="pre">true</span></code> when it wasn’t before.</p>
<p>Grounding is disallowed when the quantified expression has double polarity in the
rule.  For example, the following is disallowed, because the <code class="docutils literal notranslate"><span class="pre">forall</span></code> statement
has double polarity.</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell19"><span></span><span class="k">rule</span><span class="w"> </span><span class="nc">r</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="p">...</span>
<span class="w">    </span><span class="kr">assert</span><span class="w"> </span><span class="p">(</span><span class="kr">forall</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>x<span class="w"> </span><span class="p">.</span><span class="w"> </span>f<span class="p">(</span>x<span class="p">)</span><span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">)</span><span class="w"> </span><span class="o">&lt;=&gt;</span><span class="w"> </span>y<span class="p">;</span>
<span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell19">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>In many cases you can split a rule with a quantifier in a double-polarity
position into multiple rules with single-polarity quantifiers.  For example, the
above assertion could be split into two rules:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell20"><span></span><span class="k">rule</span><span class="w"> </span><span class="nc">r1</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="p">...</span>
<span class="w">    </span><span class="kr">assert</span><span class="w"> </span><span class="p">(</span><span class="kr">forall</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>x<span class="w"> </span><span class="p">.</span><span class="w"> </span>f<span class="p">(</span>x<span class="p">)</span><span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">)</span><span class="w"> </span><span class="o">=&gt;</span><span class="w"> </span>y<span class="p">;</span>
<span class="p">}</span>

<span class="k">rule</span><span class="w"> </span><span class="nc">r2</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="p">...</span>
<span class="w">    </span><span class="kr">assert</span><span class="w"> </span>y<span class="w"> </span><span class="o">=&gt;</span><span class="w"> </span><span class="p">(</span><span class="kr">forall</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>x<span class="w"> </span><span class="p">.</span><span class="w"> </span>f<span class="p">(</span>x<span class="p">)</span><span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">);</span>
<span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell20">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>Verifying <code class="docutils literal notranslate"><span class="pre">r1</span></code> and <code class="docutils literal notranslate"><span class="pre">r2</span></code> is logically equivalent to verifying <code class="docutils literal notranslate"><span class="pre">r</span></code>, but the
quantified expression appears with single polarity in each of the two rules.</p>
</section>
</section>
</section>


           </div>
          </div>
          <footer><div class="rst-footer-buttons" role="navigation" aria-label="Footer">
        <a href="hashing.html" class="btn btn-neutral float-left" title="Modeling of Hashing in the Certora Prover" accesskey="p" rel="prev"><span class="fa fa-arrow-circle-left" aria-hidden="true"></span> Previous</a>
        <a href="../techniques/index.html" class="btn btn-neutral float-right" title="Techniques Used by the Certora Prover" accesskey="n" rel="next">Next <span class="fa fa-arrow-circle-right" aria-hidden="true"></span></a>
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