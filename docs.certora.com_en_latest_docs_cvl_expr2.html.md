<!DOCTYPE html><html class="writer-html5" lang="en" data-content_root="../../"><head>
  <meta charset="utf-8"><meta name="viewport" content="width=device-width, initial-scale=1">

  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Expressions — Certora Prover Documentation 0.0 documentation</title>
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
    <link rel="next" title="Statements" href="statements.html">
    <link rel="prev" title="Types" href="types.html"> 
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
<li class="toctree-l2"><a class="reference internal" href="types.html">Types</a></li>
<li class="toctree-l2 current" aria-expanded="true"><a class="reference internal current" href="#" aria-expanded="true"><button class="toctree-expand" title="Open/close menu"></button>Expressions</a><ul>
<li class="toctree-l3"><a class="reference internal" href="#syntax">Syntax</a></li>
<li class="toctree-l3"><a class="reference internal" href="#basic-operations">Basic operations</a></li>
<li class="toctree-l3"><a class="reference internal" href="#struct-comparison">Struct Comparison</a></li>
<li class="toctree-l3"><a class="reference internal" href="#extended-logical-operations">Extended logical operations</a></li>
<li class="toctree-l3"><a class="reference internal" href="#ghost-mapping-sums">Ghost Mapping Sums</a></li>
<li class="toctree-l3"><a class="reference internal" href="#accessing-fields-and-arrays">Accessing fields and arrays</a></li>
<li class="toctree-l3"><a class="reference internal" href="#contracts-method-signatures-and-their-properties">Contracts, method signatures and their properties</a></li>
<li class="toctree-l3"><a class="reference internal" href="#special-variables-and-fields">Special variables and fields</a></li>
<li class="toctree-l3"><a class="reference internal" href="#calling-contract-functions"><button class="toctree-expand" title="Open/close menu"></button>Calling contract functions</a><ul>
<li class="toctree-l4"><a class="reference internal" href="#type-restrictions">Type restrictions</a></li>
</ul>
</li>
<li class="toctree-l3"><a class="reference internal" href="#comparing-storage">Comparing storage</a></li>
<li class="toctree-l3"><a class="reference internal" href="#direct-storage-access"><button class="toctree-expand" title="Open/close menu"></button>Direct storage access</a><ul>
<li class="toctree-l4"><a class="reference internal" href="#direct-storage-havoc">Direct storage havoc</a></li>
<li class="toctree-l4"><a class="reference internal" href="#direct-immutable-access">Direct immutable access</a></li>
</ul>
</li>
<li class="toctree-l3"><a class="reference internal" href="#built-in-functions"><button class="toctree-expand" title="Open/close menu"></button>Built-in Functions</a><ul>
<li class="toctree-l4"><a class="reference internal" href="#hashing">Hashing</a></li>
<li class="toctree-l4"><a class="reference internal" href="#ecrecover">ECRecover</a></li>
</ul>
</li>
</ul>
</li>
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
      <li class="breadcrumb-item active">Expressions</li>
      <li class="wy-breadcrumbs-aside">
            <a href="../../_sources/docs/cvl/expr.md.txt" rel="nofollow"> View page source</a>
      </li>
  </ul>
  <hr>
</div>
          <div role="main" class="document" itemscope="itemscope" itemtype="http://schema.org/Article">
           <div itemprop="articleBody">
             
  <section id="expressions">
<h1><a class="toc-backref" href="#id6" role="doc-backlink">Expressions</a><a class="headerlink" href="#expressions" title="Link to this heading"></a></h1>
<p>A CVL expression is anything that represents a value.  This page documents all
possible expressions in CVL and explains how they are evaluated.</p>
<nav class="contents" id="contents">
<p class="topic-title">Contents</p>
<ul class="simple">
<li><p><a class="reference internal" href="#expressions" id="id6">Expressions</a></p>
<ul>
<li><p><a class="reference internal" href="#syntax" id="id7">Syntax</a></p></li>
<li><p><a class="reference internal" href="#basic-operations" id="id8">Basic operations</a></p></li>
<li><p><a class="reference internal" href="#struct-comparison" id="id9">Struct Comparison</a></p></li>
<li><p><a class="reference internal" href="#extended-logical-operations" id="id10">Extended logical operations</a></p></li>
<li><p><a class="reference internal" href="#ghost-mapping-sums" id="id11">Ghost Mapping Sums</a></p></li>
<li><p><a class="reference internal" href="#accessing-fields-and-arrays" id="id12">Accessing fields and arrays</a></p></li>
<li><p><a class="reference internal" href="#contracts-method-signatures-and-their-properties" id="id13">Contracts, method signatures and their properties</a></p></li>
<li><p><a class="reference internal" href="#special-variables-and-fields" id="id14">Special variables and fields</a></p></li>
<li><p><a class="reference internal" href="#calling-contract-functions" id="id15">Calling contract functions</a></p>
<ul>
<li><p><a class="reference internal" href="#type-restrictions" id="id16">Type restrictions</a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#comparing-storage" id="id17">Comparing storage</a></p></li>
<li><p><a class="reference internal" href="#direct-storage-access" id="id18">Direct storage access</a></p>
<ul>
<li><p><a class="reference internal" href="#direct-storage-havoc" id="id19">Direct storage havoc</a></p></li>
<li><p><a class="reference internal" href="#direct-immutable-access" id="id20">Direct immutable access</a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#built-in-functions" id="id21">Built-in Functions</a></p>
<ul>
<li><p><a class="reference internal" href="#hashing" id="id22">Hashing</a></p>
<ul>
<li><p><a class="reference internal" href="#example" id="id23">Example</a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#ecrecover" id="id24">ECRecover</a></p>
<ul>
<li><p><a class="reference internal" href="#id5" id="id25">Example</a></p></li>
</ul>
</li>
</ul>
</li>
</ul>
</li>
</ul>
</nav>
<section id="syntax">
<h2><a class="toc-backref" href="#id7" role="doc-backlink">Syntax</a><a class="headerlink" href="#syntax" title="Link to this heading"></a></h2>
<p>The syntax for CVL expressions is given by the following <a class="reference internal" href="overview.html#ebnf-syntax"><span class="std std-ref">EBNF grammar</span></a>:</p>
<div class="highlight-default notranslate"><div class="highlight"><pre id="codecell0"><span></span><span class="n">expr</span> <span class="p">:</span><span class="o">:=</span> <span class="n">literal</span>
       <span class="o">|</span> <span class="n">unop</span> <span class="n">expr</span>
       <span class="o">|</span> <span class="n">expr</span> <span class="n">binop</span> <span class="n">expr</span>
       <span class="o">|</span> <span class="s2">"("</span> <span class="n">exprs</span> <span class="s2">")"</span>
       <span class="o">|</span> <span class="n">expr</span> <span class="s2">"?"</span> <span class="n">expr</span> <span class="s2">":"</span> <span class="n">expr</span>
       <span class="o">|</span> <span class="p">[</span> <span class="s2">"forall"</span> <span class="o">|</span> <span class="s2">"exists"</span> <span class="p">]</span> <span class="nb">type</span> <span class="nb">id</span> <span class="s2">"."</span> <span class="n">expr</span>
       <span class="o">|</span> <span class="p">[</span> <span class="s2">"sum"</span> <span class="o">|</span> <span class="s2">"usum"</span> <span class="p">]</span> <span class="nb">type</span> <span class="nb">id</span> <span class="p">{</span> <span class="s2">","</span> <span class="nb">type</span> <span class="nb">id</span> <span class="p">}</span> <span class="s2">"."</span> <span class="n">expr</span>

       <span class="o">|</span> <span class="n">expr</span> <span class="s2">"."</span> <span class="nb">id</span>
       <span class="o">|</span> <span class="nb">id</span> <span class="p">[</span> <span class="s2">"["</span> <span class="n">expr</span> <span class="s2">"]"</span> <span class="p">{</span> <span class="s2">"["</span> <span class="n">expr</span> <span class="s2">"]"</span> <span class="p">}</span> <span class="p">]</span>
       <span class="o">|</span> <span class="nb">id</span> <span class="s2">"("</span> <span class="n">types</span> <span class="s2">")"</span>

       <span class="o">|</span> <span class="n">function_call</span>

       <span class="o">|</span> <span class="n">expr</span> <span class="s2">"in"</span> <span class="nb">id</span>

<span class="n">function_call</span> <span class="p">:</span><span class="o">:=</span>
       <span class="o">|</span> <span class="p">[</span> <span class="nb">id</span> <span class="s2">"."</span> <span class="p">]</span> <span class="nb">id</span>
         <span class="p">[</span> <span class="s2">"@"</span> <span class="p">(</span> <span class="s2">"norevert"</span> <span class="o">|</span> <span class="s2">"withrevert"</span> <span class="o">|</span> <span class="s2">"dontsummarize"</span> <span class="p">)</span> <span class="p">]</span>
         <span class="s2">"("</span> <span class="n">exprs</span> <span class="s2">")"</span>
         <span class="p">[</span> <span class="s2">"at"</span> <span class="nb">id</span> <span class="p">]</span>


<span class="n">literal</span> <span class="p">:</span><span class="o">:=</span> <span class="s2">"true"</span> <span class="o">|</span> <span class="s2">"false"</span> <span class="o">|</span> <span class="n">number</span> <span class="o">|</span> <span class="n">string</span>

<span class="n">unop</span>  <span class="p">:</span><span class="o">:=</span> <span class="s2">"~"</span> <span class="o">|</span> <span class="s2">"!"</span> <span class="o">|</span> <span class="s2">"-"</span>

<span class="n">binop</span> <span class="p">:</span><span class="o">:=</span> <span class="s2">"+"</span> <span class="o">|</span> <span class="s2">"-"</span> <span class="o">|</span> <span class="s2">"*"</span> <span class="o">|</span> <span class="s2">"/"</span> <span class="o">|</span> <span class="s2">"%"</span> <span class="o">|</span> <span class="s2">"^"</span>
        <span class="o">|</span> <span class="s2">"&gt;"</span> <span class="o">|</span> <span class="s2">"&lt;"</span> <span class="o">|</span> <span class="s2">"=="</span> <span class="o">|</span> <span class="s2">"!="</span> <span class="o">|</span> <span class="s2">"&gt;="</span> <span class="o">|</span> <span class="s2">"&lt;="</span>
        <span class="o">|</span> <span class="s2">"&amp;"</span> <span class="o">|</span> <span class="s2">"|"</span> <span class="o">|</span> <span class="s2">"&lt;&lt;"</span> <span class="o">|</span> <span class="s2">"&gt;&gt;"</span> <span class="o">|</span> <span class="s2">"&amp;&amp;"</span> <span class="o">|</span> <span class="s2">"||"</span>
        <span class="o">|</span> <span class="s2">"=&gt;"</span> <span class="o">|</span> <span class="s2">"&lt;=&gt;"</span> <span class="o">|</span> <span class="s2">"xor"</span> <span class="o">|</span> <span class="s2">"&gt;&gt;&gt;"</span>

<span class="n">specials_fields</span> <span class="p">:</span><span class="o">:=</span>
           <span class="o">|</span> <span class="s2">"block"</span> <span class="s2">"."</span> <span class="p">[</span> <span class="s2">"number"</span> <span class="o">|</span> <span class="s2">"timestamp"</span> <span class="p">]</span>
           <span class="o">|</span> <span class="s2">"msg"</span>   <span class="s2">"."</span> <span class="p">[</span> <span class="s2">"address"</span> <span class="o">|</span> <span class="s2">"sender"</span> <span class="o">|</span> <span class="s2">"value"</span> <span class="p">]</span>
           <span class="o">|</span> <span class="s2">"tx"</span>    <span class="s2">"."</span> <span class="p">[</span> <span class="s2">"origin"</span> <span class="p">]</span>
           <span class="o">|</span> <span class="s2">"length"</span>
           <span class="o">|</span> <span class="s2">"selector"</span> <span class="o">|</span> <span class="s2">"isPure"</span> <span class="o">|</span> <span class="s2">"isView"</span> <span class="o">|</span> <span class="s2">"numberOfArguments"</span> <span class="o">|</span> <span class="s2">"isFallback"</span>

<span class="n">special_vars</span> <span class="p">:</span><span class="o">:=</span>
           <span class="o">|</span> <span class="s2">"lastReverted"</span>
           <span class="o">|</span> <span class="s2">"lastStorage"</span>
           <span class="o">|</span> <span class="s2">"allContracts"</span>
           <span class="o">|</span> <span class="s2">"lastMsgSig"</span>
           <span class="o">|</span> <span class="s2">"_"</span>
           <span class="o">|</span> <span class="s2">"max_uint"</span> <span class="o">|</span> <span class="s2">"max_address"</span> <span class="o">|</span> <span class="s2">"max_uint8"</span> <span class="o">|</span> <span class="o">...</span> <span class="o">|</span> <span class="s2">"max_uint256"</span>
           <span class="o">|</span> <span class="s2">"nativeBalances"</span>
           <span class="o">|</span> <span class="s2">"calledContract"</span>
           <span class="o">|</span> <span class="s2">"executingContract"</span>

<span class="n">cast_functions</span> <span class="p">:</span><span class="o">:=</span>
    <span class="o">|</span> <span class="n">require_functions</span> <span class="o">|</span> <span class="n">to_functions</span> <span class="o">|</span> <span class="n">assert_functions</span>

<span class="n">require_functions</span> <span class="p">:</span><span class="o">:=</span>
    <span class="o">|</span> <span class="s2">"require_uint8"</span> <span class="o">|</span> <span class="o">...</span> <span class="o">|</span> <span class="s2">"require_uint256"</span> <span class="o">|</span> <span class="s2">"require_int8"</span> <span class="o">|</span> <span class="o">...</span> <span class="o">|</span> <span class="s2">"require_int256"</span> <span class="o">|</span> <span class="s2">"require_address"</span>

<span class="n">to_functions</span> <span class="p">:</span><span class="o">:=</span>
    <span class="o">|</span> <span class="s2">"to_mathint"</span> <span class="o">|</span> <span class="s2">"to_bytes1"</span> <span class="o">|</span> <span class="o">...</span> <span class="o">|</span> <span class="s2">"to_bytes32"</span>

<span class="n">assert_functions</span> <span class="p">:</span><span class="o">:=</span>
   <span class="o">|</span> <span class="s2">"assert_uint8"</span> <span class="o">|</span> <span class="o">...</span> <span class="o">|</span> <span class="s2">"assert_uint256"</span> <span class="o">|</span> <span class="s2">"assert_int8"</span> <span class="o">|</span> <span class="o">...</span> <span class="o">|</span> <span class="s2">"assert_int256"</span> <span class="o">|</span> <span class="s2">"assert_address"</span>

<span class="n">contract</span> <span class="p">:</span><span class="o">:=</span> <span class="nb">id</span> <span class="o">|</span> <span class="s2">"currentContract"</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell0">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>See <a class="reference internal" href="basics.html"><span class="doc">Basic Syntax</span></a> for the <code class="docutils literal notranslate"><span class="pre">id</span></code>, <code class="docutils literal notranslate"><span class="pre">number</span></code>, and <code class="docutils literal notranslate"><span class="pre">string</span></code> productions.
See <a class="reference internal" href="types.html"><span class="doc">Types</span></a> for the <code class="docutils literal notranslate"><span class="pre">type</span></code> production.</p>
</section>
<section id="basic-operations">
<span id="math-ops"></span><h2><a class="toc-backref" href="#id8" role="doc-backlink">Basic operations</a><a class="headerlink" href="#basic-operations" title="Link to this heading"></a></h2>
<p>CVL provides the same basic arithmetic, comparison, bitwise, and logical
operations for basic types that solidity does, with a few differences listed
in this section and the next.  The <a class="reference external" href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Operator_Precedence#table">precedence and associativity rules</a>
are standard.</p>
<div class="admonition caution">
<p class="admonition-title">Caution</p>
<p>One significant difference between CVL and Solidity is that in Solidity, <code class="docutils literal notranslate"><span class="pre">^</span></code>
denotes bitwise exclusive or and <code class="docutils literal notranslate"><span class="pre">**</span></code> denotes exponentiation, whereas in CVL,
<code class="docutils literal notranslate"><span class="pre">^</span></code> denotes exponentiation and <code class="docutils literal notranslate"><span class="pre">xor</span></code> denotes exclusive or.</p>
</div>
<p>See <a class="reference internal" href="cvl2/changes.html#cvl2-integer-types"><span class="std std-ref">Changes to integer types</span></a> for more information about the interaction between
mathematical types and the meaning of mathematical operations.</p>
</section>
<section id="struct-comparison">
<span id="id1"></span><h2><a class="toc-backref" href="#id9" role="doc-backlink">Struct Comparison</a><a class="headerlink" href="#struct-comparison" title="Link to this heading"></a></h2>
<p>CVL supports equality comparison of structs under the following restrictions:</p>
<ul class="simple">
<li><p>The structs must be of the same type.</p></li>
<li><p>The structs (or any nested structs) don’t contain dynamic arrays. (<code class="docutils literal notranslate"><span class="pre">string</span></code> and <code class="docutils literal notranslate"><span class="pre">bytes</span></code> can be part of the struct)</p></li>
<li><p>There’s no support for comparison for structs fetched using direct-storage-access.</p></li>
</ul>
<p>Two structs will be evaluated as equal if and only if all the fields are equal.</p>
<p>For example:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell1"><span></span><span class="k">rule</span><span class="w"> </span><span class="nc">example</span><span class="p">(</span>MyContract<span class="p">.</span>MyStruct<span class="w"> </span>s<span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kt">env</span><span class="w"> </span>e<span class="p">;</span>
<span class="w">    </span><span class="kr">assert</span><span class="w"> </span>s<span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="nb">currentContract</span><span class="p">.</span>myStructGetter<span class="p">(</span>e<span class="p">);</span>
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
<section id="extended-logical-operations">
<span id="logic-exprs"></span><h2><a class="toc-backref" href="#id10" role="doc-backlink">Extended logical operations</a><a class="headerlink" href="#extended-logical-operations" title="Link to this heading"></a></h2>
<p>CVL also adds several useful logical operations:</p>
<ul>
<li><p>Like <code class="docutils literal notranslate"><span class="pre">&amp;&amp;</span></code> or <code class="docutils literal notranslate"><span class="pre">||</span></code>, an <em>implication</em> expression <code class="docutils literal notranslate"><span class="pre">expr1</span> <span class="pre">=&gt;</span> <span class="pre">expr2</span></code> requires
<code class="docutils literal notranslate"><span class="pre">expr1</span></code> and <code class="docutils literal notranslate"><span class="pre">expr2</span></code> to be boolean expressions and is itself a boolean
expression.  <code class="docutils literal notranslate"><span class="pre">expr1</span> <span class="pre">=&gt;</span> <span class="pre">expr2</span></code> evaluates to <code class="docutils literal notranslate"><span class="pre">false</span></code> if and only if <code class="docutils literal notranslate"><span class="pre">expr1</span></code>
evaluates to <code class="docutils literal notranslate"><span class="pre">true</span></code> and <code class="docutils literal notranslate"><span class="pre">expr2</span></code> evaluates to <code class="docutils literal notranslate"><span class="pre">false</span></code>.  <code class="docutils literal notranslate"><span class="pre">expr1</span> <span class="pre">=&gt;</span> <span class="pre">expr2</span></code> is
equivalent to <code class="docutils literal notranslate"><span class="pre">!expr1</span> <span class="pre">||</span> <span class="pre">expr2</span></code>.</p>
<p>For example, the statement <code class="docutils literal notranslate"><span class="pre">assert</span> <span class="pre">initialized</span> <span class="pre">=&gt;</span> <span class="pre">x</span> <span class="pre">&gt;</span> <span class="pre">0;</span></code> will only report
counterexamples where <code class="docutils literal notranslate"><span class="pre">initialized</span></code> is true but <code class="docutils literal notranslate"><span class="pre">x</span></code> is not positive.</p>
</li>
<li><p>The short-circuiting behavior of implications (<code class="docutils literal notranslate"><span class="pre">=&gt;</span></code>) and other boolean connectors in CVL mirrors the
short-circuiting behavior seen in standard logical operators (<code class="docutils literal notranslate"><span class="pre">&amp;&amp;</span></code> and <code class="docutils literal notranslate"><span class="pre">||</span></code>). In practical
terms, this implies that the evaluation process is terminated as soon as the final result
can be determined without necessitating further computation.
For example, when dealing with an implication expression like <code class="docutils literal notranslate"><span class="pre">expr1</span> <span class="pre">=&gt;</span> <span class="pre">expr2</span></code>, if the
evaluation of <code class="docutils literal notranslate"><span class="pre">expr1</span></code> results in false, there is no need to proceed with evaluating
<code class="docutils literal notranslate"><span class="pre">expr2</span></code> since the overall result is already known. This aligns with the common
short-circuiting behavior found in traditional logical operators.</p></li>
<li><p>Similarly, an <em>if and only if</em> expression (also called a <em>bidirectional implication</em>)
<code class="docutils literal notranslate"><span class="pre">expr1</span> <span class="pre">&lt;=&gt;</span> <span class="pre">expr2</span></code> requires <code class="docutils literal notranslate"><span class="pre">expr1</span></code> and <code class="docutils literal notranslate"><span class="pre">expr2</span></code> to be boolean
expressions and is itself a boolean expression.  <code class="docutils literal notranslate"><span class="pre">expr1</span> <span class="pre">&lt;=&gt;</span> <span class="pre">expr2</span></code> evaluates
to <code class="docutils literal notranslate"><span class="pre">true</span></code> if <code class="docutils literal notranslate"><span class="pre">expr1</span></code> and <code class="docutils literal notranslate"><span class="pre">expr2</span></code> evaluate to the same boolean value.</p>
<p>For example, the statement <code class="docutils literal notranslate"><span class="pre">assert</span> <span class="pre">balanceA</span> <span class="pre">&gt;</span> <span class="pre">0</span> <span class="pre">&lt;=&gt;</span> <span class="pre">balanceB</span> <span class="pre">&gt;</span> <span class="pre">0;</span></code> will
report a violation if exactly one of <code class="docutils literal notranslate"><span class="pre">balanceA</span></code> and <code class="docutils literal notranslate"><span class="pre">balanceB</span></code> is positive.</p>
</li>
<li><p>An <em>if-then-else</em> (<em>ITE</em>) expression of the form
<code class="docutils literal notranslate"><span class="pre">cond</span> <span class="pre">?</span> <span class="pre">expr1</span> <span class="pre">:</span> <span class="pre">expr2</span></code> requires <code class="docutils literal notranslate"><span class="pre">cond</span></code> to be a boolean expression and
requires <code class="docutils literal notranslate"><span class="pre">expr1</span></code> and <code class="docutils literal notranslate"><span class="pre">expr2</span></code> to have the same type; the entire
if-then-else expression has the same type as <code class="docutils literal notranslate"><span class="pre">expr1</span></code> and <code class="docutils literal notranslate"><span class="pre">expr2</span></code>.  The
expression <code class="docutils literal notranslate"><span class="pre">cond</span> <span class="pre">?</span> <span class="pre">expr1</span> <span class="pre">:</span> <span class="pre">expr2</span></code> should be read “if <code class="docutils literal notranslate"><span class="pre">cond</span></code> then <code class="docutils literal notranslate"><span class="pre">expr1</span></code>
else <code class="docutils literal notranslate"><span class="pre">expr2</span></code>.  If <code class="docutils literal notranslate"><span class="pre">cond</span></code> evaluates to <code class="docutils literal notranslate"><span class="pre">true</span></code> then the entire
expression evaluates to <code class="docutils literal notranslate"><span class="pre">expr1</span></code>; otherwise the entire expression evaluates
to <code class="docutils literal notranslate"><span class="pre">expr2</span></code>.</p>
<p>For example, the expression</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell2"><span></span><span class="kt">uint</span><span class="w"> </span>balance<span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="kt">address</span><span class="w"> </span><span class="o">==</span><span class="w"> </span>owner<span class="w"> </span><span class="o">?</span><span class="w"> </span>ownerBalance<span class="p">()</span>
<span class="w">                                </span><span class="o">:</span><span class="w"> </span>userBalance<span class="p">(</span><span class="kt">address</span><span class="p">);</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell2">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>will set <code class="docutils literal notranslate"><span class="pre">balance</span></code> to <code class="docutils literal notranslate"><span class="pre">ownerBalance()</span></code> if <code class="docutils literal notranslate"><span class="pre">address</span></code> is <code class="docutils literal notranslate"><span class="pre">owner</span></code>, and will set
it to <code class="docutils literal notranslate"><span class="pre">userBalance(address)</span></code> otherwise.</p>
<p>Conditional expressions are <em>short-circuiting</em>: if <code class="docutils literal notranslate"><span class="pre">expr1</span></code> or <code class="docutils literal notranslate"><span class="pre">expr2</span></code> have
side-effects (such as updating a <a class="reference internal" href="ghosts.html#ghost-variables"><span class="std std-ref">ghost variable</span></a>), only the
side-effects of the expression that is chosen are performed.</p>
<p>Regarding the logical operator precedence, <code class="docutils literal notranslate"><span class="pre">=&gt;</span></code> has higher precedence than <code class="docutils literal notranslate"><span class="pre">&lt;=&gt;</span></code>,
and unlike math operators both are <em>right</em> associative, so <code class="docutils literal notranslate"><span class="pre">expr1</span> <span class="pre">=&gt;</span> <span class="pre">expr2</span> <span class="pre">=&gt;</span> <span class="pre">expr3</span></code>
is equivalent to <code class="docutils literal notranslate"><span class="pre">expr1</span> <span class="pre">=&gt;</span> <span class="pre">(expr2</span> <span class="pre">=&gt;</span> <span class="pre">expr3)</span></code>.</p>
</li>
<li><p>A <em>universal</em> expression of the form <code class="docutils literal notranslate"><span class="pre">forall</span> <span class="pre">t</span> <span class="pre">v</span> <span class="pre">.</span> <span class="pre">expr</span></code> requires <code class="docutils literal notranslate"><span class="pre">t</span></code>
to be a <a class="reference internal" href="types.html"><span class="doc std std-doc">type</span></a> (such as <code class="docutils literal notranslate"><span class="pre">uint256</span></code> or <code class="docutils literal notranslate"><span class="pre">address</span></code>) and <code class="docutils literal notranslate"><span class="pre">v</span></code> to be
a variable name; <code class="docutils literal notranslate"><span class="pre">expr</span></code> should be a boolean expression and may refer to
the identifier <code class="docutils literal notranslate"><span class="pre">v</span></code>.  The expression evaluates to <code class="docutils literal notranslate"><span class="pre">true</span></code> if <em>every</em> possible
value of the variable <code class="docutils literal notranslate"><span class="pre">v</span></code> causes <code class="docutils literal notranslate"><span class="pre">expr</span></code> to evaluate to <code class="docutils literal notranslate"><span class="pre">true</span></code>.</p>
<p>For example, the statement</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell3"><span></span><span class="kr">require</span><span class="w"> </span><span class="p">(</span><span class="kr">forall</span><span class="w"> </span><span class="kt">address</span><span class="w"> </span>user<span class="w"> </span><span class="p">.</span><span class="w"> </span>balance<span class="p">(</span>user<span class="p">)</span><span class="w"> </span><span class="o">&lt;=</span><span class="w"> </span>balance<span class="p">(</span>biggestUser<span class="p">));</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell3">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>will ensure that every other user has a balance that is less than or equal
to the balance of <code class="docutils literal notranslate"><span class="pre">biggestUser</span></code>.</p>
</li>
<li><p>Like a universal expression, an <em>existential</em> expression of the form
<code class="docutils literal notranslate"><span class="pre">exists</span> <span class="pre">t</span> <span class="pre">v</span> <span class="pre">.</span> <span class="pre">expr</span></code> requires <code class="docutils literal notranslate"><span class="pre">t</span></code> to be a <a class="reference internal" href="types.html"><span class="doc std std-doc">type</span></a> and <code class="docutils literal notranslate"><span class="pre">v</span></code> to be a
variable name; <code class="docutils literal notranslate"><span class="pre">expr</span></code> should be a boolean expression and may refer to the
variable <code class="docutils literal notranslate"><span class="pre">v</span></code>.  The expression evaluates to <code class="docutils literal notranslate"><span class="pre">true</span></code> if there is <em>any</em> possible
value of the variable <code class="docutils literal notranslate"><span class="pre">v</span></code> that causes <code class="docutils literal notranslate"><span class="pre">expr</span></code> to evaluate to <code class="docutils literal notranslate"><span class="pre">true</span></code>.</p>
<p>For example, the statement</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell4"><span></span><span class="kr">require</span><span class="w"> </span><span class="p">(</span><span class="kr">exists</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>t<span class="w"> </span><span class="p">.</span><span class="w"> </span>priceAtTime<span class="p">(</span>t<span class="p">)</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">);</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell4">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>will ensure that there is some time for which the price is nonzero.</p>
</li>
</ul>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>The symbols <code class="docutils literal notranslate"><span class="pre">forall</span></code> and <code class="docutils literal notranslate"><span class="pre">exist</span></code> are sometimes referred to as <a class="reference internal" href="../user-guide/glossary.html#term-quantifier"><span class="xref std std-term">quantifier</span></a>s,
and expressions of the form <code class="docutils literal notranslate"><span class="pre">forall</span> <span class="pre">type</span> <span class="pre">v</span> <span class="pre">.</span> <span class="pre">e</span></code> and <code class="docutils literal notranslate"><span class="pre">exist</span> <span class="pre">type</span> <span class="pre">v</span> <span class="pre">.</span> <span class="pre">e</span></code> are
referred to as <a class="reference internal" href="../user-guide/glossary.html#term-quantified-expression"><span class="xref std std-term">quantified expression</span></a>s.</p>
</div>
<div class="admonition caution">
<p class="admonition-title">Caution</p>
<p><code class="docutils literal notranslate"><span class="pre">forall</span></code> and <code class="docutils literal notranslate"><span class="pre">exists</span></code> expressions are powerful and elegant ways to express rules
and invariants, but they require the Prover to consider all possible values of
a given type.  In some cases they can cause significant slowdowns for the
Prover.</p>
<p>If you have rules or invariants using <code class="docutils literal notranslate"><span class="pre">exists</span></code> that are running slowly or
timing out, you can remove the <code class="docutils literal notranslate"><span class="pre">exists</span></code> by manually computing the value that
exists.  For example, you might replace</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell5"><span></span><span class="kr">require</span><span class="w"> </span><span class="p">(</span><span class="kr">exists</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>t<span class="w"> </span><span class="p">.</span><span class="w"> </span>priceAtTime<span class="p">(</span>t<span class="p">)</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">);</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell5">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>with</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell6"><span></span><span class="kr">require</span><span class="w"> </span>priceAtTime<span class="p">(</span>startTime<span class="p">)</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">;</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell6">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</div>
<div class="admonition caution">
<p class="admonition-title">Caution</p>
<p>Calling contract functions within the body of a quantified expression is an
experimental feature and may not work as intended.</p>
</div>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>The Prover uses approximations that may cause spurious counterexamples in rules
that use quantifiers.  For example, a rule that requires a quantified statement
may produce a counterexample that doesn’t satisfy the requirement.  The
approximation is <a class="reference internal" href="../user-guide/glossary.html#term-sound"><span class="xref std std-term">sound</span></a>: it won’t cause violations to be hidden.  See
<a class="reference internal" href="../prover/approx/grounding.html#grounding"><span class="std std-ref">Quantifier Grounding</span></a> for more detail.</p>
</div>
</section>
<section id="ghost-mapping-sums">
<h2><a class="toc-backref" href="#id11" role="doc-backlink">Ghost Mapping Sums</a><a class="headerlink" href="#ghost-mapping-sums" title="Link to this heading"></a></h2>
<p>The prover is capable of calculating the <code class="docutils literal notranslate"><span class="pre">sum</span></code> of ghost mappings over
specified indices. For example, if we have a ghost mapping <code class="docutils literal notranslate"><span class="pre">ghost</span> <span class="pre">mapping(address</span> <span class="pre">=&gt;</span> <span class="pre">mapping(bytes32</span> <span class="pre">=&gt;</span> <span class="pre">mathint))</span> <span class="pre">myGhost</span></code>, and want to sum all
the values of the ghost over all addresses for a given <code class="docutils literal notranslate"><span class="pre">bytes32</span></code> value <code class="docutils literal notranslate"><span class="pre">b</span></code>, one
can write <code class="docutils literal notranslate"><span class="pre">sum</span> <span class="pre">address</span> <span class="pre">a.</span> <span class="pre">myGhost[a][b]</span></code>. This returns a <code class="docutils literal notranslate"><span class="pre">mathint</span></code>-typed
number that sums all known values of <code class="docutils literal notranslate"><span class="pre">myGhost</span></code> over the first index.
The full syntax for this is <code class="docutils literal notranslate"><span class="pre">sum</span> <span class="pre">type1</span> <span class="pre">t1,</span> <span class="pre">type2</span> <span class="pre">t2,</span> <span class="pre">...</span> <span class="pre">typeN</span> <span class="pre">tN.</span> <span class="pre">ghostName[...]</span></code>. See <a class="reference external" href="https://github.com/Certora/Examples/blob/master/CVLByExample/Summarization/GhostSummary/GhostSums/README.md">here</a>
for an example.</p>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>The prover support only summation of ghosts. If one wants to sum e.g. some
storage mapping, one could implement a ghost that mirrors the storage and sum
over it.</p>
</div>
<p>An extension of the summing logic is the unsigned sum which uses the <code class="docutils literal notranslate"><span class="pre">usum</span></code>
keyword. It follows the same rules as the regular sum, but adds some extra
logic to ensure the value of the sum is always larger than its parts.</p>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>The keyword <code class="docutils literal notranslate"><span class="pre">usum</span></code> indicates that all entries are non-negative (unsigned).
It can only be used on ghost mappings with unsigned or <code class="docutils literal notranslate"><span class="pre">mathint</span></code> value
types. In the case of <code class="docutils literal notranslate"><span class="pre">mathint</span></code> an assertion is added on each write to the ghost
that reports an error if the written value is negative.
When using this keyword, the solver will introduce the additional assumption
that the <code class="docutils literal notranslate"><span class="pre">usum</span></code> is larger than any value in the ghost mapping and that it is
even larger than the sum of any finite subset of values.
This additional assumption is valid, because the other values in the ghost
mapping can make the total sum only larger.</p>
</div>
</section>
<section id="accessing-fields-and-arrays">
<h2><a class="toc-backref" href="#id12" role="doc-backlink">Accessing fields and arrays</a><a class="headerlink" href="#accessing-fields-and-arrays" title="Link to this heading"></a></h2>
<p>One can access the special fields of built-in types, fields of user-defined
<code class="docutils literal notranslate"><span class="pre">struct</span></code> types, and members of user-defined <code class="docutils literal notranslate"><span class="pre">enum</span></code> types using the normal
<code class="docutils literal notranslate"><span class="pre">expr.field</span></code> notation.  Note that as described in <a class="reference internal" href="types.html#user-types"><span class="std std-ref">User-defined types</span></a>,
access to user-defined types must be qualified by a contract name.</p>
<p>Access to arrays also uses the same syntax as Solidity.</p>
</section>
<section id="contracts-method-signatures-and-their-properties">
<h2><a class="toc-backref" href="#id13" role="doc-backlink">Contracts, method signatures and their properties</a><a class="headerlink" href="#contracts-method-signatures-and-their-properties" title="Link to this heading"></a></h2>
<p>Writing the ABI signature for a contract method produces a <code class="docutils literal notranslate"><span class="pre">method</span></code> object,
which can be used to access the <a class="reference internal" href="types.html#method-type"><span class="std std-ref">method fields</span></a>.</p>
<p>For example,</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell7"><span></span><span class="kt">method</span><span class="w"> </span>m<span class="p">;</span>
<span class="kr">require</span><span class="w"> </span>m<span class="p">.</span><span class="nb">selector</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="kd">sig</span><span class="o">:</span><span class="nf">balanceOf</span><span class="p">(</span><span class="kt">address</span><span class="p">).</span><span class="nb">selector</span>
<span class="w">     </span><span class="o">||</span><span class="w"> </span>m<span class="p">.</span><span class="nb">selector</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="kd">sig</span><span class="o">:</span><span class="nf">transfer</span><span class="p">(</span><span class="kt">address</span><span class="p">,</span><span class="w"> </span><span class="kt">uint256</span><span class="p">).</span><span class="nb">selector</span><span class="p">;</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell7">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>will constrain <code class="docutils literal notranslate"><span class="pre">m</span></code> to be either the <code class="docutils literal notranslate"><span class="pre">balanceOf</span></code> or the <code class="docutils literal notranslate"><span class="pre">transfer</span></code> method.</p>
<p>One can determine whether a contract has a particular method using the <code class="docutils literal notranslate"><span class="pre">s</span> <span class="pre">in</span> <span class="pre">c</span></code>
where <code class="docutils literal notranslate"><span class="pre">s</span></code> is a method selector and <code class="docutils literal notranslate"><span class="pre">c</span></code> is a contract (either <code class="docutils literal notranslate"><span class="pre">currentContract</span></code>
or a contract introduced with a <a class="reference internal" href="using.html#using-stmt"><span class="std std-ref">using statement</span></a>.  For
example, the statement</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell8"><span></span><span class="kr">if</span><span class="w"> </span><span class="p">(</span>burnFrom<span class="p">(</span><span class="kt">address</span><span class="p">,</span><span class="kt">uint256</span><span class="p">).</span><span class="nb">selector</span><span class="w"> </span>in<span class="w"> </span><span class="nb">currentContract</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">  </span><span class="p">...</span>
<span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell8">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>will check that the current contract supports the optional <code class="docutils literal notranslate"><span class="pre">burnFrom</span></code> method.</p>
</section>
<section id="special-variables-and-fields">
<span id="currentcontract"></span><span id="special-fields"></span><h2><a class="toc-backref" href="#id14" role="doc-backlink">Special variables and fields</a><a class="headerlink" href="#special-variables-and-fields" title="Link to this heading"></a></h2>
<p>Several of the CVL types have special fields; see <a class="reference internal" href="types.html"><span class="doc">Types</span></a> (particularly
<a class="reference internal" href="types.html#env"><span class="std std-ref">The env type</span></a>, <a class="reference internal" href="types.html#method-type"><span class="std std-ref">The method and calldataarg types</span></a>, and <a class="reference internal" href="types.html#arrays"><span class="std std-ref">Array access</span></a>).</p>
<p>There are also several built-in variables:</p>
<ul>
<li><p><code class="docutils literal notranslate"><span class="pre">address</span> <span class="pre">currentContract</span></code> always refers to the main contract being verified
(that is, the contract named in the <a class="reference internal" href="../prover/cli/options.html#verify"><span class="std std-ref">verify</span></a> option).</p></li>
<li><p><code class="docutils literal notranslate"><span class="pre">bool</span> <span class="pre">lastReverted</span></code> indicates whether the most recent contract function reverted or threw an
exception.</p>
<div class="admonition caution">
<p class="admonition-title">Caution</p>
<p>The variable <code class="docutils literal notranslate"><span class="pre">lastReverted</span></code> is updated after each
contract call, even those called without <code class="docutils literal notranslate"><span class="pre">@withrevert</span></code> (see <a class="reference internal" href="#call-expr"><span class="std std-ref">Calling contract functions</span></a>).
This is a common source of errors.  For example, the following rule is
vacuous:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell9"><span></span><span class="k">rule</span><span class="w"> </span><span class="nc">revert_if_paused</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<span class="w">  </span>withdraw<span class="ow">@withrevert</span><span class="p">();</span>
<span class="w">  </span><span class="kr">assert</span><span class="w"> </span>isPaused<span class="p">()</span><span class="w"> </span><span class="o">=&gt;</span><span class="w"> </span><span class="nb">lastReverted</span><span class="p">;</span>
<span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell9">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>In this rule, the call to <code class="docutils literal notranslate"><span class="pre">isPaused</span></code> will update <code class="docutils literal notranslate"><span class="pre">lastReverted</span></code> to <code class="docutils literal notranslate"><span class="pre">true</span></code>,
overwriting the value set by <code class="docutils literal notranslate"><span class="pre">withdraw</span></code>.</p>
</div>
</li>
<li><p><code class="docutils literal notranslate"><span class="pre">lastStorage</span></code> refers to the most recent state of the EVM storage.  See
<a class="reference internal" href="types.html#storage-type"><span class="std std-ref">The storage type</span></a> for more details.</p></li>
<li><p>You can use the variable <code class="docutils literal notranslate"><span class="pre">_</span></code> as a placeholder for a value you are not
interested in.</p></li>
<li><p>The maximum values for the different integer types are available as the
variables <code class="docutils literal notranslate"><span class="pre">max_uint</span></code>, <code class="docutils literal notranslate"><span class="pre">max_address</span></code>, <code class="docutils literal notranslate"><span class="pre">max_uint8</span></code>, <code class="docutils literal notranslate"><span class="pre">max_uint16</span></code> etc.</p></li>
<li><p><code class="docutils literal notranslate"><span class="pre">nativeBalances</span></code> is a mapping of the native token balances, i.e. ETH for Ethereum.
The balance of an <code class="docutils literal notranslate"><span class="pre">address</span> <span class="pre">a</span></code> can be expressed using <code class="docutils literal notranslate"><span class="pre">nativeBalances[a]</span></code>.</p></li>
<li><p><code class="docutils literal notranslate"><span class="pre">calledContract</span></code> is only available in <a class="reference internal" href="methods.html#expression-summary"><span class="std std-ref">expression summaries</span></a>.
It refers to the receiver contract of a summarized method call.</p></li>
<li><p><code class="docutils literal notranslate"><span class="pre">executingContract</span></code> is only available in <a class="reference internal" href="hooks.html#hooks"><span class="std std-ref">hooks</span></a>.  It refers to
the contract that is executing when the hook is triggered.</p></li>
</ul>
<p>CVL also has several built-in functions for converting between
numeric types.  See <a class="reference internal" href="#math-ops"><span class="std std-ref">Basic operations</span></a> for details.</p>
</section>
<section id="calling-contract-functions">
<span id="call-expr"></span><h2><a class="toc-backref" href="#id15" role="doc-backlink">Calling contract functions</a><a class="headerlink" href="#calling-contract-functions" title="Link to this heading"></a></h2>
<p>There are many kinds of function-like things that can be called from CVL:</p>
<ul class="simple">
<li><p>Contract functions</p></li>
<li><p><a class="reference internal" href="types.html#method-type"><span class="std std-ref">Method variables</span></a></p></li>
<li><p><a class="reference internal" href="ghosts.html#ghost-functions"><span class="std std-ref">Ghost Functions</span></a></p></li>
<li><p><a class="reference internal" href="functions.html"><span class="doc">Functions</span></a></p></li>
<li><p><a class="reference internal" href="defs.html"><span class="doc">Definitions</span></a></p></li>
</ul>
<p>There are several additional features that can be used when calling contract
functions (including calling them through <a class="reference internal" href="types.html#method-type"><span class="std std-ref">method variables</span></a>).</p>
<p>The method name can optionally be prefixed by a contract name (introduced via a
<a class="reference internal" href="using.html#using-stmt"><span class="std std-ref">using statement</span></a>). If a contract is not explicitly named, the
method will be called with <code class="docutils literal notranslate"><span class="pre">currentContract</span></code> as the receiver.</p>
<p>It is possible for multiple contract methods to match the method call.  This can
happen in two ways:</p>
<ol class="arabic simple">
<li><p>The method to be called is a <a class="reference internal" href="types.html#method-type"><span class="std std-ref">method variable</span></a></p></li>
<li><p>The method to be called is overloaded in the contract (i.e. there are two
methods of the same name), and the method is called with a <a class="reference internal" href="types.html#calldataarg"><span class="std std-ref">calldataarg</span></a> argument.</p></li>
</ol>
<p>In either case, the Prover will consider every possible resolution of the method
while verifying the rule, and will provide a separate verification report for
each checked method.  Rules that use this feature are referred to as
<a class="reference internal" href="../user-guide/glossary.html#term-parametric-rule"><span class="xref std std-term">parametric rule</span></a>s.</p>
<p>Another possible way to have the Prover consider options for a function is by
using an <code class="docutils literal notranslate"><span class="pre">address</span></code> typed variable and “calling” the function on it, e.g.
<code class="docutils literal notranslate"><span class="pre">address</span> <span class="pre">a;</span> <span class="pre">a.foo(...);</span></code>. In this case the Prover will consider every possible
contract in the {ref}scene that implements a function that matches the signature
provided by the call (if no such function exists in the {ref}scene the prover will
fail with an error).
Note: The values that the address variable can take are the addresses that are
associated with the relevant contracts in the scene. Notably, other values would
not be possible: Given an address variable <code class="docutils literal notranslate"><span class="pre">a</span></code>, on which we call a some method
implemented by contracts <code class="docutils literal notranslate"><span class="pre">A</span></code> and <code class="docutils literal notranslate"><span class="pre">B</span></code>, we will have an implicit
<code class="docutils literal notranslate"><span class="pre">require</span> <span class="pre">a</span> <span class="pre">==</span> <span class="pre">A</span> <span class="pre">||</span> <span class="pre">a</span> <span class="pre">==</span> <span class="pre">B</span></code>.</p>
<p id="with-revert">After the function name, but before the arguments, you can write an optional
method tag, one of <code class="docutils literal notranslate"><span class="pre">@norevert</span></code> or <code class="docutils literal notranslate"><span class="pre">@withrevert</span></code>.</p>
<ul>
<li><p><code class="docutils literal notranslate"><span class="pre">@norevert</span></code> indicates that examples where the method revert should not be
considered.  This is the default behavior if no tag is provided</p></li>
<li><p><code class="docutils literal notranslate"><span class="pre">@withrevert</span></code> indicates that examples that would revert should still be
considered.  In this case, the method will set the <code class="docutils literal notranslate"><span class="pre">lastReverted</span></code> variable
to <code class="docutils literal notranslate"><span class="pre">true</span></code> in case the called method reverts or throws an exception.</p>
<p><a class="reference external" href="https://github.com/Certora/Examples/blob/14668d39a6ddc67af349bc5b82f73db73349ef18/CVLByExample/storage/certora/specs/storage.spec#L45C19-L45C19"><code class="docutils literal notranslate"><span class="pre">withrevert</span></code> example</a></p>
</li>
</ul>
<p>After the method tag, the method arguments are provided.  Unless the method
is declared <a class="reference internal" href="methods.html#envfree"><span class="std std-ref">envfree</span></a>, the first argument must be an
<a class="reference internal" href="types.html#env"><span class="std std-ref">environment value</span></a>.  The remaining arguments must either be a
single <a class="reference internal" href="types.html#calldataarg"><span class="std std-ref">calldataarg value</span></a>, or the same types of arguments
that would normally be passed to the contract method.</p>
<p>After the method arguments, a method invocation can optionally include <code class="docutils literal notranslate"><span class="pre">at</span> <span class="pre">s</span></code>
where <code class="docutils literal notranslate"><span class="pre">s</span></code> is a <a class="reference internal" href="types.html#storage-type"><span class="std std-ref">storage variable</span></a>.  This indicates that
before the method is executed, the EVM state should be restored to the saved
state <code class="docutils literal notranslate"><span class="pre">s</span></code>.</p>
<section id="type-restrictions">
<h3><a class="toc-backref" href="#id16" role="doc-backlink">Type restrictions</a><a class="headerlink" href="#type-restrictions" title="Link to this heading"></a></h3>
<p>When calling a contract function, the Prover must convert the arguments and
return values from their Solidity types to their CVL types and vice-versa.
There are some restrictions on the types that can be converted.  See
<a class="reference internal" href="types.html#type-conversions"><span class="std std-ref">Conversions between CVL and Solidity types</span></a> for more details.</p>
</section>
</section>
<section id="comparing-storage">
<span id="storage-comparison"></span><h2><a class="toc-backref" href="#id17" role="doc-backlink">Comparing storage</a><a class="headerlink" href="#comparing-storage" title="Link to this heading"></a></h2>
<p>As described in <a class="reference internal" href="types.html#storage-type"><span class="std std-ref">the documentation on storage types</span></a>, CVL represents the entirety of the EVM and its
<a class="reference internal" href="ghosts.html#ghost-functions"><span class="std std-ref">ghost state</span></a>
in variables with <code class="docutils literal notranslate"><span class="pre">storage</span></code> type. Variables of this type can be checked for equality and inequality.</p>
<p>The basic form of this expression is <code class="docutils literal notranslate"><span class="pre">s1</span> <span class="pre">==</span> <span class="pre">s2</span></code>, where <code class="docutils literal notranslate"><span class="pre">s1</span></code> and <code class="docutils literal notranslate"><span class="pre">s2</span></code> are variables of type <code class="docutils literal notranslate"><span class="pre">storage</span></code>.
This expression compares the states represented by <code class="docutils literal notranslate"><span class="pre">s1</span></code> and <code class="docutils literal notranslate"><span class="pre">s2</span></code>; that is, it checks equality of the following:</p>
<ol class="arabic simple">
<li><p>The values in storage for all contracts,</p></li>
<li><p>The balances of all contracts,</p></li>
<li><p>The state of all ghost variables and functions</p></li>
</ol>
<p>Thus, if any field in any contract’s storage differs between <code class="docutils literal notranslate"><span class="pre">s1</span></code> and <code class="docutils literal notranslate"><span class="pre">s2</span></code>, the expression will return <code class="docutils literal notranslate"><span class="pre">false</span></code>.
The expression <code class="docutils literal notranslate"><span class="pre">s1</span> <span class="pre">!=</span> <span class="pre">s2</span></code> is shorthand for <code class="docutils literal notranslate"><span class="pre">!(s1</span> <span class="pre">==</span> <span class="pre">s2)</span></code>.</p>
<p>Storage comparisons also support narrowing the scope of comparison to specific components of the global
state represented by <code class="docutils literal notranslate"><span class="pre">storage</span></code> variables. This syntax is <code class="docutils literal notranslate"><span class="pre">s1[r]</span> <span class="pre">==</span> <span class="pre">s2[r]</span></code> or <code class="docutils literal notranslate"><span class="pre">s1[r]</span> <span class="pre">!=</span> <span class="pre">s2[r]</span></code>, where <code class="docutils literal notranslate"><span class="pre">r</span></code> is a “storage comparison basis”,
and <code class="docutils literal notranslate"><span class="pre">s1</span></code> and <code class="docutils literal notranslate"><span class="pre">s2</span></code> are variables of type <code class="docutils literal notranslate"><span class="pre">storage</span></code>. The valid bases of comparison are:</p>
<ol class="arabic simple">
<li><p>The name of a contract imported with a <a class="reference internal" href="using.html#using-stmt"><span class="std std-ref">using statement</span></a>,</p></li>
<li><p>The keyword <code class="docutils literal notranslate"><span class="pre">nativeBalances</span></code>, or</p></li>
<li><p>The name of a ghost variable or function</p></li>
</ol>
<p>It is an error to use different bases on different sides of the comparison operator, and it is also
an error to use a comparison basis on one side and not the other.
The application of the basis restricts the comparison
to only consider the portion of global state identified by the basis.</p>
<p>If the qualifier is a contract identifier
imported via <code class="docutils literal notranslate"><span class="pre">using</span></code>, then the comparison operation will only consider the storage fields of that contract. For example:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell10"><span></span><span class="kn">using</span><span class="w"> </span>MyContract<span class="w"> </span><span class="kn">as</span><span class="w"> </span>c<span class="p">;</span>
<span class="kn">using</span><span class="w"> </span>OtherContract<span class="w"> </span><span class="kn">as</span><span class="w"> </span>o<span class="p">;</span>

<span class="k">rule</span><span class="w"> </span><span class="nc">compare_state_of_c</span><span class="p">(</span><span class="kt">env</span><span class="w"> </span>e<span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">   </span><span class="kr">storage</span><span class="w"> </span>init<span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="nb">lastStorage</span><span class="p">;</span>
<span class="w">   </span>o<span class="p">.</span>mutateOtherState<span class="p">(</span>e<span class="p">);</span><span class="w"> </span><span class="c1">// changes `o` but not `c`</span>
<span class="w">   </span><span class="kr">assert</span><span class="w"> </span><span class="nb">lastStorage</span><span class="p">[</span>c<span class="p">]</span><span class="w"> </span><span class="o">==</span><span class="w"> </span>init<span class="p">[</span>c<span class="p">];</span>
<span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell10">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>will pass verification whereas:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell11"><span></span><span class="kn">using</span><span class="w"> </span>MyContract<span class="w"> </span><span class="kn">as</span><span class="w"> </span>c<span class="p">;</span>
<span class="kn">using</span><span class="w"> </span>OtherContract<span class="w"> </span><span class="kn">as</span><span class="w"> </span>o<span class="p">;</span>

<span class="k">rule</span><span class="w"> </span><span class="nc">compare_state_of_c</span><span class="p">(</span><span class="kt">env</span><span class="w"> </span>e<span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">   </span><span class="kr">storage</span><span class="w"> </span>init<span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="nb">lastStorage</span><span class="p">;</span>
<span class="w">   </span>c<span class="p">.</span>mutateContractState<span class="p">(</span>e<span class="p">);</span><span class="w"> </span><span class="c1">// changes `c`</span>
<span class="w">   </span><span class="kr">assert</span><span class="w"> </span><span class="nb">lastStorage</span><span class="p">[</span>c<span class="p">]</span><span class="w"> </span><span class="o">==</span><span class="w"> </span>init<span class="p">[</span>c<span class="p">];</span>
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
<p>will not.</p>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>Comparing contract’s state using this method will <strong>not</strong> compare the balance of the contract between the
two states.</p>
</div>
<p>If the qualifier is the identifier <code class="docutils literal notranslate"><span class="pre">nativeBalances</span></code>, then the account balances
of all contracts are compared between the two storage states.
Finally, if the basis is the name of a ghost function or variable, the values of that
function/variable are compared between storage states.</p>
<p>Two ghost functions are considered equal if they have the same outputs for all input arguments.</p>
<div class="admonition warning">
<p class="admonition-title">Warning</p>
<p>The default behavior of the Prover on unresolved external calls is to pessimistically havoc contract
state and balances. This behavior will render most storage comparisons that incorporate such
state useless. Care should be taken (using <a class="reference internal" href="methods.html#summaries"><span class="std std-ref">summarization</span></a>) to ensure that rules
that compare storage do not encounter this behavior.</p>
</div>
<div class="admonition warning">
<p class="admonition-title">Warning</p>
<p>The grammar admits storage comparisons for both equality and inequality
that occur arbitrarily nested within expressions. However, support within the Prover for
these comparisons is primarily aimed at assertions of storage equality, e.g., <code class="docutils literal notranslate"><span class="pre">assert</span> <span class="pre">s1</span> <span class="pre">==</span> <span class="pre">s2</span></code>.
Support for storage inequality as well as nesting comparisons within other expressions is considered
experimental.</p>
</div>
<div class="admonition warning">
<p class="admonition-title">Warning</p>
<p>The storage comparison checks for exact equality between every single slot of storage which can
lead to surprising failures of storage equality assertions.
In particular, these failures can happen if an uninitialized storage slot is
written and then later cleared by Solidity (via the <code class="docutils literal notranslate"><span class="pre">pop()</span></code> function or the <code class="docutils literal notranslate"><span class="pre">delete</span></code> keyword). After the
clear operation the slot will definitely hold 0, but the Prover will not make any assumptions
about the value of the uninitialized slot which means they can be considered different.</p>
</div>
</section>
<section id="direct-storage-access">
<span id="id2"></span><h2><a class="toc-backref" href="#id18" role="doc-backlink">Direct storage access</a><a class="headerlink" href="#direct-storage-access" title="Link to this heading"></a></h2>
<p>The value of contract state variables can be directly accessed from CVL. These direct
storage accesses are written using the state variable names and struct fields defined
in the contract. For example, to access the state variable <code class="docutils literal notranslate"><span class="pre">uint</span> <span class="pre">x</span></code> defined in the <code class="docutils literal notranslate"><span class="pre">currentContract</span></code>,
one can simply write <code class="docutils literal notranslate"><span class="pre">currentContract.x</span></code>. More complex structs can be accessed by chaining field selects
and array/map dereference operations together. For example, if the current contract has the following
type definitions and state variables:</p>
<div class="highlight-solidity notranslate"><div class="highlight"><pre id="codecell12"><span></span><span class="k">contract</span><span class="w"> </span><span class="ni">Example</span><span class="w"> </span><span class="p">{</span>
<span class="w">   </span><span class="kt">struct</span><span class="w"> </span><span class="nv">Foo</span><span class="w"> </span><span class="p">{</span>
<span class="w">      </span><span class="kt">mapping</span><span class="w"> </span><span class="p">(</span><span class="kt">address</span><span class="w"> </span><span class="o">=&gt;</span><span class="w"> </span><span class="kt">uint</span><span class="p">[])</span><span class="w"> </span>bar<span class="p">;</span>
<span class="w">   </span><span class="p">}</span>
<span class="w">   </span>Foo<span class="p">[</span><span class="m m-Decimal">3</span><span class="p">]</span><span class="w"> </span>myState<span class="p">;</span>
<span class="w">   </span><span class="kt">uint32</span><span class="w"> </span><span class="nv">luckyNumber</span><span class="p">;</span>
<span class="w">   </span><span class="kt">address</span><span class="p">[]</span><span class="w"> </span><span class="kt">public</span><span class="w"> </span>addresses<span class="p">;</span>
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
<p>one can write <code class="docutils literal notranslate"><span class="pre">currentContract.myState[0].bar[addr][0]</span></code>, where <code class="docutils literal notranslate"><span class="pre">addr</span></code> is a CVL variable of type <code class="docutils literal notranslate"><span class="pre">address</span></code>.</p>
<p>The storage of contracts other than the <code class="docutils literal notranslate"><span class="pre">currentContract</span></code> can be accessed by writing the contract identifier
bound with a <a class="reference internal" href="using.html#using-stmt"><span class="std std-ref">using statement</span></a>. For example, if the <code class="docutils literal notranslate"><span class="pre">myState</span></code> definition above appeared in
a contract called <code class="docutils literal notranslate"><span class="pre">Test</span></code> and the current CVL file included  <code class="docutils literal notranslate"><span class="pre">using</span> <span class="pre">Test</span> <span class="pre">as</span> <span class="pre">t;</span></code> one could write <code class="docutils literal notranslate"><span class="pre">t.myState[0].bar[addr][0]</span></code>.</p>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>A contract identifier (or <code class="docutils literal notranslate"><span class="pre">currentContract</span></code>) <em>must</em> be included in the direct storage access. In other
words, writing just <code class="docutils literal notranslate"><span class="pre">myState[0].bar[addr][0]</span></code> will not work, even if <code class="docutils literal notranslate"><span class="pre">myState</span></code> is declared in the current contract.</p>
</div>
<p>Currently only primitive values (e.g., <code class="docutils literal notranslate"><span class="pre">uint</span></code>, <code class="docutils literal notranslate"><span class="pre">bytes3</span></code>, <code class="docutils literal notranslate"><span class="pre">bool</span></code>, enums, and user defined value types) can be directly accessed.
Attempting to access more complex types will yield a type checking error. For example, attempting to access
an entire array with <code class="docutils literal notranslate"><span class="pre">currentContract.myState[0].bar[addr]</span></code> will fail.</p>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>Although entire arrays cannot be accessed, the <em>length</em> or the <em>number of elements</em> of the dynamic arrays
can be accessed with <code class="docutils literal notranslate"><span class="pre">.length</span></code>, e.g., <code class="docutils literal notranslate"><span class="pre">currentContract.myState[0].bar[addr].length</span></code>.</p>
</div>
<div class="admonition warning">
<p class="admonition-title">Warning</p>
<p>Direct storage access is an experimental feature, and relies on several internal program analyses which can sometimes fail. For example, attempts to use direct storage access to refer to variable which is actually unused or inaccessible in the contract.
If these internal static analyses fail, any rules that use direct storage access will fail during processing. If this
occurs, check the “Global Problems” view of the web report and contact Certora for assistance.</p>
</div>
<section id="direct-storage-havoc">
<h3><a class="toc-backref" href="#id19" role="doc-backlink">Direct storage havoc</a><a class="headerlink" href="#direct-storage-havoc" title="Link to this heading"></a></h3>
<p>The same direct storage syntax can also be used in <code class="docutils literal notranslate"><span class="pre">havoc</span></code> statements. With the previously-mentioned <code class="docutils literal notranslate"><span class="pre">Example</span></code> contract and <code class="docutils literal notranslate"><span class="pre">using</span> <span class="pre">Example</span> <span class="pre">as</span> <span class="pre">ex</span></code>, you can write <code class="docutils literal notranslate"><span class="pre">havoc</span> <span class="pre">ex.luckyNumber</span></code> or <code class="docutils literal notranslate"><span class="pre">havoc</span> <span class="pre">addresses[10]</span></code> or even <code class="docutils literal notranslate"><span class="pre">havoc</span> <span class="pre">addresses.length</span></code>.</p>
<p>While you may use a <code class="docutils literal notranslate"><span class="pre">havoc</span> <span class="pre">assuming</span></code> statement, unlike <a class="reference internal" href="ghosts.html"><span class="doc std std-doc">ghosts</span></a>, you cannot directly refer to the havoced storage path in the <code class="docutils literal notranslate"><span class="pre">assuming</span></code> expression using the <code class="docutils literal notranslate"><span class="pre">@old</span></code> and <code class="docutils literal notranslate"><span class="pre">@new</span></code> syntax. This generally means <code class="docutils literal notranslate"><span class="pre">assuming</span></code> expressions are not as useful with direct storage access, so consider using and unconditional <code class="docutils literal notranslate"><span class="pre">havoc</span></code> statements instead of <code class="docutils literal notranslate"><span class="pre">havoc</span> <span class="pre">assuming</span></code>.</p>
<div class="admonition warning">
<p class="admonition-title">Warning</p>
<p>As with direct storage access in general, direct storage havoc is experimental and limited to primitive types. In particular, this mean you <em>cannot</em> currently havoc</p>
<ul class="simple">
<li><p>entire arrays or entire mappings (only arrays at a specific index, or mappings at a specific key)</p></li>
<li><p>user-defined types such as structs, or arrays/mappings of such types</p></li>
<li><p>enums</p></li>
</ul>
</div>
</section>
<section id="direct-immutable-access">
<span id="id3"></span><h3><a class="toc-backref" href="#id20" role="doc-backlink">Direct immutable access</a><a class="headerlink" href="#direct-immutable-access" title="Link to this heading"></a></h3>
<p>The Certora Prover allows to access immutable variables in a contract, in
a similar way to direct storage access.
For example, given a contract:</p>
<div class="highlight-solidity notranslate"><div class="highlight"><pre id="codecell13"><span></span><span class="k">contract</span><span class="w"> </span><span class="ni">WithImmutables</span><span class="w"> </span><span class="p">{</span>
<span class="w">  </span><span class="kt">address</span><span class="w"> </span><span class="k">private </span><span class="nv">immutable</span><span class="w"> </span>myImmutAddr<span class="p">;</span>
<span class="w">  </span><span class="kt">bool</span><span class="w"> </span><span class="k">public </span><span class="nv">immutable</span><span class="w"> </span>myImmutBool<span class="p">;</span>

<span class="w">  </span><span class="kt">constructor</span><span class="p">()</span><span class="w"> </span><span class="p">{</span><span class="w"> </span><span class="p">...</span><span class="w"> </span><span class="p">}</span>
<span class="w">  </span><span class="kt">function</span><span class="w"> </span><span class="nv">publicGetterForPrivateImmutableAddr</span><span class="p">()</span><span class="w"> </span><span class="kt">external</span><span class="w"> </span><span class="kt">returns</span><span class="w"> </span><span class="p">(</span><span class="kt">address</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kt">return</span><span class="w"> </span>myImmutAddr<span class="p">;</span>
<span class="w">  </span><span class="p">}</span>
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
<p>We can access both <code class="docutils literal notranslate"><span class="pre">myImmutAddr</span></code> and <code class="docutils literal notranslate"><span class="pre">myImmutBool</span></code> directly from CVL
like this:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell14"><span></span><span class="kn">using</span><span class="w"> </span>WithImmutables<span class="w"> </span><span class="kn">as</span><span class="w"> </span>withImmutables<span class="p">;</span>

<span class="kr">methods</span><span class="w"> </span><span class="p">{</span>
<span class="w">  </span><span class="kd">function</span><span class="w"> </span><span class="nf">publicGetterForPrivateImmutableAddr</span><span class="p">()</span><span class="w"> </span><span class="kr">external</span><span class="w"> </span><span class="kr">returns</span><span class="w"> </span><span class="p">(</span><span class="kt">address</span><span class="p">)</span><span class="w"> </span><span class="kr">envfree</span><span class="p">;</span>
<span class="w">  </span><span class="kd">function</span><span class="w"> </span><span class="nf">myImmutBool</span><span class="p">()</span><span class="w"> </span><span class="kr">external</span><span class="w"> </span><span class="kr">returns</span><span class="w"> </span><span class="p">(</span><span class="kt">bool</span><span class="p">)</span><span class="w"> </span><span class="kr">envfree</span><span class="p">;</span>
<span class="p">}</span>

<span class="k">rule</span><span class="w"> </span><span class="nc">accessPrivateImmut</span><span class="w"> </span><span class="p">{</span>
<span class="w">  </span><span class="kr">assert</span><span class="w"> </span>withImmutables<span class="p">.</span>myImmutAddr<span class="w"> </span><span class="o">==</span><span class="w"> </span>publicGetterForPrivateImmutableAddr<span class="p">();</span>
<span class="p">}</span>

<span class="k">rule</span><span class="w"> </span><span class="nc">accessPublicImmut</span><span class="w"> </span><span class="p">{</span>
<span class="w">  </span><span class="kr">assert</span><span class="w"> </span>withImmutables<span class="p">.</span>myImmutBool<span class="w"> </span><span class="o">==</span><span class="w"> </span>withImmutables<span class="p">.</span>myImmutBool<span class="p">();</span>
<span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell14">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>The advantages of direct immutable access is that there is no need to
declare <code class="docutils literal notranslate"><span class="pre">envfree</span></code> methods for the public immutables, and even more importantly, nor is there a need to harness contracts in order to
expose the private immutables.</p>
</section>
</section>
<section id="built-in-functions">
<h2><a class="toc-backref" href="#id21" role="doc-backlink">Built-in Functions</a><a class="headerlink" href="#built-in-functions" title="Link to this heading"></a></h2>
<section id="hashing">
<h3><a class="toc-backref" href="#id22" role="doc-backlink">Hashing</a><a class="headerlink" href="#hashing" title="Link to this heading"></a></h3>
<p>CVL allows to use Solidity’s <code class="docutils literal notranslate"><span class="pre">keccak256</span></code> hashing function directly in spec. Below are two usage examples: one using a <code class="docutils literal notranslate"><span class="pre">bytes</span></code> array, another using primitives.
As <code class="docutils literal notranslate"><span class="pre">bytes32</span></code> is the return type of <code class="docutils literal notranslate"><span class="pre">keccak256</span></code> and is a primitive type, calls to <code class="docutils literal notranslate"><span class="pre">keccak256</span></code> can be nested.</p>
<p>(Currently, only the <code class="docutils literal notranslate"><span class="pre">keccak256</span></code> hash is supported in CVL as a built-in.)</p>
<section id="example">
<h4><a class="toc-backref" href="#id23" role="doc-backlink">Example</a><a class="headerlink" href="#example" title="Link to this heading"></a></h4>
<p>Given the following Solidity snippet:</p>
<div class="highlight-solidity notranslate"><div class="highlight"><pre id="codecell15"><span></span><span class="k">contract</span><span class="w"> </span><span class="ni">HashingExample</span><span class="w"> </span><span class="p">{</span>
<span class="w">  </span><span class="kt">struct</span><span class="w"> </span><span class="nv">SignedMessage</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kt">address</span><span class="w"> </span><span class="nv">sender</span><span class="p">;</span>
<span class="w">    </span><span class="kt">uint256</span><span class="w"> </span><span class="nv">nonce</span><span class="p">;</span>
<span class="w">    </span><span class="kt">bytes</span><span class="w"> </span><span class="nv">signature</span><span class="p">;</span>
<span class="w">  </span><span class="p">}</span>

<span class="w">  </span><span class="kt">mapping</span><span class="w"> </span><span class="p">(</span><span class="kt">bytes32</span><span class="w"> </span><span class="o">=&gt;</span><span class="w"> </span><span class="kt">uint256</span><span class="p">)</span><span class="w"> </span>messageToValue<span class="p">;</span>

<span class="w">  </span><span class="kt">function</span><span class="w"> </span><span class="nv">hashingScheme1</span><span class="p">(</span>SignedMessage<span class="w"> </span><span class="kt">memory</span><span class="w"> </span>s<span class="p">)</span><span class="w"> </span><span class="kt">public</span><span class="w"> </span>pure<span class="w"> </span><span class="kt">returns</span><span class="w"> </span><span class="p">(</span><span class="kt">bytes32</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kt">return</span><span class="w"> </span><span class="nb">keccak256</span><span class="p">(</span>abi<span class="p">.</span>encode<span class="p">(</span>s<span class="p">.</span>sender<span class="p">,</span><span class="w"> </span>s<span class="p">.</span>nonce<span class="p">));</span>
<span class="w">  </span><span class="p">}</span>

<span class="w">  </span><span class="kt">function</span><span class="w"> </span><span class="nv">hashingScheme2</span><span class="p">(</span>SignedMessage<span class="w"> </span><span class="kt">memory</span><span class="w"> </span>s<span class="p">)</span><span class="w"> </span><span class="kt">public</span><span class="w"> </span>pure<span class="w"> </span><span class="kt">returns</span><span class="w"> </span><span class="p">(</span><span class="kt">bytes32</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kt">return</span><span class="w"> </span><span class="nb">keccak256</span><span class="p">(</span>s<span class="p">.</span>signature<span class="p">);</span>
<span class="w">  </span><span class="p">}</span>

<span class="w">  </span><span class="kt">function</span><span class="w"> </span><span class="nv">hashingScheme3</span><span class="p">(</span>SignedMessage<span class="w"> </span><span class="kt">memory</span><span class="w"> </span>s<span class="p">)</span><span class="w"> </span><span class="kt">public</span><span class="w"> </span>pure<span class="w"> </span><span class="kt">returns</span><span class="w"> </span><span class="p">(</span><span class="kt">bytes32</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kt">return</span><span class="w"> </span><span class="nb">keccak256</span><span class="p">(</span>abi<span class="p">.</span>encode<span class="p">(</span>s<span class="p">.</span>sender<span class="p">,</span><span class="w"> </span>s<span class="p">.</span>nonce<span class="p">,</span><span class="w"> </span><span class="nb">keccak256</span><span class="p">(</span>s<span class="p">.</span>signature<span class="p">)));</span>
<span class="w">  </span><span class="p">}</span>

<span class="w">  </span><span class="kt">function</span><span class="w"> </span><span class="nv">hashingScheme4</span><span class="p">(</span>SignedMessage<span class="w"> </span><span class="kt">memory</span><span class="w"> </span>s<span class="p">)</span><span class="w"> </span><span class="kt">public</span><span class="w"> </span>pure<span class="w"> </span><span class="kt">returns</span><span class="w"> </span><span class="p">(</span><span class="kt">bytes32</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kt">return</span><span class="w"> </span><span class="nb">keccak256</span><span class="p">(</span>abi<span class="p">.</span>encode<span class="p">(</span>s<span class="p">.</span>sender<span class="p">,</span><span class="w"> </span>s<span class="p">.</span>nonce<span class="p">,</span><span class="w"> </span>s<span class="p">.</span>signature<span class="p">));</span>
<span class="w">  </span><span class="p">}</span>
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
<p>The hashing schemes described by <code class="docutils literal notranslate"><span class="pre">hashingScheme1</span></code>, <code class="docutils literal notranslate"><span class="pre">hashingScheme2</span></code>, and <code class="docutils literal notranslate"><span class="pre">hashingScheme3</span></code> can be replicated in CVL as follows:</p>
<div class="highlight-default notranslate"><div class="highlight"><pre id="codecell16"><span></span><span class="n">function</span> <span class="n">hashingScheme1CVL</span><span class="p">(</span><span class="n">HashingExample</span><span class="o">.</span><span class="n">SignedMessage</span> <span class="n">s</span><span class="p">)</span> <span class="n">returns</span> <span class="n">bytes32</span> <span class="p">{</span>
  <span class="k">return</span> <span class="n">keccak256</span><span class="p">(</span><span class="n">s</span><span class="o">.</span><span class="n">sender</span><span class="p">,</span> <span class="n">s</span><span class="o">.</span><span class="n">nonce</span><span class="p">);</span>
<span class="p">}</span>

<span class="n">function</span> <span class="n">hashingScheme2CVL</span><span class="p">(</span><span class="n">HashingExample</span><span class="o">.</span><span class="n">SignedMessage</span> <span class="n">s</span><span class="p">)</span> <span class="n">returns</span> <span class="n">bytes32</span> <span class="p">{</span>
  <span class="k">return</span> <span class="n">keccak256</span><span class="p">(</span><span class="n">s</span><span class="o">.</span><span class="n">signature</span><span class="p">);</span>
<span class="p">}</span>

<span class="n">function</span> <span class="n">hashingScheme3CVL</span><span class="p">(</span><span class="n">HashingExample</span><span class="o">.</span><span class="n">SignedMessage</span> <span class="n">s</span><span class="p">)</span> <span class="n">returns</span> <span class="n">bytes32</span> <span class="p">{</span>
  <span class="k">return</span> <span class="n">keccak256</span><span class="p">(</span><span class="n">s</span><span class="o">.</span><span class="n">sender</span><span class="p">,</span> <span class="n">s</span><span class="o">.</span><span class="n">nonce</span><span class="p">,</span> <span class="n">keccak256</span><span class="p">(</span><span class="n">s</span><span class="o">.</span><span class="n">signature</span><span class="p">));</span>
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
<p>The scheme implemented in <code class="docutils literal notranslate"><span class="pre">hashingScheme4</span></code> is not supported at the moment, as it combines a <code class="docutils literal notranslate"><span class="pre">bytes</span></code> type with primitives.
The <code class="docutils literal notranslate"><span class="pre">keccak256</span></code> built-in function supports two kinds of inputs:</p>
<ul class="simple">
<li><p>a single <code class="docutils literal notranslate"><span class="pre">bytes</span></code> parameter</p></li>
<li><p>a list of primitive (e.g., <code class="docutils literal notranslate"><span class="pre">uint256</span></code>, <code class="docutils literal notranslate"><span class="pre">uint8</span></code>, <code class="docutils literal notranslate"><span class="pre">addresss</span></code>) parameters</p></li>
</ul>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p><code class="docutils literal notranslate"><span class="pre">keccak256</span></code> is currently <em><strong>unsupported</strong></em> in quantified expressions.</p>
</div>
</section>
</section>
<section id="ecrecover">
<span id="id4"></span><h3><a class="toc-backref" href="#id24" role="doc-backlink">ECRecover</a><a class="headerlink" href="#ecrecover" title="Link to this heading"></a></h3>
<p>The <code class="docutils literal notranslate"><span class="pre">ecrecover</span></code> function in Solidity is helpful in recovering the signer’s address from a signed message.
It exists in very similar form in CVL and receives exactly the same parameter types as its Solidity counterpart.</p>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p><code class="docutils literal notranslate"><span class="pre">ecrecover</span></code> is <em><strong>supported</strong></em> in quantified expressions.</p>
</div>
<p>The Prover’s model of <code class="docutils literal notranslate"><span class="pre">ecrecover</span></code> does not actually implement the elliptical curve recovery algorithm, and is instead implemented using an <a class="reference internal" href="ghosts.html#ghost-functions"><span class="std std-ref">ghost function</span></a>. Like all ghost functions, <a class="reference internal" href="../user-guide/glossary.html#glossary"><span class="std std-ref">axioms</span></a> can be added to make the behavior of CVL’s <code class="docutils literal notranslate"><span class="pre">ecrecover</span></code> more faithfully model the actual key recovery algorithm.</p>
<p>There is a useful set of axioms that can be encoded in CVL to make the modeled behavior of <code class="docutils literal notranslate"><span class="pre">ecrecover</span></code> more precise and less likely to create false counterexamples:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell17"><span></span><span class="kt">function</span><span class="w"> </span><span class="nf">ecrecoverAxioms</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<span class="w">  </span><span class="c1">// zero value:</span>
<span class="w">  </span><span class="kr">require</span><span class="w"> </span><span class="p">(</span><span class="kr">forall</span><span class="w"> </span><span class="kt">uint8</span><span class="w"> </span>v<span class="p">.</span><span class="w"> </span><span class="kr">forall</span><span class="w"> </span><span class="kt">bytes32</span><span class="w"> </span>r<span class="p">.</span><span class="w"> </span><span class="kr">forall</span><span class="w"> </span><span class="kt">bytes32</span><span class="w"> </span>s<span class="p">.</span><span class="w"> </span>ecrecover<span class="p">(</span><span class="nb">to_bytes32</span><span class="p">(</span><span class="m m-Decimal">0</span><span class="p">),</span><span class="w"> </span>v<span class="p">,</span><span class="w"> </span>r<span class="p">,</span><span class="w"> </span>s<span class="p">)</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">);</span>
<span class="w">  </span><span class="c1">// uniqueness of signature</span>
<span class="w">  </span><span class="kr">require</span><span class="w"> </span><span class="p">(</span><span class="kr">forall</span><span class="w"> </span><span class="kt">uint8</span><span class="w"> </span>v<span class="p">.</span><span class="w"> </span><span class="kr">forall</span><span class="w"> </span><span class="kt">bytes32</span><span class="w"> </span>r<span class="p">.</span><span class="w"> </span><span class="kr">forall</span><span class="w"> </span><span class="kt">bytes32</span><span class="w"> </span>s<span class="p">.</span><span class="w"> </span><span class="kr">forall</span><span class="w"> </span><span class="kt">bytes32</span><span class="w"> </span>h1<span class="p">.</span><span class="w"> </span><span class="kr">forall</span><span class="w"> </span><span class="kt">bytes32</span><span class="w"> </span>h2<span class="p">.</span>
<span class="w">    </span>h1<span class="w"> </span><span class="o">!=</span><span class="w"> </span>h2<span class="w"> </span><span class="o">=&gt;</span><span class="w"> </span>ecrecover<span class="p">(</span>h1<span class="p">,</span><span class="w"> </span>v<span class="p">,</span><span class="w"> </span>r<span class="p">,</span><span class="w"> </span>s<span class="p">)</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="w"> </span><span class="o">=&gt;</span><span class="w"> </span>ecrecover<span class="p">(</span>h2<span class="p">,</span><span class="w"> </span>v<span class="p">,</span><span class="w"> </span>r<span class="p">,</span><span class="w"> </span>s<span class="p">)</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">);</span>
<span class="w">  </span><span class="c1">// dependency on r and s</span>
<span class="w">  </span><span class="kr">require</span><span class="w"> </span><span class="p">(</span><span class="kr">forall</span><span class="w"> </span><span class="kt">bytes32</span><span class="w"> </span>h<span class="p">.</span><span class="w"> </span><span class="kr">forall</span><span class="w"> </span><span class="kt">uint8</span><span class="w"> </span>v<span class="p">.</span><span class="w"> </span><span class="kr">forall</span><span class="w"> </span><span class="kt">bytes32</span><span class="w"> </span>s<span class="p">.</span><span class="w"> </span><span class="kr">forall</span><span class="w"> </span><span class="kt">bytes32</span><span class="w"> </span>r1<span class="p">.</span><span class="w"> </span><span class="kr">forall</span><span class="w"> </span><span class="kt">bytes32</span><span class="w"> </span>r2<span class="p">.</span>
<span class="w">    </span>r1<span class="w"> </span><span class="o">!=</span><span class="w"> </span>r2<span class="w"> </span><span class="o">=&gt;</span><span class="w"> </span>ecrecover<span class="p">(</span>h<span class="p">,</span><span class="w"> </span>v<span class="p">,</span><span class="w"> </span>r1<span class="p">,</span><span class="w"> </span>s<span class="p">)</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="w"> </span><span class="o">=&gt;</span><span class="w"> </span>ecrecover<span class="p">(</span>h<span class="p">,</span><span class="w"> </span>v<span class="p">,</span><span class="w"> </span>r2<span class="p">,</span><span class="w"> </span>s<span class="p">)</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">);</span>
<span class="w">  </span><span class="kr">require</span><span class="w"> </span><span class="p">(</span><span class="kr">forall</span><span class="w"> </span><span class="kt">bytes32</span><span class="w"> </span>h<span class="p">.</span><span class="w"> </span><span class="kr">forall</span><span class="w"> </span><span class="kt">uint8</span><span class="w"> </span>v<span class="p">.</span><span class="w"> </span><span class="kr">forall</span><span class="w"> </span><span class="kt">bytes32</span><span class="w"> </span>r<span class="p">.</span><span class="w"> </span><span class="kr">forall</span><span class="w"> </span><span class="kt">bytes32</span><span class="w"> </span>s1<span class="p">.</span><span class="w"> </span><span class="kr">forall</span><span class="w"> </span><span class="kt">bytes32</span><span class="w"> </span>s2<span class="p">.</span>
<span class="w">    </span>s1<span class="w"> </span><span class="o">!=</span><span class="w"> </span>s2<span class="w"> </span><span class="o">=&gt;</span><span class="w"> </span>ecrecover<span class="p">(</span>h<span class="p">,</span><span class="w"> </span>v<span class="p">,</span><span class="w"> </span>r<span class="p">,</span><span class="w"> </span>s1<span class="p">)</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="w"> </span><span class="o">=&gt;</span><span class="w"> </span>ecrecover<span class="p">(</span>h<span class="p">,</span><span class="w"> </span>v<span class="p">,</span><span class="w"> </span>r<span class="p">,</span><span class="w"> </span>s2<span class="p">)</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">);</span>
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
<section id="id5">
<h4><a class="toc-backref" href="#id25" role="doc-backlink">Example</a><a class="headerlink" href="#id5" title="Link to this heading"></a></h4>
<p>Given the following Solidity snippet:</p>
<div class="highlight-solidity notranslate"><div class="highlight"><pre id="codecell18"><span></span><span class="k">contract</span><span class="w"> </span><span class="ni">ECExample</span><span class="w"> </span><span class="p">{</span>
<span class="w">  </span><span class="kt">function</span><span class="w"> </span><span class="nv">wrap_ecrecover</span><span class="p">(</span><span class="kt">bytes32</span><span class="w"> </span><span class="nv">digest</span><span class="p">,</span><span class="w"> </span><span class="kt">uint8</span><span class="w"> </span><span class="nv">v</span><span class="p">,</span><span class="w"> </span><span class="kt">bytes32</span><span class="w"> </span><span class="nv">r</span><span class="p">,</span><span class="w"> </span><span class="kt">bytes32</span><span class="w"> </span><span class="nv">s</span><span class="p">)</span><span class="w"> </span><span class="kt">public</span><span class="w"> </span>pure<span class="w"> </span><span class="kt">returns</span><span class="w"> </span><span class="p">(</span><span class="kt">address</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kt">return</span><span class="w"> </span>ecrecover<span class="p">(</span>digest<span class="p">,</span>v<span class="p">,</span>r<span class="p">,</span>s<span class="p">);</span>
<span class="w">  </span><span class="p">}</span>
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
<p>The following CVL function is equivalent to the <code class="docutils literal notranslate"><span class="pre">wrap_ecrecover</span></code> function in the Solidity snippet:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell19"><span></span><span class="kt">function</span><span class="w"> </span><span class="nf">wrap_ecrecoverCVL</span><span class="p">(</span><span class="kt">bytes32</span><span class="w"> </span>digest<span class="p">,</span><span class="w"> </span><span class="kt">uint8</span><span class="w"> </span>v<span class="p">,</span><span class="w"> </span><span class="kt">bytes32</span><span class="w"> </span>r<span class="p">,</span><span class="w"> </span><span class="kt">bytes32</span><span class="w"> </span>s<span class="p">)</span><span class="w"> </span><span class="kr">returns</span><span class="w"> </span><span class="kt">address</span><span class="w"> </span><span class="p">{</span>
<span class="w">  </span><span class="kr">return</span><span class="w"> </span>ecrecover<span class="p">(</span>digest<span class="p">,</span>v<span class="p">,</span>r<span class="p">,</span>s<span class="p">);</span>
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
</section>
</section>
</section>
</section>


           </div>
          </div>
          <footer><div class="rst-footer-buttons" role="navigation" aria-label="Footer">
        <a href="types.html" class="btn btn-neutral float-left" title="Types" accesskey="p" rel="prev"><span class="fa fa-arrow-circle-left" aria-hidden="true"></span> Previous</a>
        <a href="statements.html" class="btn btn-neutral float-right" title="Statements" accesskey="n" rel="next">Next <span class="fa fa-arrow-circle-right" aria-hidden="true"></span></a>
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