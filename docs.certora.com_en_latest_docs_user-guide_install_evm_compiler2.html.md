<!DOCTYPE html><html class="writer-html5" lang="en" data-content_root="../../"><head>
  <meta charset="utf-8"><meta name="viewport" content="width=device-width, initial-scale=1">

  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Installing an EVM compiler and VS Code Extension — Certora Prover Documentation 0.0 documentation</title>
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
    <link rel="next" title="Tutorial and Workshops" href="tutorials.html">
    <link rel="prev" title="Installation" href="install.html"> 
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
<li class="toctree-l2 current" aria-expanded="true"><a class="reference internal current" href="#" aria-expanded="true"><button class="toctree-expand" title="Open/close menu"></button>Installing an EVM compiler and VS Code Extension</a><ul>
<li class="toctree-l3"><a class="reference internal" href="#installing-solidity-compiler"><button class="toctree-expand" title="Open/close menu"></button>Installing Solidity compiler</a><ul>
<li class="toctree-l4"><a class="reference internal" href="#using-solc-select">Using <code class="docutils literal notranslate"><span class="pre">solc-select</span></code></a></li>
<li class="toctree-l4"><a class="reference internal" href="#download-binaries">Download binaries</a></li>
</ul>
</li>
<li class="toctree-l3"><a class="reference internal" href="#installing-the-vyper-compiler">Installing the Vyper compiler</a></li>
<li class="toctree-l3"><a class="reference internal" href="#installing-the-certora-verification-language-lsp-vs-code-extension">Installing the Certora Verification Language LSP VS Code extension</a></li>
</ul>
</li>
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
      <li class="breadcrumb-item active">Installing an EVM compiler and VS Code Extension</li>
      <li class="wy-breadcrumbs-aside">
            <a href="../../_sources/docs/user-guide/install_evm_compiler.md.txt" rel="nofollow"> View page source</a>
      </li>
  </ul>
  <hr>
</div>
          <div role="main" class="document" itemscope="itemscope" itemtype="http://schema.org/Article">
           <div itemprop="articleBody">
             
  <section id="installing-an-evm-compiler-and-vs-code-extension">
<span id="install-evm-compiler"></span><h1><a class="toc-backref" href="#id1" role="doc-backlink">Installing an EVM compiler and VS Code Extension</a><a class="headerlink" href="#installing-an-evm-compiler-and-vs-code-extension" title="Link to this heading"></a></h1>
<p>After completing the steps in the <a class="reference internal" href="install.html#installation"><span class="std std-ref">Certora Prover installation guide</span></a>, a locally installed Solidity or Vyper compiler is required to verify EVM code. This page provides instructions for installing the necessary compiler and setting up the VS Code extension for syntax checking and highlighting.</p>
<nav class="contents" id="overview">
<p class="topic-title">Overview</p>
<ul class="simple">
<li><p><a class="reference internal" href="#installing-an-evm-compiler-and-vs-code-extension" id="id1">Installing an EVM compiler and VS Code Extension</a></p>
<ul>
<li><p><a class="reference internal" href="#installing-solidity-compiler" id="id2">Installing Solidity compiler</a></p>
<ul>
<li><p><a class="reference internal" href="#using-solc-select" id="id3">Using <code class="docutils literal notranslate"><span class="pre">solc-select</span></code></a></p></li>
<li><p><a class="reference internal" href="#download-binaries" id="id4">Download binaries</a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#installing-the-vyper-compiler" id="id5">Installing the Vyper compiler</a></p></li>
<li><p><a class="reference internal" href="#installing-the-certora-verification-language-lsp-vs-code-extension" id="id6">Installing the Certora Verification Language LSP VS Code extension</a></p></li>
</ul>
</li>
</ul>
</nav>
<section id="installing-solidity-compiler">
<span id="selecting-solidity-compiler"></span><h2><a class="toc-backref" href="#id2" role="doc-backlink">Installing Solidity compiler</a><a class="headerlink" href="#installing-solidity-compiler" title="Link to this heading"></a></h2>
<p>There are two ways to install the Solidity compiler (<code class="docutils literal notranslate"><span class="pre">solc</span></code>): via <a class="reference external" href="https://github.com/crytic/solc-select">solc-select</a> or downloading the binary directly and adding its folder to your <code class="docutils literal notranslate"><span class="pre">PATH</span></code>.</p>
<section id="using-solc-select">
<span id="index-0"></span><h3><a class="toc-backref" href="#id3" role="doc-backlink">Using <code class="docutils literal notranslate"><span class="pre">solc-select</span></code></a><a class="headerlink" href="#using-solc-select" title="Link to this heading"></a></h3>
<details>
  <summary>solc-select instructions</summary>
<ul>
<li><p>Open a terminal and install <code class="docutils literal notranslate"><span class="pre">solc-select</span></code> via <code class="docutils literal notranslate"><span class="pre">pip</span></code>:</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell0"><span></span>pip<span class="w"> </span>install<span class="w"> </span>solc-select
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell0">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</li>
<li><p>Download the required compiler version. For example,
if you want to install version 0.8.0, run:</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell1"><span></span>solc-select<span class="w"> </span>install<span class="w"> </span><span class="m">0</span>.8.0
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell1">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</li>
<li><p>Set <code class="docutils literal notranslate"><span class="pre">solc</span></code> to point to the required compiler version. For example:</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell2"><span></span>solc-select<span class="w"> </span>use<span class="w"> </span><span class="m">0</span>.8.0
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell2">
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
</details>
</section>
<section id="download-binaries">
<span id="index-1"></span><h3><a class="toc-backref" href="#id4" role="doc-backlink">Download binaries</a><a class="headerlink" href="#download-binaries" title="Link to this heading"></a></h3>
<p>You can download the <code class="docutils literal notranslate"><span class="pre">solc</span></code> binaries directly from
<a class="reference external" href="https://github.com/ethereum/solidity/releases">Solidity’s release page on GitHub</a>.</p>
<p>To run the Prover, you may find it useful to add the
<code class="docutils literal notranslate"><span class="pre">solc</span></code> executables folder to your <code class="docutils literal notranslate"><span class="pre">PATH</span></code>. This way
you will not need to provide the Prover with the
full path to the <code class="docutils literal notranslate"><span class="pre">solc</span></code> executables folder every time.</p>
<details class="sd-sphinx-override sd-dropdown sd-card sd-mb-3">
<summary class="sd-summary-title sd-card-header">
<span class="sd-summary-text">Downloading binaries</span><span class="sd-summary-state-marker sd-summary-chevron-right"><svg version="1.1" width="1.5em" height="1.5em" class="sd-octicon sd-octicon-chevron-right" viewBox="0 0 24 24" aria-hidden="true"><path d="M8.72 18.78a.75.75 0 0 1 0-1.06L14.44 12 8.72 6.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018l6.25 6.25a.75.75 0 0 1 0 1.06l-6.25 6.25a.75.75 0 0 1-1.06 0Z"></path></svg></span></summary><div class="sd-summary-content sd-card-body docutils">
<div class="sd-tab-set docutils">
<input checked="checked" id="sd-tab-item-0" name="sd-tab-set-0" type="radio">
<label class="sd-tab-label" data-sync-group="tab" data-sync-id="macos" for="sd-tab-item-0">
macOS</label><div class="sd-tab-content docutils">
<ul>
<li><p class="sd-card-text">Open a terminal and move to the <code class="file docutils literal notranslate"><span class="pre">etc/paths.d</span></code> directory from root:</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell3"><span></span><span class="nb">cd</span><span class="w"> </span>/etc/paths.d
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell3">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</li>
<li><p class="sd-card-text">Use root privileges to create a file with an informative
name such as <code class="docutils literal notranslate"><span class="pre">SolidityCertoraProver</span></code>, and open it with your favorite text editor:</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell4"><span></span>sudo<span class="w"> </span>nano<span class="w"> </span>SolidityCertoraProver
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
<li><p class="sd-card-text">Write the full path to the directory that contains the <code class="docutils literal notranslate"><span class="pre">solc</span></code> executables:</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell5"><span></span>/full/path/to/solc/executable/folder
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell5">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<ul class="simple">
<li><p class="sd-card-text">If needed, more than one path can be added on a single file,
just separate the path with colon a (<code class="docutils literal notranslate"><span class="pre">:</span></code>).</p></li>
</ul>
</li>
<li><p class="sd-card-text">Quit the terminal to load the new addition to <code class="docutils literal notranslate"><span class="pre">$PATH</span></code>,
and reopen to check that the <code class="docutils literal notranslate"><span class="pre">$PATH</span></code> was updated correctly:</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell6"><span></span><span class="nb">echo</span><span class="w"> </span><span class="nv">$PATH</span>
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
</ul>
</div>
<input id="sd-tab-item-1" name="sd-tab-set-0" type="radio">
<label class="sd-tab-label" data-sync-group="tab" data-sync-id="linux" for="sd-tab-item-1">
Linux</label><div class="sd-tab-content docutils">
<ul>
<li><p class="sd-card-text">Open a terminal and make sure you’re in the home directory:</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell7"><span></span><span class="nb">cd</span><span class="w"> </span>~
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell7">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</li>
<li><p class="sd-card-text">open the .profile file with your favorite text editor:</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell8"><span></span>nano<span class="w"> </span>.profile
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell8">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</li>
<li><p class="sd-card-text">At the bottom of the file, add to <code class="docutils literal notranslate"><span class="pre">PATH="..."</span></code> the full
path to the directory that contains the <cite>solc</cite> executables.
To add an additional path just separate with a colon (<code class="docutils literal notranslate"><span class="pre">:</span></code>) :</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell9"><span></span><span class="nv">PATH</span><span class="o">=</span><span class="s2">"</span><span class="nv">$PATH</span><span class="s2">:/full/path/to/solc/executable/folder"</span>
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
<li><p class="sd-card-text">You can make sure that the file was modified correctly by opening
it again with the text editor:</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell10"><span></span>nano<span class="w"> </span>.profile
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell10">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</li>
<li><p class="sd-card-text">Make sure to apply the changes to the <code class="docutils literal notranslate"><span class="pre">$PATH</span></code> by executing the script:</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell11"><span></span><span class="nb">source</span><span class="w"> </span>.profile
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
</ul>
</div>
</div>
</div>
</details></section>
</section>
<section id="installing-the-vyper-compiler">
<span id="index-2"></span><h2><a class="toc-backref" href="#id5" role="doc-backlink">Installing the Vyper compiler</a><a class="headerlink" href="#installing-the-vyper-compiler" title="Link to this heading"></a></h2>
<p><a class="reference external" href="https://github.com/vyperlang/vyper">Vyper</a> is an EVM compatible Pythonic smart contract language.
Since the Certora Prover operates on the bytecode, it can be applied to any source-level language
that compiles to EVM bytecode.
We recommend to install Vyper either from PyPi (i.e., <code class="docutils literal notranslate"><span class="pre">pip</span> <span class="pre">install</span> <span class="pre">vyper</span></code>) or to get a
binary executable for the desired version.</p>
</section>
<section id="installing-the-certora-verification-language-lsp-vs-code-extension">
<span id="index-3"></span><h2><a class="toc-backref" href="#id6" role="doc-backlink">Installing the Certora Verification Language LSP VS Code extension</a><a class="headerlink" href="#installing-the-certora-verification-language-lsp-vs-code-extension" title="Link to this heading"></a></h2>
<p>All users of the Certora Prover can access the tool using the command line
interface, or <a class="reference external" href="https://docs.certora.com/en/latest/docs/prover/cli/index.html">CLI</a>.
Those who use Microsoft’s Visual Studio Code editor (VS Code) also have the
option of using the
<a class="reference external" href="https://marketplace.visualstudio.com/items?itemName=Certora.evmspec-lsp">Certora Verification Language LSP</a>.
This will provide both syntax checking and syntax highlighting for CVL.</p>
<hr class="docutils">
<p>Congratulations! You have just completed Certora Prover’s installation and setup.</p>
<div class="admonition caution">
<p class="admonition-title">Caution</p>
<p>We strongly recommend trying the tool on basic examples to verify correct installation.
See <a class="reference internal" href="running.html"><span class="doc">Running the Certora Prover</span></a> for a detailed walkthrough.</p>
</div>
</section>
</section>


           </div>
          </div>
          <footer><div class="rst-footer-buttons" role="navigation" aria-label="Footer">
        <a href="install.html" class="btn btn-neutral float-left" title="Installation" accesskey="p" rel="prev"><span class="fa fa-arrow-circle-left" aria-hidden="true"></span> Previous</a>
        <a href="tutorials.html" class="btn btn-neutral float-right" title="Tutorial and Workshops" accesskey="n" rel="next">Next <span class="fa fa-arrow-circle-right" aria-hidden="true"></span></a>
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