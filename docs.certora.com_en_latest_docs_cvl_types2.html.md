<!DOCTYPE html><html class="writer-html5" lang="en" data-content_root="../../"><head>
  <meta charset="utf-8"><meta name="viewport" content="width=device-width, initial-scale=1">

  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Types — Certora Prover Documentation 0.0 documentation</title>
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
    <link rel="next" title="Expressions" href="expr.html">
    <link rel="prev" title="Basic Syntax" href="basics.html"> 
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
<li class="toctree-l1 current" aria-expanded="true"><a class="reference internal" href="index.html"><button class="toctree-expand" title="Open/close menu"></button>The Certora Verification Language</a><ul class="" aria-expanded="false">
<li class="toctree-l2"><a class="reference internal" href="overview.html">Specification Files</a></li>
<li class="toctree-l2"><a class="reference internal" href="basics.html">Basic Syntax</a></li>
<li class="toctree-l2 current" aria-expanded="true"><a class="reference internal current" href="#" aria-expanded="true"><button class="toctree-expand" title="Open/close menu"></button>Types</a><ul>
<li class="toctree-l3"><a class="reference internal" href="#syntax">Syntax</a></li>
<li class="toctree-l3"><a class="reference internal" href="#solidity-types"><button class="toctree-expand" title="Open/close menu"></button>Solidity Types</a><ul>
<li class="toctree-l4"><a class="reference internal" href="#integer-types">Integer types</a></li>
<li class="toctree-l4"><a class="reference internal" href="#array-access">Array access</a></li>
<li class="toctree-l4"><a class="reference internal" href="#user-defined-types">User-defined types</a></li>
</ul>
</li>
<li class="toctree-l3"><a class="reference internal" href="#additional-cvl-types"><button class="toctree-expand" title="Open/close menu"></button>Additional CVL types</a><ul>
<li class="toctree-l4"><a class="reference internal" href="#the-mathint-type">The <code class="docutils literal notranslate"><span class="pre">mathint</span></code> type</a></li>
<li class="toctree-l4"><a class="reference internal" href="#the-env-type">The <code class="docutils literal notranslate"><span class="pre">env</span></code> type</a></li>
<li class="toctree-l4"><a class="reference internal" href="#the-method-and-calldataarg-types">The <code class="docutils literal notranslate"><span class="pre">method</span></code> and <code class="docutils literal notranslate"><span class="pre">calldataarg</span></code> types</a></li>
<li class="toctree-l4"><a class="reference internal" href="#the-storage-type">The <code class="docutils literal notranslate"><span class="pre">storage</span></code> type</a></li>
<li class="toctree-l4"><a class="reference internal" href="#uninterpreted-sorts">Uninterpreted sorts</a></li>
</ul>
</li>
<li class="toctree-l3"><a class="reference internal" href="#conversions-between-cvl-and-solidity-types">Conversions between CVL and Solidity types</a></li>
</ul>
</li>
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
      <li class="breadcrumb-item active">Types</li>
      <li class="wy-breadcrumbs-aside">
            <a href="../../_sources/docs/cvl/types.md.txt" rel="nofollow"> View page source</a>
      </li>
  </ul>
  <hr>
</div>
          <div role="main" class="document" itemscope="itemscope" itemtype="http://schema.org/Article">
           <div itemprop="articleBody">
             
  <section id="types">
<h1><a class="toc-backref" href="#id6" role="doc-backlink">Types</a><a class="headerlink" href="#types" title="Link to this heading"></a></h1>
<p>Like Solidity, CVL is a statically typed language.  There is overlap between
the types supported by Solidity and the types supported by CVL, but CVL has some
additional types and is also missing support for some Solidity types.</p>
<p>The additional CVL types are:</p>
<ul class="simple">
<li><p><a class="reference internal" href="#mathint"><span class="std std-ref">The mathint type</span></a> is an arbitrary precision integer that cannot overflow</p></li>
<li><p><a class="reference internal" href="#method-type"><span class="std std-ref">The method and calldataarg types</span></a> are used
to represent arbitrary methods and arguments of the contract under verification</p></li>
<li><p><a class="reference internal" href="#storage-type"><span class="std std-ref">The storage type</span></a> is used to represent a snapshot of the entire EVM storage</p></li>
<li><p><a class="reference internal" href="#env"><span class="std std-ref">The env type</span></a> is used to represent the Solidity global variables <code class="docutils literal notranslate"><span class="pre">msg</span></code>, <code class="docutils literal notranslate"><span class="pre">block</span></code>, and <code class="docutils literal notranslate"><span class="pre">tx</span></code></p></li>
<li><p><a class="reference internal" href="#sort"><span class="std std-ref">Uninterpreted sorts</span></a> are used to represent unknown types</p></li>
</ul>
<nav class="contents" id="contents">
<p class="topic-title">Contents</p>
<ul class="simple">
<li><p><a class="reference internal" href="#types" id="id6">Types</a></p>
<ul>
<li><p><a class="reference internal" href="#syntax" id="id7">Syntax</a></p></li>
<li><p><a class="reference internal" href="#solidity-types" id="id8">Solidity Types</a></p>
<ul>
<li><p><a class="reference internal" href="#integer-types" id="id9">Integer types</a></p></li>
<li><p><a class="reference internal" href="#array-access" id="id10">Array access</a></p></li>
<li><p><a class="reference internal" href="#user-defined-types" id="id11">User-defined types</a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#additional-cvl-types" id="id12">Additional CVL types</a></p>
<ul>
<li><p><a class="reference internal" href="#the-mathint-type" id="id13">The <code class="docutils literal notranslate"><span class="pre">mathint</span></code> type</a></p></li>
<li><p><a class="reference internal" href="#the-env-type" id="id14">The <code class="docutils literal notranslate"><span class="pre">env</span></code> type</a></p></li>
<li><p><a class="reference internal" href="#the-method-and-calldataarg-types" id="id15">The <code class="docutils literal notranslate"><span class="pre">method</span></code> and <code class="docutils literal notranslate"><span class="pre">calldataarg</span></code> types</a></p></li>
<li><p><a class="reference internal" href="#the-storage-type" id="id16">The <code class="docutils literal notranslate"><span class="pre">storage</span></code> type</a></p></li>
<li><p><a class="reference internal" href="#uninterpreted-sorts" id="id17">Uninterpreted sorts</a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#conversions-between-cvl-and-solidity-types" id="id18">Conversions between CVL and Solidity types</a></p></li>
</ul>
</li>
</ul>
</nav>
<section id="syntax">
<h2><a class="toc-backref" href="#id7" role="doc-backlink">Syntax</a><a class="headerlink" href="#syntax" title="Link to this heading"></a></h2>
<p>The syntax for types in CVL is given by the following <a class="reference internal" href="overview.html#ebnf-syntax"><span class="std std-ref">EBNF grammar</span></a>:</p>
<div class="highlight-default notranslate"><div class="highlight"><pre id="codecell0"><span></span><span class="n">basic_type</span> <span class="p">:</span><span class="o">:=</span> <span class="s2">"int*"</span> <span class="o">|</span> <span class="s2">"uint*"</span> <span class="o">|</span> <span class="s2">"address"</span> <span class="o">|</span> <span class="s2">"bool"</span>
             <span class="o">|</span> <span class="s2">"string"</span> <span class="o">|</span> <span class="s2">"bytes*"</span>
             <span class="o">|</span> <span class="n">basic_type</span> <span class="s2">"["</span> <span class="p">[</span> <span class="n">number</span> <span class="p">]</span> <span class="s2">"]"</span>
             <span class="o">|</span> <span class="nb">id</span> <span class="s2">"."</span> <span class="nb">id</span>

<span class="n">evm_type</span> <span class="p">:</span><span class="o">:=</span> <span class="n">basic_type</span>
           <span class="o">|</span> <span class="s2">"("</span> <span class="n">evm_type</span> <span class="p">{</span> <span class="s2">","</span> <span class="n">evm_type</span> <span class="p">}</span> <span class="s2">")"</span>
           <span class="o">|</span> <span class="n">evm_type</span> <span class="s2">"["</span> <span class="p">[</span> <span class="n">number</span> <span class="p">]</span> <span class="s2">"]"</span>

<span class="n">cvl_type</span> <span class="p">:</span><span class="o">:=</span> <span class="n">basic_type</span>
           <span class="o">|</span> <span class="s2">"mathint"</span> <span class="o">|</span> <span class="s2">"calldataarg"</span> <span class="o">|</span> <span class="s2">"storage"</span> <span class="o">|</span> <span class="s2">"env"</span> <span class="o">|</span> <span class="s2">"method"</span>
           <span class="o">|</span> <span class="nb">id</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell0">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>See <a class="reference internal" href="basics.html"><span class="doc">Basic Syntax</span></a> for the <code class="docutils literal notranslate"><span class="pre">id</span></code> and <code class="docutils literal notranslate"><span class="pre">number</span></code> productions.</p>
</section>
<section id="solidity-types">
<span id="id1"></span><h2><a class="toc-backref" href="#id8" role="doc-backlink">Solidity Types</a><a class="headerlink" href="#solidity-types" title="Link to this heading"></a></h2>
<p>You can declare variables in CVL of any of the following <a class="reference external" href="https://docs.soliditylang.org/en/v0.8.11/types.html">solidity types</a>:</p>
<ul class="simple">
<li><p><code class="docutils literal notranslate"><span class="pre">int</span></code>, <code class="docutils literal notranslate"><span class="pre">uint</span></code>, and the sized variants such as <code class="docutils literal notranslate"><span class="pre">uint256</span></code> and <code class="docutils literal notranslate"><span class="pre">int8</span></code></p></li>
<li><p><code class="docutils literal notranslate"><span class="pre">bool</span></code>, <code class="docutils literal notranslate"><span class="pre">address</span></code>, and the sized <code class="docutils literal notranslate"><span class="pre">bytes</span></code> variants (<code class="docutils literal notranslate"><span class="pre">bytes1</span></code> through <code class="docutils literal notranslate"><span class="pre">bytes32</span></code>)</p></li>
<li><p><code class="docutils literal notranslate"><span class="pre">string</span></code> and <code class="docutils literal notranslate"><span class="pre">bytes</span></code></p></li>
<li><p><a class="reference internal" href="#arrays"><span class="std std-ref">Single-dimensional arrays</span></a> (both statically- and dynamically-sized)</p></li>
<li><p><a class="reference internal" href="#user-types"><span class="std std-ref">Enum types, struct types, and type aliases</span></a> that are
defined in Solidity contracts.</p></li>
</ul>
<p>The following are not directly supported in CVL, although you can interact with
contracts that use them (see <a class="reference internal" href="#type-conversions"><span class="std std-ref">Conversions between CVL and Solidity types</span></a>):</p>
<ul class="simple">
<li><p>Function types</p></li>
<li><p>Multi-dimensional arrays</p></li>
<li><p>Mappings</p></li>
</ul>
<section id="integer-types">
<span id="math-types"></span><h3><a class="toc-backref" href="#id9" role="doc-backlink">Integer types</a><a class="headerlink" href="#integer-types" title="Link to this heading"></a></h3>
<p>CVL integer types are mostly identical to Solidity integer types.  See
<a class="reference internal" href="expr.html#math-ops"><span class="std std-ref">Basic operations</span></a> for details.</p>
</section>
<section id="array-access">
<span id="arrays"></span><h3><a class="toc-backref" href="#id10" role="doc-backlink">Array access</a><a class="headerlink" href="#array-access" title="Link to this heading"></a></h3>
<p>Array accesses in CVL behave slightly differently from Solidity accesses.  In
Solidity, an out-of-bounds array access will result in an exception, causing the
transaction to revert.</p>
<p>By contrast, out-of-bounds array accesses in CVL are treated as undefined
values: if <code class="docutils literal notranslate"><span class="pre">i</span> <span class="pre">&gt;</span> <span class="pre">a.length</span></code> then the Prover considers every possible value for
<code class="docutils literal notranslate"><span class="pre">a[i]</span></code> when constructing counterexamples.</p>
<p>CVL arrays also have the following limitations:</p>
<ul class="simple">
<li><p>Only single dimensional arrays are supported</p></li>
<li><p>The <code class="docutils literal notranslate"><span class="pre">push</span></code> and <code class="docutils literal notranslate"><span class="pre">pop</span></code> methods are not supported.
You can use <a class="reference internal" href="../prover/approx/harnessing.html"><span class="doc std std-doc">harnessing</span></a> to work around these limitations.</p></li>
</ul>
</section>
<section id="user-defined-types">
<span id="user-types"></span><h3><a class="toc-backref" href="#id11" role="doc-backlink">User-defined types</a><a class="headerlink" href="#user-defined-types" title="Link to this heading"></a></h3>
<p>Specifications can use structs, enums, or user-defined value types that are
defined in Solidity contracts.</p>
<p>Struct types have the following limitations:</p>
<ul class="simple">
<li><p>Assignment to struct fields is unsupported.  You can achieve the same effect
using a <a class="reference internal" href="statements.html#require"><span class="std std-ref">require</span></a> statement.  For example, instead of <code class="docutils literal notranslate"><span class="pre">s.f</span> <span class="pre">=</span> <span class="pre">x;</span></code> you can
write <code class="docutils literal notranslate"><span class="pre">require</span> <span class="pre">s.f</span> <span class="pre">==</span> <span class="pre">x;</span></code>.  However, be aware that <code class="docutils literal notranslate"><span class="pre">require</span></code> statements can
introduce <a class="reference internal" href="../user-guide/glossary.html#term-vacuity"><span class="xref std std-term">vacuity</span></a> if there are multiple conflicting constraints.</p></li>
</ul>
<p>All user-defined type names (structs, enums, and user-defined values) must be
explicitly qualified by the contract name that contains them.</p>
<ul class="simple">
<li><p>For types defined within a contract, the named contract must be the contract
containing the type definition.  Note that if a contract inherits a type from
a supertype, the contract that actually contains the type must be
named, not the inheriting contract.</p></li>
<li><p>For types defined at the file level, the named contract can be any contract
in the <a class="reference internal" href="../user-guide/glossary.html#term-0"><span class="xref std std-term">scene</span></a> from which the type is visible.</p></li>
</ul>
<div class="admonition warning">
<p class="admonition-title">Warning</p>
<p>If you do not qualify the type name with a contract name, the type name will be
misinterpreted as a <a class="reference internal" href="#sort"><span class="std std-ref">sort</span></a>.</p>
</div>
<p>For example, consider the files <code class="docutils literal notranslate"><span class="pre">parent.sol</span></code> and <code class="docutils literal notranslate"><span class="pre">child.sol</span></code>, defined as follows:</p>
<div class="literal-block-wrapper docutils container" id="id3">
<div class="code-block-caption"><span class="caption-text">parent.sol</span><a class="headerlink" href="#id3" title="Link to this code"></a></div>
<div class="highlight-solidity notranslate"><div class="highlight"><pre id="codecell1"><span></span>type<span class="w"> </span>ParentFileType<span class="w"> </span><span class="kt">is</span><span class="w"> </span><span class="kt">uint64</span><span class="p">;</span>

<span class="k">contract</span><span class="w"> </span><span class="ni">Parent</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kt">enum</span><span class="w"> </span><span class="nv">ParentContractType</span><span class="w"> </span><span class="p">{</span><span class="w"> </span>member1<span class="p">,</span><span class="w"> </span>member2<span class="w"> </span><span class="p">}</span>
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
</div>
<div class="literal-block-wrapper docutils container" id="id4">
<div class="code-block-caption"><span class="caption-text">child.sol</span><a class="headerlink" href="#id4" title="Link to this code"></a></div>
<div class="highlight-solidity notranslate"><div class="highlight"><pre id="codecell2"><span></span><span class="kt">import</span><span class="w"> </span><span class="s1">'parent.sol'</span><span class="p">;</span>

type<span class="w"> </span>ChildFileType<span class="w"> </span><span class="kt">is</span><span class="w"> </span><span class="kt">bool</span><span class="p">;</span>

<span class="k">contract</span><span class="w"> </span><span class="ni">Child</span><span class="w"> </span><span class="kt">is</span><span class="w"> </span>Parent<span class="w"> </span><span class="p">{</span>
<span class="w">    </span>type<span class="w"> </span>alias<span class="w"> </span>ChildContractType<span class="w"> </span><span class="kt">is</span><span class="w"> </span><span class="kt">uint128</span><span class="p">;</span>
<span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell2">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</div>
<p>Given these definitions, types can be named as follows:</p>
<div class="literal-block-wrapper docutils container" id="id5">
<div class="code-block-caption"><span class="caption-text">child.spec</span><a class="headerlink" href="#id5" title="Link to this code"></a></div>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell3"><span></span><span class="c1">// valid types</span>
Parent<span class="p">.</span>ParentFileType<span class="w">     </span>valid1<span class="p">;</span>
Child<span class="p">.</span>ChildFileType<span class="w">       </span>valid2<span class="p">;</span>
Parent<span class="p">.</span>ParentContractType<span class="w"> </span>valid3<span class="p">;</span>

<span class="c1">// invalid types</span>
Child<span class="p">.</span>ParentContractType<span class="w">  </span>invalid1<span class="p">;</span><span class="w"> </span><span class="c1">// user-defined types are not inherited</span>
Child<span class="p">.</span>ParentFileType<span class="w">      </span>invalid2<span class="p">;</span><span class="w"> </span><span class="c1">// user-defined types are not inherited</span>
Parent<span class="p">.</span>ChildFileType<span class="w">      </span>invalid3<span class="p">;</span><span class="w"> </span><span class="c1">// ChildFileType is not visible in Parent</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell3">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</div>
</section>
</section>
<section id="additional-cvl-types">
<h2><a class="toc-backref" href="#id12" role="doc-backlink">Additional CVL types</a><a class="headerlink" href="#additional-cvl-types" title="Link to this heading"></a></h2>
<section id="the-mathint-type">
<span id="mathint"></span><h3><a class="toc-backref" href="#id13" role="doc-backlink">The <code class="docutils literal notranslate"><span class="pre">mathint</span></code> type</a><a class="headerlink" href="#the-mathint-type" title="Link to this heading"></a></h3>
<p>Arithmetic overflow and underflow are difficult to reason about and often lead
to bugs.  To avoid this complexity, CVL provides the <code class="docutils literal notranslate"><span class="pre">mathint</span></code> type that can
represent an integer of any size; operations on <code class="docutils literal notranslate"><span class="pre">mathint</span></code>s can never overflow
or underflow.</p>
<p>See <a class="reference internal" href="expr.html#math-ops"><span class="std std-ref">Basic operations</span></a> for details on mathematical operations and casting
between <code class="docutils literal notranslate"><span class="pre">mathint</span></code> and Solidity integer types.</p>
</section>
<section id="the-env-type">
<span id="env"></span><h3><a class="toc-backref" href="#id14" role="doc-backlink">The <code class="docutils literal notranslate"><span class="pre">env</span></code> type</a><a class="headerlink" href="#the-env-type" title="Link to this heading"></a></h3>
<p>Rules often reason about the effects of multiple transactions.  In different
transactions, the global <a class="reference external" href="https://docs.soliditylang.org/en/v0.8.11/units-and-global-variables.html#special-variables-and-functions">Solidity variables</a> (such as <code class="docutils literal notranslate"><span class="pre">msg.sender</span></code>
or <code class="docutils literal notranslate"><span class="pre">block.timestamp</span></code>) may have different values.</p>
<p>To support reasoning about multiple transactions, CVL groups some of the
solidity global variables into an “environment”: an object of the special type
<code class="docutils literal notranslate"><span class="pre">env</span></code>.  Environments must be passed as the first argument of a call from CVL
into a contract function (unless the contract function is declared
<a class="reference internal" href="methods.html#envfree"><span class="std std-ref">envfree</span></a>).</p>
<p>For example, to call a Solidity function <code class="docutils literal notranslate"><span class="pre">deposit(uint</span> <span class="pre">amount)</span></code>, a spec must
explicitly pass in an additional environment argument:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell4"><span></span><span class="k">rule</span><span class="w"> </span><span class="nc">check_deposit</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kt">env</span><span class="w"> </span>e<span class="p">;</span>
<span class="w">    </span><span class="kt">uint</span><span class="w"> </span>amount<span class="p">;</span>
<span class="w">    </span>deposit<span class="p">(</span>e<span class="p">,</span><span class="w"> </span>amount<span class="p">);</span><span class="w"> </span><span class="c1">// increases e.msg.sender's balance by `amount`</span>
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
<p>The value of the Solidity global variables can be extracted from the <code class="docutils literal notranslate"><span class="pre">env</span></code>
object using a field-like syntax.  The following fields are available on an
environment <code class="docutils literal notranslate"><span class="pre">e</span></code>:</p>
<ul class="simple">
<li><p><code class="docutils literal notranslate"><span class="pre">e.msg.sender</span></code>&nbsp;- address of the sender of the message</p></li>
<li><p><code class="docutils literal notranslate"><span class="pre">e.msg.value</span></code>&nbsp;- number of Wei sent with the message</p></li>
<li><p><code class="docutils literal notranslate"><span class="pre">e.block.number</span></code>&nbsp;- current block number</p></li>
<li><p><code class="docutils literal notranslate"><span class="pre">e.block.timestamp</span></code>&nbsp;- current block’s time stamp</p></li>
<li><p><code class="docutils literal notranslate"><span class="pre">e.block.basefee</span></code> - current block’s base fee</p></li>
<li><p><code class="docutils literal notranslate"><span class="pre">e.block.coinbase</span></code> - current block’s coinbase</p></li>
<li><p><code class="docutils literal notranslate"><span class="pre">e.block.difficulty</span></code> - current block’s difficulty</p></li>
<li><p><code class="docutils literal notranslate"><span class="pre">e.block.gaslimit</span></code> - current block’s gas limit</p></li>
<li><p><code class="docutils literal notranslate"><span class="pre">e.tx.origin</span></code>&nbsp;- original message sender</p></li>
</ul>
<p>The remaining solidity global variables are not accessible from CVL.</p>
</section>
<section id="the-method-and-calldataarg-types">
<span id="calldataarg"></span><span id="method-type"></span><h3><a class="toc-backref" href="#id15" role="doc-backlink">The <code class="docutils literal notranslate"><span class="pre">method</span></code> and <code class="docutils literal notranslate"><span class="pre">calldataarg</span></code> types</a><a class="headerlink" href="#the-method-and-calldataarg-types" title="Link to this heading"></a></h3>
<div class="versionchanged">
<p><span class="versionmodified changed">Changed in version 5.0: </span>Formerly, parametric method calls would only call methods of <code class="docutils literal notranslate"><span class="pre">currentContract</span></code>;
now they call methods of all contracts.  This version also introduced the
<code class="docutils literal notranslate"><span class="pre">f.contract</span></code> field.</p>
</div>
<p>An important feature of CVL is the ability to reason about the effects of an
arbitrary method called with arbitrary arguments.  To support this, CVL
provides the <code class="docutils literal notranslate"><span class="pre">method</span></code> type to represent an arbitrary method, and the
<code class="docutils literal notranslate"><span class="pre">calldataarg</span></code> type to represent an arbitrary set of arguments.</p>
<p>For example, the following rule checks that <em>no method</em> can decrease the user’s
balance:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell5"><span></span><span class="k">rule</span><span class="w"> </span><span class="nc">balance_increasing</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kt">address</span><span class="w"> </span>user<span class="p">;</span>
<span class="w">    </span><span class="kt">uint</span><span class="w"> </span>balance_before<span class="w"> </span><span class="o">=</span><span class="w"> </span>balance<span class="p">(</span>user<span class="p">);</span>

<span class="w">    </span><span class="kt">method</span><span class="w"> </span>f<span class="p">;</span>
<span class="w">    </span><span class="kt">env</span><span class="w"> </span>e<span class="p">;</span>
<span class="w">    </span><span class="kt">calldataarg</span><span class="w"> </span>args<span class="p">;</span>

<span class="w">    </span>f<span class="p">(</span>e<span class="p">,</span>args<span class="p">);</span>

<span class="w">    </span><span class="kt">uint</span><span class="w"> </span>balance_after<span class="w"> </span><span class="o">=</span><span class="w"> </span>balance<span class="p">(</span>user<span class="p">);</span>
<span class="w">    </span><span class="kr">assert</span><span class="w"> </span>balance_after<span class="w"> </span><span class="o">&gt;=</span><span class="w"> </span>balance_before<span class="p">,</span><span class="w"> </span><span class="s2">"balance must be increasing"</span><span class="p">;</span>
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
<p>Since <code class="docutils literal notranslate"><span class="pre">f</span></code>, <code class="docutils literal notranslate"><span class="pre">e</span></code>, and <code class="docutils literal notranslate"><span class="pre">args</span></code> are not given values, the Prover will consider every
possible assignment.  This means that when evaluating the call to <code class="docutils literal notranslate"><span class="pre">f(e,args)</span></code>,
the Prover will check the rule on every method of every contract on the
<a class="reference internal" href="../user-guide/glossary.html#term-0"><span class="xref std std-term">scene</span></a>, with every possible set of method arguments.</p>
<p>See <a class="reference internal" href="rules.html#parametric-rules"><span class="std std-ref">Parametric rules</span></a> for more information about how rules that declare
method variables are verified.</p>
<p>Variables of type <code class="docutils literal notranslate"><span class="pre">method</span></code> can only be declared as an argument to the rule or
directly in the body of a rule.  They may not be nested inside of <code class="docutils literal notranslate"><span class="pre">if</span></code>
statements or declared in CVL functions.  They may be passed as arguments to
CVL functions.</p>
<p>Properties of methods can be extracted from <code class="docutils literal notranslate"><span class="pre">method</span></code> variables using a
field-like syntax.  The following fields are available on a method <code class="docutils literal notranslate"><span class="pre">m</span></code>:</p>
<ul class="simple">
<li><p><code class="docutils literal notranslate"><span class="pre">m.selector</span></code>  &nbsp;- the ABI signature of the method</p></li>
<li><p><code class="docutils literal notranslate"><span class="pre">m.isPure</span></code>&nbsp;    - true when m is declared with the pure attribute</p></li>
<li><p><code class="docutils literal notranslate"><span class="pre">m.isView</span></code>&nbsp;    - true when m is declared with the view attribute</p></li>
<li><p><code class="docutils literal notranslate"><span class="pre">m.isFallback</span></code> - true when <code class="docutils literal notranslate"><span class="pre">m</span></code> is the fallback function</p></li>
<li><p><code class="docutils literal notranslate"><span class="pre">m.numberOfArguments</span></code>&nbsp;- the number of arguments to method m</p></li>
<li><p><code class="docutils literal notranslate"><span class="pre">m.contract</span></code>   - the receiver contract for the method</p></li>
</ul>
<p>There is no way to examine the contents of a <code class="docutils literal notranslate"><span class="pre">calldataarg</span></code> variable, because
the type of its contents vary depending on which method the Prover is checking.
The only thing you can do with it is pass it as an argument to a contract
method call. It is possible to work around this limitation; see
<a class="reference internal" href="../user-guide/patterns/partial-apply.html#partially-parametric-rules"><span class="std std-ref">Partially Parametric Rules</span></a> for further details.</p>
</section>
<section id="the-storage-type">
<span id="storage-type"></span><h3><a class="toc-backref" href="#id16" role="doc-backlink">The <code class="docutils literal notranslate"><span class="pre">storage</span></code> type</a><a class="headerlink" href="#the-storage-type" title="Link to this heading"></a></h3>
<p>The Certora Prover can compare different hypothetical transactions starting
from the same state and compare their results.  For example, checking a
property like “if you stake more, you earn more” requires comparing the earnings
after two possible transactions starting in the same initial state: one where
you stake less, and one where you stake more.</p>
<p>Properties that compare the results of different hypothetical executions are
sometimes called hyperproperties.</p>
<p>CVL supports this kind of specification using the special <code class="docutils literal notranslate"><span class="pre">storage</span></code> type.  A
variable of type <code class="docutils literal notranslate"><span class="pre">storage</span></code> represents a snapshot of the EVM storage and
the state of <a class="reference internal" href="ghosts.html#ghost-functions"><span class="std std-ref">ghosts</span></a> at a given point in time.</p>
<p>The EVM storage can be reset to a saved storage value <code class="docutils literal notranslate"><span class="pre">s</span></code> by appending <code class="docutils literal notranslate"><span class="pre">at</span> <span class="pre">s</span></code> to
the end of a function call.  For example, the following rule checks that “if you
stake more, you earn more”:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell6"><span></span><span class="k">rule</span><span class="w"> </span><span class="nc">bigger_stake_more_earnings</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kr">storage</span><span class="w"> </span>initial<span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="nb">lastStorage</span><span class="p">;</span>
<span class="w">    </span><span class="kt">env</span><span class="w"> </span>e<span class="p">;</span>

<span class="w">    </span><span class="kt">uint</span><span class="w"> </span>less<span class="p">;</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>more<span class="p">;</span>
<span class="w">    </span><span class="kr">require</span><span class="w"> </span>less<span class="w"> </span><span class="o">&lt;</span><span class="w"> </span>more<span class="p">;</span>

<span class="w">    </span><span class="c1">// stake less</span>
<span class="w">    </span>stake<span class="p">(</span>e<span class="p">,</span><span class="w"> </span>less<span class="p">)</span><span class="w"> </span>at<span class="w"> </span>initial<span class="p">;</span>
<span class="w">    </span>earnings_less<span class="w"> </span><span class="o">=</span><span class="w"> </span>earnings<span class="p">(</span>e<span class="p">);</span>

<span class="w">    </span><span class="c1">// stake more</span>
<span class="w">    </span>stake<span class="p">(</span>e<span class="p">,</span><span class="w"> </span>more<span class="p">)</span><span class="w"> </span>at<span class="w"> </span>initial<span class="p">;</span>
<span class="w">    </span>earnings_more<span class="w"> </span><span class="o">=</span><span class="w"> </span>earnings<span class="p">(</span>e<span class="p">);</span>

<span class="w">    </span><span class="kr">assert</span><span class="w"> </span>earnings_less<span class="w"> </span><span class="o">&lt;</span><span class="w"> </span>earnings_more<span class="p">,</span><span class="w"> </span><span class="s2">"if you stake more, you earn more"</span><span class="p">;</span>
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
<p>The <code class="docutils literal notranslate"><span class="pre">lastStorage</span></code> variable contains the state of the EVM after the most recent
contract function call.</p>
<p>Variables of <code class="docutils literal notranslate"><span class="pre">storage</span></code> type can also be compared for equality, allowing simple
rules that check the equivalence of different functions.  See
<a class="reference internal" href="expr.html#storage-comparison"><span class="std std-ref">Comparing storage</span></a> for details.</p>
</section>
<section id="uninterpreted-sorts">
<span id="sort"></span><h3><a class="toc-backref" href="#id17" role="doc-backlink">Uninterpreted sorts</a><a class="headerlink" href="#uninterpreted-sorts" title="Link to this heading"></a></h3>
</section>
</section>
<section id="conversions-between-cvl-and-solidity-types">
<span id="type-conversions"></span><h2><a class="toc-backref" href="#id18" role="doc-backlink">Conversions between CVL and Solidity types</a><a class="headerlink" href="#conversions-between-cvl-and-solidity-types" title="Link to this heading"></a></h2>
<p>When a specification calls a contract function, the Prover must convert the
arguments from their CVL types to the corresponding Solidity types, and must
convert the return values from Solidity back to CVL.  The Prover must also apply
these conversions when inlining <a class="reference internal" href="hooks.html#hooks"><span class="std std-ref">hooks</span></a> and <a class="reference internal" href="methods.html#expression-summary"><span class="std std-ref">function summaries</span></a>.</p>
<p>There are restrictions on what types can be converted from CVL to Solidity and
vice-versa.  In general, if a contract uses a type that is not convertible, you
can still interact with it, but you cannot access the corresponding values. For
example, if a contract function returns a type that isn’t convertible to CVL,
you can call the function from CVL but you cannot access its return type.
Similarly, if the function accepts an argument of a type that is not
representable in CVL, you can still call the function from CVL, but only by
providing it a generic <a class="reference internal" href="#calldataarg"><span class="std std-ref"> `calldataarg` argument</span></a>.</p>
<p>The following restrictions apply when converting between CVL types and Solidity
types:</p>
<ul class="simple">
<li><p>The type must be a <a class="reference internal" href="#solidity-types"><span class="std std-ref">valid CVL type</span></a> (except for
contract or interface types, which are represented by <code class="docutils literal notranslate"><span class="pre">address</span></code>).</p></li>
<li><p>Reference types (arrays and structs) can only be passed to Solidity
functions that expect <code class="docutils literal notranslate"><span class="pre">calldata</span></code> or <code class="docutils literal notranslate"><span class="pre">memory</span></code> arguments; there is no way to
pass <code class="docutils literal notranslate"><span class="pre">storage</span></code> arrays.</p></li>
<li><p>Arrays returned from Solidity can only be converted to CVL if their elements
have <a class="reference external" href="https://docs.soliditylang.org/en/v0.8.11/types.html#value-types">value types</a> that are representable in CVL.</p></li>
</ul>
<p>There are additional restrictions on the types for arguments and return values
for internal function summaries; see <a class="reference internal" href="methods.html#expression-summary"><span class="std std-ref">Expression summaries</span></a>.</p>
</section>
</section>


           </div>
          </div>
          <footer><div class="rst-footer-buttons" role="navigation" aria-label="Footer">
        <a href="basics.html" class="btn btn-neutral float-left" title="Basic Syntax" accesskey="p" rel="prev"><span class="fa fa-arrow-circle-left" aria-hidden="true"></span> Previous</a>
        <a href="expr.html" class="btn btn-neutral float-right" title="Expressions" accesskey="n" rel="next">Next <span class="fa fa-arrow-circle-right" aria-hidden="true"></span></a>
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