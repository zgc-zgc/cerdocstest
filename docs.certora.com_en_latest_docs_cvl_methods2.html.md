<!DOCTYPE html><html class="writer-html5" lang="en" data-content_root="../../"><head>
  <meta charset="utf-8"><meta name="viewport" content="width=device-width, initial-scale=1">

  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>The Methods Block — Certora Prover Documentation 0.0 documentation</title>
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
    <link rel="next" title="Rules" href="rules.html">
    <link rel="prev" title="Using Statements" href="using.html"> 
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
<li class="toctree-l2"><a class="reference internal" href="expr.html">Expressions</a></li>
<li class="toctree-l2"><a class="reference internal" href="statements.html">Statements</a></li>
<li class="toctree-l2"><a class="reference internal" href="imports.html">Import and Use Statements</a></li>
<li class="toctree-l2"><a class="reference internal" href="using.html">Using Statements</a></li>
<li class="toctree-l2 current" aria-expanded="true"><a class="reference internal current" href="#" aria-expanded="true"><button class="toctree-expand" title="Open/close menu"></button>The Methods Block</a><ul>
<li class="toctree-l3"><a class="reference internal" href="#syntax">Syntax</a></li>
<li class="toctree-l3"><a class="reference internal" href="#methods-entry-patterns"><button class="toctree-expand" title="Open/close menu"></button>Methods entry patterns</a><ul>
<li class="toctree-l4"><a class="reference internal" href="#exact-entries">Exact entries</a></li>
<li class="toctree-l4"><a class="reference internal" href="#wildcard-entries">Wildcard entries</a></li>
<li class="toctree-l4"><a class="reference internal" href="#catch-all-entries">Catch-all entries</a></li>
<li class="toctree-l4"><a class="reference internal" href="#catch-unresolved-calls-entry">Catch unresolved-calls entry</a></li>
<li class="toctree-l4"><a class="reference internal" href="#location-annotations">Location annotations</a></li>
<li class="toctree-l4"><a class="reference internal" href="#visibility-modifiers">Visibility modifiers</a></li>
</ul>
</li>
<li class="toctree-l3"><a class="reference internal" href="#envfree-annotations"><code class="docutils literal notranslate"><span class="pre">envfree</span></code> annotations</a></li>
<li class="toctree-l3"><a class="reference internal" href="#optional-annotations"><code class="docutils literal notranslate"><span class="pre">optional</span></code> annotations</a></li>
<li class="toctree-l3"><a class="reference internal" href="#with-env-e-clauses"><code class="docutils literal notranslate"><span class="pre">with(env</span> <span class="pre">e)</span></code> clauses</a></li>
<li class="toctree-l3"><a class="reference internal" href="#summaries"><button class="toctree-expand" title="Open/close menu"></button>Summaries</a><ul>
<li class="toctree-l4"><a class="reference internal" href="#summary-application">Summary application</a></li>
<li class="toctree-l4"><a class="reference internal" href="#summary-resolution">Summary resolution</a></li>
<li class="toctree-l4"><a class="reference internal" href="#summary-types">Summary types</a></li>
</ul>
</li>
</ul>
</li>
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
      <li class="breadcrumb-item active">The Methods Block</li>
      <li class="wy-breadcrumbs-aside">
            <a href="../../_sources/docs/cvl/methods.md.txt" rel="nofollow"> View page source</a>
      </li>
  </ul>
  <hr>
</div>
          <div role="main" class="document" itemscope="itemscope" itemtype="http://schema.org/Article">
           <div itemprop="articleBody">
             
  <section id="the-methods-block">
<span id="methods-block"></span><h1><a class="toc-backref" href="#id8" role="doc-backlink">The Methods Block</a><a class="headerlink" href="#the-methods-block" title="Link to this heading"></a></h1>
<p>The <code class="docutils literal notranslate"><span class="pre">methods</span></code> block contains additional information about contract methods.
Although you can call contract functions from CVL even if they are not
declared in the methods block, the methods block allows users to specify
additional information about contract methods, and can help document the
expected interface of the contract.</p>
<p>There are two kinds of declarations:</p>
<ul class="simple">
<li><p><strong>Non-summary declarations</strong> document the interface between the specification
and the contracts used during verification (see <a class="reference internal" href="#envfree"><span class="std std-ref">envfree annotations</span></a>).  Non-summary
declarations also support spec reuse by allowing specs written against a
complete interface to be checked against a contract that only implements part
of the interface (see <a class="reference internal" href="#optional"><span class="std std-ref">optional annotations</span></a>).</p></li>
<li><p><strong>Summary declarations</strong> are used to replace calls to certain contract methods.
Summaries allow the Prover to reason about external contracts whose code is
unavailable.  They can also be useful to simplify the code being verified to
circumvent timeouts.  See <a class="reference internal" href="#summaries"><span class="std std-ref">Summaries</span></a>.</p></li>
</ul>
<div class="admonition caution">
<p class="admonition-title">Caution</p>
<p>Summary declarations change the way that some function calls are interpreted,
and are therefore <a class="reference internal" href="../user-guide/glossary.html#term-unsound"><span class="xref std std-term">unsound</span></a> (with the exception of <code class="docutils literal notranslate"><span class="pre">HAVOC_ALL</span></code> summaries
which are always sound, and <code class="docutils literal notranslate"><span class="pre">NONDET</span></code> summaries which are sound for <code class="docutils literal notranslate"><span class="pre">view</span></code>
functions).</p>
</div>
<nav class="contents" id="contents">
<p class="topic-title">Contents</p>
<ul class="simple">
<li><p><a class="reference internal" href="#the-methods-block" id="id8">The Methods Block</a></p>
<ul>
<li><p><a class="reference internal" href="#syntax" id="id9">Syntax</a></p></li>
<li><p><a class="reference internal" href="#methods-entry-patterns" id="id10">Methods entry patterns</a></p>
<ul>
<li><p><a class="reference internal" href="#exact-entries" id="id11">Exact entries</a></p></li>
<li><p><a class="reference internal" href="#wildcard-entries" id="id12">Wildcard entries</a></p></li>
<li><p><a class="reference internal" href="#catch-all-entries" id="id13">Catch-all entries</a></p></li>
<li><p><a class="reference internal" href="#catch-unresolved-calls-entry" id="id14">Catch unresolved-calls entry</a></p></li>
<li><p><a class="reference internal" href="#location-annotations" id="id15">Location annotations</a></p></li>
<li><p><a class="reference internal" href="#visibility-modifiers" id="id16">Visibility modifiers</a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#envfree-annotations" id="id17"><code class="docutils literal notranslate"><span class="pre">envfree</span></code> annotations</a></p></li>
<li><p><a class="reference internal" href="#optional-annotations" id="id18"><code class="docutils literal notranslate"><span class="pre">optional</span></code> annotations</a></p></li>
<li><p><a class="reference internal" href="#with-env-e-clauses" id="id19"><code class="docutils literal notranslate"><span class="pre">with(env</span> <span class="pre">e)</span></code> clauses</a></p></li>
<li><p><a class="reference internal" href="#summaries" id="id20">Summaries</a></p>
<ul>
<li><p><a class="reference internal" href="#summary-application" id="id21">Summary application</a></p></li>
<li><p><a class="reference internal" href="#summary-resolution" id="id22">Summary resolution</a></p></li>
<li><p><a class="reference internal" href="#summary-types" id="id23">Summary types</a></p>
<ul>
<li><p><a class="reference internal" href="#view-summaries-always-constant-per-callee-constant-and-nondet" id="id24">View summaries: <code class="docutils literal notranslate"><span class="pre">ALWAYS</span></code>, <code class="docutils literal notranslate"><span class="pre">CONSTANT</span></code>, <code class="docutils literal notranslate"><span class="pre">PER_CALLEE_CONSTANT</span></code>, and <code class="docutils literal notranslate"><span class="pre">NONDET</span></code></a></p></li>
<li><p><a class="reference internal" href="#havoc-summaries-havoc-all-and-havoc-ecf" id="id25">Havoc summaries: <code class="docutils literal notranslate"><span class="pre">HAVOC_ALL</span></code> and <code class="docutils literal notranslate"><span class="pre">HAVOC_ECF</span></code></a></p></li>
<li><p><a class="reference internal" href="#dispatcher-summaries" id="id26"><code class="docutils literal notranslate"><span class="pre">DISPATCHER</span></code> summaries</a></p></li>
<li><p><a class="reference internal" href="#auto-summaries" id="id27"><code class="docutils literal notranslate"><span class="pre">AUTO</span></code> summaries</a></p></li>
<li><p><a class="reference internal" href="#assert-false-summaries" id="id28"><code class="docutils literal notranslate"><span class="pre">ASSERT_FALSE</span></code> summaries</a></p></li>
<li><p><a class="reference internal" href="#expression-summaries" id="id29">Expression summaries</a></p></li>
</ul>
</li>
</ul>
</li>
</ul>
</li>
</ul>
</nav>
<section id="syntax">
<h2><a class="toc-backref" href="#id9" role="doc-backlink">Syntax</a><a class="headerlink" href="#syntax" title="Link to this heading"></a></h2>
<div class="versionchanged">
<p><span class="versionmodified changed">Changed in version 4.0: </span>The syntax for methods block entries <a class="reference internal" href="cvl2/changes.html"><span class="doc">changed in CVL 2</span></a>.</p>
</div>
<p>The syntax for the <code class="docutils literal notranslate"><span class="pre">methods</span></code> block is given by the following <a class="reference internal" href="overview.html#ebnf-syntax"><span class="std std-ref">EBNF grammar</span></a>:</p>
<div class="highlight-default notranslate"><div class="highlight"><pre id="codecell0"><span></span><span class="n">methods</span>          <span class="p">:</span><span class="o">:=</span> <span class="s2">"methods"</span> <span class="s2">"{"</span> <span class="p">{</span> <span class="n">method_spec</span> <span class="p">}</span> <span class="s2">"}"</span>

<span class="n">method_spec</span>      <span class="p">:</span><span class="o">:=</span> <span class="s2">"function"</span>
                     <span class="p">(</span> <span class="n">exact_pattern</span> <span class="o">|</span> <span class="n">wildcard_pattern</span> <span class="o">|</span> <span class="n">catch_all_pattern</span> <span class="o">|</span> <span class="n">catch_unresolved_calls_pattern</span> <span class="p">)</span>
                     <span class="p">[</span> <span class="s2">"returns"</span> <span class="s2">"("</span> <span class="n">evm_types</span> <span class="s2">")"</span> <span class="p">]</span>
                     <span class="p">[</span> <span class="s2">"envfree"</span> <span class="o">|</span>  <span class="s2">"with"</span> <span class="s2">"("</span> <span class="s2">"env"</span> <span class="nb">id</span> <span class="s2">")"</span> <span class="p">]</span>
                     <span class="p">[</span> <span class="s2">"optional"</span> <span class="p">]</span>
                     <span class="p">[</span> <span class="s2">"=&gt;"</span> <span class="n">method_summary</span> <span class="p">[</span> <span class="s2">""</span> <span class="o">|</span> <span class="s2">"UNRESOLVED"</span> <span class="o">|</span> <span class="s2">"ALL"</span> <span class="o">|</span> <span class="s2">"DELETE"</span> <span class="p">]</span> <span class="p">]</span>
                     <span class="s2">";"</span>

<span class="n">exact_pattern</span>    <span class="p">:</span><span class="o">:=</span> <span class="p">[</span> <span class="nb">id</span> <span class="s2">"."</span> <span class="p">]</span> <span class="nb">id</span> <span class="s2">"("</span> <span class="n">evm_params</span> <span class="s2">")"</span> <span class="n">visibility</span> <span class="p">[</span> <span class="s2">"returns"</span> <span class="s2">"("</span> <span class="n">evm_types</span> <span class="s2">")"</span> <span class="p">]</span>
<span class="n">wildcard_pattern</span> <span class="p">:</span><span class="o">:=</span> <span class="s2">"_"</span> <span class="s2">"."</span> <span class="nb">id</span> <span class="s2">"("</span> <span class="n">evm_params</span> <span class="s2">")"</span> <span class="n">visibility</span>
<span class="n">catch_all_pattern</span> <span class="p">:</span><span class="o">:=</span> <span class="nb">id</span> <span class="s2">"."</span> <span class="s2">"_"</span> <span class="s2">"external"</span>
<span class="n">catch_unresolved_calls_pattern</span> <span class="p">:</span><span class="o">:=</span> <span class="s2">"_"</span> <span class="s2">"."</span> <span class="s2">"_"</span> <span class="s2">"external"</span>

<span class="n">visibility</span> <span class="p">:</span><span class="o">:=</span> <span class="s2">"internal"</span> <span class="o">|</span> <span class="s2">"external"</span>

<span class="n">evm_param</span> <span class="p">:</span><span class="o">:=</span> <span class="n">evm_type</span> <span class="p">[</span> <span class="nb">id</span> <span class="p">]</span>

<span class="n">method_summary</span>   <span class="p">:</span><span class="o">:=</span> <span class="s2">"ALWAYS"</span> <span class="s2">"("</span> <span class="n">value</span> <span class="s2">")"</span>
                   <span class="o">|</span> <span class="s2">"CONSTANT"</span>
                   <span class="o">|</span> <span class="s2">"PER_CALLEE_CONSTANT"</span>
                   <span class="o">|</span> <span class="s2">"NONDET"</span>
                   <span class="o">|</span> <span class="s2">"HAVOC_ECF"</span>
                   <span class="o">|</span> <span class="s2">"HAVOC_ALL"</span>
                   <span class="o">|</span> <span class="s2">"DISPATCHER"</span> <span class="p">[</span> <span class="s2">"("</span> <span class="p">(</span> <span class="s2">"true"</span> <span class="o">|</span> <span class="s2">"false"</span> <span class="p">)</span> <span class="s2">")"</span> <span class="p">]</span>
                   <span class="o">|</span> <span class="s2">"AUTO"</span>
                   <span class="o">|</span> <span class="s2">"ASSERT_FALSE"</span>
                   <span class="o">|</span> <span class="n">expr</span> <span class="p">[</span> <span class="s2">"expect"</span> <span class="nb">id</span> <span class="p">]</span>
                   <span class="o">|</span> <span class="s2">"DISPATCH"</span> <span class="p">[</span> <span class="s2">"(optimistic=false)"</span> <span class="p">]</span>  <span class="s2">"["</span> <span class="n">dispatch_list_pattern</span> <span class="p">[</span><span class="s2">","</span><span class="p">]</span> <span class="o">|</span> <span class="n">empty</span> <span class="s2">"]"</span> <span class="s2">"default"</span> <span class="n">method_summary</span>
                   <span class="o">|</span> <span class="s2">"DISPATCH"</span> <span class="p">[</span> <span class="s2">"(optimistic=true)"</span> <span class="p">]</span>  <span class="s2">"["</span> <span class="n">dispatch_list_pattern</span> <span class="p">[</span><span class="s2">","</span><span class="p">]</span> <span class="o">|</span> <span class="n">empty</span> <span class="s2">"]"</span>

<span class="n">dispatch_list_patterns</span> <span class="p">:</span><span class="o">:=</span> <span class="n">dispatch_list_patterns</span> <span class="s2">","</span> <span class="n">dispatch_pattern</span>
                          <span class="o">|</span> <span class="n">dispatch_pattern</span>

<span class="n">dispatch_pattern</span> <span class="p">:</span><span class="o">:=</span> <span class="o">|</span> <span class="s2">"_"</span> <span class="s2">"."</span> <span class="nb">id</span> <span class="s2">"("</span> <span class="n">evm_params</span> <span class="s2">")"</span>
                     <span class="o">|</span> <span class="nb">id</span> <span class="s2">"."</span> <span class="s2">"_"</span>
                     <span class="o">|</span> <span class="nb">id</span> <span class="s2">"."</span> <span class="nb">id</span> <span class="s2">"("</span> <span class="n">evm_params</span> <span class="s2">")"</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell0">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>See <a class="reference internal" href="types.html"><span class="doc">Types</span></a> for the <code class="docutils literal notranslate"><span class="pre">evm_type</span></code> production.  See <a class="reference internal" href="basics.html"><span class="doc">Basic Syntax</span></a>
for the <code class="docutils literal notranslate"><span class="pre">id</span></code> production.  See <a class="reference internal" href="expr.html"><span class="doc">Expressions</span></a> for the <code class="docutils literal notranslate"><span class="pre">expr</span></code> production.</p>
</section>
<section id="methods-entry-patterns">
<span id="methods-entries"></span><h2><a class="toc-backref" href="#id10" role="doc-backlink">Methods entry patterns</a><a class="headerlink" href="#methods-entry-patterns" title="Link to this heading"></a></h2>
<p>Each entry in the methods block contains a pattern that matches some set of
contract functions.</p>
<ul class="simple">
<li><p><a class="reference internal" href="#exact-methods-entries"><span class="std std-ref">Exact entries</span></a> match a single method of a single contract.</p></li>
<li><p><a class="reference internal" href="#wildcard-methods-entries"><span class="std std-ref">Wildcard entries</span></a> match a single method signature on all contracts.</p></li>
<li><p><a class="reference internal" href="#catch-all-entries"><span class="std std-ref">Catch-all entries</span></a> apply a single summary to all methods of a specific contract.</p></li>
<li><p><a class="reference internal" href="#catch-unresolved-calls-entry"><span class="std std-ref">Catch unresolved-calls entry</span></a> apply a summary to all calls that cannot be statically resolved in any contract.</p></li>
</ul>
<section id="exact-entries">
<span id="exact-methods-entries"></span><h3><a class="toc-backref" href="#id11" role="doc-backlink">Exact entries</a><a class="headerlink" href="#exact-entries" title="Link to this heading"></a></h3>
<p>An exact methods block entry matches a single method of a single contract.
If the contract name is omitted, the default is <code class="docutils literal notranslate"><span class="pre">currentContract</span></code>.
For example,</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell1"><span></span><span class="kr">methods</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kd">function</span><span class="w"> </span><span class="nc">C</span><span class="p">.</span><span class="nf">f</span><span class="p">(</span><span class="kt">uint</span><span class="w"> </span>x<span class="p">)</span><span class="w"> </span><span class="kr">external</span><span class="w"> </span><span class="kr">returns</span><span class="p">(</span><span class="kt">uint</span><span class="p">);</span>
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
<p>will match the external function <code class="docutils literal notranslate"><span class="pre">f</span></code> of the contract <code class="docutils literal notranslate"><span class="pre">C</span></code>.</p>
<p>Exact methods block entries must include a return type; the Prover will check
that the declared return type matches the return type of the contract function.</p>
<p>Exact entries may contain <a class="reference internal" href="#summaries"><span class="std std-ref">summaries</span></a>, <a class="reference internal" href="#envfree"><span class="std std-ref">envfree annotations</span></a>,
<a class="reference internal" href="#optional"><span class="std std-ref">optional annotations</span></a>, and <a class="reference internal" href="#with-env"><span class="std std-ref">with(env e) clauses</span></a>.</p>
<p>It is possible for an exact entry to overlap with another entry; see
<a class="reference internal" href="#summary-resolution"><span class="std std-ref">Summary resolution</span></a> for information on how summaries are resolved.</p>
</section>
<section id="wildcard-entries">
<span id="wildcard-methods-entries"></span><h3><a class="toc-backref" href="#id12" role="doc-backlink">Wildcard entries</a><a class="headerlink" href="#wildcard-entries" title="Link to this heading"></a></h3>
<div class="versionadded">
<p><span class="versionmodified added">Added in version 4.0: </span>Wildcard entries were <a class="reference internal" href="cvl2/changes.html#cvl2-wildcards"><span class="std std-ref">introduced with CVL 2</span></a>.</p>
</div>
<p>A wildcard entry matches any function in any contract with the indicated name,
argument types, and visibility.
For example,</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell2"><span></span><span class="kr">methods</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kd">function</span><span class="w"> </span><span class="nc">_</span><span class="p">.</span><span class="nf">f</span><span class="p">(</span><span class="kt">uint</span><span class="w"> </span>x<span class="p">)</span><span class="w"> </span><span class="kr">external</span><span class="w"> </span><span class="kp">=&gt;</span><span class="w"> </span><span class="kc">NONDET</span><span class="p">;</span>
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
<p>will match any external function called <code class="docutils literal notranslate"><span class="pre">f(uint)</span></code> in any contract.</p>
<p>Wildcard entries must not declare a return type, since different matched
methods may return different types.</p>
<p>Wildcard entries may not have <a class="reference internal" href="#envfree"><span class="std std-ref">envfree annotations</span></a> or <a class="reference internal" href="#optional"><span class="std std-ref">optional annotations</span></a>; their only
purpose is <a class="reference internal" href="#summaries"><span class="std std-ref">summarization</span></a>.  Therefore, wildcard entries must
have a summary.</p>
<p>It is possible for a wildcard entry to overlap with another entry; see
<a class="reference internal" href="#summary-resolution"><span class="std std-ref">Summary resolution</span></a> for information on how summaries are resolved.</p>
</section>
<section id="catch-all-entries">
<span id="id1"></span><h3><a class="toc-backref" href="#id13" role="doc-backlink">Catch-all entries</a><a class="headerlink" href="#catch-all-entries" title="Link to this heading"></a></h3>
<p>Sometimes the behavior of a contract in the scene is irrelevant
to the properties being verified. For example, the exact behavior of an external library contract
may be unimportant for a particular verification project.</p>
<p>So-called “catch-all” entries are useful in these situations. A catch-all entry is
used to apply a single <a class="reference internal" href="#summaries"><span class="std std-ref">summary</span></a> to all functions that are declared in
a given contract. For example:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell3"><span></span><span class="kr">methods</span><span class="w"> </span><span class="p">{</span>
<span class="w">   </span><span class="kd">function</span><span class="w"> </span><span class="nc">SomeLibrary</span><span class="p">.</span><span class="nf">_</span><span class="w"> </span><span class="kr">external</span><span class="w"> </span><span class="kp">=&gt;</span><span class="w"> </span><span class="kc">NONDET</span><span class="p">;</span>
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
<p>Will apply the <code class="docutils literal notranslate"><span class="pre">NONDET</span></code> <a class="reference internal" href="#havoc-summary"><span class="std std-ref">havoc summary</span></a> in place of
<em>every</em> call to a function in the <code class="docutils literal notranslate"><span class="pre">SomeLibrary</span></code> contract. Note that there are no parameter types
<em>or</em> return types for this entry: it refers to all methods in a contract, and cannot be
further refined with parameter type information.
Catch-all summaries apply only to <code class="docutils literal notranslate"><span class="pre">external</span></code> methods, and therefore
the <code class="docutils literal notranslate"><span class="pre">external</span></code> <a class="reference internal" href="#methods-visibility"><span class="std std-ref">visibility modifier</span></a> is required.
Further, the only purpose of catch-all entries is to apply a summary to all
external methods in a contract, so a summary is required. However, only
<a class="reference internal" href="#havoc-summary"><span class="std std-ref">havocing summaries</span></a> are allowed for these entries.
Finally, <a class="reference internal" href="#envfree"><span class="std std-ref">envfree annotations</span></a> and <a class="reference internal" href="#optional"><span class="std std-ref">optional annotations</span></a> keywords are not allowed for
catch-all entries.</p>
<p>It is possible for a catch-all summary to overlap with another entry; see
<a class="reference internal" href="#summary-resolution"><span class="std std-ref">Summary resolution</span></a> for information on how summaries are resolved.</p>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>Catch-all summaries are only applied when the Prover can definitively show that
the target of a call resolves to the contract mentioned in the catch-all summary.
For library contracts (a common use case for these catch-all summaries)
the Prover is almost always able to resolve the target contract.</p>
<p>For example, if you have an entry <code class="docutils literal notranslate"><span class="pre">function</span> <span class="pre">Token._</span> <span class="pre">external</span> <span class="pre">=&gt;</span> <span class="pre">NONDET;</span></code>,
where the contract <code class="docutils literal notranslate"><span class="pre">Token</span></code> has a <code class="docutils literal notranslate"><span class="pre">burn()</span></code> method, the Prover will <em>not</em>
apply the <code class="docutils literal notranslate"><span class="pre">NONDET</span></code> summary for the call <code class="docutils literal notranslate"><span class="pre">t.burn()</span></code>, unless it can prove that
<code class="docutils literal notranslate"><span class="pre">t</span></code> must hold the address of the <code class="docutils literal notranslate"><span class="pre">Token</span></code> contract. The “Rule Call Resolution” panel
shown in the web report can indicate whether a summary was applied.</p>
</div>
</section>
<section id="catch-unresolved-calls-entry">
<span id="id2"></span><h3><a class="toc-backref" href="#id14" role="doc-backlink">Catch unresolved-calls entry</a><a class="headerlink" href="#catch-unresolved-calls-entry" title="Link to this heading"></a></h3>
<p>Example:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell4"><span></span><span class="kr">methods</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="c1">// Applies to all unresolved calls called within `C.foo()`</span>
<span class="w">    </span>unresolved<span class="w"> </span><span class="kr">external</span><span class="w"> </span>in<span class="w"> </span>C<span class="p">.</span>foo<span class="p">()</span><span class="w"> </span><span class="kp">=&gt;</span><span class="w"> </span><span class="kc">DISPATCH</span><span class="w"> </span><span class="p">[</span>
<span class="w">        </span>D<span class="p">.</span>baz<span class="p">()</span>
<span class="w">    </span><span class="p">]</span><span class="w"> </span><span class="kr">default</span><span class="w"> </span>HAVOC_ECF<span class="p">;</span>

<span class="w">    </span><span class="c1">// Applies to all unresolved calls in the scene (except ones specified by more refined catch-unresolved-calls entries)</span>
<span class="w">    </span>unresolved<span class="w"> </span><span class="kr">external</span><span class="w"> </span>in<span class="w"> </span>_<span class="p">.</span>_<span class="w"> </span><span class="kp">=&gt;</span><span class="w"> </span><span class="kc">DISPATCH</span><span class="w"> </span><span class="p">[</span>
<span class="w">        </span>C<span class="p">.</span>foo<span class="p">(</span><span class="kt">uint</span><span class="p">),</span>
<span class="w">        </span>_<span class="p">.</span>bar<span class="p">(</span><span class="kt">address</span><span class="p">),</span><span class="w"> </span><span class="c1">// Will resolve to all available functions with the signature "bar(address)", specifically Other.bar(address)</span>
<span class="w">        </span>C<span class="p">.</span>_<span class="w"> </span><span class="c1">// Will resolve to all functions in C, specifically C.foo(uint) and C.baz(bool)</span>
<span class="w">    </span><span class="p">]</span><span class="w"> </span><span class="kr">default</span><span class="w"> </span>NONDET<span class="p">;</span>

<span class="w">    </span><span class="c1">// An optimistic dispatcher can be used to enforce resolving all unresolved calls to a specific method.</span>
<span class="w">    </span><span class="c1">// Be aware: In case the method C.foo(uint) doesn't exist or the sighash doesn't match, this create vacuity.</span>
<span class="w">    </span>unresolved<span class="w"> </span><span class="kr">external</span><span class="w"> </span>in<span class="w"> </span>_<span class="p">.</span>_<span class="w"> </span><span class="kp">=&gt;</span><span class="w"> </span><span class="kc">DISPATCH</span><span class="p">(</span>optimistic<span class="o">=</span>true<span class="p">)</span><span class="w"> </span><span class="p">[</span>
<span class="w">        </span>C<span class="p">.</span>foo<span class="p">(</span><span class="kt">uint</span><span class="p">)</span>
<span class="w">    </span><span class="p">];</span>
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
<p>Catch unresolved-calls entries are a special type of summary declaration that
instructs the Prover to replace calls to unresolved external function calls
with a specific kind of summary, dispatch list.
By default, the Prover will use an <a class="reference internal" href="#auto-summary"><span class="std std-ref">AUTO summary</span></a> for
unresolved function calls, but that may produce spurious counter examples.
Catch unresolved-calls entries let the user refine the summary used for
unresolved function calls.</p>
<p>Note that the catch unresolved-calls entry <em>only applies</em> in cases where the called
function’s <em>sighash</em> is unresolved. In the example below there is a function
call <code class="docutils literal notranslate"><span class="pre">target.call(data)</span></code>. The sighash of the called function depends on the parameter
<code class="docutils literal notranslate"><span class="pre">data</span></code> and cannot be known beforehand.</p>
<div class="highlight-solidity notranslate"><div class="highlight"><pre id="codecell5"><span></span><span class="w">    </span><span class="kt">function</span><span class="w"> </span><span class="nv">flashLoan</span><span class="p">(</span>
<span class="w">        </span><span class="kt">uint256</span><span class="w"> </span><span class="nv">borrowAmount</span><span class="p">,</span>
<span class="w">        </span><span class="kt">address</span><span class="w"> </span><span class="nv">borrower</span><span class="p">,</span>
<span class="w">        </span><span class="kt">address</span><span class="w"> </span><span class="nv">target</span><span class="p">,</span>
<span class="w">        </span><span class="kt">bytes</span><span class="w"> </span><span class="nv">calldata</span><span class="w"> </span>data
<span class="w">    </span><span class="p">)</span>
<span class="w">        </span><span class="kt">external</span>
<span class="w">    </span><span class="p">{</span>
<span class="w">        </span><span class="kt">uint256</span><span class="w"> </span><span class="nv">balanceBefore</span><span class="w"> </span><span class="o">=</span><span class="w"> </span>damnValuableToken<span class="p">.</span>balanceOf<span class="p">(</span><span class="kt">address</span><span class="p">(</span><span class="kt">this</span><span class="p">));</span>
<span class="w">        </span><span class="kt">require</span><span class="p">(</span>balanceBefore<span class="w"> </span><span class="o">&gt;=</span><span class="w"> </span>borrowAmount<span class="p">,</span><span class="w"> </span><span class="s2">"Not enough tokens in pool"</span><span class="p">);</span>
<span class="w">        </span>
<span class="w">        </span>damnValuableToken<span class="p">.</span>transfer<span class="p">(</span>borrower<span class="p">,</span><span class="w"> </span>borrowAmount<span class="p">);</span>
<span class="hll"><span class="w">        </span><span class="p">(</span><span class="kt">bool</span><span class="w"> </span><span class="nv">success</span><span class="p">,</span><span class="w"> </span><span class="p">)</span><span class="w"> </span><span class="o">=</span><span class="w"> </span>target<span class="p">.</span>call<span class="p">(</span>data<span class="p">);</span>
</span><span class="w">        </span><span class="kt">require</span><span class="p">(</span>success<span class="p">,</span><span class="w"> </span><span class="s2">"External call failed"</span><span class="p">);</span>

<span class="w">        </span><span class="kt">uint256</span><span class="w"> </span><span class="nv">balanceAfter</span><span class="w"> </span><span class="o">=</span><span class="w"> </span>damnValuableToken<span class="p">.</span>balanceOf<span class="p">(</span><span class="kt">address</span><span class="p">(</span><span class="kt">this</span><span class="p">));</span>
<span class="w">        </span><span class="kt">require</span><span class="p">(</span>balanceAfter<span class="w"> </span><span class="o">&gt;=</span><span class="w"> </span>balanceBefore<span class="p">,</span><span class="w"> </span><span class="s2">"Flash loan hasn't been paid back"</span><span class="p">);</span>
<span class="w">    </span><span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell5">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>One can specify the scope (<code class="docutils literal notranslate"><span class="pre">unresolved</span> <span class="pre">external</span> <span class="pre">in</span> <span class="pre">&lt;scope&gt;</span></code>) for which the
unresolved summary will apply. The options are:</p>
<ul class="simple">
<li><p><code class="docutils literal notranslate"><span class="pre">Contract.functionSignature()</span></code> for summarizing unresolved calls within this function</p></li>
<li><p><code class="docutils literal notranslate"><span class="pre">_.functionSignature()</span></code> for summarizing unresolved calls within this function in any contract</p></li>
<li><p><code class="docutils literal notranslate"><span class="pre">Contract._</span></code> for summarizing unresolved calls in any function of the given contract</p></li>
<li><p><code class="docutils literal notranslate"><span class="pre">_._</span></code> for summarizing all unresolved calls in the scene.</p></li>
</ul>
<p>If multiple catch unresolved-calls entries exist, the order of precedence is the
order of the above list, from top to bottom.</p>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>If <code class="docutils literal notranslate"><span class="pre">C.foo</span></code> has a (resolved) external call to <code class="docutils literal notranslate"><span class="pre">D.bar</span></code>, and <code class="docutils literal notranslate"><span class="pre">D.bar</span></code> contains an
unresolved call, a catch-unresolved-calls entry that applies to <code class="docutils literal notranslate"><span class="pre">C.foo</span></code> will
<em>not</em> be applied to this unresolved call - only an entry that matches <code class="docutils literal notranslate"><span class="pre">D.bar</span></code>
will be used.</p>
</div>
<p>Catch unresolved-calls entries can only be summarized with a dispatch list
summary (and a dispatch list summary is only applicable for a catch
unresolved-calls entries).</p>
<p>As with <code class="docutils literal notranslate"><span class="pre">DISPATCH</span></code>, there are optimistic and pessimistic dispatch lists. This can
be specified via <code class="docutils literal notranslate"><span class="pre">DISPATCHER(optimistic=&lt;true|false&gt;).</span> <span class="pre">When</span> <span class="pre">the</span> </code>optimistic` option
is not specified in parentheses, the Prover will use a pessimistic dispatch list to
ensure sound reasoning.</p>
<p>A dispatch list summary directs the Prover to consider each of the methods
described in the list as possible candidates for this unresolved call.
The Prover will choose dynamically, that is, for each potential run of the
program, which of them to call.
It is done accurately by matching the selector from the call’s arguments
to that of the methods described in the dispatch list.
When using a pessimistic dispatch list and no method from the list matches,
it will use the <code class="docutils literal notranslate"><span class="pre">default</span></code> summary. When using the optimistic dispatch
list, an <code class="docutils literal notranslate"><span class="pre">ASSUME</span> <span class="pre">FALSE;</span></code> is inlined by the Prover; see the example below.
The dispatch list will contain a list of patterns and the default summary to use in case no function matched the selector.
The possible patterns are:</p>
<ol class="arabic simple">
<li><p>Exact function - a pattern specifying both a contract, and the
function signature.
Example: <code class="docutils literal notranslate"><span class="pre">C.foo(uint)</span></code></p></li>
<li><p>Wildcard contract - a pattern specifying the function signature to match
this signature on all available contracts (including the primary contract).
Example: <code class="docutils literal notranslate"><span class="pre">_.bar(address)</span></code></p></li>
<li><p>Wildcard function - a pattern specifying a contract, and matches all
external functions in specified contract (This pattern will also include the
contract’s fallback if it’s implemented).
Example: <code class="docutils literal notranslate"><span class="pre">C._</span></code></p></li>
</ol>
<p>The example entry at the head of this section will specify three functions to
route calls to:</p>
<ol class="arabic simple">
<li><p><code class="docutils literal notranslate"><span class="pre">C.foo(uint)</span></code></p></li>
<li><p><code class="docutils literal notranslate"><span class="pre">Other.bar(address)</span></code></p></li>
<li><p><code class="docutils literal notranslate"><span class="pre">C.baz(bool)</span></code></p></li>
</ol>
<p>Entry annotations (<a class="reference internal" href="#envfree"><span class="std std-ref">envfree annotations</span></a>, <a class="reference internal" href="#optional"><span class="std std-ref">optional annotations</span></a>) and the <code class="docutils literal notranslate"><span class="pre">returns</span></code> clause
are not allowed on an unresolved-calls entry.
Also, the visibility is always external, and no policy should be specified.</p>
<p>For an unresolved function call being summarized with the dispatch list above,
the Prover will replace the call with a dynamic resolution of the function call.
That is something in the lines of:</p>
<div class="highlight-solidity notranslate"><div class="highlight"><pre id="codecell6"><span></span><span class="kt">function</span><span class="w"> </span><span class="nv">summarized</span><span class="p">(</span><span class="kt">address</span><span class="w"> </span><span class="nv">a</span><span class="p">,</span><span class="w"> </span><span class="kt">bytes</span><span class="w"> </span><span class="nv">calldata</span><span class="w"> </span>data<span class="p">)</span><span class="w"> </span><span class="kt">external</span><span class="w"> </span><span class="p">{</span>
<span class="w">  </span><span class="kt">if</span><span class="w"> </span><span class="p">(</span><span class="kt">uint32</span><span class="p">(</span>data<span class="p">[</span><span class="m m-Decimal">0</span><span class="o">:</span><span class="m m-Decimal">4</span><span class="p">])</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="mh">0x11111111</span><span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span><span class="kt">address</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="kt">address</span><span class="p">(</span>c<span class="p">))</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="c1">// Function selector was equal to foo's</span>
<span class="w">    </span><span class="c1">// Call C.foo(...)</span>
<span class="w">  </span><span class="p">}</span><span class="w"> </span><span class="kt">else</span><span class="w"> </span><span class="kt">if</span><span class="w"> </span><span class="p">(</span><span class="kt">uint32</span><span class="p">(</span>data<span class="p">[</span><span class="m m-Decimal">0</span><span class="o">:</span><span class="m m-Decimal">4</span><span class="p">])</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="mh">0x22222222</span><span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span><span class="kt">address</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="kt">address</span><span class="p">(</span>o<span class="p">))</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="c1">// Function selector was equal to bar's</span>
<span class="w">    </span><span class="c1">// Call O.bar(...)</span>
<span class="w">  </span><span class="p">}</span><span class="w"> </span><span class="kt">else</span><span class="w"> </span><span class="kt">if</span><span class="w"> </span><span class="p">(</span><span class="kt">uint32</span><span class="p">(</span>data<span class="p">[</span><span class="m m-Decimal">0</span><span class="o">:</span><span class="m m-Decimal">4</span><span class="p">])</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="mh">0x33333333</span><span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span><span class="kt">address</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="kt">address</span><span class="p">(</span>c<span class="p">))</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="c1">// Function selector was equal to baz's</span>
<span class="w">    </span><span class="c1">// Call C.baz(...)</span>
<span class="w">  </span><span class="p">}</span><span class="w"> </span><span class="kt">else</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="c1">// In the case of the DISPATCHER(optimistic=false), the summary </span>
<span class="w">    </span><span class="c1">// specified after the "default" is inlined here. This is typically a HAVOC_ALL,</span>
<span class="w">    </span><span class="c1">// HAVOC_ECF or a NONDET.</span>
<span class="w">    </span><span class="c1">// In the case of the DISPATCHER(optimistic=true) option, no default is used </span>
<span class="w">    </span><span class="c1">// and the Prover inlines an ASSUME FALSE; at this location marking </span>
<span class="w">    </span><span class="c1">// this branch as unreachable.</span>
<span class="w">  </span><span class="p">}</span>
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
<p>The dispatch list summary will create a dynamic resolution process that
determines the specific function to call at runtime based on the function
signature and the target contract address.
In the provided example, when an unresolved function call is encountered, the
Prover dynamically resolves it by inspecting the function selector in the
transaction data and the target contract address.
By comparing the function selector against known signatures and verifying the
contract address, the Prover identifies the appropriate function to call.</p>
<p>This dynamic resolution mechanism is crucial for refining specifications
because it enables the Prover to accurately model the behavior of smart
contracts, even when the exact function being called is not known statically.
By replacing unresolved calls with dynamically resolved calls in the dispatch
list summary, the specification becomes more precise, leading to more accurate
verification results and improved assurance in the correctness of the smart
contract.</p>
</section>
<section id="location-annotations">
<h3><a class="toc-backref" href="#id15" role="doc-backlink">Location annotations</a><a class="headerlink" href="#location-annotations" title="Link to this heading"></a></h3>
<div class="versionadded">
<p><span class="versionmodified added">Added in version 4.0: </span>Location annotations were <a class="reference internal" href="cvl2/changes.html#cvl2-locations"><span class="std std-ref">introduced with CVL 2</span></a>.</p>
</div>
<p>Methods block entries for internal functions must contain either <code class="docutils literal notranslate"><span class="pre">calldata</span></code>,
<code class="docutils literal notranslate"><span class="pre">memory</span></code>, or <code class="docutils literal notranslate"><span class="pre">storage</span></code> annotations for all arguments with reference types (such
as arrays).</p>
<p>Entries for external functions may have <code class="docutils literal notranslate"><span class="pre">storage</span></code> annotations for argument
references (in Solidity, external library functions may have storage arguments).
If a reference-type argument does not have a <code class="docutils literal notranslate"><span class="pre">storage</span></code> annotation, the entry
will apply to a function that has either a <code class="docutils literal notranslate"><span class="pre">calldata</span></code> or a <code class="docutils literal notranslate"><span class="pre">memory</span></code> annotation
on the argument.</p>
</section>
<section id="visibility-modifiers">
<span id="methods-visibility"></span><h3><a class="toc-backref" href="#id16" role="doc-backlink">Visibility modifiers</a><a class="headerlink" href="#visibility-modifiers" title="Link to this heading"></a></h3>
<div class="versionadded">
<p><span class="versionmodified added">Added in version 4.0: </span>Visibility modifiers were <a class="reference internal" href="cvl2/changes.html#cvl2-visibility"><span class="std std-ref">introduced with CVL 2</span></a>.</p>
</div>
<p>Entries in the methods block must be marked either <code class="docutils literal notranslate"><span class="pre">internal</span></code> or <code class="docutils literal notranslate"><span class="pre">external</span></code>; the
entry will only match a function with the indicated visibility.</p>
<p>If a function is declared <code class="docutils literal notranslate"><span class="pre">public</span></code> in Solidity, then the Solidity compiler
creates an internal implementation method, and an external wrapper method that
calls the internal implementation.  An <code class="docutils literal notranslate"><span class="pre">internal</span></code> methods block entry will
apply to the generated implementation method, while an <code class="docutils literal notranslate"><span class="pre">external</span></code> entry will
apply to the generated external wrapper method.</p>
<p>This summarization behavior can be confusing, especially because functions
called directly from CVL are not summarized.</p>
<p>Consider a public function <code class="docutils literal notranslate"><span class="pre">f</span></code>.  Suppose we provide an <code class="docutils literal notranslate"><span class="pre">internal</span></code> summary for
<code class="docutils literal notranslate"><span class="pre">f</span></code>:</p>
<ul class="simple">
<li><p>Calls from CVL to <code class="docutils literal notranslate"><span class="pre">f</span></code> <em>will</em> effectively be summarized, because CVL will call
the external function, which will then call the internal implementation, and
the internal implementation will be summarized.</p></li>
<li><p>Calls from another contract to <code class="docutils literal notranslate"><span class="pre">f</span></code> (or calls to <code class="docutils literal notranslate"><span class="pre">this.f</span></code> from <code class="docutils literal notranslate"><span class="pre">f</span></code>’s contract)
<em>will</em> effectively be summarized, again because the external function
immediately calls the summarized internal implementation.</p></li>
<li><p>Internal calls to <code class="docutils literal notranslate"><span class="pre">f</span></code> will be summarized.</p></li>
</ul>
<p>On the other hand, suppose we provide an <code class="docutils literal notranslate"><span class="pre">external</span></code> summary for <code class="docutils literal notranslate"><span class="pre">f</span></code>.  In this
case:</p>
<ul class="simple">
<li><p>Calls from CVL to <code class="docutils literal notranslate"><span class="pre">f</span></code> <em>will not</em> be summarized, because direct calls from
CVL to contract functions do not use summaries.</p></li>
<li><p>Internal calls to <code class="docutils literal notranslate"><span class="pre">f</span></code> <em>will not</em> be summarized - they will use the original
implementation.</p></li>
<li><p>External calls to <code class="docutils literal notranslate"><span class="pre">f</span></code> (from Solidity code that calls <code class="docutils literal notranslate"><span class="pre">this.f</span></code> or <code class="docutils literal notranslate"><span class="pre">c.f</span></code>) will
be summarized</p></li>
</ul>
<p>In most cases, public functions should use an <code class="docutils literal notranslate"><span class="pre">internal</span></code> summary, since this
effectively summarizes both internal and external calls to the function.</p>
</section>
</section>
<section id="envfree-annotations">
<span id="envfree"></span><h2><a class="toc-backref" href="#id17" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">envfree</span></code> annotations</a><a class="headerlink" href="#envfree-annotations" title="Link to this heading"></a></h2>
<p>Following the <code class="docutils literal notranslate"><span class="pre">returns</span></code> clause of an exact methods entry is an optional
<code class="docutils literal notranslate"><span class="pre">envfree</span></code> tag.  Marking a method
with <code class="docutils literal notranslate"><span class="pre">envfree</span></code> has two effects.  First, <a class="reference internal" href="expr.html#call-expr"><span class="std std-ref">calls</span></a> to the method
from CVL do not need to explicitly pass an <a class="reference internal" href="../user-guide/glossary.html#term-environment"><span class="xref std std-term">environment</span></a> value as the
first argument.  Second, the Prover will verify that the method implementation
in the contract being verified does not depend on any of the environment
variables.  The results of this check are displayed on the verification report
as separate rules called <code class="docutils literal notranslate"><span class="pre">envfreeFuncsStaticCheck</span></code> and
<code class="docutils literal notranslate"><span class="pre">envfreeFuncsAreNonpayable</span></code><a class="footnote-reference brackets" href="#envfree-nonpayable" id="id3" role="doc-noteref"><span class="fn-bracket">[</span>1<span class="fn-bracket">]</span></a>.</p>
</section>
<section id="optional-annotations">
<span id="optional"></span><h2><a class="toc-backref" href="#id18" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">optional</span></code> annotations</a><a class="headerlink" href="#optional-annotations" title="Link to this heading"></a></h2>
<div class="versionadded">
<p><span class="versionmodified added">Added in version 4.0: </span>Prior to <a class="reference internal" href="cvl2/changes.html#cvl2-optional"><span class="std std-ref">CVL 2</span></a>, all methods entries used the <code class="docutils literal notranslate"><span class="pre">optional</span></code>
behavior, and there was no <code class="docutils literal notranslate"><span class="pre">optional</span></code> annotation.</p>
</div>
<p>When multiple contracts implement a shared interface, it is convenient to write
a generic spec of generic rules.  Some interfaces specify optional methods that
some implementations provide and others don’t.  For example, some ERC20
implementations contain a <code class="docutils literal notranslate"><span class="pre">mint</span></code> method, but others don’t.</p>
<p>In this situation, you might like to write rules that are checked if the
contract contains the <code class="docutils literal notranslate"><span class="pre">mint</span></code> method and are skipped otherwise.</p>
<p>To do so, you can add the <code class="docutils literal notranslate"><span class="pre">optional</span></code> annotation to the exact methods block
entry for the function.  Any rules that reference an optional method will be
skipped if the method does not exist in the contract.
For example:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell7"><span></span><span class="kr">methods</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kd">function</span><span class="w"> </span><span class="nf">mint</span><span class="p">(</span><span class="kt">address</span><span class="w"> </span>_to<span class="p">,</span><span class="w"> </span><span class="kt">uint256</span><span class="w"> </span>_amount<span class="p">,</span><span class="w"> </span><span class="kt">bytes</span><span class="w"> </span>calldata<span class="w"> </span>_data<span class="p">)</span><span class="w"> </span><span class="kr">external</span><span class="w"> </span><span class="kr">optional</span><span class="p">;</span>
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
<section id="with-env-e-clauses">
<span id="with-env"></span><h2><a class="toc-backref" href="#id19" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">with(env</span> <span class="pre">e)</span></code> clauses</a><a class="headerlink" href="#with-env-e-clauses" title="Link to this heading"></a></h2>
<p>After the <code class="docutils literal notranslate"><span class="pre">optional</span></code> annotation, an entry may contain a <code class="docutils literal notranslate"><span class="pre">with(env</span> <span class="pre">e)</span></code> clause.
The <code class="docutils literal notranslate"><span class="pre">with</span></code> clause introduces a new variable (<code class="docutils literal notranslate"><span class="pre">e</span></code> for <code class="docutils literal notranslate"><span class="pre">with(env</span> <span class="pre">e)</span></code>) to represent
the <a class="reference internal" href="types.html#env"><span class="std std-ref">environment</span></a> that is passed to a summarized function; the
variable can be used in function summaries.  <code class="docutils literal notranslate"><span class="pre">with</span></code> clauses may only be used if
the entry has a function summary. See <a class="reference internal" href="#expression-summary"><span class="std std-ref">Expression summaries</span></a> below for more
information about the environment provided by the <code class="docutils literal notranslate"><span class="pre">with</span></code> clause.</p>
</section>
<section id="summaries">
<span id="id4"></span><h2><a class="toc-backref" href="#id20" role="doc-backlink">Summaries</a><a class="headerlink" href="#summaries" title="Link to this heading"></a></h2>
<p><strong>Summary declarations</strong> are used to replace calls to methods having the
given signature with something that is simpler for the Prover to reason about.
Summaries allow the Prover to reason about external contracts whose code is
unavailable.  They can also be useful to simplify the code being verified to
circumvent timeouts.</p>
<p>A summary is indicated by adding <code class="docutils literal notranslate"><span class="pre">=&gt;</span></code> followed by the summary to the end of
the entry in the methods block.  For example,</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell8"><span></span><span class="kt">function</span><span class="w"> </span><span class="nf">f</span><span class="p">(</span><span class="kt">uint</span><span class="p">)</span><span class="w"> </span><span class="kr">external</span><span class="w"> </span><span class="kr">returns</span><span class="p">(</span><span class="kt">uint</span><span class="p">)</span><span class="w"> </span><span class="o">=&gt;</span><span class="w"> </span>ALWAYS<span class="p">(</span><span class="m m-Decimal">0</span><span class="p">);</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell8">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>will replace calls to <code class="docutils literal notranslate"><span class="pre">f</span></code> with an <code class="docutils literal notranslate"><span class="pre">ALWAYS</span></code> summary, while</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell9"><span></span><span class="kt">function</span><span class="w"> </span><span class="nf">f</span><span class="p">(</span><span class="kt">uint</span><span class="w"> </span>x<span class="p">)</span><span class="w"> </span><span class="kr">external</span><span class="w"> </span><span class="kr">returns</span><span class="p">(</span><span class="kt">uint</span><span class="p">)</span><span class="w"> </span><span class="o">=&gt;</span><span class="w"> </span>cvl_function<span class="p">(</span>x<span class="p">);</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell9">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>will replace calls to <code class="docutils literal notranslate"><span class="pre">f</span></code> with the CVL function <code class="docutils literal notranslate"><span class="pre">cvl_function</span></code>.</p>
<p>There are several kinds of summaries available:</p>
<ul class="simple">
<li><p><a class="reference internal" href="#view-summary"><span class="std std-ref">View summaries: ALWAYS, CONSTANT, PER_CALLEE_CONSTANT, and NONDET</span></a>.  These assume that the called method have no side-effects
and simply replace them with a specific value.</p></li>
<li><p><a class="reference internal" href="#havoc-summary"><span class="std std-ref">Havoc summaries: HAVOC_ALL and HAVOC_ECF</span></a>.  These assume that the called method can have arbitrary
side-effects on the storage of some contracts.</p></li>
<li><p><a class="reference internal" href="#dispatcher"><span class="std std-ref">DISPATCHER summaries</span></a> assume that the receiver of the method call could be any
contract that implements the method.</p></li>
<li><p><a class="reference internal" href="#expression-summary"><span class="std std-ref">Expression summaries</span></a> replace calls to the summarized method with a CVL expression, typically <a class="reference internal" href="functions.html"><span class="doc">Functions</span></a>
or <a class="reference internal" href="ghosts.html#ghost-axioms"><span class="std std-ref">Ghost axioms</span></a>.</p></li>
<li><p><a class="reference internal" href="#auto-summary"><span class="std std-ref">AUTO summaries</span></a> are the default for unresolved calls.</p></li>
<li><p><a class="reference internal" href="#assert-false-summary"><span class="std std-ref">ASSERT_FALSE summaries</span></a>. These replace the method with an assert false, effectively checking that no such method is called.</p></li>
</ul>
<section id="summary-application">
<span id="delete-summary"></span><h3><a class="toc-backref" href="#id21" role="doc-backlink">Summary application</a><a class="headerlink" href="#summary-application" title="Link to this heading"></a></h3>
<p>To decide whether to summarize a given function call at a given call site, the
Prover first determines whether it matches any of the declarations in the
methods block, and then uses the declaration and the <em>calling context</em> to
determine whether the call should be replaced by an approximation.</p>
<p>Specifically, the matching is based on three attributes:</p>
<p>(1) The contract in which the method is defined, or a wildcard contract denoted with <code class="docutils literal notranslate"><span class="pre">_</span></code>.</p>
<p>(2) The method signature, with optional named parameters.</p>
<p>(3) The context in which it is called, either <code class="docutils literal notranslate"><span class="pre">external</span></code> or <code class="docutils literal notranslate"><span class="pre">internal</span></code>.
A Solidity function which is defined as <code class="docutils literal notranslate"><span class="pre">public</span></code> can be specified in the methods block as
either <code class="docutils literal notranslate"><span class="pre">external</span></code> or <code class="docutils literal notranslate"><span class="pre">internal</span></code>, and this affects which call sites of the function will
be summarized.</p>
<p>The ability of the Prover to match a particular call site to a method declaration
depends on whether the call was <em>resolved</em> or not, i.e., whether we know which target
contract is called and which method signature is called.
Internal calls are always resolved, but for external calls it is not always the case.
For example, the target contract may be given by a user input, and there is
no single match for the target contract:</p>
<div class="highlight-solidity notranslate"><div class="highlight"><pre id="codecell10"><span></span><span class="kt">function</span><span class="w"> </span><span class="nv">callIt</span><span class="p">(</span><span class="kt">address</span><span class="w"> </span><span class="nv">it</span><span class="p">)</span><span class="w"> </span><span class="kt">external</span><span class="w"> </span><span class="p">{</span>
<span class="w">  </span>IERC20<span class="p">(</span>it<span class="p">).</span>transfer<span class="p">(...);</span><span class="w"> </span><span class="c1">// cast `it` to an IERC20 contract and call the `transfer` method</span>
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
<p>Similarly, the method signature may also be not resolvable:</p>
<div class="highlight-solidity notranslate"><div class="highlight"><pre id="codecell11"><span></span><span class="kt">function</span><span class="w"> </span><span class="nv">callIt</span><span class="p">(</span><span class="kt">bytes</span><span class="w"> </span><span class="nv">memory</span><span class="w"> </span>data<span class="p">)</span><span class="w"> </span><span class="kt">external</span><span class="w"> </span><span class="p">{</span>
<span class="w">  </span><span class="kt">address</span><span class="p">(</span><span class="kt">this</span><span class="p">).</span>call<span class="p">(</span>data<span class="p">);</span>
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
<p>To determine whether a function call is replaced by an approximation summary, the
Prover considers all three aforementioned attributes, the resolved information,
and in addition to that, also the
application policy.  If present, the application policy must
be either <code class="docutils literal notranslate"><span class="pre">ALL</span></code>, <code class="docutils literal notranslate"><span class="pre">UNRESOLVED</span></code>, or <code class="docutils literal notranslate"><span class="pre">DELETE</span></code>.
The <code class="docutils literal notranslate"><span class="pre">ALL</span></code> policy indicates the summary should be applied to all instances of the
specified method, while <code class="docutils literal notranslate"><span class="pre">UNRESOLVED</span></code> applies only to methods that cannot be fully
resolved (i.e., either target contract or the method signature are unknown).
For internal summaries, the default is <code class="docutils literal notranslate"><span class="pre">ALL</span></code>, as all internal functions
are always resolvable; thus <code class="docutils literal notranslate"><span class="pre">UNRESOLVED</span></code> is impossible and will yield an error.
Similarly, for external summaries with contract-specific entries,
the default policy is <code class="docutils literal notranslate"><span class="pre">ALL</span></code>.
Conversely, for any external summary on wildcard contracts, the default
policy is <code class="docutils literal notranslate"><span class="pre">UNRESOLVED</span></code>. One may apply the <code class="docutils literal notranslate"><span class="pre">ALL</span></code> policy to make the summary apply
on all instances of the wildcard method, even on target contracts for which
it was resolved, e.g. by <a class="reference internal" href="../prover/cli/options.html#link"><span class="std std-ref">linking</span></a>.</p>
<p>A <code class="docutils literal notranslate"><span class="pre">DELETE</span></code> summary is similar to an <code class="docutils literal notranslate"><span class="pre">ALL</span></code> summary, except that the <code class="docutils literal notranslate"><span class="pre">DELETE</span></code>
summary removes the method from the <a class="reference internal" href="../user-guide/glossary.html#term-0"><span class="xref std std-term">scene</span></a> entirely.  Calling the method
from CVL will produce a rule violation, and <a class="reference internal" href="../user-guide/glossary.html#term-parametric-rule"><span class="xref std std-term">parametric rule</span></a>s will not
be instantiated on the deleted method.  This can drastically improve
performance if the deleted method is complex.</p>
<p>The decision to replace a call by an approximation is made as follows:</p>
<ul class="simple">
<li><p>If the function is called from CVL rather than from contract code then it is
never replaced by a summary.</p></li>
<li><p>If the code for the function is known at verification time, either because
it is a method of <code class="docutils literal notranslate"><span class="pre">currentContract</span></code> or because the receiver contract is
<code class="docutils literal notranslate"><span class="pre">linked</span></code>, then the function is only summarized if the
resolution type is <code class="docutils literal notranslate"><span class="pre">ALL</span></code>.</p></li>
<li><p>If the code for the function is not known at verification time, then the
function call must be summarized.  If no summary is given, the default summary
type is <a class="reference internal" href="#auto-summary"><span class="std std-ref">AUTO</span></a>, whose behavior is determined by the type of
function call.  In this case, the verification report will contain a contract
call resolution warning.</p></li>
</ul>
</section>
<section id="summary-resolution">
<span id="id5"></span><h3><a class="toc-backref" href="#id22" role="doc-backlink">Summary resolution</a><a class="headerlink" href="#summary-resolution" title="Link to this heading"></a></h3>
<p>With <a class="reference internal" href="#wildcard-methods-entries"><span class="std std-ref">wildcard entries</span></a>, <a class="reference internal" href="#catch-all-entries"><span class="std std-ref">catch-all entries</span></a>,
and <a class="reference internal" href="#exact-methods-entries"><span class="std std-ref">exact entries</span></a>, multiple entries could apply to a method.</p>
<p>For example, given a call to <code class="docutils literal notranslate"><span class="pre">Token.burn()</span></code> with a methods block that contains the
following entries:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell12"><span></span><span class="kr">methods</span><span class="w"> </span><span class="p">{</span>
<span class="w">   </span><span class="kd">function</span><span class="w"> </span><span class="nc">Token</span><span class="p">.</span><span class="nf">burn</span><span class="p">()</span><span class="w"> </span><span class="kr">external</span><span class="w"> </span><span class="kp">=&gt;</span><span class="w"> </span><span class="kc">HAVOC_ECF</span><span class="p">;</span>
<span class="w">   </span><span class="kd">function</span><span class="w"> </span><span class="nc">_</span><span class="p">.</span><span class="nf">burn</span><span class="p">()</span><span class="w"> </span><span class="kr">external</span><span class="w"> </span><span class="kp">=&gt;</span><span class="w"> </span><span class="kc">HAVOC_ALL</span><span class="p">;</span>
<span class="w">   </span><span class="kd">function</span><span class="w"> </span><span class="nc">Token</span><span class="p">.</span><span class="nf">_</span><span class="w"> </span><span class="kr">external</span><span class="w"> </span><span class="kp">=&gt;</span><span class="w"> </span><span class="kc">NONDET</span><span class="p">;</span>
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
<p>which summary will apply? In CVL, precedence is given to the
summary attached to the <em>most specific signature</em>. Exact entries are considered more exact
than wildcard entries, which are themselves more exact than catch-all entries. In other words,
the order of precedence for summaries are:</p>
<ol class="arabic simple">
<li><p>Summaries given for <a class="reference internal" href="#exact-methods-entries"><span class="std std-ref">exact entries</span></a></p></li>
<li><p>Summaries given for <a class="reference internal" href="#wildcard-methods-entries"><span class="std std-ref">wildcard entries</span></a></p></li>
<li><p>Summaries given for <a class="reference internal" href="#catch-all-entries"><span class="std std-ref">catch-all entries</span></a></p></li>
</ol>
<p>Thus, in this example, the <code class="docutils literal notranslate"><span class="pre">HAVOC_ECF</span></code> summary would apply.</p>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>An entry that does not have a summary attached does <em>not</em> factor into the
precedence of summary application. For example, if the first entry in the above
was instead <code class="docutils literal notranslate"><span class="pre">function</span> <span class="pre">Token.burn()</span> <span class="pre">external</span> <span class="pre">envfree;</span></code> without a summary,
the <code class="docutils literal notranslate"><span class="pre">HAVOC_ALL</span></code> of the wildcard entry will apply.</p>
</div>
</section>
<section id="summary-types">
<h3><a class="toc-backref" href="#id23" role="doc-backlink">Summary types</a><a class="headerlink" href="#summary-types" title="Link to this heading"></a></h3>
<section id="view-summaries-always-constant-per-callee-constant-and-nondet">
<span id="view-summary"></span><h4><a class="toc-backref" href="#id24" role="doc-backlink">View summaries: <code class="docutils literal notranslate"><span class="pre">ALWAYS</span></code>, <code class="docutils literal notranslate"><span class="pre">CONSTANT</span></code>, <code class="docutils literal notranslate"><span class="pre">PER_CALLEE_CONSTANT</span></code>, and <code class="docutils literal notranslate"><span class="pre">NONDET</span></code></a><a class="headerlink" href="#view-summaries-always-constant-per-callee-constant-and-nondet" title="Link to this heading"></a></h4>
<p>These four summary types treat the summarized methods as view methods: the
summarized methods are replaced by approximations that do not update the state
of any contract (aside from any balances transferred with the method call
itself).  They differ in the assumptions made about the return value:</p>
<ul class="simple">
<li><p>The <code class="docutils literal notranslate"><span class="pre">ALWAYS(v)</span></code> approximation assumes that the method always returns <code class="docutils literal notranslate"><span class="pre">v</span></code>.
The value <code class="docutils literal notranslate"><span class="pre">v</span></code> must be a literal boolean or integer.</p></li>
<li><p>The <code class="docutils literal notranslate"><span class="pre">CONSTANT</span></code> approximation assumes that all calls to methods with the given
signature always return the same result.  If the summarized method is
expected to return multiple results, the approximation returns the correct
number of values.</p></li>
<li><p>The <code class="docutils literal notranslate"><span class="pre">PER_CALLEE_CONSTANT</span></code> approximation assumes that all calls to the method
on a given receiver contract must return the same result, but that the
returned value may be different for different receiver contracts.  If the
summarized method is expected to return multiple results, the approximation
returns the correct number of values.</p></li>
<li><p>The <code class="docutils literal notranslate"><span class="pre">NONDET</span></code> approximation makes no assumptions about the return values; each
call to the summarized method may return a different result.  The number of
returned values is <em>not</em> assumed to match the requested number, unless
<a class="reference internal" href="../prover/cli/options.html#optimisticreturnsize"><span class="std std-ref">optimisticReturnsize</span></a> is specified.</p></li>
</ul>
<div class="admonition warning">
<p class="admonition-title">Warning</p>
<p>Using <code class="docutils literal notranslate"><span class="pre">CONSTANT</span></code> and <code class="docutils literal notranslate"><span class="pre">PER_CALLEE_CONSTANT</span></code> summaries for functions that have
variable-sized outputs is a potential source of <a class="reference internal" href="../user-guide/glossary.html#term-vacuity"><span class="xref std std-term">vacuity</span></a> and should be
avoided.  Prefer a <code class="docutils literal notranslate"><span class="pre">NONDET</span></code> summary where possible.</p>
</div>
</section>
<section id="havoc-summaries-havoc-all-and-havoc-ecf">
<span id="havoc-summary"></span><h4><a class="toc-backref" href="#id25" role="doc-backlink">Havoc summaries: <code class="docutils literal notranslate"><span class="pre">HAVOC_ALL</span></code> and <code class="docutils literal notranslate"><span class="pre">HAVOC_ECF</span></code></a><a class="headerlink" href="#havoc-summaries-havoc-all-and-havoc-ecf" title="Link to this heading"></a></h4>
<p>The most conservative summary type is <code class="docutils literal notranslate"><span class="pre">HAVOC_ALL</span></code>.  This summary makes no
assumptions at all about the called function: it is allowed to have arbitrary
side effects on the state of any contract (including the calling contract), and
may return any value.  It can also change any contract’s ETH balance in an
arbitrary way.  In effect, calling a method that is summarized by <code class="docutils literal notranslate"><span class="pre">HAVOC_ALL</span></code>
obliterates all knowledge that the Prover has about the state of the contract
before the call.</p>
<p>The <code class="docutils literal notranslate"><span class="pre">HAVOC_ALL</span></code> approximation is <a class="reference internal" href="../user-guide/glossary.html#term-sound"><span class="xref std std-term">sound</span></a>, but it can be overly
restrictive in practice.  In reality, a contract’s state cannot be changed in
arbitrary ways, but only according to the contract’s methods.  However, the
Prover does not currently have support for more fine-grained reasoning about
the side effects of unknown methods.</p>
<p>A useful middle ground is the <code class="docutils literal notranslate"><span class="pre">HAVOC_ECF</span></code> summary type.  A <code class="docutils literal notranslate"><span class="pre">HAVOC_ECF</span></code>
summarization for a method encodes the assumption that the called method is not
reentrant.  This summarization approximates a method call by assuming it can
have arbitrary effects on contracts other than the contract being verified, but
that it can neither change the current contract’s state nor decrease its ETH
balance (aside from value transferred by the method call itself).</p>
<p>The Prover makes no assumptions about the return value of a havoc summary.  For
methods that return multiple values, the approximations are allowed to return
the incorrect number of results.  In most cases, this will cause the calling
method to revert.  If you want to ignore this particular revert condition, you
can pass the <a class="reference internal" href="../prover/cli/options.html#optimisticreturnsize"><span class="std std-ref">optimisticReturnsize</span></a> option.</p>
</section>
<section id="dispatcher-summaries">
<span id="dispatcher"></span><h4><a class="toc-backref" href="#id26" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">DISPATCHER</span></code> summaries</a><a class="headerlink" href="#dispatcher-summaries" title="Link to this heading"></a></h4>
<p>The <code class="docutils literal notranslate"><span class="pre">DISPATCHER</span></code> summary type provides a useful approximation for methods of
interfaces that are implemented by multiple contracts.  For example, the
methods defined by the ERC20 specification are often summarized using the
<code class="docutils literal notranslate"><span class="pre">DISPATCHER</span></code> summary type.</p>
<p>If a function with a <code class="docutils literal notranslate"><span class="pre">DISPATCHER</span></code> summary is called, the Prover will assume
that the receiver of the call is one of the known contract implementations
containing the given signature; the call will then behave the same way that a
normal method call on the receiver would.  The Prover will consider examples
with every possible implementing contract, but multiple <code class="docutils literal notranslate"><span class="pre">DISPATCHER</span></code> method
calls on the same receiver address in the same example will use the same
receiver contract.</p>
<p>The set of contract implementations that the Prover chooses from contains
the set of contracts passed as <a class="reference internal" href="../prover/cli/options.html"><span class="doc std std-doc">arguments to the CLI</span></a>.
In addition, the Prover may consider an unknown target contract whose methods
are all interpreted using the <a class="reference internal" href="#auto-summary"><span class="std std-ref">AUTO summary</span></a>.  The presence
of the unknown contract is determined by the optional boolean argument to the
<code class="docutils literal notranslate"><span class="pre">DISPATCHER</span></code> summary:</p>
<ul class="simple">
<li><p>With <code class="docutils literal notranslate"><span class="pre">DISPATCHER(false)</span></code> or just <code class="docutils literal notranslate"><span class="pre">DISPATCHER</span></code>, the unknown contract is
considered as a possibility</p></li>
<li><p>With <code class="docutils literal notranslate"><span class="pre">DISPATCHER(true)</span></code>, only the known contract instances are considered</p></li>
</ul>
<p>There is an alternative syntax for determining the presence or absence of the
unknown contract:</p>
<ul class="simple">
<li><p><code class="docutils literal notranslate"><span class="pre">DISPATCHER(optimistic=&lt;true|false&gt;)</span></code> with <code class="docutils literal notranslate"><span class="pre">true</span></code> and ‘false` having the same
meaning as in the other syntax.</p></li>
</ul>
<p>In some cases there’s a proxy contract that only has a fallback function and
that fallback then delegates function calls it receives to some other contract.
For this case it could be useful for <code class="docutils literal notranslate"><span class="pre">DISPATCHER</span></code> summaries to also inline the
<code class="docutils literal notranslate"><span class="pre">fallback</span></code> function of known contracts. To enable this use the following syntax:</p>
<ul class="simple">
<li><p><code class="docutils literal notranslate"><span class="pre">DISPATCHER(optimistic=&lt;true|false&gt;,</span> <span class="pre">use_fallback&lt;true|false&gt;)</span></code></p></li>
</ul>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>The most commonly used dispatcher mode is <code class="docutils literal notranslate"><span class="pre">DISPATCHER(true)</span></code>, because in almost
all cases <code class="docutils literal notranslate"><span class="pre">DISPATCHER(false)</span></code> and <code class="docutils literal notranslate"><span class="pre">AUTO</span></code> report the same set of violations. Since
Certora CLI version 7.7.0 when using <code class="docutils literal notranslate"><span class="pre">_.someFunc()</span> <span class="pre">=&gt;</span> <span class="pre">DISPATCHER(true)</span></code> the Prover
first tests that a method <code class="docutils literal notranslate"><span class="pre">someFunc()</span></code> exists in the scene, and if not will fail.
Before this version, this may cause vacuous results.</p>
</div>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p><code class="docutils literal notranslate"><span class="pre">DISPATCHER</span></code> summaries cannot be used to summarize library calls.</p>
</div>
</section>
<section id="auto-summaries">
<span id="auto-summary"></span><h4><a class="toc-backref" href="#id27" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">AUTO</span></code> summaries</a><a class="headerlink" href="#auto-summaries" title="Link to this heading"></a></h4>
<p>The behavior of the <code class="docutils literal notranslate"><span class="pre">AUTO</span></code> summary depends on the type of call<a class="footnote-reference brackets" href="#opcodes" id="id6" role="doc-noteref"><span class="fn-bracket">[</span>2<span class="fn-bracket">]</span></a>:</p>
<ul class="simple">
<li><p>Calls to non-library <code class="docutils literal notranslate"><span class="pre">view</span></code> and <code class="docutils literal notranslate"><span class="pre">pure</span></code> methods use the <code class="docutils literal notranslate"><span class="pre">NONDET</span></code> approximation:
they keep all state unchanged.</p></li>
<li><p>Calls to library methods and <code class="docutils literal notranslate"><span class="pre">delegatecall</span></code>s are assumed to change
the caller’s storage in an arbitrary way, but are assumed to leave ETH
balances and the storage of other contracts unchanged.</p></li>
<li><p>All other calls and constructors use the <code class="docutils literal notranslate"><span class="pre">HAVOC_ECF</span></code> approximation: they are
assumed to change the state of external contracts arbitrarily but to leave
the caller’s state unchanged.
<code class="docutils literal notranslate"><span class="pre">AUTO</span></code> summary behavior for the <code class="docutils literal notranslate"><span class="pre">CALL</span></code> opcode
with 0 length <code class="docutils literal notranslate"><span class="pre">calldata</span></code> can be changed with <a class="reference internal" href="../prover/cli/options.html#optimisticfallback"><span class="std std-ref">optimistic_fallback</span></a>.</p></li>
</ul>
</section>
<section id="assert-false-summaries">
<span id="assert-false-summary"></span><h4><a class="toc-backref" href="#id28" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">ASSERT_FALSE</span></code> summaries</a><a class="headerlink" href="#assert-false-summaries" title="Link to this heading"></a></h4>
<p>This summary is a short syntax for a summary that contains an <code class="docutils literal notranslate"><span class="pre">assert</span> <span class="pre">false;</span></code> and checks that the summarized method is not reached.
This can be useful for instance, in the presence of unresolved calls in combination with the <code class="docutils literal notranslate"><span class="pre">unresolved</span> <span class="pre">external</span></code> syntax to ensure that every unresolved call is actually dispatched correctly (i.e. use <code class="docutils literal notranslate"><span class="pre">unresolved</span> <span class="pre">external</span> <span class="pre">in</span> <span class="pre">_._</span> <span class="pre">=&gt;</span> <span class="pre">DISPATCH</span> <span class="pre">[...]</span> <span class="pre">default</span> <span class="pre">ASSERT_FALSE</span></code>). It also enables more optimizations in the Prover and may lead to shorter running times.</p>
</section>
<section id="expression-summaries">
<span id="expression-summary"></span><h4><a class="toc-backref" href="#id29" role="doc-backlink">Expression summaries</a><a class="headerlink" href="#expression-summaries" title="Link to this heading"></a></h4>
<p>Contract methods can also be summarized using CVL expressions, typically <a class="reference internal" href="functions.html"><span class="doc">Functions</span></a> or
<a class="reference internal" href="ghosts.html#ghost-axioms"><span class="std std-ref">Ghost axioms</span></a> as approximations.  Contract calls to the summarized method
are replaced by evaluation of the CVL expression.</p>
<p>To use a CVL function or ghost as a summary, use a call to the function in
place of the summary type.</p>
<p>If a wildcard entry has a ghost or function summary, the user must explicitly
provide an <code class="docutils literal notranslate"><span class="pre">expect</span></code> clause to the summary.  The <code class="docutils literal notranslate"><span class="pre">expect</span></code> clause tells the
Prover how to interpret the value returned by the summary.  For example:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell13"><span></span><span class="kr">methods</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kd">function</span><span class="w"> </span><span class="nc">_</span><span class="p">.</span><span class="nf">foo</span><span class="p">()</span><span class="w"> </span><span class="kr">external</span><span class="w"> </span><span class="kp">=&gt;</span><span class="w"> </span><span class="nf">fooImpl</span><span class="p">()</span><span class="w"> </span><span class="kr">expect</span><span class="w"> </span><span class="kt">uint256</span><span class="w"> </span><span class="kr">ALL</span><span class="p">;</span>
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
<p>This entry will replace any call to any external function <code class="docutils literal notranslate"><span class="pre">foo()</span></code> with a call to
the CVL function <code class="docutils literal notranslate"><span class="pre">fooImpl()</span></code> and will interpret the output of <code class="docutils literal notranslate"><span class="pre">fooImpl</span></code> as a
<code class="docutils literal notranslate"><span class="pre">uint256</span></code>.</p>
<p>If a function does not return any value, the summary should be declared with
<code class="docutils literal notranslate"><span class="pre">expect</span> <span class="pre">void</span></code>.</p>
<div class="admonition warning">
<p class="admonition-title">Warning</p>
<p>You must check that your <code class="docutils literal notranslate"><span class="pre">expect</span></code> clauses are correct.</p>
<p>The Prover cannot always check that the return type declared in the <code class="docutils literal notranslate"><span class="pre">expect</span></code>
clause matches the return type that the contract expects.  Continuing the above
example, suppose the contract being verified declared a method <code class="docutils literal notranslate"><span class="pre">foo()</span></code> that
returns a type other than <code class="docutils literal notranslate"><span class="pre">uint256</span></code>:</p>
<div class="highlight-solidity notranslate"><div class="highlight"><pre id="codecell14"><span></span><span class="kt">function</span><span class="w"> </span><span class="nv">foo</span><span class="p">()</span><span class="w"> </span><span class="kt">external</span><span class="w"> </span><span class="kt">returns</span><span class="p">(</span><span class="kt">address</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="p">...</span>
<span class="p">}</span>

<span class="kt">function</span><span class="w"> </span><span class="nv">bar</span><span class="p">()</span><span class="w"> </span><span class="kt">internal</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kt">address</span><span class="w"> </span><span class="nv">x</span><span class="w"> </span><span class="o">=</span><span class="w"> </span>y<span class="p">.</span>foo<span class="p">();</span>
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
<p>In this case, the Prover would encode the value returned by <code class="docutils literal notranslate"><span class="pre">fooImpl()</span></code> as a
<code class="docutils literal notranslate"><span class="pre">uint256</span></code>, and the <code class="docutils literal notranslate"><span class="pre">bar</span></code> method would then attempt to decode this value as an
<code class="docutils literal notranslate"><span class="pre">address</span></code>.  This will cause undefined behavior, and in some cases the Prover
will not be able to detect the error.</p>
</div>
<p>The function call can only refer directly to the variables defined as arguments
in the summary declarations; expressions that combine those variables are not
supported.</p>
<p>The function call may also use the special variable <code class="docutils literal notranslate"><span class="pre">calledContract</span></code>, which
gives the address of the contract on which the summarized method was called.
More precisely, it equates to <code class="docutils literal notranslate"><span class="pre">address(this)</span></code> in the context of the original
call that is being summarized.
This is useful for identifying the called contract in <a class="reference internal" href="cvl2/changes.html#cvl2-wildcards"><span class="std std-ref">wildcard summaries</span></a>. For internal functions, the <code class="docutils literal notranslate"><span class="pre">calledContract</span></code> is also
the calling contract, since they are the same.
For library functions and delegate calls the <code class="docutils literal notranslate"><span class="pre">calledContract</span></code> is the contract
calling the function.
Similarly, there is another special variable <code class="docutils literal notranslate"><span class="pre">executingContract</span></code>, which
gives the address of the contract making the call to the function that is
summarized. For internal, delegate and library calls, <code class="docutils literal notranslate"><span class="pre">executingContract</span></code> is
the same as <code class="docutils literal notranslate"><span class="pre">calledContract</span></code>. They differ only in non-delegate external calls,
where <code class="docutils literal notranslate"><span class="pre">calledContract</span></code> will be the receiver of the call and <code class="docutils literal notranslate"><span class="pre">executingContract</span></code>
will be the caller.
The <code class="docutils literal notranslate"><span class="pre">calledContract</span></code> and <code class="docutils literal notranslate"><span class="pre">executingContract</span></code> keywords may only be used inside
the <code class="docutils literal notranslate"><span class="pre">methods</span></code> block, and <code class="docutils literal notranslate"><span class="pre">executingContract</span></code> also
in <a class="reference internal" href="hooks.html#executingcontract"><span class="std std-ref">hook bodies</span></a>.</p>
<p>For example, a wildcard summary for a <code class="docutils literal notranslate"><span class="pre">transferFrom</span></code> method may apply to
multiple ERC20 contracts; the summary can update the correct ghost variables as
follows:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell15"><span></span><span class="kr">methods</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kd">function</span><span class="w"> </span><span class="nc">_</span><span class="p">.</span><span class="nf">transferFrom</span><span class="p">(</span><span class="kt">address</span><span class="w"> </span>from<span class="p">,</span><span class="w"> </span><span class="kt">address</span><span class="w"> </span>to<span class="p">,</span><span class="w"> </span><span class="kt">uint256</span><span class="w"> </span>amount<span class="p">)</span><span class="w"> </span><span class="kr">external</span>
<span class="w">        </span><span class="kp">=&gt;</span><span class="w"> </span><span class="nf">cvlTransferFrom</span><span class="p">(</span>calledContract<span class="p">,</span><span class="w"> </span>from<span class="p">,</span><span class="w"> </span>to<span class="p">,</span><span class="w"> </span>amount<span class="p">);</span>
<span class="p">}</span>

<span class="kd">ghost</span><span class="w"> </span><span class="kt">mapping</span><span class="p">(</span><span class="kt">address</span><span class="w"> </span><span class="o">=&gt;</span><span class="w"> </span><span class="kt">mapping</span><span class="p">(</span><span class="kt">address</span><span class="w"> </span><span class="o">=&gt;</span><span class="w"> </span><span class="kt">mathint</span><span class="p">))</span><span class="w"> </span>tokenBalances<span class="p">;</span>

<span class="kt">function</span><span class="w"> </span><span class="nf">cvlTransferFrom</span><span class="p">(</span><span class="kt">address</span><span class="w"> </span>token<span class="p">,</span><span class="w"> </span><span class="kt">address</span><span class="w"> </span>from<span class="p">,</span><span class="w"> </span><span class="kt">address</span><span class="w"> </span>to<span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>amount<span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kr">if</span><span class="w"> </span><span class="p">(...)</span><span class="w"> </span><span class="p">{</span>
<span class="w">        </span>tokenBalances<span class="p">[</span>token<span class="p">][</span>from<span class="p">]</span><span class="w"> </span><span class="o">-=</span><span class="w"> </span>amount<span class="p">;</span>
<span class="w">        </span>tokenBalances<span class="p">[</span>token<span class="p">][</span>to<span class="p">]</span><span class="w">   </span><span class="o">+=</span><span class="w"> </span>amount<span class="p">;</span>
<span class="w">    </span><span class="p">}</span>
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
<p>The call can also refer to a variable of type <code class="docutils literal notranslate"><span class="pre">env</span></code> introduced by a
<a class="reference internal" href="#with-env"><span class="std std-ref">with(env) clause</span></a>.  Here <code class="docutils literal notranslate"><span class="pre">e</span></code> may be replaced with any valid identifier.</p>
<p>The variable defined by the <code class="docutils literal notranslate"><span class="pre">with</span></code> clause contains an <a class="reference internal" href="types.html#env"><span class="std std-ref">env type</span></a>
giving the context for the summarized function.  This context may be different
from the <code class="docutils literal notranslate"><span class="pre">env</span></code> passed to the original call from the spec.  In particular:</p>
<ul class="simple">
<li><p><code class="docutils literal notranslate"><span class="pre">e.msg.sender</span></code> and <code class="docutils literal notranslate"><span class="pre">e.msg.value</span></code> refer to the sender and value from the most recent call to a
non-library<a class="footnote-reference brackets" href="#library-with-env" id="id7" role="doc-noteref"><span class="fn-bracket">[</span>3<span class="fn-bracket">]</span></a> external function (as in Solidity)</p></li>
<li><p>The variables <code class="docutils literal notranslate"><span class="pre">e.tx.origin</span></code>, <code class="docutils literal notranslate"><span class="pre">e.block.number</span></code>, and <code class="docutils literal notranslate"><span class="pre">e.block.timestamp</span></code> will
be the same as the the environment for the outermost function call.</p></li>
</ul>
<p>Continuing the above example, one can use the <code class="docutils literal notranslate"><span class="pre">env</span></code> to summarize the <code class="docutils literal notranslate"><span class="pre">transfer</span></code>
method:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell16"><span></span><span class="kr">methods</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kd">function</span><span class="w"> </span><span class="nc">_</span><span class="p">.</span><span class="nf">transfer</span><span class="p">(</span><span class="kt">address</span><span class="w"> </span>to<span class="p">,</span><span class="w"> </span><span class="kt">uint256</span><span class="w"> </span>amount<span class="p">)</span><span class="w"> </span><span class="kr">external</span><span class="w"> </span>with<span class="p">(</span><span class="kt">env</span><span class="w"> </span>e<span class="p">)</span>
<span class="w">        </span><span class="kp">=&gt;</span><span class="w"> </span><span class="nf">cvlTransfer</span><span class="p">(</span>calledContract<span class="p">,</span><span class="w"> </span>e<span class="p">,</span><span class="w"> </span>to<span class="p">,</span><span class="w"> </span>amount<span class="p">)</span><span class="w"> </span><span class="kr">expect</span><span class="w"> </span>void<span class="p">;</span>
<span class="p">}</span>

<span class="kt">function</span><span class="w"> </span><span class="nf">cvlTransfer</span><span class="p">(</span><span class="kt">address</span><span class="w"> </span>token<span class="p">,</span><span class="w"> </span><span class="kt">env</span><span class="w"> </span>passedEnv<span class="p">,</span><span class="w"> </span><span class="kt">address</span><span class="w"> </span>to<span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>amount<span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="p">...</span>
<span class="p">}</span>

<span class="k">rule</span><span class="w"> </span><span class="nc">example</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kt">env</span><span class="w"> </span>e<span class="p">;</span>
<span class="w">    </span><span class="kt">address</span><span class="w"> </span>sender<span class="p">;</span>
<span class="w">    </span><span class="kr">require</span><span class="w"> </span>e<span class="p">.</span><span class="kc">msg.sender</span><span class="w"> </span><span class="o">==</span><span class="w"> </span>sender<span class="p">;</span>
<span class="w">    </span>c<span class="p">.</span>process<span class="p">(</span>e<span class="p">);</span>
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
<p>In this example, if the <code class="docutils literal notranslate"><span class="pre">process</span></code> method calls <code class="docutils literal notranslate"><span class="pre">t.transfer(...)</span></code>, then in the
<code class="docutils literal notranslate"><span class="pre">cvlTransfer</span></code> function, <code class="docutils literal notranslate"><span class="pre">token</span></code> will be <code class="docutils literal notranslate"><span class="pre">t</span></code>, <code class="docutils literal notranslate"><span class="pre">passedEnv.msg.sender</span></code> will be
<code class="docutils literal notranslate"><span class="pre">c</span></code>, and <code class="docutils literal notranslate"><span class="pre">passedEnv.tx.origin</span></code> will be <code class="docutils literal notranslate"><span class="pre">sender</span></code>.</p>
<p>There is a restriction on the functions that can be used as approximations.
Namely, the types of any arguments passed to or values returned from the summary
must be <a class="reference internal" href="types.html#type-conversions"><span class="std std-ref">convertible</span></a> between CVL and Solidity types.
Arguments that are not accessed in the summary may have any type.</p>
<p>You can still summarize functions that take unconvertible types as arguments,
but you cannot access those arguments in your summary.</p>
<p>In case of recursive calls due to the summarization, the recursion limit can be set with
<code class="docutils literal notranslate"><span class="pre">--summary_recursion_limit</span> <span class="pre">N'</span></code> where <code class="docutils literal notranslate"><span class="pre">N</span></code> is the number of recursive calls allowed (default 0).
If <code class="docutils literal notranslate"><span class="pre">--optimistic_summary_recursion</span></code> is set, the recursion limit is assumed, i.e. one will never get a counterexample going above the recursion limit.
Otherwise, if it is possible to go above the recursion limit, an assert will fire, producing a counterexample to the rule.</p>
<hr class="footnotes docutils">
<aside class="footnote-list brackets">
<aside class="footnote brackets" id="envfree-nonpayable" role="doc-footnote">
<span class="label"><span class="fn-bracket">[</span><a role="doc-backlink" href="#id3">1</a><span class="fn-bracket">]</span></span>
<p>The effect of payable functions on the contract’s
balance depends on the message value, so payable functions also require an
<code class="docutils literal notranslate"><span class="pre">env</span></code>.</p>
</aside>
<aside class="footnote brackets" id="opcodes" role="doc-footnote">
<span class="label"><span class="fn-bracket">[</span><a role="doc-backlink" href="#id6">2</a><span class="fn-bracket">]</span></span>
<p>The behavior of <code class="docutils literal notranslate"><span class="pre">AUTO</span></code> summaries is actually determined by the EVM
opcode used to make the call: calls made using the <code class="docutils literal notranslate"><span class="pre">STATICCALL</span></code> opcode use
the <code class="docutils literal notranslate"><span class="pre">NONDET</span></code> summary, calls using <code class="docutils literal notranslate"><span class="pre">CALL</span></code> or <code class="docutils literal notranslate"><span class="pre">CREATE</span></code> opcode use the <code class="docutils literal notranslate"><span class="pre">HAVOC_ECF</span></code>
summary, and calls using the <code class="docutils literal notranslate"><span class="pre">DELEGATECALL</span></code> and <code class="docutils literal notranslate"><span class="pre">CALLCODE</span></code> opcodes havoc the
current contract only.
Modern Solidity versions output opcodes that are consistent with the above
description, but older versions behave differently.  See
<a class="reference external" href="https://docs.soliditylang.org/en/v0.8.12/contracts.html#state-mutability">State Mutability</a>
in the Solidity manual for details.</p>
</aside>
<aside class="footnote brackets" id="library-with-env" role="doc-footnote">
<span class="label"><span class="fn-bracket">[</span><a role="doc-backlink" href="#id7">3</a><span class="fn-bracket">]</span></span>
<p>As <a class="reference external" href="https://docs.soliditylang.org/en/v0.8.6/introduction-to-smart-contracts.html?#delegatecall-callcode-and-libraries">in solidity</a>, <code class="docutils literal notranslate"><span class="pre">msg.sender</span></code> and <code class="docutils literal notranslate"><span class="pre">msg.value</span></code> do not
change for <code class="docutils literal notranslate"><span class="pre">delegatecall</span></code>s or library calls.</p>
</aside>
</aside>
</section>
</section>
</section>
</section>


           </div>
          </div>
          <footer><div class="rst-footer-buttons" role="navigation" aria-label="Footer">
        <a href="using.html" class="btn btn-neutral float-left" title="Using Statements" accesskey="p" rel="prev"><span class="fa fa-arrow-circle-left" aria-hidden="true"></span> Previous</a>
        <a href="rules.html" class="btn btn-neutral float-right" title="Rules" accesskey="n" rel="next">Next <span class="fa fa-arrow-circle-right" aria-hidden="true"></span></a>
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