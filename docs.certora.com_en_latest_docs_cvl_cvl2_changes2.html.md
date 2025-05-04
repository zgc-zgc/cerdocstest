<!DOCTYPE html><html class="writer-html5" lang="en" data-content_root="../../../"><head>
  <meta charset="utf-8"><meta name="viewport" content="width=device-width, initial-scale=1">

  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Changes Introduced in CVL 2 — Certora Prover Documentation 0.0 documentation</title>
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
    <link rel="next" title="CVL2 Migration Guide" href="migration.html">
    <link rel="prev" title="Foundry Integration (Alpha)" href="../foundry-integration.html"> 
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
<li class="toctree-l1 current" aria-expanded="true"><a class="reference internal" href="../index.html"><button class="toctree-expand" title="Open/close menu"></button>The Certora Verification Language</a><ul class="" aria-expanded="false">
<li class="toctree-l2"><a class="reference internal" href="../overview.html">Specification Files</a></li>
<li class="toctree-l2"><a class="reference internal" href="../basics.html">Basic Syntax</a></li>
<li class="toctree-l2"><a class="reference internal" href="../types.html">Types</a></li>
<li class="toctree-l2"><a class="reference internal" href="../expr.html">Expressions</a></li>
<li class="toctree-l2"><a class="reference internal" href="../statements.html">Statements</a></li>
<li class="toctree-l2"><a class="reference internal" href="../imports.html">Import and Use Statements</a></li>
<li class="toctree-l2"><a class="reference internal" href="../using.html">Using Statements</a></li>
<li class="toctree-l2"><a class="reference internal" href="../methods.html">The Methods Block</a></li>
<li class="toctree-l2"><a class="reference internal" href="../rules.html">Rules</a></li>
<li class="toctree-l2"><a class="reference internal" href="../builtin.html">Built-in Rules</a></li>
<li class="toctree-l2"><a class="reference internal" href="../functions.html">Functions</a></li>
<li class="toctree-l2"><a class="reference internal" href="../invariants.html">Invariants</a></li>
<li class="toctree-l2"><a class="reference internal" href="../sorts.html">Uninterpreted Sorts</a></li>
<li class="toctree-l2"><a class="reference internal" href="../ghosts.html">Ghosts</a></li>
<li class="toctree-l2"><a class="reference internal" href="../defs.html">Definitions</a></li>
<li class="toctree-l2"><a class="reference internal" href="../hooks.html">Hooks</a></li>
<li class="toctree-l2"><a class="reference internal" href="../transient.html">Transient Storage</a></li>
<li class="toctree-l2"><a class="reference internal" href="../foundry-integration.html">Foundry Integration (Alpha)</a></li>
<li class="toctree-l2 current" aria-expanded="true"><a class="reference internal" href="../index.html#changes-since-cvl-1"><button class="toctree-expand" title="Open/close menu"></button>Changes Since CVL 1</a><ul class="" aria-expanded="false">
<li class="toctree-l3 current" aria-expanded="true"><a class="reference internal current" href="#" aria-expanded="true"><button class="toctree-expand" title="Open/close menu"></button>Changes Introduced in CVL 2</a><ul>
<li class="toctree-l4"><a class="reference internal" href="#superficial-syntax-changes">Superficial syntax changes</a></li>
<li class="toctree-l4"><a class="reference internal" href="#changes-to-methods-block-entries">Changes to methods block entries</a></li>
<li class="toctree-l4"><a class="reference internal" href="#changes-to-integer-types">Changes to integer types</a></li>
<li class="toctree-l4"><a class="reference internal" href="#changes-to-the-fallback-function">Changes to the fallback function</a></li>
<li class="toctree-l4"><a class="reference internal" href="#removed-features">Removed features</a></li>
<li class="toctree-l4"><a class="reference internal" href="#changes-to-the-command-line-interface-cli">Changes to the Command Line Interface (CLI)</a></li>
</ul>
</li>
<li class="toctree-l3"><a class="reference internal" href="migration.html">CVL2 Migration Guide</a></li>
<li class="toctree-l3"><a class="reference internal" href="../v5-changes.html">Certora CLI 5.0 Changes</a></li>
</ul>
</li>
</ul>
</li>
<li class="toctree-l1"><a class="reference internal" href="../../prover/index.html">The Certora Prover</a></li>
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
          <li class="breadcrumb-item"><a href="../index.html">The Certora Verification Language</a></li>
      <li class="breadcrumb-item active">Changes Introduced in CVL 2</li>
      <li class="wy-breadcrumbs-aside">
            <a href="../../../_sources/docs/cvl/cvl2/changes.md.txt" rel="nofollow"> View page source</a>
      </li>
  </ul>
  <hr>
</div>
          <div role="main" class="document" itemscope="itemscope" itemtype="http://schema.org/Article">
           <div itemprop="articleBody">
             
  <section id="changes-introduced-in-cvl-2">
<h1><a class="toc-backref" href="#id2" role="doc-backlink">Changes Introduced in CVL 2</a><a class="headerlink" href="#changes-introduced-in-cvl-2" title="Link to this heading"></a></h1>
<p>CVL 2 is a major overhaul to the type system of CVL. Though many
of the changes are internal, we wanted to take this opportunity to
introduce a few improvements to the syntax.  The general goal of these changes
is to make the behavior of CVL more explicit and predictable, and to bring the
syntax more in line with Solidity’s syntax.</p>
<p>This document summarizes the changes to CVL syntax introduced by CVL 2.</p>
<p>The <code class="docutils literal notranslate"><span class="pre">CVLMigration</span></code> repository contains examples demonstrating each of the
changes; the <code class="docutils literal notranslate"><span class="pre">cvl1</span></code> branch contains the examples in valid CVL 1 syntax, while
the <code class="docutils literal notranslate"><span class="pre">cvl2</span></code> branch contains the same examples in CVL 2 syntax.  You can see the
differences <a class="reference external" href="https://github.com/Certora/CVL2Migration/compare/cvl1..cvl2?diff=split">here</a>, our you can clone <a class="reference external" href="https://github.com/Certora/CVL2Migration">the
repository</a> and compare the <code class="docutils literal notranslate"><span class="pre">cvl1</span></code> and <code class="docutils literal notranslate"><span class="pre">cvl2</span></code> branches using
your favorite tools.</p>
<nav class="contents" id="contents">
<p class="topic-title">Contents</p>
<ul class="simple">
<li><p><a class="reference internal" href="#changes-introduced-in-cvl-2" id="id2">Changes Introduced in CVL 2</a></p>
<ul>
<li><p><a class="reference internal" href="#superficial-syntax-changes" id="id3">Superficial syntax changes</a></p>
<ul>
<li><p><a class="reference internal" href="#function-and-required-for-methods-block-entries" id="id4"><code class="docutils literal notranslate"><span class="pre">function</span></code> and <code class="docutils literal notranslate"><span class="pre">;</span></code> required for methods block entries</a></p></li>
<li><p><a class="reference internal" href="#required-in-more-places" id="id5">Required <code class="docutils literal notranslate"><span class="pre">;</span></code> in more places</a></p></li>
<li><p><a class="reference internal" href="#method-literals-require-sig" id="id6">Method literals require <code class="docutils literal notranslate"><span class="pre">sig:</span></code></a></p></li>
<li><p><a class="reference internal" href="#use-of-contract-name-instead-of-using-variable" id="id7">Use of contract name instead of <code class="docutils literal notranslate"><span class="pre">using</span></code> variable</a></p></li>
<li><p><a class="reference internal" href="#rules-must-start-with-rule" id="id8">Rules must start with <code class="docutils literal notranslate"><span class="pre">rule</span></code></a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#changes-to-methods-block-entries" id="id9">Changes to methods block entries</a></p>
<ul>
<li><p><a class="reference internal" href="#most-solidity-types-allowed-as-arguments" id="id10">Most Solidity types allowed as arguments</a></p></li>
<li><p><a class="reference internal" href="#required-internal-or-external-annotation" id="id11">Required <code class="docutils literal notranslate"><span class="pre">internal</span></code> or <code class="docutils literal notranslate"><span class="pre">external</span></code> annotation</a></p></li>
<li><p><a class="reference internal" href="#optional-methods-block-entries" id="id12"><code class="docutils literal notranslate"><span class="pre">optional</span></code> methods block entries</a></p></li>
<li><p><a class="reference internal" href="#required-calldata-memory-or-storage-annotations-for-reference-types" id="id13">Required <code class="docutils literal notranslate"><span class="pre">calldata</span></code>, <code class="docutils literal notranslate"><span class="pre">memory</span></code>, or <code class="docutils literal notranslate"><span class="pre">storage</span></code> annotations for reference types</a></p></li>
<li><p><a class="reference internal" href="#summaries-only-apply-to-one-contract-by-default" id="id14">Summaries only apply to one contract by default</a></p></li>
<li><p><a class="reference internal" href="#requirements-on-returns" id="id15">Requirements on <code class="docutils literal notranslate"><span class="pre">returns</span></code></a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#changes-to-integer-types" id="id16">Changes to integer types</a></p>
<ul>
<li><p><a class="reference internal" href="#mathematical-operations-return-mathint" id="id17">Mathematical operations return <code class="docutils literal notranslate"><span class="pre">mathint</span></code></a></p></li>
<li><p><a class="reference internal" href="#implicit-and-explicit-casting" id="id18">Implicit and explicit casting</a></p></li>
<li><p><a class="reference internal" href="#casting-enums-to-integer-types" id="id19">Casting enums to integer types</a></p></li>
<li><p><a class="reference internal" href="#casting-addresses-to-bytes32" id="id20">Casting addresses to bytes32</a></p></li>
<li><p><a class="reference internal" href="#modulo-operator-always-returns-non-negative-values" id="id21">Modulo operator <code class="docutils literal notranslate"><span class="pre">%</span></code> always returns non-negative values</a></p></li>
<li><p><a class="reference internal" href="#support-for-bytes1-bytes32" id="id22">Support for <code class="docutils literal notranslate"><span class="pre">bytes1</span></code>…<code class="docutils literal notranslate"><span class="pre">bytes32</span></code></a></p></li>
<li><p><a class="reference internal" href="#changes-for-bitwise-operations" id="id23">Changes for bitwise operations</a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#changes-to-the-fallback-function" id="id24">Changes to the fallback function</a></p></li>
<li><p><a class="reference internal" href="#removed-features" id="id25">Removed features</a></p>
<ul>
<li><p><a class="reference internal" href="#methods-entries-for-sighashes" id="id26">Methods entries for sighashes</a></p></li>
<li><p><a class="reference internal" href="#invoke-sinvoke-and-call" id="id27"><code class="docutils literal notranslate"><span class="pre">invoke</span></code>, <code class="docutils literal notranslate"><span class="pre">sinvoke</span></code>, and <code class="docutils literal notranslate"><span class="pre">call</span></code></a></p></li>
<li><p><a class="reference internal" href="#static-assert-and-static-require" id="id28"><code class="docutils literal notranslate"><span class="pre">static_assert</span></code> and <code class="docutils literal notranslate"><span class="pre">static_require</span></code></a></p></li>
<li><p><a class="reference internal" href="#invoke-fallback-and-certorafallback" id="id29"><code class="docutils literal notranslate"><span class="pre">invoke_fallback</span></code> and <code class="docutils literal notranslate"><span class="pre">certorafallback()</span></code></a></p></li>
<li><p><a class="reference internal" href="#invoke-whole" id="id30"><code class="docutils literal notranslate"><span class="pre">invoke_whole</span></code></a></p></li>
<li><p><a class="reference internal" href="#havocing-local-variables" id="id31">Havocing local variables</a></p></li>
<li><p><a class="reference internal" href="#destructuring-syntax-for-struct-returns" id="id32">Destructuring syntax for struct returns</a></p></li>
<li><p><a class="reference internal" href="#bytes-and-string" id="id33"><code class="docutils literal notranslate"><span class="pre">bytes[]</span></code> and <code class="docutils literal notranslate"><span class="pre">string[]</span></code></a></p></li>
<li><p><a class="reference internal" href="#pragma" id="id34"><code class="docutils literal notranslate"><span class="pre">pragma</span></code></a></p></li>
<li><p><a class="reference internal" href="#events" id="id35"><code class="docutils literal notranslate"><span class="pre">events</span></code></a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#changes-to-the-command-line-interface-cli" id="id36">Changes to the Command Line Interface (CLI)</a></p>
<ul>
<li><p><a class="reference internal" href="#flags-renaming" id="id37">Flags Renaming</a></p></li>
<li><p><a class="reference internal" href="#prover-args" id="id38"><code class="docutils literal notranslate"><span class="pre">Prover</span> <span class="pre">Args</span></code></a></p></li>
<li><p><a class="reference internal" href="#solidity-compiler-args" id="id39"><code class="docutils literal notranslate"><span class="pre">Solidity</span> <span class="pre">Compiler</span> <span class="pre">Args</span></code></a></p></li>
<li><p><a class="reference internal" href="#enhanced-server-support" id="id40">Enhanced server support</a></p></li>
</ul>
</li>
</ul>
</li>
</ul>
</nav>
<section id="superficial-syntax-changes">
<span id="cvl2-superficial-syntax-changes"></span><h2><a class="toc-backref" href="#id3" role="doc-backlink">Superficial syntax changes</a><a class="headerlink" href="#superficial-syntax-changes" title="Link to this heading"></a></h2>
<p>There are several simple changes to the syntax to make specs more uniform and
consistent, and to reduce the superficial differences with Solidity.</p>
<section id="function-and-required-for-methods-block-entries">
<h3><a class="toc-backref" href="#id4" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">function</span></code> and <code class="docutils literal notranslate"><span class="pre">;</span></code> required for methods block entries</a><a class="headerlink" href="#function-and-required-for-methods-block-entries" title="Link to this heading"></a></h3>
<p>In CVL 2, methods block entries must now start with <code class="docutils literal notranslate"><span class="pre">function</span></code> and end with
<code class="docutils literal notranslate"><span class="pre">;</span></code> (semicolons were optional in CVL 1).  For example
(<a class="reference external" href="https://github.com/Certora/CVL2Migration/blob/cvl1/certora/spec/MethodsEntries.spec">CVL 1</a>, <a class="reference external" href="https://github.com/Certora/CVL2Migration/blob/cvl2/certora/spec/MethodsEntries.spec">CVL 2</a>, <a class="reference external" href="https://github.com/Certora/CVL2Migration/compare/cvl1..cvl2?diff=split#diff-9cd1ae6f2c8146e323568cb25c79d4f6671fcb690872dce33591bd514759fc24">diff</a>):</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell0"><span></span>transferFrom<span class="p">(</span><span class="kt">address</span><span class="p">,</span><span class="w"> </span><span class="kt">address</span><span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="p">)</span><span class="w"> </span><span class="kr">returns</span><span class="p">(</span><span class="kt">bool</span><span class="p">)</span><span class="w"> </span><span class="kr">envfree</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell0">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>will become</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell1"><span></span><span class="kt">function</span><span class="w"> </span><span class="nf">transferFrom</span><span class="p">(</span><span class="kt">address</span><span class="p">,</span><span class="w"> </span><span class="kt">address</span><span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="p">)</span><span class="w"> </span><span class="kr">external</span><span class="w"> </span><span class="kr">returns</span><span class="p">(</span><span class="kt">bool</span><span class="p">)</span><span class="w"> </span><span class="kr">envfree</span><span class="p">;</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell1">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>(note also the addition of <code class="docutils literal notranslate"><span class="pre">external</span></code>, <a class="reference internal" href="#cvl2-visibility"><span class="std std-ref">described below</span></a>).</p>
<p>This is also true for entries with summaries:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell2"><span></span>balanceOf<span class="p">(</span><span class="kt">address</span><span class="p">)</span><span class="w"> </span><span class="kr">returns</span><span class="p">(</span><span class="kt">uint256</span><span class="p">)</span><span class="w"> </span><span class="o">=&gt;</span><span class="w"> </span>ALWAYS<span class="p">(</span><span class="m m-Decimal">3</span><span class="p">)</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell2">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>will become</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell3"><span></span><span class="kt">function</span><span class="w"> </span><span class="nf">balanceOf</span><span class="p">(</span><span class="kt">address</span><span class="p">)</span><span class="w"> </span><span class="kr">external</span><span class="w"> </span><span class="kr">returns</span><span class="p">(</span><span class="kt">uint256</span><span class="p">)</span><span class="w"> </span><span class="o">=&gt;</span><span class="w"> </span>ALWAYS<span class="p">(</span><span class="m m-Decimal">3</span><span class="p">);</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell3">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>If you do not change this, you will get an error message like the following:</p>
<div class="highlight-default notranslate"><div class="highlight"><pre id="codecell4"><span></span><span class="n">CRITICAL</span><span class="p">:</span> <span class="p">[</span><span class="n">main</span><span class="p">]</span> <span class="n">ERROR</span> <span class="n">ALWAYS</span> <span class="o">-</span> <span class="n">certora</span><span class="o">/</span><span class="n">spec</span><span class="o">/</span><span class="n">MethodsEntries</span><span class="o">.</span><span class="n">spec</span><span class="p">:</span><span class="mi">4</span><span class="p">:</span><span class="mi">5</span><span class="p">:</span> <span class="n">Syntax</span> <span class="n">error</span><span class="p">:</span> <span class="n">unexpected</span> <span class="n">token</span> <span class="n">near</span> <span class="n">ID</span><span class="p">(</span><span class="n">transferFrom</span><span class="p">)</span>
<span class="n">CRITICAL</span><span class="p">:</span> <span class="p">[</span><span class="n">main</span><span class="p">]</span> <span class="n">ERROR</span> <span class="n">ALWAYS</span> <span class="o">-</span> <span class="n">certora</span><span class="o">/</span><span class="n">spec</span><span class="o">/</span><span class="n">MethodsEntries</span><span class="o">.</span><span class="n">spec</span><span class="p">:</span><span class="mi">4</span><span class="p">:</span><span class="mi">5</span><span class="p">:</span> <span class="n">Couldn</span><span class="s1">'t repair and continue parse unexpected token near ID(transferFrom)</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell4">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
<section id="required-in-more-places">
<h3><a class="toc-backref" href="#id5" role="doc-backlink">Required <code class="docutils literal notranslate"><span class="pre">;</span></code> in more places</a><a class="headerlink" href="#required-in-more-places" title="Link to this heading"></a></h3>
<p><code class="docutils literal notranslate"><span class="pre">using</span></code>, <code class="docutils literal notranslate"><span class="pre">import</span></code>, <code class="docutils literal notranslate"><span class="pre">use</span></code>, and <code class="docutils literal notranslate"><span class="pre">invariant</span></code> statements all require a <code class="docutils literal notranslate"><span class="pre">;</span></code> at the
end.  For example
(<a class="reference external" href="https://github.com/Certora/CVL2Migration/blob/cvl1/certora/spec/Semicolons.spec">CVL 1</a>, <a class="reference external" href="https://github.com/Certora/CVL2Migration/blob/cvl2/certora/spec/Semicolons.spec">CVL 2</a>, <a class="reference external" href="https://github.com/Certora/CVL2Migration/compare/cvl1..cvl2?diff=split#diff-15fb1ef5e6524f8a661d83ae5160b6b072840c5c54bf8d07733aab32b9da73f7">diff</a>):</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell5"><span></span><span class="k">invariant</span><span class="w"> </span><span class="nc">balanceOfZeroIsZero</span><span class="p">()</span>
<span class="w">    </span>balanceOf<span class="p">(</span><span class="m m-Decimal">0</span><span class="p">)</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="m m-Decimal">0</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell5">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>becomes</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell6"><span></span><span class="k">invariant</span><span class="w"> </span><span class="nc">balanceOfZeroIsZero</span><span class="p">()</span>
<span class="w">    </span>balanceOf<span class="p">(</span><span class="m m-Decimal">0</span><span class="p">)</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">;</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell6">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p><code class="docutils literal notranslate"><span class="pre">use</span></code> and <code class="docutils literal notranslate"><span class="pre">invariant</span></code> statements do not require (and may not have) a semicolon
if they are followed by a <code class="docutils literal notranslate"><span class="pre">preserved</span></code> or <code class="docutils literal notranslate"><span class="pre">filtered</span></code> block.  For example, the
following is valid in both CVL 1 and CVL 2:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell7"><span></span><span class="k">invariant</span><span class="w"> </span><span class="nc">totalSupplyBoundsBalance</span><span class="p">(</span><span class="kt">address</span><span class="w"> </span>a<span class="p">)</span>
<span class="w">    </span>balanceOf<span class="p">(</span>a<span class="p">)</span><span class="w"> </span><span class="o">&lt;=</span><span class="w"> </span>totalSupply<span class="p">()</span>
<span class="w">    </span><span class="p">{</span><span class="w"> </span><span class="kr">preserved</span><span class="w"> </span><span class="p">{</span><span class="w"> </span><span class="kr">require</span><span class="w"> </span><span class="kr">false</span><span class="p">;</span><span class="w"> </span><span class="p">}</span><span class="w"> </span><span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell7">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>If you do not change this, you will see an error like the following:</p>
<div class="highlight-default notranslate"><div class="highlight"><pre id="codecell8"><span></span><span class="n">CRITICAL</span><span class="p">:</span> <span class="p">[</span><span class="n">main</span><span class="p">]</span> <span class="n">ERROR</span> <span class="n">ALWAYS</span> <span class="o">-</span> <span class="n">certora</span><span class="o">/</span><span class="n">spec</span><span class="o">/</span><span class="n">Semicolons</span><span class="o">.</span><span class="n">spec</span><span class="p">:</span><span class="mi">5</span><span class="p">:</span><span class="mi">1</span><span class="p">:</span> <span class="n">Syntax</span> <span class="n">error</span><span class="p">:</span> <span class="n">unexpected</span> <span class="n">token</span> <span class="n">near</span> <span class="n">using</span>
<span class="n">CRITICAL</span><span class="p">:</span> <span class="p">[</span><span class="n">main</span><span class="p">]</span> <span class="n">ERROR</span> <span class="n">ALWAYS</span> <span class="o">-</span> <span class="n">certora</span><span class="o">/</span><span class="n">spec</span><span class="o">/</span><span class="n">Semicolons</span><span class="o">.</span><span class="n">spec</span><span class="p">:</span><span class="mi">5</span><span class="p">:</span><span class="mi">1</span><span class="p">:</span> <span class="n">Couldn</span><span class="s1">'t repair and continue parse unexpected token near using</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell8">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
<section id="method-literals-require-sig">
<h3><a class="toc-backref" href="#id6" role="doc-backlink">Method literals require <code class="docutils literal notranslate"><span class="pre">sig:</span></code></a><a class="headerlink" href="#method-literals-require-sig" title="Link to this heading"></a></h3>
<p>In some places in CVL, you can refer to a contract method by its name and
argument types.  For example, you might write
(<a class="reference external" href="https://github.com/Certora/CVL2Migration/blob/cvl1/certora/spec/MethodLiterals.spec">CVL 1</a>, <a class="reference external" href="https://github.com/Certora/CVL2Migration/blob/cvl2/certora/spec/MethodLiterals.spec">CVL 2</a>, <a class="reference external" href="https://github.com/Certora/CVL2Migration/compare/cvl1..cvl2?diff=split#diff-41df8240fa5faa12531baa82863891b94abf3fb3b859bdd10bafde73b60eda5d">diff</a>):</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell9"><span></span>f<span class="p">.</span><span class="nb">selector</span><span class="w"> </span><span class="o">==</span><span class="w"> </span>approve<span class="p">(</span><span class="kt">address</span><span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="p">).</span><span class="nb">selector</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell9">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>In this example, <code class="docutils literal notranslate"><span class="pre">approve(address,uint)</span></code> is a <em>method literal</em>.  In CVL 2,
these methods literals must now start with <code class="docutils literal notranslate"><span class="pre">sig:</span></code>.  For example, the above
would become:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell10"><span></span>f<span class="p">.</span><span class="nb">selector</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="kd">sig</span><span class="o">:</span><span class="nf">approve</span><span class="p">(</span><span class="kt">address</span><span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="p">).</span><span class="nb">selector</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell10">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>If you do not change this, you will see the following error:</p>
<div class="highlight-default notranslate"><div class="highlight"><pre id="codecell11"><span></span><span class="n">Error</span><span class="p">:</span> <span class="n">Error</span> <span class="ow">in</span> <span class="n">spec</span> <span class="n">file</span> <span class="p">(</span><span class="n">MethodLiterals</span><span class="o">.</span><span class="n">spec</span><span class="p">:</span><span class="mi">14</span><span class="p">:</span><span class="mi">5</span><span class="p">):</span> <span class="n">Variable</span> <span class="n">address</span> <span class="ow">is</span> <span class="n">undefined</span> <span class="p">(</span><span class="n">first</span> <span class="n">instance</span> <span class="n">only</span> <span class="n">reported</span><span class="p">)</span>
<span class="n">Error</span><span class="p">:</span> <span class="n">Error</span> <span class="ow">in</span> <span class="n">spec</span> <span class="n">file</span> <span class="p">(</span><span class="n">MethodLiterals</span><span class="o">.</span><span class="n">spec</span><span class="p">:</span><span class="mi">14</span><span class="p">:</span><span class="mi">5</span><span class="p">):</span> <span class="n">Variable</span> <span class="n">uint</span> <span class="ow">is</span> <span class="n">undefined</span> <span class="p">(</span><span class="n">first</span> <span class="n">instance</span> <span class="n">only</span> <span class="n">reported</span><span class="p">)</span>
<span class="n">Error</span><span class="p">:</span> <span class="n">Error</span> <span class="ow">in</span> <span class="n">spec</span> <span class="n">file</span> <span class="p">(</span><span class="n">MethodLiterals</span><span class="o">.</span><span class="n">spec</span><span class="p">:</span><span class="mi">15</span><span class="p">:</span><span class="mi">34</span><span class="p">):</span> <span class="n">could</span> <span class="ow">not</span> <span class="nb">type</span> <span class="n">expression</span> <span class="s2">"address"</span><span class="p">,</span> <span class="n">message</span><span class="p">:</span> <span class="n">unknown</span> <span class="n">variable</span> <span class="s2">"address"</span>
<span class="n">Error</span><span class="p">:</span> <span class="n">Error</span> <span class="ow">in</span> <span class="n">spec</span> <span class="n">file</span> <span class="p">(</span><span class="n">MethodLiterals</span><span class="o">.</span><span class="n">spec</span><span class="p">:</span><span class="mi">15</span><span class="p">:</span><span class="mi">43</span><span class="p">):</span> <span class="n">could</span> <span class="ow">not</span> <span class="nb">type</span> <span class="n">expression</span> <span class="s2">"uint"</span><span class="p">,</span> <span class="n">message</span><span class="p">:</span> <span class="n">unknown</span> <span class="n">variable</span> <span class="s2">"uint"</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell11">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
<section id="use-of-contract-name-instead-of-using-variable">
<h3><a class="toc-backref" href="#id7" role="doc-backlink">Use of contract name instead of <code class="docutils literal notranslate"><span class="pre">using</span></code> variable</a><a class="headerlink" href="#use-of-contract-name-instead-of-using-variable" title="Link to this heading"></a></h3>
<p>In CVL 1, the only way to refer to a contract in the <a class="reference internal" href="../../user-guide/glossary.html#term-0"><span class="xref std std-term">scene</span></a> was to first
introduce a contract instance variable with a <code class="docutils literal notranslate"><span class="pre">using</span></code> statement, and then use
that variable.  For example, to access a struct type <code class="docutils literal notranslate"><span class="pre">S</span></code> defined in
<code class="docutils literal notranslate"><span class="pre">PrimaryContract.sol</span></code>, you would need to write
(<a class="reference external" href="https://github.com/Certora/CVL2Migration/blob/cvl1/certora/spec/ContractNames.spec">CVL 1</a>, <a class="reference external" href="https://github.com/Certora/CVL2Migration/blob/cvl2/certora/spec/ContractNames.spec">CVL 2</a>, <a class="reference external" href="https://github.com/Certora/CVL2Migration/compare/cvl1..cvl2?diff=split#diff-a6a2974b81074e87d755753c2e84ef1b0cb553bfdeb729827959e0c63f0d02d7">diff</a>):</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell12"><span></span><span class="kn">using</span><span class="w"> </span>PrimaryContract<span class="w"> </span><span class="kn">as</span><span class="w"> </span>primary<span class="p">;</span>

<span class="k">rule</span><span class="w"> </span><span class="nc">structExample</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span>primary<span class="p">.</span>S<span class="w"> </span>x<span class="p">;</span>
<span class="w">    </span><span class="p">...</span>
<span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell12">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>In CVL 2, you must now use the name of the contract, rather than the instance
variable, when referring to user-defined types.  The above example would now be
written</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell13"><span></span><span class="k">rule</span><span class="w"> </span><span class="nc">structExample</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span>PrimaryContract<span class="p">.</span>S<span class="w"> </span>x<span class="p">;</span>
<span class="w">    </span><span class="p">...</span>
<span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell13">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>There is no need for a <code class="docutils literal notranslate"><span class="pre">using</span></code> statement in this example.</p>
<p>If you don’t change this, you will an error like the following:</p>
<div class="highlight-default notranslate"><div class="highlight"><pre id="codecell14"><span></span><span class="n">Error</span><span class="p">:</span> <span class="n">Error</span> <span class="ow">in</span> <span class="n">spec</span> <span class="n">file</span> <span class="p">(</span><span class="n">ContractNames</span><span class="o">.</span><span class="n">spec</span><span class="p">:</span><span class="mi">12</span><span class="p">:</span><span class="mi">19</span><span class="p">):</span> <span class="n">Contract</span> <span class="n">name</span> <span class="n">primary</span> <span class="n">does</span> <span class="ow">not</span> <span class="n">exist</span> <span class="ow">in</span> <span class="n">the</span> <span class="n">scene</span><span class="o">.</span> <span class="n">Make</span> <span class="n">sure</span> <span class="n">you</span> <span class="n">are</span> <span class="n">using</span> <span class="n">a</span> <span class="n">contract</span> <span class="n">name</span> <span class="ow">and</span> <span class="ow">not</span> <span class="n">a</span> <span class="n">contract</span> <span class="n">instance</span> <span class="n">name</span><span class="o">.</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell14">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>Calling methods on secondary contracts still requires using a contract instance
variable:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell15"><span></span><span class="kn">using</span><span class="w"> </span>SecondaryContract<span class="w"> </span><span class="kn">as</span><span class="w"> </span>secondary<span class="p">;</span>

<span class="k">rule</span><span class="w"> </span><span class="nc">multicontractExample</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="p">...</span>
<span class="w">    </span>secondary<span class="p">.</span>balanceOf<span class="p">(</span><span class="m m-Decimal">0</span><span class="p">);</span>
<span class="w">    </span><span class="p">...</span>
<span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell15">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>Entries in the <code class="docutils literal notranslate"><span class="pre">methods</span></code> block may use either the contract name or an instance
variable:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell16"><span></span><span class="kn">using</span><span class="w"> </span>SecondaryContract<span class="w"> </span><span class="kn">as</span><span class="w"> </span>secondary<span class="p">;</span>

<span class="kr">methods</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="c1">//// both are valid (and the effect is the same):</span>
<span class="w">    </span>secondary<span class="p">.</span>balanceOf<span class="p">(</span><span class="kt">address</span><span class="p">)</span><span class="w"> </span><span class="kr">returns</span><span class="p">(</span><span class="kt">uint</span><span class="p">)</span><span class="w"> </span><span class="kr">envfree</span>
<span class="w">    </span>SecondaryContract<span class="p">.</span>transfer<span class="p">(</span><span class="kt">address</span><span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="p">)</span><span class="w"> </span><span class="kr">returns</span><span class="p">(</span><span class="kt">bool</span><span class="p">)</span><span class="w"> </span><span class="kr">envfree</span>
<span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell16">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>Using the contract name in the methods block currently has the same effect as
using an instance variable; this may change in future versions of CVL.</p>
</section>
<section id="rules-must-start-with-rule">
<h3><a class="toc-backref" href="#id8" role="doc-backlink">Rules must start with <code class="docutils literal notranslate"><span class="pre">rule</span></code></a><a class="headerlink" href="#rules-must-start-with-rule" title="Link to this heading"></a></h3>
<p>In CVL 1, you could omit the keyword <code class="docutils literal notranslate"><span class="pre">rule</span></code> when writing rules
(<a class="reference external" href="https://github.com/Certora/CVL2Migration/blob/cvl1/certora/spec/RuleKeyword.spec">CVL 1</a>, <a class="reference external" href="https://github.com/Certora/CVL2Migration/blob/cvl2/certora/spec/RuleKeyword.spec">CVL 2</a>, <a class="reference external" href="https://github.com/Certora/CVL2Migration/compare/cvl1..cvl2?diff=split#diff-b39a57bffd39f86bc1f9555a487af389f501eab9e66a1c3059a89691319da248">diff</a>):</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell17"><span></span>transferReverts<span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="p">...</span>
<span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell17">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>In CVL 2, the <code class="docutils literal notranslate"><span class="pre">rule</span></code> keyword is no longer optional:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell18"><span></span><span class="k">rule</span><span class="w"> </span><span class="nc">transferReverts</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="p">...</span>
<span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell18">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>If you don’t change this, you will receive an error like the following:</p>
<div class="highlight-default notranslate"><div class="highlight"><pre id="codecell19"><span></span><span class="n">CRITICAL</span><span class="p">:</span> <span class="p">[</span><span class="n">main</span><span class="p">]</span> <span class="n">ERROR</span> <span class="n">ALWAYS</span> <span class="o">-</span> <span class="n">certora</span><span class="o">/</span><span class="n">spec</span><span class="o">/</span><span class="n">RuleKeyword</span><span class="o">.</span><span class="n">spec</span><span class="p">:</span><span class="mi">3</span><span class="p">:</span><span class="mi">1</span><span class="p">:</span> <span class="n">Syntax</span> <span class="n">error</span><span class="p">:</span> <span class="n">unexpected</span> <span class="n">token</span> <span class="n">near</span> <span class="n">ID</span><span class="p">(</span><span class="n">transferReverts</span><span class="p">)</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell19">
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
<section id="changes-to-methods-block-entries">
<span id="cvl2-methods-blocks"></span><h2><a class="toc-backref" href="#id9" role="doc-backlink">Changes to methods block entries</a><a class="headerlink" href="#changes-to-methods-block-entries" title="Link to this heading"></a></h2>
<p>In addition to the superficial changes listed above, there are some changes to
the way that methods block entries can be written (there are also a
<a class="reference internal" href="#cvl2-wildcards"><span class="std std-ref">few instances</span></a> where the meanings of entries has
changed).  In CVL 1, <code class="docutils literal notranslate"><span class="pre">methods</span></code> block entries often had several different
functions and meanings:</p>
<ul class="simple">
<li><p>They were used to indicate targets for summarization</p></li>
<li><p>They were used to write generic specs that could apply to contracts with
missing methods</p></li>
<li><p>They were used to declare targets <code class="docutils literal notranslate"><span class="pre">envfree</span></code></p></li>
</ul>
<p>The changes described in this section make these different uses more explicit:</p>
<nav class="contents local" id="id1">
<ul class="simple">
<li><p><a class="reference internal" href="#most-solidity-types-allowed-as-arguments" id="id41">Most Solidity types allowed as arguments</a></p></li>
<li><p><a class="reference internal" href="#required-internal-or-external-annotation" id="id42">Required <code class="docutils literal notranslate"><span class="pre">internal</span></code> or <code class="docutils literal notranslate"><span class="pre">external</span></code> annotation</a></p></li>
<li><p><a class="reference internal" href="#optional-methods-block-entries" id="id43"><code class="docutils literal notranslate"><span class="pre">optional</span></code> methods block entries</a></p></li>
<li><p><a class="reference internal" href="#required-calldata-memory-or-storage-annotations-for-reference-types" id="id44">Required <code class="docutils literal notranslate"><span class="pre">calldata</span></code>, <code class="docutils literal notranslate"><span class="pre">memory</span></code>, or <code class="docutils literal notranslate"><span class="pre">storage</span></code> annotations for reference types</a></p></li>
<li><p><a class="reference internal" href="#summaries-only-apply-to-one-contract-by-default" id="id45">Summaries only apply to one contract by default</a></p></li>
<li><p><a class="reference internal" href="#requirements-on-returns" id="id46">Requirements on <code class="docutils literal notranslate"><span class="pre">returns</span></code></a></p></li>
</ul>
</nav>
<section id="most-solidity-types-allowed-as-arguments">
<h3><a class="toc-backref" href="#id41" role="doc-backlink">Most Solidity types allowed as arguments</a><a class="headerlink" href="#most-solidity-types-allowed-as-arguments" title="Link to this heading"></a></h3>
<p>CVL 1 had some restrictions on the types of arguments allowed in <code class="docutils literal notranslate"><span class="pre">methods</span></code> block
entries.  For example, user-defined types (such as enums and structs) were not
fully supported.</p>
<p>CVL 2 <code class="docutils literal notranslate"><span class="pre">methods</span></code> block entries may use any Solidity types for arguments and
return values, except for <a class="reference external" href="https://docs.soliditylang.org/en/v0.8.17/types.html#function-types">function types</a> and contract or
interface types.</p>
<p>To work around the missing types, CVL 1 allowed users to encode some
user-defined types as primitive types in the <code class="docutils literal notranslate"><span class="pre">methods</span></code> block; these workarounds
are no longer allowed in CVL 2.  For example, consider the following <a class="reference external" href="https://TODO/">solidity
function</a>:</p>
<div class="highlight-solidity notranslate"><div class="highlight"><pre id="codecell20"><span></span><span class="k">contract</span><span class="w"> </span><span class="ni">Example</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kt">enum</span><span class="w"> </span><span class="nv">Permission</span><span class="w"> </span><span class="p">{</span><span class="w"> </span>READ<span class="p">,</span><span class="w"> </span>WRITE<span class="w"> </span><span class="p">};</span>

<span class="w">    </span><span class="kt">function</span><span class="w"> </span><span class="nv">f</span><span class="p">(</span>Permission<span class="w"> </span>p<span class="p">)</span><span class="w"> </span><span class="kt">internal</span><span class="w"> </span><span class="p">{</span><span class="w"> </span><span class="p">...</span><span class="w"> </span><span class="p">}</span>
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
<p>In CVL 1, a methods block entry for <code class="docutils literal notranslate"><span class="pre">f</span></code> would need to declare that it takes a
<code class="docutils literal notranslate"><span class="pre">uint8</span></code> argument:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell21"><span></span><span class="kr">methods</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span>f<span class="p">(</span><span class="kt">uint8</span><span class="w"> </span>permission<span class="p">)</span><span class="w"> </span><span class="kp">=&gt;</span><span class="w"> </span><span class="kc">NONDET</span>
<span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell21">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>In CVL 2, the methods block entry should use the same type as the Solidity
implementations[^contract-types] (<a class="reference external" href="https://github.com/Certora/CVL2Migration/compare/cvl1..cvl2?diff=split#diff-5b1b684b999817bab176753b548b9ca548c8e9a1b7ce72d355030a8e03f498d8">compare files</a>),
except for function types and contract or interface types:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell22"><span></span><span class="kr">methods</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kd">function</span><span class="w"> </span><span class="nf">f</span><span class="p">(</span>Example<span class="p">.</span>Permission<span class="w"> </span>p<span class="p">)</span><span class="w"> </span><span class="kr">internal</span><span class="w"> </span><span class="kp">=&gt;</span><span class="w"> </span><span class="kc">NONDET</span><span class="p">;</span>
<span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell22">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>The method can be called from CVL as follows:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell23"><span></span><span class="k">rule</span><span class="w"> </span><span class="nc">example</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span>f<span class="p">(</span>Example<span class="p">.</span>Permission<span class="p">.</span>READ<span class="p">);</span>
<span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell23">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>Contract functions that take or return contract or interface types should
instead use <code class="docutils literal notranslate"><span class="pre">address</span></code> in the <code class="docutils literal notranslate"><span class="pre">methods</span></code> block declaration.  For example, if the
contract contains the following function:</p>
<div class="highlight-solidity notranslate"><div class="highlight"><pre id="codecell24"><span></span><span class="kt">function</span><span class="w"> </span><span class="nv">listToken</span><span class="p">(</span>IERC20<span class="w"> </span>token<span class="p">)</span><span class="w"> </span><span class="kt">internal</span><span class="w"> </span><span class="p">{</span><span class="w"> </span><span class="p">...</span><span class="w"> </span><span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell24">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>the <code class="docutils literal notranslate"><span class="pre">methods</span></code> block should use <code class="docutils literal notranslate"><span class="pre">address</span></code> for the <code class="docutils literal notranslate"><span class="pre">token</span></code> argument:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell25"><span></span><span class="kr">methods</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kd">function</span><span class="w"> </span><span class="nf">listToken</span><span class="p">(</span><span class="kt">address</span><span class="w"> </span>token<span class="p">)</span><span class="w"> </span><span class="kr">internal</span><span class="p">;</span>
<span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell25">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>Contract functions that take or return function types are not currently
supported.</p>
</section>
<section id="required-internal-or-external-annotation">
<span id="cvl2-visibility"></span><h3><a class="toc-backref" href="#id42" role="doc-backlink">Required <code class="docutils literal notranslate"><span class="pre">internal</span></code> or <code class="docutils literal notranslate"><span class="pre">external</span></code> annotation</a><a class="headerlink" href="#required-internal-or-external-annotation" title="Link to this heading"></a></h3>
<p>Every methods block entry must be marked either <code class="docutils literal notranslate"><span class="pre">internal</span></code> or <code class="docutils literal notranslate"><span class="pre">external</span></code>.  The
annotation must come after the argument list and before the <code class="docutils literal notranslate"><span class="pre">returns</span></code> clause.</p>
<p>If a function is declared <code class="docutils literal notranslate"><span class="pre">public</span></code> in Solidity, then the Solidity compiler
creates an internal implementation method, and an external wrapper method that
calls the internal implementation.  Therefore, you can summarize a <code class="docutils literal notranslate"><span class="pre">public</span></code>
method by marking the summarization <code class="docutils literal notranslate"><span class="pre">internal</span></code>.</p>
<div class="admonition warning">
<p class="admonition-title">Warning</p>
<p>The behavior of <code class="docutils literal notranslate"><span class="pre">internal</span></code> vs. <code class="docutils literal notranslate"><span class="pre">external</span></code> summarization for public methods can
be confusing, especially because functions called directly from CVL are not
summarized.  See <a class="reference internal" href="../methods.html#methods-visibility"><span class="std std-ref">Visibility modifiers</span></a>.</p>
</div>
</section>
<section id="optional-methods-block-entries">
<span id="cvl2-optional"></span><h3><a class="toc-backref" href="#id43" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">optional</span></code> methods block entries</a><a class="headerlink" href="#optional-methods-block-entries" title="Link to this heading"></a></h3>
<p>In CVL 1, you could write an entry in the methods block for a method that does
not exist in the contract; rules that would call the non-existent method were
skipped during verification.</p>
<p>This behavior can lead to confusion, because typos or name changes could silently
cause a rule to be skipped.</p>
<p>In CVL 2, this behavior is still available, but the methods entry must contain
the keyword <code class="docutils literal notranslate"><span class="pre">optional</span></code> somewhere after the <code class="docutils literal notranslate"><span class="pre">returns</span></code> clause and before the
summarization (if any).</p>
</section>
<section id="required-calldata-memory-or-storage-annotations-for-reference-types">
<span id="cvl2-locations"></span><h3><a class="toc-backref" href="#id44" role="doc-backlink">Required <code class="docutils literal notranslate"><span class="pre">calldata</span></code>, <code class="docutils literal notranslate"><span class="pre">memory</span></code>, or <code class="docutils literal notranslate"><span class="pre">storage</span></code> annotations for reference types</a><a class="headerlink" href="#required-calldata-memory-or-storage-annotations-for-reference-types" title="Link to this heading"></a></h3>
<p>In CVL 2, methods block entries for internal functions must contain either <code class="docutils literal notranslate"><span class="pre">calldata</span></code>,
<code class="docutils literal notranslate"><span class="pre">memory</span></code>, or <code class="docutils literal notranslate"><span class="pre">storage</span></code> annotations for all arguments with reference types (such
as arrays).</p>
<p>For methods block entries of external functions the location annotation must be
omitted unless it’s the <code class="docutils literal notranslate"><span class="pre">storage</span></code> annotation on an external library function, in
which case it is required (the reasoning here is to have the information required
in order to correctly calculate a function’s sighash).</p>
</section>
<section id="summaries-only-apply-to-one-contract-by-default">
<span id="cvl2-wildcards"></span><h3><a class="toc-backref" href="#id45" role="doc-backlink">Summaries only apply to one contract by default</a><a class="headerlink" href="#summaries-only-apply-to-one-contract-by-default" title="Link to this heading"></a></h3>
<p>In CVL 1, a summary in the <code class="docutils literal notranslate"><span class="pre">methods</span></code> block applied to all methods with the
given signature.</p>
<p>In CVL 2, summaries only apply to a single contract, unless the old behavior is
explicitly requested by using <code class="docutils literal notranslate"><span class="pre">_</span></code> as the receiver.  If no contract is specified,
the default is <code class="docutils literal notranslate"><span class="pre">currentContract</span></code>.</p>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>The receiver contract must be the contract where the method is defined.  If a
contract inherits a method defined in a supercontract, the receiver must be the
supercontract, rather than the inheriting contract.</p>
</div>
<p>Entries that use <code class="docutils literal notranslate"><span class="pre">_</span></code> as the receiver are called <a class="reference internal" href="../../user-guide/glossary.html#term-wildcard"><span class="xref std std-term">wildcard entries</span></a>, summaries
that do not are called <a class="reference internal" href="../../user-guide/glossary.html#term-exact"><span class="xref std std-term">exact entries</span></a>.</p>
<p>Consider the following example:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell26"><span></span><span class="kn">using</span><span class="w"> </span>C<span class="w"> </span><span class="kn">as</span><span class="w"> </span>c<span class="p">;</span>

<span class="kr">methods</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kd">function</span><span class="w"> </span><span class="nf">f</span><span class="p">(</span><span class="kt">uint</span><span class="p">)</span><span class="w">   </span><span class="kr">internal</span><span class="w"> </span><span class="kp">=&gt;</span><span class="w"> </span><span class="kc">NONDET</span><span class="p">;</span>
<span class="w">    </span><span class="kd">function</span><span class="w"> </span><span class="nc">c</span><span class="p">.</span><span class="nf">g</span><span class="p">(</span><span class="kt">uint</span><span class="p">)</span><span class="w"> </span><span class="kr">internal</span><span class="w"> </span><span class="kp">=&gt;</span><span class="w"> </span><span class="kc">ALWAYS</span><span class="p">(</span><span class="m m-Decimal">4</span><span class="p">);</span>
<span class="w">    </span><span class="kd">function</span><span class="w"> </span><span class="nf">h</span><span class="p">(</span><span class="kt">uint</span><span class="p">)</span><span class="w">   </span><span class="kr">internal</span><span class="w"> </span><span class="kp">=&gt;</span><span class="w"> </span><span class="kc">ALWAYS</span><span class="p">(</span><span class="m m-Decimal">1</span><span class="p">);</span>
<span class="w">    </span><span class="kd">function</span><span class="w"> </span><span class="nc">_</span><span class="p">.</span><span class="nf">h</span><span class="p">(</span><span class="kt">uint</span><span class="p">)</span><span class="w"> </span><span class="kr">internal</span><span class="w"> </span><span class="kp">=&gt;</span><span class="w"> </span><span class="kc">NONDET</span><span class="p">;</span>
<span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell26">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>In this example, the internal function <code class="docutils literal notranslate"><span class="pre">currentContract.f</span></code> has a <code class="docutils literal notranslate"><span class="pre">NONDET</span></code>
summary, <code class="docutils literal notranslate"><span class="pre">c.g</span></code> has an <code class="docutils literal notranslate"><span class="pre">ALWAYS</span></code> summary, a call to <code class="docutils literal notranslate"><span class="pre">currentContact.h</span></code> has an
<code class="docutils literal notranslate"><span class="pre">ALWAYS</span></code> summary and a call to <code class="docutils literal notranslate"><span class="pre">h(uint)</span></code> on any other contract will use a
<code class="docutils literal notranslate"><span class="pre">NONDET</span></code> summary.</p>
<p>Summaries for specific contract methods (including the default
<code class="docutils literal notranslate"><span class="pre">currentContract</span></code>) always override wildcard summaries.</p>
<p>Wildcard entries cannot be declared <code class="docutils literal notranslate"><span class="pre">optional</span></code> or <code class="docutils literal notranslate"><span class="pre">envfree</span></code>, since these
annotations only make sense for specific contract methods.</p>
<div class="admonition warning">
<p class="admonition-title">Warning</p>
<p>The meaning of your summarizations will change from CVL 1 to CVL 2.  In CVL 2,
any entry without an <code class="docutils literal notranslate"><span class="pre">_</span></code> will only apply to a single contract!</p>
</div>
</section>
<section id="requirements-on-returns">
<span id="cvl2-returns"></span><h3><a class="toc-backref" href="#id46" role="doc-backlink">Requirements on <code class="docutils literal notranslate"><span class="pre">returns</span></code></a><a class="headerlink" href="#requirements-on-returns" title="Link to this heading"></a></h3>
<p>In CVL 1, the <code class="docutils literal notranslate"><span class="pre">returns</span></code> clause on methods block entries was optional.
CVL 2 has stricter requirements on the declared return types.</p>
<p>Entries that apply to specific contracts (i.e. those that don’t use the
<code class="docutils literal notranslate"><span class="pre">_.f</span></code> <a class="reference internal" href="#cvl2-wildcards"><span class="std std-ref">syntax</span></a>) must include a <code class="docutils literal notranslate"><span class="pre">returns</span></code> clause if the
contract method returns a value.  A specific-contract entry may only omit the
<code class="docutils literal notranslate"><span class="pre">returns</span></code> clause if the contract method does not return a value.</p>
<p>The Prover will report an error if the contract method’s return type differs
from the type declared in the <code class="docutils literal notranslate"><span class="pre">methods</span></code> block entry.</p>
<p>Wildcard entries must not declare return types, because they may apply to
multiple methods that return different types.  If a wildcard entry is summarized
with a ghost or function summary, the summary must include an <code class="docutils literal notranslate"><span class="pre">expect</span></code> clause;
see <a class="reference internal" href="../methods.html#expression-summary"><span class="std std-ref">Expression summaries</span></a> for more details.</p>
</section>
</section>
<section id="changes-to-integer-types">
<span id="cvl2-integer-types"></span><h2><a class="toc-backref" href="#id16" role="doc-backlink">Changes to integer types</a><a class="headerlink" href="#changes-to-integer-types" title="Link to this heading"></a></h2>
<p>In CVL 1, the rules for casting between integer types were complex; CVL 2
simplifies them.</p>
<p>The general rule of thumb is that you should use <code class="docutils literal notranslate"><span class="pre">mathint</span></code> whenever possible;
only use <code class="docutils literal notranslate"><span class="pre">uint</span></code> or <code class="docutils literal notranslate"><span class="pre">int</span></code> types for data that will be passed as input to
contract functions.</p>
<p>It is now impossible for CVL math expressions to cause overflow - all integer
operations are exact.
The remainder of this section describes the changes in detail.</p>
<section id="mathematical-operations-return-mathint">
<span id="cvl2-mathops-return-mathint"></span><h3><a class="toc-backref" href="#id17" role="doc-backlink">Mathematical operations return <code class="docutils literal notranslate"><span class="pre">mathint</span></code></a><a class="headerlink" href="#mathematical-operations-return-mathint" title="Link to this heading"></a></h3>
<p>In CVL 2, the results of all arithmetic operators have type <code class="docutils literal notranslate"><span class="pre">mathint</span></code>,
regardless of the input types.  Arithmetic operators include <code class="docutils literal notranslate"><span class="pre">+</span></code>,
<code class="docutils literal notranslate"><span class="pre">*</span></code>, <code class="docutils literal notranslate"><span class="pre">-</span></code>, <code class="docutils literal notranslate"><span class="pre">/</span></code>, <code class="docutils literal notranslate"><span class="pre">^</span></code>, and <code class="docutils literal notranslate"><span class="pre">%</span></code>, but not bitwise operators like <code class="docutils literal notranslate"><span class="pre">&lt;&lt;</span></code>, <code class="docutils literal notranslate"><span class="pre">xor</span></code>, and <code class="docutils literal notranslate"><span class="pre">|</span></code>
(changes to bitwise operators are described <a class="reference internal" href="#cvl2-bitwise"><span class="std std-ref">below</span></a>).</p>
<p>The primary impact of this change is that you may need to declare more of your
variables as <code class="docutils literal notranslate"><span class="pre">mathint</span></code> instead of <code class="docutils literal notranslate"><span class="pre">uint</span></code>.  If you are passing the results of
arithmetic operations to contract functions, you will need to be more explicit
about the overflow behavior by using the <a class="reference internal" href="#cvl2-casting"><span class="std std-ref">new casting operators</span></a>.</p>
</section>
<section id="implicit-and-explicit-casting">
<span id="cvl2-casting"></span><h3><a class="toc-backref" href="#id18" role="doc-backlink">Implicit and explicit casting</a><a class="headerlink" href="#implicit-and-explicit-casting" title="Link to this heading"></a></h3>
<p>If every number that can be represented by one type can also be represented by
another type, then we say that the first type is a <em>subtype</em> of the second type.</p>
<p>For example, a <code class="docutils literal notranslate"><span class="pre">uint8</span></code> variable could have any value between <code class="docutils literal notranslate"><span class="pre">0</span></code> and <code class="docutils literal notranslate"><span class="pre">2^8-1</span></code>,
and all of these values can be stored in a <code class="docutils literal notranslate"><span class="pre">uint16</span></code> variable, so <code class="docutils literal notranslate"><span class="pre">uint8</span></code> is a
subtype of <code class="docutils literal notranslate"><span class="pre">uint16</span></code>.  An <code class="docutils literal notranslate"><span class="pre">int16</span></code> can also store any value between <code class="docutils literal notranslate"><span class="pre">0</span></code> and
<code class="docutils literal notranslate"><span class="pre">2^8-1</span></code>, so <code class="docutils literal notranslate"><span class="pre">uint8</span></code> is also a subtype of <code class="docutils literal notranslate"><span class="pre">int16</span></code>.</p>
<p>All integer types are subtypes of <code class="docutils literal notranslate"><span class="pre">mathint</span></code>, since any integer can be
represented by a <code class="docutils literal notranslate"><span class="pre">mathint</span></code>.</p>
<p>In CVL 1, the rules for converting between supertypes and subtypes were
complicated; they depended not only on the types involved, but on the context
in which the conversion happened.  CVL 2 simplifies these rules and improves the
clarity and predictability of casts.</p>
<p>In CVL 2, you can always use a subtype whenever the
supertype is accepted.  For example, you can always use a <code class="docutils literal notranslate"><span class="pre">uint8</span></code> where an
<code class="docutils literal notranslate"><span class="pre">int16</span></code> is expected.  We say that the subtype can be “implicitly cast” to the
supertype.</p>
<p>In order to convert from a supertype to a subtype, you must use an explicit
cast.  In CVL 1, only a few casting operators (such as <code class="docutils literal notranslate"><span class="pre">to_uint256</span></code>) were
supported.</p>
<p>CVL 2 replaces these casting operators with two new casting operators: <em>assert casts</em>
such as <code class="docutils literal notranslate"><span class="pre">assert_uint8(x)</span></code> or <code class="docutils literal notranslate"><span class="pre">assert_int256(x)</span></code>, and <em>require casts</em> such as <code class="docutils literal notranslate"><span class="pre">require_uint8(x)</span></code> or <code class="docutils literal notranslate"><span class="pre">require_int256(x)</span></code>.
Each of these casts checks that the value is in range; the <code class="docutils literal notranslate"><span class="pre">assert</span></code> cast will
report a counterexample if the value is out of range, while the <code class="docutils literal notranslate"><span class="pre">require</span></code> cast
will ignore counterexamples where the cast value is out of range.</p>
<div class="admonition warning">
<p class="admonition-title">Warning</p>
<p>As with normal <code class="docutils literal notranslate"><span class="pre">require</span></code> statements, require casts can cause vacuity and should
be used with care.</p>
</div>
<p>CVL 2 supports assert and require casts on all numeric types.</p>
<p>Casts from <code class="docutils literal notranslate"><span class="pre">address</span></code> or <code class="docutils literal notranslate"><span class="pre">bytes1</span></code>…<code class="docutils literal notranslate"><span class="pre">bytes32</span></code> to integer types are not
supported (see <a class="reference internal" href="#bytesn-support"><span class="std std-ref">Support for bytes1…bytes32</span></a> regarding casting in the other direction, and <a class="reference internal" href="#enum-casting"><span class="std std-ref">Casting enums to integer types</span></a> for information on casting
enums).</p>
<p><code class="docutils literal notranslate"><span class="pre">require</span></code> and <code class="docutils literal notranslate"><span class="pre">assert</span></code> casts are not allowed anywhere inside of a
<a class="reference internal" href="../../user-guide/glossary.html#term-quantifier"><span class="xref std std-term">quantified statement</span></a>.  You can work around this limitation
by adding a second variable.  For example, the following axiom is invalid
because <code class="docutils literal notranslate"><span class="pre">x+1</span></code> is not a <code class="docutils literal notranslate"><span class="pre">uint</span></code>:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell27"><span></span><span class="kd">ghost</span><span class="w"> </span><span class="kt">mapping</span><span class="p">(</span><span class="kt">uint</span><span class="w"> </span><span class="o">=&gt;</span><span class="w"> </span><span class="kt">uint</span><span class="p">)</span><span class="w"> </span>a<span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kr">axiom</span><span class="w"> </span><span class="kr">forall</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>x<span class="w"> </span><span class="p">.</span><span class="w"> </span>a<span class="p">[</span>x<span class="o">+</span><span class="m m-Decimal">1</span><span class="p">]</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="m m-Decimal">0</span>
<span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell27">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>However, it can be replaced with the following:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell28"><span></span><span class="kd">ghost</span><span class="w"> </span><span class="kt">mapping</span><span class="p">(</span><span class="kt">uint</span><span class="w"> </span><span class="o">=&gt;</span><span class="w"> </span><span class="kt">uint</span><span class="p">)</span><span class="w"> </span>a<span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kr">axiom</span><span class="w"> </span><span class="kr">forall</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>x<span class="w"> </span><span class="p">.</span><span class="w"> </span><span class="kr">forall</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>y<span class="w"> </span><span class="p">.</span><span class="w"> </span><span class="p">(</span><span class="nb">to_mathint</span><span class="p">(</span>y<span class="p">)</span><span class="w"> </span><span class="o">==</span><span class="w"> </span>x<span class="w"> </span><span class="o">+</span><span class="w"> </span><span class="m m-Decimal">1</span><span class="p">)</span><span class="w"> </span><span class="o">=&gt;</span><span class="w"> </span>a<span class="p">[</span>y<span class="p">]</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="m m-Decimal">0</span>
<span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell28">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
<section id="casting-enums-to-integer-types">
<span id="enum-casting"></span><h3><a class="toc-backref" href="#id19" role="doc-backlink">Casting enums to integer types</a><a class="headerlink" href="#casting-enums-to-integer-types" title="Link to this heading"></a></h3>
<p>In CVL2 enums are not directly comparable to the corresponding integer type (<code class="docutils literal notranslate"><span class="pre">uint8</span></code>). Instead one must use one of the new cast
operators. For example</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell29"><span></span><span class="kt">uint8</span><span class="w"> </span>x<span class="w"> </span><span class="o">=</span><span class="w"> </span>MyContract<span class="p">.</span>MyEnum<span class="p">.</span>VAL<span class="p">;</span><span class="w"> </span><span class="c1">// will fail typechecking</span>
<span class="kt">uint8</span><span class="w"> </span>x<span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="kr">assert_uint8</span><span class="p">(</span>MyContract<span class="p">.</span>MyEnum<span class="p">.</span>VAL<span class="p">);</span><span class="w"> </span><span class="c1">// good</span>
<span class="kt">mathint</span><span class="w"> </span>x<span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="nb">to_mathint</span><span class="p">(</span>MyContract<span class="p">.</span>MyEnum<span class="p">.</span>VAL<span class="p">);</span><span class="w"> </span><span class="c1">// good</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell29">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>Casting integer types to an enum is not supported.</p>
</section>
<section id="casting-addresses-to-bytes32">
<span id="address-casting"></span><h3><a class="toc-backref" href="#id20" role="doc-backlink">Casting addresses to bytes32</a><a class="headerlink" href="#casting-addresses-to-bytes32" title="Link to this heading"></a></h3>
<p>CVL2 supports casting from the <code class="docutils literal notranslate"><span class="pre">address</span></code> type to the <code class="docutils literal notranslate"><span class="pre">bytes32</span></code> type. For
example:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell30"><span></span><span class="kt">address</span><span class="w"> </span>a<span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mh">0xa44f5d3d624DfD660ecc11FF777587AD0a19606d</span><span class="p">;</span>
<span class="kt">bytes32</span><span class="w"> </span>b<span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="nb">to_bytes32</span><span class="p">(</span>a<span class="p">);</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell30">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>The cast from <code class="docutils literal notranslate"><span class="pre">address</span></code> to <code class="docutils literal notranslate"><span class="pre">bytes32</span></code> behaves equivalently to the Solidity
code:</p>
<div class="highlight-solidity notranslate"><div class="highlight"><pre id="codecell31"><span></span><span class="kt">address</span><span class="w"> </span><span class="nv">a</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mh">0xa44f5d3d624DfD660ecc11FF777587AD0a19606d</span><span class="p">;</span>
<span class="kt">bytes32</span><span class="w"> </span><span class="nv">b</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="kt">bytes32</span><span class="p">(</span><span class="kt">uint256</span><span class="p">(</span><span class="kt">uint160</span><span class="p">(</span>a<span class="p">)));</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell31">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>Among other things, this behavior means that the resulting <code class="docutils literal notranslate"><span class="pre">bytes32</span></code>
value is right-aligned and zero-padded to the left.</p>
<p>CVL2 also supports casting from the <code class="docutils literal notranslate"><span class="pre">bytes32</span></code> type to the <code class="docutils literal notranslate"><span class="pre">address</span></code> type
using either the <code class="docutils literal notranslate"><span class="pre">require_address()</span></code> or <code class="docutils literal notranslate"><span class="pre">assert_address()</span></code> cast functions.</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell32"><span></span><span class="kt">bytes32</span><span class="w"> </span>b<span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="nb">to_bytes32</span><span class="p">(</span><span class="mh">0xa44f5d3d624DfD660ecc11FF777587AD0a19606d</span><span class="p">);</span>
<span class="kt">address</span><span class="w"> </span>a<span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="kr">assert_address</span><span class="p">(</span>b<span class="p">);</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell32">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>Note that <code class="docutils literal notranslate"><span class="pre">require_address()</span></code> will silently allow a cast to continue
when the <code class="docutils literal notranslate"><span class="pre">bytes32</span></code> variable contains a value that lies in the range
<code class="docutils literal notranslate"><span class="pre">2^160</span> <span class="pre">&lt;</span> <span class="pre">var</span> <span class="pre">&lt;</span> <span class="pre">2^256</span></code>. The <code class="docutils literal notranslate"><span class="pre">assert_address()</span></code> cast function will fail
when the <code class="docutils literal notranslate"><span class="pre">bytes32</span></code> variable contains a value in that same range.</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell33"><span></span><span class="kt">bytes32</span><span class="w"> </span>b<span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="nb">to_bytes32</span><span class="p">(</span><span class="mh">0xa44f5d3d624DfD660ecc11FF777587AD0a19606d0e</span><span class="p">);</span><span class="w"> </span><span class="c1">// Note this contains one extra byte</span>
<span class="kt">address</span><span class="w"> </span>a<span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="kr">require_address</span><span class="p">(</span>b<span class="p">);</span><span class="w">                                       </span><span class="c1">// Silently does the cast.</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell33">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>While when using <code class="docutils literal notranslate"><span class="pre">assert_address</span></code>:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell34"><span></span><span class="kt">bytes32</span><span class="w"> </span>b<span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="nb">to_bytes32</span><span class="p">(</span><span class="mh">0xa44f5d3d624DfD660ecc11FF777587AD0a19606d0e</span><span class="p">);</span><span class="w"> </span><span class="c1">// Note this contains one extra byte</span>
<span class="kt">address</span><span class="w"> </span>a<span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="kr">assert_address</span><span class="p">(</span>b<span class="p">);</span><span class="w">                                       </span><span class="c1">// This will fail.</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell34">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>Casting from <code class="docutils literal notranslate"><span class="pre">bytes32</span></code> to <code class="docutils literal notranslate"><span class="pre">address</span></code> behaves equivalently to the Solidity
code:</p>
<div class="highlight-solidity notranslate"><div class="highlight"><pre id="codecell35"><span></span><span class="kt">bytes32</span><span class="w"> </span><span class="nv">b</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="kt">bytes32</span><span class="p">(</span><span class="mh">0xa44f5d3d624DfD660ecc11FF777587AD0a19606d</span><span class="p">);</span>
<span class="kt">address</span><span class="w"> </span><span class="nv">a</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="kt">address</span><span class="p">(</span><span class="kt">uint160</span><span class="p">(</span><span class="kt">uint256</span><span class="p">(</span>b<span class="p">)));</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell35">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
<section id="modulo-operator-always-returns-non-negative-values">
<h3><a class="toc-backref" href="#id21" role="doc-backlink">Modulo operator <code class="docutils literal notranslate"><span class="pre">%</span></code> always returns non-negative values</a><a class="headerlink" href="#modulo-operator-always-returns-non-negative-values" title="Link to this heading"></a></h3>
<p>The modulo operator <code class="docutils literal notranslate"><span class="pre">%</span></code> follows the semantics of Solidity’s unsigned modulo and
always returns non-negative values, regardless of the signs of its operands.</p>
</section>
<section id="support-for-bytes1-bytes32">
<span id="bytesn-support"></span><h3><a class="toc-backref" href="#id22" role="doc-backlink">Support for <code class="docutils literal notranslate"><span class="pre">bytes1</span></code>…<code class="docutils literal notranslate"><span class="pre">bytes32</span></code></a><a class="headerlink" href="#support-for-bytes1-bytes32" title="Link to this heading"></a></h3>
<p>CVL 2 supports the types <code class="docutils literal notranslate"><span class="pre">bytes1</span></code>, <code class="docutils literal notranslate"><span class="pre">bytes2</span></code>, …, <code class="docutils literal notranslate"><span class="pre">bytes32</span></code>, as in Solidity.
Number literals must be explicitly cast to these types using <code class="docutils literal notranslate"><span class="pre">to_bytesN</span></code>; for
example:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell36"><span></span><span class="kt">bytes32</span><span class="w"> </span>x<span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="nb">to_bytes32</span><span class="p">(</span><span class="m m-Decimal">0</span><span class="p">);</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell36">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>Unlike Solidity, <code class="docutils literal notranslate"><span class="pre">bytes1</span></code>…<code class="docutils literal notranslate"><span class="pre">bytes32</span></code> literals do not need to be written in hex
or padded to the correct length.</p>
<p>The only conversion between integer types and these types is from <code class="docutils literal notranslate"><span class="pre">uint&lt;i*8&gt;</span></code> to
<code class="docutils literal notranslate"><span class="pre">bytes&lt;i&gt;</span></code> (i.e. unsigned integers with the same bitwidth as the target <code class="docutils literal notranslate"><span class="pre">bytes&lt;i&gt;</span></code> type);
For example:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell37"><span></span><span class="kt">uint24</span><span class="w"> </span>u<span class="p">;</span>
bytes3<span class="w"> </span>x<span class="w"> </span><span class="o">=</span><span class="w"> </span>to_bytes3<span class="p">(</span>u<span class="p">);</span><span class="w"> </span><span class="c1">// This is OK</span>
bytes4<span class="w"> </span>y<span class="w"> </span><span class="o">=</span><span class="w"> </span>to_bytes4<span class="p">(</span>u<span class="p">);</span><span class="w"> </span><span class="c1">// This will fail</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell37">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
<section id="changes-for-bitwise-operations">
<span id="cvl2-bitwise"></span><h3><a class="toc-backref" href="#id23" role="doc-backlink">Changes for bitwise operations</a><a class="headerlink" href="#changes-for-bitwise-operations" title="Link to this heading"></a></h3>
<p>In CVL1, the exact details for bitwise operations (such as <code class="docutils literal notranslate"><span class="pre">&amp;</span></code>, <code class="docutils literal notranslate"><span class="pre">|</span></code>, and <code class="docutils literal notranslate"><span class="pre">&lt;&lt;</span></code>) were not
completely specified, especially for negative integers.</p>
<p>In CVL 2, all bitwise operations (<code class="docutils literal notranslate"><span class="pre">&amp;</span></code>, <code class="docutils literal notranslate"><span class="pre">|</span></code>, <code class="docutils literal notranslate"><span class="pre">~</span></code>, <code class="docutils literal notranslate"><span class="pre">&gt;&gt;</span></code>, <code class="docutils literal notranslate"><span class="pre">&gt;&gt;&gt;</span></code>, <code class="docutils literal notranslate"><span class="pre">&lt;&lt;</span></code>, and <code class="docutils literal notranslate"><span class="pre">xor</span></code>)
on integer types first convert to a 256 bit word, then perform the operations
on the full 256-bit word, then convert back to the expected type.  Signed
integer types use twos-complement encoding.</p>
<p>The two right-shifts differ in how they treat signed integers.  <code class="docutils literal notranslate"><span class="pre">&gt;&gt;</span></code> is an
arithmetic shift; it preserves the sign bit.  <code class="docutils literal notranslate"><span class="pre">&gt;&gt;&gt;</span></code> is a logical shift; it pads
the shifted word with zero.</p>
<p>Bitwise operations cannot be performed on <code class="docutils literal notranslate"><span class="pre">mathint</span></code> values.</p>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>By default, bitwise operators are <a class="reference internal" href="../../user-guide/glossary.html#term-overapproximation"><span class="xref std std-term">overapproximated</span></a>
(in both CVL 1 and CVL 2), so you may see counterexamples that incorrectly
compute the results of bitwise operations.  The approximations are still
<a class="reference internal" href="../../user-guide/glossary.html#term-sound"><span class="xref std std-term">sound</span></a>: the Prover will not report a rule as verified if the original
code does not satisfy the rule.</p>
<p>The <a class="reference internal" href="../../prover/cli/options.html#precise-bitwise-ops"><span class="std std-ref">precise_bitwise_ops</span></a> flag makes the Prover’s reasoning about bitwise
operations more precise, but this flag is experimental in CVL 2.</p>
</div>
</section>
</section>
<section id="changes-to-the-fallback-function">
<span id="cvl2-fallback-changes"></span><h2><a class="toc-backref" href="#id24" role="doc-backlink">Changes to the fallback function</a><a class="headerlink" href="#changes-to-the-fallback-function" title="Link to this heading"></a></h2>
<p>In CVL 1, you could determine whether a <code class="docutils literal notranslate"><span class="pre">method</span></code> object was the fallback function
by comparing its selector to <code class="docutils literal notranslate"><span class="pre">certorafallback().selector</span></code>:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell38"><span></span><span class="kr">assert</span><span class="w"> </span>f<span class="p">.</span><span class="nb">selector</span><span class="w"> </span><span class="o">==</span><span class="w"> </span>certorafallback<span class="p">().</span><span class="nb">selector</span><span class="p">,</span>
<span class="w">    </span><span class="s2">"f must be the fallback"</span><span class="p">;</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell38">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>In CVL 2, <code class="docutils literal notranslate"><span class="pre">certorafallback()</span></code> is no longer valid.  Instead, you can use the new
field <code class="docutils literal notranslate"><span class="pre">f.isFallback</span></code> to detect the fallback method:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell39"><span></span><span class="kr">assert</span><span class="w"> </span>f<span class="p">.</span>isFallback<span class="p">,</span>
<span class="w">    </span><span class="s2">"f must be the fallback"</span><span class="p">;</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell39">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
<section id="removed-features">
<h2><a class="toc-backref" href="#id25" role="doc-backlink">Removed features</a><a class="headerlink" href="#removed-features" title="Link to this heading"></a></h2>
<p>As we transit to CVL 2, we have removed several language features
that are no longer used.</p>
<p>We have removed these features because we think they are no longer used and no
longer useful.  If you find that you do need one of these features, contact
Certora support.</p>
<section id="methods-entries-for-sighashes">
<span id="cvl2-removed-sighashes"></span><h3><a class="toc-backref" href="#id26" role="doc-backlink">Methods entries for sighashes</a><a class="headerlink" href="#methods-entries-for-sighashes" title="Link to this heading"></a></h3>
<p>In CVL 1, you could write a sighash instead of a method identifier in the
<code class="docutils literal notranslate"><span class="pre">methods</span></code> block.  This feature is no longer supported.  You will need to have
the name and argument types of the called method in order to provide an entry.</p>
</section>
<section id="invoke-sinvoke-and-call">
<span id="cvl2-removed-invoke"></span><h3><a class="toc-backref" href="#id27" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">invoke</span></code>, <code class="docutils literal notranslate"><span class="pre">sinvoke</span></code>, and <code class="docutils literal notranslate"><span class="pre">call</span></code></a><a class="headerlink" href="#invoke-sinvoke-and-call" title="Link to this heading"></a></h3>
<p>Older versions of CVL had special syntax for calling contract and CVL functions:</p>
<ul class="simple">
<li><p><code class="docutils literal notranslate"><span class="pre">invoke</span> <span class="pre">f(args);</span></code> should be replaced with <code class="docutils literal notranslate"><span class="pre">f@withrevert(args);</span></code>.</p></li>
<li><p><code class="docutils literal notranslate"><span class="pre">sinvoke</span> <span class="pre">f(args);</span></code> should be replaced with <code class="docutils literal notranslate"><span class="pre">f(args);</span></code>.</p></li>
<li><p><code class="docutils literal notranslate"><span class="pre">call</span> <span class="pre">f(args)</span></code> should be replaced with <code class="docutils literal notranslate"><span class="pre">f(args)</span></code>.</p></li>
</ul>
</section>
<section id="static-assert-and-static-require">
<span id="cvl2-removed-static-assert-require"></span><h3><a class="toc-backref" href="#id28" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">static_assert</span></code> and <code class="docutils literal notranslate"><span class="pre">static_require</span></code></a><a class="headerlink" href="#static-assert-and-static-require" title="Link to this heading"></a></h3>
<p>These deprecated aliases for <code class="docutils literal notranslate"><span class="pre">assert</span></code> and <code class="docutils literal notranslate"><span class="pre">require</span></code> are being removed; replace
them with <code class="docutils literal notranslate"><span class="pre">assert</span></code> and <code class="docutils literal notranslate"><span class="pre">require</span></code> respectively.</p>
</section>
<section id="invoke-fallback-and-certorafallback">
<span id="cvl2-removed-fallback"></span><h3><a class="toc-backref" href="#id29" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">invoke_fallback</span></code> and <code class="docutils literal notranslate"><span class="pre">certorafallback()</span></code></a><a class="headerlink" href="#invoke-fallback-and-certorafallback" title="Link to this heading"></a></h3>
<p>The <code class="docutils literal notranslate"><span class="pre">invoke_fallback</span></code> syntax is no longer supported; there is no longer a way
to directly invoke the fallback method.  You can work around this limitation by
writing a parametric rule and filtering on <code class="docutils literal notranslate"><span class="pre">f.isFallback</span></code>.  See
<a class="reference internal" href="#cvl2-fallback-changes"><span class="std std-ref">Changes to the fallback function</span></a>.</p>
</section>
<section id="invoke-whole">
<span id="cvl2-removed-invoke-whole"></span><h3><a class="toc-backref" href="#id30" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">invoke_whole</span></code></a><a class="headerlink" href="#invoke-whole" title="Link to this heading"></a></h3>
<p>The <code class="docutils literal notranslate"><span class="pre">invoke_whole</span></code> keyword is no longer supported.</p>
</section>
<section id="havocing-local-variables">
<span id="cvl2-removed-havoc"></span><h3><a class="toc-backref" href="#id31" role="doc-backlink">Havocing local variables</a><a class="headerlink" href="#havocing-local-variables" title="Link to this heading"></a></h3>
<p>In CVL 1, you could write the following:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell40"><span></span><span class="kt">calldataarg</span><span class="w"> </span>args<span class="p">;</span><span class="w"> </span><span class="kt">env</span><span class="w"> </span>e<span class="p">;</span>
f<span class="p">(</span>e<span class="p">,</span><span class="w"> </span>args<span class="p">);</span>

<span class="kr">havoc</span><span class="w"> </span>args<span class="p">;</span>
g<span class="p">(</span>e<span class="p">,</span><span class="w"> </span>args<span class="p">);</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell40">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>In CVL 2, you can only <code class="docutils literal notranslate"><span class="pre">havoc</span></code> ghost variables and ghost functions.  Instead of
havocing a local variable, replace the havoced variable with a new variable. For
example, you should replace the above with</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell41"><span></span><span class="kt">calldataarg</span><span class="w"> </span>args<span class="p">;</span><span class="w"> </span><span class="kt">env</span><span class="w"> </span>e<span class="p">;</span>
f<span class="p">(</span>e<span class="p">,</span>args<span class="p">);</span>

<span class="kt">calldataarg</span><span class="w"> </span>args2<span class="p">;</span>
g<span class="p">(</span>e<span class="p">,</span>args2<span class="p">);</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell41">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
<section id="destructuring-syntax-for-struct-returns">
<span id="cvl2-removed-destructure-struct"></span><h3><a class="toc-backref" href="#id32" role="doc-backlink">Destructuring syntax for struct returns</a><a class="headerlink" href="#destructuring-syntax-for-struct-returns" title="Link to this heading"></a></h3>
<p>In CVL 1, if a contract function returned a struct, you could use a
destructuring syntax to get the return value in your spec.  For example,
consider the following contract:</p>
<div class="highlight-solidity notranslate"><div class="highlight"><pre id="codecell42"><span></span><span class="k">contract</span><span class="w"> </span><span class="ni">Example</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kt">struct</span><span class="w"> </span><span class="nv">S</span><span class="w"> </span><span class="p">{</span>
<span class="w">        </span><span class="kt">uint</span><span class="w"> </span><span class="nv">firstField</span><span class="p">;</span>
<span class="w">        </span><span class="kt">uint</span><span class="w"> </span><span class="nv">secondField</span><span class="p">;</span>
<span class="w">        </span><span class="kt">bool</span><span class="w"> </span><span class="nv">thirdField</span><span class="p">;</span>
<span class="w">    </span><span class="p">}</span>

<span class="w">    </span><span class="kt">function</span><span class="w"> </span><span class="nv">f</span><span class="p">()</span><span class="w"> </span><span class="kt">returns</span><span class="p">(</span>S<span class="p">)</span><span class="w"> </span><span class="p">{</span><span class="w"> </span><span class="p">...</span><span class="w"> </span><span class="p">}</span>
<span class="w">    </span><span class="kt">function</span><span class="w"> </span><span class="nv">g</span><span class="p">()</span><span class="w"> </span><span class="kt">returns</span><span class="p">(</span><span class="kt">uint</span><span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="p">)</span><span class="w"> </span><span class="p">{</span><span class="w"> </span><span class="p">...</span><span class="w"> </span><span class="p">}</span>
<span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell42">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>To access the return value of <code class="docutils literal notranslate"><span class="pre">f</span></code> in CVL 1, you could write the following:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell43"><span></span><span class="kt">uint</span><span class="w"> </span>x<span class="p">;</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>y<span class="p">;</span><span class="w"> </span><span class="kt">bool</span><span class="w"> </span>z<span class="p">;</span>
x<span class="p">,</span><span class="w"> </span>y<span class="p">,</span><span class="w"> </span>z<span class="w"> </span><span class="o">=</span><span class="w"> </span>f<span class="p">();</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell43">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>This syntax is no longer supported.  Instead, you should declare a variable with
the struct type:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell44"><span></span>Example<span class="p">.</span>S<span class="w"> </span>result<span class="w"> </span><span class="o">=</span><span class="w"> </span>f<span class="p">();</span>
<span class="kt">uint</span><span class="w"> </span>x<span class="w"> </span><span class="o">=</span><span class="w"> </span>result<span class="p">.</span>firstField<span class="p">;</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell44">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>Destructuring assignments are still allowed for functions that return multiple
values; the following is valid:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell45"><span></span><span class="kt">uint</span><span class="w"> </span>x<span class="p">;</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>y<span class="p">;</span>
x<span class="p">,</span><span class="w"> </span>y<span class="w"> </span><span class="o">=</span><span class="w"> </span>g<span class="p">();</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell45">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
<section id="bytes-and-string">
<span id="cvl2-removed-double-arrays"></span><h3><a class="toc-backref" href="#id33" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">bytes[]</span></code> and <code class="docutils literal notranslate"><span class="pre">string[]</span></code></a><a class="headerlink" href="#bytes-and-string" title="Link to this heading"></a></h3>
<p>In CVL 1, you could declare variables of type <code class="docutils literal notranslate"><span class="pre">string[]</span></code> and <code class="docutils literal notranslate"><span class="pre">bytes[]</span></code>.  You can
no longer use these types in CVL.</p>
<p>You can still declare contract methods that use these types in the <code class="docutils literal notranslate"><span class="pre">methods</span></code>
block.  However, you can only call methods that take one of these types as an
argument by passing a <code class="docutils literal notranslate"><span class="pre">calldataarg</span></code> variable, and you cannot access the return
value of a method that returns one of these types.</p>
</section>
<section id="pragma">
<span id="cvl2-removed-pragma"></span><h3><a class="toc-backref" href="#id34" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">pragma</span></code></a><a class="headerlink" href="#pragma" title="Link to this heading"></a></h3>
<p>CVL 1 had a <code class="docutils literal notranslate"><span class="pre">pragma</span></code> command for specifying the CVL version, but this feature
was not used and has been removed in CVL 2.</p>
</section>
<section id="events">
<h3><a class="toc-backref" href="#id35" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">events</span></code></a><a class="headerlink" href="#events" title="Link to this heading"></a></h3>
<p>CVL 1 had syntax for an <code class="docutils literal notranslate"><span class="pre">events</span></code> block, but it did nothing and has been removed.</p>
</section>
</section>
<section id="changes-to-the-command-line-interface-cli">
<h2><a class="toc-backref" href="#id36" role="doc-backlink">Changes to the Command Line Interface (CLI)</a><a class="headerlink" href="#changes-to-the-command-line-interface-cli" title="Link to this heading"></a></h2>
<p>As part of the transition to CVL 2 changes were made to enhanced clarity,
uniformity, and readability on the Command-Line Interface (CLI).
The complete CLI specification can be found <a class="reference internal" href="../../prover/cli/options.html"><span class="std std-doc">here</span></a></p>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>The changes will take effect starting v4.3.1 of <code class="docutils literal notranslate"><span class="pre">certora-cli</span></code>.</p>
</div>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>To opt-out of the new CLI, one can set an environment variable <code class="docutils literal notranslate"><span class="pre">CERTORA_OLD_API</span></code> to <code class="docutils literal notranslate"><span class="pre">1</span></code>, e.g.:
<code class="docutils literal notranslate"><span class="pre">export</span> <span class="pre">CERTORA_OLD_API=1</span></code>.
<strong>The old CLI will not be available in versions released after August 31st, 2023</strong></p>
</div>
<section id="flags-renaming">
<h3><a class="toc-backref" href="#id37" role="doc-backlink">Flags Renaming</a><a class="headerlink" href="#flags-renaming" title="Link to this heading"></a></h3>
<p>In CVL 2 some flags were renamed:</p>
<ol class="arabic simple">
<li><p>flags with names that are generic or wrong</p></li>
<li><p>flags that do not match their corresponding key in the <code class="docutils literal notranslate"><span class="pre">conf</span></code> file</p></li>
<li><p>flags that do not follow the snake case format</p></li>
</ol>
<p>This is the list of the flags that were renamed:</p>
<div class="wy-table-responsive"><table class="docutils align-default">
<thead>
<tr class="row-odd"><th class="head"><p>CVL 1</p></th>
<th class="head"><p>CVL 2</p></th>
</tr>
</thead>
<tbody>
<tr class="row-even"><td><p><code class="docutils literal notranslate"><span class="pre">--settings</span></code></p></td>
<td><p><code class="docutils literal notranslate"><span class="pre">--prover_args</span></code></p></td>
</tr>
<tr class="row-odd"><td><p><code class="docutils literal notranslate"><span class="pre">--path</span></code></p></td>
<td><p><code class="docutils literal notranslate"><span class="pre">--solc_allow_path</span></code></p></td>
</tr>
<tr class="row-even"><td><p><code class="docutils literal notranslate"><span class="pre">--optimize</span></code></p></td>
<td><p><code class="docutils literal notranslate"><span class="pre">--solc_optimize</span></code></p></td>
</tr>
<tr class="row-odd"><td><p><code class="docutils literal notranslate"><span class="pre">--optimize_map</span></code></p></td>
<td><p><code class="docutils literal notranslate"><span class="pre">--solc_optimize_map</span></code></p></td>
</tr>
<tr class="row-even"><td><p><code class="docutils literal notranslate"><span class="pre">--structLink</span></code></p></td>
<td><p><code class="docutils literal notranslate"><span class="pre">--struct_link</span></code></p></td>
</tr>
<tr class="row-odd"><td><p><code class="docutils literal notranslate"><span class="pre">--javaArgs</span></code></p></td>
<td><p><code class="docutils literal notranslate"><span class="pre">--java_args</span></code></p></td>
</tr>
</tbody>
</table></div>
</section>
<section id="prover-args">
<h3><a class="toc-backref" href="#id38" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">Prover</span> <span class="pre">Args</span></code></a><a class="headerlink" href="#prover-args" title="Link to this heading"></a></h3>
<p><code class="docutils literal notranslate"><span class="pre">Prover</span> <span class="pre">args</span></code> are CLI flags that are sent to the Prover. <code class="docutils literal notranslate"><span class="pre">Prover</span> <span class="pre">args</span></code> can be set in one of two ways:</p>
<ol class="arabic simple">
<li><p>Using specific CLI flags (e.g. <code class="docutils literal notranslate"><span class="pre">--loop_iter</span></code>)</p></li>
<li><p>As parameters to the <code class="docutils literal notranslate"><span class="pre">--prover_args</span></code> (<code class="docutils literal notranslate"><span class="pre">--settings</span></code> in CVL 1)</p></li>
</ol>
<p>Unlike CVL 1, if a <code class="docutils literal notranslate"><span class="pre">prover</span> <span class="pre">arg</span></code> is set using a specific CLI flag it cannot be set
using <code class="docutils literal notranslate"><span class="pre">--prover_args</span></code>. In addition, the value commas and equal signs separators that were used in <code class="docutils literal notranslate"><span class="pre">--settings</span></code>
were replaced with white-spaces
in <code class="docutils literal notranslate"><span class="pre">--prover_args</span></code>.</p>
<p>Example:</p>
<p>Consider this call to <code class="docutils literal notranslate"><span class="pre">certoraRun</span></code> using CVL 1 syntax</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell46"><span></span>certoraRun<span class="w"> </span>Compound.sol<span class="w"> </span><span class="se">\</span>
<span class="w">    </span>--verify<span class="w"> </span>Compound:Compound.spec<span class="w">  </span><span class="se">\</span>
<span class="w">    </span>--solc<span class="w"> </span>solc8.13<span class="w"> </span><span class="se">\</span>
<span class="w">    </span>--settings<span class="w"> </span>-smt_bitVectorTheory<span class="o">=</span>true,-smt_hashingScheme<span class="o">=</span>plainInjectivity,-assumeUnwindCond
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell46">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>In order to convert this call to CVL 2 we:</p>
<ol class="arabic simple">
<li><p>renamed <code class="docutils literal notranslate"><span class="pre">--settings</span></code> to <code class="docutils literal notranslate"><span class="pre">--prover_args</span></code></p></li>
<li><p>replaced <code class="docutils literal notranslate"><span class="pre">-assumeUnwindCond</span></code> with the flag <code class="docutils literal notranslate"><span class="pre">--optimistic_loop</span></code></p></li>
<li><p>removed the comma and equal sign separators</p></li>
</ol>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell47"><span></span>certoraRun<span class="w"> </span>Compound.sol<span class="w"> </span><span class="se">\</span>
<span class="w">    </span>--verify<span class="w"> </span>Compound:Compound.spec<span class="w">  </span><span class="se">\</span>
<span class="w">    </span>--solc<span class="w"> </span>solc8.13<span class="w"> </span><span class="se">\</span>
<span class="w">    </span>--optimistic_loop<span class="w"> </span><span class="se">\</span>
<span class="w">    </span>--prover_args<span class="w"> </span><span class="s1">'-smt_bitVectorTheory true -smt_hashingScheme plainInjectivity'</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell47">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
<section id="solidity-compiler-args">
<h3><a class="toc-backref" href="#id39" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">Solidity</span> <span class="pre">Compiler</span> <span class="pre">Args</span></code></a><a class="headerlink" href="#solidity-compiler-args" title="Link to this heading"></a></h3>
<p>The <code class="docutils literal notranslate"><span class="pre">Solidity</span> <span class="pre">Compiler</span> <span class="pre">Args</span></code> are CLI flags that are sent to the Solidity compiler. The behavior of the <code class="docutils literal notranslate"><span class="pre">Solidity</span> <span class="pre">Args</span></code> is similar to <code class="docutils literal notranslate"><span class="pre">Prover</span> <span class="pre">Args</span></code>. The flag <code class="docutils literal notranslate"><span class="pre">--solc_args</span></code> can only be used if there is no CLI flag that sets the Solidity flag and the value of <code class="docutils literal notranslate"><span class="pre">--solc_args</span></code> is
a string that is sent as is to the Solidity compiler.</p>
<p>Example:</p>
<p>Consider this call to <code class="docutils literal notranslate"><span class="pre">certoraRun</span></code> using CVL 1 syntax</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell48"><span></span>certoraRun<span class="w"> </span>Compound.sol<span class="w"> </span><span class="se">\</span>
<span class="w">    </span>--verify<span class="w"> </span>Compound:Compound.spec<span class="w">  </span><span class="se">\</span>
<span class="w">    </span>--solc<span class="w"> </span>solc8.13<span class="w"> </span><span class="se">\</span>
<span class="w">    </span>--solc_args<span class="w"> </span><span class="s2">"['--optimize', '--optimize-runs', '200', '--experimental-via-ir']"</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell48">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>In CVL 2 calling optimize is using <code class="docutils literal notranslate"><span class="pre">--solc_optimize</span></code></p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell49"><span></span>certoraRun<span class="w"> </span>Compound.sol<span class="w"> </span><span class="se">\</span>
<span class="w">    </span>--verify<span class="w"> </span>Compound:Compound.spec<span class="w">  </span><span class="se">\</span>
<span class="w">    </span>--solc<span class="w"> </span>solc8.13<span class="w"> </span><span class="se">\</span>
<span class="w">    </span>--solc_optimize<span class="w"> </span><span class="m">200</span><span class="w"> </span><span class="se">\</span>
<span class="w">    </span>--solc_args<span class="w"> </span><span class="s2">"--experimental-via-ir"</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell49">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
<section id="enhanced-server-support">
<h3><a class="toc-backref" href="#id40" role="doc-backlink">Enhanced server support</a><a class="headerlink" href="#enhanced-server-support" title="Link to this heading"></a></h3>
<p>In CVL 1, two server platforms were supported:</p>
<ol class="arabic simple">
<li><p><code class="docutils literal notranslate"><span class="pre">staging</span></code> was set using the flag <code class="docutils literal notranslate"><span class="pre">--staging</span> <span class="pre">[Branch/hotfix]</span></code></p></li>
<li><p><code class="docutils literal notranslate"><span class="pre">production</span></code> was set using the flag <code class="docutils literal notranslate"><span class="pre">--cloud</span> <span class="pre">[Branch/hotfix]</span></code></p></li>
</ol>
<p>In CVL 2 the flag <code class="docutils literal notranslate"><span class="pre">--server</span></code> was added to replace <code class="docutils literal notranslate"><span class="pre">--staging</span></code> <code class="docutils literal notranslate"><span class="pre">--cloud</span></code> and to allow adding additional server platforms.
<code class="docutils literal notranslate"><span class="pre">--server</span></code> gets as a parameter the platform name.
<code class="docutils literal notranslate"><span class="pre">--prover_version</span></code> is a new flag in CVL 2 For setting the Branch/hot-fix</p>
</section>
</section>
</section>


           </div>
          </div>
          <footer><div class="rst-footer-buttons" role="navigation" aria-label="Footer">
        <a href="../foundry-integration.html" class="btn btn-neutral float-left" title="Foundry Integration (Alpha)" accesskey="p" rel="prev"><span class="fa fa-arrow-circle-left" aria-hidden="true"></span> Previous</a>
        <a href="migration.html" class="btn btn-neutral float-right" title="CVL2 Migration Guide" accesskey="n" rel="next">Next <span class="fa fa-arrow-circle-right" aria-hidden="true"></span></a>
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