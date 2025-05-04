<!DOCTYPE html><html class="writer-html5" lang="en" data-content_root="../../"><head>
  <meta charset="utf-8"><meta name="viewport" content="width=device-width, initial-scale=1">

  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Uninterpreted Sorts — Certora Prover Documentation 0.0 documentation</title>
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
    <link rel="next" title="Ghosts" href="ghosts.html">
    <link rel="prev" title="Invariants" href="invariants.html"> 
</head>

<body class="wy-body-for-nav"> 
  <div class="wy-grid-for-nav">
    <nav data-toggle="wy-nav-shift" class="wy-nav-side">
      <div class="wy-side-scroll">
        <div class="wy-side-nav-search">

          
          
          <a href="../../index.html" class="icon icon-home">
            Certora Prover Documentation
              <img src="../../_static/Certora_Logo_Black.svg" class="logo" alt="Logo" width="646" height="188">
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
<li class="toctree-l1 current" aria-expanded="true"><a class="reference internal" href="index.html"><button class="toctree-expand" title="Open/close menu"></button>The Certora Verification Language</a><ul class="" aria-expanded="false">
<li class="toctree-l2"><a class="reference internal" href="overview.html">Specification Files</a></li>
<li class="toctree-l2"><a class="reference internal" href="basics.html">Basic Syntax</a></li>
<li class="toctree-l2"><a class="reference internal" href="types.html">Types</a></li>
<li class="toctree-l2"><a class="reference internal" href="expr.html">Expressions</a></li>
<li class="toctree-l2"><a class="reference internal" href="statements.html">Statements</a></li>
<li class="toctree-l2"><a class="reference internal" href="imports.html">Import and Use Statements</a></li>
<li class="toctree-l2"><a class="reference internal" href="using.html">Using Statements</a></li>
<li class="toctree-l2"><a class="reference internal" href="methods.html">The Methods Block</a></li>
<li class="toctree-l2"><a class="reference internal" href="rules.html">Rules</a></li>
<li class="toctree-l2"><a class="reference internal" href="builtin.html">Built-in Rules</a></li>
<li class="toctree-l2"><a class="reference internal" href="functions.html">Functions</a></li>
<li class="toctree-l2"><a class="reference internal" href="invariants.html">Invariants</a></li>
<li class="toctree-l2 current" aria-expanded="true"><a class="reference internal current" href="#" aria-expanded="true"><button class="toctree-expand" title="Open/close menu"></button>Uninterpreted Sorts</a><ul>
<li class="toctree-l3"><a class="reference internal" href="#syntax-for-uninterpreted-sorts">Syntax for Uninterpreted Sorts</a></li>
<li class="toctree-l3"><a class="reference internal" href="#example-usage">Example Usage</a></li>
<li class="toctree-l3"><a class="reference internal" href="#using-uninterpreted-sorts-with-ghosts">Using Uninterpreted Sorts with Ghosts</a></li>
</ul>
</li>
<li class="toctree-l2"><a class="reference internal" href="ghosts.html">Ghosts</a></li>
<li class="toctree-l2"><a class="reference internal" href="defs.html">Definitions</a></li>
<li class="toctree-l2"><a class="reference internal" href="hooks.html">Hooks</a></li>
<li class="toctree-l2"><a class="reference internal" href="transient.html">Transient Storage</a></li>
<li class="toctree-l2"><a class="reference internal" href="foundry-integration.html">Foundry Integration (Alpha)</a></li>
<li class="toctree-l2"><a class="reference internal" href="index.html#changes-since-cvl-1">Changes Since CVL 1</a></li>
</ul>
</li>
<li class="toctree-l1"><a class="reference internal" href="../prover/index.html">The Certora Prover</a></li>
<li class="toctree-l1"><a class="reference internal" href="../sunbeam/index.html">Sunbeam: Verification for Soroban</a></li>
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
          <li class="breadcrumb-item"><a href="index.html">The Certora Verification Language</a></li>
      <li class="breadcrumb-item active">Uninterpreted Sorts</li>
      <li class="wy-breadcrumbs-aside">
            <a href="../../_sources/docs/cvl/sorts.md.txt" rel="nofollow"> View page source</a>
      </li>
  </ul>
  <hr>
</div>
          <div role="main" class="document" itemscope="itemscope" itemtype="http://schema.org/Article">
           <div itemprop="articleBody">
             
  <section id="uninterpreted-sorts">
<h1>Uninterpreted Sorts<a class="headerlink" href="#uninterpreted-sorts" title="Link to this heading"></a></h1>
<p>CVL specifications support both Solidity primitives (<code class="docutils literal notranslate"><span class="pre">uint256</span></code>, <code class="docutils literal notranslate"><span class="pre">address</span></code>, etc.) and custom types (e.g., <code class="docutils literal notranslate"><span class="pre">mathint</span></code>). Solidity types are <em>interpreted</em>, meaning they have specific semantics, such as arithmetic or comparison operations. However, in some cases, it is beneficial to use <em>uninterpreted sorts</em>, which do not carry the semantics associated with interpretation.</p>
<section id="syntax-for-uninterpreted-sorts">
<h2>Syntax for Uninterpreted Sorts<a class="headerlink" href="#syntax-for-uninterpreted-sorts" title="Link to this heading"></a></h2>
<p>To declare an uninterpreted sort in CVL, use the following syntax:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell0"><span></span>sort<span class="w"> </span>MyUninterpSort<span class="p">;</span>
sort<span class="w"> </span>Foo<span class="p">;</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell0">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>These uninterpreted sorts can be utilized in various ways within a CVL specification:</p>
<ol class="arabic">
<li><p><strong>Declare Variables:</strong></p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell1"><span></span>Foo<span class="w"> </span>x<span class="p">;</span>
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
<li><p><strong>Test Equality:</strong></p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell2"><span></span>Foo<span class="w"> </span>x<span class="p">;</span><span class="w"> </span>
Foo<span class="w"> </span>y<span class="p">;</span><span class="w"> </span>
<span class="kr">assert</span><span class="w"> </span>x<span class="w"> </span><span class="o">==</span><span class="w"> </span>y<span class="p">;</span>
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
<li><p><strong>Use in Signatures:</strong></p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell3"><span></span><span class="kd">ghost</span><span class="w"> </span><span class="nf">myGhost</span><span class="p">(</span><span class="kt">uint256</span><span class="p">,</span><span class="w"> </span>Foo<span class="p">)</span><span class="w"> </span><span class="kr">returns</span><span class="w"> </span>Foo<span class="p">;</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell3">
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
<section id="example-usage">
<h2>Example Usage<a class="headerlink" href="#example-usage" title="Link to this heading"></a></h2>
<p>Consider the following example:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell4"><span></span>sort<span class="w"> </span>Foo<span class="p">;</span>

<span class="kd">ghost</span><span class="w"> </span><span class="nf">bar</span><span class="p">(</span>Foo<span class="p">,</span><span class="w"> </span>Foo<span class="p">)</span><span class="w"> </span><span class="kr">returns</span><span class="w"> </span>Foo<span class="p">;</span>

<span class="k">rule</span><span class="w"> </span><span class="nc">myRule</span><span class="w"> </span><span class="p">{</span>
<span class="w">   </span>Foo<span class="w"> </span>x<span class="p">;</span>
<span class="w">   </span>Foo<span class="w"> </span>y<span class="p">;</span>
<span class="w">   </span>Foo<span class="w"> </span>z<span class="w"> </span><span class="o">=</span><span class="w"> </span>bar<span class="p">(</span>x<span class="p">,</span><span class="w"> </span>y<span class="p">);</span>
<span class="w">   </span><span class="kr">assert</span><span class="w"> </span>x<span class="w"> </span><span class="o">==</span><span class="w"> </span>y<span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span>y<span class="w"> </span><span class="o">==</span><span class="w"> </span>z<span class="p">;</span>
<span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell4">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>This example demonstrates the use of an uninterpreted sort <code class="docutils literal notranslate"><span class="pre">Foo</span></code>. The <code class="docutils literal notranslate"><span class="pre">bar</span></code> ghost function takes two arguments of type <code class="docutils literal notranslate"><span class="pre">Foo</span></code> and returns a value of the same type. The <code class="docutils literal notranslate"><span class="pre">myRule</span></code> rule declares variables <code class="docutils literal notranslate"><span class="pre">x</span></code>, <code class="docutils literal notranslate"><span class="pre">y</span></code>, and <code class="docutils literal notranslate"><span class="pre">z</span></code>, and asserts that they are all equal.</p>
</section>
<section id="using-uninterpreted-sorts-with-ghosts">
<h2>Using Uninterpreted Sorts with Ghosts<a class="headerlink" href="#using-uninterpreted-sorts-with-ghosts" title="Link to this heading"></a></h2>
<p>Uninterpreted sorts can also be employed in ghosts, as shown in the following example:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell5"><span></span><span class="kd">ghost</span><span class="w"> </span><span class="kt">mapping</span><span class="p">(</span><span class="kt">uint256</span><span class="w"> </span><span class="o">=&gt;</span><span class="w"> </span>Node<span class="p">)</span><span class="w"> </span>toNode<span class="p">;</span>
<span class="kd">ghost</span><span class="w"> </span><span class="kt">mapping</span><span class="p">(</span>Node<span class="w"> </span><span class="o">=&gt;</span><span class="w"> </span><span class="kt">mapping</span><span class="p">(</span>Node<span class="w"> </span><span class="o">=&gt;</span><span class="w"> </span><span class="kt">bool</span><span class="p">))</span><span class="w"> </span>reach<span class="w"> </span><span class="p">{</span>
<span class="w">  </span><span class="c1">// Axioms for reachability relation</span>
<span class="w">  </span><span class="kr">axiom</span><span class="w"> </span><span class="kr">forall</span><span class="w"> </span>Node<span class="w"> </span>X<span class="p">.</span><span class="w"> </span>reach<span class="p">[</span>X<span class="p">][</span>X<span class="p">];</span>
<span class="w">  </span><span class="kr">axiom</span><span class="w"> </span><span class="kr">forall</span><span class="w"> </span>Node<span class="w"> </span>X<span class="p">.</span><span class="w"> </span><span class="kr">forall</span><span class="w"> </span>Node<span class="w"> </span>Y<span class="p">.</span>
<span class="w">      </span>reach<span class="p">[</span>X<span class="p">][</span>Y<span class="p">]</span><span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span>reach<span class="p">[</span>Y<span class="p">][</span>X<span class="p">]</span><span class="w"> </span><span class="o">=&gt;</span><span class="w"> </span>X<span class="w"> </span><span class="o">==</span><span class="w"> </span>Y<span class="p">;</span>
<span class="w">  </span><span class="kr">axiom</span><span class="w"> </span><span class="kr">forall</span><span class="w"> </span>Node<span class="w"> </span>X<span class="p">.</span><span class="w"> </span><span class="kr">forall</span><span class="w"> </span>Node<span class="w"> </span>Y<span class="p">.</span><span class="w"> </span><span class="kr">forall</span><span class="w"> </span>Node<span class="w"> </span>Z<span class="p">.</span>
<span class="w">      </span>reach<span class="p">[</span>X<span class="p">][</span>Y<span class="p">]</span><span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span>reach<span class="p">[</span>Y<span class="p">][</span>Z<span class="p">]</span><span class="w"> </span><span class="o">=&gt;</span><span class="w"> </span>reach<span class="p">[</span>X<span class="p">][</span>Z<span class="p">];</span>
<span class="w">  </span><span class="kr">axiom</span><span class="w"> </span><span class="kr">forall</span><span class="w"> </span>Node<span class="w"> </span>X<span class="p">.</span><span class="w"> </span><span class="kr">forall</span><span class="w"> </span>Node<span class="w"> </span>Y<span class="p">.</span><span class="w"> </span><span class="kr">forall</span><span class="w"> </span>Node<span class="w"> </span>Z<span class="p">.</span>
<span class="w">      </span>reach<span class="p">[</span>X<span class="p">][</span>Y<span class="p">]</span><span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span>reach<span class="p">[</span>X<span class="p">][</span>Z<span class="p">]</span><span class="w"> </span><span class="o">=&gt;</span><span class="w"> </span><span class="p">(</span>reach<span class="p">[</span>Y<span class="p">][</span>Z<span class="p">]</span><span class="w"> </span><span class="o">||</span><span class="w"> </span>reach<span class="p">[</span>Z<span class="p">][</span>Y<span class="p">]);</span>
<span class="p">}</span>

<span class="kt">definition</span><span class="w"> </span><span class="nf">isSucc</span><span class="p">(</span>Node<span class="w"> </span>a<span class="p">,</span><span class="w"> </span>Node<span class="w"> </span>b<span class="p">)</span><span class="w"> </span><span class="kr">returns</span><span class="w"> </span><span class="kt">bool</span><span class="w"> </span><span class="o">=</span>
<span class="w">    </span><span class="c1">// Definition for successor relationship</span>
<span class="w">   </span>reach<span class="p">[</span>a<span class="p">][</span>b<span class="p">]</span><span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span>a<span class="w"> </span><span class="o">!=</span><span class="w"> </span>b<span class="w"> </span><span class="o">&amp;&amp;</span>
<span class="w">      </span><span class="p">(</span><span class="kr">forall</span><span class="w"> </span>Node<span class="w"> </span>X<span class="p">.</span><span class="w"> </span>reach<span class="p">[</span>a<span class="p">][</span>X<span class="p">]</span><span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span>reach<span class="p">[</span>X<span class="p">][</span>b<span class="p">]</span><span class="w"> </span><span class="o">=&gt;</span><span class="w"> </span><span class="p">(</span>a<span class="w"> </span><span class="o">==</span><span class="w"> </span>X<span class="w"> </span><span class="o">||</span><span class="w"> </span>b<span class="w"> </span><span class="o">==</span><span class="w"> </span>X<span class="p">));</span>
<span class="w">    </span>
<span class="k">rule</span><span class="w"> </span><span class="nc">checkGetSucc</span><span class="w"> </span><span class="p">{</span>
<span class="w">  </span><span class="kt">uint256</span><span class="w"> </span>key<span class="p">;</span>
<span class="w">  </span><span class="kt">uint256</span><span class="w"> </span>afterKey<span class="w"> </span><span class="o">=</span><span class="w"> </span>getSucc<span class="p">(</span>key<span class="p">);</span>
<span class="w">  </span><span class="kr">assert</span><span class="w"> </span>reach<span class="p">[</span>toNode<span class="p">[</span>key<span class="p">]][</span>toNode<span class="p">[</span>afterKey<span class="p">]];</span>
<span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell5">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>This example demonstrates the use of uninterpreted sorts (<code class="docutils literal notranslate"><span class="pre">Node</span></code>) in ghost mappings and functions, emphasizing their application in specifying relationships and properties without being bound by specific interpretations.</p>
<p>In summary, uninterpreted sorts in CVL provide a versatile tool for declaring abstract types and relationships, allowing for greater expressiveness in specification design.</p>
</section>
</section>


           </div>
          </div>
          <footer><div class="rst-footer-buttons" role="navigation" aria-label="Footer">
        <a href="invariants.html" class="btn btn-neutral float-left" title="Invariants" accesskey="p" rel="prev"><span class="fa fa-arrow-circle-left" aria-hidden="true"></span> Previous</a>
        <a href="ghosts.html" class="btn btn-neutral float-right" title="Ghosts" accesskey="n" rel="next">Next <span class="fa fa-arrow-circle-right" aria-hidden="true"></span></a>
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