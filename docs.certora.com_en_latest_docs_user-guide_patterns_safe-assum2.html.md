<!DOCTYPE html><html class="writer-html5" lang="en" data-content_root="../../../"><head>
  <meta charset="utf-8"><meta name="viewport" content="width=device-width, initial-scale=1">

  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Listing Safe Assumptions — Certora Prover Documentation 0.0 documentation</title>
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
    <link rel="next" title="Require Invariants: Proving inter-dependent invariants" href="require-invariants.html">
    <link rel="prev" title="Partially Parametric Rules" href="partial-apply.html"> 
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
<li class="toctree-l3"><a class="reference internal" href="partial-apply.html">Partially Parametric Rules</a></li>
<li class="toctree-l3 current" aria-expanded="true"><a class="reference internal current" href="#" aria-expanded="true"><button class="toctree-expand" title="Open/close menu"></button>Listing Safe Assumptions</a><ul>
<li class="toctree-l4"><a class="reference internal" href="#context">Context:</a></li>
<li class="toctree-l4"><a class="reference internal" href="#importance-of-listing-safe-assumptions">Importance of Listing Safe Assumptions:</a></li>
</ul>
</li>
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
      <li class="breadcrumb-item active">Listing Safe Assumptions</li>
      <li class="wy-breadcrumbs-aside">
            <a href="../../../_sources/docs/user-guide/patterns/safe-assum.md.txt" rel="nofollow"> View page source</a>
      </li>
  </ul>
  <hr>
</div>
          <div role="main" class="document" itemscope="itemscope" itemtype="http://schema.org/Article">
           <div itemprop="articleBody">
             
  <section id="listing-safe-assumptions">
<h1>Listing Safe Assumptions<a class="headerlink" href="#listing-safe-assumptions" title="Link to this heading"></a></h1>
<p>The “Listing Safe Assumptions” design pattern introduces a structured approach to document and validate essential assumptions. Let’s delve into the importance of this design pattern using the provided example.</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell0"><span></span><span class="kr">methods</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kd">function</span><span class="w"> </span><span class="nf">isSigned</span><span class="p">(</span><span class="kt">address</span><span class="w"> </span>_addr<span class="p">,</span><span class="w"> </span><span class="kt">bytes32</span><span class="w"> </span>msgHash<span class="p">,</span><span class="w"> </span><span class="kt">uint8</span><span class="w"> </span>v<span class="p">,</span><span class="w"> </span><span class="kt">bytes32</span><span class="w"> </span>r<span class="p">,</span><span class="w"> </span><span class="kt">bytes32</span><span class="w"> </span>s<span class="p">)</span><span class="w"> </span><span class="kr">external</span><span class="w"> </span><span class="kr">returns</span><span class="w"> </span><span class="p">(</span><span class="kt">bool</span><span class="p">)</span><span class="w"> </span><span class="kr">envfree</span><span class="p">;</span>
<span class="w">    </span><span class="kd">function</span><span class="w"> </span><span class="nf">executeMyFunctionFromSignature</span><span class="p">(</span><span class="kt">uint8</span><span class="w"> </span>v<span class="p">,</span><span class="w"> </span><span class="kt">bytes32</span><span class="w"> </span>r<span class="p">,</span><span class="w"> </span><span class="kt">bytes32</span><span class="w"> </span>s<span class="p">,</span><span class="w"> </span><span class="kt">address</span><span class="w"> </span>owner<span class="p">,</span><span class="w"> </span><span class="kt">uint256</span><span class="w"> </span>myParam<span class="p">,</span><span class="w"> </span><span class="kt">uint256</span><span class="w"> </span>deadline<span class="p">)</span><span class="w"> </span><span class="kr">external</span><span class="p">;</span>
<span class="w">    </span><span class="kd">function</span><span class="w"> </span><span class="nf">getHash</span><span class="p">(</span><span class="kt">address</span><span class="w"> </span>owner<span class="p">,</span><span class="w"> </span><span class="kt">uint256</span><span class="w"> </span>myParam<span class="p">,</span><span class="w"> </span><span class="kt">uint256</span><span class="w"> </span>deadline<span class="p">)</span><span class="w"> </span><span class="kr">external</span><span class="w"> </span><span class="kr">returns</span><span class="p">(</span><span class="kt">bytes32</span><span class="p">)</span><span class="w"> </span><span class="kr">envfree</span><span class="p">;</span>
<span class="p">}</span>

<span class="cm">/*** # ecrecover properties:</span>
<span class="cm"># 1. zero value:</span>
<span class="cm">        ecrecover(0, v, r, s) == 0</span>
<span class="cm"># 2. deterministic </span>
<span class="cm">        ecrecover(msgHash, v, r, s) == _addr on different calls.  </span>
<span class="cm"># 3. uniqueness of signature</span>
<span class="cm">        ecrecover(msgHash, v, r, s) != 0 =&gt; ecrecover(msgHash', v, r, s) == 0</span>
<span class="cm">        where msgHash' != msgHash</span>
<span class="cm"># 4. Dependency on r and s</span>
<span class="cm">        ecrecover(msgHash, v, r, s) != 0 =&gt; ecrecover(msgHash, v, r', s) == 0</span>
<span class="cm">        where r' != r</span>
<span class="cm">        ecrecover(msgHash, v, r, s) != 0 =&gt; ecrecover(msgHash, v, r, s') == 0</span>
<span class="cm">        where s' != s</span>
<span class="cm">**/</span>

<span class="kt">function</span><span class="w"> </span><span class="nf">ecrecoverAxioms</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<span class="w">  </span><span class="c1">// zero value:</span>
<span class="w">  </span><span class="kr">require</span><span class="w"> </span><span class="p">(</span><span class="kr">forall</span><span class="w"> </span><span class="kt">uint8</span><span class="w"> </span>v<span class="p">.</span><span class="w"> </span><span class="kr">forall</span><span class="w"> </span><span class="kt">bytes32</span><span class="w"> </span>r<span class="p">.</span><span class="w"> </span><span class="kr">forall</span><span class="w"> </span><span class="kt">bytes32</span><span class="w"> </span>s<span class="p">.</span><span class="w"> </span>ecrecover<span class="p">(</span><span class="nb">to_bytes32</span><span class="p">(</span><span class="m m-Decimal">0</span><span class="p">),</span><span class="w"> </span>v<span class="p">,</span><span class="w"> </span>r<span class="p">,</span><span class="w"> </span>s<span class="p">)</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">);</span>
<span class="w">  </span><span class="c1">// uniqueness of signature</span>
<span class="w">  </span><span class="kr">require</span><span class="w"> </span><span class="p">(</span><span class="kr">forall</span><span class="w"> </span><span class="kt">uint8</span><span class="w"> </span>v<span class="p">.</span><span class="w"> </span><span class="kr">forall</span><span class="w"> </span><span class="kt">bytes32</span><span class="w"> </span>r<span class="p">.</span><span class="w"> </span><span class="kr">forall</span><span class="w"> </span><span class="kt">bytes32</span><span class="w"> </span>s<span class="p">.</span><span class="w"> </span><span class="kr">forall</span><span class="w"> </span><span class="kt">bytes32</span><span class="w"> </span>h1<span class="p">.</span><span class="w"> </span><span class="kr">forall</span><span class="w"> </span><span class="kt">bytes32</span><span class="w"> </span>h2<span class="p">.</span>
<span class="w">    </span>h1<span class="w"> </span><span class="o">!=</span><span class="w"> </span>h2<span class="w"> </span><span class="o">=&gt;</span><span class="w"> </span>ecrecover<span class="p">(</span>h1<span class="p">,</span><span class="w"> </span>v<span class="p">,</span><span class="w"> </span>r<span class="p">,</span><span class="w"> </span>s<span class="p">)</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="w"> </span><span class="o">=&gt;</span><span class="w"> </span>ecrecover<span class="p">(</span>h2<span class="p">,</span><span class="w"> </span>v<span class="p">,</span><span class="w"> </span>r<span class="p">,</span><span class="w"> </span>s<span class="p">)</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">);</span>
<span class="w">  </span><span class="c1">// dependency on r and s</span>
<span class="w">  </span><span class="kr">require</span><span class="w"> </span><span class="p">(</span><span class="kr">forall</span><span class="w"> </span><span class="kt">bytes32</span><span class="w"> </span>h<span class="p">.</span><span class="w"> </span><span class="kr">forall</span><span class="w"> </span><span class="kt">uint8</span><span class="w"> </span>v<span class="p">.</span><span class="w"> </span><span class="kr">forall</span><span class="w"> </span><span class="kt">bytes32</span><span class="w"> </span>s<span class="p">.</span><span class="w"> </span><span class="kr">forall</span><span class="w"> </span><span class="kt">bytes32</span><span class="w"> </span>r1<span class="p">.</span><span class="w"> </span><span class="kr">forall</span><span class="w"> </span><span class="kt">bytes32</span><span class="w"> </span>r2<span class="p">.</span>
<span class="w">    </span>r1<span class="w"> </span><span class="o">!=</span><span class="w"> </span>r2<span class="w"> </span><span class="o">=&gt;</span><span class="w"> </span>ecrecover<span class="p">(</span>h<span class="p">,</span><span class="w"> </span>v<span class="p">,</span><span class="w"> </span>r1<span class="p">,</span><span class="w"> </span>s<span class="p">)</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="w"> </span><span class="o">=&gt;</span><span class="w"> </span>ecrecover<span class="p">(</span>h<span class="p">,</span><span class="w"> </span>v<span class="p">,</span><span class="w"> </span>r2<span class="p">,</span><span class="w"> </span>s<span class="p">)</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">);</span>
<span class="w">  </span><span class="kr">require</span><span class="w"> </span><span class="p">(</span><span class="kr">forall</span><span class="w"> </span><span class="kt">bytes32</span><span class="w"> </span>h<span class="p">.</span><span class="w"> </span><span class="kr">forall</span><span class="w"> </span><span class="kt">uint8</span><span class="w"> </span>v<span class="p">.</span><span class="w"> </span><span class="kr">forall</span><span class="w"> </span><span class="kt">bytes32</span><span class="w"> </span>r<span class="p">.</span><span class="w"> </span><span class="kr">forall</span><span class="w"> </span><span class="kt">bytes32</span><span class="w"> </span>s1<span class="p">.</span><span class="w"> </span><span class="kr">forall</span><span class="w"> </span><span class="kt">bytes32</span><span class="w"> </span>s2<span class="p">.</span>
<span class="w">    </span>s1<span class="w"> </span><span class="o">!=</span><span class="w"> </span>s2<span class="w"> </span><span class="o">=&gt;</span><span class="w"> </span>ecrecover<span class="p">(</span>h<span class="p">,</span><span class="w"> </span>v<span class="p">,</span><span class="w"> </span>r<span class="p">,</span><span class="w"> </span>s1<span class="p">)</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="w"> </span><span class="o">=&gt;</span><span class="w"> </span>ecrecover<span class="p">(</span>h<span class="p">,</span><span class="w"> </span>v<span class="p">,</span><span class="w"> </span>r<span class="p">,</span><span class="w"> </span>s2<span class="p">)</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">);</span>
<span class="p">}</span>

<span class="k">rule</span><span class="w"> </span><span class="nc">ownerSignatureIsUnique</span><span class="w"> </span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span>ecrecoverAxioms<span class="p">();</span>
<span class="w">    </span><span class="kt">bytes32</span><span class="w"> </span>msgHashA<span class="p">;</span><span class="w"> </span><span class="kt">bytes32</span><span class="w"> </span>msgHashB<span class="p">;</span>
<span class="w">    </span><span class="kt">uint8</span><span class="w"> </span>v<span class="p">;</span><span class="w"> </span><span class="kt">bytes32</span><span class="w"> </span>r<span class="p">;</span><span class="w"> </span><span class="kt">bytes32</span><span class="w"> </span>s<span class="p">;</span><span class="w"> </span>
<span class="w">    </span><span class="kt">address</span><span class="w"> </span>addr<span class="p">;</span><span class="w"> </span>
<span class="w">    </span><span class="kr">require</span><span class="w"> </span>msgHashA<span class="w"> </span><span class="o">!=</span><span class="w"> </span>msgHashB<span class="p">;</span><span class="w"> </span>
<span class="w">    </span><span class="kr">require</span><span class="w"> </span>addr<span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">;</span>
<span class="w">    </span><span class="kr">assert</span><span class="w"> </span>isSigned<span class="p">(</span>addr<span class="p">,</span><span class="w"> </span>msgHashA<span class="p">,</span><span class="w"> </span>v<span class="p">,</span><span class="w"> </span>r<span class="p">,</span><span class="w"> </span>s<span class="w"> </span><span class="p">)</span><span class="w"> </span><span class="o">=&gt;</span><span class="w"> </span><span class="o">!</span>isSigned<span class="p">(</span>addr<span class="p">,</span><span class="w"> </span>msgHashB<span class="p">,</span><span class="w"> </span>v<span class="p">,</span><span class="w"> </span>r<span class="p">,</span><span class="w"> </span>s<span class="w"> </span><span class="p">);</span>
<span class="p">}</span>

<span class="k">invariant</span><span class="w"> </span><span class="nc">zero_message</span><span class="p">(</span><span class="kt">uint8</span><span class="w"> </span>v<span class="p">,</span><span class="w"> </span><span class="kt">bytes32</span><span class="w"> </span>r<span class="p">,</span><span class="w"> </span><span class="kt">bytes32</span><span class="w"> </span>s<span class="p">)</span>
<span class="w">    </span>ecrecover<span class="p">(</span><span class="nb">to_bytes32</span><span class="p">(</span><span class="m m-Decimal">0</span><span class="p">),</span><span class="w"> </span>v<span class="p">,</span><span class="w"> </span>r<span class="p">,</span><span class="w"> </span>s<span class="p">)</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">;</span>
<span class="w">    </span><span class="p">{</span><span class="w"> </span>
<span class="w">        </span><span class="kr">preserved</span><span class="w"> </span><span class="p">{</span>
<span class="w">            </span>ecrecoverAxioms<span class="p">();</span>
<span class="w">        </span><span class="p">}</span>
<span class="w">    </span><span class="p">}</span><span class="w"> </span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell0">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<section id="context">
<h2>Context:<a class="headerlink" href="#context" title="Link to this heading"></a></h2>
<p>In the example, we focus on the <code class="docutils literal notranslate"><span class="pre">ecrecover</span></code> function used for signature verification. The objective is to articulate and validate key assumptions associated with this function to bolster the security of smart contracts.</p>
</section>
<section id="importance-of-listing-safe-assumptions">
<h2>Importance of Listing Safe Assumptions:<a class="headerlink" href="#importance-of-listing-safe-assumptions" title="Link to this heading"></a></h2>
<ol class="arabic simple">
<li><p><strong>Clarity and Documentation:</strong></p>
<ul class="simple">
<li><p>The design pattern begins by explicitly listing assumptions related to the <code class="docutils literal notranslate"><span class="pre">ecrecover</span></code> function. This serves as clear documentation for developers, auditors, and anyone reviewing the spec. Clarity in assumptions enhances the understanding of expected behavior.</p></li>
</ul>
</li>
<li><p><strong>Preventing Unexpected Behavior:</strong></p>
<ul class="simple">
<li><p>The axioms established in the example, such as the zero message axiom and uniqueness of signature axiom, act as preventive measures against unexpected behavior. They set clear expectations for how the <code class="docutils literal notranslate"><span class="pre">ecrecover</span></code> function should behave under different circumstances, neglect all the counter-examples that are not relevant to the function intended behavior.</p></li>
</ul>
</li>
<li><p><strong>Easy To Use:</strong></p>
<ul class="simple">
<li><p>By encapsulating assumptions within the CVL function, this design pattern allow us to easily use those assumptions in any rule or invariant we desire.</p></li>
</ul>
</li>
</ol>
<p>In conclusion, the “Listing Safe Assumptions” design pattern, exemplified through the <code class="docutils literal notranslate"><span class="pre">ecrecover</span></code> function in the provided example,
serves a broader purpose in specs writing. It systematically documents assumptions, prevents unexpected behaviors,
and offers ease of use throughout the rules and invariants.</p>
</section>
</section>


           </div>
          </div>
          <footer><div class="rst-footer-buttons" role="navigation" aria-label="Footer">
        <a href="partial-apply.html" class="btn btn-neutral float-left" title="Partially Parametric Rules" accesskey="p" rel="prev"><span class="fa fa-arrow-circle-left" aria-hidden="true"></span> Previous</a>
        <a href="require-invariants.html" class="btn btn-neutral float-right" title="Require Invariants: Proving inter-dependent invariants" accesskey="n" rel="next">Next <span class="fa fa-arrow-circle-right" aria-hidden="true"></span></a>
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