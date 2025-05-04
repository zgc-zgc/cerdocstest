<!DOCTYPE html><html class="writer-html5" lang="en" data-content_root="../../"><head>
  <meta charset="utf-8"><meta name="viewport" content="width=device-width, initial-scale=1">

  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Import and Use Statements — Certora Prover Documentation 0.0 documentation</title>
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
    <link rel="next" title="Using Statements" href="using.html">
    <link rel="prev" title="Statements" href="statements.html"> 
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
<li class="toctree-l2 current" aria-expanded="true"><a class="reference internal current" href="#" aria-expanded="true"><button class="toctree-expand" title="Open/close menu"></button>Import and Use Statements</a><ul>
<li class="toctree-l3"><a class="reference internal" href="#examples">Examples</a></li>
<li class="toctree-l3"><a class="reference internal" href="#syntax">Syntax</a></li>
</ul>
</li>
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
      <li class="breadcrumb-item active">Import and Use Statements</li>
      <li class="wy-breadcrumbs-aside">
            <a href="../../_sources/docs/cvl/imports.md.txt" rel="nofollow"> View page source</a>
      </li>
  </ul>
  <hr>
</div>
          <div role="main" class="document" itemscope="itemscope" itemtype="http://schema.org/Article">
           <div itemprop="articleBody">
             
  <section id="import-and-use-statements">
<span id="use"></span><h1>Import and Use Statements<a class="headerlink" href="#import-and-use-statements" title="Link to this heading"></a></h1>
<p>Contents of additional spec files can be imported using the <code class="docutils literal notranslate"><span class="pre">import</span></code> command.
Some parts of the imported spec files are implicitly included in the importing
spec file, while others such as rules and invariants must be explicitly
<code class="docutils literal notranslate"><span class="pre">use</span></code>d. Functions, definitions, filters, and preserved blocks of the imported spec can be overridden by the importing
spec. If a spec defines a function and uses it (e.g. in a rule or function), and another spec imports it and overrides
it, uses in the imported spec use the new version.</p>
<section id="examples">
<h2>Examples<a class="headerlink" href="#examples" title="Link to this heading"></a></h2>
<ul class="simple">
<li><p><a class="reference external" href="https://github.com/Certora/Examples/blob/be09cf32c55e39f5f5aa8cba1431f9e519b52365/CVLByExample/import/certora/specs/sub.spec#L1">Example for <code class="docutils literal notranslate"><span class="pre">import</span></code></a></p></li>
<li><p><a class="reference external" href="https://github.com/Certora/Examples/blob/61ac29b1128c68aff7e8d1e77bc80bfcbd3528d6/CVLByExample/import/certora/specs/sub.spec#L24"><code class="docutils literal notranslate"><span class="pre">use</span> <span class="pre">rule</span></code></a></p></li>
<li><p><a class="reference external" href="https://github.com/Certora/Examples/blob/be09cf32c55e39f5f5aa8cba1431f9e519b52365/CVLByExample/import/certora/specs/sub.spec#L3"><code class="docutils literal notranslate"><span class="pre">use</span> <span class="pre">rule</span></code> with filters</a></p></li>
<li><p><a class="reference external" href="https://github.com/Certora/Examples/blob/be09cf32c55e39f5f5aa8cba1431f9e519b52365/CVLByExample/import/certora/specs/sub.spec#L3">overriding imported filters</a></p></li>
<li><p><a class="reference external" href="https://github.com/Certora/Examples/blob/be09cf32c55e39f5f5aa8cba1431f9e519b52365/CVLByExample/import/certora/specs/sub.spec#L8"><code class="docutils literal notranslate"><span class="pre">use</span> <span class="pre">invariant</span></code></a></p>
<ul>
<li><p><a class="reference external" href="https://github.com/Certora/Examples/blob/be09cf32c55e39f5f5aa8cba1431f9e519b52365/CVLByExample/import/certora/specs/sub.spec#L10">overriding imported <code class="docutils literal notranslate"><span class="pre">preserved</span></code></a></p></li>
<li><p><a class="reference external" href="https://github.com/Certora/Examples/blob/be09cf32c55e39f5f5aa8cba1431f9e519b52365/CVLByExample/import/certora/specs/sub.spec#L14">adding a <code class="docutils literal notranslate"><span class="pre">preserved</span></code> block</a></p></li>
</ul>
</li>
</ul>
</section>
<section id="syntax">
<h2>Syntax<a class="headerlink" href="#syntax" title="Link to this heading"></a></h2>
<p>The syntax for <code class="docutils literal notranslate"><span class="pre">import</span></code> and <code class="docutils literal notranslate"><span class="pre">use</span></code> statements is given by the following <a class="reference internal" href="overview.html#ebnf-syntax"><span class="std std-ref">EBNF grammar</span></a>:</p>
<div class="highlight-default notranslate"><div class="highlight"><pre id="codecell0"><span></span><span class="kn">import</span> <span class="p">:</span><span class="o">:=</span> <span class="s2">"import"</span> <span class="n">string</span>

<span class="n">use</span> <span class="p">:</span><span class="o">:=</span> <span class="s2">"use"</span> <span class="s2">"rule"</span> <span class="nb">id</span>
        <span class="p">[</span> <span class="s2">"filtered"</span> <span class="s2">"{"</span> <span class="nb">id</span> <span class="s2">"-&gt;"</span> <span class="n">expression</span> <span class="p">{</span> <span class="s2">","</span> <span class="nb">id</span> <span class="s2">"-&gt;"</span> <span class="n">expression</span> <span class="p">}</span> <span class="s2">"}"</span> <span class="p">]</span>
      <span class="o">|</span> <span class="s2">"use"</span> <span class="s2">"builtin"</span> <span class="s2">"rule"</span> <span class="nb">id</span>
      <span class="o">|</span> <span class="s2">"use"</span> <span class="s2">"invariant"</span> <span class="nb">id</span> <span class="p">[</span> <span class="s2">"filtered"</span> <span class="s2">"{"</span> <span class="nb">id</span> <span class="s2">"-&gt;"</span> <span class="n">expression</span> <span class="s2">"}"</span> <span class="p">]</span> <span class="p">[</span> <span class="s2">"{"</span> <span class="p">{</span> <span class="n">preserved_block</span> <span class="p">}</span> <span class="s2">"}"</span> <span class="p">]</span>

</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell0">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>See <a class="reference internal" href="basics.html"><span class="doc">Basic Syntax</span></a> for the <code class="docutils literal notranslate"><span class="pre">string</span></code> and <code class="docutils literal notranslate"><span class="pre">id</span></code> productions, <a class="reference internal" href="expr.html"><span class="doc">Expressions</span></a> for the <code class="docutils literal notranslate"><span class="pre">expression</span></code> production, and
<a class="reference internal" href="invariants.html"><span class="doc">Invariants</span></a> for the <code class="docutils literal notranslate"><span class="pre">filtered</span></code> and <code class="docutils literal notranslate"><span class="pre">preserved_block</span></code> production.</p>
</section>
</section>


           </div>
          </div>
          <footer><div class="rst-footer-buttons" role="navigation" aria-label="Footer">
        <a href="statements.html" class="btn btn-neutral float-left" title="Statements" accesskey="p" rel="prev"><span class="fa fa-arrow-circle-left" aria-hidden="true"></span> Previous</a>
        <a href="using.html" class="btn btn-neutral float-right" title="Using Statements" accesskey="n" rel="next">Next <span class="fa fa-arrow-circle-right" aria-hidden="true"></span></a>
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