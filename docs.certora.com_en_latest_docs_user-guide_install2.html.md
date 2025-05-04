<!DOCTYPE html><html class="writer-html5" lang="en" data-content_root="../../"><head>
  <meta charset="utf-8"><meta name="viewport" content="width=device-width, initial-scale=1">

  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Installation — Certora Prover Documentation 0.0 documentation</title>
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
    <link rel="next" title="Installing an EVM compiler and VS Code Extension" href="install_evm_compiler.html">
    <link rel="prev" title="Certora User’s Guide" href="index.html"> 
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
<li class="toctree-l2 current" aria-expanded="true"><a class="reference internal current" href="#" aria-expanded="true"><button class="toctree-expand" title="Open/close menu"></button>Installation</a><ul>
<li class="toctree-l3"><a class="reference internal" href="#step-1-prerequisites">Step 1: Prerequisites</a></li>
<li class="toctree-l3"><a class="reference internal" href="#step-2-install-the-certora-prover-package">Step 2: Install the Certora Prover package</a></li>
<li class="toctree-l3"><a class="reference internal" href="#installing-the-beta-version-optional">Installing the beta version (optional)</a></li>
<li class="toctree-l3"><a class="reference internal" href="#step-3-set-the-personal-access-key-as-an-environment-variable">Step 3: Set the personal access key as an environment variable</a></li>
<li class="toctree-l3"><a class="reference internal" href="#step-4-for-github-users-configure-syntax-highlighting">Step 4 (for GitHub users): Configure Syntax Highlighting</a></li>
</ul>
</li>
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
      <li class="breadcrumb-item active">Installation</li>
      <li class="wy-breadcrumbs-aside">
            <a href="../../_sources/docs/user-guide/install.md.txt" rel="nofollow"> View page source</a>
      </li>
  </ul>
  <hr>
</div>
          <div role="main" class="document" itemscope="itemscope" itemtype="http://schema.org/Article">
           <div itemprop="articleBody">
             
  <section id="installation">
<span id="index-0"></span><span id="id1"></span><h1>Installation<a class="headerlink" href="#installation" title="Link to this heading"></a></h1>
<section id="step-1-prerequisites">
<h2>Step 1: Prerequisites<a class="headerlink" href="#step-1-prerequisites" title="Link to this heading"></a></h2>
<details>
  <summary>Python3.8.16 or newer</summary>
<p>Check your Python3 version by executing the following command on the
terminal:</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell0"><span></span>python3<span class="w"> </span>--version
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell0">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>If the version is &lt; 3.8.16, follow the <a class="reference external" href="https://wiki.python.org/moin/BeginnersGuide/Download">Python installation guide</a> to upgrade.</p>
</details>
<details>
  <summary>Java Development Kit (JDK) 11 or newer</summary>
<p>Check your Java version by executing the following command on the terminal:</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell1"><span></span>java<span class="w"> </span>-version
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell1">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>If the version is &lt; 11, download and install Java version 11 or later from
<a class="reference external" href="https://www.oracle.com/java/technologies/downloads/">Oracle</a>.</p>
</details>
<details>
  <summary>Solidity compiler&nbsp;(ideally v0.5 and up)</summary>
<ul class="simple">
<li><p>We recommend using <a class="reference external" href="https://github.com/crytic/solc-select">solc-select</a>
to download and switch between Solidity compiler versions.</p></li>
<li><p>You can also download the Solidity compiler binaries from the
<a class="reference external" href="https://github.com/ethereum/solidity/releases">official Solidity repository</a> on GitHub.
It is best to place all the <code class="docutils literal notranslate"><span class="pre">solc</span></code> binaries in the same path.</p></li>
<li><p>Certora employees can clone the <code class="docutils literal notranslate"><span class="pre">CVT_Executables</span></code> repository suitable for
their OS from <a class="reference external" href="https://github.com/orgs/Certora/repositories">GitHub</a>.</p></li>
</ul>
</details>
</section>
<section id="step-2-install-the-certora-prover-package">
<h2>Step 2: Install the Certora Prover package<a class="headerlink" href="#step-2-install-the-certora-prover-package" title="Link to this heading"></a></h2>
<div class="admonition tip">
<p class="admonition-title">Tip</p>
<p>It is always recommended to use a Python virtual environment,
such as <a class="reference external" href="https://docs.python.org/3.10/library/venv.html">venv</a> or <a class="reference external" href="https://virtualenv.pypa.io/en/latest/">virtualenv</a>,
when installing a Python package.</p>
</div>
<p>Execute the following command at the terminal to install the Prover:</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell2"><span></span>pip3<span class="w"> </span>install<span class="w"> </span>certora-cli
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell2">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<div class="admonition caution">
<p class="admonition-title">Caution</p>
<p>Note that the terminal may prompt you with a warning that some files, e.g.
python3.x, are not included in the <code class="docutils literal notranslate"><span class="pre">PATH</span></code>, and should be added. Add these files
to <code class="docutils literal notranslate"><span class="pre">PATH</span></code> to avoid errors.</p>
</div>
<p>The following section presents some, but maybe not all, possible warnings that
can arise during installation and how to deal with them:</p>
<details class="sd-sphinx-override sd-dropdown sd-card sd-mb-3">
<summary class="sd-summary-title sd-card-header">
<span class="sd-summary-text">Troubleshooting warnings</span><span class="sd-summary-state-marker sd-summary-chevron-right"><svg version="1.1" width="1.5em" height="1.5em" class="sd-octicon sd-octicon-chevron-right" viewBox="0 0 24 24" aria-hidden="true"><path d="M8.72 18.78a.75.75 0 0 1 0-1.06L14.44 12 8.72 6.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018l6.25 6.25a.75.75 0 0 1 0 1.06l-6.25 6.25a.75.75 0 0 1-1.06 0Z"></path></svg></span></summary><div class="sd-summary-content sd-card-body docutils">
<div class="sd-tab-set docutils">
<input checked="checked" id="sd-tab-item-0" name="sd-tab-set-0" type="radio">
<label class="sd-tab-label" data-sync-group="tab" data-sync-id="macos" for="sd-tab-item-0">
macOS</label><div class="sd-tab-content docutils">
<div class="literal-block-wrapper docutils container" id="id2">
<div class="code-block-caption"><span class="caption-text">The warning</span><a class="headerlink" href="#id2" title="Link to this code"></a></div>
<div class="highlight-text notranslate"><div class="highlight"><pre id="codecell3"><span></span>The script certoraRun is installed in /Users/&lt;user name&gt;/Library/Python/3.8/bin
which is not on PATH. Consider adding this directory to PATH.
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
<ul>
<li><p class="sd-card-text">Open a terminal and move to the <code class="file docutils literal notranslate"><span class="pre">etc/paths.d</span></code> directory from root:</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell4"><span></span><span class="nb">cd</span><span class="w"> </span>/etc/paths.d
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
<li><p class="sd-card-text">Use root privileges to create a file with an informative name such as
<code class="docutils literal notranslate"><span class="pre">PythonForProver</span></code>, and open it with your favorite text editor:</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell5"><span></span>sudo<span class="w"> </span>nano<span class="w"> </span>PythonForProver
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell5">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</li>
<li><p class="sd-card-text">Write the specified path from the warning:</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell6"><span></span>/specified/path/in/warning
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
<li><p class="sd-card-text">If needed, more than one path can be added on a single file,
just separate the path with a colon (<code class="docutils literal notranslate"><span class="pre">:</span></code>).</p></li>
<li><p class="sd-card-text">Quit the terminal to load the new addition to <code class="docutils literal notranslate"><span class="pre">$PATH</span></code>,
and reopen to check that the <code class="docutils literal notranslate"><span class="pre">$PATH</span></code> was updated correctly:</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell7"><span></span><span class="nb">echo</span><span class="w"> </span><span class="nv">$PATH</span>
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
</ul>
</div>
<input id="sd-tab-item-1" name="sd-tab-set-0" type="radio">
<label class="sd-tab-label" data-sync-group="tab" data-sync-id="linux" for="sd-tab-item-1">
Linux</label><div class="sd-tab-content docutils">
<div class="literal-block-wrapper docutils container" id="id3">
<div class="code-block-caption"><span class="caption-text">The warning</span><a class="headerlink" href="#id3" title="Link to this code"></a></div>
<div class="highlight-text notranslate"><div class="highlight"><pre id="codecell8"><span></span>The script certoraRun is installed in /home/&lt;user name&gt;/.local/bin
which is not on PATH. Consider adding this directory to PATH.
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell8">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</div>
<ul>
<li><p class="sd-card-text">Open a terminal and make sure you’re in the home directory:</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell9"><span></span><span class="nb">cd</span><span class="w"> </span>~
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
<li><p class="sd-card-text">open the .profile file with your favorite text editor:</p>
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
<li><p class="sd-card-text">At the bottom of the file, add to <code class="docutils literal notranslate"><span class="pre">PATH="..."</span></code> the specified path
from the warning. To add an additional path just separate with a colon (<cite>:</cite>) :</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell11"><span></span><span class="nv">PATH</span><span class="o">=</span><span class="s2">"</span><span class="nv">$PATH</span><span class="s2">:/specified/path/in/warning"</span>
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
<li><p class="sd-card-text">You can make sure that the file was modified correctly by opening it again
with the text editor:</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell12"><span></span>nano<span class="w"> </span>.profile
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
<li><p class="sd-card-text">Make sure to apply the changes to the <code class="docutils literal notranslate"><span class="pre">$PATH</span></code> by executing the script:</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell13"><span></span><span class="nb">source</span><span class="w"> </span>.profile
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
</div>
</div>
</div>
</details></section>
<section id="installing-the-beta-version-optional">
<span id="beta-install"></span><span id="index-2"></span><h2>Installing the beta version (optional)<a class="headerlink" href="#installing-the-beta-version-optional" title="Link to this heading"></a></h2>
<p>If you wish to install a pre-release version, you can do so by installing
<code class="docutils literal notranslate"><span class="pre">certora-cli-beta</span></code> instead of <code class="docutils literal notranslate"><span class="pre">certora-cli</span></code>.  We do not recommend having both
packages installed simultaneously, so you should remove the <code class="docutils literal notranslate"><span class="pre">certora-cli</span></code>
package before installing <code class="docutils literal notranslate"><span class="pre">certora-cli-beta</span></code>:</p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell14"><span></span>pip<span class="w"> </span>uninstall<span class="w"> </span>certora-cli
pip<span class="w"> </span>install<span class="w"> </span>certora-cli-beta
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell14">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>If you wish to easily switch between the beta and the production versions, you
can use a <a class="reference external" href="https://virtualenv.pypa.io/en/latest/">python virtual environment</a>:</p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell15"><span></span>pip<span class="w"> </span>install<span class="w"> </span>virtualenv
virtualenv<span class="w"> </span>certora-beta
<span class="nb">source</span><span class="w"> </span>certora-beta/bin/activate
pip3<span class="w"> </span>install<span class="w"> </span>certora-cli-beta
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell15">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>You can then switch to the standard CVL release by running <code class="docutils literal notranslate"><span class="pre">deactivate</span></code>, and
back to the beta release using <code class="docutils literal notranslate"><span class="pre">certora-beta/bin/activate</span></code>.</p>
</section>
<section id="step-3-set-the-personal-access-key-as-an-environment-variable">
<span id="installation-step-3"></span><h2>Step 3: Set the personal access key as an environment variable<a class="headerlink" href="#step-3-set-the-personal-access-key-as-an-environment-variable" title="Link to this heading"></a></h2>
<p>The Certora Prover requires a personal access key.
You can get a free personal access key by registering on the
<a class="reference external" href="https://www.certora.com/signup?plan=prover">Certora website</a>.</p>
<p>Before running the Prover,
you should register your access key as a system variable.
To do so on macOS or Linux machines,
execute the following command on the terminal:</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell16"><span></span><span class="nb">export</span><span class="w"> </span><span class="nv">CERTORAKEY</span><span class="o">=</span>&lt;personal_access_key&gt;
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell16">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>This command sets a temporary variable that will be unset once the terminal is
closed. We recommended storing the access key in an environment variable named
<code class="docutils literal notranslate"><span class="pre">CERTORAKEY</span></code>. This way, you will no longer need to execute the above command
whenever you open a terminal. To set an environment variable permanently,
follow the next steps:</p>
<div class="sd-tab-set docutils">
<input checked="checked" id="sd-tab-item-2" name="sd-tab-set-1" type="radio">
<label class="sd-tab-label" data-sync-group="tab" data-sync-id="macos" for="sd-tab-item-2">
macOS</label><div class="sd-tab-content docutils">
<ul>
<li><p>Open a terminal and make sure you’re in the home directory:</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell17"><span></span><span class="nb">cd</span><span class="w"> </span>~
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell17">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</li>
<li><p>Create a file with the name <code class="docutils literal notranslate"><span class="pre">.zshenv</span></code> and open it with your favorite text editor:</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell18"><span></span>nano<span class="w"> </span>.zshenv
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell18">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</li>
<li><p>Write the export command from the beginning of step 3,
save and quit (<code class="docutils literal notranslate"><span class="pre">ctrl+x</span></code> on <code class="docutils literal notranslate"><span class="pre">nano</span></code>).</p></li>
<li><p>You can make sure that the file was created correctly by
seeing it listed on the directory or by opening it again with the text editor:</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell19"><span></span>ls<span class="w"> </span>-a
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell19">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>OR</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell20"><span></span>nano<span class="w"> </span>.zshenv
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell20">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</li>
<li><p>Make sure to apply the environment variable you’ve just created by executing the script:</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell21"><span></span><span class="nb">source</span><span class="w"> </span>.zshenv
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell21">
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
<p>When running the Certora Prover in the Visual Studio Code Extension, you may need
to restart VSCode or your computer.</p>
</div>
<input id="sd-tab-item-3" name="sd-tab-set-1" type="radio">
<label class="sd-tab-label" data-sync-group="tab" data-sync-id="linux" for="sd-tab-item-3">
Linux</label><div class="sd-tab-content docutils">
<ul>
<li><p>Open a terminal and make sure you’re in the home directory:</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell22"><span></span><span class="nb">cd</span><span class="w"> </span>~
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell22">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</li>
<li><p>open the .profile file with your favorite text editor:</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell23"><span></span>nano<span class="w"> </span>.profile
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell23">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</li>
<li><p>At the bottom of the file, under the <code class="docutils literal notranslate"><span class="pre">PATH="..."</span></code> insert
the export command from the beginning of step 3, save and quit (<code class="docutils literal notranslate"><span class="pre">ctrl+x</span></code> on <code class="docutils literal notranslate"><span class="pre">nano</span></code>).</p></li>
<li><p>You can make sure that the file was modified correctly by
opening it again with the text editor:</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell24"><span></span>nano<span class="w"> </span>.profile
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell24">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</li>
<li><p>Make sure to apply the environment variable you’ve just created by executing the script:</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell25"><span></span><span class="nb">source</span><span class="w"> </span>.profile
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell25">
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
</section>
<section id="step-4-for-github-users-configure-syntax-highlighting">
<h2>Step 4 (for GitHub users): Configure Syntax Highlighting<a class="headerlink" href="#step-4-for-github-users-configure-syntax-highlighting" title="Link to this heading"></a></h2>
<p><a class="reference internal" href="github_highlighting.html"><span class="std std-doc">Follow our guide</span></a> to configure syntax highlighting on GitHub for CVL and configuration files.</p>
</section>
</section>


           </div>
          </div>
          <footer><div class="rst-footer-buttons" role="navigation" aria-label="Footer">
        <a href="index.html" class="btn btn-neutral float-left" title="Certora User’s Guide" accesskey="p" rel="prev"><span class="fa fa-arrow-circle-left" aria-hidden="true"></span> Previous</a>
        <a href="install_evm_compiler.html" class="btn btn-neutral float-right" title="Installing an EVM compiler and VS Code Extension" accesskey="n" rel="next">Next <span class="fa fa-arrow-circle-right" aria-hidden="true"></span></a>
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