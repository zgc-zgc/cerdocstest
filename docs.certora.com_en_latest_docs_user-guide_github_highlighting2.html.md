<!DOCTYPE html><html class="writer-html5" lang="en" data-content_root="../../"><head>
  <meta charset="utf-8"><meta name="viewport" content="width=device-width, initial-scale=1">

  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Syntax Highlighting on GitHub — Certora Prover Documentation 0.0 documentation</title>
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
    <link rel="next" title="Glossary" href="glossary.html">
    <link rel="prev" title="CI Configuration" href="ci.html"> 
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
<li class="toctree-l2 current" aria-expanded="true"><a class="reference internal current" href="#" aria-expanded="true"><button class="toctree-expand" title="Open/close menu"></button>Syntax Highlighting on GitHub</a><ul>
<li class="toctree-l3"><a class="reference internal" href="#before-and-after-comparison"><button class="toctree-expand" title="Open/close menu"></button>Before and After Comparison</a><ul>
<li class="toctree-l4"><a class="reference internal" href="#spec-files">.spec files</a></li>
<li class="toctree-l4"><a class="reference internal" href="#conf-files">.conf files</a></li>
</ul>
</li>
<li class="toctree-l3"><a class="reference internal" href="#steps">Steps</a></li>
<li class="toctree-l3"><a class="reference internal" href="#explanation">Explanation</a></li>
<li class="toctree-l3"><a class="reference internal" href="#troubleshooting"><button class="toctree-expand" title="Open/close menu"></button>Troubleshooting</a><ul>
<li class="toctree-l4"><a class="reference internal" href="#step-1-verify-local-language-detection">Step 1 - Verify Local Language Detection</a></li>
<li class="toctree-l4"><a class="reference internal" href="#step-2-verify-github-server-update">Step 2 - Verify GitHub Server Update</a></li>
</ul>
</li>
</ul>
</li>
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
      <li class="breadcrumb-item active">Syntax Highlighting on GitHub</li>
      <li class="wy-breadcrumbs-aside">
            <a href="../../_sources/docs/user-guide/github_highlighting.md.txt" rel="nofollow"> View page source</a>
      </li>
  </ul>
  <hr>
</div>
          <div role="main" class="document" itemscope="itemscope" itemtype="http://schema.org/Article">
           <div itemprop="articleBody">
             
  <section id="syntax-highlighting-on-github">
<span id="index-0"></span><h1>Syntax Highlighting on GitHub<a class="headerlink" href="#syntax-highlighting-on-github" title="Link to this heading"></a></h1>
<p>This guide explains how to improve syntax highlighting in your GitHub repository for Certora Prover <a class="reference internal" href="../prover/cli/conf-file-api.html#conf-files"><span class="std std-ref">configuration</span></a> and <a class="reference internal" href="../cvl/index.html#cvl-language"><span class="std std-ref">specification</span></a> files.</p>
<section id="before-and-after-comparison">
<h2>Before and After Comparison<a class="headerlink" href="#before-and-after-comparison" title="Link to this heading"></a></h2>
<section id="spec-files">
<h3>.spec files<a class="headerlink" href="#spec-files" title="Link to this heading"></a></h3>
<p>A <code class="docutils literal notranslate"><span class="pre">.spec</span></code> file without highlighting will appear on GitHub (in dark mode) as:</p>
<p><img alt="conf before highlighting" src="../../_images/spec_without_highlighting.png" width="773" height="322"></p>
<p>After following the instructions on this guide it will look like:</p>
<p><img alt="spec after highlighting" src="../../_images/spec_with_highlighting.png"></p>
</section>
<section id="conf-files">
<h3>.conf files<a class="headerlink" href="#conf-files" title="Link to this heading"></a></h3>
<p>A <code class="docutils literal notranslate"><span class="pre">.conf</span></code> file without highlighting will appear on GitHub (in dark mode) as:</p>
<p><img alt="conf before highlighting" src="../../_images/conf_before_highlighting.png"></p>
<p>After following the instructions on this guide it will look like:</p>
<p><img alt="conf after highlighting" src="../../_images/highlighted_conf.png"></p>
</section>
</section>
<section id="steps">
<h2>Steps<a class="headerlink" href="#steps" title="Link to this heading"></a></h2>
<ol class="arabic simple">
<li><p>Create a <code class="docutils literal notranslate"><span class="pre">.gitattributes</span></code> file in the root directory of your repository if it doesn’t exist.</p></li>
<li><p>Append the following lines to the end of the <code class="docutils literal notranslate"><span class="pre">.gitattributes</span></code> file:</p></li>
</ol>
<div class="highlight-default notranslate"><div class="highlight"><pre id="codecell0"><span></span><span class="o">*.</span><span class="n">spec</span> <span class="n">linguist</span><span class="o">-</span><span class="n">language</span><span class="o">=</span><span class="n">Solidity</span>
<span class="o">*.</span><span class="n">conf</span> <span class="n">linguist</span><span class="o">-</span><span class="n">detectable</span>
<span class="o">*.</span><span class="n">conf</span> <span class="n">linguist</span><span class="o">-</span><span class="n">language</span><span class="o">=</span><span class="n">JSON5</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell0">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<ol class="arabic simple" start="3">
<li><p>Commit and push the changes to your repository.</p></li>
<li><p>Wait for GitHub to process the updates (this may take up to 24 hours).</p></li>
</ol>
</section>
<section id="explanation">
<h2>Explanation<a class="headerlink" href="#explanation" title="Link to this heading"></a></h2>
<p>The <code class="docutils literal notranslate"><span class="pre">.gitattributes</span></code> file instructs GitHub’s Linguist to classify <code class="docutils literal notranslate"><span class="pre">.spec</span></code> and <code class="docutils literal notranslate"><span class="pre">.conf</span></code> files with appropriate syntax highlighting:</p>
<p><code class="docutils literal notranslate"><span class="pre">.conf</span></code> files are <a class="reference external" href="https://json5.org/">JSON5</a> files with a different extension. Assigning them to JSON5 enables proper syntax highlighting.</p>
<p><code class="docutils literal notranslate"><span class="pre">.spec</span></code> files use <a class="reference internal" href="../cvl/index.html#cvl-language"><span class="std std-ref">CVL</span></a>, which is currently unsupported by GitHub. However, since CVL shares significant syntax with Solidity, applying Solidity highlighting significantly improves readability compared to GitHub’s default.</p>
</section>
<section id="troubleshooting">
<h2>Troubleshooting<a class="headerlink" href="#troubleshooting" title="Link to this heading"></a></h2>
<section id="step-1-verify-local-language-detection">
<h3>Step 1 - Verify Local Language Detection<a class="headerlink" href="#step-1-verify-local-language-detection" title="Link to this heading"></a></h3>
<p>To ensure <code class="docutils literal notranslate"><span class="pre">.gitattributes</span></code> was updated correctly, run the following command in your Git repository:</p>
<div class="highlight-default notranslate"><div class="highlight"><pre id="codecell1"><span></span><span class="n">git</span> <span class="n">check</span><span class="o">-</span><span class="n">attr</span> <span class="n">linguist</span><span class="o">-</span><span class="n">language</span> <span class="o">--</span> <span class="o">**/*.</span><span class="n">spec</span> <span class="o">**/*.</span><span class="n">conf</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell1">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>You should see output similar to:</p>
<div class="highlight-default notranslate"><div class="highlight"><pre id="codecell2"><span></span><span class="n">path</span><span class="o">/</span><span class="n">to</span><span class="o">/</span><span class="n">file</span><span class="o">.</span><span class="n">spec</span><span class="p">:</span> <span class="n">linguist</span><span class="o">-</span><span class="n">language</span><span class="p">:</span> <span class="n">Solidity</span>
<span class="n">path</span><span class="o">/</span><span class="n">to</span><span class="o">/</span><span class="n">file</span><span class="o">.</span><span class="n">conf</span><span class="p">:</span> <span class="n">linguist</span><span class="o">-</span><span class="n">language</span><span class="p">:</span> <span class="n">JSON5</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell2">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>If the output shows <code class="docutils literal notranslate"><span class="pre">unspecified</span></code>, the <code class="docutils literal notranslate"><span class="pre">.gitattributes</span></code> file may be missing or incorrectly placed (it must be in the root directory of the repository).</p>
<div class="highlight-default notranslate"><div class="highlight"><pre id="codecell3"><span></span><span class="n">CLIFlags</span><span class="o">/</span><span class="n">solc_via_ir</span><span class="o">.</span><span class="n">conf</span><span class="p">:</span> <span class="n">linguist</span><span class="o">-</span><span class="n">language</span><span class="p">:</span> <span class="n">unspecified</span>
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
<section id="step-2-verify-github-server-update">
<h3>Step 2 - Verify GitHub Server Update<a class="headerlink" href="#step-2-verify-github-server-update" title="Link to this heading"></a></h3>
<p>Run the following API query to confirm GitHub’s Linguist has updated the classification:
<code class="docutils literal notranslate"><span class="pre">https://api.github.com/repos/YOUR-ORG/YOUR-REPO/languages</span></code>
A successful update should return output similar to:</p>
<div class="highlight-default notranslate"><div class="highlight"><pre id="codecell4"><span></span><span class="p">{</span>
  <span class="s2">"Solidity"</span><span class="p">:</span> <span class="mi">21038</span><span class="p">,</span>
  <span class="s2">"JSON5"</span><span class="p">:</span> <span class="mi">443</span>
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
<p>If the response is an empty JSON (<code class="docutils literal notranslate"><span class="pre">{}</span></code>), ensure that:</p>
<ul class="simple">
<li><p>The <code class="docutils literal notranslate"><span class="pre">.gitattributes</span></code> changes were pushed.</p></li>
<li><p>There are no conflicting <code class="docutils literal notranslate"><span class="pre">.gitattributes</span></code> rules that override the new settings.</p></li>
</ul>
</section>
</section>
</section>


           </div>
          </div>
          <footer><div class="rst-footer-buttons" role="navigation" aria-label="Footer">
        <a href="ci.html" class="btn btn-neutral float-left" title="CI Configuration" accesskey="p" rel="prev"><span class="fa fa-arrow-circle-left" aria-hidden="true"></span> Previous</a>
        <a href="glossary.html" class="btn btn-neutral float-right" title="Glossary" accesskey="n" rel="next">Next <span class="fa fa-arrow-circle-right" aria-hidden="true"></span></a>
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