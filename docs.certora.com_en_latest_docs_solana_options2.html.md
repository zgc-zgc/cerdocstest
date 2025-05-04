<!DOCTYPE html><html class="writer-html5" lang="en" data-content_root="../../"><head>
  <meta charset="utf-8"><meta name="viewport" content="width=device-width, initial-scale=1">

  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Solana-Specific Options / CLI Flags — Certora Prover Documentation 0.0 documentation</title>
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
    <link rel="next" title="Understanding Prover Output for Solana Programs" href="output.html">
    <link rel="prev" title="Certora Verification Language for Rust (CVLR)" href="speclanguage.html"> 
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
<li class="toctree-l2"><a class="reference internal" href="usage.html">Using the Solana Certora Prover</a></li>
<li class="toctree-l2"><a class="reference internal" href="speclanguage.html">Certora Verification Language for Rust (CVLR)</a></li>
<li class="toctree-l2 current" aria-expanded="true"><a class="reference internal current" href="#" aria-expanded="true"><button class="toctree-expand" title="Open/close menu"></button>Solana-Specific Options / CLI Flags</a><ul>
<li class="toctree-l3"><a class="reference internal" href="#using-configuration-conf-files">Using Configuration (Conf) Files</a></li>
<li class="toctree-l3"><a class="reference internal" href="#modes-of-operation"><button class="toctree-expand" title="Open/close menu"></button>Modes of Operation</a><ul>
<li class="toctree-l4"><a class="reference internal" href="#build-script"><code class="docutils literal notranslate"><span class="pre">--build_script</span></code></a></li>
</ul>
</li>
<li class="toctree-l3"><a class="reference internal" href="#most-frequently-used-options"><button class="toctree-expand" title="Open/close menu"></button>Most Frequently Used Options</a><ul>
<li class="toctree-l4"><a class="reference internal" href="#rule"><code class="docutils literal notranslate"><span class="pre">--rule</span></code></a></li>
<li class="toctree-l4"><a class="reference internal" href="#solana-inlining"><code class="docutils literal notranslate"><span class="pre">--solana_inlining</span></code></a></li>
<li class="toctree-l4"><a class="reference internal" href="#solana-summaries"><code class="docutils literal notranslate"><span class="pre">--solana_summaries</span></code></a></li>
<li class="toctree-l4"><a class="reference internal" href="#cargo-features"><code class="docutils literal notranslate"><span class="pre">--cargo_features</span></code></a></li>
<li class="toctree-l4"><a class="reference internal" href="#msg"><code class="docutils literal notranslate"><span class="pre">--msg</span></code></a></li>
<li class="toctree-l4"><a class="reference internal" href="#rule-sanity"><code class="docutils literal notranslate"><span class="pre">--rule_sanity</span></code></a></li>
</ul>
</li>
<li class="toctree-l3"><a class="reference internal" href="#multi-assert-check"><code class="docutils literal notranslate"><span class="pre">--multi_assert_check</span></code></a></li>
</ul>
</li>
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
      <li class="breadcrumb-item active">Solana-Specific Options / CLI Flags</li>
      <li class="wy-breadcrumbs-aside">
            <a href="../../_sources/docs/solana/options.md.txt" rel="nofollow"> View page source</a>
      </li>
  </ul>
  <hr>
</div>
          <div role="main" class="document" itemscope="itemscope" itemtype="http://schema.org/Article">
           <div itemprop="articleBody">
             
  <section id="solana-specific-options-cli-flags">
<h1>Solana-Specific Options / CLI Flags<a class="headerlink" href="#solana-specific-options-cli-flags" title="Link to this heading"></a></h1>
<p>This page documents Solana-specific Certora Prover options, which include CLI flags or <code class="docutils literal notranslate"><span class="pre">prover_args</span></code> flags.</p>
<p>The <code class="docutils literal notranslate"><span class="pre">certoraSolanaProver</span></code> utility invokes the Rust compiler and then sends the job to Certora’s servers.</p>
<p>The most commonly used command is:</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell0"><span></span>certoraSolanaProver<span class="w"> </span>--build_script<span class="w"> </span>&lt;path_to_build_script&gt;<span class="w"> </span>--rule<span class="w"> </span>&lt;rule_name&gt;
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell0">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>If a precompiled execution is desired, the run command can skip the compilation step by executing:</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell1"><span></span>certoraSolanaProver<span class="w"> </span>&lt;path_to_binary_file&gt;<span class="w"> </span>--rule<span class="w"> </span>&lt;rule_name&gt;
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell1">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>A short summary of these options can be seen by invoking:</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell2"><span></span>certoraSolanaProver<span class="w"> </span>--help
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell2">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<section id="using-configuration-conf-files">
<h2>Using Configuration (Conf) Files<a class="headerlink" href="#using-configuration-conf-files" title="Link to this heading"></a></h2>
<p>For larger projects, the command line for running the Certora Prover can become large and cumbersome. It is therefore recommended to use configuration files instead.
These files are in <a class="reference external" href="https://json5.org/">JSON5</a> format and use a <code class="docutils literal notranslate"><span class="pre">.conf</span></code> extension. They hold the parameters and options for the Prover.
For more details, see <a class="reference external" href="https://docs.certora.com/en/latest/docs/prover/cli/conf-file-api.html#conf-files">Conf File</a>.</p>
</section>
<section id="modes-of-operation">
<h2>Modes of Operation<a class="headerlink" href="#modes-of-operation" title="Link to this heading"></a></h2>
<p>The Certora Solana Prover has two modes of operation, using a build script, or passing a precompiled binary directly.
These modes are mutually exclusive - you cannot run the tool with more than one mode at a time.
Both modes require the user to specify which rules must be verified by using the <code class="docutils literal notranslate"><span class="pre">--rule</span></code> option.</p>
<section id="build-script">
<h3><code class="docutils literal notranslate"><span class="pre">--build_script</span></code><a class="headerlink" href="#build-script" title="Link to this heading"></a></h3>
<p><strong>What does it do?</strong></p>
<p>Specifies the location of the script that has to be called to compile the Rust project.
The build script should output 0 on success and 1 on failure unless it’s being executed using the <code class="docutils literal notranslate"><span class="pre">--json</span></code> flag.
In this case, the build script should output the following:</p>
<ul class="simple">
<li><p><code class="docutils literal notranslate"><span class="pre">project_directory</span></code>: Path to the project root directory.</p></li>
<li><p><code class="docutils literal notranslate"><span class="pre">sources</span></code>: List of source files or directories used or imported in the program. Source files should be relative to the <code class="docutils literal notranslate"><span class="pre">project_directory</span></code> with support of wildcards. All files declared in this list will be uploaded as sources to the cloud and displayed in the rule report. Source files are required, for instance, for the jump to source feature to work.</p></li>
<li><p><code class="docutils literal notranslate"><span class="pre">executables</span></code>: List of compiled binary files, which are the target of the Rust program.</p></li>
<li><p><code class="docutils literal notranslate"><span class="pre">success</span></code>: Boolean flag indicating if the build phase passed successfully.</p></li>
<li><p><code class="docutils literal notranslate"><span class="pre">return_code</span></code>: The return code of the script.</p></li>
<li><p><code class="docutils literal notranslate"><span class="pre">log</span></code>: Optionally provided paths to files for <code class="docutils literal notranslate"><span class="pre">stdout</span></code> and <code class="docutils literal notranslate"><span class="pre">stderr</span></code> of the build logs.</p></li>
<li><p><code class="docutils literal notranslate"><span class="pre">solana_inlining</span></code>: List of paths to <a class="reference internal" href="#solana-inlining">inlining</a> files for Solana programs.</p></li>
<li><p><code class="docutils literal notranslate"><span class="pre">solana_summaries</span></code>: List of paths to <a class="reference internal" href="#solana-summaries">summaries</a> files for Solana programs.</p></li>
</ul>
<p>See an example of a <a class="reference external" href="https://github.com/Certora/SolanaExamples/blob/main/cvlr_by_example/first_example/certora_build.py">build script</a> and refer to the
<a class="reference internal" href="usage.html"><span class="std std-doc">usage</span></a> section for more information about it.</p>
<p><strong>When to use it?</strong></p>
<p>Use this mode to prove properties on source code while providing an automatic compilation method. This is especially useful during development when files are modified frequently.</p>
<p><strong>Example</strong></p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell3"><span></span>certoraSolanaProver<span class="w"> </span>--build_script<span class="w"> </span>&lt;path_to_build_script&gt;<span class="w"> </span>--rule<span class="w"> </span>&lt;rule_name&gt;
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell3">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>Note: If you want to skip compilation process and run on a precompiled Rust project it’s possible to provide a path to the binary target file instead</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell4"><span></span>certoraSolanaProver<span class="w"> </span>&lt;path_to_binary_file&gt;<span class="w"> </span>--rule<span class="w"> </span>&lt;rule_name&gt;
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell4">
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
<section id="most-frequently-used-options">
<h2>Most Frequently Used Options<a class="headerlink" href="#most-frequently-used-options" title="Link to this heading"></a></h2>
<section id="rule">
<h3><code class="docutils literal notranslate"><span class="pre">--rule</span></code><a class="headerlink" href="#rule" title="Link to this heading"></a></h3>
<p><strong>What does it do?</strong></p>
<p>Formally verifies one or more specified rules.</p>
<p><strong>When to use it?</strong></p>
<p>This option is always required to specify which rules the Prover should verify.</p>
<p><strong>Example</strong></p>
<p>If a Rust module includes the following:</p>
<div class="highlight-rust notranslate"><div class="highlight"><pre id="codecell5"><span></span><span class="cp">#[rule]</span>
<span class="k">fn</span><span class="w"> </span><span class="nf">rule_withdraw_succeeds</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="o">..</span><span class="p">.</span>
<span class="p">}</span>

<span class="cp">#[rule]</span>
<span class="k">fn</span><span class="w"> </span><span class="nf">rule_withdraw_fails</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="o">..</span><span class="p">.</span>
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
<p>To verify only <code class="docutils literal notranslate"><span class="pre">rule_withdraw_succeeds</span></code>, run:</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell6"><span></span>certoraSolanaProver<span class="w"> </span>--build_script<span class="w"> </span>&lt;path_to_build_script&gt;<span class="w"> </span>--rule<span class="w"> </span>rule_withdraw_succeeds
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell6">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>To verify both <code class="docutils literal notranslate"><span class="pre">rule_withdraw_succeeds</span></code> and <code class="docutils literal notranslate"><span class="pre">rule_withdraw_fails</span></code>, run:</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell7"><span></span>certoraSolanaProver<span class="w"> </span>--build_script<span class="w"> </span>&lt;path_to_build_script&gt;<span class="w"> </span>--rule<span class="w"> </span>rule_withdraw_succeeds<span class="w"> </span>rule_withdraw_fails
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell7">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
<section id="solana-inlining">
<span id="id1"></span><h3><code class="docutils literal notranslate"><span class="pre">--solana_inlining</span></code><a class="headerlink" href="#solana-inlining" title="Link to this heading"></a></h3>
<p><strong>What does it do?</strong></p>
<p>Provides the Prover with a list of paths to inlining files for Solana programs.
These files are parsed and used to prove properties.
See an <a class="reference external" href="https://github.com/Certora/SolanaExamples/blob/main/cvlr_by_example/first_example/certora/inlining.txt">example</a>.</p>
<p><strong>When to use it?</strong></p>
<p>This option is currently required for every project.
It can be provided to the Prover by passing this list as a flag or by retrieving it from the build script.</p>
<p><strong>Example</strong></p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell8"><span></span>certoraSolanaProver<span class="w"> </span>--build_script<span class="w"> </span>&lt;path_to_build_script&gt;<span class="w"> </span>--solana_inlining<span class="w"> </span>&lt;path_to_inlining_file&gt;<span class="w">  </span>--rule<span class="w"> </span>&lt;rule_name&gt;
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell8">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
<section id="solana-summaries">
<span id="id2"></span><h3><code class="docutils literal notranslate"><span class="pre">--solana_summaries</span></code><a class="headerlink" href="#solana-summaries" title="Link to this heading"></a></h3>
<p><strong>What does it do?</strong></p>
<p>Provides the Prover with a list of paths to summary files for Solana contracts.
These files are parsed and used to prove properties.
See an <a class="reference external" href="https://github.com/Certora/SolanaExamples/blob/main/cvlr_by_example/first_example/certora/summaries.txt">example</a>.</p>
<p><strong>When to use it?</strong></p>
<p>This option is currently required for every project.
It can be provided to the Prover by passing this list as a flag or by retrieving it from the build script.</p>
<p><strong>Example</strong></p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell9"><span></span>certoraSolanaProver<span class="w"> </span>--build_script<span class="w"> </span>&lt;path_to_build_script&gt;<span class="w"> </span>--solana_summaries<span class="w"> </span>&lt;path_to_summaries_file&gt;<span class="w"> </span>--rule<span class="w"> </span>&lt;rule_name&gt;
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell9">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
<section id="cargo-features">
<h3><code class="docutils literal notranslate"><span class="pre">--cargo_features</span></code><a class="headerlink" href="#cargo-features" title="Link to this heading"></a></h3>
<p><strong>What does it do?</strong></p>
<p>Provides the Prover with a whitespace-separated list of extra <a class="reference external" href="https://doc.rust-lang.org/cargo/reference/features.html">Cargo features</a> passed to the build script.
These features are then passed to <code class="docutils literal notranslate"><span class="pre">cargo</span></code> to build the project.</p>
<p><strong>When to use it?</strong></p>
<p>Use it when there is a need to enable a specific <a class="reference external" href="https://doc.rust-lang.org/cargo/reference/features.html">Cargo feature</a> to compile the source code.</p>
<p><strong>Example</strong></p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell10"><span></span>certoraSolanaProver<span class="w"> </span>--build_script<span class="w"> </span>&lt;path_to_build_script&gt;<span class="w"> </span>--cargo_features<span class="w"> </span>&lt;feature_1&gt;<span class="w"> </span>&lt;feature_2&gt;<span class="w"> </span>--rule<span class="w"> </span>&lt;rule_name&gt;
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell10">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
<section id="msg">
<h3><code class="docutils literal notranslate"><span class="pre">--msg</span></code><a class="headerlink" href="#msg" title="Link to this heading"></a></h3>
<p><strong>What does it do?</strong></p>
<p>Adds a description message to your run, similar to a commit message. This message appears on the Prover dashboard and in the rule report.
Note that you need to wrap your message in quotes if it contains spaces.</p>
<p><strong>When to use it?</strong></p>
<p>Adding a message makes it easier to track several runs on <a class="reference external" href="https://prover.certora.com/">the Prover Dashboard</a>. It is very useful if you are running many verifications simultaneously.
It is also helpful to keep track of a single file verification status over time, so we recommend always providing an informative message.</p>
<p><strong>Example</strong></p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell11"><span></span>certoraSolanaProver<span class="w"> </span>--build_script<span class="w"> </span>&lt;path_to_build_script&gt;<span class="w"> </span>--msg<span class="w"> </span><span class="s1">'Removed an assertion'</span><span class="w"> </span>--rule<span class="w"> </span>&lt;rule_name&gt;
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell11">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
<section id="rule-sanity">
<h3><code class="docutils literal notranslate"><span class="pre">--rule_sanity</span></code><a class="headerlink" href="#rule-sanity" title="Link to this heading"></a></h3>
<p><strong>What does it do?</strong></p>
<p>When used with <code class="docutils literal notranslate"><span class="pre">--rule_sanity:</span> <span class="pre">basic</span></code>, this flag executes a job in sanity mode which performs a vacuity check for a rule.</p>
<p><strong>When to use it?</strong></p>
<p>Sanity mode is helpful to check for the correctness of a rule. For details, see also <a class="reference internal" href="sanity.html"><span class="std std-doc">Rule Sanity Checks</span></a>.</p>
<p><strong>Example</strong></p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell12"><span></span>certoraSolanaProver<span class="w"> </span>--build_script<span class="w"> </span>&lt;path_to_build_script&gt;<span class="w"> </span>--rule_sanity<span class="w"> </span>basic
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell12">
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
<section id="multi-assert-check">
<h2><code class="docutils literal notranslate"><span class="pre">--multi_assert_check</span></code><a class="headerlink" href="#multi-assert-check" title="Link to this heading"></a></h2>
<p><strong>What does it do?</strong>
This flags translates each assertion statement in a rule into a separate verification task. All preceding assertions are assumed to be true - they are hence translated into assume statements.
An example can be found <a class="reference external" href="https://github.com/Certora/SolanaExamples/blob/66c1f406755893db5a081f39ca5cdd583a6f9991/cvlr_by_example/first_example/certora/conf/MultiAssertMode.conf">here</a>.</p>
<div class="admonition caution">
<p class="admonition-title">Caution</p>
<p>We suggest using this mode carefully. In general, as this mode generates generates one verification task per assert, it may lead to worse running-time performance. Please see indications for use below.</p>
</div>
<p><strong>When to use it?</strong>
When you have a rule with multiple assertions:</p>
<ol class="arabic simple">
<li><p>As a timeout mitigation strategy: checking each assertion separately may, in some cases, perform better than checking all the assertions together and consequently solve timeouts. For instance, you can identify complex to verify asserts in a rule.</p></li>
<li><p>If you wish to get multiple counter-examples in a single run of the tool, where each counter-example violates a different assertion in the rule.</p></li>
</ol>
<p><strong>Example</strong></p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell13"><span></span>certoraSolanaProver<span class="w"> </span>--build_script<span class="w"> </span>&lt;path_to_build_script&gt;<span class="w"> </span>--multi_assert_check
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
</section>


           </div>
          </div>
          <footer><div class="rst-footer-buttons" role="navigation" aria-label="Footer">
        <a href="speclanguage.html" class="btn btn-neutral float-left" title="Certora Verification Language for Rust (CVLR)" accesskey="p" rel="prev"><span class="fa fa-arrow-circle-left" aria-hidden="true"></span> Previous</a>
        <a href="output.html" class="btn btn-neutral float-right" title="Understanding Prover Output for Solana Programs" accesskey="n" rel="next">Next <span class="fa fa-arrow-circle-right" aria-hidden="true"></span></a>
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