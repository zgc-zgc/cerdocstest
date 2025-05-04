<!DOCTYPE html><html class="writer-html5" lang="en" data-content_root="../../../"><head>
  <meta charset="utf-8"><meta name="viewport" content="width=device-width, initial-scale=1">

  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Rule Sanity Checks — Certora Prover Documentation 0.0 documentation</title>
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
    <link rel="next" title="Coverage Info" href="coverage-info.html">
    <link rel="prev" title="Checking Specifications" href="index.html"> 
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
<li class="toctree-l1"><a class="reference internal" href="../../cvl/index.html">The Certora Verification Language</a></li>
<li class="toctree-l1 current" aria-expanded="true"><a class="reference internal" href="../index.html"><button class="toctree-expand" title="Open/close menu"></button>The Certora Prover</a><ul class="" aria-expanded="false">
<li class="toctree-l2"><a class="reference internal" href="../intro.html">Introduction</a></li>
<li class="toctree-l2"><a class="reference internal" href="../../user-guide/install.html">Installation</a></li>
<li class="toctree-l2"><a class="reference internal" href="../approx/index.html">Prover Approximations</a></li>
<li class="toctree-l2"><a class="reference internal" href="../techniques/index.html">Techniques Used by the Certora Prover</a></li>
<li class="toctree-l2"><a class="reference internal" href="../diagnosis/index.html">Diagnostic Tools</a></li>
<li class="toctree-l2 current" aria-expanded="true"><a class="reference internal" href="index.html"><button class="toctree-expand" title="Open/close menu"></button>Checking Specifications</a><ul class="" aria-expanded="false">
<li class="toctree-l3 current" aria-expanded="true"><a class="reference internal current" href="#" aria-expanded="true"><button class="toctree-expand" title="Open/close menu"></button><span class="highlighted">Rule</span> <span class="highlighted">Sanity</span> Checks</a><ul>
<li class="toctree-l4"><a class="reference internal" href="#vacuity-checks">Vacuity checks</a></li>
<li class="toctree-l4"><a class="reference internal" href="#assert-tautology-checks">Assert tautology checks</a></li>
<li class="toctree-l4"><a class="reference internal" href="#trivial-invariant-checks">Trivial invariant checks</a></li>
<li class="toctree-l4"><a class="reference internal" href="#assertion-structure-checks">Assertion structure checks</a></li>
<li class="toctree-l4"><a class="reference internal" href="#redundant-require-checks">Redundant require checks</a></li>
</ul>
</li>
<li class="toctree-l3"><a class="reference internal" href="coverage-info.html">Coverage Info</a></li>
<li class="toctree-l3"><a class="reference internal" href="injection.html">Bug Injection</a></li>
<li class="toctree-l3"><a class="reference internal" href="mutation.html">Mutation Testing</a></li>
</ul>
</li>
<li class="toctree-l2"><a class="reference internal" href="../cli/index.html">Certora Prover CLI</a></li>
<li class="toctree-l2"><a class="reference internal" href="../portal/using.html">Using the Certora Portal</a></li>
<li class="toctree-l2"><a class="reference internal" href="../changelog/index.html">Changelogs</a></li>
</ul>
</li>
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
          <li class="breadcrumb-item"><a href="../index.html">The Certora Prover</a></li>
          <li class="breadcrumb-item"><a href="index.html">Checking Specifications</a></li>
      <li class="breadcrumb-item active"><span class="highlighted">Rule</span> <span class="highlighted">Sanity</span> Checks</li>
      <li class="wy-breadcrumbs-aside">
            <a href="../../../_sources/docs/prover/checking/sanity.md.txt" rel="nofollow"> View page source</a>
      </li>
  </ul>
  <hr>
</div>
          <div role="main" class="document" itemscope="itemscope" itemtype="http://schema.org/Article">
           <div itemprop="articleBody">
             
  <section id="rule-sanity-checks">
<h1><span class="highlighted">Rule</span> <span class="highlighted">Sanity</span> Checks<a class="headerlink" href="#rule-sanity-checks" title="Link to this heading"></a></h1>
<p>The <a class="reference internal" href="../cli/options.html#rule-sanity"><span class="std std-ref"><span class="highlighted">rule</span>_<span class="highlighted">sanity</span></span></a> option enables some automatic checks that can warn users
about certain classes of mistakes in specifications.</p>
<p>There are several kinds of <span class="highlighted">sanity</span> checks:</p>
<ul class="simple">
<li><p><a class="reference internal" href="#sanity-vacuity"><span class="std std-ref">Vacuity checks</span></a> determines whether <span class="highlighted">rule</span>s pass <a class="reference internal" href="../../user-guide/glossary.html#term-vacuous"><span class="xref std std-term">vacuously</span></a> because they <span class="highlighted">rule</span> out all <a class="reference internal" href="../../user-guide/glossary.html#term-model"><span class="xref std std-term">models</span></a>.</p></li>
<li><p><a class="reference internal" href="#sanity-assert-tautology"><span class="std std-ref">Assert tautology checks</span></a> determines whether individual <code class="docutils literal notranslate"><span class="pre">assert</span></code> statements are <a class="reference internal" href="../../user-guide/glossary.html#term-tautology"><span class="xref std std-term">tautologies</span></a>.</p></li>
<li><p><a class="reference internal" href="#sanity-trivial-invariant"><span class="std std-ref">Trivial invariant checks</span></a> detects invariants that hold in all states, rather than just reachable states.</p></li>
<li><p><a class="reference internal" href="#sanity-assert-structure"><span class="std std-ref">Assertion structure checks</span></a> detects unnecessarily complex <code class="docutils literal notranslate"><span class="pre">assert</span></code> statements.</p></li>
<li><p><a class="reference internal" href="#sanity-redundant-require"><span class="std std-ref">Redundant require checks</span></a> detects unnecessary <code class="docutils literal notranslate"><span class="pre">require</span></code> statements.</p></li>
</ul>
<p>The <code class="docutils literal notranslate"><span class="pre">--<span class="highlighted">rule</span>_<span class="highlighted">sanity</span></span></code> option may be followed by one of <code class="docutils literal notranslate"><span class="pre">none</span></code>, <code class="docutils literal notranslate"><span class="pre">basic</span></code>, or
<code class="docutils literal notranslate"><span class="pre">advanced</span></code> options to control which <span class="highlighted">sanity</span> checks should be executed:</p>
<ul class="simple">
<li><p>With <code class="docutils literal notranslate"><span class="pre">--<span class="highlighted">rule</span>_<span class="highlighted">sanity</span></span> <span class="pre">none</span></code> or without passing <code class="docutils literal notranslate"><span class="pre">--<span class="highlighted">rule</span>_<span class="highlighted">sanity</span></span></code>, no <span class="highlighted">sanity</span>
checks are performed.</p></li>
<li><p>With <code class="docutils literal notranslate"><span class="pre">--<span class="highlighted">rule</span>_<span class="highlighted">sanity</span></span> <span class="pre">basic</span></code> or just <code class="docutils literal notranslate"><span class="pre">--<span class="highlighted">rule</span>_<span class="highlighted">sanity</span></span></code> without a mode, the
vacuity check and the trivial invariant check are performed.</p></li>
<li><p>With <code class="docutils literal notranslate"><span class="pre">--<span class="highlighted">rule</span>_<span class="highlighted">sanity</span></span> <span class="pre">advanced</span></code>, all the <span class="highlighted">sanity</span> checks will be performed for
all invariants and <span class="highlighted">rule</span>s.</p></li>
</ul>
<p>We recommend starting with the <code class="docutils literal notranslate"><span class="pre">basic</span></code> mode, since not all <span class="highlighted">rule</span>s flagged by the
<code class="docutils literal notranslate"><span class="pre">advanced</span></code> mode are incorrect.</p>
<p>Each option adds new child nodes to every <span class="highlighted">rule</span> in the specification.  If any of the <span class="highlighted">sanity</span> check nodes fails, that node will be marked with a yellow icon, and so will the parent <span class="highlighted">rule</span>’s node:</p>
<p><img alt="Screenshot of rule report showing a passing rule, a failing rule, and a sanity failure" src="../../../_images/sanity-icons.png"></p>
<p>If a <span class="highlighted">sanity</span> node is <code class="docutils literal notranslate"><span class="pre">halted</span></code>, then the parent <span class="highlighted">rule</span> will also have the status <code class="docutils literal notranslate"><span class="pre">halted</span></code>.</p>
<p>The remainder of this document describes these checks in detail.</p>
<section id="vacuity-checks">
<span id="sanity-vacuity"></span><h2>Vacuity checks<a class="headerlink" href="#vacuity-checks" title="Link to this heading"></a></h2>
<p>The <strong>vacuity</strong> <span class="highlighted">sanity</span> check ensures that even when ignoring all the
user-provided assertions, the end of the <span class="highlighted">rule</span> is reachable. This check ensures
that that the combination of <code class="docutils literal notranslate"><span class="pre">require</span></code> statements does not <span class="highlighted">rule</span> out all
possible counterexamples.  <span class="highlighted">Rule</span>s that <span class="highlighted">rule</span> out all possible counterexamples
are called <a class="reference internal" href="../../user-guide/glossary.html#term-vacuous"><span class="xref std std-term">vacuous</span></a> rules.  Since they don’t actually check any
assertions, they are almost certainly incorrect.</p>
<p>For example, the following <span class="highlighted">rule</span> would be flagged by the vacuity check:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell0"><span></span><span class="k"><span class="highlighted">rule</span></span><span class="w"> </span><span class="nc">vacuous</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kt">uint</span><span class="w"> </span>x<span class="p">;</span>
<span class="w">    </span><span class="kr">require</span><span class="w"> </span>x<span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="m m-Decimal">2</span><span class="p">;</span>
<span class="w">    </span><span class="kr">require</span><span class="w"> </span>x<span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="m m-Decimal">1</span><span class="p">;</span>
<span class="w">    </span><span class="kr">assert</span><span class="w"> </span>f<span class="p">(</span>x<span class="p">)</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="m m-Decimal">2</span><span class="p">,</span><span class="w"> </span><span class="s2">"f must return 2"</span><span class="p">;</span>
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
<p>Since there are no models satisfying both <code class="docutils literal notranslate"><span class="pre">x</span> <span class="pre">&gt;</span> <span class="pre">2</span></code> and <code class="docutils literal notranslate"><span class="pre">x</span> <span class="pre">&lt;</span> <span class="pre">1</span></code>, this <span class="highlighted">rule</span>
will always pass, regardless of the behavior of the contract.  This is an
example of a <a class="reference internal" href="../../user-guide/glossary.html#term-vacuous"><span class="xref std std-term">vacuous</span></a> rule — one that passes only because the
preconditions are contradictory.</p>
<p>A vacuity check adds a node called <code class="docutils literal notranslate"><span class="pre"><span class="highlighted">rule</span>_not_vacuous</span></code> to each <span class="highlighted">rule</span>.  For example, the <span class="highlighted">rule</span> report for the above <code class="docutils literal notranslate"><span class="pre">vacuous</span></code> rule will look like this:</p>
<p><img alt="Screenshot of vacuity subrule" src="../../../_images/vacuity_node.png" width="475" height="62"></p>
<p>The vacuity check also flags situations where counterexamples are <span class="highlighted">rule</span>d
out for reasons other than <code class="docutils literal notranslate"><span class="pre">require</span></code> statements.  A common example comes from
reusing <code class="docutils literal notranslate"><span class="pre">env</span></code> variables.  Consider the following poorly-written rule:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell1"><span></span><span class="kt">env</span><span class="w"> </span>e<span class="p">;</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>amount<span class="p">;</span><span class="w"> </span><span class="kt">address</span><span class="w"> </span>recipient<span class="p">;</span>

<span class="kr">require</span><span class="w"> </span>balanceOf<span class="p">(</span>recipient<span class="p">)</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">;</span>
<span class="kr">require</span><span class="w"> </span>amount<span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">;</span>

deposit<span class="p">(</span>e<span class="p">,</span><span class="w"> </span>amount<span class="p">);</span>
transfer<span class="p">(</span>e<span class="p">,</span><span class="w"> </span>recipient<span class="p">,</span><span class="w"> </span>amount<span class="p">);</span>

<span class="kr">assert</span><span class="w"> </span>balanceOf<span class="p">(</span>recipient<span class="p">)</span><span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">,</span>
<span class="w">    </span><span class="s2">"depositing and then transferring makes recipient's balance positive"</span><span class="p">;</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell1">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>Although it looks like this <span class="highlighted">rule</span> is reasonable, it may actually be vacuous.
The problem is that the environment <code class="docutils literal notranslate"><span class="pre">e</span></code> is reused, and in particular
<code class="docutils literal notranslate"><span class="pre">e.msg.value</span></code> is the same in the calls to <code class="docutils literal notranslate"><span class="pre">deposit</span></code> and <code class="docutils literal notranslate"><span class="pre">transfer</span></code>.  Since
<code class="docutils literal notranslate"><span class="pre">transfer</span></code> is not payable, it will always revert if <code class="docutils literal notranslate"><span class="pre">e.msg.value</span> <span class="pre">!=</span> <span class="pre">0</span></code>.  On the
other hand, <code class="docutils literal notranslate"><span class="pre">deposit</span></code> always reverts when <code class="docutils literal notranslate"><span class="pre">e.msg.value</span> <span class="pre">==</span> <span class="pre">0</span></code>.  Therefore every
example will either cause <code class="docutils literal notranslate"><span class="pre">deposit</span></code> or <code class="docutils literal notranslate"><span class="pre">transfer</span></code> to revert, so there are no
models that reach the <code class="docutils literal notranslate"><span class="pre">assert</span></code> statement.</p>
</section>
<section id="assert-tautology-checks">
<span id="sanity-assert-tautology"></span><h2>Assert tautology checks<a class="headerlink" href="#assert-tautology-checks" title="Link to this heading"></a></h2>
<p>The <strong>assert tautology</strong> <span class="highlighted">sanity</span> check ensures that individual <code class="docutils literal notranslate"><span class="pre">assert</span></code> statements
are not <a class="reference internal" href="../../user-guide/glossary.html#term-tautology"><span class="xref std std-term">tautologies</span></a>.  A tautology is a statement that is
true on all examples, even if all the <code class="docutils literal notranslate"><span class="pre">require</span></code> and <code class="docutils literal notranslate"><span class="pre">if</span></code> conditions are
removed. Tautology checks also consider the bodies of the contract functions. For
example, <code class="docutils literal notranslate"><span class="pre">assert</span> <span class="pre">square(x)</span> <span class="pre">&gt;=</span> <span class="pre">0;</span></code> is a tautology if <code class="docutils literal notranslate"><span class="pre">square</span></code> is a contract
function that squares its input.</p>
<p>For example, the following <span class="highlighted">rule</span> would be flagged by the assert tautology check:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell2"><span></span><span class="k"><span class="highlighted">rule</span></span><span class="w"> </span><span class="nc">tautology</span><span class="w"> </span><span class="p">{</span>
<span class="w">  </span><span class="kt">uint</span><span class="w"> </span>x<span class="p">;</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>y<span class="p">;</span>
<span class="w">  </span><span class="kr">require</span><span class="w"> </span>x<span class="w"> </span><span class="o">!=</span><span class="w"> </span>y<span class="p">;</span>
<span class="w">  </span><span class="p">...</span>
<span class="w">  </span><span class="kr">assert</span><span class="w"> </span>x<span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="m m-Decimal">2</span><span class="w"> </span><span class="o">||</span><span class="w"> </span>x<span class="w"> </span><span class="o">&gt;=</span><span class="w"> </span><span class="m m-Decimal">2</span><span class="p">,</span>
<span class="w">   </span><span class="s2">"x must be smaller than 2 or greater than or equal to 2"</span><span class="p">;</span>
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
<p>Since every <code class="docutils literal notranslate"><span class="pre">uint</span></code> satisfies the assertion, the assertion is tautological, which
may indicate an error in the specification.</p>
<p>The tautology check will add a node per <code class="docutils literal notranslate"><span class="pre">assert</span></code> or <code class="docutils literal notranslate"><span class="pre">satisfy</span></code> statement to each <span class="highlighted">rule</span>.  The nodes are named with the prefix <code class="docutils literal notranslate"><span class="pre">assert_not_tautological_&lt;LINE&gt;_&lt;COL&gt;</span></code>.  For example, the <span class="highlighted">rule</span> report for the above <code class="docutils literal notranslate"><span class="pre">tautology</span></code> rule will look like this:</p>
<p><img alt="Screenshot of assert tautology subrule" src="../../../_images/tautology_subrule.png" width="473" height="100"></p>
</section>
<section id="trivial-invariant-checks">
<span id="sanity-trivial-invariant"></span><h2>Trivial invariant checks<a class="headerlink" href="#trivial-invariant-checks" title="Link to this heading"></a></h2>
<p>The <strong>Trivial invariant</strong> <span class="highlighted">sanity</span> check ensures that invariants are not trivial.
A trivial invariant is one that holds in all possible states, not just in
reachable states.</p>
<p>For example, the following invariant is trivial:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell3"><span></span><span class="k">invariant</span><span class="w"> </span><span class="nc">squaresNonNeg</span><span class="p">(</span><span class="kt">int</span><span class="w"> </span>x<span class="p">)</span>
<span class="w">    </span>x<span class="w"> </span><span class="o">*</span><span class="w"> </span>x<span class="w"> </span><span class="o">&gt;=</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">;</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell3">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>While it does hold in every reachable state, it also holds in every
non-reachable state.  Therefore it could be more efficiently checked as a <span class="highlighted">rule</span>:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell4"><span></span><span class="k"><span class="highlighted">rule</span></span><span class="w"> </span><span class="nc">squaresNonNeg</span><span class="p">(</span><span class="kt">int</span><span class="w"> </span>x<span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kr">assert</span><span class="w"> </span>x<span class="w"> </span><span class="o">*</span><span class="w"> </span>x<span class="w"> </span><span class="o">&gt;=</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">;</span>
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
<p>The <span class="highlighted">rule</span> version is more efficient because it can do a single check in an
arbitrary state rather than separately checking states after arbitrary method
invocations.</p>
<p>The trivial invariant check will add a node to each method under the induction step of invariants named <code class="docutils literal notranslate"><span class="pre">invariant_not_trivial_postcondition</span></code>.  For example, the <span class="highlighted">rule</span> report for the above <code class="docutils literal notranslate"><span class="pre">squaresNonNeg</span></code> invariant will look like this:</p>
<p><img alt="Screenshot of trivial invariant subrule" src="../../../_images/trivial_invariant_node.png" width="482" height="209"></p>
</section>
<section id="assertion-structure-checks">
<span id="sanity-assert-structure"></span><h2>Assertion structure checks<a class="headerlink" href="#assertion-structure-checks" title="Link to this heading"></a></h2>
<p>The <strong>assertion structure</strong> <span class="highlighted">sanity</span> check ensures that complex assert statements
can’t be replaced with simpler ones.</p>
<p>If an assertion expression is more complex than necessary, it can pass for
misleading reasons.  For example, consider the following assertion:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell5"><span></span><span class="kt">uint</span><span class="w"> </span>x<span class="p">;</span>
<span class="kr">assert</span><span class="w"> </span><span class="p">(</span>x<span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="m m-Decimal">5</span><span class="p">)</span><span class="w"> </span><span class="o">=&gt;</span><span class="w"> </span><span class="p">(</span>x<span class="w"> </span><span class="o">&gt;=</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">);</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell5">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>In this case, the assertion is true, but only because <code class="docutils literal notranslate"><span class="pre">x</span></code> is a <code class="docutils literal notranslate"><span class="pre">uint</span></code> and is
therefore <em>always</em> non-negative.  The fact that <code class="docutils literal notranslate"><span class="pre">x</span> <span class="pre">&gt;=</span> <span class="pre">0</span></code> has nothing to do with
the fact that <code class="docutils literal notranslate"><span class="pre">x</span> <span class="pre">&lt;</span> <span class="pre">5</span></code>.  Therefore this complex assertion could be replaced with
the more informative assertion <code class="docutils literal notranslate"><span class="pre">assert</span> <span class="pre">x</span> <span class="pre">&gt;=</span> <span class="pre">0;</span></code>.</p>
<p>Similarly, if the premise of the assertion is always false, then the implication
is <a class="reference internal" href="../../user-guide/glossary.html#term-vacuous"><span class="xref std std-term">vacuously</span></a> true.  For example:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell6"><span></span><span class="kt">uint</span><span class="w"> </span>x<span class="p">;</span>
<span class="kr">assert</span><span class="w"> </span><span class="p">(</span>x<span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">)</span><span class="w"> </span><span class="o">=&gt;</span><span class="w"> </span><span class="p">(</span>x<span class="w"> </span><span class="o">&gt;=</span><span class="w"> </span><span class="m m-Decimal">5</span><span class="p">);</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell6">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>This assertion will pass, but only because the unsigned integer <code class="docutils literal notranslate"><span class="pre">x</span></code> is never
negative.  This may mislead the user into thinking that they have checked that
<code class="docutils literal notranslate"><span class="pre">x</span> <span class="pre">&gt;=</span> <span class="pre">5</span></code> in some interesting situation, when in fact they have not.  The simpler
assertion <code class="docutils literal notranslate"><span class="pre">assert</span> <span class="pre">x</span> <span class="pre">&gt;=</span> <span class="pre">0;</span></code> more clearly describes what is going on.</p>
<p>Overly complex assertions like this may indicate a mistake in the <span class="highlighted">rule</span>.  In this
case, for example, the fact that the user was checking that <code class="docutils literal notranslate"><span class="pre">x</span> <span class="pre">&gt;=</span> <span class="pre">0</span></code> may
indicate that they should have declared <code class="docutils literal notranslate"><span class="pre">x</span></code> as an <code class="docutils literal notranslate"><span class="pre">int</span></code> instead of a <code class="docutils literal notranslate"><span class="pre">uint</span></code>.</p>
<p>The assertion structure check tries to prove some complex logical statements by
breaking them into simpler parts.  The following situations are reported by the
assertion structure check:</p>
<ol class="arabic simple">
<li><p><code class="docutils literal notranslate"><span class="pre">assert</span> <span class="pre">p</span> <span class="pre">=&gt;</span> <span class="pre">q;</span></code> is reported as a <span class="highlighted">sanity</span> violation if whenever the assertion is reached:</p></li>
</ol>
<ul class="simple">
<li><ol class="arabic simple">
<li><p><code class="docutils literal notranslate"><span class="pre">p</span></code> is always false. In this case, <code class="docutils literal notranslate"><span class="pre">q</span></code> is never checked. A simpler way to write this assertion is <code class="docutils literal notranslate"><span class="pre">assert</span> <span class="pre">!p;</span></code>. The node named <code class="docutils literal notranslate"><span class="pre">assertion_left_operand_check_&lt;LINE&gt;_&lt;COL&gt;</span></code> will have a yellow icon.</p></li>
</ol>
</li>
<li><ol class="arabic simple" start="2">
<li><p><code class="docutils literal notranslate"><span class="pre">p</span></code> is always true. A simpler way to write this assertion is <code class="docutils literal notranslate"><span class="pre">assert</span> <span class="pre">q;</span></code>. The node named <code class="docutils literal notranslate"><span class="pre">assertion_left_operand_check_&lt;LINE&gt;_&lt;COL&gt;</span></code> will have a yellow icon.</p></li>
</ol>
</li>
<li><ol class="arabic simple" start="3">
<li><p><code class="docutils literal notranslate"><span class="pre">q</span></code> is always true. A simpler way to write this assertion is <code class="docutils literal notranslate"><span class="pre">assert</span> <span class="pre">p;</span></code>. The node named <code class="docutils literal notranslate"><span class="pre">assertion_right_operand_check_&lt;LINE&gt;_&lt;COL&gt;</span></code>.</p></li>
</ol>
</li>
</ul>
<ol class="arabic simple" start="2">
<li><p><code class="docutils literal notranslate"><span class="pre">assert</span> <span class="pre">p</span> <span class="pre">&lt;=&gt;</span> <span class="pre">q;</span></code>  is reported as a <span class="highlighted">sanity</span> violation if whenever the assertion is reached:</p></li>
</ol>
<ul class="simple">
<li><ol class="arabic simple">
<li><p><code class="docutils literal notranslate"><span class="pre">p</span></code> and <code class="docutils literal notranslate"><span class="pre">q</span></code> are both always true. A simpler way to write this assertion is <code class="docutils literal notranslate"><span class="pre">assert</span> <span class="pre">p;</span> <span class="pre">assert</span> <span class="pre">q;</span></code>. The node named <code class="docutils literal notranslate"><span class="pre">assertion_iff_not_both_true_&lt;LINE&gt;_&lt;COL&gt;</span></code> will have a yellow icon.</p></li>
</ol>
</li>
<li><ol class="arabic simple" start="2">
<li><p><code class="docutils literal notranslate"><span class="pre">p</span></code> and <code class="docutils literal notranslate"><span class="pre">q</span></code> are both always false. A simpler way to write this assertion is <code class="docutils literal notranslate"><span class="pre">assert</span> <span class="pre">!p;</span> <span class="pre">assert</span> <span class="pre">!q;</span></code>. The node named <code class="docutils literal notranslate"><span class="pre">assertion_iff_not_both_false_&lt;LINE&gt;_&lt;COL&gt;</span></code> will have a yellow icon.</p></li>
</ol>
</li>
</ul>
<ol class="arabic simple" start="3">
<li><p><code class="docutils literal notranslate"><span class="pre">assert</span> <span class="pre">p</span> <span class="pre">||</span> <span class="pre">q;</span></code> is reported as a <span class="highlighted">sanity</span> violation if whenever the assertion is reached:</p></li>
</ol>
<ul class="simple">
<li><ol class="arabic simple">
<li><p><code class="docutils literal notranslate"><span class="pre">p</span></code> is always true. A simpler way to write this assertion is <code class="docutils literal notranslate"><span class="pre">assert</span> <span class="pre">q;</span></code>. The node named <code class="docutils literal notranslate"><span class="pre">assertion_left_operand_check_&lt;LINE&gt;_&lt;COL&gt;</span></code> will have a yellow icon.</p></li>
</ol>
</li>
<li><ol class="arabic simple" start="2">
<li><p><code class="docutils literal notranslate"><span class="pre">q</span></code> is always true. A simpler way to write this assertion is <code class="docutils literal notranslate"><span class="pre">assert</span> <span class="pre">p;</span></code>. The node named <code class="docutils literal notranslate"><span class="pre">assertion_right_operand_check_&lt;LINE&gt;_&lt;COL&gt;</span></code> will have a yellow icon.</p></li>
</ol>
</li>
</ul>
<p><img alt="Screenshot of sanity structure for implication" src="../../../_images/implication_sanity_structure.png"></p>
</section>
<section id="redundant-require-checks">
<span id="sanity-redundant-require"></span><h2>Redundant require checks<a class="headerlink" href="#redundant-require-checks" title="Link to this heading"></a></h2>
<p>The <strong>require redundancy</strong> <span class="highlighted">sanity</span> check highlights redundant <code class="docutils literal notranslate"><span class="pre">require</span></code> statements.
A <code class="docutils literal notranslate"><span class="pre">require</span></code> is considered to be redundant if it does not <span class="highlighted">rule</span> out any <a class="reference internal" href="../../user-guide/glossary.html#term-model"><span class="xref std std-term">models</span></a>
that haven’t been ruled out by previous requires.</p>
<p>For example, the require-redundancy check would flag the following <span class="highlighted">rule</span>:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell7"><span></span><span class="k"><span class="highlighted">rule</span></span><span class="w"> </span><span class="nc">require_redundant</span><span class="w"> </span><span class="p">{</span>
<span class="w">  </span><span class="kt">uint</span><span class="w"> </span>x<span class="p">;</span>
<span class="w">  </span><span class="kr">require</span><span class="w"> </span>x<span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="m m-Decimal">3</span><span class="p">;</span>
<span class="w">  </span><span class="kr">require</span><span class="w"> </span>x<span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="m m-Decimal">2</span><span class="p">;</span>
<span class="w">  </span><span class="kr">assert</span><span class="w"> </span>f<span class="p">(</span>x<span class="p">)</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="m m-Decimal">2</span><span class="p">,</span><span class="w"> </span><span class="s2">"f must return 2"</span><span class="p">;</span>
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
<p>In this example, the second requirement is redundant, since any <code class="docutils literal notranslate"><span class="pre">x</span></code> greater
than 3 will also be greater than 2.</p>
<p>The redundant require check will add a node per <code class="docutils literal notranslate"><span class="pre">require</span></code> statement to each <span class="highlighted">rule</span>.  The nodes are named with the prefix <code class="docutils literal notranslate"><span class="pre">require_not_redundant_&lt;LINE&gt;_&lt;COL&gt;</span></code>.</p>
<p><img alt="Screenshot of rule report showing a redundant require check" src="../../../_images/sanity-icons.png"></p>
<p>Redundant require is an exhaustive check and will only be executed if neither of the checks for <a class="reference internal" href="#sanity-trivial-invariant"><span class="std std-ref">Trivial invariant checks</span></a> and <a class="reference internal" href="#sanity-assert-tautology"><span class="std std-ref">Assert tautology checks</span></a> fail.</p>
</section>
</section>


           </div>
          </div>
          <footer><div class="rst-footer-buttons" role="navigation" aria-label="Footer">
        <a href="index.html" class="btn btn-neutral float-left" title="Checking Specifications" accesskey="p" rel="prev"><span class="fa fa-arrow-circle-left" aria-hidden="true"></span> Previous</a>
        <a href="coverage-info.html" class="btn btn-neutral float-right" title="Coverage Info" accesskey="n" rel="next">Next <span class="fa fa-arrow-circle-right" aria-hidden="true"></span></a>
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