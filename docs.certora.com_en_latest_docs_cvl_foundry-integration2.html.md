<!DOCTYPE html><html class="writer-html5" lang="en" data-content_root="../../"><head>
  <meta charset="utf-8"><meta name="viewport" content="width=device-width, initial-scale=1">

  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Foundry Integration (Alpha) — Certora Prover Documentation 0.0 documentation</title>
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
    <link rel="next" title="Changes Introduced in CVL 2" href="cvl2/changes.html">
    <link rel="prev" title="Transient Storage" href="transient.html"> 
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
<li class="toctree-l2"><a class="reference internal" href="builtin.html">Built-in Rules</a></li>
<li class="toctree-l2"><a class="reference internal" href="functions.html">Functions</a></li>
<li class="toctree-l2"><a class="reference internal" href="invariants.html">Invariants</a></li>
<li class="toctree-l2"><a class="reference internal" href="sorts.html">Uninterpreted Sorts</a></li>
<li class="toctree-l2"><a class="reference internal" href="ghosts.html">Ghosts</a></li>
<li class="toctree-l2"><a class="reference internal" href="defs.html">Definitions</a></li>
<li class="toctree-l2"><a class="reference internal" href="hooks.html">Hooks</a></li>
<li class="toctree-l2"><a class="reference internal" href="transient.html">Transient Storage</a></li>
<li class="toctree-l2 current" aria-expanded="true"><a class="reference internal current" href="#" aria-expanded="true"><button class="toctree-expand" title="Open/close menu"></button>Foundry Integration (Alpha)</a><ul>
<li class="toctree-l3"><a class="reference internal" href="#usage-automatic-setup">Usage (Automatic Setup)</a></li>
<li class="toctree-l3"><a class="reference internal" href="#usage-manual-setup">Usage (Manual Setup)</a></li>
<li class="toctree-l3"><a class="reference internal" href="#key-differences-vs-foundry-fuzz-testing">Key differences vs. Foundry fuzz testing</a></li>
<li class="toctree-l3"><a class="reference internal" href="#known-limitations">Known Limitations</a></li>
</ul>
</li>
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
      <li class="breadcrumb-item active">Foundry Integration (Alpha)</li>
      <li class="wy-breadcrumbs-aside">
            <a href="../../_sources/docs/cvl/foundry-integration.md.txt" rel="nofollow"> View page source</a>
      </li>
  </ul>
  <hr>
</div>
          <div role="main" class="document" itemscope="itemscope" itemtype="http://schema.org/Article">
           <div itemprop="articleBody">
             
  <section id="foundry-integration-alpha">
<span id="foundry-integration"></span><h1>Foundry Integration (Alpha)<a class="headerlink" href="#foundry-integration-alpha" title="Link to this heading"></a></h1>
<p>Certora’s Foundry Integration allows formally verifying <a class="reference external" href="https://book.getfoundry.sh/forge/fuzz-testing">Foundry fuzz tests</a>
with the Certora Prover instead of writing specifications in CVL.</p>
<p>The Prover will yield higher guarantees of correctness than Foundry as all inputs will be evaluated.
While fuzzing is not as complete as formal verification (a fuzzer might “miss” some inputs that would expose a bug),
writing fuzz tests via Foundry is often easier since it uses Solidity.</p>
<div class="admonition caution">
<p class="admonition-title">Caution</p>
<p>This feature of the Certora Prover is in alpha state, so issues/unimplemented features are expected. Please contact us if you encounter
any issue.</p>
</div>
<section id="usage-automatic-setup">
<h2>Usage (Automatic Setup)<a class="headerlink" href="#usage-automatic-setup" title="Link to this heading"></a></h2>
<p>In Prover version 7.25.1, the flag <a class="reference internal" href="../prover/cli/options.html#foundry"><span class="std std-ref">foundry</span></a> was introduced. This flag automatically collects all test files (<code class="docutils literal notranslate"><span class="pre">.t.sol</span></code>) in the current directory and executes the Prover in Foundry mode.</p>
<p>To execute use:
<code class="docutils literal notranslate"><span class="pre">certoraRun</span> <span class="pre">--foundry</span></code></p>
<p>If you are facing issues with the automatic setup, for instance, when too many contracts that are being analyzed,
it is recommended to perform a manual setup instead.</p>
</section>
<section id="usage-manual-setup">
<h2>Usage (Manual Setup)<a class="headerlink" href="#usage-manual-setup" title="Link to this heading"></a></h2>
<p>There is a minimum of 2 required files to get the Prover to verify Foundry fuzz tests: A <code class="docutils literal notranslate"><span class="pre">.spec</span></code> file (written in CVL), and a <code class="docutils literal notranslate"><span class="pre">.conf</span></code> file.</p>
<ul class="simple">
<li><p>First, we need a <code class="docutils literal notranslate"><span class="pre">.spec</span></code> file written in CVL to tell the Prover what to verify. The file is very simple, and in the minimal case
has exactly one line:\</p></li>
</ul>
<div class="highlight-solidity notranslate"><div class="highlight"><pre id="codecell0"><span></span>use<span class="w"> </span>builtin<span class="w"> </span>rule<span class="w"> </span>verifyFoundryFuzzTests<span class="p">;</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell0">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<ul class="simple">
<li><p>Second, you need a <code class="docutils literal notranslate"><span class="pre">.conf</span></code> file that will provide the Prover the information of which contract to verify, and what <code class="docutils literal notranslate"><span class="pre">.spec</span></code> file to use.
A minimal <code class="docutils literal notranslate"><span class="pre">.conf</span></code> file will look like this:\</p></li>
</ul>
<div class="highlight-json notranslate"><div class="highlight"><pre id="codecell1"><span></span><span class="p">{</span>
<span class="w">  </span><span class="nt">"files"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span>
<span class="w">    </span><span class="s2">"path/to/file/with/Foundry/fuzz/tests.sol:&lt;name_of_contract_containing_the_tests&gt;"</span><span class="p">,</span>
<span class="w">  </span><span class="p">],</span>
<span class="w">  </span><span class="nt">"verify"</span><span class="p">:</span><span class="w"> </span><span class="s2">"name_of_contract_containing_the_tests:path/to/spec/file.spec"</span><span class="p">,</span>
<span class="w">  </span><span class="nt">"foundry_tests_mode"</span><span class="p">:</span><span class="w"> </span><span class="kc">true</span><span class="p">,</span>
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
<li><p>Now, to run the tests, execute:
<code class="docutils literal notranslate"><span class="pre">certoraRun</span> <span class="pre">path/to/conf/file.conf</span></code></p></li>
<li><p>You will receive a link to a report containing the results of the run.</p></li>
</ul>
<p>For a full running example, please also see our <a class="reference external" href="https://github.com/Certora/Examples/tree/master/FoundryIntegration">Foundry Integration Examples</a>.</p>
</section>
<section id="key-differences-vs-foundry-fuzz-testing">
<h2>Key differences vs. Foundry fuzz testing<a class="headerlink" href="#key-differences-vs-foundry-fuzz-testing" title="Link to this heading"></a></h2>
<p>In Foundry, fuzz tests start with a blank state as the initial state (i.e. all storage fields are explicitly set to <code class="docutils literal notranslate"><span class="pre">0</span></code>), and one can implement
a <code class="docutils literal notranslate"><span class="pre">setUp()</span></code> function in order to bring the state to whatever initial state one wants to run the tests in. In contrast, the Prover starts with
an arbitrary initial state and does <em>not</em> assume all storage fields to be initialized with 0 by default. This could cause the Prover to find
spurious counter examples. For example, a fuzz test may assume that a storage value of <code class="docutils literal notranslate"><span class="pre">balance</span></code> is zero for all addresses and the Prover may
choose some other initial state violating this basic assumption of the test.</p>
<p>To restrict the Prover’s search space to match the setup of the Foundry test, it’s possible write a special CVL function  <code class="docutils literal notranslate"><span class="pre">init_fuzz_tests</span></code>
that acts as a setup in CVL. This function may or may not be required depending on how the fuzz tests are setup.</p>
<div class="highlight-solidity notranslate"><div class="highlight"><pre id="codecell2"><span></span>override<span class="w"> </span><span class="kt">function</span><span class="w"> </span><span class="nv">init_fuzz_tests</span><span class="p">(</span>method<span class="w"> </span>f<span class="p">,</span><span class="w"> </span>env<span class="w"> </span>e<span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">  </span><span class="c1">// your initial state assumptions here</span>
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
<p>Depending on your fuzz test, you may need to use the <code class="docutils literal notranslate"><span class="pre">reset_storage</span></code> command in the <code class="docutils literal notranslate"><span class="pre">init_fuzz_tests</span></code> function. This will explicitly set all
storage fields of a contract to <code class="docutils literal notranslate"><span class="pre">0</span></code> before running the test. Alternatively, one could try to add a call to the <code class="docutils literal notranslate"><span class="pre">setUp()</span></code> function in the
<code class="docutils literal notranslate"><span class="pre">init_fuzz_tests</span></code> function - please note that the <code class="docutils literal notranslate"><span class="pre">init_fuzz_tests</span></code> is an empty method by default.</p>
</section>
<section id="known-limitations">
<h2>Known Limitations<a class="headerlink" href="#known-limitations" title="Link to this heading"></a></h2>
<ul class="simple">
<li><p>Foundry’s <a class="reference external" href="https://book.getfoundry.sh/forge/invariant-testing">Invariant testing</a> is not supported, i.e. forge tests prefixed with
<code class="docutils literal notranslate"><span class="pre">invariant</span></code> are not formally verified. Under the hood, the built-in rule <code class="docutils literal notranslate"><span class="pre">verifyFoundryFuzzTests</span></code> is a parametric rule that picks up all methods
that start in <code class="docutils literal notranslate"><span class="pre">test*</span></code> and will use these to formally verify them.</p></li>
<li><p>One of the usual usages of the <code class="docutils literal notranslate"><span class="pre">setUp()</span></code> function is to create new contract instances for testing.
When setting up the Prover run, the way to handle such storage references to other contracts is to use linking. If, for example,
we have the following test code\</p></li>
</ul>
<div class="highlight-solidity notranslate"><div class="highlight"><pre id="codecell3"><span></span><span class="k">contract</span><span class="w"> </span><span class="ni">TestContract</span><span class="w"> </span><span class="kt">is</span><span class="w"> </span>Test<span class="w"> </span><span class="p">{</span>
<span class="w">  </span>MyContract<span class="w"> </span>myContract<span class="p">;</span>
<span class="w">	</span>
<span class="w">  </span><span class="kt">function</span><span class="w"> </span><span class="nv">setUp</span><span class="p">()</span><span class="w"> </span><span class="kt">external</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span>myContract<span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="kt">new</span><span class="w"> </span>MyContract<span class="p">();</span>
<span class="w">  </span><span class="p">}</span>
<span class="w">  </span><span class="p">...</span>
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
<p><br>
then add to the <code class="docutils literal notranslate"><span class="pre">.conf</span></code> file:\</p>
<div class="highlight-json notranslate"><div class="highlight"><pre id="codecell4"><span></span><span class="w">  </span><span class="nt">"files"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span>
<span class="w">    </span><span class="s2">"..."</span><span class="p">,</span>
<span class="w">    </span><span class="s2">"path/to/MyContract.sol"</span>
<span class="w">  </span><span class="p">],</span>
<span class="w">  </span><span class="nt">"link"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span>
<span class="w">    </span><span class="s2">"..."</span><span class="p">,</span>
<span class="w">    </span><span class="s2">"TestContract:myContract=MyContract"</span>
<span class="w">  </span><span class="p">]</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell4">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p><br>
This way when the Prover encounters <code class="docutils literal notranslate"><span class="pre">myContract.foo()</span></code> it knows what the implementation of <code class="docutils literal notranslate"><span class="pre">foo</span></code> is and is able to inline it.</p>
<ul class="simple">
<li><p>Only a subset of the Foundry cheatcodes are currently implemented.
The implemented cheatcodes include <code class="docutils literal notranslate"><span class="pre">vm.assume</span></code>, all <code class="docutils literal notranslate"><span class="pre">assert*</span></code> cheatcodes, <code class="docutils literal notranslate"><span class="pre">vm.expectRevert</span></code>, <code class="docutils literal notranslate"><span class="pre">prank</span></code>, <code class="docutils literal notranslate"><span class="pre">startPrank</span></code>, <code class="docutils literal notranslate"><span class="pre">stopPrank</span></code>,
<code class="docutils literal notranslate"><span class="pre">warp</span></code>, and <code class="docutils literal notranslate"><span class="pre">deal</span></code>. Some other cheatcodes are irrelevant and are ignored, and many cheatcodes are not yet supported. One can
recognize these by checking the <strong>Contracts Call Resolutions</strong> tab of the report - unimplemented cheatcodes will appear there
as unresolved calls (which will usually lead to <a class="reference external" href="https://docs.certora.com/en/latest/docs/user-guide/glossary.html#term-havoc">havocs</a>
and therefore spurious counter examples). In this case, please contact Certora so we can implement the required cheatcode.</p></li>
<li><p>In cases where no explicit revert is expected, and the goal is to verify values or state using <code class="docutils literal notranslate"><span class="pre">assert*</span></code> cheatcodes,
you can use <code class="docutils literal notranslate"><span class="pre">verifyFoundryFuzzTestsNoRevert</span></code>. This ignores all code paths that lead to a revert while still verifying the <code class="docutils literal notranslate"><span class="pre">assert*</span></code> cheatcodes.</p></li>
<li><p>In Foundry, the <code class="docutils literal notranslate"><span class="pre">vm.expectRevert</span></code> cheatcode can optionally take a specific revert reason.
Foundry verifies both that the test function reverted and that it reverted with the specified reason.
In contrast, the Prover does not analyze the revert reason. As a result, if the test function reverts for a reason other than
the expected one, the test will still be marked as successful.</p></li>
</ul>
</section>
</section>


           </div>
          </div>
          <footer><div class="rst-footer-buttons" role="navigation" aria-label="Footer">
        <a href="transient.html" class="btn btn-neutral float-left" title="Transient Storage" accesskey="p" rel="prev"><span class="fa fa-arrow-circle-left" aria-hidden="true"></span> Previous</a>
        <a href="cvl2/changes.html" class="btn btn-neutral float-right" title="Changes Introduced in CVL 2" accesskey="n" rel="next">Next <span class="fa fa-arrow-circle-right" aria-hidden="true"></span></a>
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