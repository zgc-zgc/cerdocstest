<!DOCTYPE html><html class="writer-html5" lang="en" data-content_root="../../"><head>
  <meta charset="utf-8"><meta name="viewport" content="width=device-width, initial-scale=1">

  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Statements — Certora Prover Documentation 0.0 documentation</title>
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
    <link rel="next" title="Import and Use Statements" href="imports.html">
    <link rel="prev" title="Expressions" href="expr.html"> 
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
<li class="toctree-l2 current" aria-expanded="true"><a class="reference internal current" href="#" aria-expanded="true"><button class="toctree-expand" title="Open/close menu"></button>Statements</a><ul>
<li class="toctree-l3"><a class="reference internal" href="#syntax">Syntax</a></li>
<li class="toctree-l3"><a class="reference internal" href="#variable-declarations">Variable declarations</a></li>
<li class="toctree-l3"><a class="reference internal" href="#assert-and-require"><button class="toctree-expand" title="Open/close menu"></button><code class="docutils literal notranslate"><span class="pre">assert</span></code> and <code class="docutils literal notranslate"><span class="pre">require</span></code></a><ul>
<li class="toctree-l4"><a class="reference internal" href="#examples">Examples</a></li>
</ul>
</li>
<li class="toctree-l3"><a class="reference internal" href="#satisfy-statements"><code class="docutils literal notranslate"><span class="pre">satisfy</span></code> statements</a></li>
<li class="toctree-l3"><a class="reference internal" href="#requireinvariant-statements"><code class="docutils literal notranslate"><span class="pre">requireInvariant</span></code> statements</a></li>
<li class="toctree-l3"><a class="reference internal" href="#havoc-statements"><button class="toctree-expand" title="Open/close menu"></button>Havoc Statements</a><ul>
<li class="toctree-l4"><a class="reference internal" href="#id1">Syntax</a></li>
<li class="toctree-l4"><a class="reference internal" href="#usage">Usage</a></li>
<li class="toctree-l4"><a class="reference internal" href="#two-state-contexts-old-and-new">Two-State Contexts: <code class="docutils literal notranslate"><span class="pre">@old</span></code> and <code class="docutils literal notranslate"><span class="pre">@new</span></code></a></li>
<li class="toctree-l4"><a class="reference internal" href="#advanced-usage-havoc-assuming">Advanced Usage: <code class="docutils literal notranslate"><span class="pre">havoc</span> <span class="pre">assuming</span></code></a></li>
<li class="toctree-l4"><a class="reference internal" href="#conclusion">Conclusion</a></li>
</ul>
</li>
<li class="toctree-l3"><a class="reference internal" href="#solidity-like-statements"><button class="toctree-expand" title="Open/close menu"></button>Solidity-like Statements</a><ul>
<li class="toctree-l4"><a class="reference internal" href="#assert-statement">1. Assert Statement</a></li>
<li class="toctree-l4"><a class="reference internal" href="#require-statement">2. Require Statement</a></li>
<li class="toctree-l4"><a class="reference internal" href="#modeling-reverts-in-solidity-calls">3. Modeling Reverts in Solidity Calls</a></li>
<li class="toctree-l4"><a class="reference internal" href="#return-statement">4. Return Statement</a></li>
<li class="toctree-l4"><a class="reference internal" href="#id16">Conclusion</a></li>
</ul>
</li>
</ul>
</li>
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
      <li class="breadcrumb-item active">Statements</li>
      <li class="wy-breadcrumbs-aside">
            <a href="../../_sources/docs/cvl/statements.md.txt" rel="nofollow"> View page source</a>
      </li>
  </ul>
  <hr>
</div>
          <div role="main" class="document" itemscope="itemscope" itemtype="http://schema.org/Article">
           <div itemprop="articleBody">
             
  <section id="statements">
<h1><a class="toc-backref" href="#id17" role="doc-backlink">Statements</a><a class="headerlink" href="#statements" title="Link to this heading"></a></h1>
<p>The bodies of <a class="reference internal" href="rules.html"><span class="doc">rules</span></a>, <a class="reference internal" href="functions.html"><span class="doc">functions</span></a>, and
<a class="reference internal" href="hooks.html"><span class="doc">hooks</span></a> in CVL are made up of statements.  Statements describe the
steps that are simulated by the Prover when evaluating a rule.</p>
<p>Statements in CVL are similar to statements in Solidity, although there are
some differences; see <a class="reference internal" href="#control-flow"><span class="std std-ref">Solidity-like Statements</span></a>.  This document lists the available
CVL commands.</p>
<nav class="contents" id="contents">
<p class="topic-title">Contents</p>
<ul class="simple">
<li><p><a class="reference internal" href="#statements" id="id17">Statements</a></p>
<ul>
<li><p><a class="reference internal" href="#syntax" id="id18">Syntax</a></p></li>
<li><p><a class="reference internal" href="#variable-declarations" id="id19">Variable declarations</a></p></li>
<li><p><a class="reference internal" href="#assert-and-require" id="id20"><code class="docutils literal notranslate"><span class="pre">assert</span></code> and <code class="docutils literal notranslate"><span class="pre">require</span></code></a></p>
<ul>
<li><p><a class="reference internal" href="#examples" id="id21">Examples</a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#satisfy-statements" id="id22"><code class="docutils literal notranslate"><span class="pre">satisfy</span></code> statements</a></p></li>
<li><p><a class="reference internal" href="#requireinvariant-statements" id="id23"><code class="docutils literal notranslate"><span class="pre">requireInvariant</span></code> statements</a></p></li>
<li><p><a class="reference internal" href="#havoc-statements" id="id24">Havoc Statements</a></p>
<ul>
<li><p><a class="reference internal" href="#id1" id="id25">Syntax</a></p></li>
<li><p><a class="reference internal" href="#usage" id="id26">Usage</a></p>
<ul>
<li><p><a class="reference internal" href="#basic-havoc" id="id27">Basic Havoc</a></p>
<ul>
<li><p><a class="reference internal" href="#example" id="id28">Example:</a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#havoc-with-condition" id="id29">Havoc with Condition</a></p>
<ul>
<li><p><a class="reference internal" href="#id2" id="id30">Example:</a></p></li>
</ul>
</li>
</ul>
</li>
<li><p><a class="reference internal" href="#two-state-contexts-old-and-new" id="id31">Two-State Contexts: <code class="docutils literal notranslate"><span class="pre">@old</span></code> and <code class="docutils literal notranslate"><span class="pre">@new</span></code></a></p>
<ul>
<li><p><a class="reference internal" href="#id3" id="id32">Example:</a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#advanced-usage-havoc-assuming" id="id33">Advanced Usage: <code class="docutils literal notranslate"><span class="pre">havoc</span> <span class="pre">assuming</span></code></a></p>
<ul>
<li><p><a class="reference internal" href="#id4" id="id34">Example:</a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#conclusion" id="id35">Conclusion</a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#solidity-like-statements" id="id36">Solidity-like Statements</a></p>
<ul>
<li><p><a class="reference internal" href="#assert-statement" id="id37">1. Assert Statement</a></p>
<ul>
<li><p><a class="reference internal" href="#id5" id="id38">Syntax:</a></p></li>
<li><p><a class="reference internal" href="#id6" id="id39">Usage:</a></p>
<ul>
<li><p><a class="reference internal" href="#id7" id="id40">Example:</a></p></li>
</ul>
</li>
</ul>
</li>
<li><p><a class="reference internal" href="#require-statement" id="id41">2. Require Statement</a></p>
<ul>
<li><p><a class="reference internal" href="#id8" id="id42">Syntax:</a></p></li>
<li><p><a class="reference internal" href="#id9" id="id43">Usage:</a></p>
<ul>
<li><p><a class="reference internal" href="#id10" id="id44">Example:</a></p></li>
</ul>
</li>
</ul>
</li>
<li><p><a class="reference internal" href="#modeling-reverts-in-solidity-calls" id="id45">3. Modeling Reverts in Solidity Calls</a></p>
<ul>
<li><p><a class="reference internal" href="#id11" id="id46">Syntax:</a></p>
<ul>
<li><p><a class="reference internal" href="#id12" id="id47">Example:</a></p></li>
</ul>
</li>
</ul>
</li>
<li><p><a class="reference internal" href="#return-statement" id="id48">4. Return Statement</a></p>
<ul>
<li><p><a class="reference internal" href="#id13" id="id49">Syntax:</a></p></li>
<li><p><a class="reference internal" href="#id14" id="id50">Usage:</a></p>
<ul>
<li><p><a class="reference internal" href="#id15" id="id51">Example:</a></p></li>
</ul>
</li>
</ul>
</li>
<li><p><a class="reference internal" href="#id16" id="id52">Conclusion</a></p></li>
</ul>
</li>
</ul>
</li>
</ul>
</nav>
<section id="syntax">
<h2><a class="toc-backref" href="#id18" role="doc-backlink">Syntax</a><a class="headerlink" href="#syntax" title="Link to this heading"></a></h2>
<p>The syntax for statements in CVL is given by the following <a class="reference internal" href="overview.html#ebnf-syntax"><span class="std std-ref">EBNF grammar</span></a>:</p>
<div class="highlight-default notranslate"><div class="highlight"><pre id="codecell0"><span></span><span class="n">block</span> <span class="p">:</span><span class="o">:=</span> <span class="n">statement</span> <span class="p">{</span> <span class="n">statement</span> <span class="p">}</span>

<span class="n">statement</span> <span class="p">:</span><span class="o">:=</span> <span class="nb">type</span> <span class="nb">id</span> <span class="p">[</span> <span class="s2">"="</span> <span class="n">expr</span> <span class="p">]</span> <span class="s2">";"</span>

            <span class="o">|</span> <span class="s2">"require"</span> <span class="n">expr</span> <span class="s2">";"</span>
            <span class="o">|</span> <span class="s2">"assert"</span> <span class="n">expr</span> <span class="p">[</span> <span class="s2">","</span> <span class="n">string</span> <span class="p">]</span> <span class="s2">";"</span>
            <span class="o">|</span> <span class="s2">"satisfy"</span> <span class="n">expr</span> <span class="p">[</span> <span class="s2">","</span> <span class="n">string</span> <span class="p">]</span> <span class="s2">";"</span>

            <span class="o">|</span> <span class="s2">"requireInvariant"</span> <span class="nb">id</span> <span class="s2">"("</span> <span class="n">exprs</span> <span class="s2">")"</span> <span class="s2">";"</span>

            <span class="o">|</span> <span class="n">lhs</span> <span class="s2">"="</span> <span class="n">expr</span> <span class="s2">";"</span>
            <span class="o">|</span> <span class="s2">"if"</span> <span class="n">expr</span> <span class="n">statement</span> <span class="p">[</span> <span class="s2">"else"</span> <span class="n">statement</span> <span class="p">]</span>
            <span class="o">|</span> <span class="s2">"{"</span> <span class="n">block</span> <span class="s2">"}"</span>
            <span class="o">|</span> <span class="s2">"return"</span> <span class="p">[</span> <span class="n">expr</span> <span class="p">]</span> <span class="s2">";"</span>

            <span class="o">|</span> <span class="n">function_call</span> <span class="s2">";"</span>
            <span class="o">|</span> <span class="s2">"reset_storage"</span> <span class="n">expr</span> <span class="s2">";"</span>

            <span class="o">|</span> <span class="s2">"havoc"</span> <span class="nb">id</span> <span class="p">[</span> <span class="s2">"assuming"</span> <span class="n">expr</span> <span class="p">]</span> <span class="s2">";"</span>

<span class="n">lhs</span> <span class="p">:</span><span class="o">:=</span> <span class="nb">id</span> <span class="p">[</span> <span class="s2">"["</span> <span class="n">expr</span> <span class="s2">"]"</span> <span class="p">]</span> <span class="p">[</span> <span class="s2">","</span> <span class="n">lhs</span> <span class="p">]</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell0">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>See <a class="reference internal" href="basics.html"><span class="doc">Basic Syntax</span></a> for the <code class="docutils literal notranslate"><span class="pre">id</span></code> and <code class="docutils literal notranslate"><span class="pre">string</span></code> productions.  See <a class="reference internal" href="types.html"><span class="doc">Types</span></a> for
the <code class="docutils literal notranslate"><span class="pre">type</span></code> production.  See <a class="reference internal" href="expr.html"><span class="doc">Expressions</span></a> for the <code class="docutils literal notranslate"><span class="pre">expr</span></code> and <code class="docutils literal notranslate"><span class="pre">function_call</span></code> productions.</p>
</section>
<section id="variable-declarations">
<span id="declarations"></span><h2><a class="toc-backref" href="#id19" role="doc-backlink">Variable declarations</a><a class="headerlink" href="#variable-declarations" title="Link to this heading"></a></h2>
<p>Unlike undefined variables in most programming languages, undefined variables
in CVL are a centrally important language feature.  If a variable is declared
but not defined, the Prover will generate <a class="reference internal" href="../user-guide/glossary.html#term-model"><span class="xref std std-term">models</span></a> with every
possible value of the undefined variable.</p>
<p>Undefined variables in CVL behave the same way as <a class="reference internal" href="rules.html#rule-overview"><span class="std std-ref">rule parameters</span></a>.</p>
<p>When the Prover reports a counterexample that violates a rule, the values of the
variables declared in the rule are displayed in the report.  Variables declared
in CVL functions are not currently visible in the report.</p>
</section>
<section id="assert-and-require">
<span id="require"></span><h2><a class="toc-backref" href="#id20" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">assert</span></code> and <code class="docutils literal notranslate"><span class="pre">require</span></code></a><a class="headerlink" href="#assert-and-require" title="Link to this heading"></a></h2>
<p>The <code class="docutils literal notranslate"><span class="pre">assert</span></code> and <code class="docutils literal notranslate"><span class="pre">require</span></code> commands are similar to the corresponding statements
in Solidity.  The <code class="docutils literal notranslate"><span class="pre">require</span></code> statement is used to specify the preconditions for
a rule, while the <code class="docutils literal notranslate"><span class="pre">assert</span></code> statement is used to specify the expected behavior
of contract functions.</p>
<p>During verification, the Prover will ignore any <a class="reference internal" href="../user-guide/glossary.html#term-model"><span class="xref std std-term">model</span></a> that causes the
<code class="docutils literal notranslate"><span class="pre">require</span></code> expressions to evaluate to false.  Unlike Solidity, the <code class="docutils literal notranslate"><span class="pre">require</span></code>
statement does not contain a descriptive message, because the Prover will never
consider an example where the <code class="docutils literal notranslate"><span class="pre">require</span></code> statement evaluates to <code class="docutils literal notranslate"><span class="pre">false</span></code>.</p>
<p>The <code class="docutils literal notranslate"><span class="pre">assert</span></code> statements define the expected behavior of contract functions.  If
it is possible to generate a model that causes the <code class="docutils literal notranslate"><span class="pre">assert</span></code> expression to
evaluate to <code class="docutils literal notranslate"><span class="pre">false</span></code>, the Prover will construct one of them and report a
violation.</p>
<p>Assert conditions may be followed by a message string describing the condition;
this message will be included in the reported violation.</p>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>Unlike Solidity’s <code class="docutils literal notranslate"><span class="pre">assert</span></code> and <code class="docutils literal notranslate"><span class="pre">require</span></code>, the CVL syntax for <code class="docutils literal notranslate"><span class="pre">assert</span></code> and
<code class="docutils literal notranslate"><span class="pre">require</span></code> does not require parentheses around the expression and message.</p>
</div>
<section id="examples">
<h3><a class="toc-backref" href="#id21" role="doc-backlink">Examples</a><a class="headerlink" href="#examples" title="Link to this heading"></a></h3>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell1"><span></span><span class="k">rule</span><span class="w"> </span><span class="nc">withdraw_succeeds</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kt">env</span><span class="w"> </span>e<span class="p">;</span><span class="w"> </span><span class="c1">// env represents the bytecode environment passed on every call</span>
<span class="w">    </span><span class="c1">// invoke function withdraw and assume that it does not revert</span>
<span class="w">    </span><span class="kt">bool</span><span class="w"> </span>success<span class="w"> </span><span class="o">=</span><span class="w"> </span>withdraw<span class="p">(</span>e<span class="p">);</span><span class="w">  </span><span class="c1">// e is passed as an additional argument</span>
<span class="w">    </span><span class="kr">assert</span><span class="w"> </span>success<span class="p">,</span><span class="w"> </span><span class="s2">"withdraw must succeed"</span><span class="p">;</span><span class="w"> </span><span class="c1">// verify that withdraw succeeded</span>
<span class="p">}</span>

<span class="k">rule</span><span class="w"> </span><span class="nc">totalFundsAfterDeposit</span><span class="p">(</span><span class="kt">uint256</span><span class="w"> </span>amount<span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">	 </span><span class="kt">env</span><span class="w"> </span>e<span class="p">;</span>

<span class="w">	 </span>deposit<span class="p">(</span>e<span class="p">,</span><span class="w"> </span>amount<span class="p">);</span>

<span class="w">	 </span><span class="kt">uint256</span><span class="w"> </span>userFundsAfter<span class="w"> </span><span class="o">=</span><span class="w"> </span>getFunds<span class="p">(</span>e<span class="p">,</span><span class="w"> </span>e<span class="p">.</span><span class="kc">msg.sender</span><span class="p">);</span>
<span class="w">	 </span><span class="kt">uint256</span><span class="w"> </span>totalAfter<span class="w"> </span><span class="o">=</span><span class="w"> </span>getTotalFunds<span class="p">(</span>e<span class="p">);</span>

<span class="w">	 </span><span class="c1">// Verify that the total funds of the system is at least the current funds of the msg.sender.</span>
<span class="w">	 </span><span class="kr">assert</span><span class="w"> </span>totalAfter<span class="w"> </span><span class="o">&gt;=</span><span class="w"> </span>userFundsAfter<span class="p">;</span>
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
<ul class="simple">
<li><p><a class="reference external" href="https://github.com/Certora/Examples/blob/14668d39a6ddc67af349bc5b82f73db73349ef18/CVLByExample/ConstantProductPool/certora/spec/ConstantProductPool.spec#L75"><code class="docutils literal notranslate"><span class="pre">assert</span></code> example</a></p></li>
<li><p><a class="reference external" href="https://github.com/Certora/Examples/blob/14668d39a6ddc67af349bc5b82f73db73349ef18/CVLByExample/ConstantProductPool/certora/spec/ConstantProductPool.spec#L44"><code class="docutils literal notranslate"><span class="pre">require</span></code> example</a></p></li>
</ul>
</section>
</section>
<section id="satisfy-statements">
<span id="satisfy"></span><h2><a class="toc-backref" href="#id22" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">satisfy</span></code> statements</a><a class="headerlink" href="#satisfy-statements" title="Link to this heading"></a></h2>
<p>A <code class="docutils literal notranslate"><span class="pre">satisfy</span></code> statement is used to check that the rule can be executed in such a
way that the <code class="docutils literal notranslate"><span class="pre">satisfy</span></code> statement is reached and that its condition is fulfilled.</p>
<p>We require that each rule ends with either a <code class="docutils literal notranslate"><span class="pre">satisfy</span></code> statement or an <code class="docutils literal notranslate"><span class="pre">assert</span></code>
statement.</p>
<p>See <a class="reference internal" href="../user-guide/satisfy.html#producing-examples"><span class="std std-ref">Producing Positive Examples</span></a> for an example demonstrating the <code class="docutils literal notranslate"><span class="pre">satisfy</span></code>
command.</p>
<p>For each <code class="docutils literal notranslate"><span class="pre">satisfy</span></code> statement that is checked successfully, the Certora verifier
will produce a witness for a valid execution of the rule.  It will show an
execution trace containing values for each input variable and each state
variable where all <code class="docutils literal notranslate"><span class="pre">require</span></code> and <code class="docutils literal notranslate"><span class="pre">satisfy</span></code> statements are executed successfully.
In case there is no such execution, for example if the <code class="docutils literal notranslate"><span class="pre">require</span></code> statements are
already inconsistent or if a Solidity function always reverts, the rule will
show as “Violated”.</p>
<p>If the rule contains multiple <code class="docutils literal notranslate"><span class="pre">satisfy</span></code> statements, then all executed <code class="docutils literal notranslate"><span class="pre">satisfy</span></code>
statements must hold.   However, a <code class="docutils literal notranslate"><span class="pre">satisfy</span></code> statement on a conditional branch
that is not executed does not need to hold.</p>
<p>If at least one <code class="docutils literal notranslate"><span class="pre">satisfy</span></code> statement is not satisfiable, an error is reported.
If all <code class="docutils literal notranslate"><span class="pre">satisfy</span></code> statements can be fulfilled on at least one path, the rule
succeeds.</p>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>A success only guarantees that there is some satisfying execution starting in
some arbitrary state.  It is not possible to check that every possible starting
state has an execution that satisfies the condition.</p>
</div>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p><code class="docutils literal notranslate"><span class="pre">satisfy</span></code> statements are never checked in the same sub-rule with <code class="docutils literal notranslate"><span class="pre">assert</span></code> statements,
and they are always checked under <a class="reference internal" href="../user-guide/glossary.html#term-optimistic-assumptions"><span class="xref std std-term">optimistic assumptions</span></a>.
This means that rules without any explicit <code class="docutils literal notranslate"><span class="pre">assert</span></code> statements will not check the
<a class="reference internal" href="../user-guide/glossary.html#term-pessimistic-assertions"><span class="xref std std-term">pessimistic assertions</span></a>, i.e., the implicit assertions that we insert
in rules with <code class="docutils literal notranslate"><span class="pre">assert</span></code> statements when at least one of the “optimistic” flags
is not set. In order to trigger creation of a sub-rule that contains these
checks, users can insert an <code class="docutils literal notranslate"><span class="pre">assert</span> <span class="pre">true</span></code> statement into the rule. This assert
itself will never be violated, but the sub-rule we create for it will contain
all the pessimistic assertions for the program.</p>
</div>
<ul class="simple">
<li><p><a class="reference external" href="https://github.com/Certora/Examples/blob/14668d39a6ddc67af349bc5b82f73db73349ef18/CVLByExample/ConstantProductPool/certora/spec/ConstantProductPool.spec#L243"><code class="docutils literal notranslate"><span class="pre">satisfy</span></code> example</a></p></li>
</ul>
</section>
<section id="requireinvariant-statements">
<span id="requireinvariant"></span><h2><a class="toc-backref" href="#id23" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">requireInvariant</span></code> statements</a><a class="headerlink" href="#requireinvariant-statements" title="Link to this heading"></a></h2>
<p><code class="docutils literal notranslate"><span class="pre">requireInvariant</span></code> is shorthand for <code class="docutils literal notranslate"><span class="pre">require</span></code> of the expression of the invariant where the invariant parameters have to be substituted with the values/ variables for which the invariant should hold.</p>
<ul class="simple">
<li><p><a class="reference external" href="https://github.com/Certora/Examples/blob/14668d39a6ddc67af349bc5b82f73db73349ef18/CVLByExample/ConstantProductPool/certora/spec/ConstantProductPool.spec#L178"><code class="docutils literal notranslate"><span class="pre">requireInvariant</span></code> example</a></p></li>
</ul>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p><code class="docutils literal notranslate"><span class="pre">requireInvariant</span></code> is always safe for invariants that have been proved, even in
<code class="docutils literal notranslate"><span class="pre">preserved</span></code> blocks; see <a class="reference internal" href="invariants.html#invariant-induction"><span class="std std-ref">Invariants and induction</span></a> for a detailed explanation.</p>
</div>
</section>
<section id="havoc-statements">
<span id="havoc-stmt"></span><h2><a class="toc-backref" href="#id24" role="doc-backlink">Havoc Statements</a><a class="headerlink" href="#havoc-statements" title="Link to this heading"></a></h2>
<p>Havoc statements introduce non-determinism into the contract execution, allowing the SMT solver to choose random values for specific variables. Havoc statements are helpful for modeling uncertainty and verifying a wider range of possible scenarios.</p>
<section id="id1">
<h3><a class="toc-backref" href="#id25" role="doc-backlink">Syntax</a><a class="headerlink" href="#id1" title="Link to this heading"></a></h3>
<p>The syntax for a <code class="docutils literal notranslate"><span class="pre">havoc</span></code> statement is as follows:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell2"><span></span><span class="kr">havoc</span><span class="w"> </span>identifier<span class="w"> </span><span class="p">[</span><span class="w"> </span><span class="kr">assuming</span><span class="w"> </span>condition<span class="w"> </span><span class="p">];</span>
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
<li><p><strong><code class="docutils literal notranslate"><span class="pre">identifier</span></code>:</strong> The variable or expression for which non-deterministic values will be chosen.</p></li>
<li><p><strong><code class="docutils literal notranslate"><span class="pre">condition</span></code>:</strong> An optional condition that restricts the possible values for the havoc variable.</p></li>
</ul>
</section>
<section id="usage">
<h3><a class="toc-backref" href="#id26" role="doc-backlink">Usage</a><a class="headerlink" href="#usage" title="Link to this heading"></a></h3>
<section id="basic-havoc">
<h4><a class="toc-backref" href="#id27" role="doc-backlink">Basic Havoc</a><a class="headerlink" href="#basic-havoc" title="Link to this heading"></a></h4>
<p>The basic use of a havoc statement involves introducing non-deterministic values for a specific variable. This is useful when the exact value of a variable is unknown or when exploring various scenarios.</p>
<section id="example">
<h5><a class="toc-backref" href="#id28" role="doc-backlink">Example:</a><a class="headerlink" href="#example" title="Link to this heading"></a></h5>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell3"><span></span><span class="kt">uint256</span><span class="w"> </span>x<span class="p">;</span>
<span class="kr">havoc</span><span class="w"> </span>x<span class="p">;</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell3">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>In this example, the value of variable <code class="docutils literal notranslate"><span class="pre">x</span></code> is chosen randomly by the SMT solver.
<strong>Note:</strong> The havoc statement is not really necessary as unassigned values are havoc by default.</p>
</section>
</section>
<section id="havoc-with-condition">
<h4><a class="toc-backref" href="#id29" role="doc-backlink">Havoc with Condition</a><a class="headerlink" href="#havoc-with-condition" title="Link to this heading"></a></h4>
<p>Havoc statements can include a condition that restricts the possible values for the havoc variable. This allows for more fine-grained control over the non-deterministic choices made by the SMT solver.</p>
<section id="id2">
<h5><a class="toc-backref" href="#id30" role="doc-backlink">Example:</a><a class="headerlink" href="#id2" title="Link to this heading"></a></h5>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell4"><span></span><span class="kt">uint256</span><span class="w"> </span>y<span class="p">;</span>
<span class="kr">havoc</span><span class="w"> </span>y<span class="w"> </span><span class="kr">assuming</span><span class="w"> </span>y<span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="m m-Decimal">10</span><span class="p">;</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell4">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>In this example, the havoc statement introduces non-deterministic values for variable <code class="docutils literal notranslate"><span class="pre">y</span></code>, but only values greater than 10 are considered valid.</p>
<p><strong>Note:</strong> The above is equivalent to:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell5"><span></span><span class="kt">uint256</span><span class="w"> </span>y<span class="p">;</span>
<span class="kr">require</span><span class="w"> </span>y<span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">;</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell5">
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
<section id="two-state-contexts-old-and-new">
<h3><a class="toc-backref" href="#id31" role="doc-backlink">Two-State Contexts: <code class="docutils literal notranslate"><span class="pre">@old</span></code> and <code class="docutils literal notranslate"><span class="pre">@new</span></code></a><a class="headerlink" href="#two-state-contexts-old-and-new" title="Link to this heading"></a></h3>
<p>Two-state contexts, denoted by <code class="docutils literal notranslate"><span class="pre">@old</span></code> and <code class="docutils literal notranslate"><span class="pre">@new</span></code>, are essential when dealing with havoc statements. They provide a mechanism to reference the old and new states of a variable within the havoc statement, allowing for more nuanced control over the non-deterministic choices.</p>
<section id="id3">
<h4><a class="toc-backref" href="#id32" role="doc-backlink">Example:</a><a class="headerlink" href="#id3" title="Link to this heading"></a></h4>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell6"><span></span><span class="kr">havoc</span><span class="w"> </span>sumAllBalance<span class="w"> </span><span class="kr">assuming</span><span class="w"> </span>sumAllBalance<span class="ow">@new</span><span class="p">()</span><span class="w"> </span><span class="o">==</span><span class="w"> </span>sumAllBalance<span class="ow">@old</span><span class="p">()</span><span class="w"> </span><span class="o">+</span><span class="w"> </span>balance<span class="w"> </span><span class="o">-</span><span class="w"> </span>old_balance<span class="p">;</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell6">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>In the given example, the havoc statement introduces non-deterministic values for the variable <code class="docutils literal notranslate"><span class="pre">sumAllBalance</span></code>. The assuming clause adds a condition: the new state of <code class="docutils literal notranslate"><span class="pre">sumAllBalance</span></code> should be the old state plus the change in the balance variable.</p>
<p><code class="docutils literal notranslate"><span class="pre">sumAllBalance@new()</span></code>: Value in the updated state.
<code class="docutils literal notranslate"><span class="pre">sumAllBalance@old()</span></code>: Value in the previous state.
<code class="docutils literal notranslate"><span class="pre">balance</span> <span class="pre">-</span> <span class="pre">old_balance</span></code>: Change in the balance variable.</p>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p><a class="reference internal" href="hooks.html"><span class="doc">Hooks</span></a> will not be triggered for havoc statements. That is, if there is a hook defined on load, or store, of the <code class="docutils literal notranslate"><span class="pre">sumAllBalance</span></code> variable,
it will not be triggered from the havoc statement.</p>
</div>
</section>
</section>
<section id="advanced-usage-havoc-assuming">
<h3><a class="toc-backref" href="#id33" role="doc-backlink">Advanced Usage: <code class="docutils literal notranslate"><span class="pre">havoc</span> <span class="pre">assuming</span></code></a><a class="headerlink" href="#advanced-usage-havoc-assuming" title="Link to this heading"></a></h3>
<p>The <code class="docutils literal notranslate"><span class="pre">havoc</span> <span class="pre">assuming</span></code> construct allows introducing non-deterministic choices for variables while imposing specific conditions. This can be particularly useful for modeling complex scenarios where certain constraints must be satisfied.</p>
<section id="id4">
<h4><a class="toc-backref" href="#id34" role="doc-backlink">Example:</a><a class="headerlink" href="#id4" title="Link to this heading"></a></h4>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell7"><span></span><span class="kd">ghost</span><span class="w"> </span><span class="kt">uint256</span><span class="w"> </span>a<span class="p">;</span>
<span class="kd">ghost</span><span class="w"> </span><span class="kt">uint256</span><span class="w"> </span>b<span class="p">;</span>
<span class="k">rule</span><span class="w"> </span><span class="nc">example</span><span class="p">(){</span>
<span class="kr">havoc</span><span class="w"> </span>a<span class="w"> </span><span class="kr">assuming</span><span class="w"> </span>a<span class="ow">@new</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span>b<span class="p">;</span>
<span class="kr">havoc</span><span class="w"> </span>b<span class="w"> </span><span class="kr">assuming</span><span class="w"> </span>a<span class="w"> </span><span class="o">+</span><span class="w"> </span>b<span class="ow">@new</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="m m-Decimal">100</span><span class="p">;</span>
<span class="kr">assert</span><span class="w"> </span>a<span class="w"> </span><span class="o">&lt;</span><span class="w"> </span>b<span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span>a<span class="w"> </span><span class="o">+</span><span class="w"> </span>b<span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="m m-Decimal">100</span><span class="p">;</span>
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
<p>In this example, havoc statements are used to introduce non-deterministic values for ghosts <code class="docutils literal notranslate"><span class="pre">a</span></code> and <code class="docutils literal notranslate"><span class="pre">b</span></code> while ensuring that <code class="docutils literal notranslate"><span class="pre">a</span></code> is less than <code class="docutils literal notranslate"><span class="pre">b</span></code> and their sum is equal to 100.</p>
</section>
</section>
<section id="conclusion">
<h3><a class="toc-backref" href="#id35" role="doc-backlink">Conclusion</a><a class="headerlink" href="#conclusion" title="Link to this heading"></a></h3>
<p>Havoc statements play a critical role in making CVL specifications more expressive and capable of handling uncertainty. They widen the coverage of possible contract behaviors making verification more robust and comprehensive. Understanding two-state contexts (<code class="docutils literal notranslate"><span class="pre">@old</span></code> and <code class="docutils literal notranslate"><span class="pre">@new</span></code>) and the <code class="docutils literal notranslate"><span class="pre">havoc</span> <span class="pre">assuming</span></code> construct is useful for harnessing the full power of CVL, in particular when combined with ghosts.</p>
</section>
</section>
<section id="solidity-like-statements">
<span id="control-flow"></span><h2><a class="toc-backref" href="#id36" role="doc-backlink">Solidity-like Statements</a><a class="headerlink" href="#solidity-like-statements" title="Link to this heading"></a></h2>
<p>Solidity-like statements provide a familiar syntax for expressing conditions and behaviors similar to Solidity, These statements enhance the readability and ease of writing specifications by adopting a syntax that resembles Solidity.</p>
<section id="assert-statement">
<h3><a class="toc-backref" href="#id37" role="doc-backlink">1. Assert Statement</a><a class="headerlink" href="#assert-statement" title="Link to this heading"></a></h3>
<section id="id5">
<h4><a class="toc-backref" href="#id38" role="doc-backlink">Syntax:</a><a class="headerlink" href="#id5" title="Link to this heading"></a></h4>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell8"><span></span><span class="kr">assert</span><span class="w"> </span>condition<span class="p">;</span>
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
<section id="id6">
<h4><a class="toc-backref" href="#id39" role="doc-backlink">Usage:</a><a class="headerlink" href="#id6" title="Link to this heading"></a></h4>
<p>The <code class="docutils literal notranslate"><span class="pre">assert</span></code> statement is used to assert a condition that must be true during the execution of the contract. If the condition evaluates to false, it will trigger a verification failure.</p>
<section id="id7">
<h5><a class="toc-backref" href="#id40" role="doc-backlink">Example:</a><a class="headerlink" href="#id7" title="Link to this heading"></a></h5>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell9"><span></span><span class="kt">uint256</span><span class="w"> </span>balance<span class="p">;</span>
<span class="kr">assert</span><span class="w"> </span>balance<span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">;</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell9">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>In this example, the <code class="docutils literal notranslate"><span class="pre">assert</span></code> statement ensures that the balance variable is positive.</p>
</section>
</section>
</section>
<section id="require-statement">
<h3><a class="toc-backref" href="#id41" role="doc-backlink">2. Require Statement</a><a class="headerlink" href="#require-statement" title="Link to this heading"></a></h3>
<section id="id8">
<h4><a class="toc-backref" href="#id42" role="doc-backlink">Syntax:</a><a class="headerlink" href="#id8" title="Link to this heading"></a></h4>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell10"><span></span><span class="kr">require</span><span class="w"> </span>condition<span class="p">;</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell10">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
<section id="id9">
<h4><a class="toc-backref" href="#id43" role="doc-backlink">Usage:</a><a class="headerlink" href="#id9" title="Link to this heading"></a></h4>
<p>The <code class="docutils literal notranslate"><span class="pre">require</span></code> statement is similar to the <code class="docutils literal notranslate"><span class="pre">assert</span></code> statement but is used for expressing preconditions that must be satisfied for the execution to continue. Values that make the condition evaluate to false will not be considered as violations of a later <code class="docutils literal notranslate"><span class="pre">assert</span></code> statement or witnesses to a later <code class="docutils literal notranslate"><span class="pre">satisfy</span></code> statement.</p>
<section id="id10">
<h5><a class="toc-backref" href="#id44" role="doc-backlink">Example:</a><a class="headerlink" href="#id10" title="Link to this heading"></a></h5>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell11"><span></span><span class="kt">uint256</span><span class="w"> </span>amount<span class="p">;</span>
<span class="kr">require</span><span class="w"> </span>amount<span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">;</span>
<span class="kr">satisfy</span><span class="w"> </span>amount<span class="w"> </span><span class="o">&gt;=</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">;</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell11">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>Here, the <code class="docutils literal notranslate"><span class="pre">require</span></code> statement ensures that the <code class="docutils literal notranslate"><span class="pre">amount</span></code> must be greater than zero. This means there cannot be a witness of the <code class="docutils literal notranslate"><span class="pre">satisfy</span></code> command with <code class="docutils literal notranslate"><span class="pre">amount</span></code> equal to zero.</p>
</section>
</section>
</section>
<section id="modeling-reverts-in-solidity-calls">
<h3><a class="toc-backref" href="#id45" role="doc-backlink">3. Modeling Reverts in Solidity Calls</a><a class="headerlink" href="#modeling-reverts-in-solidity-calls" title="Link to this heading"></a></h3>
<p>The default method of calling Solidity functions within CVL is to assume they do not revert.
This behavior can be adjusted with the <code class="docutils literal notranslate"><span class="pre">@withrevert</span></code> modifier.
After every Solidity call, even if it is not marked with <code class="docutils literal notranslate"><span class="pre">@withrevert</span></code>, a builtin variable called <code class="docutils literal notranslate"><span class="pre">lastReverted</span></code> is updated according to whether the Solidity call reverted or not.</p>
<p>Note: For calls without <code class="docutils literal notranslate"><span class="pre">@withrevert</span></code>, <code class="docutils literal notranslate"><span class="pre">lastReverted</span></code> is automatically set to to false.</p>
<section id="id11">
<h4><a class="toc-backref" href="#id46" role="doc-backlink">Syntax:</a><a class="headerlink" href="#id11" title="Link to this heading"></a></h4>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell12"><span></span>f<span class="ow">@withrevert</span><span class="p">(</span>args<span class="p">);</span>
<span class="kr">assert</span><span class="w"> </span><span class="o">!</span><span class="nb">lastReverted</span><span class="p">;</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell12">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>In this example, we call to <code class="docutils literal notranslate"><span class="pre">f</span></code> without pruning the reverting paths, and then we assert that the call to <code class="docutils literal notranslate"><span class="pre">f</span></code> did not revert on any given input.</p>
<section id="id12">
<h5><a class="toc-backref" href="#id47" role="doc-backlink">Example:</a><a class="headerlink" href="#id12" title="Link to this heading"></a></h5>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell13"><span></span><span class="kt">uint256</span><span class="w"> </span>limit<span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="m m-Decimal">100</span><span class="p">;</span>
<span class="kt">uint256</span><span class="w"> </span>value<span class="p">;</span>
<span class="kr">require</span><span class="w"> </span>value<span class="w"> </span><span class="o">&gt;</span><span class="w"> </span>limit<span class="p">;</span>
Deposit<span class="ow">@withrevert</span><span class="p">(</span>value<span class="p">);</span>
<span class="kr">assert</span><span class="w"> </span><span class="nb">lastReverted</span><span class="p">,</span><span class="w"> </span><span class="s2">"Expected revert when value exceeds limit"</span><span class="p">;</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell13">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>In this example, the <code class="docutils literal notranslate"><span class="pre">@withrevert</span></code> modifier is applied to the <code class="docutils literal notranslate"><span class="pre">Deposit</span></code> function call, which is expected to revert if the <code class="docutils literal notranslate"><span class="pre">value</span></code> exceeds the specified <code class="docutils literal notranslate"><span class="pre">limit</span></code>. The <code class="docutils literal notranslate"><span class="pre">assert</span></code> statement checks whether <code class="docutils literal notranslate"><span class="pre">lastReverted</span></code> is true, ensuring that the contract execution does revert as anticipated when the condition is violated. The error message in the <code class="docutils literal notranslate"><span class="pre">assert</span></code> provides additional context about the expectation.</p>
</section>
</section>
</section>
<section id="return-statement">
<h3><a class="toc-backref" href="#id48" role="doc-backlink">4. Return Statement</a><a class="headerlink" href="#return-statement" title="Link to this heading"></a></h3>
<section id="id13">
<h4><a class="toc-backref" href="#id49" role="doc-backlink">Syntax:</a><a class="headerlink" href="#id13" title="Link to this heading"></a></h4>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell14"><span></span><span class="kr">return</span><span class="w"> </span>expression<span class="p">;</span>
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
<section id="id14">
<h4><a class="toc-backref" href="#id50" role="doc-backlink">Usage:</a><a class="headerlink" href="#id14" title="Link to this heading"></a></h4>
<p>The <code class="docutils literal notranslate"><span class="pre">return</span></code> statement is used to terminate the execution of a function and return a value. It can only be used in functions to specify the value to be returned.</p>
<section id="id15">
<h5><a class="toc-backref" href="#id51" role="doc-backlink">Example:</a><a class="headerlink" href="#id15" title="Link to this heading"></a></h5>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell15"><span></span><span class="kt">function</span><span class="w"> </span><span class="nf">calculateSum</span><span class="p">(</span><span class="kt">uint256</span><span class="w"> </span>a<span class="p">,</span><span class="w"> </span><span class="kt">uint256</span><span class="w"> </span>b<span class="p">)</span><span class="w"> </span><span class="kr">returns</span><span class="w"> </span><span class="p">(</span><span class="kt">uint256</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kr">return</span><span class="w"> </span>a<span class="w"> </span><span class="o">+</span><span class="w"> </span>b<span class="p">;</span>
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
<p>This example defines a function <code class="docutils literal notranslate"><span class="pre">calculateSum</span></code> that takes two parameters and returns their sum.</p>
</section>
</section>
</section>
<section id="id16">
<h3><a class="toc-backref" href="#id52" role="doc-backlink">Conclusion</a><a class="headerlink" href="#id16" title="Link to this heading"></a></h3>
<p>Solidity-like statements in CVL simplify the process of writing specifications by using a syntax that closely resembles Solidity. These statements align with the familiar patterns and structures used in Solidity smart contracts, making it easier for developers and auditors to express and verify the desired behaviors and conditions in a contract. Understanding and using these statements contributes to more readable and expressive CVL specifications.</p>
</section>
</section>
</section>


           </div>
          </div>
          <footer><div class="rst-footer-buttons" role="navigation" aria-label="Footer">
        <a href="expr.html" class="btn btn-neutral float-left" title="Expressions" accesskey="p" rel="prev"><span class="fa fa-arrow-circle-left" aria-hidden="true"></span> Previous</a>
        <a href="imports.html" class="btn btn-neutral float-right" title="Import and Use Statements" accesskey="n" rel="next">Next <span class="fa fa-arrow-circle-right" aria-hidden="true"></span></a>
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