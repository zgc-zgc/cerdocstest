<!DOCTYPE html><html class="writer-html5" lang="en" data-content_root="../../"><head>
  <meta charset="utf-8"><meta name="viewport" content="width=device-width, initial-scale=1">

  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Ghosts — Certora Prover Documentation 0.0 documentation</title>
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
    <link rel="next" title="Definitions" href="defs.html">
    <link rel="prev" title="Uninterpreted Sorts" href="sorts.html"> 
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
<li class="toctree-l2 current" aria-expanded="true"><a class="reference internal current" href="#" aria-expanded="true"><button class="toctree-expand" title="Open/close menu"></button>Ghosts</a><ul>
<li class="toctree-l3"><a class="reference internal" href="#syntax">Syntax</a></li>
<li class="toctree-l3"><a class="reference internal" href="#declaring-ghost-variables">Declaring ghost variables</a></li>
<li class="toctree-l3"><a class="reference internal" href="#ghost-functions">Ghost Functions</a></li>
<li class="toctree-l3"><a class="reference internal" href="#restrictions-on-ghost-definitions">Restrictions on ghost definitions</a></li>
<li class="toctree-l3"><a class="reference internal" href="#using-ghost-variables">Using ghost variables</a></li>
<li class="toctree-l3"><a class="reference internal" href="#ghost-axioms"><button class="toctree-expand" title="Open/close menu"></button>Ghost axioms</a><ul>
<li class="toctree-l4"><a class="reference internal" href="#global-axioms">Global axioms</a></li>
<li class="toctree-l4"><a class="reference internal" href="#initial-state-axioms">Initial state axioms</a></li>
</ul>
</li>
<li class="toctree-l3"><a class="reference internal" href="#restrictions-on-ghost-axioms">Restrictions on ghost axioms</a></li>
<li class="toctree-l3"><a class="reference internal" href="#ghosts-vs-persistent-ghosts"><button class="toctree-expand" title="Open/close menu"></button>Ghosts vs. persistent ghosts</a><ul>
<li class="toctree-l4"><a class="reference internal" href="#persistent-ghosts-that-survive-havocs">Persistent ghosts that survive havocs</a></li>
<li class="toctree-l4"><a class="reference internal" href="#persistent-ghosts-that-survive-reverts">Persistent ghosts that survive reverts</a></li>
</ul>
</li>
</ul>
</li>
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
      <li class="breadcrumb-item active">Ghosts</li>
      <li class="wy-breadcrumbs-aside">
            <a href="../../_sources/docs/cvl/ghosts.md.txt" rel="nofollow"> View page source</a>
      </li>
  </ul>
  <hr>
</div>
          <div role="main" class="document" itemscope="itemscope" itemtype="http://schema.org/Article">
           <div itemprop="articleBody">
             
  <section id="ghosts">
<span id="ghosts-doc"></span><h1><a class="toc-backref" href="#id5" role="doc-backlink">Ghosts</a><a class="headerlink" href="#ghosts" title="Link to this heading"></a></h1>
<p>Ghosts are a way of defining additional variables for use during verification.
These variables are often used to</p>
<ul class="simple">
<li><p>communicate information between <a class="reference internal" href="rules.html#rules-main"><span class="std std-ref">Rules</span></a> and <a class="reference internal" href="hooks.html#hooks"><span class="std std-ref">Hooks</span></a>.</p></li>
<li><p>define deterministic <a class="reference internal" href="methods.html#expression-summary"><span class="std std-ref">expression summaries</span></a>.</p></li>
</ul>
<p>Ghosts can be seen as an ‘extension’ to the state of the contracts under verification.
This means that in case a call reverts, the ghost values will revert to their pre-state.
Additionally, if an unresolved call is handled by a havoc, the ghost values will havoc as well.
Ghosts are regarded as part of the state of the contracts,
and when calls are invoked with <code class="docutils literal notranslate"><span class="pre">at</span> <span class="pre">storageVar</span></code> statements (see <a class="reference internal" href="types.html#storage-type"><span class="std std-ref">The storage type</span></a>),
they are restored to their state as saved in <code class="docutils literal notranslate"><span class="pre">storageVar</span></code>.
An exception to this rule are ghosts marked <em>persistent</em>.
Persistent ghosts are <strong>never</strong> havoced, and <strong>never</strong> reverted.
See <a class="reference internal" href="#persistent-ghosts"><span class="std std-ref">Ghosts vs. persistent ghosts</span></a> below for more details and examples.</p>
<nav class="contents" id="contents">
<p class="topic-title">Contents</p>
<ul class="simple">
<li><p><a class="reference internal" href="#ghosts" id="id5">Ghosts</a></p>
<ul>
<li><p><a class="reference internal" href="#syntax" id="id6">Syntax</a></p></li>
<li><p><a class="reference internal" href="#declaring-ghost-variables" id="id7">Declaring ghost variables</a></p></li>
<li><p><a class="reference internal" href="#ghost-functions" id="id8">Ghost Functions</a></p></li>
<li><p><a class="reference internal" href="#restrictions-on-ghost-definitions" id="id9">Restrictions on ghost definitions</a></p></li>
<li><p><a class="reference internal" href="#using-ghost-variables" id="id10">Using ghost variables</a></p></li>
<li><p><a class="reference internal" href="#ghost-axioms" id="id11">Ghost axioms</a></p>
<ul>
<li><p><a class="reference internal" href="#global-axioms" id="id12">Global axioms</a></p></li>
<li><p><a class="reference internal" href="#initial-state-axioms" id="id13">Initial state axioms</a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#restrictions-on-ghost-axioms" id="id14">Restrictions on ghost axioms</a></p></li>
<li><p><a class="reference internal" href="#ghosts-vs-persistent-ghosts" id="id15">Ghosts vs. persistent ghosts</a></p>
<ul>
<li><p><a class="reference internal" href="#persistent-ghosts-that-survive-havocs" id="id16">Persistent ghosts that survive havocs</a></p></li>
<li><p><a class="reference internal" href="#persistent-ghosts-that-survive-reverts" id="id17">Persistent ghosts that survive reverts</a></p></li>
</ul>
</li>
</ul>
</li>
</ul>
</nav>
<section id="syntax">
<h2><a class="toc-backref" href="#id6" role="doc-backlink">Syntax</a><a class="headerlink" href="#syntax" title="Link to this heading"></a></h2>
<p>The syntax for ghost declarations is given by the following <a class="reference internal" href="overview.html#ebnf-syntax"><span class="std std-ref">EBNF grammar</span></a>:</p>
<div class="highlight-default notranslate"><div class="highlight"><pre id="codecell0"><span></span><span class="n">ghost</span> <span class="p">:</span><span class="o">:=</span> <span class="s2">"ghost"</span> <span class="nb">type</span> <span class="nb">id</span>                             <span class="p">(</span><span class="s2">";"</span> <span class="o">|</span> <span class="s2">"{"</span> <span class="n">axioms</span> <span class="s2">"}"</span><span class="p">)</span>
        <span class="o">|</span> <span class="s2">"ghost"</span> <span class="nb">id</span> <span class="s2">"("</span> <span class="n">cvl_types</span> <span class="s2">")"</span> <span class="s2">"returns"</span> <span class="nb">type</span> <span class="p">(</span><span class="s2">";"</span> <span class="o">|</span> <span class="s2">"{"</span> <span class="n">axioms</span> <span class="s2">"}"</span><span class="p">)</span>

<span class="n">persistent_ghost</span> <span class="p">:</span><span class="o">:=</span>  <span class="s2">"persistent"</span> <span class="s2">"ghost"</span> <span class="nb">type</span> <span class="nb">id</span>                             <span class="p">(</span><span class="s2">";"</span> <span class="o">|</span> <span class="s2">"{"</span> <span class="n">axioms</span> <span class="s2">"}"</span><span class="p">)</span>
                    <span class="o">|</span> <span class="s2">"persistent"</span> <span class="s2">"ghost"</span> <span class="nb">id</span> <span class="s2">"("</span> <span class="n">cvl_types</span> <span class="s2">")"</span> <span class="s2">"returns"</span> <span class="nb">type</span> <span class="p">(</span><span class="s2">";"</span> <span class="o">|</span> <span class="s2">"{"</span> <span class="n">axioms</span> <span class="s2">"}"</span><span class="p">)</span>

<span class="nb">type</span> <span class="p">:</span><span class="o">:=</span> <span class="n">basic_type</span>
       <span class="o">|</span> <span class="s2">"mapping"</span> <span class="s2">"("</span> <span class="n">cvl_type</span> <span class="s2">"=&gt;"</span> <span class="nb">type</span> <span class="s2">")"</span>

<span class="n">axiom</span> <span class="p">:</span><span class="o">:=</span> <span class="p">[</span> <span class="s2">"init_state"</span> <span class="p">]</span> <span class="s2">"axiom"</span> <span class="n">expression</span> <span class="s2">";"</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell0">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>See <a class="reference internal" href="types.html"><span class="doc">Types</span></a> for the <code class="docutils literal notranslate"><span class="pre">type</span></code> and <code class="docutils literal notranslate"><span class="pre">cvl_type</span></code> productions, and <a class="reference internal" href="expr.html"><span class="doc">Expressions</span></a> for
the <code class="docutils literal notranslate"><span class="pre">expression</span></code> syntax.</p>
</section>
<section id="declaring-ghost-variables">
<span id="ghost-variables"></span><h2><a class="toc-backref" href="#id7" role="doc-backlink">Declaring ghost variables</a><a class="headerlink" href="#declaring-ghost-variables" title="Link to this heading"></a></h2>
<p>Ghost variables must be declared at the top level of a specification file.
A ghost variable declaration includes the keyword <code class="docutils literal notranslate"><span class="pre">ghost</span></code> followed by the type and name
of the ghost variable.</p>
<p>The type of a ghost variable may be either a <a class="reference internal" href="types.html"><span class="std std-doc">CVL type</span></a> or a <code class="docutils literal notranslate"><span class="pre">mapping</span></code> type.
Mapping types are similar to solidity mapping types.  They must have CVL types
as keys, but may contain either CVL types or mapping types as values.</p>
<p>For example, the following are valid ghost declarations:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell1"><span></span><span class="kd">ghost</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>x<span class="p">;</span>
<span class="kd">ghost</span><span class="w"> </span><span class="kt">mapping</span><span class="p">(</span><span class="kt">address</span><span class="w"> </span><span class="o">=&gt;</span><span class="w"> </span><span class="kt">mathint</span><span class="p">)</span><span class="w"> </span>balances<span class="p">;</span>
<span class="kd">ghost</span><span class="w"> </span><span class="kt">mapping</span><span class="p">(</span><span class="kt">uint</span><span class="w"> </span><span class="o">=&gt;</span><span class="w"> </span><span class="kt">mapping</span><span class="p">(</span><span class="kt">uint</span><span class="w"> </span><span class="o">=&gt;</span><span class="w"> </span><span class="kt">mathint</span><span class="p">))</span><span class="w"> </span>delegations<span class="p">;</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell1">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>while the following are invalid:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell2"><span></span>ghost<span class="w"> </span><span class="p">(</span><span class="kt">uint</span><span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="p">)</span><span class="w"> </span>x<span class="p">;</span><span class="w">                              </span><span class="c1">// tuples are not CVL types</span>
<span class="kd">ghost</span><span class="w"> </span><span class="kt">mapping</span><span class="p">(</span><span class="kt">mapping</span><span class="p">(</span><span class="kt">uint</span><span class="w"> </span><span class="o">=&gt;</span><span class="w"> </span><span class="kt">uint</span><span class="p">)</span><span class="w"> </span><span class="o">=&gt;</span><span class="w"> </span><span class="kt">address</span><span class="p">)</span><span class="w"> </span>y<span class="p">;</span><span class="w"> </span><span class="c1">// mappings cannot be keys</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell2">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<ul class="simple">
<li><p><a class="reference external" href="https://github.com/Certora/Examples/blob/14668d39a6ddc67af349bc5b82f73db73349ef18/CVLByExample/ERC20/certora/specs/ERC20.spec#L113">simple <code class="docutils literal notranslate"><span class="pre">ghost</span></code> variable example</a></p></li>
<li><p>This example uses an <a class="reference external" href="https://github.com/Certora/Examples/blob/14668d39a6ddc67af349bc5b82f73db73349ef18/CVLByExample/ERC20/certora/specs/ERC20.spec#L114"><code class="docutils literal notranslate"><span class="pre">init_state</span></code> axiom</a></p></li>
<li><p><a class="reference external" href="https://github.com/Certora/Examples/blob/14668d39a6ddc67af349bc5b82f73db73349ef18/CVLByExample/structs/BankAccounts/certora/specs/Bank.spec#L117"><code class="docutils literal notranslate"><span class="pre">ghost</span> <span class="pre">mapping</span></code> example</a></p></li>
</ul>
</section>
<section id="ghost-functions">
<span id="id1"></span><h2><a class="toc-backref" href="#id8" role="doc-backlink">Ghost Functions</a><a class="headerlink" href="#ghost-functions" title="Link to this heading"></a></h2>
<p>CVL also has support for “ghost functions”.  These serve a different purpose from ghost variables, although they can be
used in similar ways.</p>
<p>Ghost functions must be declared at the top level of a specification file.
A ghost function declaration includes the keyword <code class="docutils literal notranslate"><span class="pre">ghost</span></code> followed by the name and signature of the ghost function.
Ghost functions should be used either:</p>
<ul class="simple">
<li><p>when there are no updates to the ghost as the deterministic behavior and axioms are the only properties of the ghost</p></li>
<li><p>when updating the ghost - more than one entry is updated and then the havoc assuming statement is used.</p>
<ul>
<li><p><a class="reference external" href="https://github.com/Certora/Examples/blob/14668d39a6ddc67af349bc5b82f73db73349ef18/CVLByExample/QuantifierExamples/DoublyLinkedList/certora/spec/dll-linkedcorrectly.spec#L24"><code class="docutils literal notranslate"><span class="pre">ghost</span></code> function example</a></p></li>
</ul>
</li>
</ul>
</section>
<section id="restrictions-on-ghost-definitions">
<h2><a class="toc-backref" href="#id9" role="doc-backlink">Restrictions on ghost definitions</a><a class="headerlink" href="#restrictions-on-ghost-definitions" title="Link to this heading"></a></h2>
<ul class="simple">
<li><p>A user-defined type, such as struct, array or interface is not allowed as the key or the output type of a <code class="docutils literal notranslate"><span class="pre">ghost</span> <span class="pre">mapping</span></code>.</p></li>
</ul>
</section>
<section id="using-ghost-variables">
<h2><a class="toc-backref" href="#id10" role="doc-backlink">Using ghost variables</a><a class="headerlink" href="#using-ghost-variables" title="Link to this heading"></a></h2>
<p>While verifying a rule or invariant, the Prover considers every possible
initial value of a ghost variable (subject to its <a class="reference internal" href="#ghost-axioms"><span class="std std-ref">Ghost axioms</span></a>,
see below).</p>
<p>Within CVL, you can read or write ghosts using the normal variable syntax.  For
example:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell3"><span></span><span class="kd">ghost</span><span class="w"> </span><span class="kt">mapping</span><span class="p">(</span><span class="kt">address</span><span class="w"> </span><span class="o">=&gt;</span><span class="w"> </span><span class="kt">mathint</span><span class="p">)</span><span class="w"> </span>balances<span class="p">;</span>

<span class="kt">function</span><span class="w"> </span><span class="nf">example</span><span class="p">(</span><span class="kt">address</span><span class="w"> </span>user<span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span>balances<span class="p">[</span>user<span class="p">]</span><span class="w"> </span><span class="o">=</span><span class="w"> </span>x<span class="p">;</span>
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
<p>The most common reason to use a ghost is to communicate information from a hook
back to the rule that triggered it.  For example, the following CVL checks
that a call to the contract method <code class="docutils literal notranslate"><span class="pre">do_update(user)</span></code> changes the contract
variable <code class="docutils literal notranslate"><span class="pre">userInfo[user]</span></code> and does not change <code class="docutils literal notranslate"><span class="pre">userInfo[other]</span></code> for any other
user:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell4"><span></span><span class="kd">ghost</span><span class="w"> </span><span class="kt">mapping</span><span class="p">(</span><span class="kt">address</span><span class="w"> </span><span class="o">=&gt;</span><span class="w"> </span><span class="kt">bool</span><span class="p">)</span><span class="w"> </span>updated<span class="p">;</span>

<span class="kd">hook</span><span class="w"> </span><span class="kp">Sstore</span><span class="w"> </span>userInfo<span class="p">[</span><span class="kp">KEY</span><span class="w"> </span><span class="kt">address</span><span class="w"> </span>u<span class="p">]</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>i<span class="w"> </span><span class="p">{</span>
<span class="w">    </span>updated<span class="p">[</span>u<span class="p">]</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="kr">true</span><span class="p">;</span>
<span class="p">}</span>

<span class="k">rule</span><span class="w"> </span><span class="nc">update_changes_user</span><span class="p">(</span><span class="kt">address</span><span class="w"> </span>user<span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span>updated<span class="p">[</span>user<span class="p">]</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="kr">false</span><span class="p">;</span>

<span class="w">    </span>do_update<span class="p">(</span>user<span class="p">);</span>

<span class="w">    </span><span class="kr">assert</span><span class="w"> </span>updated<span class="p">[</span>user<span class="p">]</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="kr">true</span><span class="p">,</span><span class="w"> </span><span class="s2">"do_update(user) should affect user"</span><span class="p">;</span>
<span class="p">}</span>

<span class="k">rule</span><span class="w"> </span><span class="nc">update_changes_no_other</span><span class="p">(</span><span class="kt">address</span><span class="w"> </span>user<span class="p">,</span><span class="w"> </span><span class="kt">address</span><span class="w"> </span>other<span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kr">require</span><span class="w"> </span>user<span class="w"> </span><span class="o">!=</span><span class="w"> </span>other<span class="p">;</span>
<span class="w">    </span><span class="kr">require</span><span class="w"> </span>updated<span class="p">[</span>other<span class="p">]</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="kr">false</span><span class="p">;</span>

<span class="w">    </span>do_update<span class="p">(</span>user<span class="p">);</span>

<span class="w">    </span><span class="kr">assert</span><span class="w"> </span>updated<span class="p">[</span>other<span class="p">]</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="kr">false</span><span class="p">;</span>
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
<p>Here the <code class="docutils literal notranslate"><span class="pre">updated</span></code> ghost is used to communicate information from the <code class="docutils literal notranslate"><span class="pre">userInfo</span></code>
hook back to the <code class="docutils literal notranslate"><span class="pre">updated_changes_user</span></code> and <code class="docutils literal notranslate"><span class="pre">updated_changes_no_other</span></code> rules.</p>
</section>
<section id="ghost-axioms">
<span id="id2"></span><h2><a class="toc-backref" href="#id11" role="doc-backlink">Ghost axioms</a><a class="headerlink" href="#ghost-axioms" title="Link to this heading"></a></h2>
<p>Ghost axioms are properties that the Prover assumes whenever it makes use of a ghost.</p>
<section id="global-axioms">
<span id="id3"></span><h3><a class="toc-backref" href="#id12" role="doc-backlink">Global axioms</a><a class="headerlink" href="#global-axioms" title="Link to this heading"></a></h3>
<p>Sometimes we might want to constrain the behavior of a ghost in some particular way.
In CVL this is achieved by writing axioms. Axioms are simply CVL expressions that the tool will then assume are true
about the ghost. For example:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell5"><span></span><span class="kd">ghost</span><span class="w"> </span><span class="nf">bar</span><span class="p">(</span><span class="kt">uint256</span><span class="p">)</span><span class="w"> </span><span class="kr">returns</span><span class="w"> </span><span class="kt">uint256</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kr">axiom</span><span class="w"> </span><span class="kr">forall</span><span class="w"> </span><span class="kt">uint256</span><span class="w"> </span>x<span class="p">.</span><span class="w"> </span>bar<span class="p">(</span>x<span class="p">)</span><span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="m m-Decimal">10</span><span class="p">;</span>
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
<p>In any rule that uses bar, no application of bar could ever evaluate to a number less than or equal to 10.</p>
<ul class="simple">
<li><p><a class="reference external" href="https://github.com/Certora/Examples/blob/14668d39a6ddc67af349bc5b82f73db73349ef18/CVLByExample/structs/BankAccounts/certora/specs/Bank.spec#L119"><code class="docutils literal notranslate"><span class="pre">axiom</span></code> example</a></p></li>
</ul>
</section>
<section id="initial-state-axioms">
<h3><a class="toc-backref" href="#id13" role="doc-backlink">Initial state axioms</a><a class="headerlink" href="#initial-state-axioms" title="Link to this heading"></a></h3>
<p>When writing invariants, initial axioms are a way to express the “constructor state” of a ghost function. They are used
only when checking the base step of invariants <a class="reference internal" href="invariants.html#invariant-as-rule"><span class="std std-ref">Writing an invariant as a rule</span></a>. Before checking the initial state of an invariant, the Certora Prover adds a <code class="docutils literal notranslate"><span class="pre">require</span></code> for each <code class="docutils literal notranslate"><span class="pre">init_state</span></code> axiom. <code class="docutils literal notranslate"><span class="pre">init_state</span></code> axioms are not used in rules or the preservation check for invariants.</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell6"><span></span><span class="kd">ghost</span><span class="w"> </span><span class="kt">mathint</span><span class="w"> </span>sumBalances<span class="p">{</span>
<span class="w">    </span><span class="c1">// assuming value zero at the initial state before constructor</span>
<span class="w">    </span><span class="kr">init_state</span><span class="w"> </span><span class="kr">axiom</span><span class="w"> </span>sumBalances<span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">;</span>
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
<ul class="simple">
<li><p><a class="reference external" href="https://github.com/Certora/Examples/blob/14668d39a6ddc67af349bc5b82f73db73349ef18/CVLByExample/ConstantProductPool/certora/spec/ConstantProductPool.spec#L207">initial state axiom example</a></p></li>
</ul>
</section>
</section>
<section id="restrictions-on-ghost-axioms">
<h2><a class="toc-backref" href="#id14" role="doc-backlink">Restrictions on ghost axioms</a><a class="headerlink" href="#restrictions-on-ghost-axioms" title="Link to this heading"></a></h2>
<ul class="simple">
<li><p>A ghost axiom cannot refer to Solidity or CVL functions or to other ghosts. It can refer to the ghost itself.</p></li>
<li><p>Since the signature of a ghost contains just parameter types without names, it cannot refer to its parameters.
<code class="docutils literal notranslate"><span class="pre">forall</span></code> can be used in order to refer the storage referred to by the parameters. <a class="reference external" href="https://github.com/Certora/Examples/blob/61ac29b1128c68aff7e8d1e77bc80bfcbd3528d6/CVLByExample/summary/ghost-summary/ghost-mapping/certora/specs/WithGhostSummary.spec#L12">Example</a>.</p></li>
</ul>
</section>
<section id="ghosts-vs-persistent-ghosts">
<span id="persistent-ghosts"></span><h2><a class="toc-backref" href="#id15" role="doc-backlink">Ghosts vs. persistent ghosts</a><a class="headerlink" href="#ghosts-vs-persistent-ghosts" title="Link to this heading"></a></h2>
<p>A <code class="docutils literal notranslate"><span class="pre">persistent</span> <span class="pre">ghost</span></code> is a <code class="docutils literal notranslate"><span class="pre">ghost</span></code> that will never be <a class="reference internal" href="../user-guide/glossary.html#glossary"><span class="std std-ref">havoc</span></a>. The value of a&nbsp;non-persistent <code class="docutils literal notranslate"><span class="pre">ghost</span></code> will be <code class="docutils literal notranslate"><span class="pre">havoc'ed</span></code> when the Prover <code class="docutils literal notranslate"><span class="pre">havoc</span></code>s the storage, a <code class="docutils literal notranslate"><span class="pre">persistent</span> <span class="pre">ghost</span></code> however will keep its value when storage is havoced.</p>
<p>In most cases, non-persistent ghosts are the natural choice for a specification
that requires extra tracking of information.</p>
<p>We present two examples where persistent ghosts are useful.</p>
<section id="persistent-ghosts-that-survive-havocs">
<h3><a class="toc-backref" href="#id16" role="doc-backlink">Persistent ghosts that survive havocs</a><a class="headerlink" href="#persistent-ghosts-that-survive-havocs" title="Link to this heading"></a></h3>
<p>In the first example, we want to track the occurrence of a potential reentrant call<a class="footnote-reference brackets" href="#reentrancy" id="id4" role="doc-noteref"><span class="fn-bracket">[</span>1<span class="fn-bracket">]</span></a>:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell7"><span></span><span class="kd">persistent</span><span class="w"> </span><span class="kd">ghost</span><span class="w"> </span><span class="kt">bool</span><span class="w"> </span>reentrancy_happened<span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kr">init_state</span><span class="w"> </span><span class="kr">axiom</span><span class="w"> </span><span class="o">!</span>reentrancy_happened<span class="p">;</span>
<span class="p">}</span>

<span class="kd">hook</span><span class="w"> </span>CALL<span class="p">(</span><span class="kt">uint</span><span class="w"> </span>g<span class="p">,</span><span class="w"> </span><span class="kt">address</span><span class="w"> </span>addr<span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>value<span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>argsOffset<span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>argsLength<span class="p">,</span><span class="w"> </span>
<span class="w">          </span><span class="kt">uint</span><span class="w"> </span>retOffset<span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>retLength<span class="p">)</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>rc<span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kr">if</span><span class="w"> </span><span class="p">(</span>addr<span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="nb">currentContract</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">        </span>reentrancy_happened<span class="w"> </span><span class="o">=</span><span class="w"> </span>reentrancy_happened<span class="w"> </span>
<span class="w">                                </span><span class="o">||</span><span class="w"> </span>executingContract<span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="nb">currentContract</span><span class="p">;</span>
<span class="w">    </span><span class="p">}</span>
<span class="p">}</span>

<span class="k">invariant</span><span class="w"> </span><span class="nc">no_reentrant_calls</span><span class="w"> </span><span class="o">!</span>reentrancy_happened<span class="p">;</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell7">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>To see why a persistent ghost must be used here for the variable <code class="docutils literal notranslate"><span class="pre">reentrancy_happened</span></code>, consider the following contract:</p>
<div class="highlight-solidity notranslate"><div class="highlight"><pre id="codecell8"><span></span><span class="k">contract</span><span class="w"> </span><span class="ni">NotReentrant</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kt">function</span><span class="w"> </span><span class="nv">transfer1Token</span><span class="p">(</span>IERC20<span class="w"> </span>a<span class="p">)</span><span class="w"> </span><span class="kt">external</span><span class="w"> </span><span class="p">{</span>
<span class="w">        </span><span class="kt">require</span><span class="w"> </span><span class="p">(</span><span class="kt">address</span><span class="p">(</span>a<span class="p">)</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="kt">address</span><span class="p">(</span><span class="kt">this</span><span class="p">));</span>
<span class="w">        </span>a<span class="p">.</span>transfer<span class="p">(</span><span class="k">msg.sender</span><span class="p">,</span><span class="w"> </span><span class="m m-Decimal">1</span><span class="p">);</span>
<span class="w">    </span><span class="p">}</span>
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
<p>If we do not apply any linking or dispatching for the call done on the target <code class="docutils literal notranslate"><span class="pre">a</span></code>, the call to <code class="docutils literal notranslate"><span class="pre">transfer</span></code> would havoc.
During a havoc operation, the Prover conservatively assumes that almost any possible behavior can occur.
In particular, it must assume that during the execution of the <code class="docutils literal notranslate"><span class="pre">a.transfer</span></code> call,
non-persistent ghosts can be updated arbitrarily (e.g. by other contracts),
and thus (assuming <code class="docutils literal notranslate"><span class="pre">reentrancy_happened</span></code> were not marked as persistent),
the Prover considers the case where <code class="docutils literal notranslate"><span class="pre">reentrancy_happened</span></code> is set to <code class="docutils literal notranslate"><span class="pre">true</span></code> due to the havoc.
Thus, when the <code class="docutils literal notranslate"><span class="pre">CALL</span></code> hook executes immediately after,
it does so where the <code class="docutils literal notranslate"><span class="pre">reentrancy_happened</span></code> value is already <code class="docutils literal notranslate"><span class="pre">true</span></code>,
and thus the value after the hook will remain <code class="docutils literal notranslate"><span class="pre">true</span></code>.</p>
<p>In the lower-level view of the tool, the sequence of events is as follows:</p>
<ol class="arabic simple">
<li><p>A call to <code class="docutils literal notranslate"><span class="pre">a.transfer</span></code> which cannot be resolved and results in a <a class="reference internal" href="../user-guide/glossary.html#glossary"><span class="std std-ref">havoc</span></a> operation.
Non-persistent ghosts are havoced, in particular <code class="docutils literal notranslate"><span class="pre">reentrancy_happened</span></code> if it were not marked as such.</p></li>
<li><p>A <code class="docutils literal notranslate"><span class="pre">CALL</span></code> hook executes, updating <code class="docutils literal notranslate"><span class="pre">reentrancy_happened</span></code> based on its havoced value, meaning it can turn to true.</p></li>
</ol>
<p>Therefore even if the addresses of <code class="docutils literal notranslate"><span class="pre">a</span></code> and <code class="docutils literal notranslate"><span class="pre">NotReentrant</span></code> are distinct, we could still falsely detect a reentrant call as <code class="docutils literal notranslate"><span class="pre">reentrancy_happened</span></code> was set to true due to non-determinism.
The call trace would show <code class="docutils literal notranslate"><span class="pre">reentrancy_happened</span></code> as being determined to be true due to a havoc in the “Ghosts State” view under “Global State”.</p>
</section>
<section id="persistent-ghosts-that-survive-reverts">
<h3><a class="toc-backref" href="#id17" role="doc-backlink">Persistent ghosts that survive reverts</a><a class="headerlink" href="#persistent-ghosts-that-survive-reverts" title="Link to this heading"></a></h3>
<p>In this example, we use persistent ghosts to determine if a revert happened with user-provided data or not.
This can help distinguishing between compiler-generated reverts and user-specified reverts (but only in <a class="reference external" href="https://soliditylang.org/blog/2020/10/28/solidity-0.8.x-preview/">Solidity versions prior to 0.8.x</a>).
The idea is to set a ghost to true if a <code class="docutils literal notranslate"><span class="pre">REVERT</span></code> opcode is encountered with a positive buffer size. As in early Solidity versions the panic errors would compile to reverts with empty buffers, as well as user-provided <code class="docutils literal notranslate"><span class="pre">require</span></code>s with no message specified.</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell9"><span></span><span class="kd">persistent</span><span class="w"> </span><span class="kd">ghost</span><span class="w"> </span><span class="kt">bool</span><span class="w"> </span>saw_user_defined_revert_msg<span class="p">;</span>

<span class="kd">hook</span><span class="w"> </span>REVERT<span class="p">(</span><span class="kt">uint</span><span class="w"> </span>offset<span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>size<span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kr">if</span><span class="w"> </span><span class="p">(</span>size<span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">        </span>saw_user_defined_revert_msg<span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="kr">true</span><span class="p">;</span>
<span class="w">    </span><span class="p">}</span>
<span class="p">}</span>

<span class="k">rule</span><span class="w"> </span><span class="nc">mark_methods_that_have_user_defined_reverts</span><span class="p">(</span><span class="kt">method</span><span class="w"> </span>f<span class="p">,</span><span class="w"> </span><span class="kt">env</span><span class="w"> </span>e<span class="p">,</span><span class="w"> </span><span class="kt">calldataarg</span><span class="w"> </span>args<span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kr">require</span><span class="w"> </span><span class="o">!</span>saw_user_defined_revert_msg<span class="p">;</span>

<span class="w">    </span>f<span class="ow">@withrevert</span><span class="p">(</span>e<span class="p">,</span><span class="w"> </span>args<span class="p">);</span>

<span class="w">    </span><span class="kr">satisfy</span><span class="w"> </span>saw_user_defined_revert_msg<span class="p">;</span>
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
<p>To see why a regular ghost cannot be used to implement this rule, let’s consider the following trivial contract:</p>
<div class="highlight-solidity notranslate"><div class="highlight"><pre id="codecell10"><span></span><span class="k">contract</span><span class="w"> </span><span class="ni">Reverting</span><span class="w"> </span><span class="p">{</span>
<span class="w">	</span><span class="kt">function</span><span class="w"> </span><span class="nv">noUserDefinedRevertFlows</span><span class="p">(</span><span class="kt">uint</span><span class="w"> </span><span class="nv">a</span><span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span><span class="nv">b</span><span class="p">)</span><span class="w"> </span><span class="kt">external</span><span class="w"> </span><span class="p">{</span>
<span class="w">		</span><span class="kt">uint</span><span class="w"> </span><span class="nv">c</span><span class="w"> </span><span class="o">=</span><span class="w"> </span>a<span class="o">/</span>b<span class="p">;</span><span class="w"> </span><span class="c1">// will see a potential division-by-zero revert</span>
<span class="w">		</span><span class="kt">uint</span><span class="p">[]</span><span class="w"> </span><span class="kt">memory</span><span class="w"> </span>arr<span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="kt">new</span><span class="w"> </span><span class="kt">uint</span><span class="p">[](</span><span class="m m-Decimal">1</span><span class="p">);</span>
<span class="w">		</span><span class="kt">uint</span><span class="w"> </span><span class="nv">d</span><span class="w"> </span><span class="o">=</span><span class="w"> </span>arr<span class="p">[</span>a<span class="o">+</span>b<span class="p">];</span><span class="w"> </span><span class="c1">// will see a potential out-of-bounds access revert;</span>
<span class="w">	</span><span class="p">}</span>

<span class="w">	</span><span class="kt">function</span><span class="w"> </span><span class="nv">userDefinedRequireMsg</span><span class="p">(</span><span class="kt">uint</span><span class="w"> </span><span class="nv">a</span><span class="p">)</span><span class="w"> </span><span class="kt">external</span><span class="w"> </span><span class="p">{</span>
<span class="w">		</span><span class="kt">require</span><span class="p">(</span>a<span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">,</span><span class="w"> </span><span class="s2">"a != 0"</span><span class="p">);</span>
<span class="w">	</span><span class="p">}</span>

<span class="w">	</span><span class="kt">function</span><span class="w"> </span><span class="nv">emptyRequire</span><span class="p">(</span><span class="kt">uint</span><span class="w"> </span><span class="nv">a</span><span class="p">)</span><span class="w"> </span><span class="kt">external</span><span class="w"> </span><span class="p">{</span>
<span class="w">		</span><span class="kt">require</span><span class="p">(</span>a<span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">);</span>
<span class="w">	</span><span class="p">}</span>
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
<p>It is expected for the method <code class="docutils literal notranslate"><span class="pre">userDefinedRequireMsg</span></code> to satisfy the rule,
and it should be the only method to satisfy it.
Assuming <code class="docutils literal notranslate"><span class="pre">saw_user_defined_revert_msg</span></code> was defined as a regular, non-persistent ghost,
the rule would not be satisfied for <code class="docutils literal notranslate"><span class="pre">userDefinedRequireMsg</span></code>: in case the input argument <code class="docutils literal notranslate"><span class="pre">a</span></code> is equal to 0,
the contract reverts, and the value of <code class="docutils literal notranslate"><span class="pre">saw_user_defined_revert_msg</span></code>
is reset to its value before the call, which must be <code class="docutils literal notranslate"><span class="pre">false</span></code>
(because the rule required it before the call).
In this case, after the call <code class="docutils literal notranslate"><span class="pre">saw_user_defined_revert_msg</span></code> cannot be set to true and thus the <code class="docutils literal notranslate"><span class="pre">satisfy</span></code> fails.
Applying the same reasoning, it is clear that the same behavior happens
for reverting behaviors of <code class="docutils literal notranslate"><span class="pre">noUserDefinedRevertFlows</span></code> and <code class="docutils literal notranslate"><span class="pre">emptyRequire</span></code>,
which do not have user-defined revert messages.
This means that if <code class="docutils literal notranslate"><span class="pre">saw_user_defined_revert_msg</span></code> is not marked persistent,
the rule cannot distinguishing between methods that may revert with user-defined messages and methods that may not.</p>
<hr class="footnotes docutils">
<aside class="footnote-list brackets">
<aside class="footnote brackets" id="reentrancy" role="doc-footnote">
<span class="label"><span class="fn-bracket">[</span><a role="doc-backlink" href="#id4">1</a><span class="fn-bracket">]</span></span>
<p>The example given here is very basic,  the examples repository contains <a class="reference external" href="https://github.com/Certora/Examples/tree/master/CVLByExample/Reentrancy">more complete examples of reentrancy checks</a></p>
</aside>
</aside>
</section>
</section>
</section>


           </div>
          </div>
          <footer><div class="rst-footer-buttons" role="navigation" aria-label="Footer">
        <a href="sorts.html" class="btn btn-neutral float-left" title="Uninterpreted Sorts" accesskey="p" rel="prev"><span class="fa fa-arrow-circle-left" aria-hidden="true"></span> Previous</a>
        <a href="defs.html" class="btn btn-neutral float-right" title="Definitions" accesskey="n" rel="next">Next <span class="fa fa-arrow-circle-right" aria-hidden="true"></span></a>
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