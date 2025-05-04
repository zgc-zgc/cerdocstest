<!DOCTYPE html><html class="writer-html5" lang="en" data-content_root="../../"><head>
  <meta charset="utf-8"><meta name="viewport" content="width=device-width, initial-scale=1">

  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Definitions — Certora Prover Documentation 0.0 documentation</title>
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
    <link rel="next" title="Hooks" href="hooks.html">
    <link rel="prev" title="Ghosts" href="ghosts.html"> 
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
<li class="toctree-l2"><a class="reference internal" href="sorts.html">Uninterpreted Sorts</a></li>
<li class="toctree-l2"><a class="reference internal" href="ghosts.html">Ghosts</a></li>
<li class="toctree-l2 current" aria-expanded="true"><a class="reference internal current" href="#" aria-expanded="true"><button class="toctree-expand" title="Open/close menu"></button>Definitions</a><ul>
<li class="toctree-l3"><a class="reference internal" href="#basic-usage"><button class="toctree-expand" title="Open/close menu"></button>Basic Usage</a><ul>
<li class="toctree-l4"><a class="reference internal" href="#example">Example:</a></li>
</ul>
</li>
<li class="toctree-l3"><a class="reference internal" href="#advanced-functionality"><button class="toctree-expand" title="Open/close menu"></button>Advanced Functionality</a><ul>
<li class="toctree-l4"><a class="reference internal" href="#include-an-application-of-another-definition">Include an Application of Another Definition</a></li>
<li class="toctree-l4"><a class="reference internal" href="#type-error-circular-dependency">Type Error circular dependency</a></li>
<li class="toctree-l4"><a class="reference internal" href="#reference-ghost-functions">Reference Ghost Functions</a></li>
</ul>
</li>
<li class="toctree-l3"><a class="reference internal" href="#filter-example">Filter Example</a></li>
<li class="toctree-l3"><a class="reference internal" href="#syntax">Syntax</a></li>
</ul>
</li>
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
      <li class="breadcrumb-item active">Definitions</li>
      <li class="wy-breadcrumbs-aside">
            <a href="../../_sources/docs/cvl/defs.md.txt" rel="nofollow"> View page source</a>
      </li>
  </ul>
  <hr>
</div>
          <div role="main" class="document" itemscope="itemscope" itemtype="http://schema.org/Article">
           <div itemprop="articleBody">
             
  <section id="definitions">
<h1>Definitions<a class="headerlink" href="#definitions" title="Link to this heading"></a></h1>
<section id="basic-usage">
<h2>Basic Usage<a class="headerlink" href="#basic-usage" title="Link to this heading"></a></h2>
<p>In CVL, <strong>definitions</strong> serve as type-checked macros, encapsulating commonly used expressions. They are declared at the top level of a specification and are in scope inside every rule, function, and other definitions. The basic usage involves binding parameters for use in an expression on the right-hand side, with the result evaluating to the declared return type. Definitions can take any number of arguments of any primitive types, including uninterpreted sorts, and evaluate to a single primitive type, including uninterpreted sorts.</p>
<section id="example">
<h3>Example:<a class="headerlink" href="#example" title="Link to this heading"></a></h3>
<p><code class="docutils literal notranslate"><span class="pre">is_even</span></code> binds the variable <code class="docutils literal notranslate"><span class="pre">x</span></code> as a <code class="docutils literal notranslate"><span class="pre">uint256</span></code>. Definitions are applied just as any function would be.</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell0"><span></span><span class="kr">methods</span><span class="w"> </span><span class="p">{</span>
<span class="w">  </span>foo<span class="p">(</span><span class="kt">uint256</span><span class="p">)</span><span class="w"> </span><span class="kr">returns</span><span class="w"> </span><span class="kt">bool</span><span class="w"> </span><span class="kr">envfree</span>
<span class="p">}</span>

<span class="kt">definition</span><span class="w"> </span><span class="nf">MAX_UINT256</span><span class="p">()</span><span class="w"> </span><span class="kr">returns</span><span class="w"> </span><span class="kt">uint256</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mh">0xffffffffffffffffffffffffffffffff</span><span class="p">;</span>
<span class="kt">definition</span><span class="w"> </span><span class="nf">is_even</span><span class="p">(</span><span class="kt">uint256</span><span class="w"> </span>x<span class="p">)</span><span class="w"> </span><span class="kr">returns</span><span class="w"> </span><span class="kt">bool</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="kr">exists</span><span class="w"> </span><span class="kt">uint256</span><span class="w"> </span>y<span class="w"> </span><span class="p">.</span><span class="w"> </span><span class="m m-Decimal">2</span><span class="w"> </span><span class="o">*</span><span class="w"> </span>y<span class="w"> </span><span class="o">==</span><span class="w"> </span>x<span class="p">;</span>

<span class="k">rule</span><span class="w"> </span><span class="nc">my_rule</span><span class="p">(</span><span class="kt">uint256</span><span class="w"> </span>x<span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">  </span><span class="kr">require</span><span class="w"> </span>is_even<span class="p">(</span>x<span class="p">)</span><span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span>x<span class="w"> </span><span class="o">&lt;=</span><span class="w"> </span>MAX_UINT256<span class="p">();</span>
<span class="w">  </span>foo<span class="ow">@withrevert</span><span class="p">(</span>x<span class="p">);</span>
<span class="w">  </span><span class="kr">assert</span><span class="w"> </span><span class="o">!</span><span class="nb">lastReverted</span><span class="p">;</span>
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
</section>
<section id="advanced-functionality">
<h2>Advanced Functionality<a class="headerlink" href="#advanced-functionality" title="Link to this heading"></a></h2>
<section id="include-an-application-of-another-definition">
<h3>Include an Application of Another Definition<a class="headerlink" href="#include-an-application-of-another-definition" title="Link to this heading"></a></h3>
<p>Definitions can include an application of another definition, allowing for arbitrarily deep nesting. However, circular dependencies are not allowed, and the type checker will report an error if detected.</p>
<section id="id1">
<h4>Example:<a class="headerlink" href="#id1" title="Link to this heading"></a></h4>
<p><code class="docutils literal notranslate"><span class="pre">is_odd</span></code> and <code class="docutils literal notranslate"><span class="pre">is_odd_no_overflow</span></code> both reference other definitions:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell1"><span></span><span class="kt">definition</span><span class="w"> </span><span class="nf">MAX_UINT256</span><span class="p">()</span><span class="w"> </span><span class="kr">returns</span><span class="w"> </span><span class="kt">uint256</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mh">0xffffffffffffffffffffffffffffffff</span><span class="p">;</span>
<span class="kt">definition</span><span class="w"> </span><span class="nf">is_even</span><span class="p">(</span><span class="kt">uint256</span><span class="w"> </span>x<span class="p">)</span><span class="w"> </span><span class="kr">returns</span><span class="w"> </span><span class="kt">bool</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="kr">exists</span><span class="w"> </span><span class="kt">uint256</span><span class="w"> </span>y<span class="w"> </span><span class="p">.</span><span class="w"> </span><span class="m m-Decimal">2</span><span class="w"> </span><span class="o">*</span><span class="w"> </span>y<span class="w"> </span><span class="o">==</span><span class="w"> </span>x<span class="p">;</span>
<span class="kt">definition</span><span class="w"> </span><span class="nf">is_odd</span><span class="p">(</span><span class="kt">uint256</span><span class="w"> </span>x<span class="p">)</span><span class="w"> </span><span class="kr">returns</span><span class="w"> </span><span class="kt">bool</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="o">!</span>is_even<span class="p">(</span>x<span class="p">);</span>
<span class="kt">definition</span><span class="w"> </span><span class="nf">is_odd_no_overflow</span><span class="p">(</span><span class="kt">uint256</span><span class="w"> </span>x<span class="p">)</span><span class="w"> </span><span class="kr">returns</span><span class="w"> </span><span class="kt">bool</span><span class="w"> </span><span class="o">=</span>
<span class="w">    </span>is_odd<span class="p">(</span>x<span class="p">)</span><span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span>x<span class="w"> </span><span class="o">&lt;=</span><span class="w"> </span>MAX_UINT256<span class="p">();</span>
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
<section id="type-error-circular-dependency">
<h3>Type Error circular dependency<a class="headerlink" href="#type-error-circular-dependency" title="Link to this heading"></a></h3>
<p>The following examples would result in a type error due to a circular dependency:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell2"><span></span><span class="c1">// example 1</span>
<span class="c1">// cycle: is_even -&gt; is_odd -&gt; is_even</span>
<span class="kt">definition</span><span class="w"> </span><span class="nf">is_even</span><span class="p">(</span><span class="kt">uint256</span><span class="w"> </span>x<span class="p">)</span><span class="w"> </span><span class="kr">returns</span><span class="w"> </span><span class="kt">bool</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="o">!</span>is_odd<span class="p">(</span>x<span class="p">);</span>
<span class="kt">definition</span><span class="w"> </span><span class="nf">is_odd</span><span class="p">(</span><span class="kt">uint256</span><span class="w"> </span>x<span class="p">)</span><span class="w"> </span><span class="kr">returns</span><span class="w"> </span><span class="kt">bool</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="o">!</span>is_even<span class="p">(</span>x<span class="p">);</span>

<span class="c1">// example 2</span>
<span class="c1">// cycle: circular1-&gt;circular2-&gt;circular3-&gt;circular1</span>
<span class="kt">definition</span><span class="w"> </span><span class="nf">circular1</span><span class="p">(</span><span class="kt">uint</span><span class="w"> </span>x<span class="p">)</span><span class="w"> </span><span class="kr">returns</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span><span class="o">=</span><span class="w"> </span>circular2<span class="p">(</span>x<span class="p">)</span><span class="w"> </span><span class="o">+</span><span class="w"> </span><span class="m m-Decimal">5</span><span class="p">;</span>
<span class="kt">definition</span><span class="w"> </span><span class="nf">circular2</span><span class="p">(</span><span class="kt">uint</span><span class="w"> </span>x<span class="p">)</span><span class="w"> </span><span class="kr">returns</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span><span class="o">=</span><span class="w"> </span>circular3<span class="p">(</span>x<span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="m m-Decimal">2</span><span class="p">)</span><span class="w"> </span><span class="o">+</span><span class="w"> </span><span class="m m-Decimal">7</span><span class="p">;</span>
<span class="kt">definition</span><span class="w"> </span><span class="nf">circular3</span><span class="p">(</span><span class="kt">uint</span><span class="w"> </span>x<span class="p">)</span><span class="w"> </span><span class="kr">returns</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span><span class="o">=</span><span class="w"> </span>circular1<span class="p">(</span>x<span class="p">)</span><span class="w"> </span><span class="o">+</span><span class="w"> </span>circular1<span class="p">(</span>x<span class="p">);</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell2">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
<section id="reference-ghost-functions">
<h3>Reference Ghost Functions<a class="headerlink" href="#reference-ghost-functions" title="Link to this heading"></a></h3>
<p>Definitions may reference ghost functions. This means that definitions are not always “pure” and can affect ghosts, which are considered a “global” construct.</p>
<section id="id2">
<h4>Example:<a class="headerlink" href="#id2" title="Link to this heading"></a></h4>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell3"><span></span><span class="kd">ghost</span><span class="w"> </span><span class="nf">foo</span><span class="p">(</span><span class="kt">uint256</span><span class="p">)</span><span class="w"> </span><span class="kr">returns</span><span class="w"> </span><span class="kt">uint256</span><span class="p">;</span>

<span class="kt">definition</span><span class="w"> </span><span class="nf">is_even</span><span class="p">(</span><span class="kt">uint256</span><span class="w"> </span>x<span class="p">)</span><span class="w"> </span><span class="kr">returns</span><span class="w"> </span><span class="kt">bool</span><span class="w"> </span><span class="o">=</span><span class="w"> </span>x<span class="w"> </span><span class="o">%</span><span class="w"> </span><span class="m m-Decimal">2</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">;</span>
<span class="kt">definition</span><span class="w"> </span><span class="nf">foo_is_even_at</span><span class="p">(</span><span class="kt">uint256</span><span class="w"> </span>x<span class="p">)</span><span class="w"> </span><span class="kr">returns</span><span class="w"> </span><span class="kt">bool</span><span class="w"> </span><span class="o">=</span><span class="w"> </span>is_even<span class="p">(</span>foo<span class="p">(</span>x<span class="p">));</span>

<span class="k">rule</span><span class="w"> </span><span class="nc">rule_assuming_foo_is_even_at</span><span class="p">(</span><span class="kt">uint256</span><span class="w"> </span>x<span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">  </span><span class="kr">require</span><span class="w"> </span>foo_is_even_at<span class="p">(</span>x<span class="p">);</span>
<span class="w">  </span><span class="c1">// ...</span>
<span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell3">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>More interestingly, the two-context version of ghosts can be used in a definition by adding the <code class="docutils literal notranslate"><span class="pre">@new</span></code> or <code class="docutils literal notranslate"><span class="pre">@old</span></code> annotations. If a two-context version is used, the ghost must not be used without an <code class="docutils literal notranslate"><span class="pre">@new</span></code> or <code class="docutils literal notranslate"><span class="pre">@old</span></code> annotation, and the definition must be used in a two-state context for that ghost function (e.g., at the right side of a <code class="docutils literal notranslate"><span class="pre">havoc</span> <span class="pre">assuming</span></code> statement for that ghost).</p>
</section>
<section id="id3">
<h4>Example:<a class="headerlink" href="#id3" title="Link to this heading"></a></h4>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell4"><span></span><span class="kd">ghost</span><span class="w"> </span><span class="nf">foo</span><span class="p">(</span><span class="kt">uint256</span><span class="p">)</span><span class="w"> </span><span class="kr">returns</span><span class="w"> </span><span class="kt">uint256</span><span class="p">;</span>

<span class="kt">definition</span><span class="w"> </span><span class="nf">is_even</span><span class="p">(</span><span class="kt">uint256</span><span class="w"> </span>x<span class="p">)</span><span class="w"> </span><span class="kr">returns</span><span class="w"> </span><span class="kt">bool</span><span class="w"> </span><span class="o">=</span><span class="w"> </span>x<span class="w"> </span><span class="o">%</span><span class="w"> </span><span class="m m-Decimal">2</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">;</span>
<span class="kt">definition</span><span class="w"> </span><span class="nf">foo_add_even</span><span class="p">(</span><span class="kt">uint256</span><span class="w"> </span>x<span class="p">)</span><span class="w"> </span><span class="kr">returns</span><span class="w"> </span><span class="kt">bool</span><span class="w"> </span><span class="o">=</span><span class="w"> </span>is_even<span class="p">(</span>foo<span class="ow">@new</span><span class="p">(</span>x<span class="p">))</span><span class="w"> </span><span class="o">&amp;&amp;</span>
<span class="w">    </span><span class="kr">forall</span><span class="w"> </span><span class="kt">uint256</span><span class="w"> </span>a<span class="p">.</span><span class="w"> </span>is_even<span class="p">(</span>foo<span class="ow">@old</span><span class="p">(</span>x<span class="p">))</span><span class="w"> </span><span class="o">=&gt;</span><span class="w"> </span>is_even<span class="p">(</span>foo<span class="ow">@new</span><span class="p">(</span>x<span class="p">));</span>

<span class="k">rule</span><span class="w"> </span><span class="nc">rule_assuming_old_evens</span><span class="p">(</span><span class="kt">uint256</span><span class="w"> </span>x<span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">  </span><span class="c1">// havoc foo, assuming all old even entries are still even, and that</span>
<span class="w">  </span><span class="c1">// the entry at x is also even</span>
<span class="w">  </span><span class="kr">havoc</span><span class="w"> </span>foo<span class="w"> </span><span class="kr">assuming</span><span class="w"> </span>foo_add_even<span class="p">(</span>x<span class="p">);</span>
<span class="w">  </span><span class="c1">// ...</span>
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
<p><strong>Note:</strong> The type checker will notify you if a two-state version of a variable is used incorrectly.</p>
</section>
</section>
</section>
<section id="filter-example">
<h2>Filter Example<a class="headerlink" href="#filter-example" title="Link to this heading"></a></h2>
<p>The following example introduces a definition called <code class="docutils literal notranslate"><span class="pre">filterDef</span></code>:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell5"><span></span><span class="kt">definition</span><span class="w"> </span><span class="nf">filterDef</span><span class="p">(</span><span class="kt">method</span><span class="w"> </span>f<span class="p">)</span><span class="w"> </span><span class="kr">returns</span><span class="w"> </span><span class="kt">bool</span><span class="w"> </span><span class="o">=</span><span class="w"> </span>f<span class="p">.</span><span class="nb">selector</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="kd">sig</span><span class="o">:</span><span class="nf">someUInt</span><span class="p">().</span><span class="nb">selector</span><span class="p">;</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell5">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>This definition serves as shorthand for <code class="docutils literal notranslate"><span class="pre">f.selector</span> <span class="pre">==</span> <span class="pre">sig:someUInt().selector</span></code> and is used in the filter for the <code class="docutils literal notranslate"><span class="pre">parametricRule</span></code>:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell6"><span></span><span class="k">rule</span><span class="w"> </span><span class="nc">parametricRuleInBase</span><span class="p">(</span><span class="kt">method</span><span class="w"> </span>f<span class="p">)</span><span class="w"> </span><span class="kr">filtered</span><span class="w"> </span><span class="p">{</span><span class="w"> </span>f<span class="w"> </span><span class="o">-&gt;</span><span class="w"> </span>filterDef<span class="p">(</span>f<span class="p">)</span><span class="w">  </span><span class="p">}</span>
<span class="p">{</span>
<span class="w">  </span><span class="c1">// ...</span>
<span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell6">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>This is equivalent to:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell7"><span></span><span class="k">rule</span><span class="w"> </span><span class="nc">parametricRuleInBase</span><span class="p">(</span><span class="kt">method</span><span class="w"> </span>f<span class="p">)</span><span class="w"> </span><span class="kr">filtered</span><span class="w"> </span><span class="p">{</span><span class="w"> </span>f<span class="w"> </span><span class="o">-&gt;</span><span class="w"> </span>f<span class="p">.</span><span class="nb">selector</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="kd">sig</span><span class="o">:</span><span class="nf">someUInt</span><span class="p">().</span><span class="nb">selector</span><span class="w">  </span><span class="p">}</span><span class="w"> </span><span class="p">{</span>
<span class="w">  </span><span class="c1">// ...</span>
<span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell7">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
<section id="syntax">
<h2>Syntax<a class="headerlink" href="#syntax" title="Link to this heading"></a></h2>
<p>The syntax for definitions is given by the following EBNF grammar:</p>
<div class="highlight-default notranslate"><div class="highlight"><pre id="codecell8"><span></span><span class="n">definition</span> <span class="p">:</span><span class="o">:=</span> <span class="p">[</span> <span class="s2">"override"</span> <span class="p">]</span>
               <span class="s2">"definition"</span> <span class="nb">id</span> <span class="p">[</span> <span class="s2">"("</span> <span class="n">params</span> <span class="s2">")"</span> <span class="p">]</span>
               <span class="s2">"returns"</span> <span class="n">cvl_type</span>
               <span class="s2">"="</span> <span class="n">expression</span> <span class="s2">";"</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell8">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>See <a class="reference internal" href="types.html"><span class="doc">Types</span></a>, <a class="reference internal" href="expr.html"><span class="doc">Expressions</span></a>, and <a class="reference internal" href="basics.html#identifiers"><span class="std std-ref">Identifiers</span></a> for descriptions of the <code class="docutils literal notranslate"><span class="pre">cvl_type</span></code>, <code class="docutils literal notranslate"><span class="pre">expression</span></code>, and <code class="docutils literal notranslate"><span class="pre">id</span></code> productions, respectively.</p>
<p>In this syntax, the <code class="docutils literal notranslate"><span class="pre">definition</span></code> keyword is followed by the definition’s identifier (<code class="docutils literal notranslate"><span class="pre">id</span></code>). Parameters can be specified in parentheses, and the return type is declared using the <code class="docutils literal notranslate"><span class="pre">returns</span></code> keyword. The body of the definition is provided after the equal sign (<code class="docutils literal notranslate"><span class="pre">=</span></code>) and should end with a semicolon (<code class="docutils literal notranslate"><span class="pre">;</span></code>).</p>
</section>
</section>


           </div>
          </div>
          <footer><div class="rst-footer-buttons" role="navigation" aria-label="Footer">
        <a href="ghosts.html" class="btn btn-neutral float-left" title="Ghosts" accesskey="p" rel="prev"><span class="fa fa-arrow-circle-left" aria-hidden="true"></span> Previous</a>
        <a href="hooks.html" class="btn btn-neutral float-right" title="Hooks" accesskey="n" rel="next">Next <span class="fa fa-arrow-circle-right" aria-hidden="true"></span></a>
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