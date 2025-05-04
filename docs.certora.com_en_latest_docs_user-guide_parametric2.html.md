<!DOCTYPE html><html class="writer-html5" lang="en" data-content_root="../../"><head>
  <meta charset="utf-8"><meta name="viewport" content="width=device-width, initial-scale=1">

  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Parametric rules — Certora Prover Documentation 0.0 documentation</title>
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
    <link rel="next" title="Tracking changes with ghosts and hooks" href="ghosts.html">
    <link rel="prev" title="Invariants" href="invariants.html"> 
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
<li class="toctree-l2"><a class="reference internal" href="satisfy.html">Producing Positive Examples</a></li>
<li class="toctree-l2"><a class="reference internal" href="invariants.html">Invariants</a></li>
<li class="toctree-l2 current" aria-expanded="true"><a class="reference internal current" href="#" aria-expanded="true"><button class="toctree-expand" title="Open/close menu"></button>Parametric rules</a><ul>
<li class="toctree-l3"><a class="reference internal" href="#general">General</a></li>
<li class="toctree-l3"><a class="reference internal" href="#erc20-example">ERC20 example</a></li>
</ul>
</li>
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
      <li class="breadcrumb-item active">Parametric rules</li>
      <li class="wy-breadcrumbs-aside">
            <a href="../../_sources/docs/user-guide/parametric.rst.txt" rel="nofollow"> View page source</a>
      </li>
  </ul>
  <hr>
</div>
          <div role="main" class="document" itemscope="itemscope" itemtype="http://schema.org/Article">
           <div itemprop="articleBody">
             
  <section id="parametric-rules">
<span id="index-0"></span><h1>Parametric rules<a class="headerlink" href="#parametric-rules" title="Link to this heading"></a></h1>
<section id="general">
<h2>General<a class="headerlink" href="#general" title="Link to this heading"></a></h2>
<p>A <a class="reference internal" href="glossary.html#term-parametric-rule"><span class="xref std std-term">parametric rule</span></a> is a rule that uses a <code class="code highlight cvl docutils literal highlight-cvl"><span class="kt">method</span><span class="w"> </span>f</code> parameter.
Such a rule will be tested against all possible methods <code class="code highlight cvl docutils literal highlight-cvl">f</code>, including methods from
other contracts in the <a class="reference internal" href="glossary.html#term-0"><span class="xref std std-term">scene</span></a>.
It is possible to limit the methods tested, see <a class="reference internal" href="../cvl/rules.html#parametric-rules"><span class="std std-ref">Parametric rules</span></a>.</p>
<p>Parametric rules can be used to verify properties of the changes in storage values.
The template for such checks is:</p>
<div class="literal-block-wrapper docutils container" id="id1">
<div class="code-block-caption"><span class="caption-text">Parametric rule template</span><a class="headerlink" href="#id1" title="Link to this code"></a></div>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell0"><span></span><span class="k">rule</span><span class="w"> </span><span class="nc">parametricExample</span><span class="p">(</span><span class="kt">method</span><span class="w"> </span>f<span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="c1">// Get storage values before</span>
<span class="w">    </span><span class="kt">uint</span><span class="w"> </span>before<span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="p">...;</span>
<span class="w">    </span><span class="p">...</span>

<span class="w">    </span><span class="c1">// Function call</span>
<span class="w">    </span><span class="kt">env</span><span class="w"> </span>e<span class="p">;</span>
<span class="w">    </span><span class="kt">calldataarg</span><span class="w"> </span>args<span class="p">;</span>
<span class="w">    </span>f<span class="p">(</span>e<span class="p">,</span><span class="w"> </span>args<span class="p">)</span>

<span class="w">    </span><span class="c1">// Get storage values after</span>
<span class="w">    </span><span class="kt">uint</span><span class="w"> </span>after<span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="p">...;</span>
<span class="w">    </span><span class="p">...</span>

<span class="w">    </span><span class="c1">// Assert property of the change, e.g.:</span>
<span class="w">    </span><span class="kr">assert</span><span class="w"> </span>after<span class="w"> </span><span class="o">-</span><span class="w"> </span>before<span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="p">...;</span>
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
<p>The main differences between parametric rules and invariants are:</p>
<ol class="arabic simple">
<li><p>Invariants are also tested after the constructor.</p></li>
<li><p>Invariants are used to assert properties of the storage (between function calls),
while parametric rules are used to assert properties of <em>changes</em> in the storage
(caused by function calls).</p></li>
</ol>
</section>
<section id="erc20-example">
<h2>ERC20 example<a class="headerlink" href="#erc20-example" title="Link to this heading"></a></h2>
<p>Here is a parametric rule example from the spec file
<a class="reference external" href="https://github.com/Certora/Examples/blob/7dfc379423202c90cf284eb42800b97cf5c95d83/DEFI/ERC20/certora/specs/ERC20Full.spec">ERC20Full.spec</a> – a spec
for an ERC20 implementation.
The parametric rule <code class="code highlight cvl docutils literal highlight-cvl">onlyAllowedMethodsMayChangeBalance</code> asserts two things:</p>
<ol class="arabic simple">
<li><p>A user’s balance can increase only by calls to <code class="code highlight solidity docutils literal highlight-solidity">mint</code>,
<code class="code highlight solidity docutils literal highlight-solidity">transfer</code>, and <code class="code highlight solidity docutils literal highlight-solidity">transferFrom</code>.</p></li>
<li><p>A user’s balance can decrease only by calls to <code class="code highlight solidity docutils literal highlight-solidity">burn</code>,
<code class="code highlight solidity docutils literal highlight-solidity">transfer</code>, and <code class="code highlight solidity docutils literal highlight-solidity">transferFrom</code>.</p></li>
</ol>
<p>It follows that all other functions do not change balances.
The rule is shown below, with the lines for getting the storage value before and after
the function call highlighted.
The two helper functions used in the rule are explained below the rule.</p>
<div class="literal-block-wrapper docutils container" id="id2">
<div class="code-block-caption"><span class="caption-text"><a class="reference external" href="https://github.com/Certora/Examples/blob/7dfc379423202c90cf284eb42800b97cf5c95d83/DEFI/ERC20/certora/specs/ERC20Full.spec">onlyAllowedMethodsMayChangeBalance</a></span><a class="headerlink" href="#id2" title="Link to this code"></a></div>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell1"><span></span><span class="k">rule</span><span class="w"> </span><span class="nc">onlyAllowedMethodsMayChangeBalance</span><span class="p">(</span><span class="kt">env</span><span class="w"> </span>e<span class="p">){</span>
<span class="w">    </span><span class="kr">requireInvariant</span><span class="w"> </span>totalSupplyIsSumOfBalances<span class="p">();</span>

<span class="w">    </span><span class="kt">method</span><span class="w"> </span>f<span class="p">;</span>
<span class="w">    </span><span class="kt">calldataarg</span><span class="w"> </span>args<span class="p">;</span>

<span class="w">    </span><span class="kt">address</span><span class="w"> </span>holder<span class="p">;</span>
<span class="hll"><span class="w">    </span><span class="kt">uint256</span><span class="w"> </span>balanceBefore<span class="w"> </span><span class="o">=</span><span class="w"> </span>balanceOf<span class="p">(</span>holder<span class="p">);</span>
</span><span class="w">    </span>f<span class="p">(</span>e<span class="p">,</span><span class="w"> </span>args<span class="p">);</span>
<span class="hll"><span class="w">    </span><span class="kt">uint256</span><span class="w"> </span>balanceAfter<span class="w"> </span><span class="o">=</span><span class="w"> </span>balanceOf<span class="p">(</span>holder<span class="p">);</span>
</span><span class="w">    </span>
<span class="w">    </span><span class="kr">assert</span><span class="w"> </span>balanceAfter<span class="w"> </span><span class="o">&gt;</span><span class="w"> </span>balanceBefore<span class="w"> </span><span class="o">=&gt;</span><span class="w"> </span>canIncreaseBalance<span class="p">(</span>f<span class="p">);</span>
<span class="w">    </span><span class="kr">assert</span><span class="w"> </span>balanceAfter<span class="w"> </span><span class="o">&lt;</span><span class="w"> </span>balanceBefore<span class="w"> </span><span class="o">=&gt;</span><span class="w"> </span>canDecreaseBalance<span class="p">(</span>f<span class="p">);</span>
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
</div>
<ul class="simple">
<li><p>The function <code class="code highlight cvl docutils literal highlight-cvl">canIncreaseBalance<span class="p">(</span>f<span class="p">)</span></code> returns true if
<code class="code highlight cvl docutils literal highlight-cvl">f</code> is one of the functions <code class="code highlight solidity docutils literal highlight-solidity">mint</code>, <code class="code highlight solidity docutils literal highlight-solidity">transfer</code>, or
<code class="code highlight solidity docutils literal highlight-solidity">transferFrom</code>.</p></li>
<li><p>Similarly, <code class="code highlight cvl docutils literal highlight-cvl">canDecreaseBalance<span class="p">(</span>f<span class="p">)</span></code> returns true
if <code class="code highlight cvl docutils literal highlight-cvl">f</code> is one of <code class="code highlight solidity docutils literal highlight-solidity">burn</code>, <code class="code highlight solidity docutils literal highlight-solidity">transfer</code>, or
<code class="code highlight solidity docutils literal highlight-solidity">transferFrom</code>.</p></li>
</ul>
<details class="sd-sphinx-override sd-dropdown sd-card sd-mb-3">
<summary class="sd-summary-title sd-card-header">
<span class="sd-summary-text">The helper functions <code class="code highlight cvl docutils literal highlight-cvl">canIncreaseBalance</code> and <code class="code highlight cvl docutils literal highlight-cvl">canDecreaseBalance</code></span><span class="sd-summary-state-marker sd-summary-chevron-right"><svg version="1.1" width="1.5em" height="1.5em" class="sd-octicon sd-octicon-chevron-right" viewBox="0 0 24 24" aria-hidden="true"><path d="M8.72 18.78a.75.75 0 0 1 0-1.06L14.44 12 8.72 6.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018l6.25 6.25a.75.75 0 0 1 0 1.06l-6.25 6.25a.75.75 0 0 1-1.06 0Z"></path></svg></span></summary><div class="sd-summary-content sd-card-body docutils">
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell2"><span></span><span class="kt">definition</span><span class="w"> </span><span class="nf">canIncreaseBalance</span><span class="p">(</span><span class="kt">method</span><span class="w"> </span>f<span class="p">)</span><span class="w"> </span><span class="kr">returns</span><span class="w"> </span><span class="kt">bool</span><span class="w"> </span><span class="o">=</span><span class="w"> </span>
<span class="w">	</span>f<span class="p">.</span><span class="nb">selector</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="kd">sig</span><span class="o">:</span><span class="nf">mint</span><span class="p">(</span><span class="kt">address</span><span class="p">,</span><span class="kt">uint256</span><span class="p">).</span><span class="nb">selector</span><span class="w"> </span><span class="o">||</span><span class="w"> </span>
<span class="w">	</span>f<span class="p">.</span><span class="nb">selector</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="kd">sig</span><span class="o">:</span><span class="nf">transfer</span><span class="p">(</span><span class="kt">address</span><span class="p">,</span><span class="kt">uint256</span><span class="p">).</span><span class="nb">selector</span><span class="w"> </span><span class="o">||</span>
<span class="w">	</span>f<span class="p">.</span><span class="nb">selector</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="kd">sig</span><span class="o">:</span><span class="nf">transferFrom</span><span class="p">(</span><span class="kt">address</span><span class="p">,</span><span class="kt">address</span><span class="p">,</span><span class="kt">uint256</span><span class="p">).</span><span class="nb">selector</span><span class="p">;</span>

<span class="kt">definition</span><span class="w"> </span><span class="nf">canDecreaseBalance</span><span class="p">(</span><span class="kt">method</span><span class="w"> </span>f<span class="p">)</span><span class="w"> </span><span class="kr">returns</span><span class="w"> </span><span class="kt">bool</span><span class="w"> </span><span class="o">=</span><span class="w"> </span>
<span class="w">	</span>f<span class="p">.</span><span class="nb">selector</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="kd">sig</span><span class="o">:</span><span class="nf">burn</span><span class="p">(</span><span class="kt">address</span><span class="p">,</span><span class="kt">uint256</span><span class="p">).</span><span class="nb">selector</span><span class="w"> </span><span class="o">||</span><span class="w"> </span>
<span class="w">	</span>f<span class="p">.</span><span class="nb">selector</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="kd">sig</span><span class="o">:</span><span class="nf">transfer</span><span class="p">(</span><span class="kt">address</span><span class="p">,</span><span class="kt">uint256</span><span class="p">).</span><span class="nb">selector</span><span class="w"> </span><span class="o">||</span>
<span class="w">	</span>f<span class="p">.</span><span class="nb">selector</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="kd">sig</span><span class="o">:</span><span class="nf">transferFrom</span><span class="p">(</span><span class="kt">address</span><span class="p">,</span><span class="kt">address</span><span class="p">,</span><span class="kt">uint256</span><span class="p">).</span><span class="nb">selector</span><span class="p">;</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell2">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</div>
</details><div class="admonition seealso">
<p class="admonition-title">See also</p>
<p>There is more information about parametric rules in <a class="reference internal" href="../cvl/rules.html#parametric-rules"><span class="std std-ref">Parametric rules</span></a>.</p>
</div>
</section>
</section>


           </div>
          </div>
          <footer><div class="rst-footer-buttons" role="navigation" aria-label="Footer">
        <a href="invariants.html" class="btn btn-neutral float-left" title="Invariants" accesskey="p" rel="prev"><span class="fa fa-arrow-circle-left" aria-hidden="true"></span> Previous</a>
        <a href="ghosts.html" class="btn btn-neutral float-right" title="Tracking changes with ghosts and hooks" accesskey="n" rel="next">Next <span class="fa fa-arrow-circle-right" aria-hidden="true"></span></a>
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