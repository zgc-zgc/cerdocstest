<!DOCTYPE html><html class="writer-html5" lang="en" data-content_root="../../"><head>
  <meta charset="utf-8"><meta name="viewport" content="width=device-width, initial-scale=1">

  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Hooks — Certora Prover Documentation 0.0 documentation</title>
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
    <link rel="next" title="Transient Storage" href="transient.html">
    <link rel="prev" title="Definitions" href="defs.html"> 
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
<li class="toctree-l2"><a class="reference internal" href="defs.html">Definitions</a></li>
<li class="toctree-l2 current" aria-expanded="true"><a class="reference internal current" href="#" aria-expanded="true"><button class="toctree-expand" title="Open/close menu"></button>Hooks</a><ul>
<li class="toctree-l3"><a class="reference internal" href="#syntax">Syntax</a></li>
<li class="toctree-l3"><a class="reference internal" href="#examples">Examples</a></li>
<li class="toctree-l3"><a class="reference internal" href="#load-and-store-hooks"><button class="toctree-expand" title="Open/close menu"></button>Load and store hooks</a><ul>
<li class="toctree-l4"><a class="reference internal" href="#access-paths">Access paths</a></li>
<li class="toctree-l4"><a class="reference internal" href="#access-path-caveats">Access path caveats</a></li>
<li class="toctree-l4"><a class="reference internal" href="#hooking-on-all-storage-loads-or-stores">Hooking on all storage loads or stores</a></li>
</ul>
</li>
<li class="toctree-l3"><a class="reference internal" href="#evm-opcode-hooks"><button class="toctree-expand" title="Open/close menu"></button>EVM opcode hooks</a><ul>
<li class="toctree-l4"><a class="reference internal" href="#call-hooks">Call hooks</a></li>
<li class="toctree-l4"><a class="reference internal" href="#known-inter-dependencies-and-common-pitfalls">Known inter-dependencies and common pitfalls</a></li>
</ul>
</li>
<li class="toctree-l3"><a class="reference internal" href="#hook-bodies"><button class="toctree-expand" title="Open/close menu"></button>Hook bodies</a><ul>
<li class="toctree-l4"><a class="reference internal" href="#keywords-available-in-hook-bodies">Keywords available in hook bodies</a></li>
<li class="toctree-l4"><a class="reference internal" href="#reentrant-hooks">Reentrant hooks</a></li>
</ul>
</li>
</ul>
</li>
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
      <li class="breadcrumb-item active">Hooks</li>
      <li class="wy-breadcrumbs-aside">
            <a href="../../_sources/docs/cvl/hooks.md.txt" rel="nofollow"> View page source</a>
      </li>
  </ul>
  <hr>
</div>
          <div role="main" class="document" itemscope="itemscope" itemtype="http://schema.org/Article">
           <div itemprop="articleBody">
             
  <section id="hooks">
<span id="id1"></span><h1><a class="toc-backref" href="#id5" role="doc-backlink">Hooks</a><a class="headerlink" href="#hooks" title="Link to this heading"></a></h1>
<p>Hooks are used to attach CVL code to certain low-level operations, such as
loads and stores to specific storage variables.</p>
<p>Each hook contains a pattern that describes what operations cause the hook to
be invoked, and a block of code that is executed when the contract performs
those operations.</p>
<p>The remainder of this document describes the operation of hooks in detail.  For
examples of idiomatic hook usage, see <a class="reference internal" href="../user-guide/ghosts.html#tracking-changes"><span class="std std-ref">Tracking changes with ghosts and hooks</span></a> and
<a class="reference internal" href="../user-guide/opcodes.html#using-opcodes"><span class="std std-ref">Using Opcode Hooks</span></a>.</p>
<nav class="contents" id="contents">
<p class="topic-title">Contents</p>
<ul class="simple">
<li><p><a class="reference internal" href="#hooks" id="id5">Hooks</a></p>
<ul>
<li><p><a class="reference internal" href="#syntax" id="id6">Syntax</a></p></li>
<li><p><a class="reference internal" href="#examples" id="id7">Examples</a></p></li>
<li><p><a class="reference internal" href="#load-and-store-hooks" id="id8">Load and store hooks</a></p>
<ul>
<li><p><a class="reference internal" href="#access-paths" id="id9">Access paths</a></p></li>
<li><p><a class="reference internal" href="#access-path-caveats" id="id10">Access path caveats</a></p></li>
<li><p><a class="reference internal" href="#hooking-on-all-storage-loads-or-stores" id="id11">Hooking on all storage loads or stores</a></p>
<ul>
<li><p><a class="reference internal" href="#notes-on-transient-storage" id="id12">Notes on transient storage.</a></p></li>
</ul>
</li>
</ul>
</li>
<li><p><a class="reference internal" href="#evm-opcode-hooks" id="id13">EVM opcode hooks</a></p>
<ul>
<li><p><a class="reference internal" href="#call-hooks" id="id14">Call hooks</a></p></li>
<li><p><a class="reference internal" href="#known-inter-dependencies-and-common-pitfalls" id="id15">Known inter-dependencies and common pitfalls</a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#hook-bodies" id="id16">Hook bodies</a></p>
<ul>
<li><p><a class="reference internal" href="#keywords-available-in-hook-bodies" id="id17">Keywords available in hook bodies</a></p></li>
<li><p><a class="reference internal" href="#reentrant-hooks" id="id18">Reentrant hooks</a></p></li>
</ul>
</li>
</ul>
</li>
</ul>
</nav>
<section id="syntax">
<h2><a class="toc-backref" href="#id6" role="doc-backlink">Syntax</a><a class="headerlink" href="#syntax" title="Link to this heading"></a></h2>
<p>The syntax for hooks is given by the following EBNF grammar:</p>
<div class="highlight-default notranslate"><div class="highlight"><pre id="codecell0"><span></span><span class="n">hook</span> <span class="p">:</span><span class="o">:=</span> <span class="s2">"hook"</span> <span class="n">pattern</span> <span class="n">block</span>

<span class="n">pattern</span> <span class="p">:</span><span class="o">:=</span> <span class="s2">"Sstore"</span> <span class="n">access_path</span> <span class="n">param</span> <span class="p">[</span> <span class="s2">"("</span> <span class="n">param</span> <span class="s2">")"</span> <span class="p">]</span>
          <span class="o">|</span> <span class="s2">"Sload"</span>  <span class="n">param</span> <span class="n">access_path</span>
          <span class="o">|</span> <span class="n">opcode</span>   <span class="p">[</span> <span class="s2">"("</span> <span class="n">params</span> <span class="s2">")"</span> <span class="p">]</span> <span class="p">[</span> <span class="n">param</span> <span class="p">]</span>

<span class="n">access_path</span> <span class="p">:</span><span class="o">:=</span> <span class="nb">id</span>
              <span class="o">|</span> <span class="p">[</span> <span class="nb">id</span> <span class="s2">"."</span> <span class="p">]</span> <span class="s2">"("</span> <span class="s2">"slot"</span> <span class="n">number</span> <span class="s2">")"</span>
              <span class="o">|</span> <span class="n">access_path</span> <span class="s2">"."</span> <span class="nb">id</span>
              <span class="o">|</span> <span class="n">access_path</span> <span class="s2">"["</span> <span class="s2">"KEY"</span>   <span class="n">basic_type</span> <span class="nb">id</span> <span class="s2">"]"</span>
              <span class="o">|</span> <span class="n">access_path</span> <span class="s2">"["</span> <span class="s2">"INDEX"</span> <span class="n">basic_type</span> <span class="nb">id</span> <span class="s2">"]"</span>
              <span class="o">|</span> <span class="n">access_path</span> <span class="s2">"."</span> <span class="s2">"("</span> <span class="s2">"offset"</span> <span class="n">number</span> <span class="s2">")"</span>

<span class="n">opcode</span> <span class="p">:</span><span class="o">:=</span> <span class="s2">"ALL_SLOAD"</span> <span class="o">|</span> <span class="s2">"ALL_SSTORE"</span> <span class="o">|</span> <span class="s2">"ALL_TLOAD"</span> <span class="o">|</span> <span class="s2">"ALL_TSTORE"</span> <span class="o">|</span> <span class="o">...</span>

<span class="n">param</span>  <span class="p">:</span><span class="o">:=</span> <span class="n">evm_type</span> <span class="nb">id</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell0">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>See <a class="reference internal" href="#opcode-hooks"><span class="std std-ref">EVM opcode hooks</span></a> below for the list of available opcodes.</p>
<p>See <a class="reference internal" href="statements.html"><span class="doc">Statements</span></a> for information about the <code class="docutils literal notranslate"><span class="pre">statement</span></code> production; see
<a class="reference internal" href="types.html"><span class="doc">Types</span></a> for the <code class="docutils literal notranslate"><span class="pre">evm_type</span></code> production; see <a class="reference internal" href="basics.html"><span class="doc">Basic Syntax</span></a> for the <code class="docutils literal notranslate"><span class="pre">number</span></code>
production.</p>
<p>It is prohibited to have multiple hooks with the same hook pattern.
Two hooks have the same hook pattern if both are <code class="docutils literal notranslate"><span class="pre">Sstore</span></code> hooks with the same
access path, both are <code class="docutils literal notranslate"><span class="pre">Sload</span></code> hooks with the same access path, or both are
opcode hooks with the same opcode.
Doing so will result in an error like this:
<code class="docutils literal notranslate"><span class="pre">The</span> <span class="pre">declared</span> <span class="pre">hook</span> <span class="pre">pattern</span> <span class="pre">&lt;second</span> <span class="pre">hook&gt;</span> <span class="pre">duplicates</span> <span class="pre">the</span> <span class="pre">hook</span> <span class="pre">pattern</span> <span class="pre">&lt;first</span> <span class="pre">hook&gt;</span> <span class="pre">at</span> <span class="pre">&lt;spec</span> <span class="pre">file&gt;.</span> <span class="pre">A</span> <span class="pre">hook</span> <span class="pre">pattern</span> <span class="pre">may</span> <span class="pre">only</span> <span class="pre">be</span> <span class="pre">used</span> <span class="pre">once.</span></code>
Note that two access paths are considered to be “the same” if they resolve to
the same storage address. Syntactically different access paths can alias, e.g.,
when accessing a member by name (<code class="docutils literal notranslate"><span class="pre">contract.member</span></code>) or by slot
(<code class="docutils literal notranslate"><span class="pre">contract.(slot</span> <span class="pre">n)</span></code>).</p>
</section>
<section id="examples">
<h2><a class="toc-backref" href="#id7" role="doc-backlink">Examples</a><a class="headerlink" href="#examples" title="Link to this heading"></a></h2>
<ul class="simple">
<li><p><a class="reference external" href="https://github.com/Certora/Examples/blob/14668d39a6ddc67af349bc5b82f73db73349ef18/CVLByExample/ERC20/certora/specs/ERC20.spec#L117">store hook example</a></p></li>
<li><p><a class="reference external" href="https://github.com/Certora/Examples/blob/14668d39a6ddc67af349bc5b82f73db73349ef18/CVLByExample/structs/BankAccounts/certora/specs/Bank.spec#L141">load hook example</a></p></li>
</ul>
<p>See <a class="reference internal" href="../user-guide/opcodes.html#using-opcodes"><span class="std std-ref">Using Opcode Hooks</span></a> and <a class="reference internal" href="../user-guide/ghosts.html#tracking-changes"><span class="std std-ref">Tracking changes with ghosts and hooks</span></a> for additional examples.</p>
</section>
<section id="load-and-store-hooks">
<span id="store-hooks"></span><span id="load-hooks"></span><h2><a class="toc-backref" href="#id8" role="doc-backlink">Load and store hooks</a><a class="headerlink" href="#load-and-store-hooks" title="Link to this heading"></a></h2>
<p>Load hooks are executed before a read from a specific location in storage, while
store hooks are executed before a write to a specific location in storage.</p>
<p>The locations to be matched are given by an access path, such as a contract
variable, array index, or a slot number.  See <a class="reference internal" href="#access-paths"><span class="std std-ref">Access paths</span></a> below for
information on the available access paths.</p>
<p>A load pattern contains the keyword <code class="docutils literal notranslate"><span class="pre">Sload</span></code>, followed by the type and name of a
variable that will hold the loaded value, followed by an access path indicating
the location that is read.</p>
<p>For example, here is a load hook that will execute whenever a contract reads the
value of <code class="docutils literal notranslate"><span class="pre">C.owner</span></code>:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell1"><span></span><span class="kd">hook</span><span class="w"> </span><span class="kp">Sload</span><span class="w"> </span><span class="kt">address</span><span class="w"> </span>o<span class="w"> </span>C<span class="p">.</span>owner<span class="w"> </span><span class="p">{</span><span class="w"> </span><span class="p">...</span><span class="w"> </span><span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell1">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>Inside the body of this hook, the variable <code class="docutils literal notranslate"><span class="pre">o</span></code> will be bound to the value that
was read.</p>
<p>A store pattern contains the keyword <code class="docutils literal notranslate"><span class="pre">Sstore</span></code>, followed by an access path
indicating the location that is being written to, followed by the type and name
of a variable to hold the value that is being stored.  Optionally, the pattern
may also include the type and name of a variable to store the previous value
that is being overwritten.</p>
<p>For example, here is a store hook that will execute whenever a contract writes
the value of <code class="docutils literal notranslate"><span class="pre">C.totalSupply</span></code>:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell2"><span></span><span class="kd">hook</span><span class="w"> </span><span class="kp">Sstore</span><span class="w"> </span>C<span class="p">.</span>totalSupply<span class="w"> </span><span class="kt">uint</span><span class="w"> </span>ts<span class="w"> </span><span class="p">(</span><span class="kt">uint</span><span class="w"> </span>old_ts<span class="p">)</span><span class="w"> </span><span class="p">{</span><span class="w"> </span><span class="p">...</span><span class="w"> </span><span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell2">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>Inside the body of this hook, the variable <code class="docutils literal notranslate"><span class="pre">ts</span></code> will be bound to the value that
is being written to the <code class="docutils literal notranslate"><span class="pre">totalSupply</span></code> variable, while <code class="docutils literal notranslate"><span class="pre">old_ts</span></code> is bound to the
value that was stored there previously.</p>
<p>If you do not need to refer to the old value, you can omit the variable
declaration for it.  For example, the following hook only binds the new value
of <code class="docutils literal notranslate"><span class="pre">C.totalSupply</span></code>:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell3"><span></span><span class="kd">hook</span><span class="w"> </span><span class="kp">Sstore</span><span class="w"> </span>C<span class="p">.</span>totalSupply<span class="w"> </span><span class="kt">uint</span><span class="w"> </span>ts<span class="w"> </span><span class="p">{</span><span class="w"> </span><span class="p">...</span><span class="w"> </span><span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell3">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>A hook will <strong>not</strong> be triggered by CVL code, including access to solidity
storage from CVL.</p>
</div>
<section id="access-paths">
<span id="id2"></span><h3><a class="toc-backref" href="#id9" role="doc-backlink">Access paths</a><a class="headerlink" href="#access-paths" title="Link to this heading"></a></h3>
<p>The patterns for load and store hooks are fine-grained; they allow you to hook
on accesses to specific contract variables or specific array, struct, or
mapping accesses.</p>
<p>Storage locations are designated by “access paths”.  An access path
starts with either the name of a contract field, or a <a class="reference external" href="https://docs.soliditylang.org/en/v0.8.17/internals/layout_in_storage.html">slot number</a>.</p>
<p>Contract fields may be qualified by the contract that defines them (e.g.
<code class="docutils literal notranslate"><span class="pre">Contract.field</span></code>).  If the contract name is omitted, it defaults to
<code class="docutils literal notranslate"><span class="pre">currentContract</span></code>.  The contract name may either be an instance variable
introduced by a [using statement][using] or the name of a contract on the
<a class="reference internal" href="../user-guide/glossary.html#term-0"><span class="xref std std-term">scene</span></a>.</p>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>If a contract inherits multiple variables with the same name, you cannot use
that variable as an access path.</p>
</div>
<p>If the indicated location holds a struct, you can refer to a specific field of
the struct by appending <code class="docutils literal notranslate"><span class="pre">.&lt;field-name&gt;</span></code> to the path.  For example, the following
hook will execute on every store to the <code class="docutils literal notranslate"><span class="pre">balance</span></code> field of the struct <code class="docutils literal notranslate"><span class="pre">C.owner</span></code>:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell4"><span></span><span class="kd">hook</span><span class="w"> </span><span class="kp">Sstore</span><span class="w"> </span>C<span class="p">.</span>owner<span class="p">.</span>balance<span class="w"> </span><span class="kt">uint</span><span class="w"> </span>b<span class="w"> </span><span class="p">{</span><span class="w"> </span><span class="p">...</span><span class="w"> </span><span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell4">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>If the indicated location holds an array, you can refer to an arbitrary element
of the array by appending <code class="docutils literal notranslate"><span class="pre">[INDEX</span> <span class="pre">uint</span> <span class="pre">&lt;variable&gt;]</span></code>.  This pattern will match
any store to an element of the array, and will bind the named variable to the
index of the access.  For example, the following hook will execute on any write
to the array <code class="docutils literal notranslate"><span class="pre">C.entries</span></code> and will update the corresponding entry of the ghost
mapping <code class="docutils literal notranslate"><span class="pre">_entries</span></code> to match:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell5"><span></span><span class="kd">hook</span><span class="w"> </span><span class="kp">Sstore</span><span class="w"> </span>C<span class="p">.</span>entries<span class="p">[</span><span class="kp">INDEX</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>i<span class="p">]</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>e<span class="w"> </span><span class="p">{</span>
<span class="w">    </span>_entries<span class="p">[</span>i<span class="p">]</span><span class="w"> </span><span class="o">=</span><span class="w"> </span>e<span class="p">;</span>
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
<p>Additionally, if the indicated location holds a <em>dynamic</em> array, you can refer
to accesses to the length of the array with <code class="docutils literal notranslate"><span class="pre">.length</span></code>:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell6"><span></span><span class="kd">hook</span><span class="w"> </span><span class="kp">Sstore</span><span class="w"> </span>C<span class="p">.</span>entries<span class="p">.</span>length<span class="w"> </span><span class="kt">uint</span><span class="w"> </span>len<span class="w"> </span><span class="p">{</span>
<span class="w">    </span>_len<span class="w"> </span><span class="o">=</span><span class="w"> </span>len<span class="p">;</span><span class="w"> </span><span class="c1">// updates a ghost variable `_len` with the length is written to storage.</span>
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
<p>Similarly, if the indicated location holds a mapping, you can refer to an
arbitrary entry by appending <code class="docutils literal notranslate"><span class="pre">[KEY</span> <span class="pre">&lt;type&gt;</span> <span class="pre">&lt;variable&gt;]</span></code>.  This pattern will
match any write to the mapping, and will bind the named variable to the key.
For example, the following hook will execute on any write to the mapping
<code class="docutils literal notranslate"><span class="pre">C.balances</span></code>, and will update the <code class="docutils literal notranslate"><span class="pre">_balances</span></code> ghost accordingly:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell7"><span></span><span class="kd">hook</span><span class="w"> </span><span class="kp">Sstore</span><span class="w"> </span>C<span class="p">.</span>balances<span class="p">[</span><span class="kp">KEY</span><span class="w"> </span><span class="kt">address</span><span class="w"> </span>user<span class="p">]</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>balance<span class="w"> </span><span class="p">{</span>
<span class="w">    </span>_balances<span class="p">[</span>user<span class="p">]</span><span class="w"> </span><span class="o">=</span><span class="w"> </span>balance<span class="p">;</span>
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
<p>Finally, there is the low-level access pattern <code class="docutils literal notranslate"><span class="pre">&lt;base&gt;.(offset</span> <span class="pre">&lt;n&gt;)</span></code> for matching
loads and stores that are a specific number of bytes from the
base.  For example, the following hook will match writes to the third or fourth
byte of slot 1 (these two bytes are matched because the type of the variable is
<code class="docutils literal notranslate"><span class="pre">uint16</span></code>:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell8"><span></span><span class="kd">hook</span><span class="w"> </span><span class="kp">Sstore</span><span class="w"> </span><span class="p">(</span>slot<span class="w"> </span><span class="m m-Decimal">1</span><span class="p">).(</span>offset<span class="w"> </span><span class="m m-Decimal">2</span><span class="p">)</span><span class="w"> </span><span class="kt">uint16</span><span class="w"> </span>b<span class="w"> </span><span class="p">{</span><span class="w"> </span><span class="p">...</span><span class="w"> </span><span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell8">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>These different kinds of paths can be combined, subject to restrictions listed
below.  For example, the following hook will execute whenever the contract
writes to the <code class="docutils literal notranslate"><span class="pre">balance</span></code> field of a struct in the <code class="docutils literal notranslate"><span class="pre">users</span></code> mapping of contract
<code class="docutils literal notranslate"><span class="pre">C</span></code>:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell9"><span></span><span class="kd">hook</span><span class="w"> </span>C<span class="p">.</span>users<span class="p">[</span><span class="kp">KEY</span><span class="w"> </span><span class="kt">address</span><span class="w"> </span>user<span class="p">].</span>balance<span class="w"> </span><span class="kt">uint</span><span class="w"> </span>v<span class="w"> </span><span class="p">(</span><span class="kt">uint</span><span class="w"> </span>old_value<span class="p">)</span><span class="w"> </span><span class="p">{</span><span class="w"> </span><span class="p">...</span><span class="w"> </span><span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell9">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>Inside the body of the hook, the variable <code class="docutils literal notranslate"><span class="pre">user</span></code> will refer to the address that
was used as the key into the mapping <code class="docutils literal notranslate"><span class="pre">C.users</span></code>; the variable <code class="docutils literal notranslate"><span class="pre">v</span></code> will contain
the value that is written, and the variable <code class="docutils literal notranslate"><span class="pre">old_value</span></code> will contain the value
that was previously stored there.</p>
<p>There are a few restrictions on the available combinations of low-level and
high-level access paths:</p>
<ul class="simple">
<li><p>You cannot access struct fields on access paths that contain <code class="docutils literal notranslate"><span class="pre">slot</span></code> or
<code class="docutils literal notranslate"><span class="pre">offset</span></code> components, because the struct type is not known.</p></li>
<li><p>You can only use <code class="docutils literal notranslate"><span class="pre">KEY</span></code> and <code class="docutils literal notranslate"><span class="pre">INDEX</span></code> patterns on word-aligned access paths
(i.e.  any <code class="docutils literal notranslate"><span class="pre">offset</span></code> components must be multiples of 32).</p></li>
</ul>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>The only available access paths for <code class="docutils literal notranslate"><span class="pre">solc</span></code> versions 5.17 and older are <code class="docutils literal notranslate"><span class="pre">slot</span></code>
and <code class="docutils literal notranslate"><span class="pre">offset</span></code> paths.</p>
</div>
</section>
<section id="access-path-caveats">
<h3><a class="toc-backref" href="#id10" role="doc-backlink">Access path caveats</a><a class="headerlink" href="#access-path-caveats" title="Link to this heading"></a></h3>
<p>In order to apply hooks correctly, the Prover must analyze the contract’s
use of storage.  In some cases, especially in the presence of inline assembly
<code class="docutils literal notranslate"><span class="pre">sload</span></code> and <code class="docutils literal notranslate"><span class="pre">sstore</span></code> instructions, the analysis will fail.  In this case, hooks
may not be applied.</p>
<p>If storage analysis fails, you will see a message indicating the failure in the
global problems view of the rule report.  See <a class="reference internal" href="../prover/techniques/index.html#storage-and-memory-analysis"><span class="std std-ref">Analysis of EVM storage and EVM memory</span></a>
for more details.</p>
</section>
<section id="hooking-on-all-storage-loads-or-stores">
<span id="rawhooks"></span><h3><a class="toc-backref" href="#id11" role="doc-backlink">Hooking on all storage loads or stores</a><a class="headerlink" href="#hooking-on-all-storage-loads-or-stores" title="Link to this heading"></a></h3>
<p>Load and store hooks apply to reads and writes to specific storage locations.
In some cases, it is useful to instrument every load or store, regardless of
the location.</p>
<p>The <code class="docutils literal notranslate"><span class="pre">ALL_SLOAD</span></code> and <code class="docutils literal notranslate"><span class="pre">ALL_SSTORE</span></code> opcode hooks are used for this purpose; they
will be executed on every load and store instruction (in all contracts)
respectively.  See <a class="reference internal" href="#opcode-hooks"><span class="std std-ref">EVM opcode hooks</span></a> below for the general syntax of opcode
hooks.</p>
<p>The <code class="docutils literal notranslate"><span class="pre">ALL_SLOAD</span></code> opcode hook takes one input <code class="docutils literal notranslate"><span class="pre">uint</span></code> argument containing the slot
number of the load instruction, and has one <code class="docutils literal notranslate"><span class="pre">uint</span></code> output containing the value
that is loaded from the slot.  For example:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell10"><span></span><span class="kd">hook</span><span class="w"> </span>ALL_SLOAD<span class="p">(</span><span class="kt">uint</span><span class="w"> </span>slot<span class="p">)</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>val<span class="w"> </span><span class="p">{</span><span class="w"> </span><span class="p">...</span><span class="w"> </span><span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell10">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>The <code class="docutils literal notranslate"><span class="pre">ALL_SSTORE</span></code> opcode hook takes two input <code class="docutils literal notranslate"><span class="pre">uint</span></code> arguments; the first is the
slot number of the store instruction, and the second is the value being stored.
For example:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell11"><span></span><span class="kd">hook</span><span class="w"> </span>ALL_SSTORE<span class="p">(</span><span class="kt">uint</span><span class="w"> </span>slot<span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>val<span class="p">)</span><span class="w"> </span><span class="p">{</span><span class="w"> </span><span class="p">...</span><span class="w"> </span><span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell11">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>The storage splitting optimization must be disabled using the
<a class="reference internal" href="../prover/cli/options.html#enablestoragesplitting"><span class="std std-ref">enableStorageSplitting</span></a> option in order to use the <code class="docutils literal notranslate"><span class="pre">ALL_SLOAD</span></code> or
<code class="docutils literal notranslate"><span class="pre">ALL_SSTORE</span></code> hooks.</p>
</div>
<p>If a load instruction matches an <code class="docutils literal notranslate"><span class="pre">Sload</span></code> hook pattern and there is also an
<code class="docutils literal notranslate"><span class="pre">ALL_SLOAD</span></code> hook, then both hooks will be executed; the <code class="docutils literal notranslate"><span class="pre">Sload</span></code> hook will apply
first, and then the <code class="docutils literal notranslate"><span class="pre">ALL_SLOAD</span></code> hook.</p>
<p>Similarly, if a store would trigger both an <code class="docutils literal notranslate"><span class="pre">Sstore</span></code> pattern and an <code class="docutils literal notranslate"><span class="pre">ALL_SSTORE</span></code>
pattern, the <code class="docutils literal notranslate"><span class="pre">Sstore</span></code> hook would be executed, followed by the <code class="docutils literal notranslate"><span class="pre">ALL_SSTORE</span></code> hook.</p>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>Just like the usual opcode hooks, the raw storage hooks are applied on all
contracts.  This means that a storage access on <em>any</em> contract will trigger the
hook.  Therefore, in a rule that models calls to multiple contracts, if two
contracts are accessing the same slot the same hook code will be called with
the same slot number.</p>
</div>
<section id="notes-on-transient-storage">
<h4><a class="toc-backref" href="#id12" role="doc-backlink">Notes on transient storage.</a><a class="headerlink" href="#notes-on-transient-storage" title="Link to this heading"></a></h4>
<p>In a similar vein to <code class="docutils literal notranslate"><span class="pre">ALL_SLOAD</span></code> and <code class="docutils literal notranslate"><span class="pre">ALL_SSTORE</span></code> hooks, CVL also allows
to hook on <code class="docutils literal notranslate"><span class="pre">TLOAD</span></code> and <code class="docutils literal notranslate"><span class="pre">TSTORE</span></code> instructions for updating the transient
storage, using the <code class="docutils literal notranslate"><span class="pre">ALL_TLOAD</span></code> and <code class="docutils literal notranslate"><span class="pre">ALL_TSTORE</span></code> hooks.
The hooks for transient storage access share the syntax of their regular storage counterparts.</p>
<p>Given that Solidity only allows (as of v0.8.25) access to transient
storage via inline-assembly, and has no notion of structure to
transient storage, Prover currently does not expose access-path based
access like for the regular storage hooks.</p>
<p>For more information on how the Prover models transient storage,
please refer to the relevant section on <a class="reference internal" href="transient.html#transient-storage"><span class="std std-ref">transient storage</span></a>.</p>
</section>
</section>
</section>
<section id="evm-opcode-hooks">
<span id="opcode-hooks"></span><h2><a class="toc-backref" href="#id13" role="doc-backlink">EVM opcode hooks</a><a class="headerlink" href="#evm-opcode-hooks" title="Link to this heading"></a></h2>
<p>Opcode hooks are executed just after<a class="footnote-reference brackets" href="#before-hooks" id="id3" role="doc-noteref"><span class="fn-bracket">[</span>1<span class="fn-bracket">]</span></a> a contract executes a
specific <a class="reference external" href="https://ethereum.org/en/developers/docs/evm/opcodes/">EVM opcode</a>.  An opcode hook pattern consists of the
name of the opcode, followed by the inputs to the opcode (if any), followed by
the type and variable name for the output (if any).</p>
<p>For example, the following hook will execute immediately after any contract
executes the <code class="docutils literal notranslate"><span class="pre">EXTCODESIZE</span></code> instruction:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell12"><span></span><span class="kd">hook</span><span class="w"> </span>EXTCODESIZE<span class="p">(</span><span class="kt">address</span><span class="w"> </span>addr<span class="p">)</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>v<span class="w"> </span><span class="p">{</span><span class="w"> </span><span class="p">...</span><span class="w"> </span><span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell12">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>Within the body of the hook, the <code class="docutils literal notranslate"><span class="pre">addr</span></code> variable will be bound to the address
argument to the opcode, and the variable <code class="docutils literal notranslate"><span class="pre">v</span></code> will be bound to the returned value
of the opcode.</p>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>Opcode hooks are applied to <em>all</em> contracts, not just the main contract under
verification.</p>
</div>
<p>Opcode hooks have the same names, arguments, and return values as the
corresponding <a class="reference external" href="https://ethereum.org/en/developers/docs/evm/opcodes/">EVM opcodes</a>, with the exception of the <code class="docutils literal notranslate"><span class="pre">CREATE1</span></code>
hook, which corresponds to the <code class="docutils literal notranslate"><span class="pre">CREATE</span></code> opcode.</p>
<p>Below is the set of supported opcode hook patterns:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell13"><span></span><span class="kd">hook</span><span class="w"> </span>ADDRESS<span class="w"> </span><span class="kt">address</span><span class="w"> </span>v

<span class="kd">hook</span><span class="w"> </span>BALANCE<span class="p">(</span><span class="kt">address</span><span class="w"> </span>addr<span class="p">)</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>v

<span class="kd">hook</span><span class="w"> </span>ORIGIN<span class="w"> </span><span class="kt">address</span><span class="w"> </span>v

<span class="kd">hook</span><span class="w"> </span>CALLER<span class="w"> </span><span class="kt">address</span><span class="w"> </span>v

<span class="kd">hook</span><span class="w"> </span>CALLVALUE<span class="w"> </span><span class="kt">uint</span><span class="w"> </span>v

<span class="kd">hook</span><span class="w"> </span>CODESIZE<span class="w"> </span><span class="kt">uint</span><span class="w"> </span>v

<span class="kd">hook</span><span class="w"> </span>CODECOPY<span class="p">(</span><span class="kt">uint</span><span class="w"> </span>destOffset<span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>offset<span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>length<span class="p">)</span>

<span class="kd">hook</span><span class="w"> </span>GASPRICE<span class="w"> </span><span class="kt">uint</span><span class="w"> </span>v

<span class="kd">hook</span><span class="w"> </span>EXTCODESIZE<span class="p">(</span><span class="kt">address</span><span class="w"> </span>addr<span class="p">)</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>v

<span class="kd">hook</span><span class="w"> </span>EXTCODECOPY<span class="p">(</span><span class="kt">address</span><span class="w"> </span>b<span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>destOffset<span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>offset<span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>length<span class="p">)</span>

<span class="kd">hook</span><span class="w"> </span>EXTCODEHASH<span class="p">(</span><span class="kt">address</span><span class="w"> </span>a<span class="p">)</span><span class="w"> </span><span class="kt">bytes32</span><span class="w"> </span><span class="kt">hash</span>

<span class="kd">hook</span><span class="w"> </span>BLOCKHASH<span class="p">(</span><span class="kt">uint</span><span class="w"> </span>n<span class="p">)</span><span class="w"> </span><span class="kt">bytes32</span><span class="w"> </span><span class="kt">hash</span>

<span class="kd">hook</span><span class="w"> </span>COINBASE<span class="w"> </span><span class="kt">address</span><span class="w"> </span>v

<span class="kd">hook</span><span class="w"> </span>TIMESTAMP<span class="w"> </span><span class="kt">uint</span><span class="w"> </span>v

<span class="kd">hook</span><span class="w"> </span>NUMBER<span class="w"> </span><span class="kt">uint</span><span class="w"> </span>v

<span class="kd">hook</span><span class="w"> </span>DIFFICULTY<span class="w"> </span><span class="kt">uint</span><span class="w"> </span>v

<span class="kd">hook</span><span class="w"> </span>GASLIMIT<span class="w"> </span><span class="kt">uint</span><span class="w"> </span>v

<span class="kd">hook</span><span class="w"> </span>CHAINID<span class="w"> </span><span class="kt">uint</span><span class="w"> </span>v

<span class="kd">hook</span><span class="w"> </span>SELFBALANCE<span class="w"> </span><span class="kt">uint</span><span class="w"> </span>v

<span class="kd">hook</span><span class="w"> </span>BASEFEE<span class="w"> </span><span class="kt">uint</span><span class="w"> </span>v

<span class="kd">hook</span><span class="w"> </span>MSIZE<span class="w"> </span><span class="kt">uint</span><span class="w"> </span>v

<span class="kd">hook</span><span class="w"> </span>GAS<span class="w"> </span><span class="kt">uint</span><span class="w"> </span>v

<span class="kd">hook</span><span class="w"> </span>LOG0<span class="p">(</span><span class="kt">uint</span><span class="w"> </span>offset<span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>length<span class="p">)</span>

<span class="kd">hook</span><span class="w"> </span>LOG1<span class="p">(</span><span class="kt">uint</span><span class="w"> </span>offset<span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>length<span class="p">,</span><span class="w"> </span><span class="kt">bytes32</span><span class="w"> </span>t1<span class="p">)</span>

<span class="kd">hook</span><span class="w"> </span>LOG2<span class="p">(</span><span class="kt">uint</span><span class="w"> </span>offset<span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>length<span class="p">,</span><span class="w"> </span><span class="kt">bytes32</span><span class="w"> </span>t1<span class="p">,</span><span class="w"> </span><span class="kt">bytes32</span><span class="w"> </span>t2<span class="p">)</span>

<span class="kd">hook</span><span class="w"> </span>LOG3<span class="p">(</span><span class="kt">uint</span><span class="w"> </span>offset<span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>length<span class="p">,</span><span class="w"> </span><span class="kt">bytes32</span><span class="w"> </span>t1<span class="p">,</span><span class="w"> </span><span class="kt">bytes32</span><span class="w"> </span>t2<span class="p">,</span><span class="w"> </span><span class="kt">bytes32</span><span class="w"> </span>t3<span class="p">)</span>

<span class="kd">hook</span><span class="w"> </span>LOG4<span class="p">(</span><span class="kt">uint</span><span class="w"> </span>offset<span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>length<span class="p">,</span><span class="w"> </span><span class="kt">bytes32</span><span class="w"> </span>t1<span class="p">,</span><span class="w"> </span><span class="kt">bytes32</span><span class="w"> </span>t2<span class="p">,</span><span class="w"> </span><span class="kt">bytes32</span><span class="w"> </span>t3<span class="p">,</span><span class="w"> </span><span class="kt">bytes32</span><span class="w"> </span>t4<span class="p">)</span>

<span class="kd">hook</span><span class="w"> </span>CREATE1<span class="p">(</span><span class="kt">uint</span><span class="w"> </span>value<span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>offset<span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>length<span class="p">)</span><span class="w"> </span><span class="kt">address</span><span class="w"> </span>v

<span class="kd">hook</span><span class="w"> </span>CREATE2<span class="p">(</span><span class="kt">uint</span><span class="w"> </span>value<span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>offset<span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>length<span class="p">,</span><span class="w"> </span><span class="kt">bytes32</span><span class="w"> </span>salt<span class="p">)</span><span class="w"> </span><span class="kt">address</span><span class="w"> </span>v

<span class="kd">hook</span><span class="w"> </span>CALL<span class="p">(</span><span class="kt">uint</span><span class="w"> </span>g<span class="p">,</span><span class="w"> </span><span class="kt">address</span><span class="w"> </span>addr<span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>value<span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>argsOffset<span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>argsLength<span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>retOffset<span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>retLength<span class="p">)</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>rc

<span class="kd">hook</span><span class="w"> </span>CALLCODE<span class="p">(</span><span class="kt">uint</span><span class="w"> </span>g<span class="p">,</span><span class="w"> </span><span class="kt">address</span><span class="w"> </span>addr<span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>value<span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>argsOffset<span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>argsLength<span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>retOffset<span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>retLength<span class="p">)</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>rc

<span class="kd">hook</span><span class="w"> </span>DELEGATECALL<span class="p">(</span><span class="kt">uint</span><span class="w"> </span>g<span class="p">,</span><span class="w"> </span><span class="kt">address</span><span class="w"> </span>addr<span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>argsOffset<span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>argsLength<span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>retOffset<span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>retLength<span class="p">)</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>rc

<span class="kd">hook</span><span class="w"> </span>STATICCALL<span class="p">(</span><span class="kt">uint</span><span class="w"> </span>g<span class="p">,</span><span class="w"> </span><span class="kt">address</span><span class="w"> </span>addr<span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>argsOffset<span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>argsLength<span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>retOffset<span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>retLength<span class="p">)</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>rc

<span class="kd">hook</span><span class="w"> </span>REVERT<span class="p">(</span><span class="kt">uint</span><span class="w"> </span>offset<span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>size<span class="p">)</span>

<span class="kd">hook</span><span class="w"> </span>BLOBHASH<span class="p">(</span><span class="kt">uint</span><span class="w"> </span>n<span class="p">)</span><span class="w"> </span><span class="kt">bytes32</span><span class="w"> </span><span class="kt">hash</span>

<span class="kd">hook</span><span class="w"> </span>SELFDESTRUCT<span class="p">(</span><span class="kt">address</span><span class="w"> </span>a<span class="p">)</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell13">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<section id="call-hooks">
<span id="id4"></span><h3><a class="toc-backref" href="#id14" role="doc-backlink">Call hooks</a><a class="headerlink" href="#call-hooks" title="Link to this heading"></a></h3>
<p>We provide hooks for all four call opcodes: <a class="reference external" href="https://www.evm.codes/#f1"><code class="docutils literal notranslate"><span class="pre">CALL</span></code></a>,
<a class="reference external" href="https://www.evm.codes/#f2"><code class="docutils literal notranslate"><span class="pre">CALLCODE</span></code></a>, <a class="reference external" href="https://www.evm.codes/#f4"><code class="docutils literal notranslate"><span class="pre">DELEGATECALL</span></code></a>,
and <a class="reference external" href="https://www.evm.codes/#fa"><code class="docutils literal notranslate"><span class="pre">STATICCALL</span></code></a>.
The hook parameters match the stack inputs of the respective opcodes.</p>
<p>The arguments for the call arguments and return values (<code class="docutils literal notranslate"><span class="pre">argsOffset</span></code>, <code class="docutils literal notranslate"><span class="pre">argsSize</span></code>,
<code class="docutils literal notranslate"><span class="pre">retOffset</span></code>, and <code class="docutils literal notranslate"><span class="pre">retSize</span></code>) mostly exist for future use. Their values can be
consumed, but currently they cannot be used to read data stored in memory before
or after the call.</p>
<p>These hooks can be very useful to establish sensible security invariants.
As an example, suppose no external code should gain write access to the data of
the current contract. Both <code class="docutils literal notranslate"><span class="pre">CALLCODE</span></code> and <code class="docutils literal notranslate"><span class="pre">DELEGATECALL</span></code> have the potential to
do exactly that by calling into another contract but keeping the current context.
Note that there are exceptions to this property whenever <em>trusted</em> 3rd party
libraries are used. It might also be necessary to restrict these checks to the
contract of interest.</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell14"><span></span><span class="kd">hook</span><span class="w"> </span>CALLCODE<span class="p">(</span><span class="kt">uint</span><span class="w"> </span>g<span class="p">,</span><span class="w"> </span><span class="kt">address</span><span class="w"> </span>addr<span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>value<span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>argsOffset<span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>argsLength<span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>retOffset<span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>retLength<span class="p">)</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>rc<span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="c1">// using CALLCODE is generally not expected in this contract</span>
<span class="w">    </span><span class="kr">assert</span><span class="w"> </span><span class="p">(</span>executingContract<span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="nb">currentContract</span><span class="p">,</span><span class="w"> </span><span class="s2">"we should not use `callcode`"</span><span class="p">);</span>
<span class="p">}</span>
<span class="kd">hook</span><span class="w"> </span>DELEGATECALL<span class="p">(</span><span class="kt">uint</span><span class="w"> </span>g<span class="p">,</span><span class="w"> </span><span class="kt">address</span><span class="w"> </span>addr<span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>argsOffset<span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>argsLength<span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>retOffset<span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>retLength<span class="p">)</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>rc<span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="c1">// DELEGATECALL is used in this contract, but it only ever calls into itself</span>
<span class="w">    </span><span class="kr">assert</span><span class="w"> </span><span class="p">(</span>executingContract<span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="nb">currentContract</span><span class="w"> </span><span class="o">||</span><span class="w"> </span>addr<span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="nb">currentContract</span><span class="p">,</span>
<span class="w">        </span><span class="s2">"we should only `delegatecall` into ourselves"</span>
<span class="w">    </span><span class="p">);</span>
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
</section>
<section id="known-inter-dependencies-and-common-pitfalls">
<h3><a class="toc-backref" href="#id15" role="doc-backlink">Known inter-dependencies and common pitfalls</a><a class="headerlink" href="#known-inter-dependencies-and-common-pitfalls" title="Link to this heading"></a></h3>
<p>Hooks are instrumented for every appearance of the matching instruction in the
bytecode, as generated by a high-level source compiler such as the Solidity
compiler.  The behavior of the bytecode may sometimes be surprising.  For
example, every Solidity method call to a non-payable function will contain an
early call to <code class="docutils literal notranslate"><span class="pre">CALLVALUE</span></code> to check that it is 0. This means that every time a
non-payable Solidity function is invoked, the <code class="docutils literal notranslate"><span class="pre">CALLVALUE</span></code> hook will be
triggered.</p>
</section>
</section>
<section id="hook-bodies">
<span id="executingcontract"></span><h2><a class="toc-backref" href="#id16" role="doc-backlink">Hook bodies</a><a class="headerlink" href="#hook-bodies" title="Link to this heading"></a></h2>
<p>The body of a hook may contain almost any CVL code, including calls to other
Solidity functions.  The only exception is that hooks may not contain
parametric method calls.  Expressions in hook bodies may reference variables
bound by the hook pattern.</p>
<section id="keywords-available-in-hook-bodies">
<h3><a class="toc-backref" href="#id17" role="doc-backlink">Keywords available in hook bodies</a><a class="headerlink" href="#keywords-available-in-hook-bodies" title="Link to this heading"></a></h3>
<p>Hook bodies may refer to the special CVL variable <code class="docutils literal notranslate"><span class="pre">executingContract</span></code>,
which contains the address of the contract whose code triggered the hook.</p>
<p>The call opcodes (<code class="docutils literal notranslate"><span class="pre">CALL</span></code>, <code class="docutils literal notranslate"><span class="pre">CALLCODE</span></code>, <code class="docutils literal notranslate"><span class="pre">STATICCALL</span></code> and <code class="docutils literal notranslate"><span class="pre">DELEGATECALL</span></code>) may also
refer to a special CVL variable <code class="docutils literal notranslate"><span class="pre">selector</span></code>, which can be used to compare
to a specific method signature selector.
For example, here the hook body will assert that the native token value passed in the call is 0, only for a <code class="docutils literal notranslate"><span class="pre">transfer(address,uint)</span></code> call:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell15"><span></span><span class="kd">hook</span><span class="w"> </span>CALL<span class="p">(</span><span class="kt">uint</span><span class="w"> </span>g<span class="p">,</span><span class="w"> </span><span class="kt">address</span><span class="w"> </span>addr<span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>value<span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>argsOffs<span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>argLength<span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>retOffset<span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>retLength<span class="p">)</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>rc<span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kr">if</span><span class="p">(</span><span class="nb">selector</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="kd">sig</span><span class="o">:</span><span class="nf">transfer</span><span class="p">(</span><span class="kt">address</span><span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="p">).</span><span class="nb">selector</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">      </span><span class="kr">assert</span><span class="w"> </span>value<span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">;</span>
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
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>In case the size of the input to the call is less than 4 bytes,
the value of <code class="docutils literal notranslate"><span class="pre">selector</span></code> is 0.
This can be checked by comparing the <code class="docutils literal notranslate"><span class="pre">argLength</span></code> argument of the hook to 4.</p>
</div>
</section>
<section id="reentrant-hooks">
<h3><a class="toc-backref" href="#id18" role="doc-backlink">Reentrant hooks</a><a class="headerlink" href="#reentrant-hooks" title="Link to this heading"></a></h3>
<p>While a hook is executing, additional hooks are skipped.  If
a hook calls a contract function which would normally cause another hook to
execute, the inner hook will not execute.</p>
<p>For example, suppose the contract function <code class="docutils literal notranslate"><span class="pre">updateX()</span></code> always assigned to the
value <code class="docutils literal notranslate"><span class="pre">x</span></code>, and consider the following hook (see
<a class="reference external" href="https://github.com/Certora/Examples/tree/28cb774fc03767e8aeaf00ea1bb0fac7db595fc9/ReferenceManual/HookReentrancy"><code class="docutils literal notranslate"><span class="pre">HookReentrancy.spec</span></code> here</a> for the complete example):</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell16"><span></span><span class="linenos"> 1</span><span class="c1">/// the number of stores to `x`</span>
<span class="linenos"> 2</span><span class="kd">ghost</span><span class="w"> </span><span class="kt">mathint</span><span class="w"> </span>xStoreCount<span class="p">;</span>
<span class="linenos"> 3</span>
<span class="linenos"> 4</span><span class="c1">/// increment xStoreCount and recursively update `x`</span>
<span class="linenos"> 5</span><span class="kd">hook</span><span class="w"> </span><span class="kp">Sstore</span><span class="w"> </span>x<span class="w"> </span><span class="kt">uint</span><span class="w"> </span>v<span class="w"> </span><span class="p">{</span>
<span class="linenos"> 6</span><span class="w">    </span>xStoreCount<span class="w"> </span><span class="o">=</span><span class="w"> </span>xStoreCount<span class="w"> </span><span class="o">+</span><span class="w"> </span><span class="m m-Decimal">1</span><span class="p">;</span>
<span class="linenos"> 7</span><span class="w">    </span><span class="kr">if</span><span class="w"> </span><span class="p">(</span>xStoreCount<span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="m m-Decimal">5</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="linenos"> 8</span><span class="w">        </span>updateX<span class="p">();</span>
<span class="linenos"> 9</span><span class="w">    </span><span class="p">}</span>
<span class="linenos">10</span><span class="p">}</span>
<span class="linenos">11</span>
<span class="linenos">12</span><span class="c1">/// This rule will pass because hooks are not recursively applied</span>
<span class="linenos">13</span><span class="k">rule</span><span class="w"> </span><span class="nc">checkStoreCount</span><span class="w"> </span><span class="p">{</span>
<span class="linenos">14</span><span class="w">    </span><span class="kr">require</span><span class="w"> </span>xStoreCount<span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">;</span>
<span class="linenos">15</span><span class="w">    </span>updateX<span class="p">();</span>
<span class="linenos">16</span><span class="w">    </span><span class="kr">assert</span><span class="w"> </span>xStoreCount<span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="m m-Decimal">1</span><span class="p">;</span>
<span class="linenos">17</span><span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell16">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>In this example, the rule <code class="docutils literal notranslate"><span class="pre">checkStoreCount</span></code> calls <code class="docutils literal notranslate"><span class="pre">updateX</span></code> on line 15, which
updates <code class="docutils literal notranslate"><span class="pre">x</span></code>, triggering the hook on line 5.  The hook then calls <code class="docutils literal notranslate"><span class="pre">updateX</span></code>
again on line 8.  The recursive call to <code class="docutils literal notranslate"><span class="pre">updateX</span></code> will then update <code class="docutils literal notranslate"><span class="pre">x</span></code> a second
time.</p>
<p>At this point, you may expect that the hook will be triggered a second time,
but because there is already a hook executing, this second update to <code class="docutils literal notranslate"><span class="pre">x</span></code> will
not trigger the hook.  Therefore the <code class="docutils literal notranslate"><span class="pre">xStoreCount</span></code> ghost will <em>not</em> be updated
a second time, so its final value will be <code class="docutils literal notranslate"><span class="pre">1</span></code>.</p>
<hr class="footnotes docutils">
<aside class="footnote-list brackets">
<aside class="footnote brackets" id="before-hooks" role="doc-footnote">
<span class="label"><span class="fn-bracket">[</span><a role="doc-backlink" href="#id3">1</a><span class="fn-bracket">]</span></span>
<p>For halting instructions such as <code class="docutils literal notranslate"><span class="pre">REVERT</span></code> and <code class="docutils literal notranslate"><span class="pre">SELFDESTRUCT</span></code>,
the hook is executed before the instruction instead of after.</p>
</aside>
</aside>
</section>
</section>
</section>


           </div>
          </div>
          <footer><div class="rst-footer-buttons" role="navigation" aria-label="Footer">
        <a href="defs.html" class="btn btn-neutral float-left" title="Definitions" accesskey="p" rel="prev"><span class="fa fa-arrow-circle-left" aria-hidden="true"></span> Previous</a>
        <a href="transient.html" class="btn btn-neutral float-right" title="Transient Storage" accesskey="n" rel="next">Next <span class="fa fa-arrow-circle-right" aria-hidden="true"></span></a>
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