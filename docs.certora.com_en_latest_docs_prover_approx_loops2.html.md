<!DOCTYPE html><html class="writer-html5" lang="en" data-content_root="../../../"><head>
  <meta charset="utf-8"><meta name="viewport" content="width=device-width, initial-scale=1">

  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Loop Unrolling — Certora Prover Documentation 0.0 documentation</title>
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
    <link rel="next" title="Method Summarization" href="summarization.html">
    <link rel="prev" title="Prover Approximations" href="index.html"> 
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
<li class="toctree-l2 current" aria-expanded="true"><a class="reference internal" href="index.html"><button class="toctree-expand" title="Open/close menu"></button>Prover Approximations</a><ul class="" aria-expanded="false">
<li class="toctree-l3 current" aria-expanded="true"><a class="reference internal current" href="#" aria-expanded="true">Loop Unrolling</a></li>
<li class="toctree-l3"><a class="reference internal" href="summarization.html">Method Summarization</a></li>
<li class="toctree-l3"><a class="reference internal" href="harnessing.html">Harnessing</a></li>
<li class="toctree-l3"><a class="reference internal" href="hashing.html">Modeling of Hashing in the Certora Prover</a></li>
<li class="toctree-l3"><a class="reference internal" href="grounding.html">Quantifier Grounding</a></li>
</ul>
</li>
<li class="toctree-l2"><a class="reference internal" href="../techniques/index.html">Techniques Used by the Certora Prover</a></li>
<li class="toctree-l2"><a class="reference internal" href="../diagnosis/index.html">Diagnostic Tools</a></li>
<li class="toctree-l2"><a class="reference internal" href="../checking/index.html">Checking Specifications</a></li>
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
          <li class="breadcrumb-item"><a href="index.html">Prover Approximations</a></li>
      <li class="breadcrumb-item active">Loop Unrolling</li>
      <li class="wy-breadcrumbs-aside">
            <a href="../../../_sources/docs/prover/approx/loops.md.txt" rel="nofollow"> View page source</a>
      </li>
  </ul>
  <hr>
</div>
          <div role="main" class="document" itemscope="itemscope" itemtype="http://schema.org/Article">
           <div itemprop="articleBody">
             
  <section id="loop-unrolling">
<span id="unrolling"></span><h1>Loop Unrolling<a class="headerlink" href="#loop-unrolling" title="Link to this heading"></a></h1>
<p>One of the approximations applied by the Certora Prover is loop unrolling.
Loops in the contract are replaced by multiple copies of their bodies.
if the Prover detects that a loop has a constant number of iterations, this loop is unrolled
as many times as the constant.</p>
<p>For example, for the loop:</p>
<div class="highlight-solidity notranslate"><div class="highlight"><pre id="codecell0"><span></span><span class="kt">for</span><span class="w"> </span><span class="p">(</span><span class="kt">uint</span><span class="w"> </span><span class="nv">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">;</span><span class="w"> </span>i<span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="m m-Decimal">3</span><span class="p">;</span><span class="w"> </span>i<span class="o">++</span><span class="p">)</span>
<span class="w">        </span>j<span class="o">++</span><span class="p">;</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell0">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>the Prover can determine that the loop always runs 3 times, so the loop will be replaced by</p>
<div class="highlight-solidity notranslate"><div class="highlight"><pre id="codecell1"><span></span>j<span class="o">++</span><span class="p">;</span>
j<span class="o">++</span><span class="p">;</span>
j<span class="o">++</span><span class="p">;</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell1">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>If the Prover cannot easily determine the number of loop iterations, it will unroll it a fixed number of times. The default number is 1, but it can be configured using
the <a class="reference internal" href="../cli/options.html#loop-iter"><span class="std std-ref">loop_iter</span></a> flag.</p>
<p>For example, consider the following solidity function:</p>
<div class="highlight-solidity notranslate"><div class="highlight"><pre id="codecell2"><span></span><span class="c1">/// @notice: `slow_copy(n)` always returns `n`</span>
<span class="kt">function</span><span class="w"> </span><span class="nv">slow_copy</span><span class="p">(</span><span class="kt">uint</span><span class="w"> </span><span class="nv">n</span><span class="p">)</span><span class="w"> </span><span class="kt">returns</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kt">uint</span><span class="w"> </span><span class="nv">j</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">;</span>
<span class="w">    </span><span class="kt">for</span><span class="w"> </span><span class="p">(</span><span class="kt">uint</span><span class="w"> </span><span class="nv">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">;</span><span class="w"> </span>i<span class="w"> </span><span class="o">&lt;</span><span class="w"> </span>n<span class="p">;</span><span class="w"> </span>i<span class="o">++</span><span class="p">)</span>
<span class="w">        </span>j<span class="o">++</span><span class="p">;</span>
<span class="w">    </span><span class="kt">return</span><span class="w"> </span>j<span class="p">;</span>
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
<p>With <code class="docutils literal notranslate"><span class="pre">--loop_iter</span> <span class="pre">2</span></code>, the loop in <code class="docutils literal notranslate"><span class="pre">slow_copy</span></code> will be approximated by two copies of its
body:</p>
<div class="highlight-solidity notranslate"><div class="highlight"><pre id="codecell3"><span></span><span class="kt">function</span><span class="w"> </span><span class="nv">slow_copy_unrolled</span><span class="p">(</span><span class="kt">uint</span><span class="w"> </span><span class="nv">n</span><span class="p">)</span><span class="w"> </span><span class="kt">returns</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kt">uint</span><span class="w"> </span><span class="nv">j</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">;</span>

<span class="w">    </span><span class="kt">uint</span><span class="w"> </span><span class="nv">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">;</span>
<span class="w">    </span><span class="kt">if</span><span class="w"> </span><span class="p">(</span>i<span class="w"> </span><span class="o">&lt;</span><span class="w"> </span>n<span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">        </span>j<span class="o">++</span><span class="p">;</span>
<span class="w">        </span>i<span class="o">++</span><span class="p">;</span>
<span class="w">        </span><span class="kt">if</span><span class="w"> </span><span class="p">(</span>i<span class="w"> </span><span class="o">&lt;</span><span class="w"> </span>n<span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">            </span>j<span class="o">++</span><span class="p">;</span>
<span class="w">            </span>i<span class="o">++</span><span class="p">;</span>
<span class="w">        </span><span class="p">}</span>
<span class="w">    </span><span class="p">}</span>

<span class="w">    </span><span class="kt">return</span><span class="w"> </span>j<span class="p">;</span>
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
<p>If a particular example would cause the loop to run more than twice, then the
loop guard (<code class="docutils literal notranslate"><span class="pre">i</span> <span class="pre">&lt;</span> <span class="pre">n</span></code> in the example) would still be true at the end of the loop.</p>
<p>The Prover has two options for handling examples that would execute the loop
too many times:</p>
<ul>
<li><p>In <strong>pessimistic mode</strong> (the default), the Prover will report an example
that executes the loop too many times as a violation of the “loop unwinding
condition” rule.  In pessimistic mode, any rule run on <code class="docutils literal notranslate"><span class="pre">slow_copy(n)</span></code> would
report a violation with <code class="docutils literal notranslate"><span class="pre">n</span> <span class="pre">=</span> <span class="pre">3</span></code>.</p>
<p>Pessimistic mode is <a class="reference internal" href="../../user-guide/glossary.html#term-sound"><span class="xref std std-term">sound</span></a>, because there may be rule
violations in the original code that only occur when the loop runs more than
3 times, and loop unrolling would cause those violations to be missed.  For
example, the original function <code class="docutils literal notranslate"><span class="pre">slow_copy</span></code> should not satisfy the following rule:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell4"><span></span><span class="k">rule</span><span class="w"> </span><span class="nc">bogus_rule</span><span class="p">(</span><span class="kt">uint</span><span class="w"> </span>n<span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kr">assert</span><span class="w"> </span>slow_copy<span class="p">(</span>n<span class="p">)</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="m m-Decimal">5</span><span class="p">,</span><span class="w"> </span><span class="s2">"slow_copy always returns something less than 5"</span><span class="p">;</span>
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
<p>but any violation would require 5 or more iterations of the loop.  The loop
unwinding violation notifies the user that this rule might not hold.</p>
</li>
<li><p>In <strong>optimistic mode</strong> (enabled by passing the <a class="reference internal" href="../cli/options.html#optimistic-loop"><span class="std std-ref">optimistic_loop</span></a> option),
the Prover <em>ignores</em> any examples that would cause the loop to execute
too many times.  In optimistic mode, the rule <code class="docutils literal notranslate"><span class="pre">bogus_rule</span></code> above would be
reported as passing.</p>
<div class="admonition caution">
<p class="admonition-title">Caution</p>
<p>Optimistic mode is <a class="reference internal" href="../../user-guide/glossary.html#term-unsound"><span class="xref std std-term">unsound</span></a> since it may miss counterexamples like
these.  It should be used with care since it may hide bugs.</p>
</div>
<p>Despite the unsoundness, optimistic mode is quite useful in practice.  For
example, it allows us to document that <code class="docutils literal notranslate"><span class="pre">slow_copy</span></code> satisfies the
specification given in its documentation:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell5"><span></span><span class="k">rule</span><span class="w"> </span><span class="nc">slow_copy_correct</span><span class="p">(</span><span class="kt">uint</span><span class="w"> </span>n<span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kr">assert</span><span class="w"> </span>slow_copy<span class="p">(</span>n<span class="p">)</span><span class="w"> </span><span class="o">==</span><span class="w"> </span>n<span class="p">,</span><span class="w"> </span><span class="s2">"slow_copy(n) always returns n"</span><span class="p">;</span>
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
<p>In optimistic mode, this rule will pass (as it should), but in pessimistic
mode it will fail if <code class="docutils literal notranslate"><span class="pre">n</span> <span class="pre">&gt;</span> <span class="pre">2</span></code>.</p>
</li>
</ul>
</section>


           </div>
          </div>
          <footer><div class="rst-footer-buttons" role="navigation" aria-label="Footer">
        <a href="index.html" class="btn btn-neutral float-left" title="Prover Approximations" accesskey="p" rel="prev"><span class="fa fa-arrow-circle-left" aria-hidden="true"></span> Previous</a>
        <a href="summarization.html" class="btn btn-neutral float-right" title="Method Summarization" accesskey="n" rel="next">Next <span class="fa fa-arrow-circle-right" aria-hidden="true"></span></a>
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