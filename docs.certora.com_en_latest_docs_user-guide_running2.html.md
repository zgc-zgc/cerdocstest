<!DOCTYPE html><html class="writer-html5" lang="en" data-content_root="../../"><head>
  <meta charset="utf-8"><meta name="viewport" content="width=device-width, initial-scale=1">

  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Running the Certora Prover — Certora Prover Documentation 0.0 documentation</title>
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
    <link rel="next" title="Designing Good Specifications" href="properties/index.html">
    <link rel="prev" title="Tutorial and Workshops" href="tutorials.html"> 
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
<li class="toctree-l2"><a class="reference internal" href="install.html">Installation</a></li>
<li class="toctree-l2"><a class="reference internal" href="install_evm_compiler.html">Installing an EVM compiler and VS Code Extension</a></li>
<li class="toctree-l2"><a class="reference internal" href="tutorials.html">Tutorial and Workshops</a></li>
<li class="toctree-l2 current" aria-expanded="true"><a class="reference internal current" href="#" aria-expanded="true"><button class="toctree-expand" title="Open/close menu"></button>Running the Certora Prover</a><ul>
<li class="toctree-l3"><a class="reference internal" href="#usage-example-with-erc20-contract">Usage Example with ERC20 Contract</a></li>
<li class="toctree-l3"><a class="reference internal" href="#results">Results</a></li>
<li class="toctree-l3"><a class="reference internal" href="#using-configuration-conf-files">Using Configuration (Conf) Files</a></li>
</ul>
</li>
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
      <li class="breadcrumb-item active">Running the Certora Prover</li>
      <li class="wy-breadcrumbs-aside">
            <a href="../../_sources/docs/user-guide/running.rst.txt" rel="nofollow"> View page source</a>
      </li>
  </ul>
  <hr>
</div>
          <div role="main" class="document" itemscope="itemscope" itemtype="http://schema.org/Article">
           <div itemprop="articleBody">
             
  <section id="running-the-certora-prover">
<h1>Running the Certora Prover<a class="headerlink" href="#running-the-certora-prover" title="Link to this heading"></a></h1>
<p>The <code class="code highlight bash docutils literal highlight-bash">certoraRun</code> utility simplifies the verification process by invoking the
contract compiler (e.g., Solidity) and then sending the verification job to Certora’s
servers.</p>
<p>The most commonly used command is:</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell0"><span></span>certoraRun<span class="w"> </span>contractFile:contractName<span class="w"> </span>--verify<span class="w"> </span>contractName:specFile
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell0">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>If <code class="code highlight bash docutils literal highlight-bash">contractFile</code> is named <code class="code highlight bash docutils literal highlight-bash">contractName.sol</code>, the command can be further
simplified to:</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell1"><span></span>certoraRun<span class="w"> </span>contractFile<span class="w"> </span>--verify<span class="w"> </span>contractName:specFile
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell1">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>A concise summary of these options can be viewed by using:</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell2"><span></span>certoraRun<span class="w"> </span>--help
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell2">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<section id="usage-example-with-erc20-contract">
<h2>Usage Example with ERC20 Contract<a class="headerlink" href="#usage-example-with-erc20-contract" title="Link to this heading"></a></h2>
<p>To demonstrate the usage, let’s consider an ERC20 contract named
<a class="reference external" href="https://github.com/Certora/Examples/blob/7dfc379423202c90cf284eb42800b97cf5c95d83/DEFI/ERC20/contracts/correct/ERC20Fixed.sol">ERC20Fixed</a> from the
<a class="reference external" href="https://github.com/Certora/Examples/tree/7dfc379423202c90cf284eb42800b97cf5c95d83/.">Certora Prover and CVL Examples Repository</a>.
The corresponding spec file is named
<a class="reference external" href="https://github.com/Certora/Examples/blob/7dfc379423202c90cf284eb42800b97cf5c95d83/DEFI/ERC20/certora/specs/ERC20Fixed.spec">ERC20Fixed.spec</a>.
Here is a rule from this spec:</p>
<div class="literal-block-wrapper docutils container" id="id1">
<div class="code-block-caption"><span class="caption-text"><a class="reference external" href="https://github.com/Certora/Examples/blob/7dfc379423202c90cf284eb42800b97cf5c95d83/DEFI/ERC20/certora/specs/ERC20Fixed.spec">from ERC20Fixed.spec</a></span><a class="headerlink" href="#id1" title="Link to this code"></a></div>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell3"><span></span><span class="c1">/// Transfer must move `amount` tokens from the caller's account to `recipient`</span>
<span class="k">rule</span><span class="w"> </span><span class="nc">transferSpec</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kt">address</span><span class="w"> </span>sender<span class="p">;</span><span class="w"> </span><span class="kt">address</span><span class="w"> </span>recip<span class="p">;</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>amount<span class="p">;</span>

<span class="w">    </span><span class="kt">env</span><span class="w"> </span>e<span class="p">;</span>
<span class="w">    </span><span class="kr">require</span><span class="w"> </span>e<span class="p">.</span><span class="kc">msg.sender</span><span class="w"> </span><span class="o">==</span><span class="w"> </span>sender<span class="p">;</span>

<span class="w">    </span><span class="kt">mathint</span><span class="w"> </span>balance_sender_before<span class="w"> </span><span class="o">=</span><span class="w"> </span>balanceOf<span class="p">(</span>sender<span class="p">);</span>
<span class="w">    </span><span class="kt">mathint</span><span class="w"> </span>balance_recip_before<span class="w"> </span><span class="o">=</span><span class="w"> </span>balanceOf<span class="p">(</span>recip<span class="p">);</span>

<span class="w">    </span>transfer<span class="p">(</span>e<span class="p">,</span><span class="w"> </span>recip<span class="p">,</span><span class="w"> </span>amount<span class="p">);</span>

<span class="w">    </span><span class="kt">mathint</span><span class="w"> </span>balance_sender_after<span class="w"> </span><span class="o">=</span><span class="w"> </span>balanceOf<span class="p">(</span>sender<span class="p">);</span>
<span class="w">    </span><span class="kt">mathint</span><span class="w"> </span>balance_recip_after<span class="w"> </span><span class="o">=</span><span class="w"> </span>balanceOf<span class="p">(</span>recip<span class="p">);</span>

<span class="w">    </span><span class="kr">require</span><span class="w"> </span>sender<span class="w"> </span><span class="o">!=</span><span class="w"> </span>recip<span class="p">;</span>

<span class="w">    </span><span class="kr">assert</span><span class="w"> </span>balance_sender_after<span class="w"> </span><span class="o">==</span><span class="w"> </span>balance_sender_before<span class="w"> </span><span class="o">-</span><span class="w"> </span>amount<span class="p">,</span>
<span class="w">        </span><span class="s2">"transfer must decrease sender's balance by amount"</span><span class="p">;</span>

<span class="w">    </span><span class="kr">assert</span><span class="w"> </span>balance_recip_after<span class="w"> </span><span class="o">==</span><span class="w"> </span>balance_recip_before<span class="w"> </span><span class="o">+</span><span class="w"> </span>amount<span class="p">,</span>
<span class="w">        </span><span class="s2">"transfer must increase recipient's balance by amount"</span><span class="p">;</span>
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
</div>
<p>You can run the Certora Prover with the following command (from the
<a class="reference external" href="https://github.com/Certora/Examples/tree/7dfc379423202c90cf284eb42800b97cf5c95d83/DEFI/ERC20">/DEFI/ERC20/</a> folder in the repository):</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell4"><span></span>certoraRun<span class="w"> </span>contracts/correct/ERC20Fixed.sol<span class="w"> </span>--verify<span class="w"> </span>ERC20Fixed:certora/specs/ERC20Fixed.spec
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell4">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>This command triggers a verification run on the <code class="code highlight solidity docutils literal highlight-solidity">ERC20</code> contract from the
solidity file <code class="file docutils literal notranslate"><span class="pre">ERC20.sol</span></code>, checking all rules in the specification file
<code class="file docutils literal notranslate"><span class="pre">ERC20Fixed.spec</span></code>.</p>
<div class="admonition tip">
<p class="admonition-title">Tip</p>
<p>You will need to use the correct version of the Solidity compiler.
Either by</p>
<ul class="simple">
<li><p>using <code class="docutils literal notranslate"><span class="pre">solc-select</span></code> or having the compiler executable in your path
(see <a class="reference internal" href="install_evm_compiler.html#selecting-solidity-compiler"><span class="std std-ref">Installing Solidity compiler</span></a>),</p></li>
<li><p>or by directing the <code class="docutils literal notranslate"><span class="pre">certoraRun</span></code> to the correct path using the
<a class="reference internal" href="../prover/cli/options.html#solc"><span class="std std-ref">solc</span></a> argument.</p></li>
</ul>
</div>
</section>
<section id="results">
<h2>Results<a class="headerlink" href="#results" title="Link to this heading"></a></h2>
<p>While running, the Prover will print various information to the console about the run.
In the end, the output will look similar to this:</p>
<div class="highlight-text notranslate"><div class="highlight"><pre id="codecell5"><span></span>...

Job submitted to server

Follow your job at https://prover.certora.com
Once the job is completed, the results will be available at https://prover.certora.com/...
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell5">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>The output indicates that the Prover running the verification request, and it provides
a link to view the results on the Certora platform.</p>
</section>
<section id="using-configuration-conf-files">
<h2>Using Configuration (Conf) Files<a class="headerlink" href="#using-configuration-conf-files" title="Link to this heading"></a></h2>
<p>For larger projects, managing the command line for Certora Prover can become complex.
It is advisable to use configuration files (with a <code class="file docutils literal notranslate"><span class="pre">.conf</span></code> extension) that hold
the parameters and options for the Prover.
These <a class="reference external" href="https://json5.org/">JSON5</a> configuration files simplify the process and enhance manageability.
Refer to <a class="reference internal" href="../prover/cli/conf-file-api.html#conf-files"><span class="std std-ref">Configuration (Conf) Files</span></a> for more detailed information.</p>
</section>
</section>


           </div>
          </div>
          <footer><div class="rst-footer-buttons" role="navigation" aria-label="Footer">
        <a href="tutorials.html" class="btn btn-neutral float-left" title="Tutorial and Workshops" accesskey="p" rel="prev"><span class="fa fa-arrow-circle-left" aria-hidden="true"></span> Previous</a>
        <a href="properties/index.html" class="btn btn-neutral float-right" title="Designing Good Specifications" accesskey="n" rel="next">Next <span class="fa fa-arrow-circle-right" aria-hidden="true"></span></a>
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