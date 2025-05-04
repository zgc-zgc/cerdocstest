<!DOCTYPE html><html class="writer-html5" lang="en" data-content_root="../../"><head>
  <meta charset="utf-8"><meta name="viewport" content="width=device-width, initial-scale=1">

  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Producing Positive Examples — Certora Prover Documentation 0.0 documentation</title>
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
    <link rel="next" title="Invariants" href="invariants.html">
    <link rel="prev" title="Designing Good Specifications" href="properties/index.html"> 
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
<li class="toctree-l1 current" aria-expanded="true"><a class="reference internal" href="index.html"><button class="toctree-expand" title="Open/close menu"></button>Certora User’s Guide</a><ul class="" aria-expanded="false">
<li class="toctree-l2"><a class="reference internal" href="install.html">Installation</a></li>
<li class="toctree-l2"><a class="reference internal" href="install_evm_compiler.html">Installing an EVM compiler and VS Code Extension</a></li>
<li class="toctree-l2"><a class="reference internal" href="tutorials.html">Tutorial and Workshops</a></li>
<li class="toctree-l2"><a class="reference internal" href="running.html">Running the Certora Prover</a></li>
<li class="toctree-l2"><a class="reference internal" href="properties/index.html">Designing Good Specifications</a></li>
<li class="toctree-l2 current" aria-expanded="true"><a class="reference internal current" href="#" aria-expanded="true">Producing Positive Examples</a></li>
<li class="toctree-l2"><a class="reference internal" href="invariants.html">Invariants</a></li>
<li class="toctree-l2"><a class="reference internal" href="parametric.html">Parametric rules</a></li>
<li class="toctree-l2"><a class="reference internal" href="ghosts.html">Tracking changes with ghosts and hooks</a></li>
<li class="toctree-l2"><a class="reference internal" href="patterns/index.html">Specification Design Patterns</a></li>
<li class="toctree-l2"><a class="reference internal" href="opcodes.html">Using Opcode Hooks</a></li>
<li class="toctree-l2"><a class="reference internal" href="multicontract/index.html">Working with Multiple Contracts</a></li>
<li class="toctree-l2"><a class="reference internal" href="out-of-resources/index.html">Managing Timeouts and Out of Memory Problems</a></li>
<li class="toctree-l2"><a class="reference internal" href="gaps.html">Understanding gaps between high and low level code</a></li>
<li class="toctree-l2"><a class="reference internal" href="checking.html">Checking Specifications</a></li>
<li class="toctree-l2"><a class="reference internal" href="ci.html">CI Configuration</a></li>
<li class="toctree-l2"><a class="reference internal" href="github_highlighting.html">Syntax Highlighting on GitHub</a></li>
<li class="toctree-l2"><a class="reference internal" href="glossary.html">Glossary</a></li>
</ul>
</li>
<li class="toctree-l1"><a class="reference internal" href="../cvl/index.html">The Certora Verification Language</a></li>
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
          <li class="breadcrumb-item"><a href="index.html">Certora User’s Guide</a></li>
      <li class="breadcrumb-item active">Producing Positive Examples</li>
      <li class="wy-breadcrumbs-aside">
            <a href="../../_sources/docs/user-guide/satisfy.md.txt" rel="nofollow"> View page source</a>
      </li>
  </ul>
  <hr>
</div>
          <div role="main" class="document" itemscope="itemscope" itemtype="http://schema.org/Article">
           <div itemprop="articleBody">
             
  <section id="producing-positive-examples">
<span id="producing-examples"></span><h1>Producing Positive Examples<a class="headerlink" href="#producing-positive-examples" title="Link to this heading"></a></h1>
<p>Sometimes it is useful to produce examples of an expected behavior instead of
counterexamples that demonstrate unexpected behavior.  You can do this by
writing a rule that uses <a class="reference internal" href="../cvl/statements.html#satisfy"><span class="std std-ref">satisfy statements</span></a> instead of the <code class="docutils literal notranslate"><span class="pre">assert</span></code> command.  For
each <code class="docutils literal notranslate"><span class="pre">satisfy</span></code> command in a rule, the Prover will produce an example that makes
the condition true, or report an error.</p>
<p>The purpose of the <code class="docutils literal notranslate"><span class="pre">satisfy</span></code> statement is to produce examples that demonstrate
some execution of the code.  Not every example is interesting — users
should inspect the example to ensure that it demonstrates the expected
behavior.</p>
<p>For <a class="reference external" href="https://github.com/Certora/Examples/blob/7dfc379423202c90cf284eb42800b97cf5c95d83/DEFI/ConstantProductPool/certora/spec/ConstantProductPool.spec">example</a>,
we may be interested in showing that it is
possible for someone to deposit some assets into a pool and then immediately
withdraw them.  The following rule demonstrates this scenario:</p>
<div class="literal-block-wrapper docutils container" id="id1">
<div class="code-block-caption"><span class="caption-text">Positive example</span><a class="headerlink" href="#id1" title="Link to this code"></a></div>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell0"><span></span><span class="k">rule</span><span class="w"> </span><span class="nc">possibleToFullyWithdraw</span><span class="p">(</span><span class="kt">address</span><span class="w"> </span>sender<span class="p">,</span><span class="w"> </span><span class="kt">uint256</span><span class="w"> </span>amount<span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kt">env</span><span class="w"> </span>eT0<span class="p">;</span>
<span class="w">    </span><span class="kt">env</span><span class="w"> </span>eM<span class="p">;</span>
<span class="w">    </span>setup<span class="p">(</span>eM<span class="p">);</span>
<span class="w">    </span><span class="kt">address</span><span class="w"> </span>token<span class="p">;</span>
<span class="w">    </span><span class="kr">require</span><span class="w"> </span>token<span class="w"> </span><span class="o">==</span><span class="w"> </span>_token0<span class="w"> </span><span class="o">||</span><span class="w"> </span>token<span class="w"> </span><span class="o">==</span><span class="w"> </span>_token1<span class="p">;</span>
<span class="w">    </span><span class="kt">uint256</span><span class="w"> </span>balanceBefore<span class="w"> </span><span class="o">=</span><span class="w"> </span>token<span class="p">.</span>balanceOf<span class="p">(</span>eT0<span class="p">,</span>sender<span class="p">);</span>
<span class="w">    </span>
<span class="w">    </span><span class="kr">require</span><span class="w"> </span>eM<span class="p">.</span><span class="kc">msg.sender</span><span class="w"> </span><span class="o">==</span><span class="w"> </span>sender<span class="p">;</span>
<span class="w">    </span><span class="kr">require</span><span class="w"> </span>eT0<span class="p">.</span><span class="kc">msg.sender</span><span class="w"> </span><span class="o">==</span><span class="w"> </span>sender<span class="p">;</span>
<span class="w">    </span><span class="kr">require</span><span class="w"> </span>amount<span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">;</span>
<span class="w">    </span>token<span class="p">.</span>transfer<span class="p">(</span>eT0<span class="p">,</span><span class="w"> </span><span class="nb">currentContract</span><span class="p">,</span><span class="w"> </span>amount<span class="p">);</span>
<span class="w">    </span><span class="kt">uint256</span><span class="w"> </span>amountOut0<span class="w"> </span><span class="o">=</span><span class="w"> </span>mint<span class="p">(</span>eM<span class="p">,</span>sender<span class="p">);</span>
<span class="w">    </span><span class="c1">// immediately withdraw </span>
<span class="w">    </span>burnSingle<span class="p">(</span>eM<span class="p">,</span><span class="w"> </span>_token0<span class="p">,</span><span class="w"> </span>amountOut0<span class="p">,</span><span class="w"> </span>sender<span class="p">);</span>
<span class="w">    </span><span class="kr">satisfy</span><span class="w"> </span><span class="p">(</span>balanceBefore<span class="w"> </span><span class="o">==</span><span class="w"> </span>token<span class="p">.</span>balanceOf<span class="p">(</span>eT0<span class="p">,</span><span class="w"> </span>sender<span class="p">));</span>
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
</div>
<p>The Prover will produce an example that satisfies this condition.
Sometimes the example will be uninteresting, such as having
<code class="code highlight cvl docutils literal highlight-cvl">amount<span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="m m-Decimal">0</span></code> in the example for <code class="code highlight cvl docutils literal highlight-cvl">possibleToFullyWithdraw</code>.
In such cases we need to strengthen the conditions in order
to produce more interesting examples.
In <code class="code highlight cvl docutils literal highlight-cvl">possibleToFullyWithdraw</code> we added a
<code class="code highlight cvl docutils literal highlight-cvl"><span class="kr">require</span><span class="w"> </span>amount<span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">;</span></code> statement to prevent such a case.</p>
<p>Alternatively, we could have strengthened the <code class="code highlight cvl docutils literal highlight-cvl"><span class="kr">satisfy</span></code>
condition by adding</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell1"><span></span><span class="w">    </span><span class="kr">satisfy</span><span class="w"> </span><span class="p">(</span>amount<span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">)</span><span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span><span class="p">...</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell1">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>


           </div>
          </div>
          <footer><div class="rst-footer-buttons" role="navigation" aria-label="Footer">
        <a href="properties/index.html" class="btn btn-neutral float-left" title="Designing Good Specifications" accesskey="p" rel="prev"><span class="fa fa-arrow-circle-left" aria-hidden="true"></span> Previous</a>
        <a href="invariants.html" class="btn btn-neutral float-right" title="Invariants" accesskey="n" rel="next">Next <span class="fa fa-arrow-circle-right" aria-hidden="true"></span></a>
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