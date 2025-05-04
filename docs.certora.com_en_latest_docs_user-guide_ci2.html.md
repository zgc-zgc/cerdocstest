<!DOCTYPE html><html class="writer-html5" lang="en" data-content_root="../../"><head>
  <meta charset="utf-8"><meta name="viewport" content="width=device-width, initial-scale=1">

  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>CI Configuration — Certora Prover Documentation 0.0 documentation</title>
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
    <link rel="next" title="Syntax Highlighting on GitHub" href="github_highlighting.html">
    <link rel="prev" title="Checking Specifications" href="checking.html"> 
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
<li class="toctree-l2 current" aria-expanded="true"><a class="reference internal current" href="#" aria-expanded="true">CI Configuration</a></li>
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
      <li class="breadcrumb-item active">CI Configuration</li>
      <li class="wy-breadcrumbs-aside">
            <a href="../../_sources/docs/user-guide/ci.rst.txt" rel="nofollow"> View page source</a>
      </li>
  </ul>
  <hr>
</div>
          <div role="main" class="document" itemscope="itemscope" itemtype="http://schema.org/Article">
           <div itemprop="articleBody">
             
  <section id="ci-configuration">
<h1>CI Configuration<a class="headerlink" href="#ci-configuration" title="Link to this heading"></a></h1>
<p>Follow these steps to configure CI for GitHub Actions on your repository:</p>
<ul class="simple">
<li><dl class="simple">
<dt>Step 1:</dt><dd><p>Add the Certora CLI key <a class="reference external" href="https://docs.github.com/en/actions/security-guides/using-secrets-in-github-actions#creating-secrets-for-a-repository">as a secret</a> to your repository, the secret name is <cite>CERTORAKEY</cite>
and the value is the key provided.</p>
</dd>
</dl>
</li>
<li><dl class="simple">
<dt>Step 2:</dt><dd><p>Create a <code class="code highlight bash docutils literal highlight-bash">certora_verification.yml</code> file under <code class="code highlight bash docutils literal highlight-bash">.github</code> directory and
use the following <cite>.yaml</cite> example as a template you can use to start running <cite>certora-cli</cite>.</p>
</dd>
</dl>
</li>
</ul>
<div class="highlight-yaml notranslate"><div class="highlight"><pre id="codecell0"><span></span><span class="nt">name</span><span class="p">:</span><span class="w"> </span><span class="l l-Scalar l-Scalar-Plain">certora-verification</span>

<span class="nt">on</span><span class="p">:</span>
<span class="w">  </span><span class="nt">push</span><span class="p">:</span>
<span class="w">    </span><span class="nt">branches</span><span class="p">:</span>
<span class="w">      </span><span class="p p-Indicator">-</span><span class="w"> </span><span class="l l-Scalar l-Scalar-Plain">main</span>
<span class="w">  </span><span class="nt">pull_request</span><span class="p">:</span>
<span class="w">    </span><span class="nt">branches</span><span class="p">:</span>
<span class="w">      </span><span class="p p-Indicator">-</span><span class="w"> </span><span class="l l-Scalar l-Scalar-Plain">main</span>
<span class="w">  </span><span class="nt">workflow_dispatch</span><span class="p">:</span>
<span class="nt">jobs</span><span class="p">:</span>
<span class="w">  </span><span class="nt">verify</span><span class="p">:</span>
<span class="w">    </span><span class="nt">runs-on</span><span class="p">:</span><span class="w"> </span><span class="l l-Scalar l-Scalar-Plain">ubuntu-latest</span>
<span class="w">    </span><span class="nt">steps</span><span class="p">:</span>
<span class="w">      </span><span class="p p-Indicator">-</span><span class="w"> </span><span class="nt">uses</span><span class="p">:</span><span class="w"> </span><span class="l l-Scalar l-Scalar-Plain">actions/checkout@v4</span>
<span class="w">        </span><span class="nt">with</span><span class="p">:</span>
<span class="w">          </span><span class="nt">submodules</span><span class="p">:</span><span class="w"> </span><span class="l l-Scalar l-Scalar-Plain">recursive</span>

<span class="w">      </span><span class="p p-Indicator">-</span><span class="w"> </span><span class="nt">name</span><span class="p">:</span><span class="w"> </span><span class="l l-Scalar l-Scalar-Plain">Install python</span>
<span class="w">        </span><span class="nt">uses</span><span class="p">:</span><span class="w"> </span><span class="l l-Scalar l-Scalar-Plain">actions/setup-python@v2</span>
<span class="w">        </span><span class="nt">with</span><span class="p">:</span><span class="w"> </span><span class="p p-Indicator">{</span><span class="nt"> python-version</span><span class="p">:</span><span class="w"> </span><span class="nv">3.9</span><span class="w"> </span><span class="p p-Indicator">}</span>

<span class="w">      </span><span class="p p-Indicator">-</span><span class="w"> </span><span class="nt">name</span><span class="p">:</span><span class="w"> </span><span class="l l-Scalar l-Scalar-Plain">Install java</span>
<span class="w">        </span><span class="nt">uses</span><span class="p">:</span><span class="w"> </span><span class="l l-Scalar l-Scalar-Plain">actions/setup-java@v1</span>
<span class="w">        </span><span class="nt">with</span><span class="p">:</span><span class="w"> </span><span class="p p-Indicator">{</span><span class="nt"> java-version</span><span class="p">:</span><span class="w"> </span><span class="s">"11"</span><span class="p p-Indicator">,</span><span class="nt"> java-package</span><span class="p">:</span><span class="w"> </span><span class="nv">jre</span><span class="w"> </span><span class="p p-Indicator">}</span>

<span class="w">      </span><span class="c1"># It's recommended to pin the latest certora-cli version available in https://pypi.org/project/certora-cli/</span>
<span class="w">      </span><span class="p p-Indicator">-</span><span class="w"> </span><span class="nt">name</span><span class="p">:</span><span class="w"> </span><span class="l l-Scalar l-Scalar-Plain">Install certora cli</span>
<span class="w">        </span><span class="nt">run</span><span class="p">:</span><span class="w"> </span><span class="l l-Scalar l-Scalar-Plain">pip install certora-cli==7.3.0</span>

<span class="w">      </span><span class="p p-Indicator">-</span><span class="w"> </span><span class="nt">name</span><span class="p">:</span><span class="w"> </span><span class="l l-Scalar l-Scalar-Plain">Install solc</span>
<span class="w">        </span><span class="nt">run</span><span class="p">:</span><span class="w"> </span><span class="p p-Indicator">|</span>
<span class="w">          </span><span class="no">pip install solc-select</span>
<span class="w">          </span><span class="no">solc-select install 0.8.23</span>
<span class="w">          </span><span class="no">solc-select use 0.8.23</span>

<span class="w">          </span><span class="no"># If your project depends on compiling with multiple solc versions, you can install and differentiate them using these commands.</span>
<span class="w">          </span><span class="no"># wget https://github.com/ethereum/solidity/releases/download/v0.8.23/solc-static-linux</span>
<span class="w">          </span><span class="no"># chmod +x solc-static-linux</span>
<span class="w">          </span><span class="no"># sudo mv solc-static-linux /usr/local/bin/solc8.23</span>

<span class="w">      </span><span class="p p-Indicator">-</span><span class="w"> </span><span class="nt">name</span><span class="p">:</span><span class="w"> </span><span class="l l-Scalar l-Scalar-Plain">Verify ${{ matrix.rule }}</span>
<span class="w">        </span><span class="nt">env</span><span class="p">:</span>
<span class="w">          </span><span class="nt">CERTORAKEY</span><span class="p">:</span><span class="w"> </span><span class="l l-Scalar l-Scalar-Plain">${{ secrets.CERTORAKEY }}</span>
<span class="w">        </span><span class="nt">run</span><span class="p">:</span><span class="w"> </span><span class="l l-Scalar l-Scalar-Plain">certoraRun  ${{ matrix.rule }}</span>

<span class="w">    </span><span class="nt">strategy</span><span class="p">:</span>
<span class="w">      </span><span class="nt">fail-fast</span><span class="p">:</span><span class="w"> </span><span class="l l-Scalar l-Scalar-Plain">false</span>
<span class="w">      </span><span class="nt">max-parallel</span><span class="p">:</span><span class="w"> </span><span class="l l-Scalar l-Scalar-Plain">16</span>
<span class="w">      </span><span class="nt">matrix</span><span class="p">:</span>
<span class="w">        </span><span class="nt">rule</span><span class="p">:</span>
<span class="w">            </span><span class="p p-Indicator">-</span><span class="w"> </span><span class="l l-Scalar l-Scalar-Plain">path-to-conf1.conf --rule rule1</span><span class="w"> </span><span class="c1"># https://docs.certora.com/en/latest/docs/prover/cli/options.html#rule-rule-name</span>
<span class="w">            </span><span class="p p-Indicator">-</span><span class="w"> </span><span class="l l-Scalar l-Scalar-Plain">path-to-conf1.conf --exclude_rule rule2</span><span class="w"> </span><span class="c1"># https://docs.certora.com/en/latest/docs/prover/cli/options.html#exclude-rule-rule-name-pattern</span>
<span class="w">            </span><span class="p p-Indicator">-</span><span class="w"> </span><span class="l l-Scalar l-Scalar-Plain">path-to-conf2.conf</span><span class="w"> </span><span class="c1"># run the entire conf</span>
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


           </div>
          </div>
          <footer><div class="rst-footer-buttons" role="navigation" aria-label="Footer">
        <a href="checking.html" class="btn btn-neutral float-left" title="Checking Specifications" accesskey="p" rel="prev"><span class="fa fa-arrow-circle-left" aria-hidden="true"></span> Previous</a>
        <a href="github_highlighting.html" class="btn btn-neutral float-right" title="Syntax Highlighting on GitHub" accesskey="n" rel="next">Next <span class="fa fa-arrow-circle-right" aria-hidden="true"></span></a>
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