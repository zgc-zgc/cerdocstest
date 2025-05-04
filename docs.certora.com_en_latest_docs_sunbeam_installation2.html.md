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
    <link rel="next" title="User Guide For Sunbeam" href="usage.html">
    <link rel="prev" title="Sunbeam: Verification for Soroban" href="index.html"> 
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
<li class="toctree-l1 current" aria-expanded="true"><a class="reference internal" href="index.html"><button class="toctree-expand" title="Open/close menu"></button>Sunbeam: Verification for Soroban</a><ul class="" aria-expanded="false">
<li class="toctree-l2 current" aria-expanded="true"><a class="reference internal current" href="#" aria-expanded="true"><button class="toctree-expand" title="Open/close menu"></button>Installation</a><ul>
<li class="toctree-l3"><a class="reference internal" href="#installing-sunbeam">Installing Sunbeam</a></li>
<li class="toctree-l3"><a class="reference internal" href="#rust-and-stellar-cli-setup">Rust and Stellar CLI Setup</a></li>
</ul>
</li>
<li class="toctree-l2"><a class="reference internal" href="usage.html">User Guide For Sunbeam</a></li>
<li class="toctree-l2"><a class="reference internal" href="troubleshooting.html">Troubleshooting</a></li>
</ul>
</li>
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
          <li class="breadcrumb-item"><a href="index.html">Sunbeam: Verification for Soroban</a></li>
      <li class="breadcrumb-item active">Installation</li>
      <li class="wy-breadcrumbs-aside">
            <a href="../../_sources/docs/sunbeam/installation.rst.txt" rel="nofollow"> View page source</a>
      </li>
  </ul>
  <hr>
</div>
          <div role="main" class="document" itemscope="itemscope" itemtype="http://schema.org/Article">
           <div itemprop="articleBody">
             
  <section id="installation">
<h1>Installation<a class="headerlink" href="#installation" title="Link to this heading"></a></h1>
<div class="admonition attention">
<p class="admonition-title">Attention</p>
<p>These instructions are for Linux and macOS systems.
Windows users should use <a class="reference external" href="https://learn.microsoft.com//install">WSL</a> and follow the
Linux installation instructions.</p>
</div>
<section id="installing-sunbeam">
<h2>Installing Sunbeam<a class="headerlink" href="#installing-sunbeam" title="Link to this heading"></a></h2>
<ol class="arabic">
<li><p>First, we will need to install the Sunbeam Prover.
For that, please visit <a class="reference external" href="https://www.certora.com/">Certora.com</a> and sign up for a
free account at <a class="reference external" href="https://www.certora.com/signup">Certora sign-up page</a>.</p></li>
<li><p>You will receive an email with a temporary password and a <em>Certora Key</em>.
Use the password to login to Certora following the link in the email.</p></li>
<li><p>Next, install Python3.8.16 or newer on your machine.
If you already have Python3 installed, you can check the version: <code class="docutils literal notranslate"><span class="pre">python3</span> <span class="pre">--version</span></code>.
If you need to upgrade, follow these instructions in the
<a class="reference external" href="https://wiki.python.org/moin/BeginnersGuide/Download">Python Beginners Guide</a>.</p></li>
<li><p>Next, install Java. Check your Java version: <code class="docutils literal notranslate"><span class="pre">java</span> <span class="pre">-version</span></code>.
If the version is &lt; 11, download and install Java version 11 or later from
<a class="reference external" href="https://www.oracle.com/java/technologies/downloads/">Oracle</a>.</p></li>
<li><p>Then, install the Certora Prover: <code class="docutils literal notranslate"><span class="pre">pip3</span> <span class="pre">install</span> <span class="pre">certora-cli-beta</span></code>.</p>
<div class="admonition tip">
<p class="admonition-title">Tip</p>
<p>Always use a Python virtual environment when installing packages.</p>
</div>
</li>
<li><p>Recall that you received a <em>Certora Key</em> in your email (Step 2).
Use the key to set a temporary environment variable like so
<code class="docutils literal notranslate"><span class="pre">export</span> <span class="pre">CERTORAKEY=&lt;personal_access_key&gt;</span></code>.
Alternatively, to store the key in your profile see
<a class="reference internal" href="../user-guide/install.html#installation-step-3"><span class="std std-ref">Step 3 of the Prover installation</span></a>.</p></li>
</ol>
</section>
<section id="rust-and-stellar-cli-setup">
<h2>Rust and Stellar CLI Setup<a class="headerlink" href="#rust-and-stellar-cli-setup" title="Link to this heading"></a></h2>
<ol class="arabic simple">
<li><p>We recommend installing Rust as on the
<a class="reference external" href="https://www.rust-lang.org/tools/install">official Rust website</a>:
<code class="docutils literal notranslate"><span class="pre">curl</span> <span class="pre">--proto</span> <span class="pre">'=https'</span> <span class="pre">--tlsv1.2</span> <span class="pre">-sSf</span> <span class="pre">https://sh.rustup.rs</span> <span class="pre">|</span> <span class="pre">sh</span></code></p></li>
<li><p>Next, install the WASM target like so: <code class="docutils literal notranslate"><span class="pre">rustup</span> <span class="pre">target</span> <span class="pre">add</span> <span class="pre">wasm32-unknown-unknown</span></code></p></li>
<li><p>We recommend setting up the Stellar CLI as shown
<a class="reference external" href="https://developers.stellar.org/docs/build/smart-contracts/getting-started/setup#install-the-stellar-cli">here</a>.</p></li>
<li><p>We also recommend installing the <a class="reference external" href="https://github.com/WebAssembly/wabt">wabt</a> toolkit.
<code class="docutils literal notranslate"><span class="pre">wasm2wat</span></code> is a useful tool for converting the WASM bytecode to a human readable format.
Ensure that <code class="docutils literal notranslate"><span class="pre">wasm2wat</span></code> is executable as a command from your terminal.
You will have to add <code class="docutils literal notranslate"><span class="pre">wabt/bin</span></code> to your <code class="docutils literal notranslate"><span class="pre">PATH</span></code> by running
<code class="docutils literal notranslate"><span class="pre">export</span> <span class="pre">PATH=~/path/to/wabt/bin:$PATH</span></code>.</p></li>
<li><p>Install <cite>just</cite> like so: <code class="docutils literal notranslate"><span class="pre">cargo</span> <span class="pre">install</span> <span class="pre">just</span></code>.</p></li>
<li><p>Finally, install <code class="docutils literal notranslate"><span class="pre">rustfilt</span></code> like so: <code class="docutils literal notranslate"><span class="pre">cargo</span> <span class="pre">install</span> <span class="pre">rustfilt</span></code>.</p></li>
</ol>
<hr class="docutils">
<p>With that, you should be all set for using Certora Sunbeam. Congratulations!</p>
<p>To learn more about using Certora Sunbeam, check out the
<a class="reference external" href="https://certora-sunbeam-tutorials.readthedocs-hosted.com/en/latest/">Sunbeam Tutorials</a>.</p>
</section>
</section>


           </div>
          </div>
          <footer><div class="rst-footer-buttons" role="navigation" aria-label="Footer">
        <a href="index.html" class="btn btn-neutral float-left" title="Sunbeam: Verification for Soroban" accesskey="p" rel="prev"><span class="fa fa-arrow-circle-left" aria-hidden="true"></span> Previous</a>
        <a href="usage.html" class="btn btn-neutral float-right" title="User Guide For Sunbeam" accesskey="n" rel="next">Next <span class="fa fa-arrow-circle-right" aria-hidden="true"></span></a>
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