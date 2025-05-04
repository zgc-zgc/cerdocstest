<!DOCTYPE html><html class="writer-html5" lang="en" data-content_root="../../"><head>
  <meta charset="utf-8"><meta name="viewport" content="width=device-width, initial-scale=1">

  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Using the Solana Certora Prover — Certora Prover Documentation 0.0 documentation</title>
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
    <link rel="next" title="Certora Verification Language for Rust (CVLR)" href="speclanguage.html">
    <link rel="prev" title="Get started with the Solana Certora Prover" href="installation.html"> 
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
<li class="toctree-l1"><a class="reference internal" href="../user-guide/index.html">Certora User’s Guide</a></li>
<li class="toctree-l1"><a class="reference internal" href="../cvl/index.html">The Certora Verification Language</a></li>
<li class="toctree-l1"><a class="reference internal" href="../prover/index.html">The Certora Prover</a></li>
<li class="toctree-l1"><a class="reference internal" href="../sunbeam/index.html">Sunbeam: Verification for Soroban</a></li>
<li class="toctree-l1 current" aria-expanded="true"><a class="reference internal" href="index.html"><button class="toctree-expand" title="Open/close menu"></button>The Certora Solana Prover</a><ul class="" aria-expanded="false">
<li class="toctree-l2"><a class="reference internal" href="installation.html">Get started with the Solana Certora Prover</a></li>
<li class="toctree-l2 current" aria-expanded="true"><a class="reference internal current" href="#" aria-expanded="true"><button class="toctree-expand" title="Open/close menu"></button>Using the Solana Certora Prover</a><ul>
<li class="toctree-l3"><a class="reference internal" href="#overview">Overview</a></li>
<li class="toctree-l3"><a class="reference internal" href="#project-structure">Project Structure</a></li>
<li class="toctree-l3"><a class="reference internal" href="#configuration-formats"><button class="toctree-expand" title="Open/close menu"></button>Configuration Formats</a><ul>
<li class="toctree-l4"><a class="reference internal" href="#verifying-pre-built-contracts">Verifying Pre-Built Contracts</a></li>
<li class="toctree-l4"><a class="reference internal" href="#running-from-sources">Running from Sources</a></li>
</ul>
</li>
<li class="toctree-l3"><a class="reference internal" href="#execution-examples"><button class="toctree-expand" title="Open/close menu"></button>Execution Examples</a><ul>
<li class="toctree-l4"><a class="reference internal" href="#id1">Running from Sources</a></li>
<li class="toctree-l4"><a class="reference internal" href="#id2">Verifying Pre-Built Contracts</a></li>
</ul>
</li>
<li class="toctree-l3"><a class="reference internal" href="#building-the-project"><button class="toctree-expand" title="Open/close menu"></button>Building the Project</a><ul>
<li class="toctree-l4"><a class="reference internal" href="#using-the-build-script-or-command">Using the Build Script or Command</a></li>
<li class="toctree-l4"><a class="reference internal" href="#build-script-or-command-inputs-and-outputs">Build Script or Command Inputs and Outputs</a></li>
</ul>
</li>
</ul>
</li>
<li class="toctree-l2"><a class="reference internal" href="speclanguage.html">Certora Verification Language for Rust (CVLR)</a></li>
<li class="toctree-l2"><a class="reference internal" href="options.html">Solana-Specific Options / CLI Flags</a></li>
<li class="toctree-l2"><a class="reference internal" href="output.html">Understanding Prover Output for Solana Programs</a></li>
<li class="toctree-l2"><a class="reference internal" href="sanity.html">Rule Sanity Checks (Solana)</a></li>
<li class="toctree-l2"><a class="reference internal" href="troubleshooting.html">Troubleshooting</a></li>
</ul>
</li>
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
          <li class="breadcrumb-item"><a href="index.html">The Certora Solana Prover</a></li>
      <li class="breadcrumb-item active">Using the Solana Certora Prover</li>
      <li class="wy-breadcrumbs-aside">
            <a href="../../_sources/docs/solana/usage.md.txt" rel="nofollow"> View page source</a>
      </li>
  </ul>
  <hr>
</div>
          <div role="main" class="document" itemscope="itemscope" itemtype="http://schema.org/Article">
           <div itemprop="articleBody">
             
  <section id="using-the-solana-certora-prover">
<span id="solana-usage"></span><h1>Using the Solana Certora Prover<a class="headerlink" href="#using-the-solana-certora-prover" title="Link to this heading"></a></h1>
<section id="overview">
<h2>Overview<a class="headerlink" href="#overview" title="Link to this heading"></a></h2>
<p>This document provides a guide on how to use the Solana Certora
Prover. It details configuration formats, the build process, and how
to execute verification locally and remotely.</p>
</section>
<section id="project-structure">
<h2>Project Structure<a class="headerlink" href="#project-structure" title="Link to this heading"></a></h2>
<p>A typical Solana project integrated with the Solana Certora Prover includes:</p>
<ul class="simple">
<li><p>A Solana smart contract written in Rust.</p></li>
<li><p>Configurations for running the Certora Prover: the Prover can be executed
either by starting from source files or by verifying pre-compiled code.</p></li>
<li><p>An executable build script or command for compiling the project and preparing
it for verification. This is required only if the code has not already been
pre-compiled.</p></li>
</ul>
<p>The <a class="reference external" href="https://github.com/Certora/SolanaExamples">Certora Solana Examples</a>
repository contains a collection of example projects.</p>
</section>
<section id="configuration-formats">
<h2>Configuration Formats<a class="headerlink" href="#configuration-formats" title="Link to this heading"></a></h2>
<section id="verifying-pre-built-contracts">
<h3>Verifying Pre-Built Contracts<a class="headerlink" href="#verifying-pre-built-contracts" title="Link to this heading"></a></h3>
<p>This configuration mode explicitly specifies the pre-built files required for verification:</p>
<div class="highlight-json notranslate"><div class="highlight"><pre id="codecell0"><span></span><span class="p">{</span>
<span class="w">    </span><span class="nt">"files"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span>
<span class="w">        </span><span class="s2">"solana_contract.so"</span>
<span class="w">    </span><span class="p">],</span>
<span class="w">    </span><span class="nt">"solana_inlining"</span><span class="p">:</span><span class="w"> </span><span class="s2">"../../cvt_inlining.txt"</span><span class="p">,</span>
<span class="w">    </span><span class="nt">"solana_summaries"</span><span class="p">:</span><span class="w"> </span><span class="s2">"../../cvt_summaries.txt"</span><span class="p">,</span>
<span class="w">    </span><span class="nt">"process"</span><span class="p">:</span><span class="w"> </span><span class="s2">"sbf"</span><span class="p">,</span>
<span class="w">    </span><span class="nt">"optimistic_loop"</span><span class="p">:</span><span class="w"> </span><span class="kc">false</span><span class="p">,</span>
<span class="w">    </span><span class="nt">"rule"</span><span class="p">:</span><span class="w"> </span><span class="s2">"rule_solvency"</span>
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
<section id="running-from-sources">
<h3>Running from Sources<a class="headerlink" href="#running-from-sources" title="Link to this heading"></a></h3>
<p>This configuration mode uses a <code class="docutils literal notranslate"><span class="pre">build_script</span></code> or executable command for dynamic project building and eliminates hardcoded file paths:</p>
<div class="highlight-json notranslate"><div class="highlight"><pre id="codecell1"><span></span><span class="p">{</span>
<span class="w">    </span><span class="nt">"build_script"</span><span class="p">:</span><span class="w"> </span><span class="s2">"./certora_build.py"</span><span class="p">,</span>
<span class="w">    </span><span class="nt">"solana_inlining"</span><span class="p">:</span><span class="w"> </span><span class="s2">"../../cvt_inlining.txt"</span><span class="p">,</span>
<span class="w">    </span><span class="nt">"solana_summaries"</span><span class="p">:</span><span class="w"> </span><span class="s2">"../../cvt_summaries.txt"</span><span class="p">,</span>
<span class="w">    </span><span class="nt">"cargo_features"</span><span class="p">:</span><span class="w"> </span><span class="s2">"&lt;feature1&gt; &lt;feature2&gt; &lt;feature3&gt;"</span><span class="p">,</span>
<span class="w">    </span><span class="nt">"process"</span><span class="p">:</span><span class="w"> </span><span class="s2">"sbf"</span><span class="p">,</span>
<span class="w">    </span><span class="nt">"optimistic_loop"</span><span class="p">:</span><span class="w"> </span><span class="kc">false</span><span class="p">,</span>
<span class="w">    </span><span class="nt">"rule"</span><span class="p">:</span><span class="w"> </span><span class="s2">"rule_solvency"</span>
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
<p><strong>Key Differences:</strong></p>
<ul class="simple">
<li><p><strong>Verifying Pre-Built Contracts</strong>: Uses pre-compiled <code class="docutils literal notranslate"><span class="pre">.so</span></code> files for verification.</p></li>
<li><p><strong>Running from Sources</strong>: Automates the build process through the
<code class="docutils literal notranslate"><span class="pre">certora_build.py</span></code> script or another executable
command. See <a class="reference external" href="https://github.com/Certora/SolanaExamples/blob/main/cvlr_by_example/first_example/certora_build.py">here</a> for an example of such a script.</p></li>
</ul>
</section>
</section>
<section id="execution-examples">
<h2>Execution Examples<a class="headerlink" href="#execution-examples" title="Link to this heading"></a></h2>
<section id="id1">
<h3>Running from Sources<a class="headerlink" href="#id1" title="Link to this heading"></a></h3>
<p>To run the Certora Prover using the “running from sources” configuration:</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell2"><span></span>certoraSolanaProver<span class="w"> </span>sources_config.conf
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell2">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p><strong>Expected Output:</strong></p>
<div class="highlight-default notranslate"><div class="highlight"><pre id="codecell3"><span></span><span class="n">INFO</span><span class="p">:</span> <span class="n">Building</span> <span class="kn">from</span> <span class="nn">script</span> <span class="o">./</span><span class="n">certora_build</span><span class="o">.</span><span class="n">py</span>
<span class="n">Connecting</span> <span class="n">to</span> <span class="n">server</span><span class="o">...</span>
<span class="n">Job</span> <span class="n">submitted</span> <span class="n">to</span> <span class="n">server</span><span class="o">.</span>
<span class="n">Manage</span> <span class="n">your</span> <span class="n">jobs</span> <span class="n">at</span> <span class="o">&lt;</span><span class="n">https</span><span class="p">:</span><span class="o">//</span><span class="n">prover</span><span class="o">.</span><span class="n">certora</span><span class="o">.</span><span class="n">com</span><span class="o">&gt;.</span>
<span class="n">Follow</span> <span class="n">your</span> <span class="n">job</span> <span class="ow">and</span> <span class="n">see</span> <span class="n">verification</span> <span class="n">results</span> <span class="n">at</span> <span class="o">&lt;</span><span class="n">https</span><span class="p">:</span><span class="o">//</span><span class="n">prover</span><span class="o">.</span><span class="n">certora</span><span class="o">.</span><span class="n">com</span><span class="o">/</span><span class="n">output</span><span class="o">/</span><span class="p">{</span><span class="n">job_id</span><span class="p">}</span><span class="o">/</span><span class="p">{</span><span class="n">unique_key</span><span class="p">}</span><span class="o">&gt;.</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell3">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
<section id="id2">
<h3>Verifying Pre-Built Contracts<a class="headerlink" href="#id2" title="Link to this heading"></a></h3>
<p>To run the Certora Prover using the “verifying pre-built contracts” configuration:</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell4"><span></span>certoraSolanaProver<span class="w"> </span>prebuilt_config.conf
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell4">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p><strong>Expected Output:</strong></p>
<div class="highlight-default notranslate"><div class="highlight"><pre id="codecell5"><span></span><span class="n">Connecting</span> <span class="n">to</span> <span class="n">server</span><span class="o">...</span>
<span class="n">Job</span> <span class="n">submitted</span> <span class="n">to</span> <span class="n">server</span><span class="o">.</span>
<span class="n">Manage</span> <span class="n">your</span> <span class="n">jobs</span> <span class="n">at</span> <span class="o">&lt;</span><span class="n">https</span><span class="p">:</span><span class="o">//</span><span class="n">prover</span><span class="o">.</span><span class="n">certora</span><span class="o">.</span><span class="n">com</span><span class="o">&gt;.</span>
<span class="n">Follow</span> <span class="n">your</span> <span class="n">job</span> <span class="ow">and</span> <span class="n">see</span> <span class="n">verification</span> <span class="n">results</span> <span class="n">at</span> <span class="o">&lt;</span><span class="n">https</span><span class="p">:</span><span class="o">//</span><span class="n">prover</span><span class="o">.</span><span class="n">certora</span><span class="o">.</span><span class="n">com</span><span class="o">/</span><span class="n">output</span><span class="o">/</span><span class="p">{</span><span class="n">job_id</span><span class="p">}</span><span class="o">/</span><span class="p">{</span><span class="n">unique_key</span><span class="p">}</span><span class="o">&gt;.</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell5">
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
<section id="building-the-project">
<h2>Building the Project<a class="headerlink" href="#building-the-project" title="Link to this heading"></a></h2>
<section id="using-the-build-script-or-command">
<h3>Using the Build Script or Command<a class="headerlink" href="#using-the-build-script-or-command" title="Link to this heading"></a></h3>
<p>The <code class="docutils literal notranslate"><span class="pre">certora_build.py</span></code> script or an equivalent executable command handles project compilation and prepares it for verification. Execute it as follows:</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell6"><span></span>python3<span class="w"> </span>certora_build.py
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell6">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>This ensures the <code class="docutils literal notranslate"><span class="pre">.so</span></code> file is up-to-date and ready for verification.</p>
</section>
<section id="build-script-or-command-inputs-and-outputs">
<h3>Build Script or Command Inputs and Outputs<a class="headerlink" href="#build-script-or-command-inputs-and-outputs" title="Link to this heading"></a></h3>
<p>The script or command connects the project to the Certora Prover by:</p>
<ol class="arabic simple">
<li><p>Compiling the project.</p></li>
<li><p>Returning a JSON object with project details.</p></li>
<li><p>Handling build failures appropriately.</p></li>
</ol>
<section id="inputs">
<h4>Inputs<a class="headerlink" href="#inputs" title="Link to this heading"></a></h4>
<ul class="simple">
<li><p><code class="docutils literal notranslate"><span class="pre">-o/--output</span></code>: Specifies the output JSON file path.</p></li>
<li><p><code class="docutils literal notranslate"><span class="pre">--json</span></code>: Dumps JSON to the console.</p></li>
<li><p><code class="docutils literal notranslate"><span class="pre">-l/--log</span></code>: Displays build logs.</p></li>
<li><p><code class="docutils literal notranslate"><span class="pre">-v/--verbose</span></code>: Enables verbose mode.</p></li>
</ul>
</section>
<section id="outputs">
<h4>Outputs<a class="headerlink" href="#outputs" title="Link to this heading"></a></h4>
<p><strong>Using <code class="docutils literal notranslate"><span class="pre">--json</span></code></strong>
Prints a JSON structure to <code class="docutils literal notranslate"><span class="pre">stdout</span></code>:</p>
<div class="highlight-json notranslate"><div class="highlight"><pre id="codecell7"><span></span><span class="p">{</span>
<span class="w">    </span><span class="nt">"project_directory"</span><span class="p">:</span><span class="w"> </span><span class="s2">"&lt;path&gt;"</span><span class="p">,</span>
<span class="w">    </span><span class="nt">"sources"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="s2">"src/**/*.rs"</span><span class="p">,</span><span class="w"> </span><span class="s2">"Cargo.toml"</span><span class="p">],</span>
<span class="w">    </span><span class="nt">"executables"</span><span class="p">:</span><span class="w"> </span><span class="s2">"target/release/solana_contract.so"</span><span class="p">,</span>
<span class="w">    </span><span class="nt">"success"</span><span class="p">:</span><span class="w"> </span><span class="kc">true</span><span class="p">,</span>
<span class="w">    </span><span class="nt">"return_code"</span><span class="p">:</span><span class="w"> </span><span class="mi">0</span><span class="p">,</span>
<span class="w">    </span><span class="nt">"log"</span><span class="p">:</span><span class="w"> </span><span class="p">{</span>
<span class="w">        </span><span class="nt">"stdout"</span><span class="p">:</span><span class="w"> </span><span class="s2">"path/to/stdout"</span><span class="p">,</span>
<span class="w">        </span><span class="nt">"stderr"</span><span class="p">:</span><span class="w"> </span><span class="s2">"path/to/stderr"</span>
<span class="w">    </span><span class="p">}</span>
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
<p><strong>Using <code class="docutils literal notranslate"><span class="pre">--output</span></code></strong>
Saves the JSON structure to the file specified by the <code class="docutils literal notranslate"><span class="pre">--output</span></code> flag.</p>
<p><strong>Without <code class="docutils literal notranslate"><span class="pre">--json</span></code> or <code class="docutils literal notranslate"><span class="pre">--output</span></code></strong>
Returns <code class="docutils literal notranslate"><span class="pre">0</span></code> if the build is successful and <code class="docutils literal notranslate"><span class="pre">1</span></code> otherwise.</p>
</section>
</section>
</section>
</section>


           </div>
          </div>
          <footer><div class="rst-footer-buttons" role="navigation" aria-label="Footer">
        <a href="installation.html" class="btn btn-neutral float-left" title="Get started with the Solana Certora Prover" accesskey="p" rel="prev"><span class="fa fa-arrow-circle-left" aria-hidden="true"></span> Previous</a>
        <a href="speclanguage.html" class="btn btn-neutral float-right" title="Certora Verification Language for Rust (CVLR)" accesskey="n" rel="next">Next <span class="fa fa-arrow-circle-right" aria-hidden="true"></span></a>
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