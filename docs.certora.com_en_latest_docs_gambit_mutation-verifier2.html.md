<!DOCTYPE html><html class="writer-html5" lang="en" data-content_root="../../"><head>
  <meta charset="utf-8"><meta name="viewport" content="width=device-width, initial-scale=1">

  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Using Gambit with the Prover — Certora Prover Documentation 0.0 documentation</title>
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
    <link rel="next" title="Gambit: Mutant Generation for Solidity" href="gambit.html">
    <link rel="prev" title="Gambit: Mutation Generator for Solidity" href="index.html"> 
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
<li class="toctree-l2 current" aria-expanded="true"><a class="reference internal current" href="#" aria-expanded="true"><button class="toctree-expand" title="Open/close menu"></button>Using Gambit with the Prover</a><ul>
<li class="toctree-l3"><a class="reference internal" href="#installation">Installation</a></li>
<li class="toctree-l3"><a class="reference internal" href="#running-the-mutation-verifier">Running the Mutation Verifier</a></li>
<li class="toctree-l3"><a class="reference internal" href="#mutation-configuration">Mutation Configuration</a></li>
<li class="toctree-l3"><a class="reference internal" href="#mutation-sources"><button class="toctree-expand" title="Open/close menu"></button>Mutation Sources</a><ul>
<li class="toctree-l4"><a class="reference internal" href="#randomly-generated-mutations-via-gambit">Randomly generated mutations via Gambit</a></li>
<li class="toctree-l4"><a class="reference internal" href="#manual-mutations">Manual mutations</a></li>
</ul>
</li>
<li class="toctree-l3"><a class="reference internal" href="#original-verification-run"><button class="toctree-expand" title="Open/close menu"></button>Original Verification Run</a><ul>
<li class="toctree-l4"><a class="reference internal" href="#generating-the-original-run">Generating the original run</a></li>
<li class="toctree-l4"><a class="reference internal" href="#original-verification-link">Original verification link</a></li>
</ul>
</li>
<li class="toctree-l3"><a class="reference internal" href="#the-mutations-dashboard"><button class="toctree-expand" title="Open/close menu"></button>The Mutations Dashboard</a><ul>
<li class="toctree-l4"><a class="reference internal" href="#mutation-test-statuses">Mutation test statuses</a></li>
</ul>
</li>
<li class="toctree-l3"><a class="reference internal" href="#mutation-test-report"><button class="toctree-expand" title="Open/close menu"></button>Mutation Test Report</a><ul>
<li class="toctree-l4"><a class="reference internal" href="#metrics">Metrics</a></li>
</ul>
</li>
<li class="toctree-l3"><a class="reference internal" href="#cli-options">CLI Options</a></li>
<li class="toctree-l3"><a class="reference internal" href="#troubleshooting">Troubleshooting</a></li>
</ul>
</li>
<li class="toctree-l2"><a class="reference internal" href="gambit.html">Gambit: Mutant Generation for Solidity</a></li>
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
      <li class="breadcrumb-item active">Using Gambit with the Prover</li>
      <li class="wy-breadcrumbs-aside">
            <a href="../../_sources/docs/gambit/mutation-verifier.md.txt" rel="nofollow"> View page source</a>
      </li>
  </ul>
  <hr>
</div>
          <div role="main" class="document" itemscope="itemscope" itemtype="http://schema.org/Article">
           <div itemprop="articleBody">
             
  <section id="using-gambit-with-the-prover">
<h1>Using Gambit with the Prover<a class="headerlink" href="#using-gambit-with-the-prover" title="Link to this heading"></a></h1>
<p>The mutation verifier checks that variants of the original
Solidity program do not pass verification against a given specification.
You can either use random mutations generated by <a class="reference internal" href="gambit.html"><span class="doc">Gambit</span></a>
or <a class="reference internal" href="#man-mutants"><span class="std std-ref">manually crafted</span></a> with a specific error.
If a mutated program passes the specification,
it may indicate that the specification is vacuous or not rigorous enough.</p>
<section id="installation">
<h2>Installation<a class="headerlink" href="#installation" title="Link to this heading"></a></h2>
<p>To use the mutation verifier,
first <a class="reference internal" href="../user-guide/install.html#installation"><span class="std std-ref">install the Certora Prover and its dependencies</span></a>.
To install it, run</p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell0"><span></span>pip<span class="w"> </span>install<span class="w"> </span>certora-cli
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell0">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>If you already have <code class="docutils literal notranslate"><span class="pre">certora-cli</span></code> installed and
the <code class="docutils literal notranslate"><span class="pre">certoraMutate</span></code> command is not available,
you may need to update to a newer version by running</p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell1"><span></span>pip<span class="w"> </span>install<span class="w"> </span>--upgrade<span class="w"> </span>certora-cli
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell1">
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
<p>If you are on Linux, you will need pip version 20.3 or above.</p>
</div>
</section>
<section id="running-the-mutation-verifier">
<h2>Running the Mutation Verifier<a class="headerlink" href="#running-the-mutation-verifier" title="Link to this heading"></a></h2>
<p>You need to extend your <a class="reference internal" href="../prover/cli/conf-file-api.html#conf-files"><span class="std std-ref">Prover configuration file</span></a> by adding a <a class="reference internal" href="#mut-conf"><span class="std std-ref">mutation object</span></a>.
The mutation verification script is called <code class="docutils literal notranslate"><span class="pre">certoraMutate</span></code>.
Run it from the command line just like <code class="docutils literal notranslate"><span class="pre">certoraRun</span></code>:</p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell2"><span></span>certoraMutate<span class="w"> </span>path/to/prover.conf
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell2">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>If you do, the script will generate code mutants,
then submit a verification job per mutant to Certora’s server.</p>
<p>Submitting the verification jobs of the mutants may take several minutes.
When it finishes successfully, you should see the following lines printed:</p>
<div class="highlight-text notranslate"><div class="highlight"><pre id="codecell3"><span></span>******************** PROVER END ********************

You will receive an email notification when this mutation test is completed. It may take several hours.
You can follow the test's progress at https://prover.certora.com/mutations
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell3">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>The time required to verify all mutants depends on various factors,
such as the number of mutants, the complexity of the contracts,
and the complexity of the specifications.
In some instances, the entire testing process may take several hours.</p>
<p>You can follow the test’s progress in the <a class="reference internal" href="#mutations-dashboard"><span class="std std-ref">mutations dashboard</span></a>.
The results will be available in the dashboard when they are ready.</p>
<p>Once the test is completed, you should receive an email that looks like this:</p>
<p><img alt="Mutation suceeded email" src="../../_images/email_mutation_success.png" width="1528" height="550"></p>
</section>
<section id="mutation-configuration">
<span id="mut-conf"></span><h2>Mutation Configuration<a class="headerlink" href="#mutation-configuration" title="Link to this heading"></a></h2>
<p>The mutation tester script requires a Prover JSON <code class="docutils literal notranslate"><span class="pre">.conf</span></code> configuration file that includes a <code class="docutils literal notranslate"><span class="pre">mutations</span></code> key.
Within this key, an object is defined to specify the behavior of mutation testing.
Notably, all other settings, including those influencing compilation or verification,
remain consistent with those defined outside the <code class="docutils literal notranslate"><span class="pre">mutations</span></code> object.</p>
<p>For example, see the file <code class="docutils literal notranslate"><span class="pre">default.conf</span></code> from the <a class="reference external" href="https://github.com/Certora/CertoraInit">CertoraInit</a> repository:</p>
<div class="highlight-json notranslate"><div class="highlight"><pre id="codecell4"><span></span><span class="p">{</span>
<span class="w">  </span><span class="nt">"files"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span>
<span class="w">    </span><span class="s2">"contracts/ERC20.sol"</span>
<span class="w">  </span><span class="p">],</span>
<span class="w">  </span><span class="nt">"verify"</span><span class="p">:</span><span class="w"> </span><span class="s2">"ERC20:certora/spec/ERC20.spec"</span><span class="p">,</span>
<span class="w">  </span><span class="nt">"msg"</span><span class="p">:</span><span class="w"> </span><span class="s2">"ERC20Rules"</span><span class="p">,</span>
<span class="w">  </span><span class="nt">"mutations"</span><span class="p">:</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="nt">"gambit"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span>
<span class="w">        </span><span class="p">{</span>
<span class="w">            </span><span class="nt">"filename"</span><span class="w"> </span><span class="p">:</span><span class="w"> </span><span class="s2">"contracts/ERC20.sol"</span><span class="p">,</span>
<span class="w">            </span><span class="nt">"num_mutants"</span><span class="p">:</span><span class="w"> </span><span class="mi">5</span>
<span class="w">        </span><span class="p">}</span>
<span class="w">    </span><span class="p">],</span>
<span class="w">    </span><span class="nt">"msg"</span><span class="p">:</span><span class="w"> </span><span class="s2">"basic mutation configuration"</span>
<span class="w">  </span><span class="p">}</span><span class="w"> </span>
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
</section>
<section id="mutation-sources">
<h2>Mutation Sources<a class="headerlink" href="#mutation-sources" title="Link to this heading"></a></h2>
<p>Mutations can either be randomly generated via <a class="reference internal" href="gambit.html"><span class="doc">Gambit</span></a>, or manually generated by you.</p>
<section id="randomly-generated-mutations-via-gambit">
<h3>Randomly generated mutations via Gambit<a class="headerlink" href="#randomly-generated-mutations-via-gambit" title="Link to this heading"></a></h3>
<p>To generate random mutations via <a class="reference internal" href="gambit.html"><span class="doc">Gambit</span></a>,
add a <code class="docutils literal notranslate"><span class="pre">gambit</span></code> key inside the <code class="docutils literal notranslate"><span class="pre">mutations</span></code> object.
This key should include a list of <a class="reference internal" href="gambit.html#gambit-config"><span class="std std-ref">Gambit mutation objects</span></a>.
All file paths are relative to the current working directory.</p>
<p>For example, see the <code class="docutils literal notranslate"><span class="pre">gambit</span></code> value from the file <code class="docutils literal notranslate"><span class="pre">advanced_mutation.conf</span></code>
of the <a class="reference external" href="https://github.com/Certora/CertoraInit">CertoraInit</a> repository:</p>
<div class="highlight-json notranslate"><div class="highlight"><pre id="codecell5"><span></span><span class="nt">"gambit"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span>
<span class="w">  </span><span class="p">{</span>
<span class="w">    </span><span class="nt">"filename"</span><span class="p">:</span><span class="w"> </span><span class="s2">"contracts/ERC20.sol"</span><span class="p">,</span>
<span class="w">    </span><span class="nt">"num_mutants"</span><span class="p">:</span><span class="w"> </span><span class="mi">2</span><span class="p">,</span>
<span class="w">    </span><span class="nt">"mutations"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span>
<span class="w">      </span><span class="s2">"require-mutation"</span>
<span class="w">    </span><span class="p">]</span>
<span class="w">  </span><span class="p">},</span>
<span class="w">  </span><span class="p">{</span>
<span class="w">    </span><span class="nt">"filename"</span><span class="p">:</span><span class="w"> </span><span class="s2">"contracts/ERC20.sol"</span><span class="p">,</span>
<span class="w">    </span><span class="nt">"num_mutants"</span><span class="p">:</span><span class="w"> </span><span class="mi">1</span><span class="p">,</span>
<span class="w">    </span><span class="nt">"mutations"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span>
<span class="w">      </span><span class="s2">"assignment-mutation"</span>
<span class="w">    </span><span class="p">]</span>
<span class="w">  </span><span class="p">}</span>
<span class="p">],</span>
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
<section id="manual-mutations">
<span id="man-mutants"></span><h3>Manual mutations<a class="headerlink" href="#manual-mutations" title="Link to this heading"></a></h3>
<p>You have the option to include manually generated mutated files,
not produced by Gambit, in your mutation test.
We refer to these as ‘manual mutations.’
They can be used for regression tests,
or to check mutations that Gambit does not currently support.</p>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>It is recommended to limit each manually mutated file to a single mutation for more accurate coverage analysis and better traceability.</p>
</div>
<p>To add manual mutations, under <code class="docutils literal notranslate"><span class="pre">mutations</span></code> create a key <code class="docutils literal notranslate"><span class="pre">manual_mutants</span></code> containing a list
of manual mutation objects.
Each manual mutation object must contain two keys:</p>
<ul class="simple">
<li><p><code class="docutils literal notranslate"><span class="pre">file_to_mutate</span></code>: A file path relative to the current working directory of the file we wish to replace with the mutations</p></li>
<li><p><code class="docutils literal notranslate"><span class="pre">mutants_location</span></code>: A relative path to a directory from the current working directory. This directory contains files that will be tested in place of the mutated file. All .sol files in the directory will undergo testing.</p></li>
</ul>
<p>For example, see the <code class="docutils literal notranslate"><span class="pre">manual_mutants</span></code> value from the file <code class="docutils literal notranslate"><span class="pre">advanced_mutation.conf</span></code>
of the <a class="reference external" href="https://github.com/Certora/CertoraInit">CertoraInit</a> repository:</p>
<div class="highlight-json notranslate"><div class="highlight"><pre id="codecell6"><span></span><span class="nt">"manual_mutants"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span>
<span class="w">  </span><span class="p">{</span>
<span class="w">    </span><span class="nt">"file_to_mutate"</span><span class="p">:</span><span class="w"> </span><span class="s2">"contracts/ERC20.sol"</span><span class="p">,</span>
<span class="w">    </span><span class="nt">"mutants_location"</span><span class="p">:</span><span class="w"> </span><span class="s2">"mutations"</span>
<span class="w">  </span><span class="p">}</span>
<span class="p">]</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell6">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>If you don’t have a <code class="docutils literal notranslate"><span class="pre">gambit</span></code> object in the <code class="docutils literal notranslate"><span class="pre">conf</span></code> file,
<code class="docutils literal notranslate"><span class="pre">certoraMutate</span></code> will run only on the manual mutants,
and no other mutants will be generated.</p>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>All manual mutations must be named uniquely.
For example, if you want to generate manual mutations for <code class="docutils literal notranslate"><span class="pre">C.sol</span></code> and <code class="docutils literal notranslate"><span class="pre">D.sol</span></code>,
name them <code class="docutils literal notranslate"><span class="pre">C.m1.sol,</span> <span class="pre">C.m2.sol,</span> <span class="pre">D.m3.sol,</span> <span class="pre">D.m4.sol,</span> <span class="pre">...</span></code> etc.</p>
</div>
</section>
</section>
<section id="original-verification-run">
<h2>Original Verification Run<a class="headerlink" href="#original-verification-run" title="Link to this heading"></a></h2>
<p>A mutation test requires a verification job that was completed successfully without halting
as a basis for comparison, called the original run.
All mutant checks will be run with the same verification configuration as the
original run, and their results will be compared to the original run.
Rules that are not verified or did not pass <a class="reference internal" href="../cvl/builtin.html#built-in-sanity"><span class="std std-ref">basic sanity checks</span></a> on the original run will be ignored.</p>
<section id="generating-the-original-run">
<h3>Generating the original run<a class="headerlink" href="#generating-the-original-run" title="Link to this heading"></a></h3>
<p>Usually, the original run is sent for verification with the mutants.
An unaltered file without mutations is sent for verification
before all mutant verification runs.
The mutation test will be aborted if the original run fails to compile.</p>
</section>
<section id="original-verification-link">
<span id="orig-verification-link"></span><h3>Original verification link<a class="headerlink" href="#original-verification-link" title="Link to this heading"></a></h3>
<p>You can also provide a link to a run that was already executed.
The mutants will run with the same specification and configuration as that run.
The files relevant for that run will be downloaded to your local machine.</p>
<p>You can provide the original run job’s link via <code class="docutils literal notranslate"><span class="pre">--orig_run</span></code>, for example:</p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell7"><span></span>--orig_run<span class="w"> </span>https://prover.certora.com/output/53342/9487899b2afc4709899889fab6c2c673/?anonymousKey<span class="o">=</span>5c365717c9c1076f0c1acb050c7eb5867f07a236
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell7">
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
<p>The run must have the job status <code class="docutils literal notranslate"><span class="pre">Executed</span></code> on the <a class="reference external" href="https://prover.certora.com">Prover dashboard</a>.</p>
</div>
<p>The files will be downloaded to either a default directory or to one specified with <code class="docutils literal notranslate"><span class="pre">--orig_run_dir</span></code>.</p>
</section>
</section>
<section id="the-mutations-dashboard">
<span id="mutations-dashboard"></span><h2>The Mutations Dashboard<a class="headerlink" href="#the-mutations-dashboard" title="Link to this heading"></a></h2>
<p>You can track your mutation tests at the <a class="reference external" href="https://prover.certora.com/mutations">mutations dashboard</a>.
A test that just started would look like this:</p>
<p><img alt="Mutation test running" src="../../_images/mutation_test_started_dashboard.png" width="887" height="96"></p>
<ul class="simple">
<li><p>The <em>Mutation ID</em> is a unique identifier for the test.</p></li>
<li><p>The <em>Message</em> column includes the description given either in the command line
via the <code class="docutils literal notranslate"><span class="pre">--msg</span></code> flag or the conf file’s <code class="docutils literal notranslate"><span class="pre">"msg"</span></code> key.
It aids in identifying and documenting mutation tests.
By default, it will show <em>None</em>.</p></li>
<li><p>The <em>Status</em> column of a test includes two different parts - the status of the test (see below) and a progress counter.
The progress counter shows how many of the sent mutant verification jobs have already been executed.</p></li>
</ul>
<section id="mutation-test-statuses">
<h3>Mutation test statuses<a class="headerlink" href="#mutation-test-statuses" title="Link to this heading"></a></h3>
<p>A mutation test can have one of five different statuses:</p>
<ul class="simple">
<li><p><em>Running</em> indicates that the verification jobs of the mutants are still being computed.</p></li>
</ul>
<p><img alt="Mutation test running" src="../../_images/mutation_test_started_dashboard.png"></p>
<ul class="simple">
<li><p><em>Calculating</em> indicates that all the verification jobs have finished, and the results are now being gathered and processed into a verification report.</p></li>
</ul>
<p><img alt="Mutation test calculating" src="../../_images/mutation_test_calculating.png" width="117" height="42"></p>
<ul class="simple">
<li><p><em>Executed</em> indicates that all mutant verification jobs were executed correctly and are available in the report, which can be accessed by clicking on the <code class="docutils literal notranslate"><span class="pre">Mutation</span> <span class="pre">ID</span></code>.</p></li>
</ul>
<p><img alt="Mutation test executed" src="../../_images/mutation_test_executed.png"></p>
<ul class="simple">
<li><p><em>Halted</em> indicates that the mutation test reached a global time limit and was stopped. The partial verification results that were collected before the time limit are available in the verification report. This usually happens when too many mutants are used in a single test.</p></li>
</ul>
<p><img alt="Mutation test halted" src="../../_images/halted_mutation_test.png"></p>
<ul class="simple">
<li><p><em>Problem</em> indicates the test had errors. A report is usually not generated.</p></li>
</ul>
<p><img alt="Mutation test problem" src="../../_images/mutation_test_problem.png"></p>
</section>
</section>
<section id="mutation-test-report">
<h2>Mutation Test Report<a class="headerlink" href="#mutation-test-report" title="Link to this heading"></a></h2>
<p>The mutation verification results are
summarized in a user-friendly visual report.</p>
<p><a class="reference external" href="https://mutation-testing-beta.certora.com/?id=01623b02-0cda-435b-8c31-af9306d6d302&amp;amp;anonymousKey=857c3aeb-169c-4c93-8021-e82058603ca1">Here</a>
is an example summary for the
<a class="reference external" href="https://github.com/Certora/CertoraInit/blob/master/mutation/advanced_mutation.conf">advanced mutation of an ERC20 example</a>.
The green outer circles represent the rules,
and the gray dots represent the mutants.</p>
<p><img alt="Report of the advanced mutation of CertoraInit" src="../../_images/mutation_advanced_results.png"></p>
<p>Selecting a rule shows which mutants it detected,
and selecting a mutant shows which rules caught it.</p>
<p><img alt="Selecting a rule" src="../../_images/selecting_a_rule.png"></p>
<p>Clicking on a mutant’s patch shows the difference between it and the original program.</p>
<p><img alt="Showing a mutant patch" src="../../_images/show_mutant_patch.png"></p>
<section id="metrics">
<h3>Metrics<a class="headerlink" href="#metrics" title="Link to this heading"></a></h3>
<p>At the top bar of the report there are different coverage metrics.</p>
<p><img alt="Mutation metrics" src="../../_images/mutation_metrics.png"></p>
<ul class="simple">
<li><p>The <em>Coverage</em> metric is the ratio of the caught mutants to all mutants tested,
also shown under <em>Caught Mutations</em>.</p></li>
<li><p>The <em>Rules</em> metric shows the ratio of the rules that caught at least one mutation
out of all the rules in the tested specification.</p></li>
<li><p>The <em>Solo Rules</em> metric shows the ratio between the rules that caught a unique mutation
and all rules that caught at least one mutation.</p></li>
</ul>
</section>
</section>
<section id="cli-options">
<h2>CLI Options<a class="headerlink" href="#cli-options" title="Link to this heading"></a></h2>
<p><code class="docutils literal notranslate"><span class="pre">certoraMutate</span></code> supports the following options; for a comprehensive list, run <code class="docutils literal notranslate"><span class="pre">certoraMutate</span> <span class="pre">--help</span></code>:</p>
<div class="wy-table-responsive"><table class="docutils align-default">
<thead>
<tr class="row-odd"><th class="head text-left"><p></p><div style="width:160px">Option</div><p></p></th>
<th class="head text-left"><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="row-even"><td class="text-left"><p><code class="docutils literal notranslate"><span class="pre">--orig_run</span></code></p></td>
<td class="text-left"><p>Specify the <a class="reference internal" href="#orig-verification-link"><span class="std std-ref">link to a previous verification job</span></a></p></td>
</tr>
<tr class="row-odd"><td class="text-left"><p><code class="docutils literal notranslate"><span class="pre">--orig_run_dir</span></code></p></td>
<td class="text-left"><p>Specify the folder where the files will be downloaded from the <a class="reference internal" href="#orig-verification-link"><span class="std std-ref">original verification job</span></a></p></td>
</tr>
<tr class="row-even"><td class="text-left"><p><code class="docutils literal notranslate"><span class="pre">--msg</span></code></p></td>
<td class="text-left"><p>Add a message to identify the <code class="docutils literal notranslate"><span class="pre">certoraMutate</span></code> run</p></td>
</tr>
<tr class="row-odd"><td class="text-left"><p><code class="docutils literal notranslate"><span class="pre">--gambit_only</span></code></p></td>
<td class="text-left"><p>Stop processing after generating mutations</p></td>
</tr>
<tr class="row-even"><td class="text-left"><p><code class="docutils literal notranslate"><span class="pre">--dump_failed_collects</span></code></p></td>
<td class="text-left"><p>Specify a log file to capture mutant collection failures</p></td>
</tr>
<tr class="row-odd"><td class="text-left"><p><code class="docutils literal notranslate"><span class="pre">--debug</span></code></p></td>
<td class="text-left"><p>Show additional logging information during execution</p></td>
</tr>
</tbody>
</table></div>
</section>
<section id="troubleshooting">
<h2>Troubleshooting<a class="headerlink" href="#troubleshooting" title="Link to this heading"></a></h2>
<p>At the moment, there are a few ways in which <code class="docutils literal notranslate"><span class="pre">certoraMutate</span></code> can fail.
Here are some suggestions on how to troubleshoot when that happens.
We are actively working on mitigating them.</p>
<ul class="simple">
<li><p>There are currently no official Gambit binaries for Linux ARM or Windows. That means that Gambit will not be installed with <code class="docutils literal notranslate"><span class="pre">pip</span> <span class="pre">install</span> <span class="pre">certora-cli</span></code>, and must be <a class="reference internal" href="gambit.html#build-gambit-from-source"><span class="std std-ref">built from source</span></a>.</p></li>
<li><p>Sometimes, the problem stems from Gambit’s mutant generation.
Try running with <code class="docutils literal notranslate"><span class="pre">--gambit_only</span></code> and look at the generated mutations.</p></li>
<li><p>Try running the Prover on your mutants individually using <code class="docutils literal notranslate"><span class="pre">certoraRun</span></code>.
Usually the mutant setup will be in <code class="docutils literal notranslate"><span class="pre">.certora_internal/applied_mutants_dir</span></code> and can be retried by running the Prover’s <code class="docutils literal notranslate"><span class="pre">.conf</span></code> file with <code class="docutils literal notranslate"><span class="pre">certoraRun</span></code>.
<a class="reference internal" href="#man-mutants"><span class="std std-ref">Manual mutants</span></a> that don’t show up in the report may had a Solidity compilation error.
It is also possible that you are encountering a bug with the underlying version of the Prover.</p></li>
<li><p>Check if your packages paths have a trailing <code class="docutils literal notranslate"><span class="pre">/</span></code>. The packages paths, both sources and targets, should never end with a <code class="docutils literal notranslate"><span class="pre">/</span></code>.</p></li>
</ul>
</section>
</section>


           </div>
          </div>
          <footer><div class="rst-footer-buttons" role="navigation" aria-label="Footer">
        <a href="index.html" class="btn btn-neutral float-left" title="Gambit: Mutation Generator for Solidity" accesskey="p" rel="prev"><span class="fa fa-arrow-circle-left" aria-hidden="true"></span> Previous</a>
        <a href="gambit.html" class="btn btn-neutral float-right" title="Gambit: Mutant Generation for Solidity" accesskey="n" rel="next">Next <span class="fa fa-arrow-circle-right" aria-hidden="true"></span></a>
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