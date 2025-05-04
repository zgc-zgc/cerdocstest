<!DOCTYPE html><html class="writer-html5" lang="en" data-content_root="../../"><head>
  <meta charset="utf-8"><meta name="viewport" content="width=device-width, initial-scale=1">

  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>The Certora Equivalence Checker — Certora Prover Documentation 0.0 documentation</title>
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
    <link rel="next" title="Certora Technology White Paper" href="../whitepaper/index.html">
    <link rel="prev" title="Gambit: Mutant Generation for Solidity" href="../gambit/gambit.html"> 
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
<ul>
<li class="toctree-l1"><a class="reference internal" href="../user-guide/index.html">Certora User’s Guide</a></li>
<li class="toctree-l1"><a class="reference internal" href="../cvl/index.html">The Certora Verification Language</a></li>
<li class="toctree-l1"><a class="reference internal" href="../prover/index.html">The Certora Prover</a></li>
<li class="toctree-l1"><a class="reference internal" href="../sunbeam/index.html">Sunbeam: Verification for Soroban</a></li>
<li class="toctree-l1"><a class="reference internal" href="../solana/index.html">The Certora Solana Prover</a></li>
<li class="toctree-l1"><a class="reference internal" href="../gambit/index.html">Gambit: Mutation Generator for Solidity</a></li>
</ul>
<p class="caption" role="heading"><span class="caption-text">Additional information</span></p>
<ul class="current" aria-expanded="true">
<li class="toctree-l1 current" aria-expanded="true"><a class="reference internal current" href="#" aria-expanded="true"><button class="toctree-expand" title="Open/close menu"></button>The Certora Equivalence Checker</a><ul>
<li class="toctree-l2"><a class="reference internal" href="#installation">Installation</a></li>
<li class="toctree-l2"><a class="reference internal" href="#example">Example</a></li>
<li class="toctree-l2"><a class="reference internal" href="#usage"><button class="toctree-expand" title="Open/close menu"></button>Usage</a><ul>
<li class="toctree-l3"><a class="reference internal" href="#default-mode">Default mode</a></li>
<li class="toctree-l3"><a class="reference internal" href="#configuration-mode">Configuration mode</a></li>
</ul>
</li>
</ul>
</li>
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
      <li class="breadcrumb-item active">The Certora Equivalence Checker</li>
      <li class="wy-breadcrumbs-aside">
            <a href="../../_sources/docs/equiv-check/index.md.txt" rel="nofollow"> View page source</a>
      </li>
  </ul>
  <hr>
</div>
          <div role="main" class="document" itemscope="itemscope" itemtype="http://schema.org/Article">
           <div itemprop="articleBody">
             
  <section id="the-certora-equivalence-checker">
<span id="equivcheck-intro"></span><h1>The Certora Equivalence Checker<a class="headerlink" href="#the-certora-equivalence-checker" title="Link to this heading"></a></h1>
<p>This chapter describes how one can use the Certora Prover to
check the equivalence of two smart contract functions.</p>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>Currently the equivalence checker only compares two <code class="docutils literal notranslate"><span class="pre">pure</span></code> functions,
but we are actively working to develop an
equivalence checker for non-<code class="docutils literal notranslate"><span class="pre">pure</span></code> functions as well.</p>
</div>
<p>The equivalence checker front-end automatically generates (1) a
CVL spec to check if two functions are equivalent, and, (2) a
configuration file (<code class="docutils literal notranslate"><span class="pre">.conf</span></code>) for running the Certora Prover.</p>
<section id="installation">
<h2>Installation<a class="headerlink" href="#installation" title="Link to this heading"></a></h2>
<p>The equivalence checker is part of the <code class="docutils literal notranslate"><span class="pre">certora-cli</span></code> package; see <a class="reference internal" href="../user-guide/install.html#installation"><span class="std std-ref">Installation</span></a>.</p>
</section>
<section id="example">
<span id="equivalence-checker-example"></span><h2>Example<a class="headerlink" href="#example" title="Link to this heading"></a></h2>
<p>Consider two contracts, <code class="docutils literal notranslate"><span class="pre">BasicMathGood.sol</span></code> and <code class="docutils literal notranslate"><span class="pre">BasicMathBad.sol</span></code> shown
below with two functions, <code class="docutils literal notranslate"><span class="pre">add</span></code> and <code class="docutils literal notranslate"><span class="pre">add_mult</span></code>.</p>
<div class="highlight-solidity notranslate"><div class="highlight"><pre id="codecell0"><span></span><span class="k">contract</span><span class="w"> </span><span class="ni">BasicMathGood</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kt">function</span><span class="w"> </span><span class="nv">add</span><span class="p">(</span><span class="kt">uint256</span><span class="w"> </span><span class="nv">a</span><span class="p">,</span><span class="w"> </span><span class="kt">uint256</span><span class="w"> </span><span class="nv">b</span><span class="p">)</span><span class="w"> </span><span class="kt">public</span><span class="w"> </span>pure<span class="w"> </span><span class="kt">returns</span><span class="p">(</span><span class="kt">uint256</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">        </span><span class="kt">return</span><span class="w"> </span>a<span class="w"> </span><span class="o">+</span><span class="w"> </span>b<span class="p">;</span>
<span class="w">    </span><span class="p">}</span>
<span class="p">}</span>

<span class="k">contract</span><span class="w"> </span><span class="ni">BasicMathBad</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kt">function</span><span class="w"> </span><span class="nv">add_uncheck</span><span class="p">(</span><span class="kt">uint256</span><span class="w"> </span><span class="nv">a</span><span class="p">,</span><span class="w"> </span><span class="kt">uint256</span><span class="w"> </span><span class="nv">b</span><span class="p">)</span><span class="w"> </span><span class="kt">public</span><span class="w"> </span>pure<span class="w"> </span><span class="kt">returns</span><span class="p">(</span><span class="kt">uint256</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">        </span>unchecked<span class="w"> </span><span class="p">{</span>
<span class="w">            </span><span class="kt">return</span><span class="w"> </span>a<span class="w"> </span><span class="o">*</span><span class="w"> </span>b<span class="p">;</span>
<span class="w">        </span><span class="p">}</span>
<span class="w">    </span><span class="p">}</span>
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
<p>We are interested in checking the equivalence of <code class="docutils literal notranslate"><span class="pre">add</span></code> and <code class="docutils literal notranslate"><span class="pre">add_uncheck</span></code>.
While this is a simple case,
you can imagine scenarios where
the functions are more complex.
Equivalence checking can be used to check whether two functions that
may be implemented differently, are still semantically equivalent.
The following sections describe how to use the tool.</p>
</section>
<section id="usage">
<h2>Usage<a class="headerlink" href="#usage" title="Link to this heading"></a></h2>
<p><code class="docutils literal notranslate"><span class="pre">certoraEqCheck</span></code> can be run either in default (<code class="docutils literal notranslate"><span class="pre">def</span></code>) mode,
in which the user must supply all the required information as
command line arguments (see below),
or in a <code class="docutils literal notranslate"><span class="pre">conf</span></code> mode where the user supplies a
Certora Prover <code class="docutils literal notranslate"><span class="pre">conf</span></code> file along with additional arguments.</p>
<section id="default-mode">
<h3>Default mode<a class="headerlink" href="#default-mode" title="Link to this heading"></a></h3>
<p>To run the equivalence checker in default mode,
use <code class="docutils literal notranslate"><span class="pre">certoraEqCheck</span></code>:</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell1"><span></span>certoraEqCheck<span class="w"> </span>def<span class="w"> </span><span class="s2">"path_to_file:contract:function:solc"</span><span class="w"> </span><span class="s2">"path_to_file:contract:function:solc"</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell1">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>For the functions in <a class="reference internal" href="#equivalence-checker-example"><span class="std std-ref">Example</span></a>, this would look as follows:</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell2"><span></span>certoraEqCheck<span class="w"> </span>def<span class="w"> </span>Test/EqCheck/BasicMathGood.sol:add:solc8.0<span class="w"> </span>Test/EqCheck/BasicMathBad.sol:add_pass:solc8.0
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell2">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>In the above example, <code class="docutils literal notranslate"><span class="pre">solc</span></code> is the name of the executable
for the Solidity compiler version you are using.
The Solidity compilers do not need to be the same for both arguments to
<code class="docutils literal notranslate"><span class="pre">certoraEqCheck</span></code>, it only need to be appropriate for the given contract.
Also note how
the contract field can be omitted if the contract name is the same
the file name.</p>
</section>
<section id="configuration-mode">
<h3>Configuration mode<a class="headerlink" href="#configuration-mode" title="Link to this heading"></a></h3>
<p>To run the equivalence checker in the configuration mode,
use <code class="docutils literal notranslate"><span class="pre">certoraEqCheck</span></code> as follows:</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell3"><span></span>certoraEqCheck<span class="w"> </span>conf<span class="w"> </span>&lt;path_to_conf&gt;.conf<span class="w"> </span>contract:function<span class="w"> </span>contract:function
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell3">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>For the functions in <a class="reference internal" href="#equivalence-checker-example"><span class="std std-ref">Example</span></a>, this would be:</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell4"><span></span><span class="w">   </span>certoraEqCheck<span class="w"> </span>conf<span class="w"> </span>Test/EqCheck/testGood.conf<span class="w"> </span>BasicMathGood:add<span class="w"> </span>BasicMathBad:add_mult
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell4">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>where <code class="docutils literal notranslate"><span class="pre">testGood.conf</span></code> is the standard Certora configuration file
and contains:</p>
<div class="highlight-json notranslate"><div class="highlight"><pre id="codecell5"><span></span><span class="p">{</span>
<span class="w">    </span><span class="nt">"disable_local_typechecking"</span><span class="p">:</span><span class="w"> </span><span class="kc">true</span><span class="p">,</span>
<span class="w">    </span><span class="nt">"files"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="s2">"BasicMathGood.sol"</span><span class="p">,</span><span class="w"> </span><span class="s2">"BasicMathBad.sol"</span><span class="p">],</span>
<span class="w">    </span><span class="nt">"msg"</span><span class="p">:</span><span class="w"> </span><span class="s2">"Equivalence Check"</span><span class="p">,</span>
<span class="w">    </span><span class="nt">"optimistic_loop"</span><span class="p">:</span><span class="w"> </span><span class="kc">true</span><span class="p">,</span>
<span class="w">    </span><span class="nt">"loop_iter"</span><span class="p">:</span><span class="w"> </span><span class="s2">"4"</span><span class="p">,</span>
<span class="w">    </span><span class="nt">"process"</span><span class="p">:</span><span class="w"> </span><span class="s2">"emv"</span><span class="p">,</span>
<span class="w">    </span><span class="nt">"send_only"</span><span class="p">:</span><span class="w"> </span><span class="kc">true</span><span class="p">,</span>
<span class="w">    </span><span class="nt">"short_output"</span><span class="p">:</span><span class="w"> </span><span class="kc">true</span><span class="p">,</span>
<span class="w">    </span><span class="nt">"rule_sanity"</span><span class="p">:</span><span class="w"> </span><span class="s2">"basic"</span><span class="p">,</span>
<span class="w">    </span><span class="nt">"solc"</span><span class="p">:</span><span class="w"> </span><span class="s2">"solc8.0"</span><span class="p">,</span>
<span class="w">    </span><span class="nt">"solc_optimize"</span><span class="p">:</span><span class="w"> </span><span class="s2">"200"</span><span class="p">,</span>
<span class="w">    </span><span class="nt">"server"</span><span class="p">:</span><span class="w"> </span><span class="s2">"staging"</span><span class="p">,</span>
<span class="w">    </span><span class="nt">"prover_version"</span><span class="p">:</span><span class="w"> </span><span class="s2">"master"</span>
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
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>Use <a class="reference internal" href="../prover/cli/options.html#precise-bitwise-ops"><span class="std std-ref">precise_bitwise_ops</span></a> if you are comparing functions with bitwise operations.
This will slow down the tool slightly,
but ensure that the results are sound.</p>
</div>
<p><code class="docutils literal notranslate"><span class="pre">certoraEqCheck</span></code> produces two files that are then used to run the
Certora Prover automatically.
The first one is a CVL specification file, whose content
in the case of the example shown here is:</p>
<div class="highlight-default notranslate"><div class="highlight"><pre id="codecell6"><span></span>  <span class="n">using</span> <span class="n">BasicMathBad</span> <span class="k">as</span> <span class="n">B</span><span class="p">;</span>

<span class="o">//</span> <span class="n">sets</span> <span class="n">everything</span> <span class="n">but</span> <span class="n">the</span> <span class="n">callee</span> <span class="n">the</span> <span class="n">same</span> <span class="ow">in</span> <span class="n">two</span> <span class="n">environments</span>
<span class="n">function</span> <span class="n">e_equivalence</span><span class="p">(</span><span class="n">env</span> <span class="n">e1</span><span class="p">,</span> <span class="n">env</span> <span class="n">e2</span><span class="p">)</span> <span class="p">{</span>
    <span class="n">require</span> <span class="n">e1</span><span class="o">.</span><span class="n">msg</span><span class="o">.</span><span class="n">sender</span> <span class="o">==</span> <span class="n">e2</span><span class="o">.</span><span class="n">msg</span><span class="o">.</span><span class="n">sender</span><span class="p">;</span>
    <span class="n">require</span> <span class="n">e1</span><span class="o">.</span><span class="n">block</span><span class="o">.</span><span class="n">timestamp</span> <span class="o">==</span> <span class="n">e2</span><span class="o">.</span><span class="n">block</span><span class="o">.</span><span class="n">timestamp</span><span class="p">;</span>
    <span class="n">require</span> <span class="n">e1</span><span class="o">.</span><span class="n">msg</span><span class="o">.</span><span class="n">value</span> <span class="o">==</span> <span class="n">e2</span><span class="o">.</span><span class="n">msg</span><span class="o">.</span><span class="n">value</span><span class="p">;</span>
    <span class="o">//</span> <span class="n">require</span> <span class="n">e1</span><span class="o">.</span><span class="n">msg</span><span class="o">.</span><span class="n">data</span> <span class="o">==</span> <span class="n">e2</span><span class="o">.</span><span class="n">msg</span><span class="o">.</span><span class="n">data</span><span class="p">;</span>
<span class="p">}</span>

<span class="n">rule</span> <span class="n">equivalence_of_revert_conditions</span><span class="p">()</span>
<span class="p">{</span>
    <span class="nb">bool</span> <span class="n">add_revert</span><span class="p">;</span>
    <span class="nb">bool</span> <span class="n">add_mult_revert</span><span class="p">;</span>
    <span class="o">//</span> <span class="n">using</span> <span class="n">this</span> <span class="k">as</span> <span class="n">opposed</span> <span class="n">to</span> <span class="n">generating</span> <span class="nb">input</span> <span class="n">parameters</span> <span class="ow">is</span> <span class="n">experimental</span>
    <span class="n">env</span> <span class="n">e_add</span><span class="p">;</span> <span class="n">calldataarg</span> <span class="n">args</span><span class="p">;</span>
    <span class="n">env</span> <span class="n">e_add_mult</span><span class="p">;</span>
    <span class="n">e_equivalence</span><span class="p">(</span><span class="n">e_add</span><span class="p">,</span> <span class="n">e_add_mult</span><span class="p">);</span>

    <span class="n">add</span><span class="nd">@withrevert</span><span class="p">(</span><span class="n">e_add</span><span class="p">,</span> <span class="n">args</span><span class="p">);</span>
    <span class="n">add_revert</span> <span class="o">=</span> <span class="n">lastReverted</span><span class="p">;</span>

    <span class="n">B</span><span class="o">.</span><span class="n">add_mult</span><span class="nd">@withrevert</span><span class="p">(</span><span class="n">e_add_mult</span><span class="p">,</span> <span class="n">args</span><span class="p">);</span>
    <span class="n">add_mult_revert</span> <span class="o">=</span> <span class="n">lastReverted</span><span class="p">;</span>

    <span class="k">assert</span><span class="p">(</span><span class="n">add_revert</span> <span class="o">==</span> <span class="n">add_mult_revert</span><span class="p">);</span>
<span class="p">}</span>

<span class="n">rule</span> <span class="n">equivalence_of_return_value</span><span class="p">()</span>
<span class="p">{</span>
    <span class="n">uint256</span> <span class="n">add_uint256_out0</span><span class="p">;</span>
    <span class="n">uint256</span> <span class="n">add_mult_uint256_out0</span><span class="p">;</span>

    <span class="n">env</span> <span class="n">e_add</span><span class="p">;</span> <span class="n">calldataarg</span> <span class="n">args</span><span class="p">;</span>
    <span class="n">env</span> <span class="n">e_add_mult</span><span class="p">;</span>

    <span class="n">e_equivalence</span><span class="p">(</span><span class="n">e_add</span><span class="p">,</span> <span class="n">e_add_mult</span><span class="p">);</span>

    <span class="n">add_uint256_out0</span> <span class="o">=</span> <span class="n">add</span><span class="p">(</span><span class="n">e_add</span><span class="p">,</span> <span class="n">args</span><span class="p">);</span>
    <span class="n">add_mult_uint256_out0</span> <span class="o">=</span> <span class="n">B</span><span class="o">.</span><span class="n">add_mult</span><span class="p">(</span><span class="n">e_add_mult</span><span class="p">,</span> <span class="n">args</span><span class="p">);</span>

    <span class="k">assert</span><span class="p">(</span><span class="n">add_uint256_out0</span> <span class="o">==</span> <span class="n">add_mult_uint256_out0</span><span class="p">);</span>
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
<p>The second one is a standard Certora <code class="docutils literal notranslate"><span class="pre">conf</span></code> file:</p>
<div class="highlight-default notranslate"><div class="highlight"><pre id="codecell7"><span></span><span class="p">{</span>
    <span class="s2">"disable_local_typechecking"</span><span class="p">:</span> <span class="n">true</span><span class="p">,</span>
    <span class="s2">"files"</span><span class="p">:</span> <span class="p">[</span>
        <span class="s2">"Test/EqCheck/BasicMathGood.sol"</span><span class="p">,</span>
        <span class="s2">"Test/EqCheck/BasicMathBad.sol"</span>
    <span class="p">],</span>
    <span class="s2">"msg"</span><span class="p">:</span> <span class="s2">"EquivalenceCheck of add and add_mult"</span><span class="p">,</span>
    <span class="s2">"optimistic_loop"</span><span class="p">:</span> <span class="n">true</span><span class="p">,</span>
    <span class="s2">"loop_iter"</span><span class="p">:</span> <span class="s2">"4"</span><span class="p">,</span>
    <span class="s2">"process"</span><span class="p">:</span> <span class="s2">"emv"</span><span class="p">,</span>
    <span class="s2">"send_only"</span><span class="p">:</span> <span class="n">true</span><span class="p">,</span>
    <span class="s2">"short_output"</span><span class="p">:</span> <span class="n">true</span><span class="p">,</span>
    <span class="s2">"rule_sanity"</span><span class="p">:</span> <span class="s2">"basic"</span><span class="p">,</span>
    <span class="s2">"server"</span><span class="p">:</span> <span class="s2">"staging"</span><span class="p">,</span>
    <span class="s2">"prover_version"</span><span class="p">:</span> <span class="s2">"master"</span><span class="p">,</span>
    <span class="s2">"solc_optimize"</span><span class="p">:</span> <span class="s2">"200"</span><span class="p">,</span>
    <span class="s2">"verify"</span><span class="p">:</span> <span class="s2">"BasicMathGood:Test/EqCheck/add_to_add_mult_equivalence.spec"</span><span class="p">,</span>
    <span class="s2">"solc"</span><span class="p">:</span> <span class="s2">"solc8.0"</span>
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
<p>The script then invokes the Certora Prover using this <code class="docutils literal notranslate"><span class="pre">conf</span></code> file.</p>
</section>
</section>
</section>


           </div>
          </div>
          <footer><div class="rst-footer-buttons" role="navigation" aria-label="Footer">
        <a href="../gambit/gambit.html" class="btn btn-neutral float-left" title="Gambit: Mutant Generation for Solidity" accesskey="p" rel="prev"><span class="fa fa-arrow-circle-left" aria-hidden="true"></span> Previous</a>
        <a href="../whitepaper/index.html" class="btn btn-neutral float-right" title="Certora Technology White Paper" accesskey="n" rel="next">Next <span class="fa fa-arrow-circle-right" aria-hidden="true"></span></a>
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