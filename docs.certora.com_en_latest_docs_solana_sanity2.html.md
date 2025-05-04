<!DOCTYPE html><html class="writer-html5" lang="en" data-content_root="../../"><head>
  <meta charset="utf-8"><meta name="viewport" content="width=device-width, initial-scale=1">

  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Rule Sanity Checks (Solana) — Certora Prover Documentation 0.0 documentation</title>
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
    <link rel="next" title="Troubleshooting" href="troubleshooting.html">
    <link rel="prev" title="Understanding Prover Output for Solana Programs" href="output.html"> 
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
<li class="toctree-l1 current" aria-expanded="true"><a class="reference internal" href="index.html"><button class="toctree-expand" title="Open/close menu"></button>The Certora Solana Prover</a><ul class="" aria-expanded="false">
<li class="toctree-l2"><a class="reference internal" href="installation.html">Get started with the Solana Certora Prover</a></li>
<li class="toctree-l2"><a class="reference internal" href="usage.html">Using the Solana Certora Prover</a></li>
<li class="toctree-l2"><a class="reference internal" href="speclanguage.html">Certora Verification Language for Rust (CVLR)</a></li>
<li class="toctree-l2"><a class="reference internal" href="options.html">Solana-Specific Options / CLI Flags</a></li>
<li class="toctree-l2"><a class="reference internal" href="output.html">Understanding Prover Output for Solana Programs</a></li>
<li class="toctree-l2 current" aria-expanded="true"><a class="reference internal current" href="#" aria-expanded="true"><button class="toctree-expand" title="Open/close menu"></button>Rule Sanity Checks (Solana)</a><ul>
<li class="toctree-l3"><a class="reference internal" href="#vacuity-checks">Vacuity checks</a></li>
</ul>
</li>
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
      <li class="breadcrumb-item active">Rule Sanity Checks (Solana)</li>
      <li class="wy-breadcrumbs-aside">
            <a href="../../_sources/docs/solana/sanity.md.txt" rel="nofollow"> View page source</a>
      </li>
  </ul>
  <hr>
</div>
          <div role="main" class="document" itemscope="itemscope" itemtype="http://schema.org/Article">
           <div itemprop="articleBody">
             
  <section id="rule-sanity-checks-solana">
<h1>Rule Sanity Checks (Solana)<a class="headerlink" href="#rule-sanity-checks-solana" title="Link to this heading"></a></h1>
<p>The <a class="reference internal" href="../prover/cli/options.html#rule-sanity"><span class="std std-ref">rule_sanity</span></a> option enables automatic checks that warn
about potential problems in the specification. Currently the only supported sanity check is the one called vacuity.</p>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>This is the documentation for the sanity checks for Solana.
If you are looking for the Sanity checks for Solidity, please refer to <a class="reference external" href="https://docs.certora.com/en/latest/docs/prover/checking/sanity.html">this section</a>.</p>
</div>
<p>The <code class="docutils literal notranslate"><span class="pre">--rule_sanity</span></code> option can be set to <code class="docutils literal notranslate"><span class="pre">none</span></code> or <code class="docutils literal notranslate"><span class="pre">basic</span></code> and controls whether the sanity checks should be executed:</p>
<ul class="simple">
<li><p>With <code class="docutils literal notranslate"><span class="pre">--rule_sanity</span> <span class="pre">none</span></code> or without passing <code class="docutils literal notranslate"><span class="pre">--rule_sanity</span></code>, no sanity check is performed.</p></li>
<li><p>With <code class="docutils literal notranslate"><span class="pre">--rule_sanity</span> <span class="pre">basic</span></code> or simply <code class="docutils literal notranslate"><span class="pre">--rule_sanity</span></code> without a mode, the sanity checks are executed.</p></li>
</ul>
<p>Each sanity check adds a new child node to every rule in the rule tree of the
rule report. Each check transforms the the original program into a variant where
<code class="docutils literal notranslate"><span class="pre">cvlr_satisfy!(true)</span></code> is inserted at the end of the program, and all calls to
<code class="docutils literal notranslate"><span class="pre">cvlr_assert</span></code> are removed.
If the sanity check fails on a rule, the sanity node in the rule
report is displayed as a yellow icon, and its status propagates to the
parent rule’s node (see below for an example).</p>
<p>The remainder of this document describes the vacuity check in detail.</p>
<section id="vacuity-checks">
<span id="solana-sanity-vacuity"></span><h2>Vacuity checks<a class="headerlink" href="#vacuity-checks" title="Link to this heading"></a></h2>
<p>The <strong>vacuity</strong> sanity check ensures that even when ignoring all the
user-provided assertions, the end of the rule is reachable. This check ensures
that the combination of <code class="docutils literal notranslate"><span class="pre">cvlr_assume!</span></code> statements and implicit panics are not
contradictory. Rules that are satisfied due to contradictory assumptions are
called <a class="reference internal" href="../user-guide/glossary.html#term-vacuous"><span class="xref std std-term">vacuous</span></a>. Since vacuous rules do not actually check any
assertion, they are almost certainly incorrect.</p>
<p>For example, the following rule is vacuous (and is flagged by the vacuity check):</p>
<div class="highlight-rs notranslate"><div class="highlight"><pre id="codecell0"><span></span><span class="cp">#[rule]</span>
<span class="k">pub</span><span class="w"> </span><span class="k">fn</span><span class="w"> </span><span class="nf">rule_vacuity_test_expect_sanity_failure</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kd">let</span><span class="w"> </span><span class="n">amount</span><span class="p">:</span><span class="w"> </span><span class="kt">u64</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">nondet</span><span class="p">();</span>

<span class="w">    </span><span class="n">cvlr_assume</span><span class="o">!</span><span class="p">(</span><span class="n">amount</span><span class="w"> </span><span class="o">&gt;=</span><span class="w"> </span><span class="mi">2</span><span class="p">);</span>
<span class="w">    </span><span class="n">cvlr_assume</span><span class="o">!</span><span class="p">(</span><span class="n">amount</span><span class="w"> </span><span class="o">&lt;=</span><span class="w"> </span><span class="mi">1</span><span class="p">);</span>
<span class="w">    </span><span class="n">cvlr_assert</span><span class="o">!</span><span class="p">(</span><span class="n">amount</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="mi">1</span><span class="p">);</span><span class="w"> </span>
<span class="w">    </span><span class="c1">// Expect a sanity failure here as the assumptions are conflicting</span>
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
<p>Since the two assumes <code class="docutils literal notranslate"><span class="pre">amount</span> <span class="pre">&gt;=</span> <span class="pre">2</span></code> and <code class="docutils literal notranslate"><span class="pre">amount</span> <span class="pre">&lt;=</span> <span class="pre">1</span></code> contradict each other, this rule
always passes, regardless of the content of the assertion. This is an
example of a <a class="reference internal" href="../user-guide/glossary.html#term-vacuous"><span class="xref std std-term">vacuous</span></a> rule — one that passes only because the
preconditions are contradictory.</p>
<p>In the rule report, a vacuity check adds a node called <code class="docutils literal notranslate"><span class="pre">rule_not_vacuous_cvlr</span></code>
to each rule.  For example, see how the rule
<code class="docutils literal notranslate"><span class="pre">rule_vacuity_test_expect_sanity_failure</span></code> from above is reported as failing
sanity, as <code class="docutils literal notranslate"><span class="pre">rule_not_vacuous_cvlr</span></code> fails.  Below you see an example of a rule
without the contradicting <code class="docutils literal notranslate"><span class="pre">assume</span></code>s that does not fail vacuity.</p>
<p><img alt="Screenshot of vacuity subrule" src="../../_images/vacuity_check.png" width="483" height="74"></p>
</section>
</section>


           </div>
          </div>
          <footer><div class="rst-footer-buttons" role="navigation" aria-label="Footer">
        <a href="output.html" class="btn btn-neutral float-left" title="Understanding Prover Output for Solana Programs" accesskey="p" rel="prev"><span class="fa fa-arrow-circle-left" aria-hidden="true"></span> Previous</a>
        <a href="troubleshooting.html" class="btn btn-neutral float-right" title="Troubleshooting" accesskey="n" rel="next">Next <span class="fa fa-arrow-circle-right" aria-hidden="true"></span></a>
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