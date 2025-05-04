<!DOCTYPE html><html class="writer-html5" lang="en" data-content_root="../../../"><head>
  <meta charset="utf-8"><meta name="viewport" content="width=device-width, initial-scale=1">

  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Partially Parametric Rules — Certora Prover Documentation 0.0 documentation</title>
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
    <link rel="next" title="Listing Safe Assumptions" href="safe-assum.html">
    <link rel="prev" title="Tracking Sums" href="sums.html"> 
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
<li class="toctree-l1 current" aria-expanded="true"><a class="reference internal" href="../index.html"><button class="toctree-expand" title="Open/close menu"></button>Certora User’s Guide</a><ul class="" aria-expanded="false">
<li class="toctree-l2"><a class="reference internal" href="../install.html">Installation</a></li>
<li class="toctree-l2"><a class="reference internal" href="../install_evm_compiler.html">Installing an EVM compiler and VS Code Extension</a></li>
<li class="toctree-l2"><a class="reference internal" href="../tutorials.html">Tutorial and Workshops</a></li>
<li class="toctree-l2"><a class="reference internal" href="../running.html">Running the Certora Prover</a></li>
<li class="toctree-l2"><a class="reference internal" href="../properties/index.html">Designing Good Specifications</a></li>
<li class="toctree-l2"><a class="reference internal" href="../satisfy.html">Producing Positive Examples</a></li>
<li class="toctree-l2"><a class="reference internal" href="../invariants.html">Invariants</a></li>
<li class="toctree-l2"><a class="reference internal" href="../parametric.html">Parametric rules</a></li>
<li class="toctree-l2"><a class="reference internal" href="../ghosts.html">Tracking changes with ghosts and hooks</a></li>
<li class="toctree-l2 current" aria-expanded="true"><a class="reference internal" href="index.html"><button class="toctree-expand" title="Open/close menu"></button>Specification Design Patterns</a><ul class="" aria-expanded="false">
<li class="toctree-l3"><a class="reference internal" href="sums.html">Tracking Sums</a></li>
<li class="toctree-l3 current" aria-expanded="true"><a class="reference internal current" href="#" aria-expanded="true">Partially Parametric Rules</a></li>
<li class="toctree-l3"><a class="reference internal" href="safe-assum.html">Listing Safe Assumptions</a></li>
<li class="toctree-l3"><a class="reference internal" href="require-invariants.html">Require Invariants: Proving inter-dependent invariants</a></li>
</ul>
</li>
<li class="toctree-l2"><a class="reference internal" href="../opcodes.html">Using Opcode Hooks</a></li>
<li class="toctree-l2"><a class="reference internal" href="../multicontract/index.html">Working with Multiple Contracts</a></li>
<li class="toctree-l2"><a class="reference internal" href="../out-of-resources/index.html">Managing Timeouts and Out of Memory Problems</a></li>
<li class="toctree-l2"><a class="reference internal" href="../gaps.html">Understanding gaps between high and low level code</a></li>
<li class="toctree-l2"><a class="reference internal" href="../checking.html">Checking Specifications</a></li>
<li class="toctree-l2"><a class="reference internal" href="../ci.html">CI Configuration</a></li>
<li class="toctree-l2"><a class="reference internal" href="../github_highlighting.html">Syntax Highlighting on GitHub</a></li>
<li class="toctree-l2"><a class="reference internal" href="../glossary.html">Glossary</a></li>
</ul>
</li>
<li class="toctree-l1"><a class="reference internal" href="../../cvl/index.html">The Certora Verification Language</a></li>
<li class="toctree-l1"><a class="reference internal" href="../../prover/index.html">The Certora Prover</a></li>
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
          <li class="breadcrumb-item"><a href="../index.html">Certora User’s Guide</a></li>
          <li class="breadcrumb-item"><a href="index.html">Specification Design Patterns</a></li>
      <li class="breadcrumb-item active">Partially Parametric Rules</li>
      <li class="wy-breadcrumbs-aside">
            <a href="../../../_sources/docs/user-guide/patterns/partial-apply.md.txt" rel="nofollow"> View page source</a>
      </li>
  </ul>
  <hr>
</div>
          <div role="main" class="document" itemscope="itemscope" itemtype="http://schema.org/Article">
           <div itemprop="articleBody">
             
  <section id="partially-parametric-rules">
<span id="id1"></span><h1>Partially Parametric Rules<a class="headerlink" href="#partially-parametric-rules" title="Link to this heading"></a></h1>
<p>The provided code snippet illustrates a partially parametric rule in CVL that defines specific behavior based on the method invoked (<code class="docutils literal notranslate"><span class="pre">f</span></code>) and its arguments (<code class="docutils literal notranslate"><span class="pre">calldataarg</span></code>). Let’s break down the example for better understanding:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell0"><span></span><span class="k">rule</span><span class="w"> </span><span class="nc">partially_parametric_rule</span><span class="p">(</span><span class="kt">env</span><span class="w"> </span>e<span class="p">,</span><span class="w"> </span><span class="kt">method</span><span class="w"> </span>f<span class="p">,</span><span class="w"> </span><span class="kt">calldataarg</span><span class="w"> </span>args<span class="p">)</span>
<span class="p">{</span>
<span class="w">    </span><span class="kr">if</span><span class="w"> </span><span class="p">(</span>f<span class="p">.</span><span class="nb">selector</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="kd">sig</span><span class="o">:</span><span class="nf">withdraw</span><span class="p">(</span><span class="kt">uint256</span><span class="p">,</span><span class="w"> </span><span class="kt">address</span><span class="p">).</span><span class="nb">selector</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">        </span><span class="kt">uint256</span><span class="w"> </span>shares<span class="p">;</span>
<span class="w">        </span><span class="kt">address</span><span class="w"> </span>to<span class="p">;</span>
<span class="w">		</span><span class="kr">require</span><span class="w"> </span>e<span class="p">.</span><span class="kc">msg.sender</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="nb">currentContract</span><span class="p">;</span>
<span class="w">		</span><span class="kr">require</span><span class="w"> </span>shares<span class="w"> </span><span class="o">==</span><span class="w"> </span>totalSupply<span class="p">();</span>
<span class="w">		</span>withdraw<span class="p">(</span>e<span class="p">,</span><span class="w"> </span>shares<span class="p">,</span><span class="w"> </span>to<span class="p">);</span>
<span class="w">		</span><span class="kr">assert</span><span class="w"> </span>balanceOf<span class="p">(</span>to<span class="p">)</span><span class="w"> </span><span class="o">&gt;=</span><span class="w"> </span>balanceOf<span class="p">(</span><span class="nb">currentContract</span><span class="p">);</span><span class="w"> </span>
<span class="w">	</span><span class="p">}</span>
<span class="w">	</span><span class="kr">else</span><span class="w"> </span><span class="kr">if</span><span class="w"> </span><span class="p">(</span>f<span class="p">.</span><span class="nb">selector</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="kd">sig</span><span class="o">:</span><span class="nf">deposit</span><span class="p">(</span><span class="kt">uint256</span><span class="p">,</span><span class="w"> </span><span class="kt">address</span><span class="p">).</span><span class="nb">selector</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">        </span><span class="kt">uint256</span><span class="w"> </span>depositedAmount<span class="w"> </span><span class="o">=</span><span class="w"> </span>balanceOf<span class="p">(</span>e<span class="p">.</span><span class="kc">msg.sender</span><span class="p">);</span>
<span class="w">        </span><span class="kt">address</span><span class="w"> </span>to<span class="p">;</span>
<span class="w">		</span><span class="kr">require</span><span class="w"> </span>e<span class="p">.</span><span class="kc">msg.sender</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="nb">currentContract</span><span class="p">;</span>
<span class="w">		</span>deposit<span class="p">(</span>e<span class="p">,</span><span class="w"> </span>depositedAmount<span class="p">,</span><span class="w"> </span>to<span class="p">);</span>
<span class="w">        </span><span class="kr">assert</span><span class="w"> </span>balanceOf<span class="p">(</span>to<span class="p">)</span><span class="w"> </span><span class="o">&gt;=</span><span class="w"> </span>balanceOf<span class="p">(</span>e<span class="p">.</span><span class="kc">msg.sender</span><span class="p">);</span>
<span class="w">	</span><span class="p">}</span>
<span class="w">	</span><span class="kr">else</span><span class="w"> </span><span class="p">{</span>
<span class="w">        </span><span class="kt">uint256</span><span class="w"> </span>currentContract_balance_before<span class="w"> </span><span class="o">=</span><span class="w"> </span>balanceOf<span class="p">(</span><span class="nb">currentContract</span><span class="p">);</span>
<span class="w">		</span>f<span class="p">(</span>e<span class="p">,</span><span class="w"> </span>args<span class="p">);</span>
<span class="w">        </span><span class="kr">assert</span><span class="w"> </span>balanceOf<span class="p">(</span><span class="nb">currentContract</span><span class="p">)</span><span class="w"> </span><span class="o">==</span><span class="w"> </span>currentContract_balance_before<span class="p">;</span>
<span class="w">	</span><span class="p">}</span>
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
<ol class="arabic simple">
<li><p><strong>Withdrawal Case:</strong></p>
<ul class="simple">
<li><p>If the invoked method (<code class="docutils literal notranslate"><span class="pre">f</span></code>) corresponds to the <code class="docutils literal notranslate"><span class="pre">withdraw</span></code> function with arguments of type <code class="docutils literal notranslate"><span class="pre">uint256</span></code> and <code class="docutils literal notranslate"><span class="pre">address</span></code>, the rule checks certain conditions:</p>
<ul>
<li><p>Ensures that the sender is not the current contract (<code class="docutils literal notranslate"><span class="pre">currentContract</span></code>).</p></li>
<li><p>Requires that the variable <code class="docutils literal notranslate"><span class="pre">shares</span></code> is equal to the total supply.</p></li>
<li><p>Invokes the <code class="docutils literal notranslate"><span class="pre">withdraw</span></code> function with specified parameters (<code class="docutils literal notranslate"><span class="pre">e</span></code>, <code class="docutils literal notranslate"><span class="pre">shares</span></code>, <code class="docutils literal notranslate"><span class="pre">to</span></code>).</p></li>
<li><p>Asserts that the balance of the recipient (<code class="docutils literal notranslate"><span class="pre">to</span></code>) is greater than or equal to the balance of the current contract.</p></li>
</ul>
</li>
</ul>
</li>
<li><p><strong>Deposit Case:</strong></p>
<ul class="simple">
<li><p>If the invoked method (<code class="docutils literal notranslate"><span class="pre">f</span></code>) corresponds to the <code class="docutils literal notranslate"><span class="pre">deposit</span></code> function with arguments of type <code class="docutils literal notranslate"><span class="pre">uint256</span></code> and <code class="docutils literal notranslate"><span class="pre">address</span></code>, the rule checks similar conditions:</p>
<ul>
<li><p>Ensures that the sender is not the current contract (<code class="docutils literal notranslate"><span class="pre">currentContract</span></code>).</p></li>
<li><p>Computes the <code class="docutils literal notranslate"><span class="pre">depositedAmount</span></code> as the balance of the sender (<code class="docutils literal notranslate"><span class="pre">e.msg.sender</span></code>).</p></li>
<li><p>Invokes the <code class="docutils literal notranslate"><span class="pre">deposit</span></code> function with specified parameters (<code class="docutils literal notranslate"><span class="pre">e</span></code>, <code class="docutils literal notranslate"><span class="pre">depositedAmount</span></code>, <code class="docutils literal notranslate"><span class="pre">to</span></code>).</p></li>
<li><p>Asserts that the balance of the recipient (<code class="docutils literal notranslate"><span class="pre">to</span></code>) is greater than or equal to the balance of the sender.</p></li>
</ul>
</li>
</ul>
</li>
<li><p><strong>Default Case:</strong></p>
<ul class="simple">
<li><p>For any other method, the rule captures the state of the current contract’s balance before the method (<code class="docutils literal notranslate"><span class="pre">f</span></code>) execution in the variable <code class="docutils literal notranslate"><span class="pre">currentContract_balance_before</span></code>.</p></li>
<li><p>Invokes the method (<code class="docutils literal notranslate"><span class="pre">f</span></code>) with its corresponding arguments (<code class="docutils literal notranslate"><span class="pre">args</span></code>).</p></li>
<li><p>Asserts that the balance of the current contract after the method execution is equal to the recorded <code class="docutils literal notranslate"><span class="pre">currentContract_balance_before</span></code>.</p></li>
</ul>
</li>
</ol>
<p>This partially parametric rule demonstrates conditional logic based on the type of method invoked, allowing for specific actions and assertions tailored to different scenarios within the smart contract.</p>
</section>


           </div>
          </div>
          <footer><div class="rst-footer-buttons" role="navigation" aria-label="Footer">
        <a href="sums.html" class="btn btn-neutral float-left" title="Tracking Sums" accesskey="p" rel="prev"><span class="fa fa-arrow-circle-left" aria-hidden="true"></span> Previous</a>
        <a href="safe-assum.html" class="btn btn-neutral float-right" title="Listing Safe Assumptions" accesskey="n" rel="next">Next <span class="fa fa-arrow-circle-right" aria-hidden="true"></span></a>
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