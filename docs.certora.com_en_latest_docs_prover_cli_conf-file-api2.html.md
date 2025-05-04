<!DOCTYPE html><html class="writer-html5" lang="en" data-content_root="../../../"><head>
  <meta charset="utf-8"><meta name="viewport" content="width=device-width, initial-scale=1">

  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Configuration (Conf) Files — Certora Prover Documentation 0.0 documentation</title>
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
    <link rel="next" title="Using the Certora Portal" href="../portal/using.html">
    <link rel="prev" title="CLI Options" href="options.html"> 
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
<li class="toctree-l2"><a class="reference internal" href="../approx/index.html">Prover Approximations</a></li>
<li class="toctree-l2"><a class="reference internal" href="../techniques/index.html">Techniques Used by the Certora Prover</a></li>
<li class="toctree-l2"><a class="reference internal" href="../diagnosis/index.html">Diagnostic Tools</a></li>
<li class="toctree-l2"><a class="reference internal" href="../checking/index.html">Checking Specifications</a></li>
<li class="toctree-l2 current" aria-expanded="true"><a class="reference internal" href="index.html"><button class="toctree-expand" title="Open/close menu"></button>Certora Prover CLI</a><ul class="" aria-expanded="false">
<li class="toctree-l3"><a class="reference internal" href="options.html">CLI Options</a></li>
<li class="toctree-l3"><a class="reference internal" href="options.html#most-frequently-used-options">Most frequently used options</a></li>
<li class="toctree-l3"><a class="reference internal" href="options.html#options-affecting-the-type-of-verification-run">Options affecting the type of verification run</a></li>
<li class="toctree-l3"><a class="reference internal" href="options.html#options-that-control-the-solidity-compiler">Options that control the Solidity compiler</a></li>
<li class="toctree-l3"><a class="reference internal" href="options.html#options-regarding-source-code-loops">Options regarding source code loops</a></li>
<li class="toctree-l3"><a class="reference internal" href="options.html#options-regarding-summarization">Options regarding summarization</a></li>
<li class="toctree-l3"><a class="reference internal" href="options.html#options-regarding-hashing-of-unbounded-data">Options regarding hashing of unbounded data</a></li>
<li class="toctree-l3"><a class="reference internal" href="options.html#options-that-help-reduce-the-running-time">Options that help reduce the running time</a></li>
<li class="toctree-l3"><a class="reference internal" href="options.html#options-to-set-addresses-and-link-contracts">Options to set addresses and link contracts</a></li>
<li class="toctree-l3"><a class="reference internal" href="options.html#options-for-job-metadata-and-dashboard-filtering">Options for job metadata and dashboard filtering</a></li>
<li class="toctree-l3"><a class="reference internal" href="options.html#options-for-controlling-contract-creation">Options for controlling contract creation</a></li>
<li class="toctree-l3"><a class="reference internal" href="options.html#version-options">Version options</a></li>
<li class="toctree-l3"><a class="reference internal" href="options.html#conf-file-options">Conf file options</a></li>
<li class="toctree-l3"><a class="reference internal" href="options.html#advanced-options">Advanced options</a></li>
<li class="toctree-l3 current" aria-expanded="true"><a class="reference internal current" href="#" aria-expanded="true"><button class="toctree-expand" title="Open/close menu"></button>Configuration (Conf) Files</a><ul>
<li class="toctree-l4"><a class="reference internal" href="#how-cli-options-are-mapped-to-json">How CLI options are mapped to JSON</a></li>
<li class="toctree-l4"><a class="reference internal" href="#generating-a-conf-file">Generating a conf file</a></li>
</ul>
</li>
</ul>
</li>
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
          <li class="breadcrumb-item"><a href="index.html">Certora Prover CLI</a></li>
      <li class="breadcrumb-item active">Configuration (Conf) Files</li>
      <li class="wy-breadcrumbs-aside">
            <a href="../../../_sources/docs/prover/cli/conf-file-api.md.txt" rel="nofollow"> View page source</a>
      </li>
  </ul>
  <hr>
</div>
          <div role="main" class="document" itemscope="itemscope" itemtype="http://schema.org/Article">
           <div itemprop="articleBody">
             
  <section id="configuration-conf-files">
<span id="conf-files"></span><h1>Configuration (Conf) Files<a class="headerlink" href="#configuration-conf-files" title="Link to this heading"></a></h1>
<p>Conf files are an alternative way for setting arguments for the
&nbsp;<code class="docutils literal notranslate"><span class="pre">certoraRun</span></code>&nbsp;tool. In terms of functionality
using conf files is identical to the use of the <a class="reference internal" href="options.html"><span class="std std-doc">CLI Options</span></a>. Instead of calling <code class="docutils literal notranslate"><span class="pre">certoraRun</span></code>
with a list of shell flags, some or all the flags can be stored in a JSON file
(to be more precise the format is <a class="reference external" href="https://json5.org/">JSON5</a>):</p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell0"><span></span>certoraRun<span class="w"> </span>my_params.conf
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell0">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>Conf files must use the <code class="docutils literal notranslate"><span class="pre">.conf</span></code> suffix.</p>
<section id="how-cli-options-are-mapped-to-json">
<h2>How CLI options are mapped to JSON<a class="headerlink" href="#how-cli-options-are-mapped-to-json" title="Link to this heading"></a></h2>
<p>Command-line arguments are stored as key-value pairs in the conf file.
The keys are the names of the CLI options (with the leading <code class="docutils literal notranslate"><span class="pre">--</span></code> removed).
For example,</p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell1"><span></span>certoraRun<span class="w"> </span>--verify<span class="w"> </span>Example:example.spec
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell1">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>is equivalent to running with the following conf file:</p>
<div class="highlight-json notranslate"><div class="highlight"><pre id="codecell2"><span></span><span class="p">{</span><span class="w"> </span><span class="nt">"verify"</span><span class="p">:</span><span class="w"> </span><span class="s2">"Example:example.spec"</span><span class="w"> </span><span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell2">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>The values in the map depend on the type of arguments:</p>
<ul>
<li><p>The input files in the CLI API will be stored as a list under the key <code class="docutils literal notranslate"><span class="pre">files</span></code>.  For example,</p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell3"><span></span>certoraRun<span class="w"> </span>example.sol<span class="w">  </span>...
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell3">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>will appear in the conf file as:</p>
<div class="highlight-default notranslate"><div class="highlight"><pre id="codecell4"><span></span><span class="p">{</span>
  <span class="o">...</span>
  <span class="s2">"files"</span><span class="p">:</span> <span class="p">[</span> <span class="s2">"example.sol"</span> <span class="p">],</span> 
  <span class="o">...</span>
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
</li>
<li><p>Boolean options are options that take no arguments (for example <a class="reference internal" href="options.html#multi-assert-check"><span class="std std-ref">multi_assert_check</span></a>). In
the conf file all keys must come with a value, the value for boolean options is <code class="docutils literal notranslate"><span class="pre">true</span></code>.
Since the default value of boolean options is <code class="docutils literal notranslate"><span class="pre">false</span></code> there is no need to set a boolean attribute to values other than <code class="docutils literal notranslate"><span class="pre">true</span></code>.  For example,</p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell5"><span></span>certoraRun<span class="w"> </span>--multi_assert_check
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell5">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>would be encoded as:</p>
<div class="highlight-json notranslate"><div class="highlight"><pre id="codecell6"><span></span><span class="p">{</span><span class="w"> </span><span class="nt">"multi_assert_check"</span><span class="p">:</span><span class="w"> </span><span class="kc">true</span><span class="w"> </span><span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell6">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</li>
<li><p>Options that expect a single argument (for example <a class="reference internal" href="options.html#solc"><span class="std std-ref">solc</span></a> or <a class="reference internal" href="options.html#loop-iter"><span class="std std-ref">loop_iter</span></a>)
are encoded as a JSON string. For example,</p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell7"><span></span>certoraRun<span class="w"> </span>--solc<span class="w"> </span>solc4.25<span class="w"> </span>--loop_iter<span class="w"> </span><span class="m">2</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell7">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>would be encoded as:</p>
<div class="highlight-json notranslate"><div class="highlight"><pre id="codecell8"><span></span><span class="p">{</span><span class="w"> </span><span class="nt">"solc"</span><span class="p">:</span><span class="w"> </span><span class="s2">"solc4.25"</span><span class="p">,</span><span class="w"> </span><span class="nt">"loop_iter"</span><span class="p">:</span><span class="w"> </span><span class="s2">"2"</span><span class="w"> </span><span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell8">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>Note that in conf files numbers are also encoded as strings.</p>
</li>
<li><p>Options that expect multiple arguments (for example <a class="reference internal" href="options.html#packages"><span class="std std-ref">packages</span></a>)
are encoded as JSON lists. For example,</p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell9"><span></span>certoraRun<span class="w"> </span>--packages<span class="w"> </span>@balancer-labs/v2-solidity-utils<span class="o">=</span>pkg/solidity-utils<span class="w"> </span><span class="se">\</span>
<span class="w">                  </span>@balancer-labs/v2-vault<span class="o">=</span>pkg/vault
would<span class="w"> </span>be<span class="w"> </span>encoded<span class="w"> </span>as:
<span class="sb">```</span>json
<span class="o">{</span>
<span class="w">  </span><span class="s2">"packages"</span>:<span class="w"> </span><span class="o">[</span>
<span class="w">    </span><span class="s2">"@balancer-labs/v2-solidity-utils=pkg/solidity-utils"</span>,
<span class="w">    </span><span class="s2">"@balancer-labs/v2-vault=pkg/vault"</span>
<span class="w">  </span><span class="o">]</span><span class="w"> </span>
<span class="o">}</span>
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
<li><p>Options that are maps (<a class="reference internal" href="options.html#solc-map"><span class="std std-ref">compiler_map</span></a>, <a class="reference internal" href="options.html#solc-optimize-map"><span class="std std-ref">solc_optimize_map</span></a> and <a class="reference internal" href="options.html#solc-evm-version-map"><span class="std std-ref">solc_evm_version_map</span></a>) will be stored as JSON objects.
For example,</p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell10"><span></span>certoraRun<span class="w"> </span>--solc_map<span class="w"> </span><span class="nv">A</span><span class="o">=</span>solc5.11,B<span class="o">=</span>solc5.9,C<span class="o">=</span>solc6.8
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell10">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>would be encoded as:</p>
</li>
</ul>
<div class="highlight-json notranslate"><div class="highlight"><pre id="codecell11"><span></span><span class="p">{</span>
<span class="w">  </span><span class="nt">"solc_map"</span><span class="p">:</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="nt">"A"</span><span class="p">:</span><span class="w"> </span><span class="s2">"solc5.11"</span><span class="p">,</span>
<span class="w">    </span><span class="nt">"B"</span><span class="p">:</span><span class="w"> </span><span class="s2">"solc5.9"</span><span class="p">,</span>
<span class="w">    </span><span class="nt">"C"</span><span class="p">:</span><span class="w"> </span><span class="s2">"solc6.8"</span>
<span class="w">  </span><span class="p">}</span>
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
<div class="highlight-none notranslate"><div class="highlight"><pre id="codecell12"><span></span>and 

```sh
certoraRun --solc_optimize_map A=200,B=200,C=300
```
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell12">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>would be encoded as:</p>
<div class="highlight-json notranslate"><div class="highlight"><pre id="codecell13"><span></span><span class="p">{</span>
<span class="w">  </span><span class="nt">"solc_optimize_map"</span><span class="p">:</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="nt">"A"</span><span class="p">:</span><span class="w"> </span><span class="s2">"200"</span><span class="p">,</span>
<span class="w">    </span><span class="nt">"B"</span><span class="p">:</span><span class="w"> </span><span class="s2">"200"</span><span class="p">,</span>
<span class="w">    </span><span class="nt">"C"</span><span class="p">:</span><span class="w"> </span><span class="s2">"300"</span>
<span class="w">  </span><span class="p">}</span>
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
</section>
<section id="generating-a-conf-file">
<h2>Generating a conf file<a class="headerlink" href="#generating-a-conf-file" title="Link to this heading"></a></h2>
<p>After each successful run of&nbsp;<code class="docutils literal notranslate"><span class="pre">certoraRun</span></code>&nbsp;a conf file is generated and is
stored in the file <code class="docutils literal notranslate"><span class="pre">run.conf</span></code> under the internal directory of that run.
The conf file of the latest run can be found in:</p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell14"><span></span>.certora_internal/latest/run.conf
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell14">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>Instead of generating a complete conf file from scratch, users can take
one of these generated conf files as a basis for their modifications.</p>
<section id="complete-example">
<h3>Complete example<a class="headerlink" href="#complete-example" title="Link to this heading"></a></h3>
<p>The command line</p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell15"><span></span>certoraRun<span class="w"> </span>SolcArgs/A.sol<span class="w"> </span>SolcArgs/A.sol:B<span class="w"> </span>SolcArgs/C.sol<span class="w"> </span><span class="se">\</span>
<span class="w">  </span>--verify<span class="w"> </span>A:SolcArgs/Trigger.spec<span class="w"> </span><span class="se">\</span>
<span class="w">  </span>--solc_map<span class="w"> </span>SolcArgs/A.sol<span class="o">=</span>solc6.1,B<span class="o">=</span>solc6.1,C<span class="o">=</span>solc5.12<span class="w"> </span><span class="se">\</span>
<span class="w">  </span>--multi_assert_check<span class="w"> </span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell15">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>will generate the conf file below:</p>
<div class="highlight-json notranslate"><div class="highlight"><pre id="codecell16"><span></span><span class="p">{</span>
<span class="w">    </span><span class="nt">"files"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span>
<span class="w">        </span><span class="s2">"SolcArgs/A.sol"</span><span class="p">,</span>
<span class="w">        </span><span class="s2">"SolcArgs/A.sol:B"</span><span class="p">,</span>
<span class="w">        </span><span class="s2">"SolcArgs/C.sol"</span>
<span class="w">    </span><span class="p">],</span>
<span class="w">    </span><span class="nt">"multi_assert_check"</span><span class="p">:</span><span class="w"> </span><span class="kc">true</span><span class="p">,</span>
<span class="w">    </span><span class="nt">"solc_map"</span><span class="p">:</span><span class="w"> </span><span class="p">{</span>
<span class="w">        </span><span class="nt">"B"</span><span class="p">:</span><span class="w"> </span><span class="s2">"solc6.1"</span><span class="p">,</span>
<span class="w">        </span><span class="nt">"C"</span><span class="p">:</span><span class="w"> </span><span class="s2">"solc5.12"</span><span class="p">,</span>
<span class="w">        </span><span class="nt">"SolcArgs/A.sol"</span><span class="p">:</span><span class="w"> </span><span class="s2">"solc6.1"</span>
<span class="w">    </span><span class="p">},</span>
<span class="w">    </span><span class="nt">"verify"</span><span class="p">:</span><span class="w"> </span><span class="s2">"A:SolcArgs/Trigger.spec"</span>
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
</section>
</section>
</section>


           </div>
          </div>
          <footer><div class="rst-footer-buttons" role="navigation" aria-label="Footer">
        <a href="options.html" class="btn btn-neutral float-left" title="CLI Options" accesskey="p" rel="prev"><span class="fa fa-arrow-circle-left" aria-hidden="true"></span> Previous</a>
        <a href="../portal/using.html" class="btn btn-neutral float-right" title="Using the Certora Portal" accesskey="n" rel="next">Next <span class="fa fa-arrow-circle-right" aria-hidden="true"></span></a>
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