<!DOCTYPE html><html class="writer-html5" lang="en" data-content_root="../../../"><head>
  <meta charset="utf-8"><meta name="viewport" content="width=device-width, initial-scale=1">

  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Working with Multiple Contracts — Certora Prover Documentation 0.0 documentation</title>
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
    <link rel="next" title="Managing Timeouts and Out of Memory Problems" href="../out-of-resources/index.html">
    <link rel="prev" title="Using Opcode Hooks" href="../opcodes.html"> 
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
<li class="toctree-l2"><a class="reference internal" href="../patterns/index.html">Specification Design Patterns</a></li>
<li class="toctree-l2"><a class="reference internal" href="../opcodes.html">Using Opcode Hooks</a></li>
<li class="toctree-l2 current" aria-expanded="true"><a class="reference internal current" href="#" aria-expanded="true"><button class="toctree-expand" title="Open/close menu"></button>Working with Multiple Contracts</a><ul>
<li class="toctree-l3"><a class="reference internal" href="#example-protocol">Example protocol</a></li>
<li class="toctree-l3"><a class="reference internal" href="#handling-unresolved-method-calls">Handling unresolved method calls</a></li>
<li class="toctree-l3"><a class="reference internal" href="#working-with-known-contracts"><button class="toctree-expand" title="Open/close menu"></button>Working with known contracts</a><ul>
<li class="toctree-l4"><a class="reference internal" href="#accessing-additional-contracts-from-cvl">Accessing additional contracts from CVL</a></li>
</ul>
</li>
<li class="toctree-l3"><a class="reference internal" href="#working-with-unknown-contracts"><button class="toctree-expand" title="Open/close menu"></button>Working with unknown contracts</a><ul>
<li class="toctree-l4"><a class="reference internal" href="#the-dangers-of-dispatcher">The dangers of <code class="docutils literal notranslate"><span class="pre">DISPATCHER</span></code></a></li>
<li class="toctree-l4"><a class="reference internal" href="#designing-flexible-dispatchees">Designing flexible dispatchees</a></li>
<li class="toctree-l4"><a class="reference internal" href="#using-dispatcher-for-erc20-contracts">Using <code class="docutils literal notranslate"><span class="pre">DISPATCHER</span></code> for ERC20 contracts</a></li>
</ul>
</li>
<li class="toctree-l3"><a class="reference internal" href="#conclusion">Conclusion</a></li>
</ul>
</li>
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
      <li class="breadcrumb-item active">Working with Multiple Contracts</li>
      <li class="wy-breadcrumbs-aside">
            <a href="../../../_sources/docs/user-guide/multicontract/index.md.txt" rel="nofollow"> View page source</a>
      </li>
  </ul>
  <hr>
</div>
          <div role="main" class="document" itemscope="itemscope" itemtype="http://schema.org/Article">
           <div itemprop="articleBody">
             
  <section id="working-with-multiple-contracts">
<h1><a class="toc-backref" href="#id21" role="doc-backlink">Working with Multiple Contracts</a><a class="headerlink" href="#working-with-multiple-contracts" title="Link to this heading"></a></h1>
<p>In the previous chapter, we focused on rules describing the behavior of a
single contract.  In practice, most protocols consist of multiple interacting
contracts.  In this chapter, we discuss techniques for verifying protocols
involving multiple contracts.</p>
<p>We begin by walking through a running example protocol and explaining the
Prover’s default behavior when it encounters calls from one contract to
another.  We then show how to handle a protocol consisting of multiple
contracts whose implementation is known.  After that, we discuss dispatcher
summaries, an important technique for handling contracts whose implementation
is not known at verification time.  Finally, we give a concrete and reusable
setup for a very common case: a contract that can work with many different ERC20
implementations.</p>
<p>The entire running example for this chapter can be found <a class="reference external" href="https://github.com/Certora/Examples/tree/7dfc379423202c90cf284eb42800b97cf5c95d83/DEFI/LiquidityPool">here</a>.</p>
<nav class="contents" id="contents">
<p class="topic-title">Contents</p>
<ul class="simple">
<li><p><a class="reference internal" href="#working-with-multiple-contracts" id="id21">Working with Multiple Contracts</a></p>
<ul>
<li><p><a class="reference internal" href="#example-protocol" id="id22">Example protocol</a></p></li>
<li><p><a class="reference internal" href="#handling-unresolved-method-calls" id="id23">Handling unresolved method calls</a></p></li>
<li><p><a class="reference internal" href="#working-with-known-contracts" id="id24">Working with known contracts</a></p>
<ul>
<li><p><a class="reference internal" href="#accessing-additional-contracts-from-cvl" id="id25">Accessing additional contracts from CVL</a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#working-with-unknown-contracts" id="id26">Working with unknown contracts</a></p>
<ul>
<li><p><a class="reference internal" href="#the-dangers-of-dispatcher" id="id27">The dangers of <code class="docutils literal notranslate"><span class="pre">DISPATCHER</span></code></a></p></li>
<li><p><a class="reference internal" href="#designing-flexible-dispatchees" id="id28">Designing flexible dispatchees</a></p></li>
<li><p><a class="reference internal" href="#using-dispatcher-for-erc20-contracts" id="id29">Using <code class="docutils literal notranslate"><span class="pre">DISPATCHER</span></code> for ERC20 contracts</a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#conclusion" id="id30">Conclusion</a></p></li>
</ul>
</li>
</ul>
</nav>
<section id="example-protocol">
<h2><a class="toc-backref" href="#id22" role="doc-backlink">Example protocol</a><a class="headerlink" href="#example-protocol" title="Link to this heading"></a></h2>
<p>To demonstrate these concepts, we work with a simplified liquidity pool contract called
<a class="reference external" href="https://github.com/Certora/Examples/blob/7dfc379423202c90cf284eb42800b97cf5c95d83/DEFI/LiquidityPool/contracts/Pool.sol">Pool</a>.
The <a class="reference external" href="https://github.com/Certora/Examples/blob/7dfc379423202c90cf284eb42800b97cf5c95d83/DEFI/LiquidityPool/certora/specs/Full.spec">full specification</a> is in
<code class="docutils literal notranslate"><span class="pre">certora/specs/Full.spec</span></code> (although this chapter only discusses the
<code class="docutils literal notranslate"><span class="pre">integrityOfDeposit</span></code> and <code class="docutils literal notranslate"><span class="pre">flashLoanIncreasesBalance</span></code> properties) and the
<a class="reference external" href="https://github.com/Certora/Examples/blob/7dfc379423202c90cf284eb42800b97cf5c95d83/DEFI/LiquidityPool/runFullPool.conf">final run conf</a> is in <code class="docutils literal notranslate"><span class="pre">runFullPool.conf</span></code>.</p>
<p>The liquidity pool allows users to deposit and withdraw a single fixed type of
ERC20 token (the <code class="docutils literal notranslate"><span class="pre">asset</span></code>). The liquidity pool itself is an ERC20 token and
balance in the liquidity pool token denotes the <em>shares</em> in the pool.
We’ll reserve the words <em>amount</em> and <em>assets</em> to denote balance in the <code class="docutils literal notranslate"><span class="pre">asset</span></code>.
So, in return for depositing <em>assets</em> the user receives <em>shares</em> in the pool.
Withdrawing decreases the user’s shares and increases the user’ assets.</p>
<p>Here is the interface for the pool, followed by the Pool’s code.</p>
<div class="literal-block-wrapper docutils container" id="id10">
<div class="code-block-caption"><span class="caption-text"><a class="reference external" href="https://github.com/Certora/Examples/blob/7dfc379423202c90cf284eb42800b97cf5c95d83/DEFI/LiquidityPool/contracts/IPool.sol">IPool interface</a></span><a class="headerlink" href="#id10" title="Link to this code"></a></div>
<div class="highlight-solidity notranslate"><div class="highlight"><pre id="codecell0"><span></span><span class="k">pragma solidity</span><span class="w"> </span><span class="o">&gt;=</span><span class="k">0.8.0</span><span class="p">;</span>

<span class="kt">import</span><span class="w"> </span><span class="s2">"./IERC20.sol"</span><span class="p">;</span>

interface<span class="w"> </span>IPool<span class="w"> </span><span class="kt">is</span><span class="w"> </span>IERC20<span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="c1">// Deposit amount of underlying token returning the amount of shares minted to msg.sender   </span>
<span class="w">    </span><span class="kt">function</span><span class="w"> </span><span class="nv">deposit</span><span class="p">(</span><span class="kt">uint256</span><span class="w"> </span><span class="nv">amount</span><span class="p">)</span><span class="w"> </span><span class="kt">external</span><span class="w"> </span><span class="kt">payable</span><span class="w"> </span><span class="kt">returns</span><span class="p">(</span><span class="kt">uint256</span><span class="p">);</span>
<span class="w">    </span><span class="c1">// Withdraw shares and returns the anount of underlying token transfered to msg.sender </span>
<span class="w">    </span><span class="kt">function</span><span class="w"> </span><span class="nv">withdraw</span><span class="p">(</span><span class="kt">uint256</span><span class="w"> </span><span class="nv">shares</span><span class="p">)</span><span class="w"> </span><span class="kt">external</span><span class="w"> </span><span class="kt">returns</span><span class="w"> </span><span class="p">(</span><span class="kt">uint256</span><span class="p">);</span>
<span class="w">    </span><span class="c1">// Flashlaon an amount of underlying token and calls reciverAddress </span>
<span class="w">    </span><span class="kt">function</span><span class="w"> </span><span class="nv">flashLoan</span><span class="p">(</span><span class="kt">address</span><span class="w"> </span><span class="nv">receiverAddress</span><span class="p">,</span><span class="w"> </span><span class="kt">uint256</span><span class="w"> </span><span class="nv">amount</span><span class="p">)</span><span class="w"> </span><span class="kt">external</span><span class="w"> </span><span class="p">;</span>
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
<details class="sd-sphinx-override sd-dropdown sd-card sd-mb-3">
<summary class="sd-summary-title sd-card-header">
<span class="sd-summary-text"><a class="reference external" href="https://github.com/Certora/Examples/blob/7dfc379423202c90cf284eb42800b97cf5c95d83/DEFI/LiquidityPool/contracts/Pool.sol">Pool.sol</a></span><span class="sd-summary-state-marker sd-summary-chevron-right"><svg version="1.1" width="1.5em" height="1.5em" class="sd-octicon sd-octicon-chevron-right" viewBox="0 0 24 24" aria-hidden="true"><path d="M8.72 18.78a.75.75 0 0 1 0-1.06L14.44 12 8.72 6.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018l6.25 6.25a.75.75 0 0 1 0 1.06l-6.25 6.25a.75.75 0 0 1-1.06 0Z"></path></svg></span></summary><div class="sd-summary-content sd-card-body docutils">
<div class="highlight-solidity notranslate"><div class="highlight"><pre id="codecell1"><span></span><span class="kt">import</span><span class="w"> </span><span class="p">{</span>IFlashLoanReceiver<span class="p">}</span><span class="w"> </span>from<span class="w"> </span><span class="s1">'./IFlashLoanReceiver.sol'</span><span class="p">;</span>
<span class="kt">import</span><span class="w"> </span><span class="p">{</span>ERC20<span class="p">}</span><span class="w"> </span>from<span class="w"> </span><span class="s1">'./ERC20.sol'</span><span class="p">;</span>
<span class="kt">import</span><span class="w"> </span><span class="p">{</span>IERC20<span class="p">}</span><span class="w"> </span>from<span class="w"> </span><span class="s1">'./IERC20.sol'</span><span class="p">;</span>
<span class="k">pragma solidity</span><span class="w"> </span><span class="o">&gt;=</span><span class="k">0.8.0</span><span class="p">;</span>


<span class="k">contract</span><span class="w"> </span><span class="ni">Pool</span><span class="w"> </span><span class="kt">is</span><span class="w"> </span>ERC20<span class="w"> </span><span class="p">{</span>

<span class="w">  </span><span class="kt">uint256</span><span class="w"> </span><span class="k">private </span><span class="nv">constant</span><span class="w"> </span>_NOT_ENTERED<span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="m m-Decimal">1</span><span class="p">;</span>
<span class="w">  </span><span class="kt">uint256</span><span class="w"> </span><span class="k">private </span><span class="nv">constant</span><span class="w"> </span>_ENTERED<span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="m m-Decimal">2</span><span class="p">;</span>

<span class="w">  </span><span class="kt">uint256</span><span class="w"> </span><span class="k">private </span><span class="nv">_status</span><span class="p">;</span>
<span class="w">  </span><span class="kt">modifier</span><span class="w"> </span>nonReentrant<span class="p">()</span><span class="w"> </span><span class="p">{</span>
<span class="w">        </span><span class="c1">// On the first call to nonReentrant, _notEntered will be true</span>
<span class="w">        </span><span class="kt">require</span><span class="p">(</span>_status<span class="w"> </span><span class="o">!=</span><span class="w"> </span>_ENTERED<span class="p">,</span><span class="w"> </span><span class="s2">"ReentrancyGuard: reentrant call"</span><span class="p">);</span>

<span class="w">        </span><span class="c1">// Any calls to nonReentrant after this point will fail</span>
<span class="w">        </span>_status<span class="w"> </span><span class="o">=</span><span class="w"> </span>_ENTERED<span class="p">;</span>

<span class="w">        </span>_<span class="p">;</span>

<span class="w">        </span><span class="c1">// By storing the original value once again, a refund is triggered (see</span>
<span class="w">        </span><span class="c1">// https://eips.ethereum.org/EIPS/eip-2200)</span>
<span class="w">        </span>_status<span class="w"> </span><span class="o">=</span><span class="w"> </span>_NOT_ENTERED<span class="p">;</span>
<span class="w">    </span><span class="p">}</span>

<span class="w">  </span>IERC20<span class="w"> </span><span class="kt">public</span><span class="w"> </span>asset<span class="p">;</span><span class="w">   </span>
<span class="w">  </span><span class="kt">uint256</span><span class="w"> </span><span class="k">private </span><span class="nv">constant</span><span class="w"> </span>feePrecision<span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="m m-Decimal">10000</span><span class="p">;</span><span class="w"> </span>
<span class="w">  </span><span class="c1">//feeRate is up to 1%, so less than 100 as it is divided by feePrecision</span>
<span class="w">  </span><span class="kt">uint256</span><span class="w"> </span><span class="k">public </span><span class="nv">feeRate</span><span class="p">;</span><span class="w"> </span>
<span class="w">  </span><span class="kt">uint256</span><span class="w"> </span><span class="k">public </span><span class="nv">depositedAmount</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">;</span>

<span class="w">  </span><span class="kt">function</span><span class="w"> </span><span class="nv">sharesToAmount</span><span class="p">(</span><span class="kt">uint256</span><span class="w"> </span><span class="nv">shares</span><span class="p">)</span><span class="w"> </span><span class="kt">public</span><span class="w"> </span>view<span class="w"> </span>virtual<span class="w"> </span><span class="kt">returns</span><span class="w"> </span><span class="p">(</span><span class="kt">uint256</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">     </span><span class="kt">return</span><span class="w"> </span>shares<span class="w"> </span><span class="o">*</span><span class="w"> </span>depositedAmount<span class="w"> </span><span class="o">/</span><span class="w"> </span>totalSupply<span class="p">();</span><span class="w">  </span>
<span class="w">  </span><span class="p">}</span>


<span class="w">  </span><span class="kt">function</span><span class="w"> </span><span class="nv">amountToShares</span><span class="p">(</span><span class="kt">uint256</span><span class="w"> </span><span class="nv">amount</span><span class="p">)</span><span class="w"> </span><span class="kt">public</span><span class="w"> </span>view<span class="w"> </span>virtual<span class="w"> </span><span class="kt">returns</span><span class="w"> </span><span class="p">(</span><span class="kt">uint256</span><span class="p">)</span><span class="w"> </span><span class="p">{</span><span class="w"> </span>
<span class="w">      </span><span class="kt">return</span><span class="w"> </span>amount<span class="w"> </span><span class="o">*</span><span class="w"> </span>totalSupply<span class="p">()</span><span class="w"> </span><span class="o">/</span><span class="w"> </span>depositedAmount<span class="p">;</span><span class="w">   </span>
<span class="w">  </span><span class="p">}</span>

<span class="w">  </span><span class="kt">function</span><span class="w"> </span><span class="nv">deposit</span><span class="p">(</span><span class="kt">uint256</span><span class="w"> </span><span class="nv">amount</span><span class="p">)</span><span class="w"> </span><span class="kt">public</span><span class="w"> </span>nonReentrant<span class="p">()</span><span class="w"> </span><span class="kt">returns</span><span class="p">(</span><span class="kt">uint256</span><span class="w"> </span><span class="nv">shares</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">      </span><span class="kt">if</span><span class="w"> </span><span class="p">(</span>totalSupply<span class="p">()</span><span class="o">==</span><span class="m m-Decimal">0</span><span class="w"> </span><span class="o">||</span><span class="w"> </span>depositedAmount<span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">){</span>
<span class="w">          </span>shares<span class="w"> </span><span class="o">=</span><span class="w"> </span>amount<span class="p">;</span>
<span class="w">      </span><span class="p">}</span>
<span class="w">      </span><span class="kt">else</span><span class="p">{</span>
<span class="w">        </span>shares<span class="w"> </span><span class="o">=</span><span class="w"> </span>amountToShares<span class="p">(</span>amount<span class="p">);</span>
<span class="w">        </span><span class="kt">require</span><span class="w"> </span><span class="p">(</span>shares<span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">);</span>
<span class="w">      </span><span class="p">}</span>
<span class="w">      </span>asset<span class="p">.</span>transferFrom<span class="p">(</span><span class="k">msg.sender</span><span class="p">,</span><span class="kt">address</span><span class="p">(</span><span class="kt">this</span><span class="p">),</span>amount<span class="p">);</span>
<span class="w">      </span>depositedAmount<span class="w"> </span><span class="o">=</span><span class="w"> </span>depositedAmount<span class="w"> </span><span class="o">+</span><span class="w"> </span>amount<span class="p">;</span>
<span class="w">      </span>_mint<span class="p">(</span><span class="k">msg.sender</span><span class="p">,</span>shares<span class="p">);</span>
<span class="w">    </span><span class="p">}</span>


<span class="w">  </span><span class="kt">function</span><span class="w"> </span><span class="nv">withdraw</span><span class="p">(</span><span class="kt">uint256</span><span class="w"> </span><span class="nv">shares</span><span class="p">)</span><span class="w"> </span><span class="kt">public</span><span class="w"> </span>nonReentrant<span class="p">()</span><span class="w"> </span><span class="kt">returns</span><span class="w"> </span><span class="p">(</span><span class="kt">uint256</span><span class="w"> </span><span class="nv">amountOut</span><span class="p">)</span><span class="w">  </span><span class="p">{</span>
<span class="w">    </span><span class="kt">uint256</span><span class="w"> </span><span class="nv">poolBalance</span><span class="w"> </span><span class="o">=</span><span class="w"> </span>asset<span class="p">.</span>balanceOf<span class="p">(</span><span class="kt">address</span><span class="p">(</span><span class="kt">this</span><span class="p">));</span>
<span class="w">    </span><span class="kt">require</span><span class="w"> </span><span class="p">(</span>poolBalance<span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">);</span>
<span class="w">    </span>amountOut<span class="w"> </span><span class="o">=</span><span class="w"> </span>sharesToAmount<span class="p">(</span>shares<span class="p">);</span>
<span class="w">    </span><span class="kt">require</span><span class="w"> </span><span class="p">(</span>amountOut<span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">);</span>
<span class="w">   	</span>_burn<span class="p">(</span><span class="k">msg.sender</span><span class="p">,</span>shares<span class="p">);</span>
<span class="w">		</span>asset<span class="p">.</span>transferFrom<span class="p">(</span><span class="kt">address</span><span class="p">(</span><span class="kt">this</span><span class="p">),</span><span class="k">msg.sender</span><span class="p">,</span>amountOut<span class="p">);</span>
<span class="w">    </span>depositedAmount<span class="w"> </span><span class="o">=</span><span class="w"> </span>depositedAmount<span class="w"> </span><span class="o">-</span><span class="w"> </span>amountOut<span class="p">;</span>
<span class="w">    </span><span class="p">}</span>

<span class="w">    </span>
<span class="w">  </span><span class="kt">function</span><span class="w"> </span><span class="nv">flashLoan</span><span class="p">(</span><span class="kt">address</span><span class="w"> </span><span class="nv">receiverAddress</span><span class="p">,</span><span class="w"> </span><span class="kt">uint256</span><span class="w"> </span><span class="nv">amount</span><span class="p">)</span><span class="w"> </span>nonReentrant<span class="p">()</span><span class="w"> </span><span class="kt">public</span><span class="w"> </span><span class="p">{</span><span class="w">          </span>
<span class="w">    </span><span class="kt">uint256</span><span class="w"> </span><span class="nv">totalPremium</span><span class="w"> </span><span class="o">=</span><span class="w"> </span>calcPremium<span class="p">(</span>amount<span class="p">);</span>
<span class="w">    </span><span class="kt">require</span><span class="w"> </span><span class="p">(</span>totalPremium<span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">);</span>
<span class="w">    </span><span class="kt">uint256</span><span class="w"> </span><span class="nv">amountPlusPremium</span><span class="w"> </span><span class="o">=</span><span class="w"> </span>amount<span class="w"> </span><span class="o">+</span><span class="w"> </span>totalPremium<span class="p">;</span>
<span class="w">    </span>asset<span class="p">.</span>transferFrom<span class="p">(</span><span class="kt">address</span><span class="p">(</span><span class="kt">this</span><span class="p">),</span><span class="k">msg.sender</span><span class="p">,</span>amount<span class="p">);</span>
<span class="w">    </span>depositedAmount<span class="w"> </span><span class="o">=</span><span class="w"> </span>depositedAmount<span class="w"> </span><span class="o">-</span><span class="w"> </span>amount<span class="p">;</span>
<span class="w">    </span><span class="kt">require</span><span class="p">(</span>IFlashLoanReceiver<span class="p">(</span>receiverAddress<span class="p">).</span>executeOperation<span class="p">(</span>amount<span class="p">,</span>totalPremium<span class="p">,</span><span class="k">msg.sender</span><span class="p">),</span><span class="s1">'P_INVALID_FLASH_LOAN_EXECUTOR_RETURN'</span><span class="p">);</span>
<span class="w">    </span>asset<span class="p">.</span>transferFrom<span class="p">(</span><span class="k">msg.sender</span><span class="p">,</span><span class="kt">address</span><span class="p">(</span><span class="kt">this</span><span class="p">),</span>amountPlusPremium<span class="p">);</span>
<span class="w">    </span>depositedAmount<span class="w"> </span><span class="o">=</span><span class="w"> </span>depositedAmount<span class="w"> </span><span class="o">+</span><span class="w"> </span>amountPlusPremium<span class="p">;</span>
<span class="w">  </span><span class="p">}</span>

<span class="w">  </span><span class="kt">function</span><span class="w"> </span><span class="nv">calcPremium</span><span class="p">(</span><span class="kt">uint256</span><span class="w"> </span><span class="nv">amount</span><span class="p">)</span><span class="w"> </span><span class="kt">public</span><span class="w"> </span>view<span class="w"> </span><span class="kt">returns</span><span class="w"> </span><span class="p">(</span><span class="kt">uint256</span><span class="p">){</span>
<span class="w">    </span><span class="kt">return</span><span class="w"> </span><span class="p">((</span>amount<span class="o">*</span>feeRate<span class="p">)</span><span class="o">/</span>feePrecision<span class="p">);</span>
<span class="w">  </span><span class="p">}</span>

<span class="w">  </span><span class="kt">function</span><span class="w"> </span><span class="nv">assetBalance</span><span class="p">()</span><span class="w"> </span><span class="kt">public</span><span class="w"> </span>view<span class="w"> </span><span class="kt">returns</span><span class="w"> </span><span class="p">(</span><span class="kt">uint256</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kt">return</span><span class="w"> </span>asset<span class="p">.</span>balanceOf<span class="p">(</span><span class="kt">address</span><span class="p">(</span><span class="kt">this</span><span class="p">));</span>
<span class="w">  </span><span class="p">}</span>
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
</details><p>For demonstration purposes, we have also added function <code class="docutils literal notranslate"><span class="pre">assetBalance</span></code>, which
returns the pool’s balance of the underlying asset (we’ll see
<a class="reference internal" href="#using-example"><span class="std std-ref">later</span></a> that this is not necessary):</p>
<div class="literal-block-wrapper docutils container" id="id11">
<div class="code-block-caption"><span class="caption-text"><a class="reference external" href="https://github.com/Certora/Examples/blob/7dfc379423202c90cf284eb42800b97cf5c95d83/DEFI/LiquidityPool/contracts/IPool.sol">assetBalance</a></span><a class="headerlink" href="#id11" title="Link to this code"></a></div>
<div class="highlight-solidity notranslate"><div class="highlight"><pre id="codecell2"><span></span><span class="w">  </span><span class="kt">function</span><span class="w"> </span><span class="nv">assetBalance</span><span class="p">()</span><span class="w"> </span><span class="kt">public</span><span class="w"> </span>view<span class="w"> </span><span class="kt">returns</span><span class="w"> </span><span class="p">(</span><span class="kt">uint256</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kt">return</span><span class="w"> </span>asset<span class="p">.</span>balanceOf<span class="p">(</span><span class="kt">address</span><span class="p">(</span><span class="kt">this</span><span class="p">));</span>
<span class="w">  </span><span class="p">}</span>
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
<p>Users can also take out <em>flash loans</em> - loans that must be repaid within the same
transaction.  To do so, the user calls <code class="docutils literal notranslate"><span class="pre">flashLoan</span></code>, passing in a
<code class="docutils literal notranslate"><span class="pre">FlashLoanReceiver</span></code> contract and the desired number of tokens.  The <code class="docutils literal notranslate"><span class="pre">flashLoan</span></code>
method transfers the tokens to the receiver, calls the <code class="docutils literal notranslate"><span class="pre">executeOperation</span></code>
method on the receiver, and finally transfers the tokens (plus a fee) from the
receiver back to the pool:</p>
<div class="literal-block-wrapper docutils container" id="id12">
<div class="code-block-caption"><span class="caption-text"><a class="reference external" href="https://github.com/Certora/Examples/blob/7dfc379423202c90cf284eb42800b97cf5c95d83/DEFI/LiquidityPool/contracts/IPool.sol">flashLoan</a></span><a class="headerlink" href="#id12" title="Link to this code"></a></div>
<div class="highlight-solidity notranslate"><div class="highlight"><pre id="codecell3"><span></span><span class="w">  </span><span class="kt">function</span><span class="w"> </span><span class="nv">flashLoan</span><span class="p">(</span><span class="kt">address</span><span class="w"> </span><span class="nv">receiverAddress</span><span class="p">,</span><span class="w"> </span><span class="kt">uint256</span><span class="w"> </span><span class="nv">amount</span><span class="p">)</span><span class="w"> </span>nonReentrant<span class="p">()</span><span class="w"> </span><span class="kt">public</span><span class="w"> </span><span class="p">{</span><span class="w">          </span>
<span class="w">    </span><span class="kt">uint256</span><span class="w"> </span><span class="nv">totalPremium</span><span class="w"> </span><span class="o">=</span><span class="w"> </span>calcPremium<span class="p">(</span>amount<span class="p">);</span>
<span class="w">    </span><span class="kt">require</span><span class="w"> </span><span class="p">(</span>totalPremium<span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">);</span>
<span class="w">    </span><span class="kt">uint256</span><span class="w"> </span><span class="nv">amountPlusPremium</span><span class="w"> </span><span class="o">=</span><span class="w"> </span>amount<span class="w"> </span><span class="o">+</span><span class="w"> </span>totalPremium<span class="p">;</span>
<span class="w">    </span>asset<span class="p">.</span>transferFrom<span class="p">(</span><span class="kt">address</span><span class="p">(</span><span class="kt">this</span><span class="p">),</span><span class="k">msg.sender</span><span class="p">,</span>amount<span class="p">);</span>
<span class="w">    </span>depositedAmount<span class="w"> </span><span class="o">=</span><span class="w"> </span>depositedAmount<span class="w"> </span><span class="o">-</span><span class="w"> </span>amount<span class="p">;</span>
<span class="w">    </span><span class="kt">require</span><span class="p">(</span>IFlashLoanReceiver<span class="p">(</span>receiverAddress<span class="p">).</span>executeOperation<span class="p">(</span>amount<span class="p">,</span>totalPremium<span class="p">,</span><span class="k">msg.sender</span><span class="p">),</span><span class="s1">'P_INVALID_FLASH_LOAN_EXECUTOR_RETURN'</span><span class="p">);</span>
<span class="w">    </span>asset<span class="p">.</span>transferFrom<span class="p">(</span><span class="k">msg.sender</span><span class="p">,</span><span class="kt">address</span><span class="p">(</span><span class="kt">this</span><span class="p">),</span>amountPlusPremium<span class="p">);</span>
<span class="w">    </span>depositedAmount<span class="w"> </span><span class="o">=</span><span class="w"> </span>depositedAmount<span class="w"> </span><span class="o">+</span><span class="w"> </span>amountPlusPremium<span class="p">;</span>
<span class="w">  </span><span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell3">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</div>
<p>Our goal is to prove properties about the <code class="docutils literal notranslate"><span class="pre">Pool</span></code> contract, but we will need to
interact with the entire combined protocol consisting of the <code class="docutils literal notranslate"><span class="pre">Pool</span></code> contract,
the <code class="docutils literal notranslate"><span class="pre">Asset</span></code> contract, and the <code class="docutils literal notranslate"><span class="pre">FlashLoanReceiver</span></code> contracts.  We will begin by
explaining the default behavior of the Prover when making external calls to
unknown contracts.  We will then show how to link the specific <code class="docutils literal notranslate"><span class="pre">Asset</span></code> contract
implementation to the <code class="docutils literal notranslate"><span class="pre">Pool</span></code> contract. Finally, we will show some techniques
for reasoning about the open-ended set of possible <code class="docutils literal notranslate"><span class="pre">FlashLoanReceiver</span></code>
implementations.</p>
</section>
<section id="handling-unresolved-method-calls">
<h2><a class="toc-backref" href="#id23" role="doc-backlink">Handling unresolved method calls</a><a class="headerlink" href="#handling-unresolved-method-calls" title="Link to this heading"></a></h2>
<p>To start, let’s write a basic property of the pool and run the Prover on the
<code class="docutils literal notranslate"><span class="pre">Pool</span></code> contract to see how it handles calls to unknown code.</p>
<p>Here is a simple property:</p>
<div class="literal-block-wrapper docutils container" id="id13">
<div class="code-block-caption"><span class="caption-text"><a class="reference external" href="https://github.com/Certora/Examples/blob/7dfc379423202c90cf284eb42800b97cf5c95d83/DEFI/LiquidityPool/certora/specs/pool_havoc.spec">integrityOfDeposit</a></span><a class="headerlink" href="#id13" title="Link to this code"></a></div>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell4"><span></span><span class="c1">/// `deposit` must increase the pool's underlying asset balance</span>
<span class="k">rule</span><span class="w"> </span><span class="nc">integrityOfDeposit</span><span class="w"> </span><span class="p">{</span>

<span class="w">    </span><span class="kt">mathint</span><span class="w"> </span>balance_before<span class="w"> </span><span class="o">=</span><span class="w"> </span>assetBalance<span class="p">();</span>

<span class="w">    </span><span class="kt">env</span><span class="w"> </span>e<span class="p">;</span><span class="w"> </span><span class="kt">uint256</span><span class="w"> </span>amount<span class="p">;</span>
<span class="w">    </span><span class="kr">require</span><span class="w"> </span>e<span class="p">.</span><span class="kc">msg.sender</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="nb">currentContract</span><span class="p">;</span>

<span class="w">    </span>deposit<span class="p">(</span>e<span class="p">,</span><span class="w"> </span>amount<span class="p">);</span>

<span class="w">    </span><span class="kt">mathint</span><span class="w"> </span>balance_after<span class="w"> </span><span class="o">=</span><span class="w"> </span>assetBalance<span class="p">();</span>

<span class="w">    </span><span class="kr">assert</span><span class="w"> </span>balance_after<span class="w"> </span><span class="o">==</span><span class="w"> </span>balance_before<span class="w"> </span><span class="o">+</span><span class="w"> </span>amount<span class="p">,</span>
<span class="w">        </span><span class="s2">"deposit must increase the underlying balance of the pool"</span><span class="p">;</span>
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
</div>
<p>This rule makes a call to <code class="docutils literal notranslate"><span class="pre">Pool.deposit(...)</span></code>, which in turn makes a call to
<code class="docutils literal notranslate"><span class="pre">asset.transferFrom(...)</span></code>; to understand the behavior of <code class="docutils literal notranslate"><span class="pre">deposit</span></code> the Prover
must also reason about the <code class="docutils literal notranslate"><span class="pre">Asset</span></code> contract.  If we verify the rule without
giving the Prover access to the <code class="docutils literal notranslate"><span class="pre">Asset</span></code> code, the call to <code class="docutils literal notranslate"><span class="pre">transferFrom(...)</span></code>
will be unresolved.</p>
<p>By default, the Prover will handle calls to unresolved functions by assuming
they can do almost anything — we say that the Prover “<a class="reference internal" href="../glossary.html#term-havoc"><span class="xref std std-term">havocs</span></a>”
some part of the state.  The part of the state that is havoced depends on the
type of call: calls to view functions are allowed to return any value but can
not affect storage (a <code class="docutils literal notranslate"><span class="pre">NONDET</span></code> summary), while calls to non-view functions are
allowed to change the storage of all contracts in the system <em>besides the
calling contract</em><a class="footnote-reference brackets" href="#reentrancy" id="id1" role="doc-noteref"><span class="fn-bracket">[</span>1<span class="fn-bracket">]</span></a> (a <code class="docutils literal notranslate"><span class="pre">HAVOC_ECF</span></code> summary).  See
<a class="reference internal" href="../../cvl/methods.html#auto-summary"><span class="std std-ref">AUTO summaries</span></a> in the reference manual for complete details.</p>
<p>We can see this behavior by verifying the <code class="docutils literal notranslate"><span class="pre">integrityOfDeposit</span></code> rule against the
<code class="docutils literal notranslate"><span class="pre">Pool</span></code> contract without giving the Prover access to the <code class="docutils literal notranslate"><span class="pre">Asset</span></code> contract.
The <a class="reference external" href="https://github.com/Certora/Examples/blob/7dfc379423202c90cf284eb42800b97cf5c95d83/DEFI/LiquidityPool/JustPool.conf">JustPool.conf</a> config file does
just that, run it using:</p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell5"><span></span>$<span class="w"> </span>certoraRun<span class="w"> </span>JustPool.conf
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell5">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>In this case, the <code class="docutils literal notranslate"><span class="pre">integrityOfDeposit</span></code> rule fails.  To understand why, we can
unfold the call trace for the call to <code class="docutils literal notranslate"><span class="pre">deposit</span></code>:</p>
<p><img alt="Call trace for  with  method unfolded to show DEFAULT HAVOCs for calls to  and " src="../../../_images/no-link-call-trace.png" width="785" height="760"></p>
<p>Here we see that the calls to <code class="docutils literal notranslate"><span class="pre">transferFrom</span></code> and <code class="docutils literal notranslate"><span class="pre">balanceOf</span></code> are marked with
“DEFAULT HAVOC”.  This means that the Prover lets the call to
<code class="docutils literal notranslate"><span class="pre">transferFrom</span></code> to change the balances any way it likes.  In fact, calls to
<code class="docutils literal notranslate"><span class="pre">asset.balanceOf(...)</span></code> are also unresolved, so the Prover can choose any return
value that causes a counterexample.  In this case, we can see that the Prover
chose <code class="docutils literal notranslate"><span class="pre">3</span></code> for the first return value of <code class="docutils literal notranslate"><span class="pre">balanceOf</span></code> and <code class="docutils literal notranslate"><span class="pre">9</span></code>
for the last return value of <code class="docutils literal notranslate"><span class="pre">balanceOf</span></code>:</p>
<p><img alt="Call trace for  on  showing call to  with internal havoced call to , returning 3 in once place and 9 in another" src="../../../_images/no-link-variables.png"></p>
<p>The “Call Resolution” tab on the report provides more information about all of
the unlinked external method calls within the contract and how they are
resolved by the Prover<a class="footnote-reference brackets" href="#resolutionwarnings" id="id2" role="doc-noteref"><span class="fn-bracket">[</span>2<span class="fn-bracket">]</span></a>:</p>
<p><img alt="Call resolution for  showing havocs of return values for  and all variables of external contracts for " src="../../../_images/no-link-call-resolution.png"></p>
<p>Here we see that the call from <code class="docutils literal notranslate"><span class="pre">Pool.deposit</span></code> to <code class="docutils literal notranslate"><span class="pre">balanceOf</span></code> is summarized by
havocing only the return value (since <code class="docutils literal notranslate"><span class="pre">balanceOf</span></code> is a view method), while the
call from <code class="docutils literal notranslate"><span class="pre">Pool.deposit</span></code> to <code class="docutils literal notranslate"><span class="pre">transferFrom</span></code> havocs all contracts except <code class="docutils literal notranslate"><span class="pre">Pool</span></code>.</p>
</section>
<section id="working-with-known-contracts">
<h2><a class="toc-backref" href="#id24" role="doc-backlink">Working with known contracts</a><a class="headerlink" href="#working-with-known-contracts" title="Link to this heading"></a></h2>
<p>In the case of the <code class="docutils literal notranslate"><span class="pre">Pool</span></code> verification, we don’t want the Prover to choose
arbitrary behavior for the <code class="docutils literal notranslate"><span class="pre">Asset</span></code>, because we have the <code class="docutils literal notranslate"><span class="pre">Asset</span></code> code.  Instead,
we would like the Prover to model the <code class="docutils literal notranslate"><span class="pre">asset</span></code> contract using the <code class="docutils literal notranslate"><span class="pre">Asset</span></code> code.</p>
<p>To do so, we must first add the <code class="docutils literal notranslate"><span class="pre">Asset</span></code> contract to the set of contracts that
the Prover knows about.  This set of contracts is called the <a class="reference internal" href="../glossary.html#term-0"><span class="xref std std-term">scene</span></a>.  You
can add a contract to the scene by passing the solidity source as a
<a class="reference internal" href="../../prover/cli/options.html"><span class="std std-doc">command line argument</span></a>
to <code class="docutils literal notranslate"><span class="pre">certoraRun</span></code>.  The Prover creates a contract instance (with a corresponding
address<a class="footnote-reference brackets" href="#addressoption" id="id3" role="doc-noteref"><span class="fn-bracket">[</span>3<span class="fn-bracket">]</span></a>) in the scene for each source contract provided on the command
line (or the config file).</p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell6"><span></span>$<span class="w"> </span>certoraRun<span class="w"> </span>contracts/Pool.sol<span class="w"> </span>contracts/Asset.sol<span class="w"> </span>--verify<span class="w"> </span>Pool:certora/specs/pool_havoc.spec<span class="w"> </span>...
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell6">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>Adding <code class="docutils literal notranslate"><span class="pre">Asset.sol</span></code> to the scene makes the Prover aware of it, but it does not
connect the <code class="docutils literal notranslate"><span class="pre">asset</span></code> field of the pool to the <code class="docutils literal notranslate"><span class="pre">Asset</span></code> contract.  Although
<code class="docutils literal notranslate"><span class="pre">Pool.asset</span></code> is declared to have type <code class="docutils literal notranslate"><span class="pre">Asset</span></code> in the solidity source, the
solidity compiler erases that information from the bytecode; in the compiled
bytecode the field is just treated as an <code class="docutils literal notranslate"><span class="pre">address</span></code>, and at run time the field
could point to any contract.</p>
<p>To connect the <code class="docutils literal notranslate"><span class="pre">Asset</span></code> code to the <code class="docutils literal notranslate"><span class="pre">Pool.asset</span></code> field, we can use the
<a class="reference internal" href="../../prover/cli/options.html#link"><span class="std std-ref">link</span></a> option:</p>
<div class="literal-block-wrapper docutils container" id="id14">
<div class="code-block-caption"><span class="caption-text"><a class="reference external" href="https://github.com/Certora/Examples/blob/7dfc379423202c90cf284eb42800b97cf5c95d83/DEFI/LiquidityPool/WithLinking.conf">WithLinking.conf</a></span><a class="headerlink" href="#id14" title="Link to this code"></a></div>
<div class="highlight-json notranslate"><div class="highlight"><pre id="codecell7"><span></span><span class="p">{</span>
<span class="w">  </span><span class="nt">"files"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span>
<span class="w">    </span><span class="s2">"contracts/Pool.sol"</span><span class="p">,</span>
<span class="w">    </span><span class="s2">"contracts/Asset.sol"</span>
<span class="w">  </span><span class="p">],</span>
<span class="w">  </span><span class="nt">"verify"</span><span class="p">:</span><span class="w"> </span><span class="s2">"Pool:certora/specs/pool_link.spec"</span><span class="p">,</span>
<span class="w">  </span><span class="nt">"msg"</span><span class="p">:</span><span class="w"> </span><span class="s2">"Pool with linking"</span><span class="p">,</span>
<span class="hll"><span class="w">  </span><span class="nt">"link"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span>
</span><span class="hll"><span class="w">        </span><span class="s2">"Pool:asset=Asset"</span>
</span><span class="hll"><span class="w">    </span><span class="p">],</span>
</span><span class="w">  </span><span class="nt">"rule_sanity"</span><span class="p">:</span><span class="w"> </span><span class="s2">"basic"</span>
<span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell7">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</div>
<p>The <code class="docutils literal notranslate"><span class="pre">--link</span> <span class="pre">Pool:asset=Asset</span></code> option tells the Prover to assume that the <code class="docutils literal notranslate"><span class="pre">asset</span></code>
field of the <code class="docutils literal notranslate"><span class="pre">Pool</span></code> contract instance in the scene is a pointer to the <code class="docutils literal notranslate"><span class="pre">Asset</span></code>
contract instance in the scene.  With this information, the Prover is able to
resolve the calls to the methods on <code class="docutils literal notranslate"><span class="pre">Pool.asset</span></code> using the code in <code class="docutils literal notranslate"><span class="pre">Asset.sol</span></code>.</p>
<p>With this option, the Prover is no longer able to construct a counterexample to
the <code class="docutils literal notranslate"><span class="pre">integrityOfDeposit</span></code> rule, so the rule passes. Note that the external calls
to the <code class="docutils literal notranslate"><span class="pre">Asset</span></code> contract no longer appear in the “Call Resolution” tab, because
the Prover does not report linked calls here.</p>
<section id="accessing-additional-contracts-from-cvl">
<span id="using-example"></span><h3><a class="toc-backref" href="#id25" role="doc-backlink">Accessing additional contracts from CVL</a><a class="headerlink" href="#accessing-additional-contracts-from-cvl" title="Link to this heading"></a></h3>
<p>When a contract instance is added to the scene, it is also possible to call
methods on that contract directly from CVL.  To do so, you need to introduce
a variable name for the contract instance using
<a class="reference internal" href="../../cvl/using.html#using-stmt"><span class="std std-ref">the using statement</span></a>.  In our running example, we can create
a variable <code class="docutils literal notranslate"><span class="pre">underlying</span></code> to refer to the <code class="docutils literal notranslate"><span class="pre">Asset</span></code> contract instance<a class="footnote-reference brackets" href="#using-position" id="id4" role="doc-noteref"><span class="fn-bracket">[</span>4<span class="fn-bracket">]</span></a>.</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell8"><span></span><span class="kn">using</span><span class="w"> </span>Asset<span class="w"> </span><span class="kn">as</span><span class="w"> </span>underlying<span class="p">;</span>
<span class="kn">using</span><span class="w"> </span>Pool<span class="w"> </span><span class="kn">as</span><span class="w"> </span>pool<span class="p">;</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell8">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>We can then call methods on the contract <code class="docutils literal notranslate"><span class="pre">underlying</span></code>.  For example, instead of
adding a special method <code class="docutils literal notranslate"><span class="pre">assetBalance</span></code> to the <code class="docutils literal notranslate"><span class="pre">Pool</span></code> contract to call
<code class="docutils literal notranslate"><span class="pre">asset.balanceOf</span></code> for us, we can call it directly from the spec:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell9"><span></span><span class="c1">/// `deposit` must increase the pool's underlying asset balance</span>
<span class="k">rule</span><span class="w"> </span><span class="nc">integrityOfDeposit</span><span class="w"> </span><span class="p">{</span>

<span class="w">    </span><span class="kt">env</span><span class="w"> </span>e1<span class="p">;</span>
<span class="w">    </span><span class="kt">mathint</span><span class="w"> </span>balance_before<span class="w"> </span><span class="o">=</span><span class="w"> </span>underlying<span class="p">.</span>balanceOf<span class="p">(</span>e1<span class="p">,</span><span class="w"> </span>pool<span class="p">);</span>

<span class="w">    </span><span class="kt">env</span><span class="w"> </span>e<span class="p">;</span><span class="w"> </span><span class="kt">uint256</span><span class="w"> </span>amount<span class="p">;</span>
<span class="w">    </span><span class="kr">require</span><span class="w"> </span>e<span class="p">.</span><span class="kc">msg.sender</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span>pool<span class="p">;</span>
<span class="w">   </span>
<span class="w">    </span>deposit<span class="p">(</span>e<span class="p">,</span><span class="w"> </span>amount<span class="p">);</span>

<span class="w">    </span><span class="kt">env</span><span class="w"> </span>e2<span class="p">;</span>
<span class="w">    </span><span class="kt">mathint</span><span class="w"> </span>balance_after<span class="w"> </span><span class="o">=</span><span class="w"> </span>underlying<span class="p">.</span>balanceOf<span class="p">(</span>e2<span class="p">,</span><span class="w"> </span>pool<span class="p">);</span>

<span class="w">    </span><span class="kr">assert</span><span class="w"> </span>balance_after<span class="w"> </span><span class="o">==</span><span class="w"> </span>balance_before<span class="w"> </span><span class="o">+</span><span class="w"> </span>amount<span class="p">,</span>
<span class="w">        </span><span class="s2">"deposit must increase the underlying balance of the pool"</span><span class="p">;</span>
<span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell9">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>We can simplify this rule in two ways. First, we can declare the
<code class="docutils literal notranslate"><span class="pre">underlying.balanceOf</span></code> method <code class="docutils literal notranslate"><span class="pre">envfree</span></code> to avoid explicitly passing in <code class="docutils literal notranslate"><span class="pre">env</span></code>
variables. This works the same way as <code class="docutils literal notranslate"><span class="pre">envfree</span></code> <a class="reference internal" href="../../cvl/methods.html#envfree"><span class="std std-ref">declarations for the main contract</span></a>, except that you must indicate that the method is for
the <code class="docutils literal notranslate"><span class="pre">underlying</span></code> contract instance <a class="footnote-reference brackets" href="#wildcards" id="id5" role="doc-noteref"><span class="fn-bracket">[</span>5<span class="fn-bracket">]</span></a>:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell10"><span></span><span class="w">    </span><span class="kt">function</span><span class="w"> </span><span class="nf">underlying</span><span class="p">.</span>balanceOf<span class="p">(</span><span class="kt">address</span><span class="p">)</span><span class="w">           </span><span class="kr">external</span><span class="w"> </span><span class="kr">returns</span><span class="p">(</span><span class="kt">uint256</span><span class="p">)</span><span class="w"> </span><span class="kr">envfree</span><span class="p">;</span>
<span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell10">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>The second simplification is that we can use the special variable
<code class="docutils literal notranslate"><span class="pre">currentContract</span></code> to refer to the main contract being verified (the one passed
to <a class="reference internal" href="../../prover/cli/options.html#verify"><span class="std std-ref">verify</span></a>), so we don’t need to add the <code class="docutils literal notranslate"><span class="pre">using</span></code> statement for <code class="docutils literal notranslate"><span class="pre">Pool</span></code>.
With these changes, the rule looks as follows:</p>
<div class="literal-block-wrapper docutils container" id="id15">
<div class="code-block-caption"><span class="caption-text"><a class="reference external" href="https://github.com/Certora/Examples/blob/7dfc379423202c90cf284eb42800b97cf5c95d83/DEFI/LiquidityPool/certora/specs/pool_link.spec">integrityOfDeposit from pool_link.spec</a></span><a class="headerlink" href="#id15" title="Link to this code"></a></div>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell11"><span></span><span class="c1">/// `deposit` must increase the pool's underlying asset balance</span>
<span class="k">rule</span><span class="w"> </span><span class="nc">integrityOfDeposit</span><span class="w"> </span><span class="p">{</span>

<span class="w">    </span><span class="kt">mathint</span><span class="w"> </span>balance_before<span class="w"> </span><span class="o">=</span><span class="w"> </span>underlying<span class="p">.</span>balanceOf<span class="p">(</span><span class="nb">currentContract</span><span class="p">);</span>

<span class="w">    </span><span class="kt">env</span><span class="w"> </span>e<span class="p">;</span><span class="w"> </span><span class="kt">uint256</span><span class="w"> </span>amount<span class="p">;</span>
<span class="w">    </span><span class="kr">require</span><span class="w"> </span>e<span class="p">.</span><span class="kc">msg.sender</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="nb">currentContract</span><span class="p">;</span>

<span class="w">    </span>deposit<span class="p">(</span>e<span class="p">,</span><span class="w"> </span>amount<span class="p">);</span>

<span class="w">    </span><span class="kt">mathint</span><span class="w"> </span>balance_after<span class="w"> </span><span class="o">=</span><span class="w"> </span>underlying<span class="p">.</span>balanceOf<span class="p">(</span><span class="nb">currentContract</span><span class="p">);</span>

<span class="w">    </span><span class="kr">assert</span><span class="w"> </span>balance_after<span class="w"> </span><span class="o">==</span><span class="w"> </span>balance_before<span class="w"> </span><span class="o">+</span><span class="w"> </span>amount<span class="p">,</span>
<span class="w">        </span><span class="s2">"deposit must increase the underlying balance of the pool"</span><span class="p">;</span>
<span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell11">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</div>
<p>You can run this rule using the
<a class="reference external" href="https://github.com/Certora/Examples/blob/7dfc379423202c90cf284eb42800b97cf5c95d83/DEFI/LiquidityPool/WithLinking.conf">WithLinking.conf</a> config file.</p>
</section>
</section>
<section id="working-with-unknown-contracts">
<span id="unknown-contracts"></span><h2><a class="toc-backref" href="#id26" role="doc-backlink">Working with unknown contracts</a><a class="headerlink" href="#working-with-unknown-contracts" title="Link to this heading"></a></h2>
<p>Linking is appropriate for situations when we know the specific contracts that
a field points to.  In many cases, however, we <em>don’t</em> know what contract an
address refers to.  For example:</p>
<ul class="simple">
<li><p>A contract may call a method on a contract address passed in by the user.  In
our running example, the user may provide any <code class="docutils literal notranslate"><span class="pre">FlashLoanReceiver</span></code>
implementation they want to.</p></li>
<li><p>A contract may be designed to work with many instances of the same interface.
For example, a pool might be designed to work with arbitrary ERC20
implementations.</p></li>
</ul>
<p>In this case, the only option is to <a class="reference internal" href="../glossary.html#term-summarize"><span class="xref std std-term">summarize</span></a> the unknown code for the
Prover.  Although there are many available types of summaries, the ones most
commonly used for unknown code are <a class="reference internal" href="../../cvl/methods.html#dispatcher"><span class="std std-ref">DISPATCHER summaries</span></a>.</p>
<p>The <code class="docutils literal notranslate"><span class="pre">DISPATCHER</span></code> summary resolves calls by assuming that the receiver address
is one of the contracts in the scene that implements the called method.  It
will try every option, and if any of them can cause a violation, it will
report a counterexample.</p>
<div class="admonition warning">
<p class="admonition-title">Warning</p>
<p>The <code class="docutils literal notranslate"><span class="pre">DISPATCHER</span></code> summary is <a class="reference internal" href="../glossary.html#term-unsound"><span class="xref std std-term">unsound</span></a>, meaning that using it can cause you
to hide bugs in your contracts.  Therefore, you should make sure you understand
the risks before using them.  See <a class="reference internal" href="#dispatcher-danger"><span class="std std-ref">The dangers of DISPATCHER</span></a> below.</p>
</div>
<p>To demonstrate the <code class="docutils literal notranslate"><span class="pre">DISPATCHER</span></code> summary, let us prove a basic property about
flash loans.  For example, we might like to show that flash loans can only
increase the underlying balance of the pool.  We can write the property as
follows:</p>
<div class="literal-block-wrapper docutils container" id="id16">
<div class="code-block-caption"><span class="caption-text"><a class="reference external" href="https://github.com/Certora/Examples/blob/7dfc379423202c90cf284eb42800b97cf5c95d83/DEFI/LiquidityPool/certora/specs/flashLoan_dispatcher.spec">flashLoanIncreasesBalance</a></span><a class="headerlink" href="#id16" title="Link to this code"></a></div>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell12"><span></span><span class="c1">/// flash loans must increase the pool's underlying asset balance, assuming the</span>
<span class="c1">/// receiver has no pool balance.</span>
<span class="k">rule</span><span class="w"> </span><span class="nc">flashLoanIncreasesBalance</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kt">address</span><span class="w"> </span>receiver<span class="p">;</span><span class="w"> </span><span class="kt">uint256</span><span class="w"> </span>amount<span class="p">;</span><span class="w"> </span><span class="kt">env</span><span class="w"> </span>e<span class="p">;</span>

<span class="w">    </span><span class="kr">require</span><span class="w"> </span>e<span class="p">.</span><span class="kc">msg.sender</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="nb">currentContract</span><span class="p">;</span>

<span class="w">    </span><span class="kt">mathint</span><span class="w"> </span>balance_before<span class="w"> </span><span class="o">=</span><span class="w"> </span>underlying<span class="p">.</span>balanceOf<span class="p">(</span><span class="nb">currentContract</span><span class="p">);</span>

<span class="w">    </span>flashLoan<span class="p">(</span>e<span class="p">,</span><span class="w"> </span>receiver<span class="p">,</span><span class="w"> </span>amount<span class="p">);</span>

<span class="w">    </span><span class="kt">mathint</span><span class="w"> </span>balance_after<span class="w"> </span><span class="o">=</span><span class="w"> </span>underlying<span class="p">.</span>balanceOf<span class="p">(</span><span class="nb">currentContract</span><span class="p">);</span>

<span class="w">    </span><span class="kr">assert</span><span class="w"> </span>balance_after<span class="w"> </span><span class="o">&gt;=</span><span class="w"> </span>balance_before<span class="p">,</span>
<span class="w">        </span><span class="s2">"flash loans must not decrease the contract's underlying balance"</span><span class="p">;</span>
<span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell12">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</div>
<p>Verifying this rule without any summarization will fail, for the same reasons
that the first run of <code class="docutils literal notranslate"><span class="pre">integrityOfDeposit</span></code> above failed:  the <code class="docutils literal notranslate"><span class="pre">flashLoan</span></code>
method calls <code class="docutils literal notranslate"><span class="pre">executeOperation</span></code> on an unknown contract, and the Prover
constructs a counterexample where <code class="docutils literal notranslate"><span class="pre">executeOperation</span></code> changes the underlying
balance.  This is possible because the default <code class="docutils literal notranslate"><span class="pre">HAVOC_ECF</span></code> summary allows
<code class="docutils literal notranslate"><span class="pre">executeOperation</span></code> to do anything to the <code class="docutils literal notranslate"><span class="pre">underlying</span></code> contract.</p>
<p>To use a <code class="docutils literal notranslate"><span class="pre">DISPATCHER</span></code> summary for the <code class="docutils literal notranslate"><span class="pre">executeOperation</span></code> method, we add it to
the <code class="docutils literal notranslate"><span class="pre">methods</span></code> block<a class="footnote-reference brackets" href="#optimistic-dispatcher" id="id6" role="doc-noteref"><span class="fn-bracket">[</span>6<span class="fn-bracket">]</span></a>:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell13"><span></span><span class="kr">methods</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kd">function</span><span class="w"> </span><span class="nc">_</span><span class="p">.</span><span class="nf">executeOperation</span><span class="p">(</span><span class="kt">uint256</span><span class="p">,</span><span class="kt">uint256</span><span class="p">,</span><span class="kt">address</span><span class="p">)</span><span class="w"> </span><span class="kr">external</span><span class="w"> </span><span class="kp">=&gt;</span><span class="w"> </span><span class="kc">DISPATCHER</span><span class="p">(</span>true<span class="p">);</span>
<span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell13">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>This summary means that when the Prover encounters an external call to
<code class="docutils literal notranslate"><span class="pre">receiver.executeOperation(...)</span></code>, it will try to construct counterexamples
where the <code class="docutils literal notranslate"><span class="pre">receiver</span></code> contract is any of the contracts in the scene that
implement the <code class="docutils literal notranslate"><span class="pre">executeOperation</span></code> method.  We use the wildcard <code class="docutils literal notranslate"><span class="pre">_</span></code> as the
receiver contract so that the summary will apply regardless of the receiver
contract.</p>
<p>So far, there are no contracts in the scene that implement the
<code class="docutils literal notranslate"><span class="pre">executeOperation</span></code> method, so the Prover will conservatively use a havoc
summary for the call, and the rule will still fail.  To make use of the
dispatcher summary, we need to add a contract to the scene that implements the
method.</p>
<p>Let’s start by adding a trivial receiver
(in <a class="reference external" href="https://github.com/Certora/Examples/blob/7dfc379423202c90cf284eb42800b97cf5c95d83/DEFI/LiquidityPool/certora/harness/TrivialReceiver.sol">TrivialReceiver.sol</a>)
that implements <code class="docutils literal notranslate"><span class="pre">executeOperation</span></code> but does nothing:</p>
<div class="literal-block-wrapper docutils container" id="id17">
<div class="code-block-caption"><span class="caption-text"><a class="reference external" href="https://github.com/Certora/Examples/blob/7dfc379423202c90cf284eb42800b97cf5c95d83/DEFI/LiquidityPool/certora/harness/TrivialReceiver.sol">TrivialReceiver.sol</a></span><a class="headerlink" href="#id17" title="Link to this code"></a></div>
<div class="highlight-solidity notranslate"><div class="highlight"><pre id="codecell14"><span></span><span class="k">contract</span><span class="w"> </span><span class="ni">TrivialReceiver</span><span class="w"> </span><span class="kt">is</span><span class="w"> </span>IFlashLoanReceiver<span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kt">function</span><span class="w"> </span><span class="nv">executeOperation</span><span class="p">(</span>
<span class="w">        </span><span class="kt">uint256</span><span class="w"> </span><span class="nv">amount</span><span class="p">,</span>
<span class="w">        </span><span class="kt">uint256</span><span class="w"> </span><span class="nv">premium</span><span class="p">,</span>
<span class="w">        </span><span class="kt">address</span><span class="w"> </span><span class="nv">initiator</span>
<span class="w">    </span><span class="p">)</span><span class="w"> </span><span class="kt">external</span><span class="w"> </span>override<span class="p">(</span>IFlashLoanReceiver<span class="p">)</span><span class="w"> </span><span class="kt">returns</span><span class="w"> </span><span class="p">(</span><span class="kt">bool</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">        </span><span class="c1">// do nothing</span>
<span class="w">        </span><span class="kt">return</span><span class="w"> </span><span class="kt">true</span><span class="p">;</span>
<span class="w">    </span><span class="p">}</span>
<span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell14">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</div>
<p>Adding <code class="docutils literal notranslate"><span class="pre">TrivialReceiver.sol</span></code> to the scene allows the Prover to dispatch to it.
To run, use the <a class="reference external" href="https://github.com/Certora/Examples/blob/7dfc379423202c90cf284eb42800b97cf5c95d83/DEFI/LiquidityPool/FlashLoanTrivial.conf">FlashLoanTrivial.conf</a>
config file.</p>
<p>With this dispatcher in place, the rule passes. Examining the call resolution
tab shows that the Prover used the dispatcher summary for <code class="docutils literal notranslate"><span class="pre">executeOperation</span></code>
and considered only <code class="docutils literal notranslate"><span class="pre">TrivialReceiver.executeOperation</span></code> as a possible
implementation:</p>
<p><img alt="Call resolution tab showing  summarized with a Dispatcher.The &quot;alternatives&quot; list contains " src="../../../_images/trivial-resolution.png"></p>
<p>Although the rule passes, it is important to pause and think about what we have
proved; the next section shows that we shouldn’t rest easy yet.</p>
<section id="the-dangers-of-dispatcher">
<span id="dispatcher-danger"></span><h3><a class="toc-backref" href="#id27" role="doc-backlink">The dangers of <code class="docutils literal notranslate"><span class="pre">DISPATCHER</span></code></a><a class="headerlink" href="#the-dangers-of-dispatcher" title="Link to this heading"></a></h3>
<p>What we have proved so far is that <em>if</em> the only possible <code class="docutils literal notranslate"><span class="pre">FlashLoanReceiver</span></code>
is <code class="docutils literal notranslate"><span class="pre">TrivialReceiver</span></code>, <em>then</em> the pool’s underlying balance doesn’t decrease.
However, we have not proved that the underlying balance <em>never</em> decreases after
a flash loan.</p>
<p>Since the <code class="docutils literal notranslate"><span class="pre">DISPATCHER</span></code> summary only considers the contracts you provide as
possible implementations, it forces you to think about a threat model: the set
of behaviors that you want to protect against.  If there is a clever way to
construct a receiver contract that violates the rule, but you don’t think of
it, the Prover won’t be able to find it.  So far, we were able to prove the
rule, but only with a very weak threat model: we assume that the flash loan
receiver does nothing.</p>
<p>In fact, we can easily construct a flash loan receiver that decreases the
pool’s underlying balance.  For example, if the receiver somehow got an
approval to transfer underlying tokens away from the pool, it could just
transfer them, thereby decreasing the underlying balance of the pool.
We can write such a receiver:</p>
<div class="literal-block-wrapper docutils container" id="id18">
<div class="code-block-caption"><span class="caption-text"><a class="reference external" href="https://github.com/Certora/Examples/blob/7dfc379423202c90cf284eb42800b97cf5c95d83/DEFI/LiquidityPool/certora/harness/TransferReceiver.sol">TransferReceiver.sol</a></span><a class="headerlink" href="#id18" title="Link to this code"></a></div>
<div class="highlight-solidity notranslate"><div class="highlight"><pre id="codecell15"><span></span><span class="k">contract</span><span class="w"> </span><span class="ni">TransferReceiver</span><span class="w"> </span><span class="kt">is</span><span class="w"> </span>IFlashLoanReceiver<span class="w"> </span><span class="p">{</span>
<span class="w">    </span>IERC20<span class="w">  </span>underlying<span class="p">;</span>
<span class="w">    </span><span class="kt">uint</span><span class="w">    </span><span class="nv">transfer_amount</span><span class="p">;</span>
<span class="w">    </span><span class="kt">address</span><span class="w"> </span><span class="nv">pool</span><span class="p">;</span>

<span class="w">    </span><span class="kt">function</span><span class="w"> </span><span class="nv">executeOperation</span><span class="p">(</span>
<span class="w">        </span><span class="kt">uint256</span><span class="w"> </span><span class="nv">amount</span><span class="p">,</span>
<span class="w">        </span><span class="kt">uint256</span><span class="w"> </span><span class="nv">premium</span><span class="p">,</span>
<span class="w">        </span><span class="kt">address</span><span class="w"> </span><span class="nv">initiator</span>
<span class="w">    </span><span class="p">)</span><span class="w"> </span><span class="kt">external</span><span class="w"> </span>override<span class="p">(</span>IFlashLoanReceiver<span class="p">)</span><span class="w"> </span><span class="kt">returns</span><span class="w"> </span><span class="p">(</span><span class="kt">bool</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">        </span>underlying<span class="p">.</span>transferFrom<span class="p">(</span>pool<span class="p">,</span><span class="w"> </span><span class="kt">address</span><span class="p">(</span><span class="kt">this</span><span class="p">),</span><span class="w"> </span>transfer_amount<span class="p">);</span>
<span class="w">        </span><span class="kt">return</span><span class="w"> </span><span class="kt">true</span><span class="p">;</span>
<span class="w">    </span><span class="p">}</span>
<span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell15">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</div>
<p>Note that this isn’t a complete working example; we haven’t provided a
constructor, or linked the <code class="docutils literal notranslate"><span class="pre">pool</span></code> address to the actual pool, or any way to
ensure that the pool has given the receiver an allowance.  Nevertheless, if we
add it to the scene, the Prover is able to use it to construct a
counterexample. Since the Prover explores every possible value of the <code class="docutils literal notranslate"><span class="pre">pool</span></code>
variable, and every possible value for the underlying’s allowances, it is able
to set up the details of the counterexample automatically.</p>
<p>We do need to do one more piece of setup to get this receiver to work the way
we’d like. If we just add <code class="docutils literal notranslate"><span class="pre">TransferReceiver</span></code> to the scene, the Prover will not
be able to resolve its call to <code class="docutils literal notranslate"><span class="pre">transferFrom</span></code>.  This will cause the same kind
of havoc we saw above. We could remedy this using a <code class="docutils literal notranslate"><span class="pre">DISPATCHER</span></code> summary for
<code class="docutils literal notranslate"><span class="pre">transferFrom</span></code> (see <a class="reference internal" href="#erc20-dispatcher"><span class="std std-ref">Using DISPATCHER for ERC20 contracts</span></a>), but for now, we’ll simply
link the <code class="docutils literal notranslate"><span class="pre">underlying</span></code> variable to the <code class="docutils literal notranslate"><span class="pre">Asset</span></code> contract instance:</p>
<div class="literal-block-wrapper docutils container" id="id19">
<div class="code-block-caption"><span class="caption-text"><a class="reference external" href="https://github.com/Certora/Examples/blob/7dfc379423202c90cf284eb42800b97cf5c95d83/DEFI/LiquidityPool/FlashLoanTransfer.conf">FlashLoanTransfer.conf</a></span><a class="headerlink" href="#id19" title="Link to this code"></a></div>
<div class="highlight-json notranslate"><div class="highlight"><pre id="codecell16"><span></span><span class="p">{</span>
<span class="w">  </span><span class="nt">"files"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span>
<span class="w">    </span><span class="s2">"contracts/Pool.sol"</span><span class="p">,</span>
<span class="w">    </span><span class="s2">"contracts/Asset.sol"</span><span class="p">,</span>
<span class="w">    </span><span class="s2">"certora/harness/TrivialReceiver.sol"</span><span class="p">,</span>
<span class="w">    </span><span class="s2">"certora/harness/TransferReceiver.sol"</span>
<span class="w">  </span><span class="p">],</span>
<span class="w">  </span><span class="nt">"verify"</span><span class="p">:</span><span class="w"> </span><span class="s2">"Pool:certora/specs/flashLoan_dispatcher.spec"</span><span class="p">,</span>
<span class="w">  </span><span class="nt">"msg"</span><span class="p">:</span><span class="w"> </span><span class="s2">"flashLoan with transfer dispatchee"</span><span class="p">,</span>
<span class="hll"><span class="w">  </span><span class="nt">"link"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span>
</span><span class="hll"><span class="w">        </span><span class="s2">"Pool:asset=Asset"</span><span class="p">,</span>
</span><span class="hll"><span class="w">        </span><span class="s2">"TransferReceiver:underlying=Asset"</span>
</span><span class="hll"><span class="w">    </span><span class="p">],</span>
</span><span class="w">  </span><span class="nt">"rule_sanity"</span><span class="p">:</span><span class="w"> </span><span class="s2">"basic"</span>
<span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell16">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</div>
<p>With the additional receiver implementation on the scene, we see that the Prover
considers both alternatives for the <code class="docutils literal notranslate"><span class="pre">executeOperation</span></code> call:</p>
<p><img alt="Call resolution tab showing unresolved call from  to, with the &quot;alternatives&quot; set containing both and " src="../../../_images/transfer-resolution.png"></p>
<p>And we also see that it was able to use the <code class="docutils literal notranslate"><span class="pre">TransferReceiver</span></code> to construct a
counterexample:</p>
<p><img alt="Partial call trace showing  dispatched to, which calls" src="../../../_images/transfer-trace.png"></p>
<p>As we expected, the dispatcher for <code class="docutils literal notranslate"><span class="pre">executeOperation</span></code> chooses
<code class="docutils literal notranslate"><span class="pre">TransferReceiver.executeOperation</span></code> as the receiver, which in turn calls
<code class="docutils literal notranslate"><span class="pre">underlying.transferFrom(Pool,</span> <span class="pre">...,</span> <span class="pre">2)</span></code>.  If we look in the initial storage of the contract,
we see that the Prover chose the pool’s allowance for the recipient to be
<code class="docutils literal notranslate"><span class="pre">10</span></code>:</p>
<p><img alt="Call trace entry showing  returning " src="../../../_images/transfer-allowance.png"></p>
<p>It turns out that this particular violation can’t actually happen, because the
pool contract never approves any other contract to transfer its funds.  We
could prove an invariant to this effect and add it to our rule using
<a class="reference internal" href="../../cvl/statements.html#requireinvariant"><span class="std std-ref">requireInvariant statements</span></a>.</p>
<p>For more examples of <code class="docutils literal notranslate"><span class="pre">requireInvariant</span></code> usage, check out the <a class="reference internal" href="../patterns/require-invariants.html"><span class="std std-doc">user guide</span></a>.</p>
<p>Nevertheless, this example shows that having too few dispatchees can cause a
rule to pass, even though the property it describes is not necessarily true in
all situations.</p>
</section>
<section id="designing-flexible-dispatchees">
<h3><a class="toc-backref" href="#id28" role="doc-backlink">Designing flexible dispatchees</a><a class="headerlink" href="#designing-flexible-dispatchees" title="Link to this heading"></a></h3>
<p>The <code class="docutils literal notranslate"><span class="pre">TransferReceiver</span></code> described in the previous section is fairly targeted: we
thought of a way to violate the rule, and then designed a receiver contract to
cause the violation.  However, one of the main benefits of the Prover is that
you don’t have to know in advance the attacks you’re trying to prevent, and
this approach to creating dispatchees loses that benefit.</p>
<p>There is a clever trick you can use to write flexible dispatchees that can
cover a broad range of potential attacks.  The trick relies on the fact that the
Prover will consider all possible values for contract fields when trying to
produce a counterexample.</p>
<p>Suppose we wanted to reason about the possibility that a flash loan receiver
could make non-view calls back to the pool from <code class="docutils literal notranslate"><span class="pre">executeOperation</span></code>.  We could
write a separate receiver contract for each method which just calls that method,
and add them all to the scene as potential dispatchees.  However, this can
become cumbersome, especially if there are multiple methods that need to be
implemented.</p>
<p>Instead, we can write a single receiver that simulates all of these potential
method calls.  Let’s start by getting a list of the external methods of the
contract.  The Prover helpfully provides such a list whenever we verify a rule<a class="footnote-reference brackets" href="#noview" id="id7" role="doc-noteref"><span class="fn-bracket">[</span>7<span class="fn-bracket">]</span></a>:</p>
<p><img alt="&quot;Contract list&quot; tab (next to the &quot;Results&quot; tab) showing the  contractand all of its methods" src="../../../_images/pool-methods.png"></p>
<p>Now, we can write an <code class="docutils literal notranslate"><span class="pre">executeOperation</span></code> method that could call any of the
non-view functions.  We can do this with a big <code class="docutils literal notranslate"><span class="pre">if</span></code>-<code class="docutils literal notranslate"><span class="pre">then</span></code>-<code class="docutils literal notranslate"><span class="pre">else</span></code> statement (
:clink:<code class="docutils literal notranslate"><span class="pre">full</span> <span class="pre">contract&lt;/DEFI/LiquidityPool/certora/harness/FlexibleReceiver.sol&gt;</span></code>)<a class="footnote-reference brackets" href="#no-recursion" id="id8" role="doc-noteref"><span class="fn-bracket">[</span>8<span class="fn-bracket">]</span></a>:</p>
<div class="highlight-solidity notranslate"><div class="highlight"><pre id="codecell17"><span></span><span class="k">contract</span><span class="w"> </span><span class="ni">FlexibleReceiver</span><span class="w"> </span><span class="kt">is</span><span class="w"> </span>IFlashLoanReceiver<span class="w"> </span><span class="p">{</span>
<span class="w">    </span>IPool<span class="w"> </span>token<span class="p">;</span>

<span class="w">    </span><span class="kt">function</span><span class="w"> </span><span class="nv">executeOperation</span><span class="p">(...)</span><span class="w"> </span><span class="p">...</span><span class="w"> </span><span class="p">{</span>
<span class="w">        </span><span class="kt">uint</span><span class="w">  </span><span class="nv">callbackChoice</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="p">...;</span>

<span class="w">        </span><span class="kt">if</span><span class="w"> </span><span class="p">(</span>callbackChoice<span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">)</span>
<span class="w">            </span>token<span class="p">.</span>deposit<span class="p">(...);</span>
<span class="w">        </span><span class="kt">else</span><span class="w"> </span><span class="kt">if</span><span class="w"> </span><span class="p">(</span>callbackChoice<span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="m m-Decimal">1</span><span class="p">)</span>
<span class="w">            </span>token<span class="p">.</span>transferFrom<span class="p">(...);</span>
<span class="w">        </span><span class="kt">else</span><span class="w"> </span><span class="kt">if</span><span class="w"> </span><span class="p">(</span>callbackChoice<span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="m m-Decimal">2</span><span class="p">)</span>
<span class="w">            </span>token<span class="p">.</span>withdraw<span class="p">(...);</span>
<span class="w">        </span><span class="p">...</span>
<span class="w">        </span><span class="kt">else</span>
<span class="w">            </span>assert<span class="p">(</span><span class="kt">false</span><span class="p">,</span><span class="w"> </span><span class="s2">"invalid callbackChoice value"</span><span class="p">);</span>

<span class="w">        </span><span class="kt">return</span><span class="w"> </span><span class="p">...;</span>
<span class="w">    </span><span class="p">}</span>
<span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell17">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>The value of the <code class="docutils literal notranslate"><span class="pre">callbackChoice</span></code> variable determines which <code class="docutils literal notranslate"><span class="pre">Pool</span></code> method
<code class="docutils literal notranslate"><span class="pre">executeOperation</span></code> will call. We would like the Prover to consider every
possible value of the <code class="docutils literal notranslate"><span class="pre">callbackChoice</span></code> field, so that it can choose to call any
of the pool’s methods. We would also like the Prover to consider every choice
of arguments to these method calls.</p>
<p>For this to be valid solidity code, we need to actually give values to the
<code class="docutils literal notranslate"><span class="pre">callbackChoice</span></code> and the arguments to the called methods. To do this, we use a
clever trick. Since the Prover considers every possible value for storage
variables, we can simply use a storage variable for <code class="docutils literal notranslate"><span class="pre">callbackChoice</span></code> and for
the arguments. For example, we could write</p>
<div class="highlight-solidity notranslate"><div class="highlight"><pre id="codecell18"><span></span><span class="k">contract</span><span class="w"> </span><span class="ni">FlexibleReceiver</span><span class="w"> </span><span class="kt">is</span><span class="w"> </span>IFlashLoanReceiver<span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="p">...</span>

<span class="w">    </span><span class="kt">uint</span><span class="w"> </span><span class="nv">arbitraryCallback</span><span class="p">;</span>
<span class="w">    </span><span class="kt">function</span><span class="w"> </span><span class="nv">executeOperation</span><span class="p">(...)</span><span class="w"> </span><span class="p">...</span><span class="w"> </span><span class="p">{</span>
<span class="w">        </span><span class="kt">uint</span><span class="w"> </span><span class="nv">callbackChoice</span><span class="w"> </span><span class="o">=</span><span class="w"> </span>arbitraryCallback<span class="p">;</span>

<span class="w">        </span><span class="p">...</span>
<span class="w">    </span><span class="p">}</span>
<span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell18">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>The Prover will consider cases where <code class="docutils literal notranslate"><span class="pre">arbitraryCallback</span></code> can have any possible
value at the beginning of the rule, and we can use this arbitrary value to fill
in <code class="docutils literal notranslate"><span class="pre">callbackChoice</span></code><a class="footnote-reference brackets" href="#arbitrary-constructor" id="id9" role="doc-noteref"><span class="fn-bracket">[</span>9<span class="fn-bracket">]</span></a>.</p>
<p>One potential drawback of this choice is that the receiver contract will make
the same callback every time <code class="docutils literal notranslate"><span class="pre">executeOperation</span></code> is called within a rule.  We can
relax this restriction by using a mapping of arbitrary values instead of a
single callback:</p>
<div class="highlight-solidity notranslate"><div class="highlight"><pre id="codecell19"><span></span><span class="k">contract</span><span class="w"> </span><span class="ni">FlexibleReceiver</span><span class="w"> </span><span class="kt">is</span><span class="w"> </span>IFlashLoanReceiver<span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="p">...</span>

<span class="w">    </span><span class="kt">uint</span><span class="w"> </span><span class="nv">counter</span><span class="p">;</span>
<span class="w">    </span><span class="kt">mapping</span><span class="p">(</span><span class="kt">uint</span><span class="w"> </span><span class="o">=&gt;</span><span class="w"> </span><span class="kt">uint</span><span class="p">)</span><span class="w"> </span>arbitraryCallbacks<span class="p">;</span>

<span class="w">    </span><span class="kt">function</span><span class="w"> </span><span class="nv">executeOperation</span><span class="p">(...)</span><span class="w"> </span><span class="p">...</span><span class="w"> </span><span class="p">{</span>
<span class="w">        </span><span class="kt">uint</span><span class="w">  </span><span class="nv">callbackChoice</span><span class="w"> </span><span class="o">=</span><span class="w"> </span>arbitraryCallbacks<span class="p">[</span>counter<span class="o">++</span><span class="p">];</span>

<span class="w">        </span><span class="p">...</span>
<span class="w">    </span><span class="p">}</span>
<span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell19">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>With this version, the Prover is able to choose a new value of
<code class="docutils literal notranslate"><span class="pre">arbitraryCallbacks[i]</span></code> for each <code class="docutils literal notranslate"><span class="pre">i</span></code>; since the <code class="docutils literal notranslate"><span class="pre">counter</span></code> variable is updated
on each call, this means that it can choose a different value of
<code class="docutils literal notranslate"><span class="pre">callbackChoice</span></code> for each call.</p>
<p>The abstract contract <a class="reference external" href="https://github.com/Certora/Examples/blob/7dfc379423202c90cf284eb42800b97cf5c95d83/DEFI/LiquidityPool/certora/helpers/ArbitraryValues.sol">ArbitraryValues</a>
makes this simple. For each value type, it provides an <code class="docutils literal notranslate"><span class="pre">arbitraryType()</span></code> method that
returns an undefined value that the Prover can fill in arbitrarily as it is
constructing counterexamples.  For example, the <code class="docutils literal notranslate"><span class="pre">arbitraryInt192()</span></code> method
returns a newly selected <code class="docutils literal notranslate"><span class="pre">int192</span></code> each time it called.  In this case, we can
use the <code class="docutils literal notranslate"><span class="pre">arbitraryUint</span></code> and <code class="docutils literal notranslate"><span class="pre">arbitraryAddress</span></code> methods to choose the callback
and the arguments (conf file <a class="reference external" href="https://github.com/Certora/Examples/blob/7dfc379423202c90cf284eb42800b97cf5c95d83/DEFI/LiquidityPool/WithFlexibleLinked.conf">WithFlexibleLinked.conf</a>).</p>
<div class="literal-block-wrapper docutils container" id="id20">
<div class="code-block-caption"><span class="caption-text"><a class="reference external" href="https://github.com/Certora/Examples/blob/7dfc379423202c90cf284eb42800b97cf5c95d83/DEFI/LiquidityPool/certora/harness/FlexibleReceiver.sol">FlexibleReceiver.sol</a></span><a class="headerlink" href="#id20" title="Link to this code"></a></div>
<div class="highlight-solidity notranslate"><div class="highlight"><pre id="codecell20"><span></span><span class="cm">/**</span>
<span class="cm"> * A flexible implementation of the FlashLoanReceiver callback that</span>
<span class="cm"> * nondeterministically makes calls back to the token.</span>
<span class="cm"> */</span>
<span class="k">contract</span><span class="w"> </span><span class="ni">FlexibleReceiver</span><span class="w"> </span><span class="kt">is</span><span class="w"> </span>IFlashLoanReceiver<span class="p">,</span><span class="w"> </span>ArbitraryValues<span class="w"> </span><span class="p">{</span>
<span class="w">    </span>IPool<span class="w">   </span>token<span class="p">;</span>

<span class="w">    </span><span class="cm">/**</span>
<span class="cm">     * Nondeterministically call {deposit}, {transferFrom}, {withdraw},</span>
<span class="cm">     * {transfer}, or {approve} on the {token}.</span>
<span class="cm">     *</span>
<span class="cm">     * @return true</span>
<span class="cm">     */</span>
<span class="w">    </span><span class="kt">function</span><span class="w"> </span><span class="nv">executeOperation</span><span class="p">(</span>
<span class="w">        </span><span class="kt">uint256</span><span class="w"> </span><span class="nv">amount</span><span class="p">,</span>
<span class="w">        </span><span class="kt">uint256</span><span class="w"> </span><span class="nv">premium</span><span class="p">,</span>
<span class="w">        </span><span class="kt">address</span><span class="w"> </span><span class="nv">initiator</span>
<span class="w">    </span><span class="p">)</span><span class="w"> </span><span class="kt">external</span><span class="w"> </span>override<span class="p">(</span>IFlashLoanReceiver<span class="p">)</span><span class="w"> </span><span class="kt">returns</span><span class="w"> </span><span class="p">(</span><span class="kt">bool</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>

<span class="w">        </span><span class="kt">uint</span><span class="w">    </span><span class="nv">callbackChoice</span><span class="w">    </span><span class="o">=</span><span class="w"> </span>arbitraryUint<span class="p">();</span>

<span class="w">        </span><span class="kt">if</span><span class="w"> </span><span class="p">(</span>callbackChoice<span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">)</span>
<span class="w">            </span>token<span class="p">.</span>deposit<span class="p">(</span>arbitraryUint<span class="p">());</span>
<span class="w">        </span><span class="kt">else</span><span class="w"> </span><span class="kt">if</span><span class="w"> </span><span class="p">(</span>callbackChoice<span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="m m-Decimal">1</span><span class="p">)</span>
<span class="w">            </span>token<span class="p">.</span>transferFrom<span class="p">(</span>arbitraryAddress<span class="p">(),</span>arbitraryAddress<span class="p">(),</span>arbitraryUint<span class="p">());</span>
<span class="w">        </span><span class="kt">else</span><span class="w"> </span><span class="kt">if</span><span class="w"> </span><span class="p">(</span>callbackChoice<span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="m m-Decimal">2</span><span class="p">)</span>
<span class="w">            </span>token<span class="p">.</span>withdraw<span class="p">(</span>arbitraryUint<span class="p">());</span>
<span class="w">        </span><span class="kt">else</span><span class="w"> </span><span class="kt">if</span><span class="w"> </span><span class="p">(</span>callbackChoice<span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="m m-Decimal">3</span><span class="p">)</span>
<span class="w">            </span>token<span class="p">.</span>transfer<span class="p">(</span>arbitraryAddress<span class="p">(),</span>arbitraryUint<span class="p">());</span>
<span class="w">        </span><span class="kt">else</span><span class="w"> </span><span class="kt">if</span><span class="w"> </span><span class="p">(</span>callbackChoice<span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="m m-Decimal">4</span><span class="p">)</span>
<span class="w">            </span>token<span class="p">.</span>approve<span class="p">(</span>arbitraryAddress<span class="p">(),</span>arbitraryUint<span class="p">());</span>

<span class="w">        </span><span class="kt">return</span><span class="w"> </span><span class="kt">true</span><span class="p">;</span>
<span class="w">    </span><span class="p">}</span>
<span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell20">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</div>
<p>With this implementation, the Prover will consider every possible value for
<code class="docutils literal notranslate"><span class="pre">callbackChoice</span></code> as well as for the arguments to the methods, which has the
effect of calling an arbitrary non-view method on <code class="docutils literal notranslate"><span class="pre">pool</span></code> with arbitrary
arguments.</p>
<p>This approach still doesn’t give perfect coverage.  If the <code class="docutils literal notranslate"><span class="pre">token</span></code> field is
linked to the pool, it will only call methods on the pool.  In fact, this
receiver will miss the violation that the <code class="docutils literal notranslate"><span class="pre">TransferReceiver</span></code> uncovered, because
that requires calling <code class="docutils literal notranslate"><span class="pre">transferFrom</span></code> on the <code class="docutils literal notranslate"><span class="pre">Asset</span></code> rather than the <code class="docutils literal notranslate"><span class="pre">Pool</span></code>,
although this particular shortcoming can be
addressed by <a class="reference internal" href="#erc20-dispatcher"><span class="std std-ref">using a dispatcher for the ERC20 methods</span></a>
instead of linking to the pool.</p>
<p>Another important caveat is that this technique does not work for initial state
checks for invariants.  In this case, the Prover does not choose arbitrary
values for storage variables, since it knows that storage variables are all
initialized to 0 before the constructor call.  Therefore, the <code class="docutils literal notranslate"><span class="pre">arbitraryType()</span></code>
methods will always return 0.</p>
<p>A third shortcoming with this implementation is that it only makes one
reentrant call to the <code class="docutils literal notranslate"><span class="pre">token</span></code> contract.  Vulnerabilities that require two or
more callbacks from the <code class="docutils literal notranslate"><span class="pre">FlashLoanReceiver</span></code> to exploit will not be detected.</p>
<p>Nevertheless, this technique is a useful way to build dispatchers that get
pretty good coverage without requiring too much prediction of the bugs they
will find.  The <code class="docutils literal notranslate"><span class="pre">ArbitraryValues</span></code> helper contract makes this pattern easy to
implement.</p>
</section>
<section id="using-dispatcher-for-erc20-contracts">
<span id="erc20-dispatcher"></span><h3><a class="toc-backref" href="#id29" role="doc-backlink">Using <code class="docutils literal notranslate"><span class="pre">DISPATCHER</span></code> for ERC20 contracts</a><a class="headerlink" href="#using-dispatcher-for-erc20-contracts" title="Link to this heading"></a></h3>
<p>One very common use case for the material discussed in this chapter is when a
contract is designed to work with arbitrary ERC20 tokens.  In this case, it is
common to summarize all of the ERC20 methods using <code class="docutils literal notranslate"><span class="pre">DISPATCHER</span></code> summaries, and
to provide several ERC20 implementations to the Prover.</p>
<p>To facilitate this, the <a class="reference external" href="https://github.com/Certora/Examples/tree/7dfc379423202c90cf284eb42800b97cf5c95d83/DEFI/LiquidityPool/certora/helpers">helpers</a>
directory of the example code contains a
<a class="reference external" href="https://github.com/Certora/Examples/blob/7dfc379423202c90cf284eb42800b97cf5c95d83/DEFI/LiquidityPool/certora/helpers/erc20.spec">spec file called erc20.spec</a>
as well as a variety of ERC20 token implementations
(inside <a class="reference external" href="https://github.com/Certora/Examples/tree/7dfc379423202c90cf284eb42800b97cf5c95d83/DEFI/LiquidityPool/certora/helpers/tokens">tokens</a> folder).
The <code class="docutils literal notranslate"><span class="pre">erc20.spec</span></code> file simply contains a methods block that summarizes all of the
ERC20 methods as <code class="docutils literal notranslate"><span class="pre">DISPATCHER</span></code>.  You can use an
<a class="reference internal" href="../../cvl/imports.html"><span class="doc">import statement</span></a> to include this in your spec:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell21"><span></span><span class="kn">import</span><span class="w"> </span><span class="s2">"../helpers/erc20.spec"</span><span class="p">;</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell21">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>This gives a concise way to handle this situation.  Be sure to include the
tokens in the scene!</p>
</section>
</section>
<section id="conclusion">
<h2><a class="toc-backref" href="#id30" role="doc-backlink">Conclusion</a><a class="headerlink" href="#conclusion" title="Link to this heading"></a></h2>
<p>In this chapter, we’ve seen several techniques for handling inter-contract
calls.  Linking allows us to give the source code for a contract referenced by
a particular field.  <code class="docutils literal notranslate"><span class="pre">DISPATCHER</span></code> summaries instruct the Prover to consider
several possible implementations of a contract, and can be used when we don’t
know exactly which contract an address will refer to.</p>
<p>We’ve seen that <code class="docutils literal notranslate"><span class="pre">DISPATCHER</span></code> summaries are not completely safe — they
constrain the possible implementations of external contracts, so they may miss
bugs that those implementations don’t trigger.  However, we have seen a useful
technique that can explore a wide range of behaviors with little effort.</p>
<hr class="footnotes docutils">
<aside class="footnote-list brackets">
<aside class="footnote brackets" id="reentrancy" role="doc-footnote">
<span class="label"><span class="fn-bracket">[</span><a role="doc-backlink" href="#id1">1</a><span class="fn-bracket">]</span></span>
<p>The Prover assumes that the external calls do not modify the
storage of the calling contract.  This assumption comes from an assumption
that the called code is non-reentrant.  If you are concerned about violations
caused by reentrancy, you can override this assumption using a <code class="docutils literal notranslate"><span class="pre">HAVOC_ALL</span></code>
summary; see <a class="reference internal" href="../../cvl/methods.html#havoc-summary"><span class="std std-ref">Havoc summaries: HAVOC_ALL and HAVOC_ECF</span></a> for details.</p>
</aside>
<aside class="footnote brackets" id="resolutionwarnings" role="doc-footnote">
<span class="label"><span class="fn-bracket">[</span><a role="doc-backlink" href="#id2">2</a><span class="fn-bracket">]</span></span>
<p>Unresolved calls that are not explicitly handled are
considered warnings; in this case there are three unresolved calls, which is
why there is a red 3 on the call resolution tab.  In general, it is good
practice to explicitly resolve all calls.</p>
</aside>
<aside class="footnote brackets" id="addressoption" role="doc-footnote">
<span class="label"><span class="fn-bracket">[</span><a role="doc-backlink" href="#id3">3</a><span class="fn-bracket">]</span></span>
<p>You can control the address chosen for the contract instance
using the <a class="reference internal" href="../../prover/cli/options.html#address"><span class="std std-ref">address</span></a> option.</p>
</aside>
<aside class="footnote brackets" id="using-position" role="doc-footnote">
<span class="label"><span class="fn-bracket">[</span><a role="doc-backlink" href="#id4">4</a><span class="fn-bracket">]</span></span>
<p><code class="docutils literal notranslate"><span class="pre">using</span></code> statements must appear after the <code class="docutils literal notranslate"><span class="pre">import</span></code> statements
(if any) and before the <code class="docutils literal notranslate"><span class="pre">methods</span></code> block (if any).</p>
</aside>
<aside class="footnote brackets" id="wildcards" role="doc-footnote">
<span class="label"><span class="fn-bracket">[</span><a role="doc-backlink" href="#id5">5</a><span class="fn-bracket">]</span></span>
<p>instead of <code class="docutils literal notranslate"><span class="pre">underlying.balanceOf</span></code> in the methods block, you could
also use the contract name: <code class="docutils literal notranslate"><span class="pre">Asset.balanceOf</span></code>.  You could also write a single
entry for all <code class="docutils literal notranslate"><span class="pre">balanceOf</span></code> methods using <code class="docutils literal notranslate"><span class="pre">_</span></code> for the contract: <code class="docutils literal notranslate"><span class="pre">_.balanceOf</span></code>.
See <a class="reference internal" href="../../cvl/methods.html#methods-entries"><span class="std std-ref">Methods entry patterns</span></a> for full details.</p>
</aside>
<aside class="footnote brackets" id="optimistic-dispatcher" role="doc-footnote">
<span class="label"><span class="fn-bracket">[</span><a role="doc-backlink" href="#id6">6</a><span class="fn-bracket">]</span></span>
<p>The <code class="docutils literal notranslate"><span class="pre">true</span></code> in <code class="docutils literal notranslate"><span class="pre">DISPATCHER(true)</span></code> tells the Prover to
use “optimistic dispatch mode”.  Optimistic mode is almost always the right
choice; see <a class="reference internal" href="../../cvl/methods.html#dispatcher"><span class="std std-ref">DISPATCHER summaries</span></a> in the reference manual for full details.</p>
</aside>
<aside class="footnote brackets" id="noview" role="doc-footnote">
<span class="label"><span class="fn-bracket">[</span><a role="doc-backlink" href="#id7">7</a><span class="fn-bracket">]</span></span>
<p>The Prover doesn’t identify the view functions, so we have to look at
the source code to determine which ones are non-view functions.</p>
</aside>
<aside class="footnote brackets" id="no-recursion" role="doc-footnote">
<span class="label"><span class="fn-bracket">[</span><a role="doc-backlink" href="#id8">8</a><span class="fn-bracket">]</span></span>
<p>We don’t include a call to <code class="docutils literal notranslate"><span class="pre">token.flashLoan</span></code> since this will
cause potentially infinite recursion, which will cause the Prover to fail.</p>
</aside>
<aside class="footnote brackets" id="arbitrary-constructor" role="doc-footnote">
<span class="label"><span class="fn-bracket">[</span><a role="doc-backlink" href="#id9">9</a><span class="fn-bracket">]</span></span>
<p>This trick doesn’t work during the initial state
checks for invariants, since storage is always initialized to zero at the
start of a constructor.</p>
</aside>
</aside>
</section>
</section>


           </div>
          </div>
          <footer><div class="rst-footer-buttons" role="navigation" aria-label="Footer">
        <a href="../opcodes.html" class="btn btn-neutral float-left" title="Using Opcode Hooks" accesskey="p" rel="prev"><span class="fa fa-arrow-circle-left" aria-hidden="true"></span> Previous</a>
        <a href="../out-of-resources/index.html" class="btn btn-neutral float-right" title="Managing Timeouts and Out of Memory Problems" accesskey="n" rel="next">Next <span class="fa fa-arrow-circle-right" aria-hidden="true"></span></a>
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