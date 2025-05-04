<!DOCTYPE html><html class="writer-html5" lang="en" data-content_root="../../../"><head>
  <meta charset="utf-8"><meta name="viewport" content="width=device-width, initial-scale=1">

  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Modeling of Hashing in the Certora Prover — Certora Prover Documentation 0.0 documentation</title>
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
    <link rel="next" title="Quantifier Grounding" href="grounding.html">
    <link rel="prev" title="Harnessing" href="harnessing.html"> 
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
<li class="toctree-l3"><a class="reference internal" href="loops.html">Loop Unrolling</a></li>
<li class="toctree-l3"><a class="reference internal" href="summarization.html">Method Summarization</a></li>
<li class="toctree-l3"><a class="reference internal" href="harnessing.html">Harnessing</a></li>
<li class="toctree-l3 current" aria-expanded="true"><a class="reference internal current" href="#" aria-expanded="true"><button class="toctree-expand" title="Open/close menu"></button>Modeling of Hashing in the Certora Prover</a><ul>
<li class="toctree-l4"><a class="reference internal" href="#introduction">Introduction</a></li>
<li class="toctree-l4"><a class="reference internal" href="#modeling-the-keccak-function-bounded-case">Modeling the Keccak function (bounded case)</a></li>
<li class="toctree-l4"><a class="reference internal" href="#hashing-of-unbounded-data">Hashing of unbounded data</a></li>
<li class="toctree-l4"><a class="reference internal" href="#background-the-solidity-storage-model">Background: The Solidity Storage Model</a></li>
<li class="toctree-l4"><a class="reference internal" href="#conclusion">Conclusion</a></li>
</ul>
</li>
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
      <li class="breadcrumb-item active">Modeling of Hashing in the Certora Prover</li>
      <li class="wy-breadcrumbs-aside">
            <a href="../../../_sources/docs/prover/approx/hashing.md.txt" rel="nofollow"> View page source</a>
      </li>
  </ul>
  <hr>
</div>
          <div role="main" class="document" itemscope="itemscope" itemtype="http://schema.org/Article">
           <div itemprop="articleBody">
             
  <section id="modeling-of-hashing-in-the-certora-prover">
<span id="hashing"></span><h1>Modeling of Hashing in the Certora Prover<a class="headerlink" href="#modeling-of-hashing-in-the-certora-prover" title="Link to this heading"></a></h1>
<p>In this document we present how the Keccak hash function is modeled in the
Certora Prover and how that impacts smart contract verification.</p>
<section id="introduction">
<h2>Introduction<a class="headerlink" href="#introduction" title="Link to this heading"></a></h2>
<p>The Keccak hash function is used heavily by Solidity smart contracts in an
implicit way.
Most prominently, all unbounded data structures in storage (arrays, mappings)
receive their storage addresses as values of the Keccak function.
It is also possible to call the Keccak hash function explicitly, both through
a solidity built in function and through inline assembly.</p>
<p>The Certora Prover does not operate with an actual implementation of the Keccak
hash function, since this would make most verification intractable and provide
no practical benefits.
Instead, the Certora Prover models the properties of the Keccak hash
function that are crucial for the function of the smart contracts under
verification while abstracting away from implementation details of the actual
hash function.</p>
</section>
<section id="modeling-the-keccak-function-bounded-case">
<h2>Modeling the Keccak function (bounded case)<a class="headerlink" href="#modeling-the-keccak-function-bounded-case" title="Link to this heading"></a></h2>
<p>The Certora Prover models the Keccak hash function as an arbitrary function that
is <em>injective with large gaps</em>.</p>
<p>The hash function <code class="docutils literal notranslate"><span class="pre">hash</span></code> being injective with large gaps means that on distinct
inputs <code class="docutils literal notranslate"><span class="pre">x</span></code> and <code class="docutils literal notranslate"><span class="pre">y</span></code></p>
<ul class="simple">
<li><p>the hashes <code class="docutils literal notranslate"><span class="pre">hash(x)</span></code> and <code class="docutils literal notranslate"><span class="pre">hash(y)</span></code> are also distinct, and</p></li>
<li><p>the gap between <code class="docutils literal notranslate"><span class="pre">hash(x)</span></code> and <code class="docutils literal notranslate"><span class="pre">hash(y)</span></code> is large enough that every additive
term <code class="docutils literal notranslate"><span class="pre">hash(x)</span> <span class="pre">+</span> <span class="pre">i</span></code> that occurs in the program is also distinct from <code class="docutils literal notranslate"><span class="pre">hash(y)</span></code>.</p></li>
</ul>
<p>Furthermore, the initial storage slots and large constants that appear in the code
are reserved. I.e., we make sure that no hash value ends up colliding with slots
0 to 10000 nor with any constant that is explicitly given in the source code. (The
latter constraint is necessary to avoid collisions with hashes that the solidity
compiler has precompiled.)</p>
<p>These constraints are enough for the Solidity storage model to work as expected.
However, this modeling allows the Certora Prover to pick hash functions that
show different behavior from the actual Keccak function. For instance, it is
unlikely that the individual numeric values or their ordering matches that of
the Keccak function. We present some examples in the following subsection. We
have not observed a practical use case yet where the numeric values of the hash
function play a role, thus we chose this modeling for tractability reasons.</p>
<p>See the later subsection <a class="reference internal" href="#background-the-solidity-storage-model"><span class="std std-ref">Background: The Solidity Storage Model</span></a> for
details on why this property is an adequate model for maintaining integrity
of solidity’s storage operations.</p>
<section id="examples-imprecision-of-modeling">
<h3>Examples (Imprecision of Modeling)<a class="headerlink" href="#examples-imprecision-of-modeling" title="Link to this heading"></a></h3>
<p>We illustrate the implications of our modeling decisions using a few examples.</p>
</section>
<section id="modeling-does-not-account-for-individual-values-of-the-keccak-function">
<h3>Modeling does not account for individual values of the Keccak function<a class="headerlink" href="#modeling-does-not-account-for-individual-values-of-the-keccak-function" title="Link to this heading"></a></h3>
<p>The Keccak256-hash of the string <code class="docutils literal notranslate"><span class="pre">hello</span></code> is
<code class="docutils literal notranslate"><span class="pre">0x1c8aff950685c2ed4bc3174f3472287b56d9517b9c948127319a09a7a36deac8</span></code>.
However, due to our modeling, the Certora Prover cannot prove that fact. the
rule <code class="docutils literal notranslate"><span class="pre">hashOf17Eq</span></code> will show as “violated” since the Prover can pick a function
for <code class="docutils literal notranslate"><span class="pre">keccak256</span></code> that assigns <code class="docutils literal notranslate"><span class="pre">hello</span></code> differently.
For the same reason the Prover also does not disprove that the hash of <code class="docutils literal notranslate"><span class="pre">17</span></code>
is <code class="docutils literal notranslate"><span class="pre">0x1c8aff950685c2ed4bc3174f3472287b56d9517b9c948127319a09a7a36deac8</span></code>, since
we allow it to choose <code class="docutils literal notranslate"><span class="pre">keccak256</span></code> appropriately.</p>
<div class="highlight-solidity notranslate"><div class="highlight"><pre id="codecell0"><span></span><span class="c1">// CVL:</span>
methods<span class="w"> </span><span class="p">{</span><span class="w"> </span><span class="kt">hash</span><span class="p">(</span><span class="kt">uint</span><span class="p">)</span><span class="w"> </span><span class="kt">returns</span><span class="w"> </span><span class="p">(</span><span class="kt">uint</span><span class="p">)</span><span class="w"> </span>envfree<span class="p">;</span><span class="w"> </span><span class="p">}</span>

rule<span class="w"> </span>hashOf17Eq<span class="w"> </span><span class="p">{</span>
<span class="w">	</span>assert<span class="p">(</span><span class="kt">hash</span><span class="p">(</span><span class="s2">"hello"</span><span class="p">)</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="mh">0x1c8aff950685c2ed4bc3174f3472287b56d9517b9c948127319a09a7a36deac8</span><span class="p">);</span>
<span class="p">}</span>

rule<span class="w"> </span>hashOf17Neq<span class="w"> </span><span class="p">{</span>
<span class="w">	</span>assert<span class="p">(</span><span class="kt">hash</span><span class="p">(</span><span class="s2">"hello"</span><span class="p">)</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="mh">0x1c8aff950685c2ed4bc3174f3472287b56d9517b9c948127319a09a7a36deac8</span><span class="p">);</span>
<span class="p">}</span>

<span class="c1">// solidity:</span>
<span class="k">contract</span><span class="w"> </span><span class="ni">C</span><span class="w"> </span><span class="p">{</span>
<span class="w">	</span><span class="kt">function</span><span class="w"> </span><span class="nv">hash</span><span class="p">(</span><span class="kt">string</span><span class="w"> </span><span class="nv">x</span><span class="p">)</span><span class="w"> </span><span class="kt">public</span><span class="w"> </span><span class="kt">returns</span><span class="w"> </span><span class="p">(</span><span class="kt">bytes32</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">		</span><span class="kt">return</span><span class="w"> </span><span class="nb">keccak256</span><span class="p">(</span><span class="kt">bytes</span><span class="p">(</span>x<span class="p">));</span>
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
</section>
<section id="modeling-does-not-account-for-ordering">
<h3>Modeling does not account for ordering<a class="headerlink" href="#modeling-does-not-account-for-ordering" title="Link to this heading"></a></h3>
<p>Whichever distinct values we chose for <code class="docutils literal notranslate"><span class="pre">x</span></code> and <code class="docutils literal notranslate"><span class="pre">y</span></code> in the example below, on the
real Keccak function, one rule would be violated and one rule would not. In the
modeling of the Certora Prover, both rules are violated, since the Prover is
allowed to “invent” a hash function for each rule and will choose one that
violates the property whenever there is such a function (as long as that
function fulfills the “injectivity with large gaps” property).</p>
<div class="highlight-solidity notranslate"><div class="highlight"><pre id="codecell1"><span></span><span class="c1">// CVL:</span>
methods<span class="w"> </span><span class="p">{</span><span class="w"> </span><span class="kt">hash</span><span class="p">(</span><span class="kt">uint</span><span class="p">)</span><span class="w"> </span><span class="kt">returns</span><span class="w"> </span><span class="p">(</span><span class="kt">uint</span><span class="p">)</span><span class="w"> </span>envfree<span class="p">;</span><span class="w"> </span><span class="p">}</span>

definition<span class="w"> </span>x<span class="p">()</span><span class="w"> </span><span class="o">:</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="m m-Decimal">12345678</span>
definition<span class="w"> </span>y<span class="p">()</span><span class="w"> </span><span class="o">:</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="m m-Decimal">87654321</span>

rule<span class="w"> </span>hashXLowerOrEqualToHashY<span class="w"> </span><span class="p">{</span>
<span class="w">	</span>assert<span class="w"> </span><span class="kt">hash</span><span class="p">(</span>x<span class="p">())</span><span class="w"> </span><span class="o">&lt;=</span><span class="w"> </span><span class="kt">hash</span><span class="p">(</span>y<span class="p">());</span>
<span class="p">}</span>

rule<span class="w"> </span>hashXLargerThanHashY<span class="w"> </span><span class="p">{</span>
<span class="w">	</span>assert<span class="p">(</span><span class="kt">hash</span><span class="p">(</span>x<span class="p">())</span><span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="kt">hash</span><span class="p">(</span>y<span class="p">()));</span>
<span class="p">}</span>

<span class="c1">// solidity:</span>
<span class="k">contract</span><span class="w"> </span><span class="ni">C</span><span class="w"> </span><span class="p">{</span>
<span class="w">	</span><span class="kt">function</span><span class="w"> </span><span class="nv">hash</span><span class="p">(</span><span class="kt">uint</span><span class="w"> </span><span class="nv">x</span><span class="p">)</span><span class="w"> </span><span class="kt">public</span><span class="w"> </span><span class="kt">returns</span><span class="w"> </span><span class="p">(</span><span class="kt">bytes32</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">		</span><span class="c1">// we're assuming presence of some to_bytes function here; it's </span>
<span class="w">		</span><span class="c1">// practical implementation is not relevant here</span>
<span class="w">		</span><span class="kt">return</span><span class="w"> </span><span class="nb">keccak256</span><span class="p">(</span>to_bytes<span class="p">(</span>x<span class="p">));</span><span class="w"> </span>
<span class="w">	</span><span class="p">}</span>
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
<section id="constants-in-code-vs-hashes">
<h3>Constants in code vs hashes<a class="headerlink" href="#constants-in-code-vs-hashes" title="Link to this heading"></a></h3>
<p>A special case in Certora Prover’s modeling of hashing is the treatment of
constants that appear in the code: The Prover implicitly assumes that the hash
function never outputs one of these constants on any of the concrete inputs it
gets in that program.</p>
<p>For an example, consider this rule and spec:</p>
<div class="highlight-default notranslate"><div class="highlight"><pre id="codecell2"><span></span><span class="o">//</span> <span class="n">CVL</span><span class="p">:</span>
<span class="n">methods</span> <span class="p">{</span>
    <span class="n">function</span> <span class="n">readAtSlotAddress</span><span class="p">()</span> <span class="n">external</span> <span class="n">returns</span> <span class="p">(</span><span class="n">uint</span><span class="p">)</span> <span class="n">envfree</span><span class="p">;</span>
    <span class="n">function</span> <span class="n">updateMap</span><span class="p">(</span><span class="n">uint</span> <span class="n">k</span><span class="p">,</span> <span class="n">uint</span> <span class="n">v</span><span class="p">)</span> <span class="n">external</span> <span class="n">envfree</span><span class="p">;</span>
<span class="p">}</span>

<span class="n">rule</span> <span class="n">foo</span> <span class="p">{</span>
	<span class="n">uint</span> <span class="n">v1</span> <span class="o">=</span> <span class="n">readAtSlotAddress</span><span class="p">();</span>

	<span class="n">uint</span> <span class="n">preImage</span><span class="p">;</span>
	<span class="n">uint</span> <span class="n">x</span><span class="p">;</span> 

	<span class="n">updateMap</span><span class="p">(</span><span class="n">preImage</span><span class="p">,</span> <span class="n">x</span><span class="p">);</span>

	<span class="n">uint</span> <span class="n">v2</span> <span class="o">=</span> <span class="n">readAtSlotAddress</span><span class="p">();</span>

	<span class="k">assert</span><span class="p">(</span><span class="n">v1</span> <span class="o">==</span> <span class="n">v2</span><span class="p">);</span>
<span class="p">}</span>

<span class="o">//</span> <span class="n">solidity</span>
<span class="n">contract</span> <span class="n">C</span> <span class="p">{</span>
	<span class="n">uint</span> <span class="n">constant</span> <span class="n">slotAddress</span> <span class="o">=</span> <span class="mi">1000000</span><span class="p">;</span>

	<span class="n">mapping</span><span class="p">(</span><span class="n">uint</span> <span class="o">=&gt;</span> <span class="n">uint</span><span class="p">)</span> <span class="nb">map</span><span class="p">;</span>

	<span class="n">function</span> <span class="n">updateMap</span><span class="p">(</span><span class="n">uint</span> <span class="n">k</span><span class="p">,</span> <span class="n">uint</span> <span class="n">v</span><span class="p">)</span> <span class="n">public</span> <span class="p">{</span>
		<span class="nb">map</span><span class="p">[</span><span class="n">k</span><span class="p">]</span> <span class="o">=</span> <span class="n">v</span><span class="p">;</span>
	<span class="p">}</span>

	<span class="n">function</span> <span class="n">readAtSlotAddress</span><span class="p">()</span> <span class="n">public</span> <span class="n">returns</span> <span class="p">(</span><span class="n">uint</span> <span class="n">r</span><span class="p">)</span> <span class="p">{</span>
		<span class="n">assembly</span> <span class="p">{</span>
			<span class="n">r</span> <span class="o">:=</span> <span class="n">sload</span><span class="p">(</span><span class="n">slotAddress</span><span class="p">)</span>
		<span class="p">}</span>
	<span class="p">}</span>
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
<p>The function <code class="docutils literal notranslate"><span class="pre">readAtSlotAddress</span></code> reads from storage at the slot with the number
1000000. The function <code class="docutils literal notranslate"><span class="pre">updateMap</span></code> updates a mapping; this means it updates
storage at a hash computed from its identifier (here 1, since it is the second
field in the contract) and the key <code class="docutils literal notranslate"><span class="pre">k</span></code>. Now, if <code class="docutils literal notranslate"><span class="pre">k</span></code> is chosen such that
<code class="docutils literal notranslate"><span class="pre">keccak(1,</span> <span class="pre">k)</span></code> equals 1000000, the map update would overwrite that storage
slot, and thus the assertion in the rule <code class="docutils literal notranslate"><span class="pre">foo</span></code> would be violated.</p>
<p>However, the Certora Prover will return “not violated” for this assertion, since
it assumes that no hash ever collides with the constant 1000000, which occurs in
the program.</p>
<p>On the other hand, if we change the contract to leave <code class="docutils literal notranslate"><span class="pre">slotAddress</span></code>
uninitialized, then Certora Prover will return a violation, since then it can
choose the values such that <code class="docutils literal notranslate"><span class="pre">keccak(2,</span> <span class="pre">preImage)</span></code> == <code class="docutils literal notranslate"><span class="pre">slotAddress</span></code>.</p>
<p>Also see this <a class="reference external" href="https://prover.certora.com/output/91772/e02fc5c0f57c4404b6fe28f237ecab07?anonymousKey=9e9e40a985a82d55446b0cdc2c75a7540ca696bc">example run</a>
for a further illustration of both cases.</p>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>The reader may wonder at first whether this means that the Certora Prover computes
the inverse value of the Keccak function for some image value (which would be a
challenging task in and of itself). This is not the case, in practice the Prover
makes up any arbitrary function that fulfills the previously described axioms and
also maps that single input to an output accordingly.</p>
</div>
</section>
</section>
<section id="hashing-of-unbounded-data">
<span id="hashing-unbounded"></span><h2>Hashing of unbounded data<a class="headerlink" href="#hashing-of-unbounded-data" title="Link to this heading"></a></h2>
<p>In the discussion so far we only considered hashes of data whose length is
already known before program execution (e.g. a <code class="docutils literal notranslate"><span class="pre">uint</span></code> variable always has 256
bits). Hashing of unbounded data (typically unbounded arrays, like <code class="docutils literal notranslate"><span class="pre">bytes</span></code>,
<code class="docutils literal notranslate"><span class="pre">uint[]</span></code>, etc.) requires some extra measures, since their implementation
requires loops and the Certora Prover
<a class="reference internal" href="loops.html"><span class="doc">internally eliminates all loops</span></a> in order to achieve better
tractability.</p>
<p>The Certora Prover models unbounded hashing similar to how it eliminates loops.
The user specifies an upper length bound up to which unbounded hashing should
be modeled precisely (using the CLI option <a class="reference internal" href="../cli/options.html#hashing-length-bound"><span class="std std-ref">hashing_length_bound</span></a>) as
well as whether this bound is to be assumed or to be verified (using the CLI
option <a class="reference internal" href="../cli/options.html#optimistic-hashing"><span class="std std-ref">optimistic_hashing</span></a>).</p>
<p>We demonstrate how these flags work using the following program snippet:</p>
<div class="highlight-solidity notranslate"><div class="highlight"><pre id="codecell3"><span></span><span class="k">contract</span><span class="w"> </span><span class="ni">C</span><span class="w"> </span><span class="p">{</span>
<span class="w">	</span><span class="kt">mapping</span><span class="p">(</span><span class="kt">bytes</span><span class="w"> </span><span class="o">=&gt;</span><span class="w"> </span><span class="kt">uint</span><span class="p">)</span><span class="w"> </span>m<span class="p">;</span>
<span class="w">	</span><span class="kt">bytes</span><span class="w"> </span><span class="nv">b1</span><span class="p">,</span><span class="w"> </span>b2<span class="p">,</span><span class="w"> </span>b3<span class="p">;</span>
<span class="w">	</span><span class="kt">uint</span><span class="w"> </span><span class="nv">u</span><span class="p">,</span><span class="w"> </span>v<span class="p">,</span><span class="w"> </span>w<span class="p">;</span>
<span class="w">	</span><span class="c1">// ...</span>
<span class="w">		</span><span class="kt">require</span><span class="w"> </span>b1<span class="p">.</span>length<span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="m m-Decimal">224</span><span class="p">;</span>
<span class="w">		</span>m<span class="p">[</span>b1<span class="p">]</span><span class="w"> </span><span class="o">=</span><span class="w"> </span>u<span class="p">;</span>
<span class="w">	</span><span class="c1">// ...</span>
<span class="w">		</span><span class="c1">// no constraints on b2.length</span>
<span class="w">		</span>m<span class="p">[</span>b2<span class="p">]</span><span class="w"> </span><span class="o">=</span><span class="w"> </span>v<span class="p">;</span><span class="w"> </span>
<span class="w">	</span><span class="c1">// ...</span>
<span class="w">		</span><span class="c1">// no constraints on b3.length</span>
<span class="w">		</span>m<span class="p">[</span>b3<span class="p">]</span><span class="w"> </span><span class="o">=</span><span class="w"> </span>v<span class="p">;</span>
<span class="w">		</span>assert<span class="p">(</span>b3<span class="p">.</span>length<span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="m m-Decimal">300</span><span class="p">,</span><span class="w"> </span><span class="s2">"b3 is more than 300 bytes long, unexpectedly"</span><span class="p">)</span>
<span class="w">	</span><span class="c1">// ...</span>
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
<p>Let us assume that the <code class="docutils literal notranslate"><span class="pre">--hashing_length_bound</span></code> flag is set to 224 (which
corresponds to 7 machine words).</p>
<p>Then, the first hash operation, triggered by the mapping access <code class="docutils literal notranslate"><span class="pre">m[b1]</span></code>, behaves
like the hash of a bounded data chunk. The <code class="docutils literal notranslate"><span class="pre">--optimstic_hashing</span></code> flag has no
impact on this hash operation.</p>
<p>The behavior of the second hash operation, triggered by the mapping access <code class="docutils literal notranslate"><span class="pre">m[b2]</span></code>,
depends on whether <code class="docutils literal notranslate"><span class="pre">--optimistic_hashing</span></code> is set.</p>
<ul class="simple">
<li><p>If the <code class="docutils literal notranslate"><span class="pre">--optimistic_hashing</span></code> flag is not set, the violation of an internal
assertion will be reported by the Prover, stating that a chunk of data is being
hashed that may exceed the given bound of 224.
The reported message will look like this:</p></li>
</ul>
<div class="highlight-text notranslate"><div class="highlight"><pre id="codecell4"><span></span>Trying to hash a non-constant length array whose length may exceed the bound 
(set in option "--hashing_length_bound", current value is 224). 
Optimistic unbounded hashing is currently deactivated (can be activated via 
option "--optimistic_hashing").
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell4">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<ul class="simple">
<li><p>If the <code class="docutils literal notranslate"><span class="pre">--optimistic_hashing</span></code> flag is set, the Prover will internally make an
assumption (equivalent to a <code class="docutils literal notranslate"><span class="pre">require</span></code> statement) on <code class="docutils literal notranslate"><span class="pre">b2</span></code> stating that its length cannot
exceed 224 bytes.</p></li>
</ul>
<p>The third operation, triggered by the mapping access <code class="docutils literal notranslate"><span class="pre">m[b3]</span></code> behaves like the second,
since no length constraint on <code class="docutils literal notranslate"><span class="pre">b3</span></code> is made by the program.
However, we can see the impact of the <code class="docutils literal notranslate"><span class="pre">--optimistic_hashing</span></code> flag on the <code class="docutils literal notranslate"><span class="pre">assert</span></code>
command that follows the hash operation:
When the flag is set, the assertion will be shown as not violated
even though nothing in the program itself prevents <code class="docutils literal notranslate"><span class="pre">b3</span></code> from being longer than
300 bytes. This is an example of unsoundness coming from “optimistic” assumptions.
(When <code class="docutils literal notranslate"><span class="pre">--optimistic_hashing</span></code> is not set, then we get a violation from any or all
assertions, depending on the configuration of the Certora Prover.)</p>
<section id="examples-for-unbounded-hashing">
<h3>Examples for Unbounded Hashing<a class="headerlink" href="#examples-for-unbounded-hashing" title="Link to this heading"></a></h3>
<p>The following collection snippet illustrates the most common use cases for
hashing of data that has unbounded length.</p>
<div class="highlight-solidity notranslate"><div class="highlight"><pre id="codecell5"><span></span><span class="k">contract</span><span class="w"> </span><span class="ni">C</span><span class="w"> </span><span class="p">{</span>
<span class="w">	</span><span class="kt">mapping</span><span class="p">(</span><span class="kt">bytes</span><span class="w"> </span><span class="o">=&gt;</span><span class="w"> </span><span class="kt">uint</span><span class="p">)</span><span class="w"> </span>m<span class="p">;</span>
<span class="w">	</span><span class="kt">uint</span><span class="w"> </span><span class="nv">x</span><span class="p">,</span><span class="w"> </span>y<span class="p">,</span><span class="w"> </span>z<span class="p">,</span><span class="w"> </span>start<span class="p">,</span><span class="w"> </span>len<span class="p">;</span>
<span class="w">	</span><span class="c1">// ... </span>
<span class="w">		</span>m<span class="p">[</span>b<span class="p">]</span><span class="w"> </span><span class="o">=</span><span class="w"> </span>v
<span class="w">	</span><span class="c1">// ... </span>
<span class="w">		</span><span class="nb">keccak256</span><span class="p">(</span>abi<span class="p">.</span>encode<span class="p">(</span>x<span class="p">,</span><span class="w"> </span>y<span class="p">,</span><span class="w"> </span>z<span class="p">))</span>
<span class="w">	</span><span class="c1">// ... </span>
<span class="w">		</span><span class="nb">keccak256</span><span class="p">(</span>abi<span class="p">.</span>encodePacked<span class="p">(</span>x<span class="p">,</span><span class="w"> </span>y<span class="p">,</span><span class="w"> </span>z<span class="p">))</span>
<span class="w">	</span><span class="c1">// ...</span>
<span class="w">		</span>assembly<span class="w"> </span><span class="p">{</span>
<span class="w">			</span>keccak<span class="p">(</span>start<span class="p">,</span><span class="w"> </span>len<span class="p">)</span>
<span class="w">		</span><span class="p">}</span>
<span class="w">	</span><span class="c1">// ...</span>
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
<p>Probably the most common use case is the use of mappings whose keys are an
unbounded array (<code class="docutils literal notranslate"><span class="pre">bytes</span></code>, <code class="docutils literal notranslate"><span class="pre">string</span></code>, <code class="docutils literal notranslate"><span class="pre">uint[]</span></code>, etc.); any access to such a
mapping induces a hash of the corresponding array whose length is often unknown
and unbounded.</p>
<p>Further use cases include direct calls of the Keccak function, either directly
on Solidity or inside an inline assembly snippet.</p>
<p>Note that the Certora Prover’s static analysis is aware of the ABI encoder. Thus,
in many cases, it can figure out that when <code class="docutils literal notranslate"><span class="pre">x,</span> <span class="pre">y,</span> <span class="pre">z</span></code> are scalars that
<code class="docutils literal notranslate"><span class="pre">keccak256(abi.encode(x,</span> <span class="pre">y,</span> <span class="pre">z))</span></code> is actually a bounded hash of the form
<code class="docutils literal notranslate"><span class="pre">hash(x,</span> <span class="pre">y,</span> <span class="pre">z)</span></code> as opposed to an unbounded hash of the <code class="docutils literal notranslate"><span class="pre">bytes</span></code> array that is the
result of the <code class="docutils literal notranslate"><span class="pre">encode</span></code> function.</p>
</section>
</section>
<section id="background-the-solidity-storage-model">
<span id="id1"></span><h2>Background: The Solidity Storage Model<a class="headerlink" href="#background-the-solidity-storage-model" title="Link to this heading"></a></h2>
<p>In this subsection we illustrate the consequences on storage integrity if the
“injectivity with large gaps” property is not maintained.</p>
<p>For instance consider this contract:</p>
<div class="highlight-solidity notranslate"><div class="highlight"><pre id="codecell6"><span></span><span class="c1">// solidity</span>
<span class="k">contract</span><span class="w"> </span><span class="ni">C</span><span class="w"> </span><span class="p">{</span>
<span class="w">	</span><span class="kt">uint</span><span class="w"> </span><span class="nv">i</span><span class="p">;</span><span class="w">                  </span><span class="c1">// slot 0</span>
<span class="w">	</span><span class="kt">uint</span><span class="p">[]</span><span class="w"> </span>a<span class="p">;</span><span class="w">                </span><span class="c1">// slot 1</span>
<span class="w">	</span><span class="kt">mapping</span><span class="p">(</span><span class="kt">uint</span><span class="w"> </span><span class="o">=&gt;</span><span class="w"> </span><span class="kt">uint</span><span class="p">)</span><span class="w"> </span>m<span class="p">;</span><span class="w"> </span><span class="c1">// slot 2</span>

<span class="w">	</span><span class="cm">/** Always returns writeToArray (unless hashing is broken). */</span>
<span class="w">	</span><span class="kt">function</span><span class="w"> </span><span class="nv">foo</span><span class="p">(</span><span class="kt">uint</span><span class="w"> </span><span class="nv">writeToArray</span><span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span><span class="nv">writeToMap</span><span class="p">)</span><span class="w"> </span><span class="kt">public</span><span class="w"> </span><span class="kt">returns</span><span class="w"> </span><span class="p">(</span><span class="kt">uint</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">		</span>i<span class="w"> </span><span class="o">=</span><span class="w"> </span>u<span class="p">;</span><span class="w">               </span><span class="c1">// sstore(0, u)</span>
<span class="w">   		</span>a<span class="p">[</span>j<span class="p">]</span><span class="w"> </span><span class="o">=</span><span class="w"> </span>writeToArray<span class="p">;</span><span class="w"> </span><span class="c1">// sstore(hash(1) + j, writeToArray)</span>
<span class="w">   		</span>m<span class="p">[</span>k<span class="p">]</span><span class="w"> </span><span class="o">=</span><span class="w"> </span>writeToMap<span class="p">;</span><span class="w">   </span><span class="c1">// sstore(hash(2, k), writeToMap)</span>
<span class="w">		</span><span class="kt">return</span><span class="w"> </span>a<span class="p">[</span>j<span class="p">];</span>
<span class="w">  	</span><span class="p">}</span>
<span class="p">}</span>

<span class="c1">// CVL</span>
methods<span class="w"> </span><span class="p">{</span><span class="w"> </span>foo<span class="p">(</span><span class="kt">uint</span><span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="p">)</span><span class="w"> </span><span class="kt">return</span><span class="w"> </span><span class="p">(</span><span class="kt">uint</span><span class="p">);</span><span class="w"> </span><span class="p">};</span>

rule<span class="w"> </span>storageIntegrity<span class="w"> </span><span class="p">{</span>
<span class="w">	</span><span class="kt">uint</span><span class="w"> </span><span class="nv">writeToArray</span><span class="p">,</span><span class="w"> </span>writeToMap<span class="p">;</span>
<span class="w">	</span><span class="kt">require</span><span class="w"> </span>writeToArray<span class="w"> </span><span class="o">!=</span><span class="w"> </span>writeToMap<span class="p">;</span>

<span class="w">	</span><span class="kt">uint</span><span class="w"> </span><span class="nv">res</span><span class="w"> </span><span class="o">=</span><span class="w"> </span>foo<span class="p">(</span>writeToArray<span class="p">,</span><span class="w"> </span>writeToMap<span class="p">)</span>

<span class="w">	</span>assert<span class="p">(</span>res<span class="w"> </span><span class="o">==</span><span class="w"> </span>writeToArray<span class="p">);</span>
<span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell6">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>The comments of the function <code class="docutils literal notranslate"><span class="pre">foo</span></code> illustrate how storage is laid out by
Solidity.
The occurrences of <code class="docutils literal notranslate"><span class="pre">sstore(x,</span> <span class="pre">y)</span></code> in the line comments above denote a storage
update of storage address <code class="docutils literal notranslate"><span class="pre">x</span></code> to value <code class="docutils literal notranslate"><span class="pre">y</span></code>.
The scalar <code class="docutils literal notranslate"><span class="pre">i</span></code> is stored at storage address <code class="docutils literal notranslate"><span class="pre">0</span></code>, which is derived from its
slot number in the contract (slots are numbered in order of appearance in the
source code).
The array <code class="docutils literal notranslate"><span class="pre">a</span></code> is stored contiguously, starting from slot <code class="docutils literal notranslate"><span class="pre">hash(1)</span></code>.
The entries of mapping <code class="docutils literal notranslate"><span class="pre">m</span></code> are spread out over storage; their locations are
computed as the hash of the mapping’s storage slot and the key at which the
mapping is being accessed; thus the storage slot used for the entry of <code class="docutils literal notranslate"><span class="pre">m</span></code> under
key <code class="docutils literal notranslate"><span class="pre">k</span></code> is computed as <code class="docutils literal notranslate"><span class="pre">hash(2,</span> <span class="pre">k)</span></code>.</p>
<p>We can see that non-collision of hashes is essential for storage integrity.
E.g., if <code class="docutils literal notranslate"><span class="pre">hash(1)</span> <span class="pre">+</span> <span class="pre">j</span></code> was equal to <code class="docutils literal notranslate"><span class="pre">hash(2,</span> <span class="pre">k)</span></code> then the operations on <code class="docutils literal notranslate"><span class="pre">a</span></code> and
<code class="docutils literal notranslate"><span class="pre">m</span></code> would interfere with each other, and <code class="docutils literal notranslate"><span class="pre">foo</span></code> would return the value of
<code class="docutils literal notranslate"><span class="pre">writeToMap</span></code> rather than the value of <code class="docutils literal notranslate"><span class="pre">writeToArray</span></code>.</p>
</section>
<section id="conclusion">
<h2>Conclusion<a class="headerlink" href="#conclusion" title="Link to this heading"></a></h2>
<p>To summarize, the Certora Prover handles hashing in a way that behaves as
expected for most hashes.</p>
<p>However, it is good to be aware of limitations of the modeling; i.e. that not
all properties of the actual Keccak function are preserved but only the ones
that are crucial for practical use cases, which are covered by the “injectivity
with large gaps” property.</p>
<p>Furthermore, special attention may be necessary when hashing of unbounded data
is required. For this case, Certora Prover relies on user-controlled
approximations that are analogous to its handling of loops.</p>
</section>
</section>


           </div>
          </div>
          <footer><div class="rst-footer-buttons" role="navigation" aria-label="Footer">
        <a href="harnessing.html" class="btn btn-neutral float-left" title="Harnessing" accesskey="p" rel="prev"><span class="fa fa-arrow-circle-left" aria-hidden="true"></span> Previous</a>
        <a href="grounding.html" class="btn btn-neutral float-right" title="Quantifier Grounding" accesskey="n" rel="next">Next <span class="fa fa-arrow-circle-right" aria-hidden="true"></span></a>
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