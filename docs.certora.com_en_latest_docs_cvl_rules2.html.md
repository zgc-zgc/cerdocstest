<!DOCTYPE html><html class="writer-html5" lang="en" data-content_root="../../"><head>
  <meta charset="utf-8"><meta name="viewport" content="width=device-width, initial-scale=1">

  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Rules — Certora Prover Documentation 0.0 documentation</title>
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
    <link rel="next" title="Built-in Rules" href="builtin.html">
    <link rel="prev" title="The Methods Block" href="methods.html"> 
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
<li class="toctree-l2 current" aria-expanded="true"><a class="reference internal current" href="#" aria-expanded="true"><button class="toctree-expand" title="Open/close menu"></button>Rules</a><ul>
<li class="toctree-l3"><a class="reference internal" href="#syntax">Syntax</a></li>
<li class="toctree-l3"><a class="reference internal" href="#overview">Overview</a></li>
<li class="toctree-l3"><a class="reference internal" href="#parametric-rules">Parametric rules</a></li>
<li class="toctree-l3"><a class="reference internal" href="#filters">Filters</a></li>
<li class="toctree-l3"><a class="reference internal" href="#multiple-assertions">Multiple assertions</a></li>
<li class="toctree-l3"><a class="reference internal" href="#rule-descriptions">Rule descriptions</a></li>
<li class="toctree-l3"><a class="reference internal" href="#how-rules-are-verified">How rules are verified</a></li>
</ul>
</li>
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
      <li class="breadcrumb-item active">Rules</li>
      <li class="wy-breadcrumbs-aside">
            <a href="../../_sources/docs/cvl/rules.md.txt" rel="nofollow"> View page source</a>
      </li>
  </ul>
  <hr>
</div>
          <div role="main" class="document" itemscope="itemscope" itemtype="http://schema.org/Article">
           <div itemprop="articleBody">
             
  <section id="rules">
<span id="rules-main"></span><h1><a class="toc-backref" href="#id2" role="doc-backlink">Rules</a><a class="headerlink" href="#rules" title="Link to this heading"></a></h1>
<p>Rules (along with <a class="reference internal" href="invariants.html"><span class="doc">Invariants</span></a>) are the main entry points for the Prover.
A rule defines a sequence of <a class="reference internal" href="statements.html"><span class="doc std std-doc">commands</span></a> that should be simulated
during verification.</p>
<p>When the Prover is invoked with the <a class="reference internal" href="../prover/cli/options.html#verify"><span class="std std-ref">verify</span></a> option, it generates a
report for each rule and invariant present in the spec file (as well as any
<a class="reference internal" href="imports.html#use"><span class="std std-ref">imported rules</span></a>).</p>
<p>You can find examples for rules in the
<a class="reference external" href="https://github.com/Certora/Examples/">Certora Prover and CVL Examples Repository</a>.
For example, the specs in <a class="reference external" href="https://github.com/Certora/Examples/tree/7dfc379423202c90cf284eb42800b97cf5c95d83/CVLByExample/Teams">/CVLByExample/Teams/</a> demonstrate some of
these features.</p>
<nav class="contents" id="contents">
<p class="topic-title">Contents</p>
<ul class="simple">
<li><p><a class="reference internal" href="#rules" id="id2">Rules</a></p>
<ul>
<li><p><a class="reference internal" href="#syntax" id="id3">Syntax</a></p></li>
<li><p><a class="reference internal" href="#overview" id="id4">Overview</a></p></li>
<li><p><a class="reference internal" href="#parametric-rules" id="id5">Parametric rules</a></p></li>
<li><p><a class="reference internal" href="#filters" id="id6">Filters</a></p></li>
<li><p><a class="reference internal" href="#multiple-assertions" id="id7">Multiple assertions</a></p></li>
<li><p><a class="reference internal" href="#rule-descriptions" id="id8">Rule descriptions</a></p></li>
<li><p><a class="reference internal" href="#how-rules-are-verified" id="id9">How rules are verified</a></p></li>
</ul>
</li>
</ul>
</nav>
<section id="syntax">
<h2><a class="toc-backref" href="#id3" role="doc-backlink">Syntax</a><a class="headerlink" href="#syntax" title="Link to this heading"></a></h2>
<p>The syntax for rules is given by the following <a class="reference internal" href="overview.html#ebnf-syntax"><span class="std std-ref">EBNF grammar</span></a>:</p>
<div class="highlight-default notranslate"><div class="highlight"><pre id="codecell0"><span></span><span class="n">rule</span> <span class="p">:</span><span class="o">:=</span> <span class="p">[</span> <span class="s2">"rule"</span> <span class="p">]</span>
         <span class="nb">id</span>
         <span class="p">[</span> <span class="s2">"("</span> <span class="p">[</span> <span class="n">params</span> <span class="p">]</span> <span class="s2">")"</span> <span class="p">]</span>
         <span class="p">[</span> <span class="s2">"filtered"</span> <span class="s2">"{"</span> <span class="nb">id</span> <span class="s2">"-&gt;"</span> <span class="n">expression</span> <span class="p">{</span> <span class="s2">","</span> <span class="nb">id</span> <span class="s2">"-&gt;"</span> <span class="n">expression</span> <span class="p">}</span> <span class="s2">"}"</span> <span class="p">]</span>
         <span class="p">[</span> <span class="s2">"description"</span> <span class="n">string</span> <span class="p">]</span>
         <span class="p">[</span> <span class="s2">"good_description"</span> <span class="n">string</span> <span class="p">]</span>
         <span class="n">block</span>

<span class="n">params</span> <span class="p">:</span><span class="o">:=</span> <span class="n">cvl_type</span> <span class="p">[</span> <span class="nb">id</span> <span class="p">]</span> <span class="p">{</span> <span class="s2">","</span> <span class="n">cvl_type</span> <span class="p">[</span> <span class="nb">id</span> <span class="p">]</span> <span class="p">}</span>

</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell0">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>See <a class="reference internal" href="basics.html"><span class="doc">Basic Syntax</span></a> for the <code class="docutils literal notranslate"><span class="pre">id</span></code> and <code class="docutils literal notranslate"><span class="pre">string</span></code> productions; see <a class="reference internal" href="expr.html"><span class="doc">Expressions</span></a> for the <code class="docutils literal notranslate"><span class="pre">expression</span></code>
production; see <a class="reference internal" href="types.html"><span class="doc">Types</span></a> for the <code class="docutils literal notranslate"><span class="pre">cvl_type</span></code> production.</p>
</section>
<section id="overview">
<span id="rule-overview"></span><h2><a class="toc-backref" href="#id4" role="doc-backlink">Overview</a><a class="headerlink" href="#overview" title="Link to this heading"></a></h2>
<p>A rule defines a sequence of commands that should be simulated during
verification.  These commands may be non-deterministic: they may contain
<a class="reference internal" href="statements.html#declarations"><span class="std std-ref">unassigned variables</span></a> whose value is not specified.  The
state of storage at the beginning of a rule is also unspecified.  Rules may also
be declared with a set of parameters; these parameters are treated the same way
as undeclared variables.</p>
<p>In principal, the Prover will generate every possible combination of values for
the undefined variables, and simulate the commands in the rule using those
values.  A particular combination of values is referred to as an <a class="reference internal" href="../user-guide/glossary.html#term-example"><span class="xref std std-term">example</span></a> or a
<a class="reference internal" href="../user-guide/glossary.html#term-model"><span class="xref std std-term">model</span></a>.  There are often an infinite number of models for a given rule; see
<a class="reference internal" href="#verification"><span class="std std-ref">How rules are verified</span></a> for a brief explanation of how the Prover considers all of
them.</p>
<p>If a rule contains a <code class="docutils literal notranslate"><span class="pre">require</span></code> statement that fails on a particular example,
the example is ignored.  Of the remaining examples, the Prover checks that all
of the <code class="docutils literal notranslate"><span class="pre">assert</span></code> statements evaluate to true.  If all of the <code class="docutils literal notranslate"><span class="pre">assert</span></code> statements
evaluate to true on every example, the rule passes.  Otherwise, the Prover will
output a specific counterexample that causes the assertions to fail.</p>
<ul>
<li><p><a class="reference external" href="https://github.com/Certora/Examples/blob/14668d39a6ddc67af349bc5b82f73db73349ef18/CVLByExample/LiquidityPool/certora/specs/pool.spec#L54">simple rule example</a></p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell1"><span></span><span class="c1">/// `deposit` must increase the pool's underlying asset balance</span>
<span class="k">rule</span><span class="w"> </span><span class="nc">integrityOfDeposit</span><span class="w"> </span><span class="p">{</span>

<span class="w">    </span><span class="kt">mathint</span><span class="w"> </span>balance_before<span class="w"> </span><span class="o">=</span><span class="w"> </span>underlyingBalance<span class="p">();</span>


<span class="w">    </span><span class="kt">env</span><span class="w"> </span>e<span class="p">;</span><span class="w"> </span><span class="kt">uint256</span><span class="w"> </span>amount<span class="p">;</span>
<span class="w">    </span>safeAssumptions<span class="p">(</span>_<span class="p">,</span><span class="w"> </span>e<span class="p">);</span>

<span class="w">    </span>deposit<span class="p">(</span>e<span class="p">,</span><span class="w"> </span>amount<span class="p">);</span>

<span class="w">    </span><span class="kt">mathint</span><span class="w"> </span>balance_after<span class="w"> </span><span class="o">=</span><span class="w"> </span>underlyingBalance<span class="p">();</span>

<span class="w">    </span><span class="kr">assert</span><span class="w"> </span>balance_after<span class="w"> </span><span class="o">==</span><span class="w"> </span>balance_before<span class="w"> </span><span class="o">+</span><span class="w"> </span>amount<span class="p">,</span>
<span class="w">        </span><span class="s2">"deposit must increase the underlying balance of the pool"</span><span class="p">;</span>
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
</li>
</ul>
<div class="admonition caution">
<p class="admonition-title">Caution</p>
<p><code class="docutils literal notranslate"><span class="pre">assert</span></code> statements in contract code are handled differently from <code class="docutils literal notranslate"><span class="pre">assert</span></code>
statements in rules.</p>
<p>An <code class="docutils literal notranslate"><span class="pre">assert</span></code> statement in Solidity causes the transaction to revert, in the same
way that a <code class="docutils literal notranslate"><span class="pre">require</span></code> statement in Solidity would.  By default, examples that
cause contract functions to revert are <a class="reference internal" href="expr.html#with-revert"><span class="std std-ref">ignored by the prover</span></a>, and these examples will <em>not</em> be reported as counterexamples.</p>
<p>The <a class="reference internal" href="../prover/cli/options.html#multi-assert-check"><span class="std std-ref">multi_assert_check</span></a> option causes assertions in the contract code
to be reported as counterexamples.</p>
</div>
</section>
<section id="parametric-rules">
<span id="id1"></span><h2><a class="toc-backref" href="#id5" role="doc-backlink">Parametric rules</a><a class="headerlink" href="#parametric-rules" title="Link to this heading"></a></h2>
<p>Rules that contain undefined <code class="docutils literal notranslate"><span class="pre">method</span></code> variables are sometimes called
<a class="reference internal" href="../user-guide/glossary.html#term-parametric-rule"><span class="xref std std-term">parametric rule</span></a>s.  See <a class="reference internal" href="types.html#method-type"><span class="std std-ref">The method and calldataarg types</span></a> for more details about
how to use method variables.</p>
<p>Undefined variables of the <code class="docutils literal notranslate"><span class="pre">method</span></code> type are treated slightly differently from
undefined variables of other types.  If a rule uses one or more undefined
<code class="docutils literal notranslate"><span class="pre">method</span></code> variables, the Prover will generate a separate report for each method
(or combination of methods).</p>
<p>In particular, the Prover will generate a separate counterexample for each
method that violates the rule, and will indicate if some contract methods
always satisfy the rule.</p>
<p>You can request that the Prover only run with specific methods using the
<a class="reference internal" href="../prover/cli/options.html#method"><span class="std std-ref">method</span></a> and <a class="reference internal" href="../prover/cli/options.html#parametric-contracts"><span class="std std-ref">parametric_contracts</span></a> command line arguments.  The set of
methods can also be restricted using <a class="reference internal" href="#rule-filters"><span class="std std-ref">rule filters</span></a>.
The Prover will automatically skip any methods that have
<a class="reference internal" href="methods.html#delete-summary"><span class="std std-ref"> `DELETE` summaries</span></a>.</p>
<p>If you wish to only invoke methods on a certain contract, you can call the
<code class="docutils literal notranslate"><span class="pre">method</span></code> variable with an explicit receiver contract.  The receiver must be a
contract variable (either <a class="reference internal" href="expr.html#currentcontract"><span class="std std-ref">currentContract</span></a> or a variable introduced with a
<code class="docutils literal notranslate"><span class="pre">using</span></code> statement).  For example, the following will only verify the rule <code class="docutils literal notranslate"><span class="pre">r</span></code>
on methods of the contract <code class="docutils literal notranslate"><span class="pre">example</span></code>:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell2"><span></span><span class="kn">using</span><span class="w"> </span>Example<span class="w"> </span><span class="kn">as</span><span class="w"> </span>example<span class="p">;</span>

<span class="k">rule</span><span class="w"> </span><span class="nc">r</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kt">method</span><span class="w"> </span>f<span class="p">;</span><span class="w"> </span><span class="kt">env</span><span class="w"> </span>e<span class="p">;</span><span class="w"> </span><span class="kt">calldataarg</span><span class="w"> </span>args<span class="p">;</span>
<span class="w">    </span>example<span class="p">.</span>f<span class="p">(</span>e<span class="p">,</span>args<span class="p">);</span>
<span class="w">    </span><span class="p">...</span>
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
<p>It is an error to call the same <code class="docutils literal notranslate"><span class="pre">method</span></code> variable on two different contracts.</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell3"><span></span><span class="w">  </span><span class="k">rule</span><span class="w"> </span><span class="nc">sanity</span><span class="p">(</span><span class="kt">method</span><span class="w"> </span>f<span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kt">env</span><span class="w"> </span>e<span class="p">;</span>
<span class="w">    </span><span class="kt">calldataarg</span><span class="w"> </span>args<span class="p">;</span>
<span class="w">    </span>f<span class="p">(</span>e<span class="p">,</span>args<span class="p">);</span>
<span class="w">    </span><span class="kr">assert</span><span class="w"> </span><span class="kr">false</span><span class="p">;</span>
<span class="w">    </span><span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell3">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<ul class="simple">
<li><p><a class="reference external" href="https://github.com/Certora/Examples/blob/14668d39a6ddc67af349bc5b82f73db73349ef18/CVLByExample/structs/BankAccounts/certora/specs/Bank.spec#L94">parameteric rule example</a></p></li>
</ul>
</section>
<section id="filters">
<span id="rule-filters"></span><h2><a class="toc-backref" href="#id6" role="doc-backlink">Filters</a><a class="headerlink" href="#filters" title="Link to this heading"></a></h2>
<p>A rule declaration may have a <code class="docutils literal notranslate"><span class="pre">filtered</span></code> block after the rule parameters.
Rule filters allow you to prevent verification of parametric rules on certain
methods.  This can be less computationally expensive than using a <code class="docutils literal notranslate"><span class="pre">require</span></code>
statement to ignore counterexamples for a method.</p>
<p>The <code class="docutils literal notranslate"><span class="pre">filtered</span></code> block consists of zero or more filters of the form <code class="docutils literal notranslate"><span class="pre">var</span> <span class="pre">-&gt;</span> <span class="pre">expr</span></code>.
<code class="docutils literal notranslate"><span class="pre">var</span></code> must match one of the <code class="docutils literal notranslate"><span class="pre">method</span></code> parameters to the rule, and <code class="docutils literal notranslate"><span class="pre">expr</span></code> must be
a boolean expression that may refer to the variable <code class="docutils literal notranslate"><span class="pre">var</span></code>.  The filter
expression may not refer to other method parameters or any variables defined in
the rule.</p>
<p>Before verifying that a method <code class="docutils literal notranslate"><span class="pre">m</span></code> satisfies a parametric rule, the <code class="docutils literal notranslate"><span class="pre">expr</span></code> is
evaluated with <code class="docutils literal notranslate"><span class="pre">var</span></code> bound to a <code class="docutils literal notranslate"><span class="pre">method</span></code> object.  This allows <code class="docutils literal notranslate"><span class="pre">expr</span></code> to refer
to the fields of <code class="docutils literal notranslate"><span class="pre">var</span></code>, such as <code class="docutils literal notranslate"><span class="pre">var.selector</span></code> and <code class="docutils literal notranslate"><span class="pre">var.isView</span></code>.  See
<a class="reference internal" href="types.html#method-type"><span class="std std-ref">The method and calldataarg types</span></a> for a list of the fields available on <code class="docutils literal notranslate"><span class="pre">method</span></code> objects.</p>
<p>For example, the following rule has two filters.  The rule will only be
verified with <code class="docutils literal notranslate"><span class="pre">f</span></code> instantiated by a view method, and <code class="docutils literal notranslate"><span class="pre">g</span></code> instantiated by a
method other than <code class="docutils literal notranslate"><span class="pre">exampleMethod(uint,uint)</span></code> or <code class="docutils literal notranslate"><span class="pre">otherExample(address)</span></code>:</p>
<ul class="simple">
<li><p><a class="reference external" href="https://github.com/Certora/Examples/blob/14668d39a6ddc67af349bc5b82f73db73349ef18/CVLByExample/Reentrancy/certora/spec/Reentrancy.spec#L29C9-L29C9">filters example</a></p></li>
</ul>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell4"><span></span><span class="k">rule</span><span class="w"> </span><span class="nc">r</span><span class="p">(</span><span class="kt">method</span><span class="w"> </span>f<span class="p">,</span><span class="w"> </span><span class="kt">method</span><span class="w"> </span>g<span class="p">)</span><span class="w"> </span><span class="kr">filtered</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span>f<span class="w"> </span><span class="o">-&gt;</span><span class="w"> </span>f<span class="p">.</span>isView<span class="p">,</span>
<span class="w">    </span>g<span class="w"> </span><span class="o">-&gt;</span><span class="w"> </span>g<span class="p">.</span><span class="nb">selector</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span>exampleMethod<span class="p">(</span><span class="kt">uint</span><span class="p">,</span><span class="kt">uint</span><span class="p">).</span><span class="nb">selector</span>
<span class="w">      </span><span class="o">&amp;&amp;</span><span class="w"> </span>g<span class="p">.</span><span class="nb">selector</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span>otherExample<span class="p">(</span><span class="kt">address</span><span class="p">).</span><span class="nb">selector</span>
<span class="p">}</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="c1">// rule body</span>
<span class="w">    </span><span class="p">...</span>
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
<p>See <a class="reference internal" href="types.html#method-type"><span class="std std-ref">The method and calldataarg types</span></a> for a list of the fields of the <code class="docutils literal notranslate"><span class="pre">method</span></code> type.</p>
</section>
<section id="multiple-assertions">
<h2><a class="toc-backref" href="#id7" role="doc-backlink">Multiple assertions</a><a class="headerlink" href="#multiple-assertions" title="Link to this heading"></a></h2>
<p>Rules may contain multiple assertions.  By default, if any assertion fails, the
Prover will report that the entire rule failed and give a counterexample that
causes one of the assertions to fail.</p>
<p>Occasionally it is useful to consider different assert statements in a rule
separately.  With the <a class="reference internal" href="../prover/cli/options.html#multi-assert-check"><span class="std std-ref">multi_assert_check</span></a> option, the Prover will try
to generate separate counterexamples for each <code class="docutils literal notranslate"><span class="pre">assert</span></code> statement.   The
counterexamples generated for a particular <code class="docutils literal notranslate"><span class="pre">assert</span></code> statement will pass all
earlier <code class="docutils literal notranslate"><span class="pre">assert</span></code> statements.</p>
</section>
<section id="rule-descriptions">
<h2><a class="toc-backref" href="#id8" role="doc-backlink">Rule descriptions</a><a class="headerlink" href="#rule-descriptions" title="Link to this heading"></a></h2>
<p>Rules may be annotated by writing <code class="docutils literal notranslate"><span class="pre">description</span></code> and/or <code class="docutils literal notranslate"><span class="pre">good_description</span></code> before
the method body, followed by a string.  These strings are displayed in the
verification report.</p>
</section>
<section id="how-rules-are-verified">
<span id="verification"></span><h2><a class="toc-backref" href="#id9" role="doc-backlink">How rules are verified</a><a class="headerlink" href="#how-rules-are-verified" title="Link to this heading"></a></h2>
<p>While verifying a rule, the Prover does not actually enumerate every possible
example and run the rule on the example.  Instead, the Prover translates the
contract code and the rule into a logical formula with logical variables
representing the unspecified variables from the rule.</p>
<p>The logical formula is designed so that if a particular example satisfies the
requirements and also causes an assertion to fail, then the formula will
evaluate to <code class="docutils literal notranslate"><span class="pre">true</span></code> on that example; otherwise the formula will evaluate
to false.</p>
<p>The Prover then uses off-the-shelf software called an SMT solver to determine
whether there are any examples that cause the formula to evaluate to true.  If
there are, the SMT solver provides an example to the Prover, which then
translates it into an example for the user.  If the SMT solver reports that the
formula is unsatisfiable, then we are guaranteed that whenever the <code class="docutils literal notranslate"><span class="pre">require</span></code>
statements are true, the <code class="docutils literal notranslate"><span class="pre">assert</span></code> statements are also true.</p>
</section>
</section>


           </div>
          </div>
          <footer><div class="rst-footer-buttons" role="navigation" aria-label="Footer">
        <a href="methods.html" class="btn btn-neutral float-left" title="The Methods Block" accesskey="p" rel="prev"><span class="fa fa-arrow-circle-left" aria-hidden="true"></span> Previous</a>
        <a href="builtin.html" class="btn btn-neutral float-right" title="Built-in Rules" accesskey="n" rel="next">Next <span class="fa fa-arrow-circle-right" aria-hidden="true"></span></a>
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