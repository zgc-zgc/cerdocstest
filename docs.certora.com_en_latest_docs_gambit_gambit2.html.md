<!DOCTYPE html><html class="writer-html5" lang="en" data-content_root="../../"><head>
  <meta charset="utf-8"><meta name="viewport" content="width=device-width, initial-scale=1">

  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Gambit: Mutant Generation for Solidity — Certora Prover Documentation 0.0 documentation</title>
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
    <link rel="next" title="The Certora Equivalence Checker" href="../equiv-check/index.html">
    <link rel="prev" title="Using Gambit with the Prover" href="mutation-verifier.html"> 
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
<li class="toctree-l1"><a class="reference internal" href="../solana/index.html">The Certora Solana Prover</a></li>
<li class="toctree-l1 current" aria-expanded="true"><a class="reference internal" href="index.html"><button class="toctree-expand" title="Open/close menu"></button>Gambit: Mutation Generator for Solidity</a><ul class="" aria-expanded="false">
<li class="toctree-l2"><a class="reference internal" href="mutation-verifier.html">Using Gambit with the Prover</a></li>
<li class="toctree-l2 current" aria-expanded="true"><a class="reference internal current" href="#" aria-expanded="true"><button class="toctree-expand" title="Open/close menu"></button>Gambit: Mutant Generation for Solidity</a><ul>
<li class="toctree-l3"><a class="reference internal" href="#requirements">Requirements</a></li>
<li class="toctree-l3"><a class="reference internal" href="#installation"><button class="toctree-expand" title="Open/close menu"></button>Installation</a><ul>
<li class="toctree-l4"><a class="reference internal" href="#building-gambit-from-source">Building Gambit from source</a></li>
</ul>
</li>
<li class="toctree-l3"><a class="reference internal" href="#usage"><button class="toctree-expand" title="Open/close menu"></button>Usage</a><ul>
<li class="toctree-l4"><a class="reference internal" href="#running-gambit-mutate">Running  <code class="docutils literal notranslate"><span class="pre">gambit</span> <span class="pre">mutate</span></code></a></li>
</ul>
</li>
<li class="toctree-l3"><a class="reference internal" href="#examples"><button class="toctree-expand" title="Open/close menu"></button>Examples</a><ul>
<li class="toctree-l4"><a class="reference internal" href="#example-1-mutating-a-single-file">Example 1: Mutating a single file</a></li>
<li class="toctree-l4"><a class="reference internal" href="#example-2-mutating-and-downsampling">Example 2: Mutating and downsampling</a></li>
<li class="toctree-l4"><a class="reference internal" href="#example-3-viewing-gambit-results">Example 3: Viewing Gambit results</a></li>
<li class="toctree-l4"><a class="reference internal" href="#example-4-specifying-solc-pass-through-arguments">Example 4: Specifying <code class="docutils literal notranslate"><span class="pre">solc</span></code> pass-through arguments</a></li>
<li class="toctree-l4"><a class="reference internal" href="#example-5-the-sourceroot-option">Example 5: The <code class="docutils literal notranslate"><span class="pre">--sourceroot</span></code> option</a></li>
<li class="toctree-l4"><a class="reference internal" href="#example-6-running-gambit-using-a-configuration-file">Example 6: Running Gambit using a configuration file</a></li>
</ul>
</li>
<li class="toctree-l3"><a class="reference internal" href="#configuration-files"><button class="toctree-expand" title="Open/close menu"></button>Configuration Files</a><ul>
<li class="toctree-l4"><a class="reference internal" href="#paths-in-configuration-files">Paths in Configuration Files</a></li>
</ul>
</li>
<li class="toctree-l3"><a class="reference internal" href="#results-directory">Results Directory</a></li>
<li class="toctree-l3"><a class="reference internal" href="#cli-options">CLI Options</a></li>
<li class="toctree-l3"><a class="reference internal" href="#mutation-operators">Mutation Operators</a></li>
</ul>
</li>
</ul>
</li>
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
          <li class="breadcrumb-item"><a href="index.html">Gambit: Mutation Generator for Solidity</a></li>
      <li class="breadcrumb-item active">Gambit: Mutant Generation for Solidity</li>
      <li class="wy-breadcrumbs-aside">
            <a href="../../_sources/docs/gambit/gambit.md.txt" rel="nofollow"> View page source</a>
      </li>
  </ul>
  <hr>
</div>
          <div role="main" class="document" itemscope="itemscope" itemtype="http://schema.org/Article">
           <div itemprop="articleBody">
             
  <section id="gambit-mutant-generation-for-solidity">
<h1>Gambit: Mutant Generation for Solidity<a class="headerlink" href="#gambit-mutant-generation-for-solidity" title="Link to this heading"></a></h1>
<!--
  WARNING: AUTO_GENERATED DOCUMENTATION

  The following documentation is automatlically generated from the Gambit
  README.md located at https://github.com/Certora/Gambit/README.md. Please view
  this document for instructions on producing this file.
-->
<p>Gambit is a state-of-the-art mutation system for Solidity.
By applying predefined syntax transformations called <em>mutation operators</em> (for
example, convert <code class="docutils literal notranslate"><span class="pre">a</span> <span class="pre">+</span> <span class="pre">b</span></code> to <code class="docutils literal notranslate"><span class="pre">a</span> <span class="pre">-</span> <span class="pre">b</span></code>) to a Solidity program’s source code, Gambit
generates variants of the program called <em>mutants</em>.
Mutants can be used to evaluate test suites or specs used for formal
verification: each mutant represents a potential bug in the program, and
stronger test suites and specifications should detect more mutants.</p>
<section id="requirements">
<h2>Requirements<a class="headerlink" href="#requirements" title="Link to this heading"></a></h2>
<ol class="arabic simple">
<li><p>Gambit is written in Rust. You’ll need to <a class="reference external" href="https://www.rust-lang.org/tools/install">install Rust and
Cargo</a> to build Gambit.</p></li>
<li><p>Gambit uses <code class="docutils literal notranslate"><span class="pre">solc</span></code>, the Solidity compiler, to generate mutants. You’ll need
to have a <code class="docutils literal notranslate"><span class="pre">solc</span></code> binary that is compatible with the project you are mutating (see
the <code class="docutils literal notranslate"><span class="pre">--solc</span></code> option in <code class="docutils literal notranslate"><span class="pre">gambit</span> <span class="pre">mutate</span> <span class="pre">--help</span></code>)</p></li>
</ol>
</section>
<section id="installation">
<h2>Installation<a class="headerlink" href="#installation" title="Link to this heading"></a></h2>
<p>You can download prebuilt Gambit binaries for Linux x86-64 and Mac from our
<a class="reference external" href="https://github.com/Certora/gambit/releases">releases</a> page. For Windows and Linux ARM, you must build Gambit from source.</p>
<section id="building-gambit-from-source">
<span id="build-gambit-from-source"></span><h3>Building Gambit from source<a class="headerlink" href="#building-gambit-from-source" title="Link to this heading"></a></h3>
<p>To build Gambit from source, clone <a class="reference external" href="https://github.com/Certora/gambit">the Gambit repository</a> and run</p>
<div class="highlight-default notranslate"><div class="highlight"><pre id="codecell0"><span></span><span class="n">cargo</span> <span class="n">install</span> <span class="o">--</span><span class="n">path</span> <span class="o">.</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell0">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>from this repository’s root. This will build Gambit and install it to a globally visible
location on your <code class="docutils literal notranslate"><span class="pre">PATH</span></code>.</p>
<p>You can also build gambit with <code class="docutils literal notranslate"><span class="pre">cargo</span> <span class="pre">build</span> <span class="pre">--release</span></code> from the root of this
repository.  This will create a <code class="docutils literal notranslate"><span class="pre">gambit</span></code> binary in <code class="docutils literal notranslate"><span class="pre">gambit/target/release/</span></code>
which you can manually place on your path or invoke directly (e.g., by calling
<code class="docutils literal notranslate"><span class="pre">path/to/gambit/target/release/gambit</span></code>).</p>
</section>
</section>
<section id="usage">
<h2>Usage<a class="headerlink" href="#usage" title="Link to this heading"></a></h2>
<p>Gambit has two main commands: <code class="docutils literal notranslate"><span class="pre">mutate</span></code> and <code class="docutils literal notranslate"><span class="pre">summary</span></code>. <code class="docutils literal notranslate"><span class="pre">gambit</span> <span class="pre">mutate</span></code> is
responsible for mutating code, and <code class="docutils literal notranslate"><span class="pre">gambit</span> <span class="pre">summary</span></code> is a convenience command for
summarizing generated mutants in a human-readable way.</p>
<p>Running <code class="docutils literal notranslate"><span class="pre">gambit</span> <span class="pre">mutate</span></code> will invoke <code class="docutils literal notranslate"><span class="pre">solc</span></code>, so make
sure it is visible on your <code class="docutils literal notranslate"><span class="pre">PATH</span></code>. Alternatively, you can specify where Gambit can
find the Solidity compiler with the option <code class="docutils literal notranslate"><span class="pre">--solc</span> <span class="pre">path/to/solc</span></code>, or specify a
<code class="docutils literal notranslate"><span class="pre">solc</span></code> binary (e.g., <code class="docutils literal notranslate"><span class="pre">solc8.12</span></code>) with the option <code class="docutils literal notranslate"><span class="pre">--solc</span> <span class="pre">solc8.12</span></code>.</p>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>All tests (<code class="docutils literal notranslate"><span class="pre">cargo</span> <span class="pre">test</span></code>) are currently run using <code class="docutils literal notranslate"><span class="pre">solc8.13</span></code>. Your tests may fail
if your <code class="docutils literal notranslate"><span class="pre">solc</span></code> points at a different version of the compiler.</p>
</div>
<section id="running-gambit-mutate">
<h3>Running  <code class="docutils literal notranslate"><span class="pre">gambit</span> <span class="pre">mutate</span></code><a class="headerlink" href="#running-gambit-mutate" title="Link to this heading"></a></h3>
<p>The <code class="docutils literal notranslate"><span class="pre">gambit</span> <span class="pre">mutate</span></code> command expects either a <code class="docutils literal notranslate"><span class="pre">--filename</span></code> argument or a <code class="docutils literal notranslate"><span class="pre">--json</span></code>
argument.  Using <code class="docutils literal notranslate"><span class="pre">--filename</span></code> allows you to specify a specific Solidity file to
mutate:</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell1"><span></span>gambit<span class="w"> </span>mutate<span class="w"> </span>--filename<span class="w"> </span>file.sol
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell1">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>However, if you want to mutate multiple files or apply a more complex set of
parameters, we recommend using a configuration file via the <code class="docutils literal notranslate"><span class="pre">--json</span></code> option
instead:</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell2"><span></span>gambit<span class="w"> </span>mutate<span class="w"> </span>--json<span class="w"> </span>gambit_conf.json
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell2">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>Run <code class="docutils literal notranslate"><span class="pre">gambit</span> <span class="pre">--help</span></code> for more information.</p>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>All relative paths specified in a JSON configuration file are interpreted
to be relative to the configuration file’s parent directory.</p>
</div>
<p>In the following section we provide examples of how to run Gambit using both
<code class="docutils literal notranslate"><span class="pre">--filename</span></code> and <code class="docutils literal notranslate"><span class="pre">--json</span></code>. We provide more complete documentation in the
<a class="reference internal" href="#configuration-files"><span class="std std-ref">Configuration Files</span></a> and <a class="reference internal" href="#cli-options"><span class="std std-ref">CLI Options</span></a> sections below.</p>
</section>
</section>
<section id="examples">
<h2>Examples<a class="headerlink" href="#examples" title="Link to this heading"></a></h2>
<p>Unless otherwise noted, examples use code from <a class="reference external" href="https://github.com/Certora/gambit/tree/master/benchmarks">benchmarks/</a>
and are run from the root of the <a class="reference external" href="https://github.com/Certora/gambit">Gambit repository</a>.</p>
<section id="example-1-mutating-a-single-file">
<h3>Example 1: Mutating a single file<a class="headerlink" href="#example-1-mutating-a-single-file" title="Link to this heading"></a></h3>
<p>To mutate a single file, use the <code class="docutils literal notranslate"><span class="pre">--filename</span></code> option (or <code class="docutils literal notranslate"><span class="pre">-f</span></code>), followed by the
file to mutate.</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell3"><span></span>gambit<span class="w"> </span>mutate<span class="w"> </span>-f<span class="w"> </span>benchmarks/BinaryOpMutation/BinaryOpMutation.sol
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell3">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>This will generate:</p>
<div class="highlight-default notranslate"><div class="highlight"><pre id="codecell4"><span></span><span class="n">Generated</span> <span class="mi">34</span> <span class="n">mutants</span> <span class="ow">in</span> <span class="mf">0.69</span> <span class="n">seconds</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell4">
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
<p>The mutated file must be located within your current working directory or
one of its subdirectories. If you want to mutate code in an arbitrary directory,
use the <code class="docutils literal notranslate"><span class="pre">--sourceroot</span></code> option.</p>
</div>
</section>
<section id="example-2-mutating-and-downsampling">
<h3>Example 2: Mutating and downsampling<a class="headerlink" href="#example-2-mutating-and-downsampling" title="Link to this heading"></a></h3>
<p>The above command produced 34 mutants which may be more than you need. Gambit
provides a way to randomly downsample the number of mutants with the
<code class="docutils literal notranslate"><span class="pre">--num_mutants</span></code> or <code class="docutils literal notranslate"><span class="pre">-n</span></code> option:</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell5"><span></span>gambit<span class="w"> </span>mutate<span class="w"> </span>-f<span class="w"> </span>benchmarks/BinaryOpMutation/BinaryOpMutation.sol<span class="w"> </span>-n<span class="w"> </span><span class="m">3</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell5">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>which will generate:</p>
<div class="highlight-default notranslate"><div class="highlight"><pre id="codecell6"><span></span><span class="n">Generated</span> <span class="mi">3</span> <span class="n">mutants</span> <span class="ow">in</span> <span class="mf">0.15</span> <span class="n">seconds</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell6">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
<section id="example-3-viewing-gambit-results">
<h3>Example 3: Viewing Gambit results<a class="headerlink" href="#example-3-viewing-gambit-results" title="Link to this heading"></a></h3>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>This example assumes you’ve just completed Example 2.</p>
</div>
<p>Gambit outputs all of its results in <code class="docutils literal notranslate"><span class="pre">gambit_out</span></code>:</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell7"><span></span>tree<span class="w"> </span>-L<span class="w"> </span><span class="m">2</span><span class="w"> </span>gambit_out
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell7">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>This produces:</p>
<div class="highlight-default notranslate"><div class="highlight"><pre id="codecell8"><span></span>gambit_out
├── gambit_results.json
├── input_json
│&nbsp;&nbsp; ├── BinaryOpMutation.sol_json.ast
│&nbsp;&nbsp; └── BinaryOpMutation.sol_json.ast.json
├── mutants
│&nbsp;&nbsp; ├── 1
│&nbsp;&nbsp; ├── 2
│&nbsp;&nbsp; └── 3
└── mutants.log
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell8">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>See the <a class="reference internal" href="#results-directory"><span class="std std-ref">Results Directory</span></a> section for a detailed
explanation of this layout. The <code class="docutils literal notranslate"><span class="pre">gambit</span> <span class="pre">summary</span></code> command
pretty prints each mutant for easy inspection:</p>
<p><img alt="The output of " src="../../_images/gambit-summary.png" width="1200" height="662"></p>
<p>By default <code class="docutils literal notranslate"><span class="pre">gambit</span> <span class="pre">summary</span></code> prints info on all mutants. If you are interested in
particular mutants you can specify a subset of mutant ids with the <code class="docutils literal notranslate"><span class="pre">--mids</span></code> flag.
For instance, <code class="docutils literal notranslate"><span class="pre">gambit</span> <span class="pre">summary</span> <span class="pre">--mids</span> <span class="pre">3</span> <span class="pre">4</span> <span class="pre">5</span></code>  will only print info for mutant ids
3 through 5.</p>
</section>
<section id="example-4-specifying-solc-pass-through-arguments">
<h3>Example 4: Specifying <code class="docutils literal notranslate"><span class="pre">solc</span></code> pass-through arguments<a class="headerlink" href="#example-4-specifying-solc-pass-through-arguments" title="Link to this heading"></a></h3>
<p>The Solidity compiler (<code class="docutils literal notranslate"><span class="pre">solc</span></code>) may need some extra information to successfully
run on a file or a project.  Gambit enables this with <em>pass-through arguments</em>
that, as the name suggests, are passed directly through to the <code class="docutils literal notranslate"><span class="pre">solc</span></code> compiler.</p>
<p>For projects that have complex dependencies and imports, you may need to:</p>
<ul>
<li><p><strong>Specify base paths</strong>: To specify the Solidity <a class="reference external" href="https://docs.soliditylang.org/en/v0.8.17/path-resolution.html#base-path-and-include-paths"><code class="docutils literal notranslate"><span class="pre">--base-path</span></code></a>
argument, use <code class="docutils literal notranslate"><span class="pre">--solc_base_path</span></code>:</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell9"><span></span>gambit<span class="w"> </span>mutate<span class="w"> </span>--filename<span class="w"> </span>path/to/file.sol<span class="w"> </span>--solc_base_path<span class="w"> </span>base/path/dir
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell9">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</li>
<li><p><strong>Specify remappings:</strong> To indicate where Solidity should find libraries,
use <code class="docutils literal notranslate"><span class="pre">solc</span></code>’s <a class="reference external" href="https://docs.soliditylang.org/en/v0.8.17/path-resolution.html#import-remapping">import remapping</a> syntax with <code class="docutils literal notranslate"><span class="pre">--solc_remappings</span></code>:</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell10"><span></span>gambit<span class="w"> </span>mutate<span class="w"> </span>--filename<span class="w"> </span>path/to/file.sol<span class="w"> </span><span class="se">\</span>
<span class="w">  </span>--solc_remappings<span class="w"> </span>@openzeppelin<span class="o">=</span>node_modules/@openzeppelin<span class="w"> </span>@foo<span class="o">=</span>node_modules/@foo
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell10">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<div class="admonition warning">
<p class="admonition-title">Warning</p>
<p>The paths should <em><strong>NOT</strong></em> end with a trailing /</p>
</div>
</li>
<li><p><strong>Specify allow paths:</strong> To include additional allowed paths via <code class="docutils literal notranslate"><span class="pre">solc</span></code>’s
<a class="reference external" href="https://docs.soliditylang.org/en/v0.8.17/path-resolution.html#allowed-paths"><code class="docutils literal notranslate"><span class="pre">--allow-paths</span></code></a> argument, use <code class="docutils literal notranslate"><span class="pre">--solc_allow_paths</span></code>:</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell11"><span></span>gambit<span class="w"> </span>mutate<span class="w"> </span>--filename<span class="w"> </span>path/to/file.sol<span class="w"> </span><span class="se">\</span>
<span class="w">  </span>--solc_allow_paths<span class="w"> </span>PATH1<span class="w"> </span>--solc_allow_paths<span class="w"> </span>PATH2<span class="w"> </span>...
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell11">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</li>
<li><p><strong>Specify include-path:</strong> To make an additional source directory available
to the default import callback via <code class="docutils literal notranslate"><span class="pre">solc</span></code>’s [–include-path][included] argument,
use <code class="docutils literal notranslate"><span class="pre">--solc_include_path</span></code>:</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell12"><span></span>gambit<span class="w"> </span>mutate<span class="w"> </span>--filename<span class="w"> </span>path/to/file.sol<span class="w"> </span>--solc_include_path<span class="w"> </span>PATH
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell12">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</li>
<li><p><strong>Use optimization:</strong> To run the Solidity compiler with optimizations
(<code class="docutils literal notranslate"><span class="pre">solc</span></code>’s <code class="docutils literal notranslate"><span class="pre">--optimize</span></code> argument), use <code class="docutils literal notranslate"><span class="pre">--solc_optimize</span></code>:</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell13"><span></span>gambit<span class="w"> </span>mutate<span class="w"> </span>--filename<span class="w"> </span>path/to/file.sol<span class="w"> </span>--solc_optimize
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell13">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</li>
</ul>
</section>
<section id="example-5-the-sourceroot-option">
<h3>Example 5: The <code class="docutils literal notranslate"><span class="pre">--sourceroot</span></code> option<a class="headerlink" href="#example-5-the-sourceroot-option" title="Link to this heading"></a></h3>
<p>Gambit needs to track the location of source files that it mutates within a
project: for instance, imagine there are files <code class="docutils literal notranslate"><span class="pre">foo/Foo.sol</span></code> and <code class="docutils literal notranslate"><span class="pre">bar/Foo.sol</span></code>.
These are separate files, and their path prefixes are needed to determine this.
Gambit addresses this with the <code class="docutils literal notranslate"><span class="pre">--sourceroot</span></code> option: the source root indicates
to Gambit the root of the files that are being mutated, and all source file
paths (both original and mutated) are reported relative to this source root.</p>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>If Gambit encounters a source file that does not belong to the source root it
will print an error message and exit.</p>
</div>
<p><em>When running <code class="docutils literal notranslate"><span class="pre">gambit</span> <span class="pre">mutate</span></code> with the <code class="docutils literal notranslate"><span class="pre">--filename</span></code> option,
source root defaults to the current working directory.
When running <code class="docutils literal notranslate"><span class="pre">gambit</span> <span class="pre">mutate</span></code> with the <code class="docutils literal notranslate"><span class="pre">--json</span></code> option,
source root defaults to the directory containing the configuration JSON.</em></p>
<p>Here are some examples of using the <code class="docutils literal notranslate"><span class="pre">--sourceroot</span></code> option.</p>
<ol class="arabic">
<li><p>From the root of the Gambit repository, run:</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell14"><span></span>gambit<span class="w"> </span>mutate<span class="w"> </span>-f<span class="w"> </span>benchmarks/BinaryOpMutation/BinaryOpMutation.sol<span class="w"> </span>-n<span class="w"> </span><span class="m">1</span>
cat<span class="w"> </span>gambit_out/mutants.log
find<span class="w"> </span>gambit_out/mutants<span class="w"> </span>-name<span class="w"> </span><span class="s2">"*.sol"</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell14">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>This should output the following:</p>
<div class="highlight-default notranslate"><div class="highlight"><pre id="codecell15"><span></span><span class="n">Generated</span> <span class="mi">1</span> <span class="n">mutants</span> <span class="ow">in</span> <span class="mf">0.13</span> <span class="n">seconds</span>
<span class="mi">1</span><span class="p">,</span><span class="n">BinaryOpMutation</span><span class="p">,</span><span class="n">benchmarks</span><span class="o">/</span><span class="n">BinaryOpMutation</span><span class="o">/</span><span class="n">BinaryOpMutation</span><span class="o">.</span><span class="n">sol</span><span class="p">,</span><span class="mi">23</span><span class="p">:</span><span class="mi">10</span><span class="p">,</span> <span class="o">%</span> <span class="p">,</span><span class="o">*</span>
<span class="n">gambit_out</span><span class="o">/</span><span class="n">mutants</span><span class="o">/</span><span class="mi">1</span><span class="o">/</span><span class="n">benchmarks</span><span class="o">/</span><span class="n">BinaryOpMutation</span><span class="o">/</span><span class="n">BinaryOpMutation</span><span class="o">.</span><span class="n">sol</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell15">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>The first command generates a single mutant, and its source path is relative to <code class="docutils literal notranslate"><span class="pre">.</span></code>,
the default source root. We can see that the reported paths in <code class="docutils literal notranslate"><span class="pre">mutants.log</span></code>,
and the mutant file path in <code class="docutils literal notranslate"><span class="pre">gambit_out/mutants/1</span></code>, are the relative to this
source root: <code class="docutils literal notranslate"><span class="pre">benchmarks/BinaryOpMutation/BinaryOpMutation.sol</span></code></p>
</li>
<li><p>Suppose we want our paths to be reported relative to
<code class="docutils literal notranslate"><span class="pre">benchmarks/BinaryOpMutation</span></code>. We can run</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell16"><span></span>gambit<span class="w"> </span>mutate<span class="w"> </span>-f<span class="w"> </span>benchmarks/BinaryOpMutation/BinaryOpMutation.sol<span class="w"> </span>-n<span class="w"> </span><span class="m">1</span><span class="w"> </span>--sourceroot<span class="w"> </span>benchmarks/BinaryOpMutation
cat<span class="w"> </span>gambit_out/mutants.log
find<span class="w"> </span>gambit_out/mutants<span class="w"> </span>-name<span class="w"> </span><span class="s2">"*.sol"</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell16">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>which will output:</p>
<div class="highlight-default notranslate"><div class="highlight"><pre id="codecell17"><span></span><span class="n">Generated</span> <span class="mi">1</span> <span class="n">mutants</span> <span class="ow">in</span> <span class="mf">0.13</span> <span class="n">seconds</span>
<span class="mi">1</span><span class="p">,</span><span class="n">BinaryOpMutation</span><span class="p">,</span><span class="n">BinaryOpMutation</span><span class="o">.</span><span class="n">sol</span><span class="p">,</span><span class="mi">23</span><span class="p">:</span><span class="mi">10</span><span class="p">,</span> <span class="o">%</span> <span class="p">,</span><span class="o">*</span>
<span class="n">gambit_out</span><span class="o">/</span><span class="n">mutants</span><span class="o">/</span><span class="mi">1</span><span class="o">/</span><span class="n">BinaryOpMutation</span><span class="o">.</span><span class="n">sol</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell17">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>The reported filenames, and the offset path inside of
<code class="docutils literal notranslate"><span class="pre">gambit_out/mutants/1/</span></code>, are now relative to the source root that we
specified.</p>
</li>
<li><p>Finally, suppose we use a source root that doesn’t contain the source file:</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell18"><span></span>gambit<span class="w"> </span>mutate<span class="w"> </span>-f<span class="w"> </span>benchmarks/BinaryOpMutation/BinaryOpMutation.sol<span class="w"> </span>-n<span class="w"> </span><span class="m">1</span><span class="w"> </span>--sourceroot<span class="w"> </span>scripts
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell18">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>This will try to find the specified file inside of <code class="docutils literal notranslate"><span class="pre">scripts</span></code>, and since it
doesn’t exist Gambit reports the error:</p>
<div class="highlight-default notranslate"><div class="highlight"><pre id="codecell19"><span></span>[ERROR gambit] [!!] Illegal Configuration: Resolved filename `/Users/USER/Gambit/benchmarks/BinaryOpMutation/BinaryOpMutation.sol` is not prefixed by the derived source root /Users/USER/Gambit/scripts
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell19">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>Gambit prints an error and exits.</p>
</li>
</ol>
</section>
<section id="example-6-running-gambit-using-a-configuration-file">
<span id="gambit-config"></span><h3>Example 6: Running Gambit using a configuration file<a class="headerlink" href="#example-6-running-gambit-using-a-configuration-file" title="Link to this heading"></a></h3>
<p>To run gambit with a configuration file, use the <code class="docutils literal notranslate"><span class="pre">--json</span></code> argument:</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell20"><span></span>gambit<span class="w"> </span>mutate<span class="w"> </span>--json<span class="w"> </span>benchmarks/config-jsons/test1.json
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell20">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>The configuration file is a JSON file containing the command line arguments for
<code class="docutils literal notranslate"><span class="pre">gambit</span></code> and additional configuration options:</p>
<div class="highlight-json notranslate"><div class="highlight"><pre id="codecell21"><span></span><span class="p">{</span>
<span class="w">    </span><span class="nt">"filename"</span><span class="p">:</span><span class="w"> </span><span class="s2">"../10Power/TenPower.sol"</span><span class="p">,</span>
<span class="w">    </span><span class="nt">"sourceroot"</span><span class="p">:</span><span class="w"> </span><span class="s2">".."</span><span class="p">,</span>
<span class="w">    </span><span class="nt">"solc_remappings"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span>
<span class="w">        </span><span class="s2">"@openzeppelin=node_modules/@openzeppelin"</span>
<span class="w">    </span><span class="p">],</span>
<span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell21">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>In addition to specifying the command line arguments, you can list the specific
mutants that you want to apply, the specific functions you wish to mutate, and
more. See the <a class="reference external" href="https://github.com/Certora/gambit/blob/master/benchmarks/config-jsons/"><code class="docutils literal notranslate"><span class="pre">benchmark/config-jsons</span></code> directory</a> for
examples.</p>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>Any paths provided by the configuration file are resolved relative to the
configuration file’s parent directory.</p>
</div>
</section>
</section>
<section id="configuration-files">
<span id="id1"></span><h2>Configuration Files<a class="headerlink" href="#configuration-files" title="Link to this heading"></a></h2>
<p>Configuration files allow you to save complex configurations and perform
multiple mutations at once. Gambit uses a simple JSON object format to store
mutation options, where each <code class="docutils literal notranslate"><span class="pre">--option</span> <span class="pre">VALUE</span></code> specified on the CLI is
represented as a <code class="docutils literal notranslate"><span class="pre">"option":</span> <span class="pre">VALUE</span></code> key/value pair in the JSON object.  Boolean
<code class="docutils literal notranslate"><span class="pre">--flag</span></code>s are enabled by storing them as true: <code class="docutils literal notranslate"><span class="pre">"flag":</span> <span class="pre">true</span></code>. For instance,
<code class="docutils literal notranslate"><span class="pre">--no_overwrite</span></code> would be written as <code class="docutils literal notranslate"><span class="pre">"no_overwrite":</span> <span class="pre">true</span></code>.</p>
<p>As an example, consider the command from Example 1:</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell22"><span></span>gambit<span class="w"> </span>mutate<span class="w"> </span>-f<span class="w"> </span>benchmarks/BinaryOpMutation/BinaryOpMutation.sol
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell22">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>To execute this using a configuration file you would write the following to
<code class="docutils literal notranslate"><span class="pre">example-1.json</span></code> to the root of this repository and run <code class="docutils literal notranslate"><span class="pre">gambit</span> <span class="pre">mutate</span> <span class="pre">--json</span> <span class="pre">example-1.json</span></code></p>
<div class="highlight-json notranslate"><div class="highlight"><pre id="codecell23"><span></span><span class="p">{</span>
<span class="w">  </span><span class="nt">"filename"</span><span class="p">:</span><span class="w"> </span><span class="s2">"benchmarks/BinaryOpMutation/BinaryOpMutation.sol"</span>
<span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell23">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>Gambit also supports using multiple configurations in the same file: instead of
a single JSON object, your configuration file should contain an array of objects:</p>
<div class="highlight-json notranslate"><div class="highlight"><pre id="codecell24"><span></span><span class="p">[</span>
<span class="w">    </span><span class="p">{</span>
<span class="w">        </span><span class="nt">"filename"</span><span class="p">:</span><span class="w"> </span><span class="s2">"Foo.sol"</span><span class="p">,</span>
<span class="w">        </span><span class="nt">"contract"</span><span class="p">:</span><span class="w"> </span><span class="s2">"C"</span><span class="p">,</span>
<span class="w">        </span><span class="nt">"functions"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="s2">"bar"</span><span class="p">,</span><span class="w"> </span><span class="s2">"baz"</span><span class="p">],</span>
<span class="w">        </span><span class="nt">"solc"</span><span class="p">:</span><span class="w"> </span><span class="s2">"solc8.12"</span><span class="p">,</span>
<span class="w">        </span><span class="nt">"solc_optimize"</span><span class="p">:</span><span class="w"> </span><span class="kc">true</span>
<span class="w">    </span><span class="p">},</span>
<span class="w">    </span><span class="p">{</span>
<span class="w">        </span><span class="nt">"filename"</span><span class="p">:</span><span class="w"> </span><span class="s2">"Blip.sol"</span><span class="p">,</span>
<span class="w">        </span><span class="nt">"contract"</span><span class="p">:</span><span class="w"> </span><span class="s2">"D"</span><span class="p">,</span>
<span class="w">        </span><span class="nt">"functions"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="s2">"bang"</span><span class="p">],</span>
<span class="w">        </span><span class="nt">"solc"</span><span class="p">:</span><span class="w"> </span><span class="nt">"solc8.12"</span>
<span class="w">        </span><span class="nt">"mutations"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span>
<span class="w">          </span><span class="s2">"binary-op-mutation"</span><span class="p">,</span>
<span class="w">          </span><span class="s2">"swap-arguments-operator-mutation"</span>
<span class="w">        </span><span class="p">]</span>
<span class="w">    </span><span class="p">}</span>
<span class="p">]</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell24">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>This configuration file will perform all mutations on <code class="docutils literal notranslate"><span class="pre">Foo.sol</span></code>’s functions
<code class="docutils literal notranslate"><span class="pre">bar</span></code> and <code class="docutils literal notranslate"><span class="pre">baz</span></code> in the contract <code class="docutils literal notranslate"><span class="pre">C</span></code>, and only <code class="docutils literal notranslate"><span class="pre">binary-op-mutation</span></code> and
<code class="docutils literal notranslate"><span class="pre">swap-arguments-operator-mutation</span></code> mutations on the function <code class="docutils literal notranslate"><span class="pre">bang</span></code> in the
contract <code class="docutils literal notranslate"><span class="pre">D</span></code>.  Both will compile using the Solidity compiler version <code class="docutils literal notranslate"><span class="pre">solc5.12</span></code>.</p>
<section id="paths-in-configuration-files">
<h3>Paths in Configuration Files<a class="headerlink" href="#paths-in-configuration-files" title="Link to this heading"></a></h3>
<p>Relative paths in a Gambit configuration file are <em>relative to the parent
directory of the configuration file</em>. So if the JSON file listed above was moved
to the <code class="docutils literal notranslate"><span class="pre">benchmarks/</span></code> directory the <code class="docutils literal notranslate"><span class="pre">"filename"</span></code> would need to be updated to
<code class="docutils literal notranslate"><span class="pre">BinaryOpMutation/BinaryOpMutation.sol</span></code>.</p>
</section>
</section>
<section id="results-directory">
<span id="id2"></span><h2>Results Directory<a class="headerlink" href="#results-directory" title="Link to this heading"></a></h2>
<p><code class="docutils literal notranslate"><span class="pre">gambit</span> <span class="pre">mutate</span></code> produces all results in an output directory (default:
<code class="docutils literal notranslate"><span class="pre">gambit_out</span></code>). Here is an example:</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell25"><span></span>gambit<span class="w"> </span>mutate<span class="w"> </span>-f<span class="w"> </span>benchmarks/BinaryOpMutation/BinaryOpMutation.sol<span class="w"> </span>-n<span class="w"> </span><span class="m">5</span>
tree<span class="w"> </span>gambit_out<span class="w"> </span>-L<span class="w"> </span><span class="m">2</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell25">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>which produces:</p>
<div class="highlight-default notranslate"><div class="highlight"><pre id="codecell26"><span></span>Generated 5 mutants in 0.15 seconds

gambit_out
├── gambit_results.json
├── input_json
├── mutants
│   ├── 1
│   ├── 2
│   ├── 3
│   ├── 4
│   └── 5
└── mutants.log

</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell26">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>This has the following structure:</p>
<ul class="simple">
<li><p><code class="docutils literal notranslate"><span class="pre">gambit_results.json</span></code>: a JSON file with detailed results</p></li>
<li><p><code class="docutils literal notranslate"><span class="pre">input_json/</span></code>: intermediate files produced by <code class="docutils literal notranslate"><span class="pre">solc</span></code> that are used during mutation</p></li>
<li><p><code class="docutils literal notranslate"><span class="pre">mutants/</span></code>: exported mutants. Each mutant is in its own directory named after
its mutant ID (mid) 1, 2, 3, …</p></li>
<li><p><code class="docutils literal notranslate"><span class="pre">mutants.log</span></code>: a log file with all mutant information. This is similar to
<code class="docutils literal notranslate"><span class="pre">results.json</span></code> but in a different format and with different information</p></li>
</ul>
</section>
<section id="cli-options">
<span id="id3"></span><h2>CLI Options<a class="headerlink" href="#cli-options" title="Link to this heading"></a></h2>
<p><code class="docutils literal notranslate"><span class="pre">gambit</span> <span class="pre">mutate</span></code> supports the following options; for a comprehensive list, run
<code class="docutils literal notranslate"><span class="pre">gambit</span> <span class="pre">mutate</span> <span class="pre">--help</span></code>:</p>
<div class="wy-table-responsive"><table class="docutils align-default">
<thead>
<tr class="row-odd"><th class="head text-left"><p>Option</p></th>
<th class="head text-left"><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="row-even"><td class="text-left"><p><code class="docutils literal notranslate"><span class="pre">-o</span></code>, <code class="docutils literal notranslate"><span class="pre">--outdir</span></code></p></td>
<td class="text-left"><p>specify Gambit’s output directory (defaults to <code class="docutils literal notranslate"><span class="pre">gambit_out</span></code>)</p></td>
</tr>
<tr class="row-odd"><td class="text-left"><p><code class="docutils literal notranslate"><span class="pre">--no_overwrite</span></code></p></td>
<td class="text-left"><p>do not overwrite an output directory; if the output directory exists, print an error and exit</p></td>
</tr>
<tr class="row-even"><td class="text-left"><p><code class="docutils literal notranslate"><span class="pre">-n</span></code>, <code class="docutils literal notranslate"><span class="pre">--num_mutants</span></code></p></td>
<td class="text-left"><p>randomly downsample to a given number of mutants.</p></td>
</tr>
<tr class="row-odd"><td class="text-left"><p><code class="docutils literal notranslate"><span class="pre">-s</span></code>, <code class="docutils literal notranslate"><span class="pre">--seed</span></code></p></td>
<td class="text-left"><p>specify a random seed. For reproducibility, Gambit defaults to using the seed <code class="docutils literal notranslate"><span class="pre">0</span></code>. To randomize the seed use <code class="docutils literal notranslate"><span class="pre">--random_seed</span></code></p></td>
</tr>
<tr class="row-even"><td class="text-left"><p><code class="docutils literal notranslate"><span class="pre">--random_seed</span></code></p></td>
<td class="text-left"><p>use a random seed. Note that this overrides any value specified by <code class="docutils literal notranslate"><span class="pre">--seed</span></code></p></td>
</tr>
<tr class="row-odd"><td class="text-left"><p><code class="docutils literal notranslate"><span class="pre">--contract</span></code></p></td>
<td class="text-left"><p>specify a specific contract name to mutate; by default mutate all contracts</p></td>
</tr>
<tr class="row-even"><td class="text-left"><p><code class="docutils literal notranslate"><span class="pre">--functions</span></code></p></td>
<td class="text-left"><p>specify one or more functions to mutate; by default mutate all functions</p></td>
</tr>
<tr class="row-odd"><td class="text-left"><p><code class="docutils literal notranslate"><span class="pre">--mutations</span></code></p></td>
<td class="text-left"><p>specify one or more mutation operators to use; only generates mutants that are created using the specified operators</p></td>
</tr>
<tr class="row-even"><td class="text-left"><p><code class="docutils literal notranslate"><span class="pre">--skip_validate</span></code></p></td>
<td class="text-left"><p>only generate mutants without validating them by compilation</p></td>
</tr>
</tbody>
</table></div>
<p>Gambit also supports <em>pass-through arguments</em>, which are arguments that are
passed directly to the Solidity compiler. All pass-through arguments are
prefixed with <code class="docutils literal notranslate"><span class="pre">solc_</span></code>:</p>
<div class="wy-table-responsive"><table class="docutils align-default">
<thead>
<tr class="row-odd"><th class="head text-left"><p>Option</p></th>
<th class="head text-left"><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="row-even"><td class="text-left"><p><code class="docutils literal notranslate"><span class="pre">--solc_allow_paths</span></code></p></td>
<td class="text-left"><p>passes a value to <code class="docutils literal notranslate"><span class="pre">solc</span></code>’s <code class="docutils literal notranslate"><span class="pre">--allow-paths</span></code> argument</p></td>
</tr>
<tr class="row-odd"><td class="text-left"><p><code class="docutils literal notranslate"><span class="pre">--solc_base_path</span></code></p></td>
<td class="text-left"><p>passes a value to <code class="docutils literal notranslate"><span class="pre">solc</span></code>’s <code class="docutils literal notranslate"><span class="pre">--base-path</span></code> argument</p></td>
</tr>
<tr class="row-even"><td class="text-left"><p><code class="docutils literal notranslate"><span class="pre">--solc_include_path</span></code></p></td>
<td class="text-left"><p>passes a value to <code class="docutils literal notranslate"><span class="pre">solc</span></code>’s <code class="docutils literal notranslate"><span class="pre">--include-path</span></code> argument</p></td>
</tr>
<tr class="row-odd"><td class="text-left"><p><code class="docutils literal notranslate"><span class="pre">--solc_remappings</span></code></p></td>
<td class="text-left"><p>passes a value to directly to <code class="docutils literal notranslate"><span class="pre">solc</span></code>: this should be of the form <code class="docutils literal notranslate"><span class="pre">prefix=path</span></code>.</p></td>
</tr>
</tbody>
</table></div>
</section>
<section id="mutation-operators">
<h2>Mutation Operators<a class="headerlink" href="#mutation-operators" title="Link to this heading"></a></h2>
<p>Gambit implements the following mutation operators</p>
<div class="wy-table-responsive"><table class="docutils align-default">
<thead>
<tr class="row-odd"><th class="head"><p>Mutation Operator</p></th>
<th class="head"><p>Description</p></th>
<th class="head"><p>Example</p></th>
</tr>
</thead>
<tbody>
<tr class="row-even"><td><p><strong>binary-op-mutation</strong></p></td>
<td><p>Replace a binary operator with another</p></td>
<td><p><code class="docutils literal notranslate"><span class="pre">a+b</span></code> -&gt; <code class="docutils literal notranslate"><span class="pre">a-b</span></code></p></td>
</tr>
<tr class="row-odd"><td><p><strong>unary-operator-mutation</strong></p></td>
<td><p>Replace a unary operator with another</p></td>
<td><p><code class="docutils literal notranslate"><span class="pre">~a</span></code> -&gt; <code class="docutils literal notranslate"><span class="pre">-a</span></code></p></td>
</tr>
<tr class="row-even"><td><p><strong>require-mutation</strong></p></td>
<td><p>Alter the condition of a <code class="docutils literal notranslate"><span class="pre">require</span></code> statement</p></td>
<td><p><code class="docutils literal notranslate"><span class="pre">require(some_condition())</span></code> -&gt; <code class="docutils literal notranslate"><span class="pre">require(true)</span></code></p></td>
</tr>
<tr class="row-odd"><td><p><strong>assignment-mutation</strong></p></td>
<td><p>Replaces the right hand side of an assignment</p></td>
<td><p><code class="docutils literal notranslate"><span class="pre">x</span> <span class="pre">=</span> <span class="pre">foo();</span></code> -&gt; <code class="docutils literal notranslate"><span class="pre">x</span> <span class="pre">=</span> <span class="pre">-1;</span></code></p></td>
</tr>
<tr class="row-even"><td><p><strong>delete-expression-mutation</strong></p></td>
<td><p>Replaces an expression with a no-op (<code class="docutils literal notranslate"><span class="pre">assert(true)</span></code>)</p></td>
<td><p><code class="docutils literal notranslate"><span class="pre">foo();</span></code> -&gt; <code class="docutils literal notranslate"><span class="pre">assert(true);</span></code></p></td>
</tr>
<tr class="row-odd"><td><p><strong>if-cond-mutation</strong></p></td>
<td><p>Mutate the conditional of an <code class="docutils literal notranslate"><span class="pre">if</span></code> statement</p></td>
<td><p><code class="docutils literal notranslate"><span class="pre">if</span> <span class="pre">(C)</span> <span class="pre">{...}</span></code> -&gt; <code class="docutils literal notranslate"><span class="pre">if</span> <span class="pre">(true)</span> <span class="pre">{...}</span></code></p></td>
</tr>
<tr class="row-even"><td><p><strong>swap-arguments-operator-mutation</strong></p></td>
<td><p>Swap the order of non-commutative operators</p></td>
<td><p><code class="docutils literal notranslate"><span class="pre">a</span> <span class="pre">-</span> <span class="pre">b</span></code> -&gt; <code class="docutils literal notranslate"><span class="pre">b</span> <span class="pre">-</span> <span class="pre">a</span></code></p></td>
</tr>
<tr class="row-odd"><td><p><strong>elim-delegate-mutation</strong></p></td>
<td><p>Change a <code class="docutils literal notranslate"><span class="pre">delegatecall()</span></code> to a <code class="docutils literal notranslate"><span class="pre">call()</span></code></p></td>
<td><p><code class="docutils literal notranslate"><span class="pre">_c.delegatecall(...)</span></code> -&gt; <code class="docutils literal notranslate"><span class="pre">_c.call(...)</span></code></p></td>
</tr>
<tr class="row-even"><td><p><strong>function-call-mutation</strong></p></td>
<td><p><strong>(Disabled)</strong> Changes arguments of a function</p></td>
<td><p><code class="docutils literal notranslate"><span class="pre">add(a,</span> <span class="pre">b)</span></code> -&gt; <code class="docutils literal notranslate"><span class="pre">add(a,</span> <span class="pre">a)</span></code></p></td>
</tr>
<tr class="row-odd"><td><p><strong>swap-arguments-function-mutation</strong></p></td>
<td><p><strong>(Disabled)</strong> Swaps the order of a function’s arguments</p></td>
<td><p><code class="docutils literal notranslate"><span class="pre">add(a,</span> <span class="pre">b)</span></code> -&gt; <code class="docutils literal notranslate"><span class="pre">add(b,</span> <span class="pre">a)</span></code></p></td>
</tr>
</tbody>
</table></div>
<p>For more details on each mutation type, refer to the <a class="reference external" href="https://docs.certora.com/en/latest/docs/gambit/gambit.html#mutation-types">full documentation</a>.</p>
</section>
</section>


           </div>
          </div>
          <footer><div class="rst-footer-buttons" role="navigation" aria-label="Footer">
        <a href="mutation-verifier.html" class="btn btn-neutral float-left" title="Using Gambit with the Prover" accesskey="p" rel="prev"><span class="fa fa-arrow-circle-left" aria-hidden="true"></span> Previous</a>
        <a href="../equiv-check/index.html" class="btn btn-neutral float-right" title="The Certora Equivalence Checker" accesskey="n" rel="next">Next <span class="fa fa-arrow-circle-right" aria-hidden="true"></span></a>
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