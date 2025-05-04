<!DOCTYPE html><html class="writer-html5" lang="en" data-content_root="../../"><head>
  <meta charset="utf-8"><meta name="viewport" content="width=device-width, initial-scale=1">

  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Specification Files — Certora Prover Documentation 0.0 documentation</title>
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
    <link rel="next" title="Basic Syntax" href="basics.html">
    <link rel="prev" title="The Certora Verification Language" href="index.html"> 
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
<li class="toctree-l2 current" aria-expanded="true"><a class="reference internal current" href="#" aria-expanded="true"><button class="toctree-expand" title="Open/close menu"></button>Specification Files</a><ul>
<li class="toctree-l3"><a class="reference internal" href="#syntactic-conventions">Syntactic Conventions</a></li>
</ul>
</li>
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
      <li class="breadcrumb-item active">Specification Files</li>
      <li class="wy-breadcrumbs-aside">
            <a href="../../_sources/docs/cvl/overview.md.txt" rel="nofollow"> View page source</a>
      </li>
  </ul>
  <hr>
</div>
          <div role="main" class="document" itemscope="itemscope" itemtype="http://schema.org/Article">
           <div itemprop="articleBody">
             
  <section id="specification-files">
<h1>Specification Files<a class="headerlink" href="#specification-files" title="Link to this heading"></a></h1>
<p>The Certora Prover verifies that a smart contract satisfies a set of rules
written in a language called Certora Verification Language (CVL).  The syntax
of CVL is similar to Solidity, but CVL contains additional features
that are useful for writing specifications.</p>
<p>A spec may contain any of the following:</p>
<ul class="simple">
<li><p><strong><a class="reference internal" href="imports.html"><span class="doc std std-doc">Import statements</span></a>:</strong> CVL files can import the contents of other CVL files.</p></li>
<li><p><strong><a class="reference internal" href="imports.html"><span class="doc std std-doc">Use statements</span></a>:</strong> A <code class="docutils literal notranslate"><span class="pre">use</span></code> statement instructs the Certora Prover to check
a rule that is imported from another spec or from the built-in rules.</p></li>
<li><p><strong><a class="reference internal" href="using.html"><span class="doc std std-doc">Using statements</span></a>:</strong> Using statements allow a specification to reference
multiple contracts.</p></li>
<li><p><strong><a class="reference internal" href="methods.html"><span class="doc std std-doc">Methods blocks</span></a>:</strong> <code class="docutils literal notranslate"><span class="pre">methods</span></code> blocks contain information on how methods
should be summarized by the Prover during verification.</p></li>
<li><p><strong><a class="reference internal" href="rules.html#rules-main"><span class="std std-ref">Rules</span></a>:</strong> A rule describes the expected behavior of the methods of a
contract.</p></li>
<li><p><strong><a class="reference internal" href="invariants.html#invariants"><span class="std std-ref">Invariants</span></a>:</strong> Invariants describe facts about the state of a contract that
should always be true.</p></li>
<li><p><strong><a class="reference internal" href="functions.html"><span class="doc std std-doc">Functions</span></a>:</strong> CVL functions contain CVL code that can be reused throughout the spec.</p></li>
<li><p><strong><a class="reference internal" href="defs.html"><span class="doc std std-doc">Definitions</span></a>:</strong> CVL definitions contain CVL expressions that can be reused throughout the spec.</p></li>
<li><p><strong><a class="reference internal" href="sorts.html"><span class="doc std std-doc">Sorts</span></a>:</strong> Sorts define simple types that can be compared for equality.</p></li>
<li><p><strong><a class="reference internal" href="ghosts.html#ghosts-doc"><span class="std std-ref">Ghosts</span></a>:</strong> Ghosts define additional variables that can be used to keep track
of state changes in the contracts.</p></li>
<li><p><strong><a class="reference internal" href="hooks.html#hooks"><span class="std std-ref">Hooks</span></a>:</strong> Hooks allow the specification to instrument the contracts being
verified to insert additional CVL code when various instructions are executed.</p></li>
</ul>
<p>The remainder of this chapter describes the syntax and semantics of a
specification file in detail.</p>
<section id="syntactic-conventions">
<span id="ebnf-syntax"></span><h2>Syntactic Conventions<a class="headerlink" href="#syntactic-conventions" title="Link to this heading"></a></h2>
<p>Many of the pages in this guide describe the syntax of parts of the Certora
Verification Language using a modified version of the <a class="reference external" href="https://en.wikipedia.org/wiki/Extended_Backus%E2%80%93Naur_form">EBNF format</a>.</p>
<p>When reading the syntax blocks, keep the following in mind:</p>
<ul class="simple">
<li><p>Text in double quotes is a terminal that matches the exact string.
For example, <code class="docutils literal notranslate"><span class="pre">"ghost"</span></code> matches <code class="docutils literal notranslate"><span class="pre">ghost</span></code>, and <code class="docutils literal notranslate"><span class="pre">"."</span></code> matches <code class="docutils literal notranslate"><span class="pre">.</span></code></p></li>
<li><p>Names that are not in double quotes are nonterminals that refers to other
parts of the grammar.  For example, <code class="docutils literal notranslate"><span class="pre">number</span></code> matches <code class="docutils literal notranslate"><span class="pre">1</span></code> or <code class="docutils literal notranslate"><span class="pre">2</span></code> or <code class="docutils literal notranslate"><span class="pre">372</span></code>.</p></li>
<li><p>Multiple items placed next to each other can be separated
by whitespace.  For example, <code class="docutils literal notranslate"><span class="pre">"pragma"</span> <span class="pre">"specify"</span> <span class="pre">number</span> <span class="pre">"."</span> <span class="pre">number</span></code> matches <code class="docutils literal notranslate"><span class="pre">pragma</span> <span class="pre">specify</span> <span class="pre">1.5</span></code>
and also <code class="docutils literal notranslate"><span class="pre">pragma</span>&nbsp;&nbsp;&nbsp;&nbsp; <span class="pre">specify</span> <span class="pre">0.3</span></code>.  Note that this is different from the
EBNF format described in the link above (that format would add a comma between items).</p></li>
<li><p>An item surrounded by square brackets is optional.  For example, <code class="docutils literal notranslate"><span class="pre">"pragma"</span> <span class="pre">"specify"</span> <span class="pre">number</span> <span class="pre">[</span> <span class="pre">"."</span> <span class="pre">number</span> <span class="pre">]</span></code>
matches <code class="docutils literal notranslate"><span class="pre">pragma</span> <span class="pre">specify</span> <span class="pre">3.1</span></code> and also matches <code class="docutils literal notranslate"><span class="pre">pragma</span> <span class="pre">specify</span> <span class="pre">3</span></code>.</p></li>
<li><p>An item surrounded by curly braces may be repeated 0 or more times.  For example,
<code class="docutils literal notranslate"><span class="pre">number</span> <span class="pre">{</span> <span class="pre">"."</span> <span class="pre">number</span> <span class="pre">}</span></code> matches <code class="docutils literal notranslate"><span class="pre">3</span></code> and <code class="docutils literal notranslate"><span class="pre">3.1</span></code> and <code class="docutils literal notranslate"><span class="pre">3.1.4.1.5</span></code></p></li>
<li><p>Items separated by a vertical bar represent different alternatives.  For example,
<code class="docutils literal notranslate"><span class="pre">"use"</span> <span class="pre">"rule"</span> <span class="pre">id</span> <span class="pre">|</span> <span class="pre">"use"</span> <span class="pre">"invariant"</span> <span class="pre">id</span> <span class="pre">|</span> <span class="pre">"use"</span> <span class="pre">"builtin"</span> <span class="pre">"rule"</span> <span class="pre">id</span></code> matches
<code class="docutils literal notranslate"><span class="pre">use</span> <span class="pre">rule</span> <span class="pre">foo</span></code> and also matches <code class="docutils literal notranslate"><span class="pre">use</span> <span class="pre">invariant</span> <span class="pre">bar</span></code> but does not match
<code class="docutils literal notranslate"><span class="pre">use</span> <span class="pre">rule</span> <span class="pre">foo</span> <span class="pre">use</span> <span class="pre">invariant</span> <span class="pre">bar</span></code>.</p></li>
</ul>
</section>
</section>


           </div>
          </div>
          <footer><div class="rst-footer-buttons" role="navigation" aria-label="Footer">
        <a href="index.html" class="btn btn-neutral float-left" title="The Certora Verification Language" accesskey="p" rel="prev"><span class="fa fa-arrow-circle-left" aria-hidden="true"></span> Previous</a>
        <a href="basics.html" class="btn btn-neutral float-right" title="Basic Syntax" accesskey="n" rel="next">Next <span class="fa fa-arrow-circle-right" aria-hidden="true"></span></a>
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