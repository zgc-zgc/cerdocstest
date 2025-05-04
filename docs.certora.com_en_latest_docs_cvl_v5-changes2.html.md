<!DOCTYPE html><html class="writer-html5" lang="en" data-content_root="../../"><head>
  <meta charset="utf-8"><meta name="viewport" content="width=device-width, initial-scale=1">

  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Certora CLI 5.0 Changes — Certora Prover Documentation 0.0 documentation</title>
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
    <link rel="next" title="The Certora Prover" href="../prover/index.html">
    <link rel="prev" title="CVL2 Migration Guide" href="cvl2/migration.html"> 
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
<li class="toctree-l2"><a class="reference internal" href="hooks.html">Hooks</a></li>
<li class="toctree-l2"><a class="reference internal" href="transient.html">Transient Storage</a></li>
<li class="toctree-l2"><a class="reference internal" href="foundry-integration.html">Foundry Integration (Alpha)</a></li>
<li class="toctree-l2 current" aria-expanded="true"><a class="reference internal" href="index.html#changes-since-cvl-1"><button class="toctree-expand" title="Open/close menu"></button>Changes Since CVL 1</a><ul class="" aria-expanded="false">
<li class="toctree-l3"><a class="reference internal" href="cvl2/changes.html">Changes Introduced in CVL 2</a></li>
<li class="toctree-l3"><a class="reference internal" href="cvl2/migration.html">CVL2 Migration Guide</a></li>
<li class="toctree-l3 current" aria-expanded="true"><a class="reference internal current" href="#" aria-expanded="true"><button class="toctree-expand" title="Open/close menu"></button>Certora CLI 5.0 Changes</a><ul>
<li class="toctree-l4"><a class="reference internal" href="#exhaustive-parametric-rules">Exhaustive parametric rules</a></li>
<li class="toctree-l4"><a class="reference internal" href="#disallow-calls-to-contract-functions-in-quantified-expressions">Disallow calls to contract functions in quantified expressions</a></li>
<li class="toctree-l4"><a class="reference internal" href="#method-variable-restrictions">Method variable restrictions</a></li>
<li class="toctree-l4"><a class="reference internal" href="#new-delete-summary-syntax">New <code class="docutils literal notranslate"><span class="pre">DELETE</span></code> summary syntax</a></li>
<li class="toctree-l4"><a class="reference internal" href="#cli-changes-new-parametric-contracts-attribute">CLI changes: New Parametric Contracts Attribute</a></li>
<li class="toctree-l4"><a class="reference internal" href="#cli-changes-end-of-cvl1-deprecation-period">CLI changes: End of CVL1 Deprecation period</a></li>
</ul>
</li>
</ul>
</li>
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
      <li class="breadcrumb-item active">Certora CLI 5.0 Changes</li>
      <li class="wy-breadcrumbs-aside">
            <a href="../../_sources/docs/cvl/v5-changes.md.txt" rel="nofollow"> View page source</a>
      </li>
  </ul>
  <hr>
</div>
          <div role="main" class="document" itemscope="itemscope" itemtype="http://schema.org/Article">
           <div itemprop="articleBody">
             
  <section id="certora-cli-5-0-changes">
<h1><a class="toc-backref" href="#id3" role="doc-backlink">Certora CLI 5.0 Changes</a><a class="headerlink" href="#certora-cli-5-0-changes" title="Link to this heading"></a></h1>
<p>The release of <code class="docutils literal notranslate"><span class="pre">certora-cli</span></code> version 5.0 introduces a few small breaking
changes for CVL.  These changes improve the coverage for parametric rules and
invariants, disallow Solidity function calls in quantified expressions,
and simplify some rarely-used features.  This document explains those changes
and how to work with them.</p>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p><code class="docutils literal notranslate"><span class="pre">certora-cli</span></code> 5.0 also includes several new features, bug fixes, and
performance improvements that are not discussed here; see <a class="reference internal" href="../prover/changelog/prover_changelog.html#prover-release-notes"><span class="std std-ref">Prover Release Notes</span></a>
for more details.</p>
</div>
<nav class="contents" id="contents">
<p class="topic-title">Contents</p>
<ul class="simple">
<li><p><a class="reference internal" href="#certora-cli-5-0-changes" id="id3">Certora CLI 5.0 Changes</a></p>
<ul>
<li><p><a class="reference internal" href="#exhaustive-parametric-rules" id="id4">Exhaustive parametric rules</a></p>
<ul>
<li><p><a class="reference internal" href="#fixing-properties-that-should-hold" id="id5">Fixing properties that should hold</a></p></li>
<li><p><a class="reference internal" href="#filtering-properties-that-should-not-be-checked" id="id6">Filtering properties that should not be checked</a></p></li>
<li><p><a class="reference internal" href="#focusing-on-specific-contracts" id="id7">Focusing on specific contracts</a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#disallow-calls-to-contract-functions-in-quantified-expressions" id="id8">Disallow calls to contract functions in quantified expressions</a></p></li>
<li><p><a class="reference internal" href="#method-variable-restrictions" id="id9">Method variable restrictions</a></p></li>
<li><p><a class="reference internal" href="#new-delete-summary-syntax" id="id10">New <code class="docutils literal notranslate"><span class="pre">DELETE</span></code> summary syntax</a></p></li>
<li><p><a class="reference internal" href="#cli-changes-new-parametric-contracts-attribute" id="id11">CLI changes: New Parametric Contracts Attribute</a></p></li>
<li><p><a class="reference internal" href="#cli-changes-end-of-cvl1-deprecation-period" id="id12">CLI changes: End of CVL1 Deprecation period</a></p></li>
</ul>
</li>
</ul>
</nav>
<section id="exhaustive-parametric-rules">
<h2><a class="toc-backref" href="#id4" role="doc-backlink">Exhaustive parametric rules</a><a class="headerlink" href="#exhaustive-parametric-rules" title="Link to this heading"></a></h2>
<p>Starting with <code class="docutils literal notranslate"><span class="pre">certora-cli</span></code> version 5.0, <a class="reference internal" href="../user-guide/glossary.html#term-parametric-rule"><span class="xref std std-term">parametric rule</span></a>s and
<a class="reference internal" href="../user-guide/glossary.html#term-invariant"><span class="xref std std-term">invariant</span></a>s will now be checked on the methods of all contracts by
default, instead of just the primary contract.</p>
<p>This change improves the coverage of rules and can catch important errors.  For
example, an invariant that relates a contract’s total supply to its balance in
an underlying token contract could be invalidated by calling methods directly on
the underlying token; before this change those violations would not have been
detected.</p>
<p>This change can break existing specifications in a few ways:</p>
<ul class="simple">
<li><p>A property that should hold cannot be verified.</p></li>
<li><p>A parametric rule that was never intended to apply to secondary contracts
may be violated by methods of those contracts.</p></li>
<li><p>Verification may time out on methods of secondary contracts.</p></li>
</ul>
<p>The remainder of this section describes how to address these three failure
modes.</p>
<nav class="contents local" id="id1">
<ul class="simple">
<li><p><a class="reference internal" href="#fixing-properties-that-should-hold" id="id13">Fixing properties that should hold</a></p></li>
<li><p><a class="reference internal" href="#filtering-properties-that-should-not-be-checked" id="id14">Filtering properties that should not be checked</a></p></li>
<li><p><a class="reference internal" href="#focusing-on-specific-contracts" id="id15">Focusing on specific contracts</a></p></li>
</ul>
</nav>
<section id="fixing-properties-that-should-hold">
<h3><a class="toc-backref" href="#id13" role="doc-backlink">Fixing properties that should hold</a><a class="headerlink" href="#fixing-properties-that-should-hold" title="Link to this heading"></a></h3>
<p>Most parametric rules and all invariants encode general properties of a system
that should be impossible for any contract to violate.  For example, consider a
“solvency” invariant that shows that a vault contract holds enough underlying
tokens to cover any withdrawals:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell0"><span></span><span class="k">invariant</span><span class="w"> </span><span class="nc">solvency</span><span class="p">()</span>
<span class="w">    </span>underlying<span class="p">.</span>balanceOf<span class="p">(</span><span class="nb">currentContract</span><span class="p">)</span><span class="w"> </span><span class="o">&gt;=</span><span class="w"> </span><span class="nb">currentContract</span><span class="p">.</span>totalSupply<span class="p">();</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell0">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>Any violation of this property would be an important security vulnerability,
regardless of whether it is violated by a method of the vault or a method of
the underlying token.  Therefore, it is important to check that no method of
any contract can violate these kinds of properties.  However, sometimes
verifying these kinds of properties on methods of secondary contracts will
require additional work.</p>
<p>Continuing the solvency example, the Prover is likely to find a violation of
the solvency rule in <code class="docutils literal notranslate"><span class="pre">underlying.transferFrom</span></code> where the vault contract has
given an allowance to a third party.  If a third party has an allowance, it
will be able to reduce the vault’s balance by transferring the vault’s tokens
to itself.</p>
<p>This violation represents an important vulnerability: if the vault mismanages
its allowances, then it may become insolvent.  This violation shows that the
solvency of the vault depends on the correct management of its underlying
allowances.</p>
<p>Therefore, to get the rule to pass, we will need to add another invariant
stating that the vault manages its allowances correctly:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell1"><span></span><span class="k">invariant</span><span class="w"> </span><span class="nc">no_vault_allowance</span><span class="p">()</span>
<span class="w">    </span>underlying<span class="p">.</span>allowance<span class="p">(</span><span class="nb">currentContract</span><span class="p">)</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">;</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell1">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>We can then use this invariant in the <code class="docutils literal notranslate"><span class="pre">preserved</span></code> block for the original
solvency rule.  We are also likely to get violations from the case that the
vault contract itself calls methods on the underlying contract, so we rule that
out as well<a class="footnote-reference brackets" href="#call-note" id="id2" role="doc-noteref"><span class="fn-bracket">[</span>1<span class="fn-bracket">]</span></a>:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell2"><span></span><span class="k">invariant</span><span class="w"> </span><span class="nc">solvency</span><span class="p">()</span>
<span class="w">    </span>underlying<span class="p">.</span>balanceOf<span class="p">(</span><span class="nb">currentContract</span><span class="p">)</span><span class="w"> </span><span class="o">&gt;=</span><span class="w"> </span><span class="nb">currentContract</span><span class="p">.</span>totalSupply<span class="p">()</span>
<span class="w">    </span><span class="p">{</span>
<span class="w">        </span><span class="kr">preserved</span><span class="w"> </span>with<span class="w"> </span><span class="p">(</span><span class="kt">env</span><span class="w"> </span>e<span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">            </span><span class="kr">require</span><span class="w"> </span>e<span class="p">.</span><span class="kc">msg.sender</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="nb">currentContract</span><span class="p">;</span>
<span class="w">            </span><span class="kr">requireInvariant</span><span class="w"> </span>no_vault_allowance<span class="p">();</span>
<span class="w">        </span><span class="p">}</span>
<span class="w">    </span><span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell2">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>There is nothing new about this process of identifying violations and adding
new invariants as necessary; it is the same process you would use for analyzing
any violation.  This example just shows that some work may be required when
verifying old specifications with <code class="docutils literal notranslate"><span class="pre">certora-cli</span></code> 5.0.</p>
<p>The benefit is that by checking methods on secondary contracts, the Prover
forces us to consider a previously unstated assumptions about the contract and
write invariants that could detect important security vulnerabilities.  For
this reason, you are encouraged to identify and prove additional invariants
to address counterexamples instead of using the filtering techniques described
in the following sections.</p>
</section>
<section id="filtering-properties-that-should-not-be-checked">
<h3><a class="toc-backref" href="#id14" role="doc-backlink">Filtering properties that should not be checked</a><a class="headerlink" href="#filtering-properties-that-should-not-be-checked" title="Link to this heading"></a></h3>
<p>Some parametric rules encode properties that are only expected to hold on a
specific contract.  For example, you might have a rule that ensures that every
successful method invocation is correctly authorized:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell3"><span></span><span class="k">rule</span><span class="w"> </span><span class="nc">authorization_check</span><span class="p">(</span><span class="kt">method</span><span class="w"> </span>f<span class="p">)</span>
<span class="kr">filtered</span><span class="w"> </span><span class="p">{</span><span class="w"> </span>f<span class="w"> </span><span class="o">-&gt;</span><span class="w"> </span>f<span class="p">.</span>isView<span class="w"> </span><span class="p">}</span>
<span class="p">{</span>
<span class="w">    </span><span class="kt">env</span><span class="w"> </span>e<span class="p">;</span><span class="w"> </span><span class="kt">calldataarg</span><span class="w"> </span>args<span class="p">;</span>

<span class="w">    </span>f<span class="p">(</span>e<span class="p">,</span>args<span class="p">);</span>

<span class="w">    </span><span class="kr">assert</span><span class="w"> </span>is_authorized<span class="p">(</span>e<span class="p">.</span><span class="kc">msg.sender</span><span class="p">,</span><span class="w"> </span>f<span class="p">.</span><span class="nb">selector</span><span class="p">);</span>
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
<p>There is no reason to expect this property to hold on any contract besides the
main contract.</p>
<p>To handle cases like these, <code class="docutils literal notranslate"><span class="pre">certora-cli</span></code> 5.0 introduces two new ways to filter
methods to a specific contract.</p>
<p>The first and simplest way to restrict verification to a specific contract is
to call the <code class="docutils literal notranslate"><span class="pre">method</span></code> object with a specific receiver contract:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell4"><span></span><span class="k">rule</span><span class="w"> </span><span class="nc">authorization_check</span><span class="p">(</span><span class="kt">method</span><span class="w"> </span>f<span class="p">)</span>
<span class="kr">filtered</span><span class="w"> </span><span class="p">{</span><span class="w"> </span>f<span class="w"> </span><span class="o">-&gt;</span><span class="w"> </span>f<span class="p">.</span>isView<span class="w"> </span><span class="p">}</span>
<span class="p">{</span>
<span class="w">    </span><span class="kt">env</span><span class="w"> </span>e<span class="p">;</span><span class="w"> </span><span class="kt">calldataarg</span><span class="w"> </span>args<span class="p">;</span>

<span class="hll"><span class="w">    </span><span class="nb">currentContract</span><span class="p">.</span>f<span class="p">(</span>e<span class="p">,</span>args<span class="p">);</span>
</span>
<span class="w">    </span><span class="kr">assert</span><span class="w"> </span>is_authorized<span class="p">(</span>e<span class="p">.</span><span class="kc">msg.sender</span><span class="p">,</span><span class="w"> </span>f<span class="p">.</span><span class="nb">selector</span><span class="p">);</span>
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
<p>This syntax will add a filter that will only instantiate <code class="docutils literal notranslate"><span class="pre">f</span></code> with the methods
of <code class="docutils literal notranslate"><span class="pre">currentContract</span></code>.  The receiver may be either <code class="docutils literal notranslate"><span class="pre">currentContract</span></code> or a
variable introduced by a <code class="docutils literal notranslate"><span class="pre">using</span></code> clause.</p>
<p>The second and more flexible way is to use the new <code class="docutils literal notranslate"><span class="pre">contract</span></code> property of the
<code class="docutils literal notranslate"><span class="pre">method</span></code> variable:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell5"><span></span><span class="k">rule</span><span class="w"> </span><span class="nc">authorization_check</span><span class="p">(</span><span class="kt">method</span><span class="w"> </span>f<span class="p">)</span>
<span class="hll"><span class="kr">filtered</span><span class="w"> </span><span class="p">{</span><span class="w"> </span>f<span class="w"> </span><span class="o">-&gt;</span><span class="w"> </span>f<span class="p">.</span>isView<span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span>f<span class="p">.</span>contract<span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="nb">currentContract</span><span class="w"> </span><span class="p">}</span>
</span><span class="p">{</span>
<span class="w">    </span><span class="kt">env</span><span class="w"> </span>e<span class="p">;</span><span class="w"> </span><span class="kt">calldataarg</span><span class="w"> </span>args<span class="p">;</span>

<span class="w">    </span>f<span class="p">(</span>e<span class="p">,</span>args<span class="p">);</span>

<span class="w">    </span><span class="kr">assert</span><span class="w"> </span>is_authorized<span class="p">(</span>e<span class="p">.</span><span class="kc">msg.sender</span><span class="p">,</span><span class="w"> </span>f<span class="p">.</span><span class="nb">selector</span><span class="p">);</span>
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
<p>If <code class="docutils literal notranslate"><span class="pre">f</span></code> is a <code class="docutils literal notranslate"><span class="pre">method</span></code> variable, <code class="docutils literal notranslate"><span class="pre">f.contract</span></code> refers to the contract that contains
the method <code class="docutils literal notranslate"><span class="pre">f</span></code>.</p>
</section>
<section id="focusing-on-specific-contracts">
<span id="v5-contract-option"></span><h3><a class="toc-backref" href="#id15" role="doc-backlink">Focusing on specific contracts</a><a class="headerlink" href="#focusing-on-specific-contracts" title="Link to this heading"></a></h3>
<p>If you want to focus verification on a specific contract, you can do so using
the <a class="reference internal" href="../prover/cli/options.html#parametric-contracts"><span class="std std-ref">parametric_contracts</span></a> option.  This option takes a list of contracts and only
instantiates parametric rules and invariants on methods of those contracts.</p>
<p>You can use this option to help transition specs to <code class="docutils literal notranslate"><span class="pre">certora-cli</span></code> 5.0; if <code class="docutils literal notranslate"><span class="pre">C</span></code>
is the main contract being verified, then passing <code class="docutils literal notranslate"><span class="pre">--parametric_contracts</span> <span class="pre">C</span></code> will cause
method variables to be instantiated in the same way the would have in older
versions.</p>
</section>
</section>
<section id="disallow-calls-to-contract-functions-in-quantified-expressions">
<h2><a class="toc-backref" href="#id8" role="doc-backlink">Disallow calls to contract functions in quantified expressions</a><a class="headerlink" href="#disallow-calls-to-contract-functions-in-quantified-expressions" title="Link to this heading"></a></h2>
<p>Starting with <code class="docutils literal notranslate"><span class="pre">certora-cli</span></code> version 5.0, the Prover no longer supports
making contract method calls in quantified expression bodies by
default.</p>
<p>For example, given the simple contract below, you can no longer
use the <code class="docutils literal notranslate"><span class="pre">method</span></code> <code class="docutils literal notranslate"><span class="pre">getI()</span></code> in a quantified expression body.</p>
<div class="highlight-solidity notranslate"><div class="highlight"><pre id="codecell6"><span></span><span class="k">contract</span><span class="w"> </span><span class="ni">example</span><span class="w"> </span><span class="p">{</span>

<span class="w">   </span><span class="kt">uint</span><span class="w"> </span><span class="nv">i</span><span class="p">;</span><span class="w"> </span>
<span class="w">    </span>
<span class="w">   </span><span class="kt">function</span><span class="w"> </span><span class="nv">getI</span><span class="p">()</span><span class="w"> </span><span class="kt">public</span><span class="w"> </span>view<span class="w"> </span><span class="kt">returns</span><span class="w"> </span><span class="p">(</span><span class="kt">uint256</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">       </span><span class="kt">return</span><span class="w"> </span>i<span class="p">;</span>
<span class="w">   </span><span class="p">}</span>
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
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell7"><span></span><span class="k">rule</span><span class="w"> </span><span class="nc">there_exists</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="c1">// Using getI() in the quantified body will now cause the Prover to</span>
<span class="w">    </span><span class="c1">// generate a type-checking error.</span>
<span class="hll"><span class="w">    </span><span class="kr">require</span><span class="w"> </span><span class="p">(</span><span class="kr">exists</span><span class="w"> </span><span class="kt">uint256</span><span class="w"> </span>i<span class="w"> </span><span class="p">.</span><span class="w"> </span>i<span class="w"> </span><span class="o">==</span><span class="w"> </span>getI<span class="p">());</span>
</span><span class="w">    </span><span class="kr">assert</span><span class="w"> </span><span class="kr">false</span><span class="p">,</span><span class="w"> </span><span class="s2">"Prover will generate an error before this line"</span><span class="p">;</span>
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
<p>In the example rule <code class="docutils literal notranslate"><span class="pre">there_exists</span></code>, the Prover will now generate an error similar
to the following:</p>
<div class="highlight-text notranslate"><div class="highlight"><pre id="codecell8"><span></span>Error in spec file (test2.spec:8:36): Contract function calls such as getI()
are disallowed inside quantified formulas.
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell8">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>In most simple cases, you can replace contract method calls with either a
{ref}direct storage access &lt;…&gt; or a {ref}ghost <ghosts>. For example the
above function <code class="docutils literal notranslate"><span class="pre">getI</span></code> simply returns the storage variable <code class="docutils literal notranslate"><span class="pre">i</span></code> and you can
change the <code class="docutils literal notranslate"><span class="pre">require</span></code> statement in the <code class="docutils literal notranslate"><span class="pre">there_exists</span></code> rule to use storage access:
<code class="docutils literal notranslate"><span class="pre">require</span> <span class="pre">(exists</span> <span class="pre">uint</span> <span class="pre">i</span> <span class="pre">.</span> <span class="pre">i</span> <span class="pre">==</span> <span class="pre">currentContract.i)</span></code>. To use a ghost, declare
the ghost and the hook that populates the ghost with the current value of
the contract variable <code class="docutils literal notranslate"><span class="pre">i</span></code>.</ghosts></p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell9"><span></span><span class="kd">ghost</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>gI<span class="p">;</span>

<span class="kd">hook</span><span class="w"> </span><span class="kp">Sstore</span><span class="w"> </span>i<span class="w"> </span><span class="kt">uint256</span><span class="w"> </span>v<span class="w"> </span><span class="p">{</span>
<span class="w">    </span>gI<span class="w"> </span><span class="o">=</span><span class="w"> </span>v<span class="p">;</span>
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
<p>Finally, replace <code class="docutils literal notranslate"><span class="pre">getI</span></code> in the <code class="docutils literal notranslate"><span class="pre">require</span></code> statement in rule <code class="docutils literal notranslate"><span class="pre">there_exists</span></code> with the
ghost variable <code class="docutils literal notranslate"><span class="pre">gI</span></code>: <code class="docutils literal notranslate"><span class="pre">require</span> <span class="pre">(exists</span> <span class="pre">uint</span> <span class="pre">i</span> <span class="pre">.</span> <span class="pre">i</span> <span class="pre">==</span> <span class="pre">gI)</span></code>.</p>
</section>
<section id="method-variable-restrictions">
<h2><a class="toc-backref" href="#id9" role="doc-backlink">Method variable restrictions</a><a class="headerlink" href="#method-variable-restrictions" title="Link to this heading"></a></h2>
<p>Starting with <code class="docutils literal notranslate"><span class="pre">certora-cli</span></code> version 5.0, you cannot declare new <a class="reference internal" href="types.html#method-type"><span class="std std-ref">method variables</span></a> anywhere except the top-level body of a rule.
Declaring new <code class="docutils literal notranslate"><span class="pre">method</span></code> variables inside of <code class="docutils literal notranslate"><span class="pre">if</span></code> statements, hook bodies, CVL
function bodies, preserved blocks, and all other contexts are all disallowed.</p>
<p>You can still pass <code class="docutils literal notranslate"><span class="pre">method</span></code>-type variables as arguments to CVL functions and
definitions.  You can use this feature to rewrite CVL functions that formerly
declared new <code class="docutils literal notranslate"><span class="pre">method</span></code> variables.</p>
<p>For example, before <code class="docutils literal notranslate"><span class="pre">certora-cli</span></code> 5.0, the following CVL function was valid:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell10"><span></span><span class="kt">function</span><span class="w"> </span><span class="nf">call_arbitrary</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kt">method</span><span class="w"> </span>f<span class="p">;</span><span class="w"> </span><span class="kt">env</span><span class="w"> </span>e<span class="p">;</span><span class="w"> </span><span class="kt">calldataarg</span><span class="w"> </span>args<span class="p">;</span>
<span class="w">    </span>f<span class="p">(</span>e<span class="p">,</span><span class="w"> </span>args<span class="p">);</span>
<span class="p">}</span>

<span class="k">rule</span><span class="w"> </span><span class="nc">r</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span>call_arbitrary<span class="p">();</span>
<span class="w">    </span><span class="kr">assert</span><span class="w"> </span><span class="kr">true</span><span class="p">;</span>
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
<p>The declaration of <code class="docutils literal notranslate"><span class="pre">f</span></code> inside of <code class="docutils literal notranslate"><span class="pre">call_arbitrary</span></code> is now disallowed, so <code class="docutils literal notranslate"><span class="pre">f</span></code> must
be passed into <code class="docutils literal notranslate"><span class="pre">call_arbitrary</span></code> instead of declared within it:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell11"><span></span><span class="kt">function</span><span class="w"> </span><span class="nf">call_arbitrary</span><span class="p">(</span><span class="kt">method</span><span class="w"> </span>f<span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kt">env</span><span class="w"> </span>e<span class="p">;</span><span class="w"> </span><span class="kt">calldataarg</span><span class="w"> </span>args<span class="p">;</span>
<span class="w">    </span>f<span class="p">(</span>e<span class="p">,</span>args<span class="p">);</span>
<span class="p">}</span>

<span class="k">rule</span><span class="w"> </span><span class="nc">r</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kt">method</span><span class="w"> </span>f<span class="p">;</span>
<span class="w">    </span>call_arbitrary<span class="p">(</span>f<span class="p">);</span>
<span class="w">    </span><span class="kr">assert</span><span class="w"> </span><span class="kr">true</span><span class="p">;</span>
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
</section>
<section id="new-delete-summary-syntax">
<h2><a class="toc-backref" href="#id10" role="doc-backlink">New <code class="docutils literal notranslate"><span class="pre">DELETE</span></code> summary syntax</a><a class="headerlink" href="#new-delete-summary-syntax" title="Link to this heading"></a></h2>
<p>The syntax of the <a class="reference internal" href="methods.html#delete-summary"><span class="std std-ref">new `DELETE` keyword</span></a> in summaries
has changed.  Prior to <code class="docutils literal notranslate"><span class="pre">certora-cli</span></code> 5.0, it was possible to call methods
summarized with <code class="docutils literal notranslate"><span class="pre">DELETE</span></code> summaries from spec, and the user had to annotate the
<code class="docutils literal notranslate"><span class="pre">DELETE</span></code> modifier to indicate how those calls should be treated.</p>
<p>Starting with <code class="docutils literal notranslate"><span class="pre">certora-cli</span></code> 5.0, calling methods that have been summarized with
a <code class="docutils literal notranslate"><span class="pre">DELETE</span></code> summary is disallowed, and the <code class="docutils literal notranslate"><span class="pre">DELETE</span></code> annotation requires no
additional annotation.</p>
</section>
<section id="cli-changes-new-parametric-contracts-attribute">
<h2><a class="toc-backref" href="#id11" role="doc-backlink">CLI changes: New Parametric Contracts Attribute</a><a class="headerlink" href="#cli-changes-new-parametric-contracts-attribute" title="Link to this heading"></a></h2>
<p>As mentioned above the attribute <code class="docutils literal notranslate"><span class="pre">parametric_contracts</span></code> was added to <code class="docutils literal notranslate"><span class="pre">certora-cli</span></code> 5.0.
The attribute accepts the parametric contracts as a list of strings.
The attribute can be set as the CLI flag <code class="docutils literal notranslate"><span class="pre">--parametric_contracts</span></code> or in a <code class="docutils literal notranslate"><span class="pre">.conf</span></code> file.</p>
<p><strong>Example</strong>
CLI:</p>
<p><code class="docutils literal notranslate"><span class="pre">certoraRun</span> <span class="pre">C1.sol</span> <span class="pre">C2.sol</span> <span class="pre">C3.sol</span> <span class="pre">--parametric_contracts</span> <span class="pre">C1</span> <span class="pre">C3</span> <span class="pre">...</span></code></p>
<p>Configuration file:</p>
<p><code class="docutils literal notranslate"><span class="pre">"files":</span> <span class="pre">[</span> <span class="pre">"C1",</span> <span class="pre">"C2",</span> <span class="pre">"C3"],</span> <span class="pre">"parametric_contracts":</span> <span class="pre">[</span> <span class="pre">"C1",</span> <span class="pre">"C3"],</span> <span class="pre">...</span></code></p>
</section>
<section id="cli-changes-end-of-cvl1-deprecation-period">
<h2><a class="toc-backref" href="#id12" role="doc-backlink">CLI changes: End of CVL1 Deprecation period</a><a class="headerlink" href="#cli-changes-end-of-cvl1-deprecation-period" title="Link to this heading"></a></h2>
<p>With the release of <code class="docutils literal notranslate"><span class="pre">certora-cli</span></code> version 5.0, we stop supporting
the CVL1 attributes that were deprecated during the transition to CVL2.
You can find the list of the deprecated attributes <a class="reference external" href="https://docs.certora.com/en/latest/docs/cvl/cvl2/changes.html?highlight=cvl2#changes-to-the-command-line-interface-cli">here</a>.</p>
<hr class="footnotes docutils">
<aside class="footnote-list brackets">
<aside class="footnote brackets" id="call-note" role="doc-footnote">
<span class="label"><span class="fn-bracket">[</span><a role="doc-backlink" href="#id2">1</a><span class="fn-bracket">]</span></span>
<p>Adding this restriction does not ignore any actual contract
behaviors. If the vault does call methods on the underlying contract, it will
only do so from its code, and that call will be analyzed while the Prover is
verifying the calling method.  The additional requirement only rules out
spurious counterexamples where the vault makes calls to the underlying token
without having code that does so.</p>
</aside>
</aside>
</section>
</section>


           </div>
          </div>
          <footer><div class="rst-footer-buttons" role="navigation" aria-label="Footer">
        <a href="cvl2/migration.html" class="btn btn-neutral float-left" title="CVL2 Migration Guide" accesskey="p" rel="prev"><span class="fa fa-arrow-circle-left" aria-hidden="true"></span> Previous</a>
        <a href="../prover/index.html" class="btn btn-neutral float-right" title="The Certora Prover" accesskey="n" rel="next">Next <span class="fa fa-arrow-circle-right" aria-hidden="true"></span></a>
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