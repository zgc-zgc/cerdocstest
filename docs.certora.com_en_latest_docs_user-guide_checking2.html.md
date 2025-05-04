<!DOCTYPE html><html class="writer-html5" lang="en" data-content_root="../../"><head>
  <meta charset="utf-8"><meta name="viewport" content="width=device-width, initial-scale=1">

  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Checking Specifications — Certora Prover Documentation 0.0 documentation</title>
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
    <link rel="next" title="CI Configuration" href="ci.html">
    <link rel="prev" title="Understanding gaps between high and low level code" href="gaps.html"> 
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
<li class="toctree-l2"><a class="reference internal" href="opcodes.html">Using Opcode Hooks</a></li>
<li class="toctree-l2"><a class="reference internal" href="multicontract/index.html">Working with Multiple Contracts</a></li>
<li class="toctree-l2"><a class="reference internal" href="out-of-resources/index.html">Managing Timeouts and Out of Memory Problems</a></li>
<li class="toctree-l2"><a class="reference internal" href="gaps.html">Understanding gaps between high and low level code</a></li>
<li class="toctree-l2 current" aria-expanded="true"><a class="reference internal current" href="#" aria-expanded="true"><button class="toctree-expand" title="Open/close menu"></button>Checking Specifications</a><ul>
<li class="toctree-l3"><a class="reference internal" href="#detecting-vacuous-specifications">Detecting Vacuous Specifications</a></li>
<li class="toctree-l3"><a class="reference internal" href="#identifying-tautology-specifications">Identifying Tautology Specifications</a></li>
<li class="toctree-l3"><a class="reference internal" href="#conclusion">Conclusion</a></li>
</ul>
</li>
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
      <li class="breadcrumb-item active">Checking Specifications</li>
      <li class="wy-breadcrumbs-aside">
            <a href="../../_sources/docs/user-guide/checking.md.txt" rel="nofollow"> View page source</a>
      </li>
  </ul>
  <hr>
</div>
          <div role="main" class="document" itemscope="itemscope" itemtype="http://schema.org/Article">
           <div itemprop="articleBody">
             
  <section id="checking-specifications">
<h1>Checking Specifications<a class="headerlink" href="#checking-specifications" title="Link to this heading"></a></h1>
<p>Effective formal verification relies on accurate specifications. A flaw in the specification could lead to critical bugs slipping through undetected. Certora offers a set of tools to enhance the accuracy of specifications and identify potential issues. This chapter outlines these tools and demonstrates their application.</p>
<section id="detecting-vacuous-specifications">
<h2>Detecting Vacuous Specifications<a class="headerlink" href="#detecting-vacuous-specifications" title="Link to this heading"></a></h2>
<p>A vacuous statement is one that is technically true but lacks meaningful content. Consider the following example:</p>
<p><strong>Contract:</strong></p>
<div class="highlight-solidity notranslate"><div class="highlight"><pre id="codecell0"><span></span><span class="kt">function</span><span class="w"> </span><span class="nv">balanceOf</span><span class="p">(</span><span class="kt">address</span><span class="w"> </span><span class="nv">account</span><span class="p">,</span><span class="w"> </span><span class="kt">uint256</span><span class="w"> </span><span class="nv">id</span><span class="p">)</span><span class="w"> </span><span class="kt">public</span><span class="w"> </span>view<span class="w"> </span>override<span class="w"> </span><span class="kt">returns</span><span class="w"> </span><span class="p">(</span><span class="kt">uint256</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kt">require</span><span class="p">(</span>account<span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="kt">address</span><span class="p">(</span><span class="m m-Decimal">0</span><span class="p">),</span><span class="w"> </span><span class="s2">"account is zero"</span><span class="p">);</span>
<span class="w">    </span><span class="kt">return</span><span class="w"> </span>_balances<span class="p">[</span>id<span class="p">][</span>account<span class="p">];</span>
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
<p><strong>Specification:</strong></p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell1"><span></span><span class="k">rule</span><span class="w"> </span><span class="nc">held_token_should_exist</span><span class="p">{</span>
<span class="w">    </span><span class="kt">address</span><span class="w"> </span>user<span class="p">;</span>
<span class="w">    </span><span class="kt">uint256</span><span class="w"> </span>token<span class="p">;</span>
<span class="w">    </span><span class="kr">require</span><span class="w"> </span>balanceOf<span class="p">(</span><span class="m m-Decimal">0</span><span class="p">,</span><span class="w"> </span>token<span class="p">)</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">;</span>

<span class="w">    </span><span class="kr">require</span><span class="w"> </span>balanceOf<span class="p">(</span>user<span class="p">,</span><span class="w"> </span>token<span class="p">)</span><span class="w"> </span><span class="o">&lt;=</span><span class="w"> </span>totalSupplyOf<span class="p">(</span>token<span class="p">);</span>
<span class="w">    </span><span class="kr">assert</span><span class="w"> </span>balanceOf<span class="p">(</span>user<span class="p">,</span><span class="w"> </span>token<span class="p">)</span><span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="w"> </span><span class="o">=&gt;</span><span class="w"> </span>token_exists<span class="p">(</span>token<span class="p">);</span>
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
<p>The specification contains a flaw; the statement <code class="docutils literal notranslate"><span class="pre">balanceOf(0,</span> <span class="pre">token)</span> <span class="pre">==</span> <span class="pre">0;</span></code> will always revert due to the <code class="docutils literal notranslate"><span class="pre">require</span></code> in the contract, resulting in an empty starting state. To address such issues, Certora allows to run <a class="reference external" href="https://docs.certora.com/en/latest/docs/prover/checking/sanity.html?highlight=rule%20sanity#sanity-vacuity">Vacuity checks</a>. These checks append <code class="docutils literal notranslate"><span class="pre">assert</span> <span class="pre">false</span></code> to each rule, exposing vacuously proven assumptions. This ensures that every rule in the specification has at least one input that reaches all the assertions. It is a useful check, but nevertheless, it is not a good measure of coverage.
For more information on coverage measures, check out <a class="reference external" href="https://docs.certora.com/en/latest/docs/prover/checking/mutation.html?highlight=rule%20mutation#mutation-testing">mutation testing</a>.</p>
<p><em>Note: Vacuity in real-world examples often arises from combinations of requirements, not just isolated statements.</em></p>
</section>
<section id="identifying-tautology-specifications">
<h2>Identifying Tautology Specifications<a class="headerlink" href="#identifying-tautology-specifications" title="Link to this heading"></a></h2>
<p>Tautology, a special case of vacuity known as the “vacuous assertion,” occurs when a statement is always true regardless of the system’s state. An example is provided below:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell2"><span></span><span class="k">rule</span><span class="w"> </span><span class="nc">something_is_always_transferred</span><span class="p">{</span>
<span class="w">    </span><span class="kt">address</span><span class="w"> </span>receiver<span class="p">;</span>
<span class="w">    </span><span class="kt">uint256</span><span class="w"> </span>balance_before_transfer<span class="w"> </span><span class="o">=</span><span class="w"> </span>balanceOf<span class="p">(</span>receiver<span class="p">);</span>
<span class="w">    </span><span class="kr">require</span><span class="w"> </span>balanceOf<span class="p">(</span>receiver<span class="p">)</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">;</span>

<span class="w">    </span><span class="kt">uint256</span><span class="w"> </span>amount<span class="p">;</span>
<span class="w">    </span><span class="kr">require</span><span class="w"> </span>amount<span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">;</span>

<span class="w">    </span>transfer<span class="p">(</span>receiver<span class="p">,</span><span class="w"> </span>amount<span class="p">);</span>
<span class="w">    </span><span class="kt">uint256</span><span class="w"> </span>balance_after_transfer<span class="w"> </span><span class="o">=</span><span class="w"> </span>balanceOf<span class="p">(</span>receiver<span class="p">);</span>
<span class="w">    </span><span class="kr">assert</span><span class="w"> </span>balanceOf<span class="p">(</span>receiver<span class="p">)</span><span class="w"> </span><span class="o">&lt;=</span><span class="w"> </span>balance_after_transfer<span class="p">;</span>
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
<p>In this case, the <code class="docutils literal notranslate"><span class="pre">assert</span></code> statement is always true since it compares equal values, neglecting any meaningful checks related to the transfer behavior. Certora allows to run <a class="reference external" href="https://docs.certora.com/en/latest/docs/prover/checking/sanity.html?highlight=rule%20sanity#assert-tautology-checks">Assert tautology checks</a> to address such instances. By removing preconditions and operations, these checks focus solely on the <code class="docutils literal notranslate"><span class="pre">assert</span></code> statement, revealing whether it is always true regardless of the process being examined.</p>
</section>
<section id="conclusion">
<h2>Conclusion<a class="headerlink" href="#conclusion" title="Link to this heading"></a></h2>
<p>For more comprehensive examples and solutions, please refer to our <a class="reference external" href="https://docs.certora.com/en/latest/docs/prover/checking/index.html">documentation</a>. Certora’s suite of verification tools empowers developers to enhance the precision of their specifications, ensuring robust and reliable smart contract development.</p>
</section>
</section>


           </div>
          </div>
          <footer><div class="rst-footer-buttons" role="navigation" aria-label="Footer">
        <a href="gaps.html" class="btn btn-neutral float-left" title="Understanding gaps between high and low level code" accesskey="p" rel="prev"><span class="fa fa-arrow-circle-left" aria-hidden="true"></span> Previous</a>
        <a href="ci.html" class="btn btn-neutral float-right" title="CI Configuration" accesskey="n" rel="next">Next <span class="fa fa-arrow-circle-right" aria-hidden="true"></span></a>
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