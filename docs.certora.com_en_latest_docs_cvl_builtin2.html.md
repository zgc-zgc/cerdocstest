<!DOCTYPE html><html class="writer-html5" lang="en" data-content_root="../../"><head>
  <meta charset="utf-8"><meta name="viewport" content="width=device-width, initial-scale=1">

  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Built-in Rules — Certora Prover Documentation 0.0 documentation</title>
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
    <link rel="next" title="Functions" href="functions.html">
    <link rel="prev" title="Rules" href="rules.html"> 
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
<li class="toctree-l2"><a class="reference internal" href="methods.html">The Methods Block</a></li>
<li class="toctree-l2"><a class="reference internal" href="rules.html">Rules</a></li>
<li class="toctree-l2 current" aria-expanded="true"><a class="reference internal current" href="#" aria-expanded="true"><button class="toctree-expand" title="Open/close menu"></button>Built-in Rules</a><ul>
<li class="toctree-l3"><a class="reference internal" href="#syntax">Syntax</a></li>
<li class="toctree-l3"><a class="reference internal" href="#bad-loop-detection-msgvalueinlooprule">Bad loop detection — <code class="docutils literal notranslate"><span class="pre">msgValueInLoopRule</span></code></a></li>
<li class="toctree-l3"><a class="reference internal" href="#delegate-call-detection-hasdelegatecalls">Delegate call detection — <code class="docutils literal notranslate"><span class="pre">hasDelegateCalls</span></code></a></li>
<li class="toctree-l3"><a class="reference internal" href="#basic-setup-checks-sanity"><button class="toctree-expand" title="Open/close menu"></button>Basic setup checks — <code class="docutils literal notranslate"><span class="pre">sanity</span></code></a><ul>
<li class="toctree-l4"><a class="reference internal" href="#how-sanity-is-checked">How <code class="docutils literal notranslate"><span class="pre">sanity</span></code> is checked</a></li>
</ul>
</li>
<li class="toctree-l3"><a class="reference internal" href="#thorough-complexity-checks-deepsanity"><button class="toctree-expand" title="Open/close menu"></button>Thorough complexity checks — <code class="docutils literal notranslate"><span class="pre">deepSanity</span></code></a><ul>
<li class="toctree-l4"><a class="reference internal" href="#how-deepsanity-is-checked">How <code class="docutils literal notranslate"><span class="pre">deepSanity</span></code> is checked</a></li>
</ul>
</li>
<li class="toctree-l3"><a class="reference internal" href="#read-only-reentrancy-detection-viewreentrancy"><button class="toctree-expand" title="Open/close menu"></button>Read-only reentrancy detection — <code class="docutils literal notranslate"><span class="pre">viewReentrancy</span></code></a><ul>
<li class="toctree-l4"><a class="reference internal" href="#how-viewreentrancy-is-checked">How <code class="docutils literal notranslate"><span class="pre">viewReentrancy</span></code> is checked</a></li>
</ul>
</li>
</ul>
</li>
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
      <li class="breadcrumb-item active">Built-in Rules</li>
      <li class="wy-breadcrumbs-aside">
            <a href="../../_sources/docs/cvl/builtin.md.txt" rel="nofollow"> View page source</a>
      </li>
  </ul>
  <hr>
</div>
          <div role="main" class="document" itemscope="itemscope" itemtype="http://schema.org/Article">
           <div itemprop="articleBody">
             
  <section id="built-in-rules">
<span id="built-in"></span><h1><a class="toc-backref" href="#id1" role="doc-backlink">Built-in Rules</a><a class="headerlink" href="#built-in-rules" title="Link to this heading"></a></h1>
<p>The Certora Prover has built-in general-purpose rules targeted at finding common
vulnerabilities.  These rules can be verified on a contract without writing any
contract-specific rules.</p>
<p>Built-in rules can be included in any spec file by writing <code class="docutils literal notranslate"><span class="pre">use</span> <span class="pre">builtin</span> <span class="pre">rule</span> <span class="pre">&lt;rule-name&gt;;</span></code>.  This document describes the available built-in rules.</p>
<nav class="contents" id="contents">
<p class="topic-title">Contents</p>
<ul class="simple">
<li><p><a class="reference internal" href="#built-in-rules" id="id1">Built-in Rules</a></p>
<ul>
<li><p><a class="reference internal" href="#syntax" id="id2">Syntax</a></p></li>
<li><p><a class="reference internal" href="#bad-loop-detection-msgvalueinlooprule" id="id3">Bad loop detection — <code class="docutils literal notranslate"><span class="pre">msgValueInLoopRule</span></code></a></p></li>
<li><p><a class="reference internal" href="#delegate-call-detection-hasdelegatecalls" id="id4">Delegate call detection — <code class="docutils literal notranslate"><span class="pre">hasDelegateCalls</span></code></a></p></li>
<li><p><a class="reference internal" href="#basic-setup-checks-sanity" id="id5">Basic setup checks — <code class="docutils literal notranslate"><span class="pre">sanity</span></code></a></p>
<ul>
<li><p><a class="reference internal" href="#how-sanity-is-checked" id="id6">How <code class="docutils literal notranslate"><span class="pre">sanity</span></code> is checked</a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#thorough-complexity-checks-deepsanity" id="id7">Thorough complexity checks — <code class="docutils literal notranslate"><span class="pre">deepSanity</span></code></a></p>
<ul>
<li><p><a class="reference internal" href="#how-deepsanity-is-checked" id="id8">How <code class="docutils literal notranslate"><span class="pre">deepSanity</span></code> is checked</a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#read-only-reentrancy-detection-viewreentrancy" id="id9">Read-only reentrancy detection — <code class="docutils literal notranslate"><span class="pre">viewReentrancy</span></code></a></p>
<ul>
<li><p><a class="reference internal" href="#how-viewreentrancy-is-checked" id="id10">How <code class="docutils literal notranslate"><span class="pre">viewReentrancy</span></code> is checked</a></p></li>
</ul>
</li>
</ul>
</li>
</ul>
</nav>
<section id="syntax">
<h2><a class="toc-backref" href="#id2" role="doc-backlink">Syntax</a><a class="headerlink" href="#syntax" title="Link to this heading"></a></h2>
<p>The syntax for rules is given by the following <a class="reference internal" href="overview.html#ebnf-syntax"><span class="std std-ref">EBNF grammar</span></a>:</p>
<div class="highlight-default notranslate"><div class="highlight"><pre id="codecell0"><span></span><span class="n">built_in_rule</span> <span class="p">:</span><span class="o">:=</span> <span class="s2">"use"</span> <span class="s2">"builtin"</span> <span class="s2">"rule"</span> <span class="n">built_in_rule_name</span> <span class="s2">";"</span>

<span class="n">built_in_rule_name</span> <span class="p">:</span><span class="o">:=</span>
    <span class="o">|</span> <span class="s2">"msgValueInLoopRule"</span>
    <span class="o">|</span> <span class="s2">"hasDelegateCalls"</span>
    <span class="o">|</span> <span class="s2">"sanity"</span>
    <span class="o">|</span> <span class="s2">"deepSanity"</span>
    <span class="o">|</span> <span class="s2">"viewReentrancy"</span>
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
<section id="bad-loop-detection-msgvalueinlooprule">
<span id="built-in-msg-value-in-loop"></span><h2><a class="toc-backref" href="#id3" role="doc-backlink">Bad loop detection — <code class="docutils literal notranslate"><span class="pre">msgValueInLoopRule</span></code></a><a class="headerlink" href="#bad-loop-detection-msgvalueinlooprule" title="Link to this heading"></a></h2>
<p>Loops that <a class="reference external" href="https://trustchain.medium.com/ethereum-msg-value-reuse-vulnerability-5afd0aa2bcef">use <code class="docutils literal notranslate"><span class="pre">msg.value</span></code> or make delegate
calls</a> are a well-known source of security
vulnerabilities.</p>
<p>The <code class="docutils literal notranslate"><span class="pre">msgValueInLoopRule</span></code> detects these anti-patterns.  It can be enabled by
including</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell1"><span></span><span class="kn">use</span><span class="w"> </span><span class="kr">builtin</span><span class="w"> </span><span class="k">rule</span><span class="w"> </span><span class="nc">msgValueInLoopRule</span><span class="p">;</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell1">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>in a spec file.  The rule will fail on any functions that can make delegate
calls or access <code class="docutils literal notranslate"><span class="pre">msg.value</span></code> inside a loop. This includes any functions that recursively call any functions that has
this vulnerability.</p>
</section>
<section id="delegate-call-detection-hasdelegatecalls">
<span id="built-in-has-delegate-calls"></span><h2><a class="toc-backref" href="#id4" role="doc-backlink">Delegate call detection — <code class="docutils literal notranslate"><span class="pre">hasDelegateCalls</span></code></a><a class="headerlink" href="#delegate-call-detection-hasdelegatecalls" title="Link to this heading"></a></h2>
<p>The <code class="docutils literal notranslate"><span class="pre">hasDelegateCalls</span></code> built-in rule is a handy way to find delegate calls in
a contract. <a class="reference external" href="https://blog.solidityscan.com/security-issues-with-delegate-calls-4ae64d775b76">Contracts that use delegate calls</a> require proper security checking.</p>
<p>The <code class="docutils literal notranslate"><span class="pre">hasDelegateCalls</span></code> can be enabled by including</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell2"><span></span><span class="kn">use</span><span class="w"> </span><span class="kr">builtin</span><span class="w"> </span><span class="k">rule</span><span class="w"> </span><span class="nc">hasDelegateCalls</span><span class="p">;</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell2">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>in a spec file.  Any functions that can make delegate calls will fail the
<code class="docutils literal notranslate"><span class="pre">hasDelegateCalls</span></code> rule.</p>
</section>
<section id="basic-setup-checks-sanity">
<span id="built-in-sanity"></span><h2><a class="toc-backref" href="#id5" role="doc-backlink">Basic setup checks — <code class="docutils literal notranslate"><span class="pre">sanity</span></code></a><a class="headerlink" href="#basic-setup-checks-sanity" title="Link to this heading"></a></h2>
<p>The <code class="docutils literal notranslate"><span class="pre">sanity</span></code> rule checks that there is at least one non-reverting path through
each contract function.  It can be enabled by including</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell3"><span></span><span class="kn">use</span><span class="w"> </span><span class="kr">builtin</span><span class="w"> </span><span class="k">rule</span><span class="w"> </span><span class="nc">sanity</span><span class="p">;</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell3">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>in a spec file.</p>
<p>The sanity rule is useful for two reasons:</p>
<ul class="simple">
<li><p>It is an easy way to determine which contract functions take a long time to
analyze.  If a method takes a long time to verify the <code class="docutils literal notranslate"><span class="pre">sanity</span></code> rule (or
times out), it will almost certainly time out while verifying interesting
properties.  This can help you quickly discover which methods may need
<a class="reference internal" href="../user-guide/glossary.html#term-summary"><span class="xref std std-term">summarization</span></a>.</p></li>
<li><p>A method the fails the <code class="docutils literal notranslate"><span class="pre">sanity</span></code> rule will revert on every input; every rule
that calls the method will therefore be <a class="reference internal" href="../user-guide/glossary.html#term-vacuity"><span class="xref std std-term">vacuous</span></a>.  This
probably indicates a problem with the Prover configuration; the most likely
cause is <a class="reference internal" href="../prover/approx/loops.html#unrolling"><span class="std std-ref">loop unrolling</span></a>.</p></li>
</ul>
<p>We recommend running the sanity rule at the beginning of a project to
ensure that the Prover’s configuration is reasonable.</p>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>The <code class="docutils literal notranslate"><span class="pre">sanity</span></code> built-in rule is unrelated to the <a class="reference internal" href="../prover/cli/options.html#rule-sanity"><span class="std std-ref">rule_sanity</span></a> option;
the built-in rule is used to check the basic setup, while <code class="docutils literal notranslate"><span class="pre">--rule_sanity</span></code> checks
individual rules.</p>
</div>
<section id="how-sanity-is-checked">
<h3><a class="toc-backref" href="#id6" role="doc-backlink">How <code class="docutils literal notranslate"><span class="pre">sanity</span></code> is checked</a><a class="headerlink" href="#how-sanity-is-checked" title="Link to this heading"></a></h3>
<p>The <code class="docutils literal notranslate"><span class="pre">sanity</span></code> rule is translated into the following <a class="reference internal" href="../user-guide/glossary.html#term-parametric-rule"><span class="xref std std-term">parametric rule</span></a>:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell4"><span></span><span class="k">rule</span><span class="w"> </span><span class="nc">sanity</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kt">method</span><span class="w"> </span>f<span class="p">;</span><span class="w"> </span><span class="kt">env</span><span class="w"> </span>e<span class="p">;</span>
<span class="w">    </span><span class="kt">calldataarg</span><span class="w"> </span>arg<span class="p">;</span>
<span class="w">    </span>f<span class="p">(</span>e<span class="p">,</span><span class="w"> </span>arg<span class="p">);</span><span class="w"> </span>
<span class="w">    </span><span class="kr">assert</span><span class="w"> </span><span class="kr">true</span><span class="p">;</span>
<span class="w">    </span><span class="kr">satisfy</span><span class="w"> </span><span class="kr">true</span><span class="p">;</span>
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
<p>This will create two sub-rules, which will be visible in the report. One
sub-rule checks the <code class="docutils literal notranslate"><span class="pre">satisfy</span> <span class="pre">true</span></code> statement, which is fulfilled if there is an
input such that <code class="docutils literal notranslate"><span class="pre">f(e,</span> <span class="pre">arg)</span></code> runs to completion without reverting. The other
sub-rule checks the <code class="docutils literal notranslate"><span class="pre">assert</span> <span class="pre">true</span></code> statement. Of course, this assertion itself is
never violated, but the sub-rule contains the <a class="reference internal" href="../user-guide/glossary.html#term-pessimistic-assertions"><span class="xref std std-term">pessimistic assertions</span></a> that
we insert when at least one of the “optimistic” flags (e.g.
<a class="reference internal" href="../prover/cli/options.html#optimistic-loop"><span class="std std-ref">optimistic_loop</span></a>, <a class="reference internal" href="../prover/cli/options.html#optimistic-hashing"><span class="std std-ref">optimistic_hashing</span></a>, etc.) is not active. Note
that rules with only <a class="reference internal" href="statements.html#satisfy"><span class="std std-ref">satisfy statements</span></a> do not check these assertions.</p>
</section>
</section>
<section id="thorough-complexity-checks-deepsanity">
<span id="built-in-deep-sanity"></span><h2><a class="toc-backref" href="#id7" role="doc-backlink">Thorough complexity checks — <code class="docutils literal notranslate"><span class="pre">deepSanity</span></code></a><a class="headerlink" href="#thorough-complexity-checks-deepsanity" title="Link to this heading"></a></h2>
<p>The basic sanity rule only tries to find a <em>single</em> input that causes each
function to execute without reverting.  While this check can quickly identify
problems with the Prover setup, a successful <code class="docutils literal notranslate"><span class="pre">sanity</span></code> run does not guarantee
that the contract methods won’t cause Prover timeouts, or that all of the
contract code is reachable.</p>
<p>For example, consider the following method:</p>
<div class="highlight-solidity notranslate"><div class="highlight"><pre id="codecell5"><span></span><span class="kt">function</span><span class="w"> </span><span class="nv">veryComplexFunction</span><span class="p">()</span><span class="w"> </span><span class="kt">returns</span><span class="p">(</span><span class="kt">uint</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kt">uint</span><span class="w"> </span><span class="nv">x</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">;</span>
<span class="w">    </span><span class="kt">for</span><span class="w"> </span><span class="p">(</span><span class="kt">uint</span><span class="w"> </span><span class="nv">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="w"> </span><span class="p">;</span><span class="w"> </span>i<span class="w"> </span><span class="o">&lt;</span><span class="w"> </span>array<span class="p">.</span>len<span class="p">;</span><span class="w"> </span>i<span class="o">++</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">        </span>x<span class="w"> </span><span class="o">=</span><span class="w"> </span>x<span class="w"> </span><span class="o">+</span><span class="w"> </span>complexComputation<span class="p">(</span>i<span class="p">);</span>
<span class="w">    </span><span class="p">}</span>
<span class="w">    </span><span class="kt">return</span><span class="w"> </span>x<span class="p">;</span>
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
<p>There is clearly a simple non-reverting path through the code: it will
immediately return if <code class="docutils literal notranslate"><span class="pre">array.len</span></code> is <code class="docutils literal notranslate"><span class="pre">0</span></code>; the basic <code class="docutils literal notranslate"><span class="pre">sanity</span></code> can quickly find a
<a class="reference internal" href="../user-guide/glossary.html#term-model"><span class="xref std std-term">model</span></a> like this without even considering the implementation of
<code class="docutils literal notranslate"><span class="pre">complexComputation</span></code>, so the <code class="docutils literal notranslate"><span class="pre">sanity</span></code> rule will succeed.  However, verifying
any property that depends on the return value of <code class="docutils literal notranslate"><span class="pre">veryComplexFunction</span></code> will
require the Prover to reason about <code class="docutils literal notranslate"><span class="pre">complexComputation()</span></code>, which may cause
timeouts.  Moreover, portions of <code class="docutils literal notranslate"><span class="pre">complexComputation</span></code> may be unreachable, and
this will not be caught by the basic <code class="docutils literal notranslate"><span class="pre">sanity</span></code> rule.</p>
<p>The <code class="docutils literal notranslate"><span class="pre">deepSanity</span></code> rule generalizes the basic <code class="docutils literal notranslate"><span class="pre">sanity</span></code> rule by heuristically
choosing interesting statements in the contract code and ensuring that there
are non-reverting <a class="reference internal" href="../user-guide/glossary.html#term-model"><span class="xref std std-term">models</span></a> that execute those statements.  In the above
example, one of the paths chosen by <code class="docutils literal notranslate"><span class="pre">deepSanity</span></code> would go through the body of
the <code class="docutils literal notranslate"><span class="pre">for</span></code> loop, forcing the Prover to find a non-reverting path through the
<code class="docutils literal notranslate"><span class="pre">complexComputation</span></code> method.</p>
<p>The <code class="docutils literal notranslate"><span class="pre">deepSanity</span></code> rule heuristic favors the following program points:</p>
<ol class="arabic simple">
<li><p>The “if” and “else” branches of a code-heavy <code class="docutils literal notranslate"><span class="pre">if</span></code> statement</p></li>
<li><p>The beginning of an external call</p></li>
<li><p>The beginning of the program (this is the same as the usual sanity rule)</p></li>
</ol>
<p>The <code class="docutils literal notranslate"><span class="pre">deepSanity</span></code> rule can be enabled by including</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell6"><span></span><span class="kn">use</span><span class="w"> </span><span class="kr">builtin</span><span class="w"> </span><span class="k">rule</span><span class="w"> </span><span class="nc">deepSanity</span><span class="p">;</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell6">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>in a spec file.  You must also pass the <a class="reference internal" href="../prover/cli/options.html#multi-assert-check"><span class="std std-ref">multi_assert_check</span></a> flag to
the Prover.</p>
<p>The number of code points that are chosen can be configured with the
<a class="reference internal" href="../prover/cli/options.html#maxnumberofreachchecksbasedondomination"><span class="std std-ref">maxNumberOfReachChecksBasedOnDomination</span></a> flag; the default value is
<code class="docutils literal notranslate"><span class="pre">10</span></code>.</p>
<section id="how-deepsanity-is-checked">
<h3><a class="toc-backref" href="#id8" role="doc-backlink">How <code class="docutils literal notranslate"><span class="pre">deepSanity</span></code> is checked</a><a class="headerlink" href="#how-deepsanity-is-checked" title="Link to this heading"></a></h3>
<p>The <code class="docutils literal notranslate"><span class="pre">deepSanity</span></code> rule works similarly to the <code class="docutils literal notranslate"><span class="pre">sanity</span></code> rule; it adds an
additional variable <code class="docutils literal notranslate"><span class="pre">x_p</span></code> for each interesting program point <code class="docutils literal notranslate"><span class="pre">p</span></code>, and
instruments the contract code at <code class="docutils literal notranslate"><span class="pre">p</span></code> to set <code class="docutils literal notranslate"><span class="pre">x_p</span></code> to <code class="docutils literal notranslate"><span class="pre">true</span></code>.  The Prover then
tries to prove that <code class="docutils literal notranslate"><span class="pre">x_p</span></code> is false after executing the function.  To find a
counterexample; the Prover must construct a model that passes through <code class="docutils literal notranslate"><span class="pre">p</span></code>.</p>
</section>
</section>
<section id="read-only-reentrancy-detection-viewreentrancy">
<span id="built-in-view-reentrancy"></span><h2><a class="toc-backref" href="#id9" role="doc-backlink">Read-only reentrancy detection — <code class="docutils literal notranslate"><span class="pre">viewReentrancy</span></code></a><a class="headerlink" href="#read-only-reentrancy-detection-viewreentrancy" title="Link to this heading"></a></h2>
<p>The <code class="docutils literal notranslate"><span class="pre">viewReentrancy</span></code>  built-in rule detects
<a class="reference external" href="https://blog.pessimistic.io/read-only-reentrancy-in-depth-6ea7e9d78e85">read-only reentrancy vulnerabilities in a contract</a>.</p>
<p>The <code class="docutils literal notranslate"><span class="pre">viewReentrancy</span></code> rule can be enabled by including</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell7"><span></span><span class="kn">use</span><span class="w"> </span><span class="kr">builtin</span><span class="w"> </span><span class="k">rule</span><span class="w"> </span><span class="nc">viewReentrancy</span><span class="p">;</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell7">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>in a spec file.  Any functions that have read-only reentrancy will fail the
<code class="docutils literal notranslate"><span class="pre">viewReentrancy</span></code> rule.</p>
<section id="how-viewreentrancy-is-checked">
<h3><a class="toc-backref" href="#id10" role="doc-backlink">How <code class="docutils literal notranslate"><span class="pre">viewReentrancy</span></code> is checked</a><a class="headerlink" href="#how-viewreentrancy-is-checked" title="Link to this heading"></a></h3>
<p>Reentrancy vulnerabilities can arise when a contract makes an external call with an inconsistent internal
state. This behavior allows the receiver contract to make reentrant calls that exploit the inconsistency.</p>
<p>The <code class="docutils literal notranslate"><span class="pre">viewReentrancy</span></code> rule ensures that whenever a method <code class="docutils literal notranslate"><span class="pre">f</span></code> of <a class="reference internal" href="expr.html#currentcontract"><span class="std std-ref">currentContract</span></a> makes an external call,
the internal state of <code class="docutils literal notranslate"><span class="pre">currentContract</span></code> is equivalent to either (1) the state of <code class="docutils literal notranslate"><span class="pre">currentContract</span></code> at the beginning of the calling function,
or (2) the state of <code class="docutils literal notranslate"><span class="pre">currentContract</span></code> at the end of the calling function (by “equivalent”,
we mean that all view functions return the same values).
This ensures that the external call cannot observe <code class="docutils literal notranslate"><span class="pre">currentContract</span></code> in any state that it couldn’t have without being
called from <code class="docutils literal notranslate"><span class="pre">currentContract</span></code>.</p>
</section>
</section>
</section>


           </div>
          </div>
          <footer><div class="rst-footer-buttons" role="navigation" aria-label="Footer">
        <a href="rules.html" class="btn btn-neutral float-left" title="Rules" accesskey="p" rel="prev"><span class="fa fa-arrow-circle-left" aria-hidden="true"></span> Previous</a>
        <a href="functions.html" class="btn btn-neutral float-right" title="Functions" accesskey="n" rel="next">Next <span class="fa fa-arrow-circle-right" aria-hidden="true"></span></a>
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