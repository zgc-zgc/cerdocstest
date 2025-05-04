<!DOCTYPE html><html class="writer-html5" lang="en" data-content_root="../../../"><head>
  <meta charset="utf-8"><meta name="viewport" content="width=device-width, initial-scale=1">

  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Timeouts — Certora Prover Documentation 0.0 documentation</title>
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
    <link rel="next" title="Timeouts in Certora Prover - Theoretical Background" href="timeout-theory.html">
    <link rel="prev" title="Out of memory problems" href="memout.html"> 
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
<li class="toctree-l1 current" aria-expanded="true"><a class="reference internal" href="../index.html"><button class="toctree-expand" title="Open/close menu"></button>Certora User’s Guide</a><ul class="" aria-expanded="false">
<li class="toctree-l2"><a class="reference internal" href="../install.html">Installation</a></li>
<li class="toctree-l2"><a class="reference internal" href="../install_evm_compiler.html">Installing an EVM compiler and VS Code Extension</a></li>
<li class="toctree-l2"><a class="reference internal" href="../tutorials.html">Tutorial and Workshops</a></li>
<li class="toctree-l2"><a class="reference internal" href="../running.html">Running the Certora Prover</a></li>
<li class="toctree-l2"><a class="reference internal" href="../properties/index.html">Designing Good Specifications</a></li>
<li class="toctree-l2"><a class="reference internal" href="../satisfy.html">Producing Positive Examples</a></li>
<li class="toctree-l2"><a class="reference internal" href="../invariants.html">Invariants</a></li>
<li class="toctree-l2"><a class="reference internal" href="../parametric.html">Parametric rules</a></li>
<li class="toctree-l2"><a class="reference internal" href="../ghosts.html">Tracking changes with ghosts and hooks</a></li>
<li class="toctree-l2"><a class="reference internal" href="../patterns/index.html">Specification Design Patterns</a></li>
<li class="toctree-l2"><a class="reference internal" href="../opcodes.html">Using Opcode Hooks</a></li>
<li class="toctree-l2"><a class="reference internal" href="../multicontract/index.html">Working with Multiple Contracts</a></li>
<li class="toctree-l2 current" aria-expanded="true"><a class="reference internal" href="index.html"><button class="toctree-expand" title="Open/close menu"></button>Managing Timeouts and Out of Memory Problems</a><ul class="" aria-expanded="false">
<li class="toctree-l3"><a class="reference internal" href="memout.html">Out of memory problems</a></li>
<li class="toctree-l3 current" aria-expanded="true"><a class="reference internal current" href="#" aria-expanded="true"><button class="toctree-expand" title="Open/close menu"></button>Timeouts</a><ul>
<li class="toctree-l4"><a class="reference internal" href="#classification-of-timeouts">Classification of Timeouts</a></li>
<li class="toctree-l4"><a class="reference internal" href="#timeout-causes">Identifying timeout causes</a></li>
<li class="toctree-l4"><a class="reference internal" href="#timeout-prevention">Timeout prevention</a></li>
</ul>
</li>
<li class="toctree-l3"><a class="reference internal" href="timeout-theory.html">Timeouts in Certora Prover - Theoretical Background</a></li>
</ul>
</li>
<li class="toctree-l2"><a class="reference internal" href="../gaps.html">Understanding gaps between high and low level code</a></li>
<li class="toctree-l2"><a class="reference internal" href="../checking.html">Checking Specifications</a></li>
<li class="toctree-l2"><a class="reference internal" href="../ci.html">CI Configuration</a></li>
<li class="toctree-l2"><a class="reference internal" href="../github_highlighting.html">Syntax Highlighting on GitHub</a></li>
<li class="toctree-l2"><a class="reference internal" href="../glossary.html">Glossary</a></li>
</ul>
</li>
<li class="toctree-l1"><a class="reference internal" href="../../cvl/index.html">The Certora Verification Language</a></li>
<li class="toctree-l1"><a class="reference internal" href="../../prover/index.html">The Certora Prover</a></li>
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
          <li class="breadcrumb-item"><a href="../index.html">Certora User’s Guide</a></li>
          <li class="breadcrumb-item"><a href="index.html">Managing Timeouts and Out of Memory Problems</a></li>
      <li class="breadcrumb-item active">Timeouts</li>
      <li class="wy-breadcrumbs-aside">
            <a href="../../../_sources/docs/user-guide/out-of-resources/timeout.md.txt" rel="nofollow"> View page source</a>
      </li>
  </ul>
  <hr>
</div>
          <div role="main" class="document" itemscope="itemscope" itemtype="http://schema.org/Article">
           <div itemprop="articleBody">
             
  <section id="timeouts">
<span id="timeouts-introduction"></span><h1>Timeouts<a class="headerlink" href="#timeouts" title="Link to this heading"></a></h1>
<p>In the following, we will give a basic classification of timeouts, explain some
candidate causes for timeouts, and show ways to sometimes prevent them. See
<a class="reference internal" href="timeout-theory.html#timeouts-background"><span class="std std-ref">Timeouts in Certora Prover - Theoretical Background</span></a> for a glimpse into some of the theoretical background
on verification timeouts.</p>
<section id="classification-of-timeouts">
<span id="timeouts-classification"></span><h2>Classification of Timeouts<a class="headerlink" href="#classification-of-timeouts" title="Link to this heading"></a></h2>
<p>For a first classification of timeouts in Certora Prover, we consider where they occur
in the Prover’s pipeline. The pipeline starts by compiling the source
code into an intermediate language (called <a class="reference internal" href="../glossary.html#term-TAC"><span class="xref std std-term">TAC</span></a>).
Many static analyses and program transformations follow this.
Afterwards, the TAC program is iteratively split into parts and translated into
logical formulas. The logical formulas are then sent to an <a class="reference internal" href="../glossary.html#term-SMT"><span class="xref std std-term">SMT</span></a> solver.
For more details on how programs are split up, see <a class="reference internal" href="../../prover/techniques/index.html#control-flow-splitting"><span class="std std-ref">Control flow splitting</span></a>.
For a more comprehensive overview of the Certora Prover, see the
<a class="reference internal" href="../../whitepaper/index.html#white-paper"><span class="std std-ref">Certora Technology White Paper</span></a>.</p>
<p>We classify Certora Prover timeouts as follows:</p>
<ol class="arabic simple">
<li><p>timeouts that happen before SMT solvers are running</p></li>
<li><p>timeouts where the SMT queries in sum lead to a global timeout</p></li>
<li><p>timeouts where a single SMT query could not be solved</p></li>
</ol>
<p>Types 1. and 2. are signified by a hard stop of the Prover. That means the
Prover ran into the timeout of the cloud job, which is set at 2 hours, and was
forcefully shut down from everything it was doing (it is possible to lower that
timeout using the <a class="reference internal" href="../../prover/cli/options.html#global-timeout"><span class="std std-ref">global_timeout</span></a> flag). A message like “hard stop
reached” appears in the “Global problems” pane of the
<a class="reference internal" href="../../prover/portal/report.html#verification-report"><span class="std std-ref">report</span></a>, and error symbols next to one or many rules.</p>
<figure class="align-center" id="hard-stop-in-report">
<a class="reference internal image-reference" href="../../../_images/hard-stop-in-report.png"><img alt="../../../_images/hard-stop-in-report.png" src="../../../_images/hard-stop-in-report.png" style="height: 130px;" width="1194" height="330"></a>
<figcaption>
<p><span class="caption-text">A hard stop message appearing under Global Problems</span><a class="headerlink" href="#hard-stop-in-report" title="Link to this image"></a></p>
</figcaption>
</figure>
<p>Type 3. is signified by a soft stop. This means an SMT solver shut down due to
hitting the limit for a single SMT run (set via <a class="reference internal" href="../../prover/cli/options.html#smt-timeout"><span class="std std-ref">smt_timeout</span></a>).</p>
<figure class="align-center" id="rule-timeout-in-report">
<a class="reference internal image-reference" href="../../../_images/rule-timeout-in-report.png"><img alt="../../../_images/rule-timeout-in-report.png" src="../../../_images/rule-timeout-in-report.png" style="height: 200px;" width="722" height="532"></a>
<figcaption>
<p><span class="caption-text">A rule that timed out in the SMT solver</span><a class="headerlink" href="#rule-timeout-in-report" title="Link to this image"></a></p>
</figcaption>
</figure>
<p>In the remainder, we will focus on the mitigation of SMT timeouts, i.e., types
2. and 3. Non-SMT Timeouts (Type 1.) should be reported to Certora.</p>
</section>
<section id="timeout-causes">
<span id="identifying-timeout-causes"></span><h2>Identifying timeout causes<a class="headerlink" href="#timeout-causes" title="Link to this heading"></a></h2>
<p>As a first step towards resolving an SMT timeout, we need to diagnose its root
causes. In our experience, the following are some of the most common reasons for
SMT timeouts:</p>
<ul class="simple">
<li><p>non-trivial amount of nonlinear arithmetic</p></li>
<li><p>very high path count</p></li>
<li><p>high Storage/Memory complexity</p></li>
</ul>
<p>The term <a class="reference internal" href="../glossary.html#term-nonlinear-arithmetic"><span class="xref std std-term">nonlinear arithmetic</span></a> refers to computations involving
multiplications or divisions of variables. These are notoriously hard for
solvers. The path count is the number of paths from the initial location to the final
location in the  rule’s <a class="reference internal" href="../glossary.html#term-control-flow-graph"><span class="xref std std-term">control flow graph</span></a>. In the worst case, this
leads to a very high number of sub-cases that the solver needs to consider.
Furthermore, a high number of updates to Storage or Memory can be challenging
for the solver, because it needs to reason about
<a class="reference external" href="https://en.wikipedia.org/wiki/Aliasing_(computing)">aliasing</a> of Storage/Memory
locations.</p>
<p>This list is not exhaustive, but the majority of timeouts we have observed so
far can be traced back to one or more of these causes. While these are not the
only sources of complexity, they provide a good idea of the probable causes for
a given timeout.</p>
<section id="complexity-feedback-from-certora-prover">
<h3>Complexity feedback from Certora Prover<a class="headerlink" href="#complexity-feedback-from-certora-prover" title="Link to this heading"></a></h3>
<p>Certora Prover provides help with diagnosing timeouts. We present these features
in this section.</p>
<section id="difficulty-statistics">
<h4>Difficulty statistics<a class="headerlink" href="#difficulty-statistics" title="Link to this heading"></a></h4>
<p>Certora Prover provides statistics on the problem sizes it encounters. These
statistics are available in the <a class="reference internal" href="../../prover/diagnosis/index.html#tac-reports"><span class="std std-ref">TAC Reports</span></a> that are generated in case of
an SMT timeout. The statistics are structured according to the timeout reasons
given above.</p>
<p>Currently, the Prover tracks the following statistics:</p>
<ul class="simple">
<li><p>nonlinear operations count</p></li>
<li><p>path count</p></li>
<li><p>memory/storage complexity measures</p></li>
</ul>
<p>For a very short summary we give one summarizing number for each of the
statistics, along with a LOW/MEDIUM/HIGH statement.</p>
<p>The meanings of the LOW/MEDIUM/HIGH classifications are as follows:</p>
<ul class="simple">
<li><p><strong>LOW:</strong> unlikely to be a reason for a timeout</p></li>
<li><p><strong>MEDIUM:</strong> might be a reason for a timeout; the timeout might also be a result
of the combined complexity with other measures</p></li>
<li><p><strong>HIGH:</strong> likely to be a reason for a timeout, even if it is the only aspect of
the verification problem that shows high complexity</p></li>
</ul>
<p>For more details on the individual statistics and how to make use of them, also
see the section on <a class="reference internal" href="#dealing-with-complexity"><span class="std std-ref">Dealing with different kinds of complexity</span></a> below.</p>
</section>
<section id="timeout-tac-reports">
<span id="id1"></span><h4>Timeout TAC reports<a class="headerlink" href="#timeout-tac-reports" title="Link to this heading"></a></h4>
<p>A TAC graph for each verification item is linked in the verification report. In case of a timeout, this graph contains information on which parts of the program were part of the actual timeout and which were already solved successfully. It also contains statistics on the timeout causes mentioned above.</p>
<p>In the timeout case, the TAC reports contain additional information that should help diagnose the timeout.</p>
</section>
<section id="finding-timeout-causes-through-modularization">
<h4>Finding timeout causes through modularization<a class="headerlink" href="#finding-timeout-causes-through-modularization" title="Link to this heading"></a></h4>
<p>In addition to the other techniques described here, it can be insightful to
remove parts of the code in order to isolate the timeout reason. If timeouts are
eliminated through this, modular verification techniques can be employed in
order to prove correctness of the parts separately.
These techniques are a relatively blunt instrument, but can be necessary in
particular with large or complex code bases.</p>
<section id="sanity-rules">
<h5>Sanity rules<a class="headerlink" href="#sanity-rules" title="Link to this heading"></a></h5>
<p>One way of isolating the timeout cause is by running with a trivial
specification.  This way, the specification is ruled out as the source of
complexity. Thus, a timeout on such a rule hints towards some parts of the
program code being challenging for the solver, rather than the program code in
combination with another, less trivial, spec.</p>
<p>Sanity rules are such trivial specifications. For documentation on them, see
<a class="reference internal" href="../../cvl/builtin.html#built-in-sanity"><span class="std std-ref">sanity</span></a> and <a class="reference internal" href="../../cvl/builtin.html#built-in-deep-sanity"><span class="std std-ref">deep sanity</span></a>.</p>
</section>
<section id="library-contracts">
<span id="timeout-causes-library-contracts"></span><h5>Library contracts<a class="headerlink" href="#library-contracts" title="Link to this heading"></a></h5>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>This section is EVM-specific and does not apply to Solana or Soroban.</p>
</div>
<p>Some systems are based on multiple library contracts that implement
business logic. They also forward storage updates to a single external contract
holding the storage.</p>
<p>In these systems, it can be appropriate to verify each library independently.</p>
<p>If you encounter timeouts when trying to verify the main entry point contract to
the system, check the impact of the libraries on the verification by summarizing
all external library (delegate) calls as <code class="docutils literal notranslate"><span class="pre">NONDET</span></code>, using the option
<code class="docutils literal notranslate"><span class="pre">-summarizeExtLibraryCallsAsNonDetPreLinking</span></code> as follows:</p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell0"><span></span>certoraRun<span class="w"> </span>...<span class="w"> </span>--prover_args<span class="w"> </span><span class="s1">'-summarizeExtLibraryCallsAsNonDetPreLinking true'</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell0">
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
<p>This option is only applied to <code class="docutils literal notranslate"><span class="pre">delegatecall</span></code>s and <em>external</em> library calls.
The Solidity compiler automatically inlines internal calls, and they are subject to summarizations specified in the spec file’s&nbsp;methods&nbsp;block.</p>
</div>
</section>
</section>
</section>
</section>
<section id="timeout-prevention">
<span id="id2"></span><h2>Timeout prevention<a class="headerlink" href="#timeout-prevention" title="Link to this heading"></a></h2>
<p>Timeout prevention approaches fall into these categories:</p>
<ol class="arabic simple">
<li><p>Changing prover settings</p></li>
<li><p>Changing specs</p></li>
<li><p>Changing source code</p></li>
</ol>
<p>Changing Prover settings is the least invasive and easiest to do, so it is usually preferable to the other options. However, there are cases when parts of the input code that are very hard to reason about need to be worked around. Sometimes, a combination of approaches is needed to resolve a timeout.</p>
<p>The following will discuss some concrete approaches to timeout prevention. This collection will be extended over time based on user experiences and tool improvements.</p>
<section id="running-rules-individually">
<span id="timeout-single-rule"></span><h3>Running rules individually<a class="headerlink" href="#running-rules-individually" title="Link to this heading"></a></h3>
<p>The Certora Prover works on the rules of the specification in parallel.
Even if no rule is very expensive on its own, working on all of them in parallel
can add up quickly and thereby exceed the timeout.
Try running individual rules only via the <a class="reference internal" href="../../prover/cli/options.html#rule"><span class="std std-ref">rule</span></a> option or split the
specification into separate files.
For EVM, keep in mind that a <a class="reference internal" href="../glossary.html#term-parametric-rule"><span class="xref std std-term">parametric rule</span></a>, as well as an
<a class="reference internal" href="../glossary.html#term-invariant"><span class="xref std std-term">invariant</span></a>, spawns a sub-rule for every contract method.  This can
further be reduced via the <a class="reference internal" href="../../prover/cli/options.html#method"><span class="std std-ref">method</span></a> option.</p>
</section>
<section id="detect-candidates-for-summarization">
<span id="id4"></span><h3>Detect candidates for summarization<a class="headerlink" href="#detect-candidates-for-summarization" title="Link to this heading"></a></h3>
<p>It can be difficult to find all the functions that may be difficult for the Prover in a large codebase.
A traditional approach would be to run a simple parametric rule to explore all functions in the relevant contracts and study the resulting potential timeouts.
However, such an approach prolongs the feedback loop of working with the Prover.</p>
<p>As an alternative approach, the Prover supports an <a class="reference internal" href="../glossary.html#term-overapproximation"><span class="xref std std-term">overapproximating</span></a> <em>auto-summarization</em> mode.
It is based on the idea that internal <code class="docutils literal notranslate"><span class="pre">view</span></code> or <code class="docutils literal notranslate"><span class="pre">pure</span></code> functions (in Solidity) that are analyzed
and found to be heuristically difficult for the Prover can be automatically summarized as <code class="docutils literal notranslate"><span class="pre">NONDET</span></code>,
resulting in two positive outcomes:</p>
<ol class="arabic simple">
<li><p>The run is faster since complex code is summarized early in the Prover’s pipeline.</p></li>
<li><p>The Prover emits the list of <em>new</em> summaries (i.e., for functions that were not summarized already in the given specification)
it auto-generated, so that the user can then adapt the list
and make the user-specified summaries more precise, or remove them altogether if the user wishes.</p></li>
</ol>
<p>The Prover will not auto-summarize methods that were already summarized by the user.</p>
<p>To enable this mode, add <a class="reference internal" href="../../prover/cli/options.html#nondet-difficult-funcs"><span class="std std-ref">nondet_difficult_funcs</span></a> to the <code class="docutils literal notranslate"><span class="pre">certoraRun</span></code> command.
The minimal difficulty threshold used for the auto-summarization
can be adjusted using <a class="reference internal" href="../../prover/cli/options.html#nondet-minimal-difficulty"><span class="std std-ref">nondet_minimal_difficulty</span></a>.</p>
<p>For Solana and Soroban, we recommend summarizing hotspots by enabling munging
with <a class="reference external" href="https://doc.rust-lang.org/reference/conditional-compilation.html">conditional compilation</a>.</p>
<section id="example-usage">
<h4>Example usage<a class="headerlink" href="#example-usage" title="Link to this heading"></a></h4>
<p>Many DeFi protocols use the <code class="docutils literal notranslate"><span class="pre">OpenZeppelin</span></code> math libraries.
One such library is <a class="reference external" href="https://github.com/OpenZeppelin/openzeppelin-contracts/blob/21c8312b022f495ebe3621d5daeed20552b43ff9/contracts/utils/math/Math.sol#L197">Math</a>, which provides a <code class="docutils literal notranslate"><span class="pre">mulDiv</span></code> functionality:
<code class="docutils literal notranslate"><span class="pre">function</span> <span class="pre">mulDiv(uint256</span> <span class="pre">x,</span> <span class="pre">uint256</span> <span class="pre">y,</span> <span class="pre">uint256</span> <span class="pre">denominator)</span> <span class="pre">internal</span> <span class="pre">pure</span> <span class="pre">returns</span> <span class="pre">(uint256</span> <span class="pre">result)</span></code>.
The implementation is known to be difficult for the Prover due to
applying numerous multiplication, division and <code class="docutils literal notranslate"><span class="pre">mulmod</span></code> operations,
and thus is often summarized.</p>
<p>However, it is sometimes easy to miss the library also contains a more generalized version
of <code class="docutils literal notranslate"><span class="pre">mulDiv</span></code> that supports either rounding-up or rounding down:
<code class="docutils literal notranslate"><span class="pre">function</span> <span class="pre">mulDiv(uint256</span> <span class="pre">x,</span> <span class="pre">uint256</span> <span class="pre">y,</span> <span class="pre">uint256</span> <span class="pre">denominator,</span> <span class="pre">Rounding</span> <span class="pre">rounding)</span> <span class="pre">internal</span> <span class="pre">pure</span> <span class="pre">returns</span> <span class="pre">(uint256)</span></code>.
Sometimes, it can be beneficial to summarize the generalized function as well.
The auto-summarization will highlight the generalized function in its output:
<img alt="auto-summarizer-output-example" src="../../../_images/auto-summarizer-output-example.png" width="836" height="58">
The contents can be copy-pasted into the <code class="docutils literal notranslate"><span class="pre">methods</span></code> block directly for future runs.</p>
<p>The “Contracts Call Resolutions” tab and the “Rule Call Resolution” bar also show
the instrumented auto-summaries and distinguish between them and user-defined summaries.</p>
</section>
</section>
<section id="dealing-with-different-kinds-of-complexity">
<span id="dealing-with-complexity"></span><h3>Dealing with different kinds of complexity<a class="headerlink" href="#dealing-with-different-kinds-of-complexity" title="Link to this heading"></a></h3>
<p>In this section we list some hints for timeout prevention based on which
statistic (path count, number of nonlinear operations, memory/storage
complexity) shows high severity on a given rule.</p>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>The techniques described further down under <a class="reference internal" href="#modular-verification"><span class="std std-ref">modular verification</span></a>
are worth considering no matter which statistic is showing high severity.</p>
</div>
<section id="dealing-with-a-high-path-count">
<span id="high-path-count"></span><h4>Dealing with a high path count<a class="headerlink" href="#dealing-with-a-high-path-count" title="Link to this heading"></a></h4>
<p>The number of control flow paths is a major indication of how difficult a rule
is to solve. Intuitively, an argument for the correctness of each of its paths has to be found to obtain a correctness proof for the rule.</p>
<p>The Certora Prover indicates the path count in the Live Statistics panel.
The path count is given once for the whole rule and separately on a per-call
basis.
The per-call path count always includes the paths of all deeper calls (the
same holds for the count of nonlinear operations of the call).</p>
<figure class="align-default" id="path-count-stats">
<img alt="../../../_images/path-count-stats.png" src="../../../_images/path-count-stats.png" width="541" height="665">
<figcaption>
<p><span class="caption-text">Global and per-call path counts are displayed in the Live Statistics panel for
each rule.</span><a class="headerlink" href="#path-count-stats" title="Link to this image"></a></p>
</figcaption>
</figure>
<section id="path-explosion">
<h5>Path explosion<a class="headerlink" href="#path-explosion" title="Link to this heading"></a></h5>
<p>The number of paths given in the path count statistic might seem very high
to users. The essential reason for these high numbers is known as the
<a class="reference external" href="https://en.wikipedia.org/wiki/Path_explosion">path explosion problem</a>: The path count
is usually exponential in the number of nodes and edges in the control flow graph.</p>
<p>For some intuition on how this happens, see the following illustration. Whenever there
is a sequence of subgraphs that branch and then join again, the simplest variant of this
being the diamond shapes in the picture, the path count of the whole graph is the product
of these subgraph’s path counts. Thus, it is typical for the path count of a control flow
graph to grow exponentially in its number of nodes (or edges).</p>
<figure class="align-default" id="path-diamonds">
<a class="reference internal image-reference" href="../../../_images/path-diamonds.png"><img alt="../../../_images/path-diamonds.png" src="../../../_images/path-diamonds.png" style="height: 400px;"></a>
<figcaption>
<p><span class="caption-text">Illustration of path explosion through a sequence of <em>n</em> “diamond” shapes in the control
flow graph. The shown control flow graph has 2<sup>n</sup> paths.</span><a class="headerlink" href="#path-diamonds" title="Link to this image"></a></p>
</figcaption>
</figure>
<p>The path count statistic for a given rule is based on the control flow graph of
the rule with all calls (and their calls and so forth) inlined. For example, if
some method with 5 paths is called 10 times within the rule, its control flow
graph will appear 10 times as a subgraph of the rule’s control flow graph. If,
for instance, all these calls were made in sequence, and there was no further
branching in the rule, the path count would be 5<sup>10</sup>.</p>
<p>For EVM, a particular potential cause for path explosion are <a class="reference internal" href="../../cvl/methods.html#dispatcher"><span class="std std-ref">DISPATCHER summaries</span></a>. How much a
<code class="docutils literal notranslate"><span class="pre">DISPATCHER</span></code> summary contributes to the path count depends on three factors:</p>
<ul class="simple">
<li><p>How many potential call targets are there (how many known implementations)</p></li>
<li><p>How often the summarized function is called</p></li>
<li><p>Whether the function is called in sequence or in parallel in the control flow
(generally, control flow branchings in sequence lead to an exponential path explosion)</p></li>
</ul>
</section>
<section id="mitigation-approaches">
<h5>Mitigation approaches<a class="headerlink" href="#mitigation-approaches" title="Link to this heading"></a></h5>
<p>To reduce the path count of a rule, the usual modularization techniques,
like method summarization, can be applied. (See also the section
<a class="reference internal" href="#modular-verification"><span class="std std-ref">Modular verification</span></a> below.)</p>
<p>As pointed out in the previous sub-section, <code class="docutils literal notranslate"><span class="pre">DISPATCHER</span></code> summaries can lead to a path
explosion, so replacing them, for instance, with <code class="docutils literal notranslate"><span class="pre">AUTO</span></code> summaries can have a significant
impact. (See also <a class="reference internal" href="../../cvl/methods.html#auto-summary"><span class="std std-ref">AUTO summaries</span></a>.)</p>
<p>Furthermore, it can help to change the parameters of the <em>control flow
splitting</em> feature of the Certora Prover. Control flow splitting is a natural
area to consider when the path count of a rule is high. When applying this
technique, the Certora Prover internally divides each verification condition
into smaller subproblems and attempts to solve them separately. For a more
detailed explanation, see <a class="reference internal" href="../../prover/techniques/index.html#control-flow-splitting"><span class="std std-ref">Control flow splitting</span></a>.</p>
<p>We list a few option combinations that can help in various settings. There is a
tradeoff between spending time in different places: The Prover can either try to
spend much time at a low splitting level in the hope that no further splitting
will be needed, or it can split quickly in the hope that the subproblems will be
much easier to solve.</p>
<p>The options for control flow splitting are described in more detail in the
<a class="reference internal" href="../../prover/cli/options.html#control-flow-splitting-options"><span class="std std-ref">corresponding section of the CLI
documentation</span></a>. In the following, we list some
brief examples of how they can be used to avoid timeouts in certain scenarios.</p>
<p>When the relevant source code is very large, the shallow splits have a chance of
being too large for the solvers, thus eager splitting might help:</p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell1"><span></span>certoraRun<span class="w"> </span>...<span class="w"> </span>--prover_args<span class="w"> </span><span class="s1">'-smt_initialSplitDepth 5 -depth 15'</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell1">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>When there are very many subproblems medium difficulty, there is a
chance that the Prover has to split too often (not being able to “close” any
sub-splits). In that case, a lazier splitting strategy could help. We achieve lazier
splitting by giving the solver more time to find a solution before we split a
problem.</p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell2"><span></span>certoraRun<span class="w"> </span>...<span class="w"> </span>--prover_args<span class="w"> </span><span class="s1">'-mediumTimeout 30 -depth 5'</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell2">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>It can also help to have splitting run in parallel (the splits are solved
sequentially by default).</p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell3"><span></span>certoraRun<span class="w"> </span>...<span class="w"> </span>--prover_args<span class="w"> </span><span class="s1">'-splitParallel true'</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell3">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>If the expectation is that the rule is violated (or not violated in case of a
<code class="docutils literal notranslate"><span class="pre">satisfy</span></code>-style rule), the <a class="reference internal" href="../../prover/cli/options.html#dontstopatfirstsplittimeout"><span class="std std-ref">dontStopAtFirstSplitTimeout</span></a> option can prove
useful.</p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell4"><span></span>certoraRun<span class="w"> </span>...<span class="w"> </span>--prover_args<span class="w"> </span><span class="s1">'-dontStopAtFirstSplitTimeout true -depth 15 -mediumTimeout 5'</span><span class="w"> </span>--smt_timeout<span class="w"> </span><span class="m">10</span>
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
<section id="dealing-with-nonlinear-arithmetic">
<span id="high-nonlinear-op-count"></span><h4>Dealing with nonlinear arithmetic<a class="headerlink" href="#dealing-with-nonlinear-arithmetic" title="Link to this heading"></a></h4>
<p>Nonlinear integer arithmetic is often the hardest part of the formulas that the Certora Prover is solving.</p>
<p>The Certora Prover displays the absolute number of nonlinear operations and their number per call in the Live Statistics panel. The per-call display has a warning sign next to the call when there is a non-trivial number of nonlinear operations in the call or its sub-call. Rules with two or more nonlinear operations are marked in this way.</p>
<p>For EVM, unless the detection of internal functions fails, both internal and external calls are considered in the statistics. If the detection fails (which should be rare), internal calls are treated as inlined into the external calls. In that case, each inlined internal call’s statistics contribute to the statistics of the enclosing external call.</p>
<figure class="align-default" id="nonlinear-ops-field">
<img alt="../../../_images/nonlinear-ops-field.png" src="../../../_images/nonlinear-ops-field.png">
<figcaption>
<p><span class="caption-text">Field in the Live Statistics panel indicating the number of nonlinear operations
in the selected rule</span><a class="headerlink" href="#nonlinear-ops-field" title="Link to this image"></a></p>
</figcaption>
</figure>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>Counting the number of nonlinear operations is a rather coarse
statistic. There are formulas with 10 nonlinear operations that are out of reach
of current SMT solvers, while in other cases formulas with 120 operations are
solved. Nevertheless, reducing the number of nonlinear operations has often
proven a successful measure in timeout prevention, even if some remained.</p>
</div>
<p>The main techniques for reducing these numbers are modularization and
underapproximation.</p>
<p>Modularization, typically by introducing method summaries, can help reduce the
size of the rule, thus reducing the nonlinear operations. The per-call statistics in the Live Statistics panel (picture below) can help identify nonlinearity hot spots. Summarizing these hot spots, in particular, can help reduce the number of nonlinear operations, especially when a method is called multiple times.</p>
<figure class="align-default" id="nonlinear-ops-call">
<img alt="../../../_images/nonlinear-ops-call.png" src="../../../_images/nonlinear-ops-call.png">
<figcaption>
<p><span class="caption-text">Entry in Live Statistics indicating the number of operations are made in a given
call, including its sub-calls</span><a class="headerlink" href="#nonlinear-ops-call" title="Link to this image"></a></p>
</figcaption>
</figure>
<p>In some rules it is feasible to only consider an underapproximation of the
actual behavior by fixing some value that is used very often in nonlinear
computations to a concrete value. A typical example would be the decimal digits
in fixed decimal arithmetic – having this unconstrained can increase
nonlinearity in the rule massively, although only a small range of values is
actually feasible. Of course, great care must be taken when choosing these
underapproximations since they may lead to missed bugs.</p>
<p>A weaker form of underapproximation would be to introduce an extra requirement
on the range of some variable that contributes to nonlinearity. For example, for the number of decimals in a fixed decimal computation, only values between 0 and 256 make sense, and in practice, values from an even smaller range are likely to be used. This measure will not change the values in the Live Statistics panel, but it has prevented timeouts in some cases nonetheless.</p>
</section>
<section id="dealing-with-high-memory-or-storage-complexity">
<span id="high-memory-complexity"></span><h4>Dealing with high memory (or storage) complexity<a class="headerlink" href="#dealing-with-high-memory-or-storage-complexity" title="Link to this heading"></a></h4>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>This section is EVM-specific and does not apply to Solana or Soroban.</p>
</div>
<p>The memory complexity of each rule or parametric rule is displayed in the Live
Statistics panel in the Certora Prover reports.</p>
<p>The Certora Prover decompiles bytecode so that all EVM
primitives can ultimately be modeled as SMT constructs. This process introduces
key-to-value mappings for EVM memory and EVM storage. Additionally, the CVL
specification may introduce ghost mappings. The Prover runs static analyses to
reduce the load on these mappings by splitting them into smaller pieces
(smaller mappings or scalar variables).
However, this is not always possible, and some mappings usually remain in the final SMT formula.</p>
<p>Under this model, “memory updates” is a measure of how many times we store
into a key-value mapping such as memory, storage, or a ghost function. The
“longest update sequence” statistic represents the length the longest sequence
of updates (i.e. store operations) performed on one of the mappings. In both
cases, a smaller number indicates a less difficult problem for the Prover to
solve.</p>
<figure class="align-default" id="memory-complexity-field">
<a class="reference internal image-reference" href="../../../_images/memory-complexity-field.png"><img alt="../../../_images/memory-complexity-field.png" src="../../../_images/memory-complexity-field.png" style="height: 90px;"></a>
<figcaption>
<p><span class="caption-text">Entry in the Live Statistics panel indicating memory complexity</span><a class="headerlink" href="#memory-complexity-field" title="Link to this image"></a></p>
</figcaption>
</figure>
<p>In the following we consider common culprits for high memory complexity.</p>
<section id="passing-complex-structs">
<h5>Passing complex structs<a class="headerlink" href="#passing-complex-structs" title="Link to this heading"></a></h5>
<p>One common reason for high memory complexity is complex data structures in the program or specification.
<code class="docutils literal notranslate"><span class="pre">struct</span></code> types that contain many dynamically-sized arrays are especially
problematic.</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell5"><span></span><span class="k">rule</span><span class="w"> </span><span class="nc">myRule</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span>MyStruct<span class="w"> </span>x<span class="p">;</span>
<span class="w">    </span>foo<span class="p">(</span>x<span class="p">);</span>

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
<div class="highlight-solidity notranslate"><div class="highlight"><pre id="codecell6"><span></span><span class="kt">struct</span><span class="w"> </span><span class="nv">MyStruct</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="c1">// several dynamically-sized arrays</span>
<span class="w">    </span><span class="kt">bytes</span><span class="w"> </span><span class="nv">b</span><span class="p">;</span>
<span class="w">    </span><span class="kt">string</span><span class="w"> </span><span class="nv">s</span><span class="p">;</span>
<span class="w">    </span><span class="kt">uint</span><span class="p">[]</span><span class="w"> </span>u1<span class="p">;</span>
<span class="w">    </span><span class="kt">uint8</span><span class="p">[]</span><span class="w"> </span>u2<span class="p">;</span>
<span class="p">}</span>

<span class="kt">function</span><span class="w"> </span><span class="nv">foo</span><span class="p">(</span>MyStruct<span class="w"> </span>x<span class="p">)</span><span class="w"> </span><span class="kt">public</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="p">...</span>
<span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell6">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>In this case, it can help to identify fields of the struct that are not relevant to the property of the program that is currently being reasoned about and comment out those fields. In our experience, these fields exist relatively often, especially in large structs. Naturally, the removal might be complicated because all usages of these fields also need some munging steps applied to them.</p>
</section>
<section id="memory-and-storage-in-inline-assembly">
<h5>Memory and storage in inline assembly<a class="headerlink" href="#memory-and-storage-in-inline-assembly" title="Link to this heading"></a></h5>
<p>The Certora Prover employs <a class="reference internal" href="../../prover/techniques/index.html#storage-and-memory-analysis"><span class="std std-ref">static analyses and
simplifications</span></a> to make reasoning about Storage and Memory easier for SMT solvers.
However, unusual code patterns (most often produced when using inline assembly) can sometimes throw off these static analyses, making the SMT formulas too hard to solve.</p>
<p>CVT reports of Storage or Memory analysis failures in the Global Problems
pane of the reports, along with pointers to the offending source code positions
(typically inline assembly containing <code class="docutils literal notranslate"><span class="pre">sstore</span></code>/<code class="docutils literal notranslate"><span class="pre">sload</span></code>/<code class="docutils literal notranslate"><span class="pre">mstore</span></code>/<code class="docutils literal notranslate"><span class="pre">mload</span></code>
operations). To resolve such failures, the relevant code parts need to be
summarized or munged. (Naturally, the Certora developers are working to make such
failures less frequent as well.)</p>
</section>
</section>
</section>
<section id="modular-verification">
<span id="id5"></span><h3>Modular verification<a class="headerlink" href="#modular-verification" title="Link to this heading"></a></h3>
<p>Often, it is useful to break a complex problem into simpler subproblems; this process is called modularization. You can modularize a verification problem by first proving a property about a complex piece of code (such as a library or a method) and then using that property to summarize the complex code. In the following, we elaborate on modularization techniques that can help prevent timeouts.</p>
<section id="library-based-systems">
<span id="library-timeouts"></span><h4>Library-based systems<a class="headerlink" href="#library-based-systems" title="Link to this heading"></a></h4>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>This section is EVM-specific and does not apply to Solana or Soroban.</p>
</div>
<p>As mentioned here <a class="reference internal" href="#timeout-causes-library-contracts"><span class="std std-ref">before</span></a>, systems with
libraries are a natural candidate for modularization.</p>
<p>As an alternative to using the <code class="docutils literal notranslate"><span class="pre">-summarizeExtLibraryCallsAsNonDetPreLinking</span> <span class="pre">true</span></code>
option mentioned before, one can summarize all the methods of a single library
using a <a class="reference internal" href="../../cvl/methods.html#catch-all-entries"><span class="std std-ref">catch-all summary</span></a>.
For example, to use a
<code class="docutils literal notranslate"><span class="pre">NONDET</span></code> summary for all functions of <code class="docutils literal notranslate"><span class="pre">MyBigLibrary</span></code>, one could add the
following:</p>
<div class="highlight-default notranslate"><div class="highlight"><pre id="codecell7"><span></span><span class="n">methods</span> <span class="p">{</span>
    <span class="n">function</span> <span class="n">MyBigLibrary</span><span class="o">.</span><span class="n">_</span> <span class="n">external</span> <span class="o">=&gt;</span> <span class="n">NONDET</span><span class="p">;</span>
    <span class="n">function</span> <span class="n">MyBigLibrary</span><span class="o">.</span><span class="n">_</span> <span class="n">internal</span> <span class="o">=&gt;</span> <span class="n">NONDET</span><span class="p">;</span>
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
<p>The above snippet has the effect of summarizing as <code class="docutils literal notranslate"><span class="pre">NONDET</span></code> all external calls
to the library and <em>internal</em> ones as well. Only <code class="docutils literal notranslate"><span class="pre">NONDET</span></code> and <code class="docutils literal notranslate"><span class="pre">HAVOC</span></code> summaries
can be applied.
For more information on method summaries, see <a class="reference internal" href="../../cvl/methods.html#summaries"><span class="std std-ref">Summaries</span></a>.</p>
</section>
</section>
<section id="command-line-options">
<span id="timeout-cli-options"></span><h3>Command line options<a class="headerlink" href="#command-line-options" title="Link to this heading"></a></h3>
<p>There are several command line options that influence specific parts of the
Prover’s pipeline. While their default values generally yield the best results,
changing them can improve running time in certain cases.</p>
<section id="prover-args-destructiveoptimizations-enable">
<h4><code class="docutils literal notranslate"><span class="pre">--prover_args</span> <span class="pre">'-destructiveOptimizations</span> <span class="pre">enable'</span></code><a class="headerlink" href="#prover-args-destructiveoptimizations-enable" title="Link to this heading"></a></h4>
<p>This option enables some aggressive simplifications that speed up the Prover in many cases,
but breaks call trace generation in case a rule is violated.</p>
</section>
</section>
</section>
</section>


           </div>
          </div>
          <footer><div class="rst-footer-buttons" role="navigation" aria-label="Footer">
        <a href="memout.html" class="btn btn-neutral float-left" title="Out of memory problems" accesskey="p" rel="prev"><span class="fa fa-arrow-circle-left" aria-hidden="true"></span> Previous</a>
        <a href="timeout-theory.html" class="btn btn-neutral float-right" title="Timeouts in Certora Prover - Theoretical Background" accesskey="n" rel="next">Next <span class="fa fa-arrow-circle-right" aria-hidden="true"></span></a>
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