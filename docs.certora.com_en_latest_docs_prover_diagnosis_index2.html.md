<!DOCTYPE html><html class="writer-html5" lang="en" data-content_root="../../../"><head>
  <meta charset="utf-8"><meta name="viewport" content="width=device-width, initial-scale=1">

  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Diagnostic Tools — Certora Prover Documentation 0.0 documentation</title>
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
    <link rel="next" title="Checking Specifications" href="../checking/index.html">
    <link rel="prev" title="Techniques Used by the Certora Prover" href="../techniques/index.html"> 
</head>

<body class="wy-body-for-nav"> 
  <div class="wy-grid-for-nav">
    <nav data-toggle="wy-nav-shift" class="wy-nav-side">
      <div class="wy-side-scroll">
        <div class="wy-side-nav-search">

          
          
          <a href="../../../index.html" class="icon icon-home">
            Certora Prover Documentation
              <img src="../../../_static/Certora_Logo_Black.svg" class="logo" alt="Logo">
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
<li class="toctree-l2 current" aria-expanded="true"><a class="reference internal current" href="#" aria-expanded="true"><button class="toctree-expand" title="Open/close menu"></button>Diagnostic Tools</a><ul>
<li class="toctree-l3"><a class="reference internal" href="#tac-reports"><button class="toctree-expand" title="Open/close menu"></button>TAC Reports</a><ul>
<li class="toctree-l4"><a class="reference internal" href="#plain-tac-reports">Plain TAC reports</a></li>
<li class="toctree-l4"><a class="reference internal" href="#sat-tac-reports">SAT TAC reports</a></li>
<li class="toctree-l4"><a class="reference internal" href="#unsat-tac-reports">UNSAT TAC reports</a></li>
<li class="toctree-l4"><a class="reference internal" href="#timeout-tac-reports">Timeout TAC reports</a></li>
</ul>
</li>
</ul>
</li>
<li class="toctree-l2"><a class="reference internal" href="../checking/index.html">Checking Specifications</a></li>
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
      <li class="breadcrumb-item active">Diagnostic Tools</li>
      <li class="wy-breadcrumbs-aside">
            <a href="../../../_sources/docs/prover/diagnosis/index.md.txt" rel="nofollow"> View page source</a>
      </li>
  </ul>
  <hr>
</div>
          <div role="main" class="document" itemscope="itemscope" itemtype="http://schema.org/Article">
           <div itemprop="articleBody">
             
  <section id="diagnostic-tools">
<h1>Diagnostic Tools<a class="headerlink" href="#diagnostic-tools" title="Link to this heading"></a></h1>
<section id="tac-reports">
<span id="id1"></span><h2>TAC Reports<a class="headerlink" href="#tac-reports" title="Link to this heading"></a></h2>
<p><a class="reference internal" href="../../user-guide/glossary.html#term-TAC"><span class="xref std std-term">TAC</span></a> Reports provide an under-the-hood view on a given
<a class="reference internal" href="../../user-guide/glossary.html#term-verification-condition"><span class="xref std std-term">verification condition</span></a> as well as the result that the Prover produced
for that verification condition, if available. There are four variants
of TAC reports, one each for the results SAT, UNSAT, TIMEOUT, and one that
contains no information from the result. In the following, we will discuss these
variants one by one. We will begin with the TAC report without Prover result
information, since its constituents are present in the other variants as well.</p>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>In addition to the information below, there is a brief explanation of how to
use TAC reports in the
<a class="reference external" href="https://www.youtube.com/watch?v=mntP0_EN-ZQ">webinar on timeouts</a>.</p>
</div>
<section id="plain-tac-reports">
<h3>Plain TAC reports<a class="headerlink" href="#plain-tac-reports" title="Link to this heading"></a></h3>
<figure class="align-center" id="plain-tac-report">
<img alt="Plain TAC report example" src="../../../_images/rebase-tac-report-plain-annotated.png" width="3004" height="1860">
<figcaption>
<p><span class="caption-text">Example of a plain TAC report (with annotations in red)</span><a class="headerlink" href="#plain-tac-report" title="Link to this image"></a></p>
</figcaption>
</figure>
<p>At the center of a TAC report is a visualization of the verification condition’s
<a class="reference internal" href="../../user-guide/glossary.html#term-control-flow-graph"><span class="xref std std-term">control flow graph</span></a> (CFG).<a class="footnote-reference brackets" href="#nested-cfg" id="id2" role="doc-noteref"><span class="fn-bracket">[</span>1<span class="fn-bracket">]</span></a> There are two kinds of nodes.
Regular nodes and call nodes. Regular nodes have a solid outline, while call
nodes have a dashed outline. Clicking on a regular nodes will make the source
code box (discussed below) focus on the corresponding TAC source code; clicking
on a call node will replace the currently displayed CFG with the CFG that
belongs to the called method.</p>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>Only external calls are explicit in the TAC report’s CFGs. Internal calls are
inlined on the TAC source code level.</p>
</div>
<p>The upper-mid left part of a TAC report contains the TAC source code. The
details of the TAC language are outside the scope of this documentation.
Generally speaking, TAC is generated by compiler-style transformations of the
EVM bytecode together with the CVL specification. Many patterns from EVM
bytecode are retained in TAC, however inlining of functions and various
simplifications have already happened at the stage that the TAC reports display.
Also, CVL method summaries from the spec have been applied on this stage, and
any unintentional lack of summarization can be diagnosed here.</p>
<p>Some commands in the TAC source code have pointers to the program or
CVL code that the TAC program was created from. These commands are
highlighted a dotted underline; the source code location they have been
translated from is revealed on hovering with the mouse over such a command, as
displayed in the image below.</p>
<figure class="align-center" id="source-pointer-on-hover">
<img alt="Source pointer shown on hover" src="../../../_images/source-pointer-on-hover-annotated.png" width="2252" height="390">
<figcaption>
<p><span class="caption-text">source pointer is shown on hover over TAC commands that have a dotted underline</span><a class="headerlink" href="#source-pointer-on-hover" title="Link to this image"></a></p>
</figcaption>
</figure>
<p>The call-based navigation on the mid-right side of the report lists all the
calls in the TAC program. Each call is identified by a number. After the number
there is a number of arrows, indicating the nesting depth of the call, i.e.
calls from spec get one arrow, a call from a method body with one arrow gets two
arrows, etc.; see the picture below for an example. After the arrows the name of
the called method is given. Each of these calls is clickable and will lead to
the corresponding CFG.</p>
<figure class="align-center" id="call-depth-arrows">
<a class="reference internal image-reference" href="../../../_images/call-depth-arrows.png"><img alt="Arrows indicating depth of call" src="../../../_images/call-depth-arrows.png" style="height: 300px;"></a>
<figcaption>
<p><span class="caption-text">arrows indicating the “depth” of a call in the call links</span><a class="headerlink" href="#call-depth-arrows" title="Link to this image"></a></p>
</figcaption>
</figure>
<p>The bottom part of the TAC report shows a more-detailed control-flow relations
within individual nodes. These are usually not useful for the tool user, so we
will ignore them in the remainder of this document.</p>
</section>
<section id="sat-tac-reports">
<h3>SAT TAC reports<a class="headerlink" href="#sat-tac-reports" title="Link to this heading"></a></h3>
<p>Once a rule has been checked with a <a class="reference internal" href="../../user-guide/glossary.html#term-SAT"><span class="xref std std-term">SAT</span></a> outcome, a TAC report like the one
in the figure below is generated. In addition to the components of the plain TAC
report, this report variant illustrates the <a class="reference internal" href="../../user-guide/glossary.html#term-model"><span class="xref std std-term">model</span></a> (aka. counterexample)
that is provided by the SMT solver to witness violation of an <code class="docutils literal notranslate"><span class="pre">assert</span></code> command
(or the fulfillment of a <code class="docutils literal notranslate"><span class="pre">satisfy</span></code> command). The model is illustrated by a path
in the control flow graph and a valuation of the TAC program variables.</p>
<figure class="align-center" id="sat-tac-report">
<img alt="../../../_images/sat-tac-report-plain.png" src="../../../_images/sat-tac-report-plain.png">
<figcaption>
<p><span class="caption-text">example TAC report for a run with a SAT result</span><a class="headerlink" href="#sat-tac-report" title="Link to this image"></a></p>
</figcaption>
</figure>
<p>The path corresponds to the <a class="reference internal" href="../../user-guide/glossary.html#term-call-trace"><span class="xref std std-term">call trace</span></a> from the
<a class="reference internal" href="../portal/report.html#verification-report"><span class="std std-ref">report</span></a>. It is the path through the program that is taken
on the input given by the counterexample. The arrows and nodes in the control
flow graph that lie on this path are displayed in red.</p>
<p>The valuation is given in the box in the top right. It lists every variable in
the TAC program along with the value that it has in the current counterexample.</p>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>The names of the TAC variables are often not helpful for understanding what they
mean, but the context (e.g. operations they occur in, or the source pointers) can
give some hints.
Running the Prover with the option
<code class="docutils literal notranslate"><span class="pre">--prover_args</span> <span class="pre">"-canonicalizeTAC</span> <span class="pre">false"</span></code> can lead to more helpful variable names
in some cases, especially the names of CVL variables are mostly preserved.</p>
</div>
</section>
<section id="unsat-tac-reports">
<h3>UNSAT TAC reports<a class="headerlink" href="#unsat-tac-reports" title="Link to this heading"></a></h3>
<p>By default, the TAC report in the UNSAT case is the same as the plain TAC
report.</p>
<p>When the <code class="docutils literal notranslate"><span class="pre">--coverage_info</span></code> option is set either to <code class="docutils literal notranslate"><span class="pre">basic</span></code> or <code class="docutils literal notranslate"><span class="pre">advanced</span></code>
(default is <code class="docutils literal notranslate"><span class="pre">none</span></code>), a version of the TAC reports is shown that illustrates
coverage information about the rule. In particular, nodes in the control flow
graph that were used for proving the rule are displayed with a green fill color,
while nodes that were definitely irrelevant to the proof are displayed with a
yellow fill color.</p>
</section>
<section id="timeout-tac-reports">
<h3>Timeout TAC reports<a class="headerlink" href="#timeout-tac-reports" title="Link to this heading"></a></h3>
<p>In case of a Timeout result, the TAC report contains additional information that
is meant to help with preventing the timeout in the future.</p>
<figure class="align-center" id="timeout-tac-report-plain">
<img alt="../../../_images/timeout-tac-report-overview.png" src="../../../_images/timeout-tac-report-overview.png">
<figcaption>
<p><span class="caption-text">example TAC report for a run with a Timeout result</span><a class="headerlink" href="#timeout-tac-report-plain" title="Link to this image"></a></p>
</figcaption>
</figure>
<p>The figure above shows a TAC report that was generated from a Certora Prover run
that timed out. Compared to the plain TAC report, additional information is
available in three ways:</p>
<ul class="simple">
<li><p>Explanations and statistics are given in the box in the top right corner
(double click to expand).</p></li>
<li><p>CFG nodes have colors that indicate how the Prover run went and which parts
are difficult.</p></li>
<li><p>In the source code box there is difficulty information given by color
highlights to some commands and by additional text giving difficulty
statistics on difficult code blocks .</p></li>
</ul>
<section id="statistics-and-explanation-box">
<h4>Statistics- and explanation-box<a class="headerlink" href="#statistics-and-explanation-box" title="Link to this heading"></a></h4>
<p>The box in the top right of the Timeout TAC reports contains explanations on the
node colors as well as statistical information pertaining to how difficult the
verification is to solve in general and what might be the particularly difficult
parts.</p>
<figure class="align-center" id="timeout-tac-report-explanation-box">
<img alt="../../../_images/timeout-tac-report-explanation-box.png" src="../../../_images/timeout-tac-report-explanation-box.png">
<figcaption>
<p><span class="caption-text">Timeout TAC report with expanded statistics- and explanation-box</span><a class="headerlink" href="#timeout-tac-report-explanation-box" title="Link to this image"></a></p>
</figcaption>
</figure>
<p>The above picture shows the expanded statistics- and explanation box. Currently,
the contents of the box are the following:</p>
<ul class="simple">
<li><p>explanations for each color used in the CFG nodes</p></li>
<li><p>general difficulty-related statistics pertaining to the whole program</p></li>
<li><p>per-call breakdown of the “path count” statistic</p></li>
<li><p>per-call breakdown of the “number of nonlinear operations” statistic</p></li>
</ul>
</section>
<section id="split-and-heuristic-difficulty-coloring-in-cfg-and-source-code">
<h4>Split- and heuristic difficulty-coloring in CFG and source code<a class="headerlink" href="#split-and-heuristic-difficulty-coloring-in-cfg-and-source-code" title="Link to this heading"></a></h4>
<p>The fill-colors of the graph nodes in the timeout TAC report summarize the
outcomes of the individual control flow splits for the current rule. See
<a class="reference internal" href="../techniques/index.html#control-flow-splitting"><span class="std std-ref">Control flow splitting</span></a> for background on the procedure.
An additional violet gradient is used to indicate nodes that are likely to
contain code that is difficult for the Prover to handle.</p>
<p>Nodes that have a green fill color are contained exclusively in splits that have
been successfully proven UNSAT by the current run of the Prover. This means
they are at least manageable for the Prover, although they still might have
taken significant time to prove.</p>
<p>Nodes that have a orange fill color lie on a split whose checking has timed
out under the timeout specified by <a class="reference internal" href="../cli/options.html#smt-timeout"><span class="std std-ref">smt_timeout</span></a>. This means that the
combination of the orange nodes was too difficulty to solve within that time.
Note that this does not say anything about the difficulty of any individual
orange node.</p>
<figure class="align-center" id="timeout-tac-report-orange-and-green-nodes">
<img alt="../../../_images/timeout-tac-report-green-nodes.png" src="../../../_images/timeout-tac-report-green-nodes.png">
<figcaption>
<p><span class="caption-text">CFG segment with orange and green nodes</span><a class="headerlink" href="#timeout-tac-report-orange-and-green-nodes" title="Link to this image"></a></p>
</figcaption>
</figure>
<p>Nodes that have a yellow fill color are on splits that were still queued for
solving when the timeout on the orange nodes happened. No strong statements can
be made about their difficulty at this point.</p>
<figure class="align-center" id="timeout-tac-report-yellow-nodes">
<img alt="../../../_images/timeout-tac-report-yellow-nodes.png" src="../../../_images/timeout-tac-report-yellow-nodes.png">
<figcaption>
<p><span class="caption-text">CFG segment with nodes that have not yet been queued during control flow splitting,
indicated by the yellow fill color</span><a class="headerlink" href="#timeout-tac-report-yellow-nodes" title="Link to this image"></a></p>
</figcaption>
</figure>
<p>When a call node has a violet gradient, this means its subgraph contains at
least one node with a violet gradient. When a regular node has a violet gradient
this means that our heuristic analysis of the node’s difficulty has marked it as
potentially difficult.</p>
<p>In practice, the violet highlighting typically means that there are at least two
nonlinear operations in the node, or a high number of case splits.
<a class="reference internal" href="../../user-guide/glossary.html#term-nonlinear-arithmetic"><span class="xref std std-term">Nonlinear operations</span></a> include multiplications of
two non-constant values, divisions by a non-constant value, and more. Case
splits can be induced by hashing unbounded arrays among other things.</p>
<p>When a regular node is marked violet, the source code in the source code box of
the report will contain highlights of the relevant lines, as well as a summary
of the difficult operations a the top of the block corresponding to the node.</p>
<figure class="align-center" id="timeout-tac-report-source-code-highlights">
<img alt="../../../_images/timeout-tac-report-source-code.png" src="../../../_images/timeout-tac-report-source-code.png">
<figcaption>
<p><span class="caption-text">Source code with highlighting and difficulty summary</span><a class="headerlink" href="#timeout-tac-report-source-code-highlights" title="Link to this image"></a></p>
</figcaption>
</figure>
<hr class="footnotes docutils">
<aside class="footnote-list brackets">
<aside class="footnote brackets" id="nested-cfg" role="doc-footnote">
<span class="label"><span class="fn-bracket">[</span><a role="doc-backlink" href="#id2">1</a><span class="fn-bracket">]</span></span>
<p>Strictly speaking, there is a set of CFGs available for each
verification condition. Every external call has its own CFG, and the CFGs
are related by call nodes which lead from a call site to the corresponding
callee’s CFG. Intuitively, this set can be viewed as one CFG with nested
sub-CFGs for the calls.</p>
</aside>
</aside>
</section>
</section>
</section>
</section>


           </div>
          </div>
          <footer><div class="rst-footer-buttons" role="navigation" aria-label="Footer">
        <a href="../techniques/index.html" class="btn btn-neutral float-left" title="Techniques Used by the Certora Prover" accesskey="p" rel="prev"><span class="fa fa-arrow-circle-left" aria-hidden="true"></span> Previous</a>
        <a href="../checking/index.html" class="btn btn-neutral float-right" title="Checking Specifications" accesskey="n" rel="next">Next <span class="fa fa-arrow-circle-right" aria-hidden="true"></span></a>
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