<!DOCTYPE html><html class="writer-html5" lang="en" data-content_root="../../"><head>
  <meta charset="utf-8"><meta name="viewport" content="width=device-width, initial-scale=1">

  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Understanding Prover Output for Solana Programs — Certora Prover Documentation 0.0 documentation</title>
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
    <link rel="next" title="Rule Sanity Checks (Solana)" href="sanity.html">
    <link rel="prev" title="Solana-Specific Options / CLI Flags" href="options.html"> 
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
<li class="toctree-l1"><a class="reference internal" href="../cvl/index.html">The Certora Verification Language</a></li>
<li class="toctree-l1"><a class="reference internal" href="../prover/index.html">The Certora Prover</a></li>
<li class="toctree-l1"><a class="reference internal" href="../sunbeam/index.html">Sunbeam: Verification for Soroban</a></li>
<li class="toctree-l1 current" aria-expanded="true"><a class="reference internal" href="index.html"><button class="toctree-expand" title="Open/close menu"></button>The Certora Solana Prover</a><ul class="" aria-expanded="false">
<li class="toctree-l2"><a class="reference internal" href="installation.html">Get started with the Solana Certora Prover</a></li>
<li class="toctree-l2"><a class="reference internal" href="usage.html">Using the Solana Certora Prover</a></li>
<li class="toctree-l2"><a class="reference internal" href="speclanguage.html">Certora Verification Language for Rust (CVLR)</a></li>
<li class="toctree-l2"><a class="reference internal" href="options.html">Solana-Specific Options / CLI Flags</a></li>
<li class="toctree-l2 current" aria-expanded="true"><a class="reference internal current" href="#" aria-expanded="true"><button class="toctree-expand" title="Open/close menu"></button>Understanding Prover Output for Solana Programs</a><ul>
<li class="toctree-l3"><a class="reference internal" href="#overview">Overview</a></li>
<li class="toctree-l3"><a class="reference internal" href="#verification-tasks">Verification Tasks</a></li>
<li class="toctree-l3"><a class="reference internal" href="#understanding-rule-results"><button class="toctree-expand" title="Open/close menu"></button>Understanding Rule Results</a><ul>
<li class="toctree-l4"><a class="reference internal" href="#assert-statements">Assert Statements</a></li>
<li class="toctree-l4"><a class="reference internal" href="#satisfy-statements">Satisfy Statements</a></li>
</ul>
</li>
<li class="toctree-l3"><a class="reference internal" href="#analyzing-counterexamples"><button class="toctree-expand" title="Open/close menu"></button>Analyzing Counterexamples</a><ul>
<li class="toctree-l4"><a class="reference internal" href="#call-trace-analysis">Call Trace Analysis</a></li>
</ul>
</li>
<li class="toctree-l3"><a class="reference internal" href="#rule-sanity-checking"><button class="toctree-expand" title="Open/close menu"></button>Rule Sanity Checking</a><ul>
<li class="toctree-l4"><a class="reference internal" href="#common-sanity-check-results">Common Sanity Check Results</a></li>
</ul>
</li>
<li class="toctree-l3"><a class="reference internal" href="#best-practices">Best Practices</a></li>
<li class="toctree-l3"><a class="reference internal" href="#advanced-topics"><button class="toctree-expand" title="Open/close menu"></button>Advanced Topics</a><ul>
<li class="toctree-l4"><a class="reference internal" href="#analyzing-functions-complexity">Analyzing Functions Complexity</a></li>
<li class="toctree-l4"><a class="reference internal" href="#over-approximation-detection">Over-approximation Detection</a></li>
</ul>
</li>
</ul>
</li>
<li class="toctree-l2"><a class="reference internal" href="sanity.html">Rule Sanity Checks (Solana)</a></li>
<li class="toctree-l2"><a class="reference internal" href="troubleshooting.html">Troubleshooting</a></li>
</ul>
</li>
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
          <li class="breadcrumb-item"><a href="index.html">The Certora Solana Prover</a></li>
      <li class="breadcrumb-item active">Understanding Prover Output for Solana Programs</li>
      <li class="wy-breadcrumbs-aside">
            <a href="../../_sources/docs/solana/output.md.txt" rel="nofollow"> View page source</a>
      </li>
  </ul>
  <hr>
</div>
          <div role="main" class="document" itemscope="itemscope" itemtype="http://schema.org/Article">
           <div itemprop="articleBody">
             
  <section id="understanding-prover-output-for-solana-programs">
<h1>Understanding Prover Output for Solana Programs<a class="headerlink" href="#understanding-prover-output-for-solana-programs" title="Link to this heading"></a></h1>
<section id="overview">
<h2>Overview<a class="headerlink" href="#overview" title="Link to this heading"></a></h2>
<p>This guide explains how to interpret verification results from the Certora Prover for Solana programs. It’s designed for developers familiar with Solana/Rust development and formal verification concepts.</p>
</section>
<section id="verification-tasks">
<h2>Verification Tasks<a class="headerlink" href="#verification-tasks" title="Link to this heading"></a></h2>
<p>A verification task consists of one or more rules that verify specific properties of your Solana program. Each rule contains at least one of the following:</p>
<ul class="simple">
<li><p>Assert statements <code class="docutils literal notranslate"><span class="pre">cvlr_assert!</span></code></p></li>
<li><p>Satisfy statements <code class="docutils literal notranslate"><span class="pre">cvlr_satisfy!</span></code></p></li>
</ul>
</section>
<section id="understanding-rule-results">
<h2>Understanding Rule Results<a class="headerlink" href="#understanding-rule-results" title="Link to this heading"></a></h2>
<section id="assert-statements">
<h3>Assert Statements<a class="headerlink" href="#assert-statements" title="Link to this heading"></a></h3>
<p>When using <code class="docutils literal notranslate"><span class="pre">cvlr_assert</span></code>, the Prover attempts to prove that the assertion holds true for all possible program states. For example:</p>
<div class="highlight-rust notranslate"><div class="highlight"><pre id="codecell0"><span></span><span class="n">cvlr_assert</span><span class="o">!</span><span class="p">(</span><span class="n">amount</span><span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="mi">10</span><span class="p">);</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell0">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>The Prover will return one of two results:
<img alt="A passed rule in the Certora Rule Report" src="../../_images/passed.png" width="858" height="278"></p>
<ol class="arabic simple">
<li><p><strong>PASSED</strong>: The assertion is proven true for all possible computation paths and initial values</p></li>
</ol>
<p><img alt="A failed rule in the Certora Rule Report" src="../../_images/failed.png" width="848" height="128"></p>
<ol class="arabic simple" start="2">
<li><p><strong>FAILED</strong>: A counterexample (CEX) was found, i.e a starting state and computation path that violates the assertion.
The Prover stops at the first counterexample found, even if multiple counterexamples exist</p></li>
</ol>
</section>
<section id="satisfy-statements">
<h3>Satisfy Statements<a class="headerlink" href="#satisfy-statements" title="Link to this heading"></a></h3>
<p><code class="docutils literal notranslate"><span class="pre">cvlr_satisfy</span></code> statements verify that a certain condition is reachable. For example:</p>
<div class="highlight-rust notranslate"><div class="highlight"><pre id="codecell1"><span></span><span class="n">cvlr_satisfy</span><span class="o">!</span><span class="p">(</span><span class="n">amount</span><span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="mi">10</span><span class="p">);</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell1">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>The results can be:</p>
<ol class="arabic simple">
<li><p><strong>PASSED</strong>: At least one execution path exists where the condition is true</p></li>
<li><p><strong>FAILED</strong>: The condition is unreachable under any execution path</p></li>
</ol>
</section>
</section>
<section id="analyzing-counterexamples">
<h2>Analyzing Counterexamples<a class="headerlink" href="#analyzing-counterexamples" title="Link to this heading"></a></h2>
<p>When a rule fails, the Prover generates a counterexample showing the execution path that led to the failure. Counterexamples can be:</p>
<ol class="arabic simple">
<li><p><strong>Valid</strong>: Indicating a genuine bug in the code</p></li>
<li><p><strong>Spurious</strong>: Resulting from over-approximation of possible program states</p></li>
</ol>
<section id="call-trace-analysis">
<h3>Call Trace Analysis<a class="headerlink" href="#call-trace-analysis" title="Link to this heading"></a></h3>
<p><img alt="A call trace example" src="../../_images/call_trace_example.png" width="1790" height="944"></p>
<p>The call trace provides detailed information about the execution path. Here’s how to interpret it:</p>
<section id="nondeterministic-values">
<h4>Nondeterministic Values<a class="headerlink" href="#nondeterministic-values" title="Link to this heading"></a></h4>
<ul class="simple">
<li><p>Appear at the beginning of the trace</p></li>
<li><p>Represent the starting state which leads to a violation</p></li>
<li><p>Format: <code class="docutils literal notranslate"><span class="pre">CVT_nondet_u64:</span> <span class="pre">&lt;value&gt;</span></code></p></li>
</ul>
</section>
<section id="variable-values">
<h4>Variable Values<a class="headerlink" href="#variable-values" title="Link to this heading"></a></h4>
<ul class="simple">
<li><p>The values of variables can be printed using the <code class="docutils literal notranslate"><span class="pre">clog!</span></code> macro</p></li>
<li><p>Example: <code class="docutils literal notranslate"><span class="pre">let</span> <span class="pre">x:</span> <span class="pre">u64</span> <span class="pre">=</span> <span class="pre">nondet();</span> <span class="pre">clog!(x);</span></code></p></li>
</ul>
</section>
<section id="method-calls">
<h4>Method Calls<a class="headerlink" href="#method-calls" title="Link to this heading"></a></h4>
<ul class="simple">
<li><p>Automatically logged</p></li>
<li><p>Show the sequence of function calls</p></li>
<li><p>To see parameter values, they have to be logged using <code class="docutils literal notranslate"><span class="pre">clog!</span></code> macro</p></li>
</ul>
</section>
<section id="let-s-look-at-a-concrete-example">
<h4>Let’s look at a concrete example<a class="headerlink" href="#let-s-look-at-a-concrete-example" title="Link to this heading"></a></h4>
<p><a class="reference external" href="https://prover.certora.com/output/1324651/741e8ee5a5754c1ab8db0aa36be39e4d?anonymousKey=ca602f5139de3bfbae17eb1fbf9c11145be3a912">Prover output</a></p>
<div class="highlight-rust notranslate"><div class="highlight"><pre id="codecell2"><span></span><span class="cp">#[rule]</span>
<span class="k">pub</span><span class="w"> </span><span class="k">fn</span><span class="w"> </span><span class="nf">rule_fail_call_trace</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kd">let</span><span class="w"> </span><span class="n">amount1</span><span class="p">:</span><span class="w"> </span><span class="kt">u64</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">nondet</span><span class="p">();</span>
<span class="w">    </span><span class="kd">let</span><span class="w"> </span><span class="n">amount2</span><span class="p">:</span><span class="w"> </span><span class="kt">u64</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">nondet</span><span class="p">();</span>

<span class="w">    </span><span class="n">cvlr_assume</span><span class="o">!</span><span class="p">(</span><span class="n">amount1</span><span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="mi">100</span><span class="p">);</span>
<span class="w">    </span><span class="n">cvlr_assume</span><span class="o">!</span><span class="p">(</span><span class="n">amount2</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="mi">10</span><span class="p">);</span>

<span class="w">    </span><span class="n">clog</span><span class="o">!</span><span class="p">(</span><span class="n">amount1</span><span class="p">,</span><span class="w"> </span><span class="n">amount2</span><span class="p">);</span>

<span class="w">    </span><span class="n">cvlr_assert</span><span class="o">!</span><span class="p">(</span><span class="n">amount1</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="mi">100</span><span class="p">);</span>
<span class="w">    </span><span class="n">cvlr_assert</span><span class="o">!</span><span class="p">(</span><span class="n">amount2</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="mi">100</span><span class="p">);</span>
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
<p>When this rule fails, the Prover generates a counterexample that looks like
this:</p>
<p><img alt="A call trace example" src="../../_images/call_trace_detail.png" width="648" height="572"></p>
<p>Let’s analyze this counterexample:</p>
<ol class="arabic simple">
<li><p><strong>Nondet Values</strong>:</p>
<ul class="simple">
<li><p>The Prover chose <code class="docutils literal notranslate"><span class="pre">101</span></code> for <code class="docutils literal notranslate"><span class="pre">amount1</span></code> and implicitly <code class="docutils literal notranslate"><span class="pre">0</span></code> for <code class="docutils literal notranslate"><span class="pre">amount2</span></code></p></li>
<li><p>These values are chosen to demonstrate the violation of our assertions</p></li>
<li><p><code class="docutils literal notranslate"><span class="pre">&lt;?&gt;</span></code> means that the value is not important for the counterexample</p></li>
</ul>
</li>
<li><p><strong>Variable States</strong>:</p>
<ul class="simple">
<li><p><code class="docutils literal notranslate"><span class="pre">amount1</span></code> is 101, which satisfies our assumption <code class="docutils literal notranslate"><span class="pre">cvlr_assume!(amount1</span> <span class="pre">&gt;</span> <span class="pre">100)</span></code></p></li>
<li><p><code class="docutils literal notranslate"><span class="pre">amount2</span></code> is 0, which satisfies our assumption <code class="docutils literal notranslate"><span class="pre">cvlr_assume!(amount2</span> <span class="pre">!=</span> <span class="pre">10)</span></code></p></li>
</ul>
</li>
<li><p><strong>Assertion Failure</strong>:</p>
<ul class="simple">
<li><p>The assertion <code class="docutils literal notranslate"><span class="pre">cvlr_assert!(amount1</span> <span class="pre">&lt;</span> <span class="pre">100)</span></code> fails because we have a contradiction:</p>
<ul>
<li><p>We previously assumed <code class="docutils literal notranslate"><span class="pre">amount1</span> <span class="pre">&gt;</span> <span class="pre">100</span></code></p></li>
<li><p>But then we assert <code class="docutils literal notranslate"><span class="pre">amount1</span> <span class="pre">&lt;</span> <span class="pre">100</span></code></p></li>
</ul>
</li>
<li><p>This is impossible to satisfy, hence the counterexample</p></li>
</ul>
</li>
</ol>
</section>
</section>
</section>
<section id="rule-sanity-checking">
<h2>Rule Sanity Checking<a class="headerlink" href="#rule-sanity-checking" title="Link to this heading"></a></h2>
<p>To ensure rules aren’t passing vacuously (due to contradictory assumptions), add sanity checking to your configuration:</p>
<div class="highlight-json notranslate"><div class="highlight"><pre id="codecell3"><span></span><span class="p">{</span>
<span class="w">    </span><span class="nt">"rule_sanity"</span><span class="p">:</span><span class="w"> </span><span class="s2">"basic"</span>
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
<p>This adds an implicit <code class="docutils literal notranslate"><span class="pre">cvlr_satisfy!(true)</span></code> at the end of each rule. If this assertion is unreachable, it confirms that:</p>
<ol class="arabic simple">
<li><p>The assumptions are not contradictory</p></li>
<li><p>The successful verification of the rule is meaningful</p></li>
</ol>
<section id="common-sanity-check-results">
<h3>Common Sanity Check Results<a class="headerlink" href="#common-sanity-check-results" title="Link to this heading"></a></h3>
<ol class="arabic simple">
<li><p><strong>Sanity Check PASSED</strong>: The desired outcome - confirms rule isn’t vacuously true</p></li>
<li><p><strong>Sanity Check WARNING</strong>: Warning sign - indicates contradictory assumptions</p></li>
</ol>
<p>See <a class="reference internal" href="sanity.html"><span class="std std-doc">Rule Sanity Checks</span></a> for more details.</p>
</section>
</section>
<section id="best-practices">
<h2>Best Practices<a class="headerlink" href="#best-practices" title="Link to this heading"></a></h2>
<ol class="arabic simple">
<li><p>Always enable rule sanity checking in your configuration</p></li>
<li><p>Review full call traces when investigating failures</p></li>
<li><p>Validate counterexamples against your program’s expected state space</p></li>
</ol>
</section>
<section id="advanced-topics">
<h2>Advanced Topics<a class="headerlink" href="#advanced-topics" title="Link to this heading"></a></h2>
<section id="analyzing-functions-complexity">
<h3>Analyzing Functions Complexity<a class="headerlink" href="#analyzing-functions-complexity" title="Link to this heading"></a></h3>
<p>The Certora Solana Prover offers the Live Statistics panel to analyze the complexity of individual functions.
The Live Statistics provide information, for instance, about the number of paths of a function body which may help when having difficult to solve rules.
Observe that the Live Statistics panel is affected by the <code class="docutils literal notranslate"><span class="pre">solanaMinSizeForCalltrace</span></code> option.
Functions with a size smaller than this threshold, measured by the number of TAC commands they correspond to, will not be displayed in the Live Statistics panel.
Refer to the <a class="reference internal" href="../user-guide/out-of-resources/timeout.html"><span class="std std-doc">Timeouts</span></a> section for further information.</p>
</section>
<section id="over-approximation-detection">
<h3>Over-approximation Detection<a class="headerlink" href="#over-approximation-detection" title="Link to this heading"></a></h3>
<p>When analyzing counterexamples, consider:</p>
<ol class="arabic simple">
<li><p>Initial state feasibility: Is the starting state reachable for the code you’re analyzing?</p></li>
<li><p>Transaction sequence validity: Does the computation path make sense? Did you overlook a certain scenario?</p></li>
<li><p>State transition legitimacy: Do the values throughout the computation match? Are the parameters of your rule changing as expected?</p></li>
</ol>
<p>If any seem impossible in your actual program, the counterexample might be due to over-approximation.</p>
</section>
</section>
</section>


           </div>
          </div>
          <footer><div class="rst-footer-buttons" role="navigation" aria-label="Footer">
        <a href="options.html" class="btn btn-neutral float-left" title="Solana-Specific Options / CLI Flags" accesskey="p" rel="prev"><span class="fa fa-arrow-circle-left" aria-hidden="true"></span> Previous</a>
        <a href="sanity.html" class="btn btn-neutral float-right" title="Rule Sanity Checks (Solana)" accesskey="n" rel="next">Next <span class="fa fa-arrow-circle-right" aria-hidden="true"></span></a>
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