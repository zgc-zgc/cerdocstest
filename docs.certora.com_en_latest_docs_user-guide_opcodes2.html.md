<!DOCTYPE html><html class="writer-html5" lang="en" data-content_root="../../"><head>
  <meta charset="utf-8"><meta name="viewport" content="width=device-width, initial-scale=1">

  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Using Opcode Hooks — Certora Prover Documentation 0.0 documentation</title>
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
    <link rel="next" title="Working with Multiple Contracts" href="multicontract/index.html">
    <link rel="prev" title="Require Invariants: Proving inter-dependent invariants" href="patterns/require-invariants.html"> 
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
<li class="toctree-l1 current" aria-expanded="true"><a class="reference internal" href="index.html"><button class="toctree-expand" title="Open/close menu"></button>Certora User’s Guide</a><ul class="" aria-expanded="false">
<li class="toctree-l2"><a class="reference internal" href="install.html">Installation</a></li>
<li class="toctree-l2"><a class="reference internal" href="install_evm_compiler.html">Installing an EVM compiler and VS Code Extension</a></li>
<li class="toctree-l2"><a class="reference internal" href="tutorials.html">Tutorial and Workshops</a></li>
<li class="toctree-l2"><a class="reference internal" href="running.html">Running the Certora Prover</a></li>
<li class="toctree-l2"><a class="reference internal" href="properties/index.html">Designing Good Specifications</a></li>
<li class="toctree-l2"><a class="reference internal" href="satisfy.html">Producing Positive Examples</a></li>
<li class="toctree-l2"><a class="reference internal" href="invariants.html">Invariants</a></li>
<li class="toctree-l2"><a class="reference internal" href="parametric.html">Parametric rules</a></li>
<li class="toctree-l2"><a class="reference internal" href="ghosts.html">Tracking changes with ghosts and hooks</a></li>
<li class="toctree-l2"><a class="reference internal" href="patterns/index.html">Specification Design Patterns</a></li>
<li class="toctree-l2 current" aria-expanded="true"><a class="reference internal current" href="#" aria-expanded="true"><button class="toctree-expand" title="Open/close menu"></button>Using Opcode Hooks</a><ul>
<li class="toctree-l3"><a class="reference internal" href="#accessing-environment-variables">Accessing environment variables</a></li>
<li class="toctree-l3"><a class="reference internal" href="#detecting-call-instructions">Detecting <code class="docutils literal notranslate"><span class="pre">CALL</span></code> instructions</a></li>
</ul>
</li>
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
      <li class="breadcrumb-item active">Using Opcode Hooks</li>
      <li class="wy-breadcrumbs-aside">
            <a href="../../_sources/docs/user-guide/opcodes.md.txt" rel="nofollow"> View page source</a>
      </li>
  </ul>
  <hr>
</div>
          <div role="main" class="document" itemscope="itemscope" itemtype="http://schema.org/Article">
           <div itemprop="articleBody">
             
  <section id="using-opcode-hooks">
<span id="using-opcodes"></span><h1><a class="toc-backref" href="#id1" role="doc-backlink">Using Opcode Hooks</a><a class="headerlink" href="#using-opcode-hooks" title="Link to this heading"></a></h1>
<p><a class="reference internal" href="../cvl/hooks.html#opcode-hooks"><span class="std std-ref">EVM opcode hooks</span></a> are useful for reasoning about the low-level behavior of
your contracts, and for accessing EVM state that is otherwise unavailable in
CVL.  This guide gives a few examples of how opcode hooks can be used.</p>
<nav class="contents" id="contents">
<p class="topic-title">Contents</p>
<ul class="simple">
<li><p><a class="reference internal" href="#using-opcode-hooks" id="id1">Using Opcode Hooks</a></p>
<ul>
<li><p><a class="reference internal" href="#accessing-environment-variables" id="id2">Accessing environment variables</a></p></li>
<li><p><a class="reference internal" href="#detecting-call-instructions" id="id3">Detecting <code class="docutils literal notranslate"><span class="pre">CALL</span></code> instructions</a></p></li>
</ul>
</li>
</ul>
</nav>
<section id="accessing-environment-variables">
<h2><a class="toc-backref" href="#id2" role="doc-backlink">Accessing environment variables</a><a class="headerlink" href="#accessing-environment-variables" title="Link to this heading"></a></h2>
<p>In CVL, you can access EVM variables like <code class="docutils literal notranslate"><span class="pre">msg.sender</span></code> using an
<a class="reference internal" href="../cvl/types.html#env"><span class="std std-ref">environment object</span></a>.  However, <code class="docutils literal notranslate"><span class="pre">env</span></code> objects do not contain all of
the EVM state that is available to contracts.</p>
<p>We made this choice for a few reasons: for one, it would be annoying to have to
manually specify that global constants like the chain ID are same in every
transaction.  Another is that we have tried to decouple CVL from EVM as much as
possible.</p>
<p>Nevertheless, sometimes you need access to EVM variables that are not included
in the <code class="docutils literal notranslate"><span class="pre">env</span></code> type, such as the <code class="docutils literal notranslate"><span class="pre">CHAINID</span></code> or <code class="docutils literal notranslate"><span class="pre">GASPRICE</span></code>.  You can use opcode
hooks on the corresponding instructions to restrict these values or save them
in <a class="reference internal" href="../cvl/ghosts.html#ghost-variables"><span class="std std-ref">Declaring ghost variables</span></a> for use in rules.</p>
<p>For example, if your contract uses <code class="docutils literal notranslate"><span class="pre">chainid()</span></code> to detect whether it is running
on the Ethereum Mainnet, you could ensure that the chain ID is always 1 (which
is the Ethereum Mainnet chain ID) by adding the following hook:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell0"><span></span><span class="kd">hook</span><span class="w"> </span>CHAINID<span class="w"> </span><span class="kt">uint</span><span class="w"> </span>id<span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kr">require</span><span class="w"> </span>id<span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="m m-Decimal">1</span><span class="p">;</span>
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
<p>Alternatively, you could save the chain ID in a ghost variable and then use it
in your rule:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell1"><span></span><span class="kd">ghost</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>chain_id<span class="p">;</span>
<span class="kd">hook</span><span class="w"> </span>CHAINID<span class="w"> </span><span class="kt">uint</span><span class="w"> </span>id<span class="w"> </span><span class="p">{</span>
<span class="w">    </span>chain_id<span class="w"> </span><span class="o">=</span><span class="w"> </span>id<span class="p">;</span>
<span class="p">}</span>

<span class="c1">/// The contract's behavior changes appropriately when run on mainnet</span>
<span class="k">rule</span><span class="w"> </span><span class="nc">chainid_behavior_correct</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="p">...</span>
<span class="w">    </span><span class="kr">if</span><span class="w"> </span><span class="p">(</span>chain_id<span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="m m-Decimal">1</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">        </span><span class="p">...</span>
<span class="w">    </span><span class="p">}</span><span class="w"> </span><span class="kr">else</span><span class="w"> </span><span class="p">{</span>
<span class="w">        </span><span class="p">...</span>
<span class="w">    </span><span class="p">}</span>
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
</section>
<section id="detecting-call-instructions">
<h2><a class="toc-backref" href="#id3" role="doc-backlink">Detecting <code class="docutils literal notranslate"><span class="pre">CALL</span></code> instructions</a><a class="headerlink" href="#detecting-call-instructions" title="Link to this heading"></a></h2>
<p>Suppose you want to ensure that a specific contract function never makes an
external call while it is in an emergency shutdown mode.  In order to verify
this property, you need to know whether the contract has made a call.</p>
<p>You can use a hook on the <code class="docutils literal notranslate"><span class="pre">CALL</span></code> opcode to write such a rule:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell2"><span></span><span class="kd">ghost</span><span class="w"> </span><span class="kt">bool</span><span class="w"> </span>made_call<span class="p">;</span>

<span class="kd">hook</span><span class="w"> </span>CALL<span class="p">(</span><span class="kt">uint</span><span class="w"> </span>g<span class="p">,</span><span class="w"> </span><span class="kt">address</span><span class="w"> </span>addr<span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>value<span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>argsOffset<span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>argsLength<span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>retOffset<span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>retLength<span class="p">)</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>rc<span class="w"> </span><span class="p">{</span>
<span class="w">    </span>made_call<span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="kr">true</span><span class="p">;</span>
<span class="p">}</span>

<span class="c1">/// While in `emergencyMode`, no function can make an external call.</span>
<span class="k">rule</span><span class="w"> </span><span class="nc">no_call_during_emergency</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kr">require</span><span class="w"> </span><span class="o">!</span>made_call<span class="p">;</span>
<span class="w">    </span><span class="kr">require</span><span class="w"> </span>emergencyMode<span class="p">();</span>

<span class="w">    </span><span class="kt">method</span><span class="w"> </span>f<span class="p">;</span><span class="w"> </span><span class="kt">env</span><span class="w"> </span>e<span class="p">;</span><span class="w"> </span><span class="kt">calldataarg</span><span class="w"> </span>args<span class="p">;</span>
<span class="w">    </span>f<span class="p">(</span>e<span class="p">,</span><span class="w"> </span>args<span class="p">);</span>

<span class="w">    </span><span class="kr">assert</span><span class="w"> </span><span class="o">!</span>made_call<span class="p">;</span>
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
<p>In this example, the <code class="docutils literal notranslate"><span class="pre">made_call</span></code> variable gets set to <code class="docutils literal notranslate"><span class="pre">true</span></code> whenever the
contract executes the <code class="docutils literal notranslate"><span class="pre">CALL</span></code> opcode, which is used to make external calls.  The
rule simply asserts that this variable is <code class="docutils literal notranslate"><span class="pre">false</span></code> (note that we required
<code class="docutils literal notranslate"><span class="pre">!made_call</span></code> to avoid counterexamples where <code class="docutils literal notranslate"><span class="pre">made_call</span></code> started out set).</p>
</section>
</section>


           </div>
          </div>
          <footer><div class="rst-footer-buttons" role="navigation" aria-label="Footer">
        <a href="patterns/require-invariants.html" class="btn btn-neutral float-left" title="Require Invariants: Proving inter-dependent invariants" accesskey="p" rel="prev"><span class="fa fa-arrow-circle-left" aria-hidden="true"></span> Previous</a>
        <a href="multicontract/index.html" class="btn btn-neutral float-right" title="Working with Multiple Contracts" accesskey="n" rel="next">Next <span class="fa fa-arrow-circle-right" aria-hidden="true"></span></a>
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