<!DOCTYPE html><html class="writer-html5" lang="en" data-content_root="../../../"><head>
  <meta charset="utf-8"><meta name="viewport" content="width=device-width, initial-scale=1">

  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Coverage Info — Certora Prover Documentation 0.0 documentation</title>
      <link rel="stylesheet" type="text/css" href="../../../_static/pygments.css?v=80d5e7a1">
      <link rel="stylesheet" type="text/css" href="../../../_static/css/theme.css?v=19f00094">
      <link rel="stylesheet" type="text/css" href="../../../_static/copybutton.css?v=76b2166b">
      <link rel="stylesheet" type="text/css" href="../../../_static/custom.css?v=098d337b">
      <link rel="stylesheet" type="text/css" href="../../../_static/sphinx-design.min.css?v=87e54e7c">

  
  <!--[if lt IE 9]>
    <script src="../../../_static/js/html5shiv.min.js"></script>
  <![endif]-->
  
        <script src="../../../_static/jquery.js?v=5d32c60e"></script>
        <script src="../../../_static/_sphinx_javascript_frameworks_compat.js?v=2cd50e6c"></script>
        <script src="../../../_static/documentation_options.js?v=837179f8"></script>
        <script src="../../../_static/doctools.js?v=9a2dae69"></script>
        <script src="../../../_static/sphinx_highlight.js?v=dc90522c"></script>
        <script src="../../../_static/clipboard.min.js?v=a7894cd8"></script>
        <script src="../../../_static/copybutton.js?v=f281be69"></script>
        <script src="../../../_static/design-tabs.js?v=f930bc37"></script>
    <script src="../../../_static/js/theme.js"></script>
    <link rel="index" title="Index" href="../../../genindex.html">
    <link rel="search" title="Search" href="../../../search.html">
    <link rel="next" title="Bug Injection" href="injection.html">
    <link rel="prev" title="Rule Sanity Checks" href="sanity.html"> 
</head>

<body class="wy-body-for-nav"> 
  <div class="wy-grid-for-nav">
    <nav data-toggle="wy-nav-shift" class="wy-nav-side">
      <div class="wy-side-scroll">
        <div class="wy-side-nav-search">

          
          
          <a href="../../../index.html" class="icon icon-home">
            Certora Prover Documentation
              <img src="../../../_static/Certora_Logo_Black.svg" class="logo" alt="Logo" width="646" height="188">
          </a>
<div role="search">
  <form id="rtd-search-form" class="wy-form" action="../../../search.html" method="get">
    <input type="text" name="q" placeholder="Search docs" aria-label="Search docs">
    <input type="hidden" name="check_keywords" value="yes">
    <input type="hidden" name="area" value="default">
  </form>
</div>
        </div><div class="wy-menu wy-menu-vertical" data-spy="affix" role="navigation" aria-label="Navigation menu">
              <p class="caption" role="heading"><span class="caption-text">Contents</span></p>
<ul class="current" aria-expanded="true">
<li class="toctree-l1"><a class="reference internal" href="../../user-guide/index.html">Certora User’s Guide</a></li>
<li class="toctree-l1"><a class="reference internal" href="../../cvl/index.html">The Certora Verification Language</a></li>
<li class="toctree-l1 current" aria-expanded="true"><a class="reference internal" href="../index.html"><button class="toctree-expand" title="Open/close menu"></button>The Certora Prover</a><ul class="" aria-expanded="false">
<li class="toctree-l2"><a class="reference internal" href="../intro.html">Introduction</a></li>
<li class="toctree-l2"><a class="reference internal" href="../../user-guide/install.html">Installation</a></li>
<li class="toctree-l2"><a class="reference internal" href="../approx/index.html">Prover Approximations</a></li>
<li class="toctree-l2"><a class="reference internal" href="../techniques/index.html">Techniques Used by the Certora Prover</a></li>
<li class="toctree-l2"><a class="reference internal" href="../diagnosis/index.html">Diagnostic Tools</a></li>
<li class="toctree-l2 current" aria-expanded="true"><a class="reference internal" href="index.html"><button class="toctree-expand" title="Open/close menu"></button>Checking Specifications</a><ul class="" aria-expanded="false">
<li class="toctree-l3"><a class="reference internal" href="sanity.html">Rule Sanity Checks</a></li>
<li class="toctree-l3 current" aria-expanded="true"><a class="reference internal current" href="#" aria-expanded="true"><button class="toctree-expand" title="Open/close menu"></button>Coverage Info</a><ul>
<li class="toctree-l4"><a class="reference internal" href="#examples">Examples</a></li>
<li class="toctree-l4"><a class="reference internal" href="#basic-vs-advanced-mode">Basic vs. advanced mode</a></li>
<li class="toctree-l4"><a class="reference internal" href="#completeness">Completeness</a></li>
</ul>
</li>
<li class="toctree-l3"><a class="reference internal" href="injection.html">Bug Injection</a></li>
<li class="toctree-l3"><a class="reference internal" href="mutation.html">Mutation Testing</a></li>
</ul>
</li>
<li class="toctree-l2"><a class="reference internal" href="../cli/index.html">Certora Prover CLI</a></li>
<li class="toctree-l2"><a class="reference internal" href="../portal/using.html">Using the Certora Portal</a></li>
<li class="toctree-l2"><a class="reference internal" href="../changelog/index.html">Changelogs</a></li>
</ul>
</li>
<li class="toctree-l1"><a class="reference internal" href="../../sunbeam/index.html">Sunbeam: Verification for Soroban</a></li>
<li class="toctree-l1"><a class="reference internal" href="../../solana/index.html">The Certora Solana Prover</a></li>
<li class="toctree-l1"><a class="reference internal" href="../../gambit/index.html">Gambit: Mutation Generator for Solidity</a></li>
</ul>
<p class="caption" role="heading"><span class="caption-text">Additional information</span></p>
<ul>
<li class="toctree-l1"><a class="reference internal" href="../../equiv-check/index.html">The Certora Equivalence Checker</a></li>
<li class="toctree-l1"><a class="reference internal" href="../../whitepaper/index.html">Certora Technology White Paper</a></li>
</ul>
<ul>
<li class="toctree-l1"><a class="reference internal" href="../../../genindex.html">Index</a></li>
</ul>

        </div>
      </div>
    </nav>

    <section data-toggle="wy-nav-shift" class="wy-nav-content-wrap"><nav class="wy-nav-top" aria-label="Mobile navigation menu">
          <i data-toggle="wy-nav-top" class="fa fa-bars"></i>
          <a href="../../../index.html">Certora Prover Documentation</a>
      </nav>

      <div class="wy-nav-content">
        <div class="rst-content">
          <div role="navigation" aria-label="Page navigation">
  <ul class="wy-breadcrumbs">
      <li><a href="../../../index.html" class="icon icon-home" aria-label="Home"></a></li>
          <li class="breadcrumb-item"><a href="../index.html">The Certora Prover</a></li>
          <li class="breadcrumb-item"><a href="index.html">Checking Specifications</a></li>
      <li class="breadcrumb-item active">Coverage Info</li>
      <li class="wy-breadcrumbs-aside">
            <a href="../../../_sources/docs/prover/checking/coverage-info.md.txt" rel="nofollow"> View page source</a>
      </li>
  </ul>
  <hr>
</div>
          <div role="main" class="document" itemscope="itemscope" itemtype="http://schema.org/Article">
           <div itemprop="articleBody">
             
  <section id="coverage-info">
<h1>Coverage Info<a class="headerlink" href="#coverage-info" title="Link to this heading"></a></h1>
<p>The <a class="reference internal" href="../cli/options.html#coverage-info"><span class="std std-ref">coverage_info</span></a> flag enables automatic computation of coverage
information for a verification run. In particular, using this flag can help you
answer questions such as:</p>
<ul class="simple">
<li><p><em>Are all solidity functions from the input involved in proving my rules?</em></p></li>
<li><p><em>Are all solidity commands from the input involved in proving my rules?</em></p></li>
<li><p><em>Supposing an <code class="docutils literal notranslate"><span class="pre">assert</span></code> in my rule is not reachable, what is the reason for the
unreachability?</em></p></li>
<li><p><em>Do I really need all hooks that are defined in my <code class="docutils literal notranslate"><span class="pre">.spec</span></code> file(s)?</em></p></li>
<li><p><em>Do I really need all <code class="docutils literal notranslate"><span class="pre">require</span></code> statements in my rule?</em></p></li>
<li><p><em>Do I really need to initialize a CVL variable in my rule?</em></p></li>
<li><p><em>Do I really need all of the preserved blocks in my CVL <code class="docutils literal notranslate"><span class="pre">invariant</span></code>?</em></p></li>
</ul>
<p>To answer the above questions, the Certora Prover identifies a minimal subset of
the commands in the input <code class="docutils literal notranslate"><span class="pre">.sol</span></code> and <code class="docutils literal notranslate"><span class="pre">.spec</span></code> files that are relevant for proving
the CVL properties. If some of the input <code class="docutils literal notranslate"><span class="pre">.sol</span></code> commands are not relevant for
deriving the proof, it might indicate that the specification does not cover all
behavior implemented in the smart contract. If some of the input <code class="docutils literal notranslate"><span class="pre">.spec</span></code>
commands are irrelevant (typically unnecessary <code class="docutils literal notranslate"><span class="pre">require</span></code> statements or variable
initializations), it indicates that the CVL rules/invariants can be made
stronger.</p>
<p>You can access the coverage visualization via <code class="docutils literal notranslate"><span class="pre">Job</span> <span class="pre">Info</span> <span class="pre">-&gt;</span> <span class="pre">Coverage</span> <span class="pre">Info</span> <span class="pre">page</span></code>
buttons:</p>
<p><img alt="Coverage Info Button" src="../../../_images/coverage-info-button.png" width="1088" height="574"></p>
<section id="examples">
<h2>Examples<a class="headerlink" href="#examples" title="Link to this heading"></a></h2>
<section id="tautology-example">
<h3>Tautology example<a class="headerlink" href="#tautology-example" title="Link to this heading"></a></h3>
<p>Consider the following CVL rule called <code class="docutils literal notranslate"><span class="pre">tautology</span></code>:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell0"><span></span><span class="k">rule</span><span class="w"> </span><span class="nc">tautology</span><span class="p">(</span><span class="kt">uint256</span><span class="w"> </span>fundId<span class="p">,</span><span class="w"> </span><span class="kt">method</span><span class="w"> </span>f<span class="p">)</span><span class="w"> </span><span class="p">{</span><span class="w"> </span>
<span class="w">	</span><span class="kt">env</span><span class="w"> </span>e<span class="p">;</span>
<span class="w">	</span><span class="kt">address</span><span class="w"> </span>manager<span class="w"> </span><span class="o">=</span><span class="w">  </span>getCurrentManager<span class="p">(</span>fundId<span class="p">);</span>
<span class="w">	</span><span class="kt">address</span><span class="w"> </span>other<span class="p">;</span>
<span class="w">	</span><span class="kr">require</span><span class="w"> </span>other<span class="w"> </span><span class="o">!=</span><span class="w"> </span>manager<span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span>other<span class="w"> </span><span class="o">!=</span><span class="w"> </span>e<span class="p">.</span><span class="kc">msg.sender</span><span class="p">;</span>
<span class="w">	</span><span class="kt">calldataarg</span><span class="w"> </span>args<span class="p">;</span>
<span class="w">	</span>f<span class="p">(</span>e<span class="p">,</span>args<span class="p">);</span>
<span class="w">	</span><span class="kt">address</span><span class="w"> </span>newManager<span class="w"> </span><span class="o">=</span><span class="w"> </span>getCurrentManager<span class="p">(</span>fundId<span class="p">);</span>
<span class="w">	</span><span class="kr">assert</span><span class="w"> </span>newManager<span class="o">!=</span><span class="w"> </span>other<span class="w"> </span><span class="o">||</span><span class="w"> </span>newManager<span class="w"> </span><span class="o">!=</span><span class="w"> </span>manager<span class="p">;</span>
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
<p>Notice that we required that <code class="docutils literal notranslate"><span class="pre">other</span> <span class="pre">!=</span> <span class="pre">manager</span></code> and hence the <code class="docutils literal notranslate"><span class="pre">assert</span></code> is
necessarily <code class="docutils literal notranslate"><span class="pre">true</span></code> (see the concept of a <a class="reference internal" href="../../user-guide/glossary.html#term-tautology"><span class="xref std std-term">tautology</span></a>). The executions of
<code class="docutils literal notranslate"><span class="pre">getCurrentManager(...)</span></code> and <code class="docutils literal notranslate"><span class="pre">f(...)</span></code> are completely irrelevant.</p>
<p>The coverage visualization is shown below. It consists of two <em>panes</em>:</p>
<ol class="arabic simple">
<li><p>The left pane shows <em>per-line</em> visualization.</p></li>
<li><p>The right pane shows detailed info about individual visualized lines.</p></li>
</ol>
<p><img alt="Example Coverage Info Visualization" src="../../../_images/tautology-sol-and-spec-cropped.png" width="3249" height="1768"></p>
<p>In particular, in the left pane, we highlight lines from individual <code class="docutils literal notranslate"><span class="pre">.sol</span></code> and
<code class="docutils literal notranslate"><span class="pre">.spec</span></code> files. Every line may optionally have a green, yellow, or red background
color. No background means we have no information about this line, i.e. it might
or might not be needed for the proof. Green, red or yellow background means we
have some information about values of commands on the line:</p>
<ol class="arabic simple">
<li><p>Green means that all of the values on the line are relevant for proving the
property.</p></li>
<li><p>Red means that none of the values on the line is relevant for proving the
property. In particular, you can arbitrary change the values and the property
would still hold.</p></li>
<li><p>Yellow means that some of the values on the line are relevant and some are
not.</p></li>
</ol>
<p>Furthermore, if we have multiple rules/invariants or a parametric rule (such as
our <code class="docutils literal notranslate"><span class="pre">tautology</span></code>), we can also have multiple rules/invariants mapping to a single
<code class="docutils literal notranslate"><span class="pre">.sol</span></code> or <code class="docutils literal notranslate"><span class="pre">.spec</span></code> line. In such a case, a yellow line means that some of the
values on the line are relevant for proving some of the rules/methods/invariants
and some of the values are not relevant. If you want to generate coverage
visualization for a single rule or method, use <a class="reference internal" href="../cli/options.html#rule"><span class="std std-ref">rule</span></a> or <a class="reference internal" href="../cli/options.html#method"><span class="std std-ref">method</span></a>.</p>
<p>The right pane provides detailed information about individual values mapped to
the lines grouped by the rule/method/invariant name (denoted <em>rule</em>). For
instance, in the Tautology example, we can see that the value of the command
<code class="docutils literal notranslate"><span class="pre">other</span> <span class="pre">!=</span> <span class="pre">manager</span></code> on line <code class="docutils literal notranslate"><span class="pre">11</span></code> matters, whereas the value of <code class="docutils literal notranslate"><span class="pre">other</span> <span class="pre">!=</span> <span class="pre">e.msg.sender</span></code> is irrelevant for the proof. Also, note that the pane shows e.g.
both <code class="docutils literal notranslate"><span class="pre">other</span> <span class="pre">!=</span> <span class="pre">manager</span></code> and <code class="docutils literal notranslate"><span class="pre">other</span> <span class="pre">==</span> <span class="pre">manager</span></code>; this is due our internal
representation of the input where we encode <code class="docutils literal notranslate"><span class="pre">other</span> <span class="pre">!=</span> <span class="pre">manager</span></code> as <code class="docutils literal notranslate"><span class="pre">!(other</span> <span class="pre">==</span> <span class="pre">manager)</span></code>.</p>
</section>
</section>
<section id="basic-vs-advanced-mode">
<h2>Basic vs. advanced mode<a class="headerlink" href="#basic-vs-advanced-mode" title="Link to this heading"></a></h2>
<p>The <code class="docutils literal notranslate"><span class="pre">--coverage_info</span></code> flag takes three possible values: <code class="docutils literal notranslate"><span class="pre">none</span></code>, <code class="docutils literal notranslate"><span class="pre">basic</span></code> and
<code class="docutils literal notranslate"><span class="pre">advanced</span></code>:</p>
<ol class="arabic simple">
<li><p><code class="docutils literal notranslate"><span class="pre">none</span></code> means no coverage analysis,</p></li>
<li><p><code class="docutils literal notranslate"><span class="pre">basic</span></code> means relatively fast but possibly very imprecise analysis (i.e. can
claim that some values are not relevant even if they are, and also vice
versa),</p></li>
<li><p>and <code class="docutils literal notranslate"><span class="pre">advanced</span></code> means possibly slow but more precise analysis.</p></li>
</ol>
</section>
<section id="completeness">
<h2>Completeness<a class="headerlink" href="#completeness" title="Link to this heading"></a></h2>
<p>We perform the coverage analysis on our internal <a class="reference internal" href="../../user-guide/glossary.html#term-SMT"><span class="xref std std-term">SMT</span></a> representation of the <a class="reference internal" href="../../user-guide/glossary.html#term-verification-condition"><span class="xref std std-term">verification condition</span></a>, and then map the results of
the analysis to the <code class="docutils literal notranslate"><span class="pre">.sol</span></code> and <code class="docutils literal notranslate"><span class="pre">.spec</span></code> files. Unfortunately, due to the
compilation of the solidity code to EVM bytecode, we cannot maintain a complete
mapping between commands from solidity and commands in our SMT representation.
Consequently, the visualization on <code class="docutils literal notranslate"><span class="pre">.sol</span></code> files can be very limited.</p>
</section>
</section>


           </div>
          </div>
          <footer><div class="rst-footer-buttons" role="navigation" aria-label="Footer">
        <a href="sanity.html" class="btn btn-neutral float-left" title="Rule Sanity Checks" accesskey="p" rel="prev"><span class="fa fa-arrow-circle-left" aria-hidden="true"></span> Previous</a>
        <a href="injection.html" class="btn btn-neutral float-right" title="Bug Injection" accesskey="n" rel="next">Next <span class="fa fa-arrow-circle-right" aria-hidden="true"></span></a>
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