<!DOCTYPE html><html class="writer-html5" lang="en" data-content_root="../../../"><head>
  <meta charset="utf-8"><meta name="viewport" content="width=device-width, initial-scale=1">

  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Techniques Used by the Certora Prover — Certora Prover Documentation 0.0 documentation</title>
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
    <link rel="next" title="Diagnostic Tools" href="../diagnosis/index.html">
    <link rel="prev" title="Quantifier Grounding" href="../approx/grounding.html"> 
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
<li class="toctree-l2 current" aria-expanded="true"><a class="reference internal current" href="#" aria-expanded="true"><button class="toctree-expand" title="Open/close menu"></button>Techniques Used by the Certora Prover</a><ul>
<li class="toctree-l3"><a class="reference internal" href="#control-flow-splitting"><button class="toctree-expand" title="Open/close menu"></button>Control flow splitting</a><ul>
<li class="toctree-l4"><a class="reference internal" href="#idea">Idea</a></li>
<li class="toctree-l4"><a class="reference internal" href="#technical-description">Technical Description</a></li>
</ul>
</li>
<li class="toctree-l3"><a class="reference internal" href="#analysis-of-evm-storage-and-evm-memory">Analysis of EVM storage and EVM memory</a></li>
</ul>
</li>
<li class="toctree-l2"><a class="reference internal" href="../diagnosis/index.html">Diagnostic Tools</a></li>
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
      <li class="breadcrumb-item active">Techniques Used by the Certora Prover</li>
      <li class="wy-breadcrumbs-aside">
            <a href="../../../_sources/docs/prover/techniques/index.md.txt" rel="nofollow"> View page source</a>
      </li>
  </ul>
  <hr>
</div>
          <div role="main" class="document" itemscope="itemscope" itemtype="http://schema.org/Article">
           <div itemprop="articleBody">
             
  <section id="techniques-used-by-the-certora-prover">
<h1>Techniques Used by the Certora Prover<a class="headerlink" href="#techniques-used-by-the-certora-prover" title="Link to this heading"></a></h1>
<p>In this chapter, we describe some of the techniques used inside the Certora
Prover. While this knowledge is not essential for using the Prover, it can
sometimes be helpful when the Prover does not behave as expected, for instance
in case of a timeout.</p>
<section id="control-flow-splitting">
<span id="id1"></span><h2>Control flow splitting<a class="headerlink" href="#control-flow-splitting" title="Link to this heading"></a></h2>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>In addition to the text-form documentation below,  there is a brief explanation
of control flow splitting in the
<a class="reference external" href="https://www.youtube.com/watch?v=mntP0_EN-ZQ">webinar on timeouts</a>.</p>
</div>
<p>Control flow splitting (or “splitting” for short) is one of the techniques that
the Certora Prover employs to speed up solving. In the remainder of this
section, we will give an overview of how the technique works. This background
should be helpful when using the settings described
<a class="reference internal" href="../cli/options.html#control-flow-splitting-options"><span class="std std-ref">here</span></a> to prevent Prover timeouts.</p>
<section id="idea">
<h3>Idea<a class="headerlink" href="#idea" title="Link to this heading"></a></h3>
<p>We explain the core idea behind control flow splitting on a simple example.</p>
<p>Whenever there is branching in a program we want to verify, we can look for
counterexamples on each branch separately. Basically we split the question A:
“Is there a violating execution in the program?” into the two questions B: “Is
there a violating execution in the program that takes the first branch?”, and C:
“Is there a violating execution in the program that takes the second branch?”. If
the answer to either B or C is “yes”, then we can conclude that the answer to A
must be “yes”. If the answers to B and C are both “no”, then we can conclude
that the answer to A must be “no”.</p>
<p>For example, consider a rule with an <code class="docutils literal notranslate"><span class="pre">if</span></code> statement:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell0"><span></span><span class="k">rule</span><span class="w"> </span><span class="nc">example</span><span class="w"> </span><span class="p">{</span>
<span class="w">  </span><span class="p">...</span>
<span class="w">  </span><span class="kr">if</span><span class="w"> </span><span class="p">(</span>owner<span class="w"> </span><span class="o">==</span><span class="w"> </span>spender<span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kr">assert</span><span class="w"> </span>balance_after<span class="w"> </span><span class="o">==</span><span class="w"> </span>balance_before<span class="p">;</span>
<span class="w">  </span><span class="p">}</span><span class="w"> </span><span class="kr">else</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kr">assert</span><span class="w"> </span>balance_after<span class="w"> </span><span class="o">==</span><span class="w"> </span>balance_before<span class="w"> </span><span class="o">+</span><span class="w"> </span>amount<span class="p">;</span>
<span class="w">  </span><span class="p">}</span>
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
<p>To simplify the search for a counterexample, the Prover may internally split this single rule into two rules:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell1"><span></span><span class="k">rule</span><span class="w"> </span><span class="nc">example_split_1</span><span class="w"> </span><span class="p">{</span>
<span class="w">  </span><span class="p">...</span>
<span class="w">  </span><span class="kr">require</span><span class="w"> </span>owner<span class="w"> </span><span class="o">==</span><span class="w"> </span>spender<span class="p">;</span>
<span class="w">  </span><span class="kr">assert</span><span class="w"> </span>balance_after<span class="w"> </span><span class="o">==</span><span class="w"> </span>balance_before<span class="p">;</span>
<span class="p">}</span>

<span class="k">rule</span><span class="w"> </span><span class="nc">example_split_2</span><span class="w"> </span><span class="p">{</span>
<span class="w">  </span><span class="p">...</span>
<span class="w">  </span><span class="kr">require</span><span class="w"> </span>owner<span class="w"> </span><span class="o">!=</span><span class="w"> </span>spender<span class="p">;</span>
<span class="w">  </span><span class="kr">assert</span><span class="w"> </span>balance_after<span class="w"> </span><span class="o">==</span><span class="w"> </span>balance_before<span class="w"> </span><span class="o">+</span><span class="w"> </span>amount<span class="p">;</span>
<span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell1">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>A counterexample for either of the split rules will also be a counterexample for
the original rule, and any counterexample for the original rule must violate one
of the two split rules, so this splitting doesn’t change the meaning of the
rule.  However, in some cases the split rule is easier for the Prover to reason
about.</p>
</section>
<section id="technical-description">
<h3>Technical Description<a class="headerlink" href="#technical-description" title="Link to this heading"></a></h3>
<p>On a technical level, splitting is best illustrated using the <a class="reference internal" href="../../user-guide/glossary.html#term-control-flow-graph"><span class="xref std std-term">control flow graph</span></a> (CFG) of a given CVL rule.</p>
<p>A single splitting step proceeds as follows:</p>
<ul class="simple">
<li><p>Pick a node with two successors in the CFG, the <em>split point</em>.</p></li>
<li><p>Generate two new CFGs, we call them <em>splits</em>; both splits are copies of the
original CFG, except that in the first (second) split, the edge to the first
(second) successor has been removed. The algorithm also removes all nodes and
edges that become unreachable through the removal of the edge.</p></li>
</ul>
<figure class="align-center" id="single-split">
<a class="reference internal image-reference" href="../../../_images/split-step.png"><img alt="A single splitting step" src="../../../_images/split-step.png" style="height: 300px;" width="1038" height="702"></a>
<figcaption>
<p><span class="caption-text">Illustration of a single splitting step</span><a class="headerlink" href="#single-split" title="Link to this image"></a></p>
</figcaption>
</figure>
<p>There is an internal heuristic deciding which branching nodes to pick for each
single splitting step.</p>
<p>The following pseudo-code illustrates how Certora Prover applies the single splitting
in a recursive fashion.</p>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>In the remainder of this subsection, we’ll use the terms <a class="reference internal" href="../../user-guide/glossary.html#term-SAT"><span class="xref std std-term">SAT</span></a> and
<a class="reference internal" href="../../user-guide/glossary.html#term-UNSAT"><span class="xref std std-term">UNSAT</span></a>. SAT denotes the presence of a <a class="reference internal" href="../../user-guide/glossary.html#term-counterexample"><span class="xref std std-term">counterexample</span></a> (if the rule
has an <code class="docutils literal notranslate"><span class="pre">assert</span></code> statement) or a <a class="reference internal" href="../../user-guide/glossary.html#term-witness-example"><span class="xref std std-term">witness example</span></a> (if the rule has a
<code class="docutils literal notranslate"><span class="pre">satisify</span></code> statement). UNSAT denotes the absence of any counter- or witness
examples.</p>
</div>
<div class="literal-block-wrapper docutils container" id="recursive-splitting-algorithm">
<div class="code-block-caption"><span class="caption-text">Recursive splitting algorithm as pseudo code</span><a class="headerlink" href="#recursive-splitting-algorithm" title="Link to this code"></a></div>
<div class="highlight-default notranslate"><div class="highlight"><pre id="codecell2"><span></span><span class="n">Input</span><span class="p">:</span> <span class="n">input_program_cfg</span>

<span class="n">worklist</span> <span class="o">=</span> <span class="p">[]</span>
<span class="n">worklist</span><span class="o">.</span><span class="n">add</span><span class="p">([</span><span class="n">input_program_cfg</span><span class="p">,</span> <span class="mi">0</span><span class="p">])</span>

<span class="k">while</span> <span class="p">(</span><span class="n">worklist</span> <span class="o">!=</span> <span class="p">[])</span>
    <span class="p">[</span><span class="n">cfg</span><span class="p">,</span> <span class="n">current_depth</span><span class="p">]</span> <span class="o">=</span> <span class="n">worklist</span><span class="o">.</span><span class="n">pop</span><span class="p">()</span>

    <span class="n">res</span> <span class="o">=</span> <span class="n">smt_check</span><span class="p">(</span><span class="n">cfg</span><span class="p">,</span> <span class="n">get_timeout_for</span><span class="p">(</span><span class="n">current_depth</span><span class="p">))</span>
    <span class="n">when</span> <span class="p">(</span><span class="n">res</span><span class="p">)</span> 
        <span class="p">[</span><span class="n">SAT</span><span class="p">,</span> <span class="n">model</span><span class="p">]</span> <span class="o">-&gt;</span> <span class="k">return</span> <span class="p">[</span><span class="n">SAT</span><span class="p">,</span> <span class="n">model</span><span class="p">]</span>
        <span class="n">UNSAT</span> <span class="o">-&gt;</span> <span class="k">continue</span>
        <span class="n">TIMEOUT</span> <span class="o">-&gt;</span> 
            <span class="k">if</span> <span class="p">(</span><span class="n">current_depth</span> <span class="o">==</span> <span class="n">max_depth</span><span class="p">)</span>
                <span class="k">return</span> <span class="n">timeout</span>
            <span class="k">else</span>
                <span class="p">[</span><span class="n">split_1</span><span class="p">,</span> <span class="n">split_2</span><span class="p">]</span> <span class="o">=</span> <span class="n">split_single</span><span class="p">(</span><span class="n">cfg</span><span class="p">)</span>
                <span class="n">worklist</span><span class="o">.</span><span class="n">add</span><span class="p">([</span><span class="n">split_1</span><span class="p">,</span> <span class="n">current_depth</span> <span class="o">+</span> <span class="mi">1</span><span class="p">])</span>
                <span class="n">worklist</span><span class="o">.</span><span class="n">add</span><span class="p">([</span><span class="n">split_2</span><span class="p">,</span> <span class="n">current_depth</span> <span class="o">+</span> <span class="mi">1</span><span class="p">])</span>
<span class="k">return</span> <span class="n">UNSAT</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell2">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</div>
<p>Intuitively, the algorithm explores the tree of all possible recursive
splittings along a fixed sequence of split points up to the maximum splitting
depth. We call the splits at maximum splitting depth <em>split leaves</em>. The
exploration stops in any of the following three cases:</p>
<ul class="simple">
<li><p>if one split was found that is SAT (reasoning: if one split is SAT, then the
original program must be SAT, since the behavior of the split is replayable in
the original program)</p></li>
<li><p>if all splits have been shown to be UNSAT</p></li>
<li><p>if solving on a split leaf has timed out (except if
<a class="reference internal" href="../cli/options.html#dontstopatfirstsplittimeout"><span class="std std-ref">dontStopAtFirstSplitTimeout</span></a> has been set)</p></li>
</ul>
<p>The settings with which the user can influence this process are the
following (each links to a more detailed description of the option):</p>
<ul class="simple">
<li><p><a class="reference internal" href="../cli/options.html#depth"><span class="std std-ref">depth</span></a> controls the maximum splitting depth.</p></li>
<li><p><a class="reference internal" href="../cli/options.html#mediumtimeout"><span class="std std-ref">mediumTimeout</span></a> controls the timeout that is applied when
checking splits that are not split leafs, i.e., that are not at the maximum
depth.</p></li>
<li><p><a class="reference internal" href="../cli/options.html#smt-timeout"><span class="std std-ref">smt_timeout</span></a> controls the timeout that is used to solve split
leafs; if this is exceeded, the Prover will give up with a TIMEOUT
result, unless <a class="reference internal" href="../cli/options.html#dontstopatfirstsplittimeout"><span class="std std-ref">the corresponding setting</span></a> says
to go on.</p></li>
<li><p>Setting <a class="reference internal" href="../cli/options.html#smt-initialsplitdepth"><span class="std std-ref">smt_initialSplitDepth</span></a> to a value
above 0 will make the Prover skip the checking and immediately enumerate all
splits up to that depth.</p></li>
</ul>
</section>
</section>
<section id="analysis-of-evm-storage-and-evm-memory">
<span id="storage-and-memory-analysis"></span><h2>Analysis of EVM storage and EVM memory<a class="headerlink" href="#analysis-of-evm-storage-and-evm-memory" title="Link to this heading"></a></h2>
<p>The Certora Prover works on <a class="reference internal" href="../../user-guide/glossary.html#term-EVM"><span class="xref std std-term">EVM</span></a> bytecode as its input. To the bytecode,
the address space of both <a class="reference internal" href="../../user-guide/glossary.html#term-EVM-storage"><span class="xref std std-term">EVM storage</span></a> and <a class="reference internal" href="../../user-guide/glossary.html#term-EVM-memory"><span class="xref std std-term">EVM memory</span></a> are flat number
lines. That two contract fields <code class="docutils literal notranslate"><span class="pre">x</span></code> and <code class="docutils literal notranslate"><span class="pre">y</span></code> don’t share the same memory is an
arithmetic property. With more complex data structures like mappings, arrays,
and structs, this means that every
<a class="reference external" href="https://en.wikipedia.org/wiki/Aliasing_(computing)">“non-aliasing”</a> argument
requires reasoning about multiplications, additions, and hash functions.</p>
<p>The Certora Prover models this reasoning correctly, but this naive low-level
modeling can quickly overwhelm SMT solvers. In order to handle storage
efficiently, the Certora Prover analyzes Storage (Memory) accesses in EVM code
in order to understand the Storage (Memory) layout, thus making information like
“an update to mapping <code class="docutils literal notranslate"><span class="pre">x</span></code> will never overwrite the scalar variable <code class="docutils literal notranslate"><span class="pre">y</span></code>” much
more obvious to the SMT solvers. For scaling SMT solving to larger programs,
these simplifications are essential.</p>
</section>
</section>


           </div>
          </div>
          <footer><div class="rst-footer-buttons" role="navigation" aria-label="Footer">
        <a href="../approx/grounding.html" class="btn btn-neutral float-left" title="Quantifier Grounding" accesskey="p" rel="prev"><span class="fa fa-arrow-circle-left" aria-hidden="true"></span> Previous</a>
        <a href="../diagnosis/index.html" class="btn btn-neutral float-right" title="Diagnostic Tools" accesskey="n" rel="next">Next <span class="fa fa-arrow-circle-right" aria-hidden="true"></span></a>
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