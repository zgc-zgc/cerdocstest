<!DOCTYPE html><html class="writer-html5" lang="en" data-content_root="../../"><head>
  <meta charset="utf-8"><meta name="viewport" content="width=device-width, initial-scale=1">

  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Understanding gaps between high and low level code — Certora Prover Documentation 0.0 documentation</title>
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
    <link rel="next" title="Checking Specifications" href="checking.html">
    <link rel="prev" title="Timeouts in Certora Prover - Theoretical Background" href="out-of-resources/timeout-theory.html"> 
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
<li class="toctree-l2 current" aria-expanded="true"><a class="reference internal current" href="#" aria-expanded="true"><button class="toctree-expand" title="Open/close menu"></button>Understanding gaps between high and low level code</a><ul>
<li class="toctree-l3"><a class="reference internal" href="#loops"><button class="toctree-expand" title="Open/close menu"></button>Loops</a><ul>
<li class="toctree-l4"><a class="reference internal" href="#determining-the-number-of-needed-iterations">Determining the number of needed iterations</a></li>
</ul>
</li>
</ul>
</li>
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
      <li class="breadcrumb-item active">Understanding gaps between high and low level code</li>
      <li class="wy-breadcrumbs-aside">
            <a href="../../_sources/docs/user-guide/gaps.md.txt" rel="nofollow"> View page source</a>
      </li>
  </ul>
  <hr>
</div>
          <div role="main" class="document" itemscope="itemscope" itemtype="http://schema.org/Article">
           <div itemprop="articleBody">
             
  <section id="understanding-gaps-between-high-and-low-level-code">
<h1>Understanding gaps between high and low level code<a class="headerlink" href="#understanding-gaps-between-high-and-low-level-code" title="Link to this heading"></a></h1>
<p>The Certora Prover analyzes low-level code, such as the EVM bytecode. However, the CVL specification, Rule Report, and Call Trace usually present information in terms of a high-level language (e.g., Solidity).</p>
<p>In this document, we describe how some of the gaps between the high-level source and the low-level bytecode can affect our understanding of the Prover’s outputs and recommended solutions.</p>
<section id="loops">
<h2>Loops<a class="headerlink" href="#loops" title="Link to this heading"></a></h2>
<section id="determining-the-number-of-needed-iterations">
<h3>Determining the number of needed iterations<a class="headerlink" href="#determining-the-number-of-needed-iterations" title="Link to this heading"></a></h3>
<p>The Prover deals with loops by unrolling them a constant number of times
(see <a class="reference internal" href="../prover/cli/options.html#loop-iter"><span class="std std-ref">loop_iter</span></a>).
Furthermore, it can add an assertion that the number of unrolled iterations
was sufficient to fully capture all of the loop’s behavior, which is usually useful
in loops that are known to have a constant number of iterations.
Otherwise, the user can opt-in to assume the unroll bound was sufficient
(see <a class="reference internal" href="../prover/cli/options.html#optimistic-loop"><span class="std std-ref">optimistic_loop</span></a>).</p>
<p>This approach works well for common simple loops such as:</p>
<div class="highlight-solidity notranslate"><div class="highlight"><pre id="codecell0"><span></span><span class="kt">uint</span><span class="w"> </span><span class="nv">x</span><span class="p">;</span>
<span class="kt">for</span><span class="w"> </span><span class="p">(</span><span class="kt">uint</span><span class="w"> </span><span class="nv">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">;</span><span class="w"> </span>i<span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="m m-Decimal">3</span><span class="w"> </span><span class="p">;</span><span class="w"> </span>i<span class="o">++</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span>x<span class="o">++</span><span class="p">;</span>
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
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>For trivial loops such as the above, the Prover
automatically infers the required number of iterations is 3,
even if a lower <code class="docutils literal notranslate"><span class="pre">--loop_iter</span></code> is provided.</p>
</div>
<p>The natural loop condition determining whether we enter the body of the loop or exit
is clearly <code class="docutils literal notranslate"><span class="pre">i</span> <span class="pre">&lt;</span> <span class="pre">3</span></code>, thus 3 iterations are sufficient to fully unroll the loop and render
the loop condition false.
If <code class="docutils literal notranslate"><span class="pre">--loop_iter</span> <span class="pre">3</span></code> is defined, the Prover unrolls the loop 3 times,
and evaluates the loop exit condition one more time (a total of 4 evaluations of the loop exit condition).
The resulting code would behave like the following Solidity snippet:</p>
<div class="highlight-solidity notranslate"><div class="highlight"><pre id="codecell1"><span></span><span class="kt">uint</span><span class="w"> </span><span class="nv">x</span><span class="p">;</span>
<span class="kt">uint</span><span class="w"> </span><span class="nv">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">;</span>
<span class="kt">if</span><span class="w"> </span><span class="p">(</span>i<span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="m m-Decimal">3</span><span class="p">)</span><span class="w"> </span><span class="p">{</span><span class="w"> </span><span class="c1">// iteration #1</span>
<span class="w">    </span>i<span class="o">++</span><span class="p">;</span>
<span class="w">    </span>x<span class="o">++</span><span class="p">;</span>
<span class="w">    </span><span class="kt">if</span><span class="w"> </span><span class="p">(</span>i<span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="m m-Decimal">3</span><span class="p">)</span><span class="w"> </span><span class="p">{</span><span class="w"> </span><span class="c1">// iteration #2</span>
<span class="w">        </span>i<span class="o">++</span><span class="p">;</span>
<span class="w">        </span>x<span class="o">++</span><span class="p">;</span>
<span class="w">        </span><span class="kt">if</span><span class="w"> </span><span class="p">(</span>i<span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="m m-Decimal">3</span><span class="p">)</span><span class="w"> </span><span class="p">{</span><span class="w"> </span><span class="c1">// iteration #3</span>
<span class="w">            </span>i<span class="o">++</span><span class="p">;</span>
<span class="w">            </span>x<span class="o">++</span><span class="p">;</span>
<span class="w">            </span>assert<span class="w"> </span><span class="p">(</span>i<span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="m m-Decimal">3</span><span class="p">)</span><span class="w"> </span><span class="c1">// exit condition evaluation</span>
<span class="w">            </span><span class="c1">// require(i &lt; 3) if `--optimistic_loop` is set</span>
<span class="w">        </span><span class="p">}</span>
<span class="w">    </span><span class="p">}</span>
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
<p>However, for less trivial cases, the definition is not so clear:</p>
<div class="highlight-solidity notranslate"><div class="highlight"><pre id="codecell2"><span></span><span class="kt">uint</span><span class="w"> </span><span class="nv">x</span><span class="p">;</span><span class="w"> </span><span class="c1">// global state variable</span>
<span class="kt">uint</span><span class="w"> </span><span class="nv">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">;</span>
<span class="kt">while</span><span class="w"> </span><span class="p">(</span><span class="kt">true</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span>x<span class="o">++</span><span class="p">;</span><span class="w"> </span><span class="c1">// if x overflows, we exit the loop and revert. But is this the loop condition?</span>
<span class="w">    </span><span class="kt">if</span><span class="w"> </span><span class="p">(</span>i<span class="w"> </span><span class="o">&gt;=</span><span class="w"> </span><span class="m m-Decimal">3</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">        </span><span class="kt">break</span><span class="p">;</span>
<span class="w">    </span><span class="p">}</span>
<span class="w">    </span>i<span class="w"> </span><span class="o">+=</span><span class="w"> </span><span class="m m-Decimal">1</span><span class="p">;</span>
<span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell2">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>Running the builtin sanity rule for the above code with <code class="docutils literal notranslate"><span class="pre">--loop_iter</span></code> of 2 or less
results in sanity violation (can find no paths reaching the end of the loop),
as is expected.
Sanity is passing with <code class="docutils literal notranslate"><span class="pre">--loop_iter</span> <span class="pre">3</span></code>.</p>
<p>However, running with <code class="docutils literal notranslate"><span class="pre">--loop_iter</span> <span class="pre">3</span></code> actually shows 4 loop iterations
in the Call Trace output.
The reason for that is that in cases the Prover cannot detect an exit condition
in the loop’s head, it unrolls one extra time to evaluate a potential exit condition
in the loop’s body.
In our case, the bytecode representation shows that the loop’s head is ending with
a non-conditional jump.
The equivalent Solidity-like version of the unrolled code would look as follows
(<code class="docutils literal notranslate"><span class="pre">c</span></code>-style <code class="docutils literal notranslate"><span class="pre">goto</span></code> and <code class="docutils literal notranslate"><span class="pre">label</span></code> commands were added for clarity):</p>
<div class="highlight-solidity notranslate"><div class="highlight"><pre id="codecell3"><span></span><span class="kt">uint</span><span class="w"> </span><span class="nv">x</span><span class="p">;</span><span class="w"> </span><span class="c1">// global state variable</span>
<span class="kt">uint</span><span class="w"> </span><span class="nv">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">;</span>
<span class="c1">// iteration #1</span>
x<span class="o">++</span><span class="p">;</span>
<span class="kt">if</span><span class="w"> </span><span class="p">(</span>i<span class="w"> </span><span class="o">&gt;=</span><span class="w"> </span><span class="m m-Decimal">3</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span>goto<span class="w"> </span>after_original_while_loop_end<span class="p">;</span>
<span class="p">}</span>
i<span class="w"> </span><span class="o">+=</span><span class="w"> </span><span class="m m-Decimal">1</span><span class="p">;</span>

<span class="c1">// iteration #2</span>
x<span class="o">++</span><span class="p">;</span>
<span class="kt">if</span><span class="w"> </span><span class="p">(</span>i<span class="w"> </span><span class="o">&gt;=</span><span class="w"> </span><span class="m m-Decimal">3</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span>goto<span class="w"> </span>after_original_while_loop_end<span class="p">;</span>
<span class="p">}</span>
i<span class="w"> </span><span class="o">+=</span><span class="w"> </span><span class="m m-Decimal">1</span><span class="p">;</span>

<span class="c1">// iteration #3</span>
x<span class="o">++</span><span class="p">;</span>
<span class="kt">if</span><span class="w"> </span><span class="p">(</span>i<span class="w"> </span><span class="o">&gt;=</span><span class="w"> </span><span class="m m-Decimal">3</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span>goto<span class="w"> </span>after_original_while_loop_end<span class="p">;</span>
<span class="p">}</span>
i<span class="w"> </span><span class="o">+=</span><span class="w"> </span><span class="m m-Decimal">1</span><span class="p">;</span>

<span class="c1">// iteration #4</span>
x<span class="o">++</span><span class="p">;</span>
<span class="kt">if</span><span class="w"> </span><span class="p">(</span>i<span class="w"> </span><span class="o">&gt;=</span><span class="w"> </span><span class="m m-Decimal">3</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span>goto<span class="w"> </span>after_original_while_loop_end<span class="p">;</span>
<span class="p">}</span>
i<span class="w"> </span><span class="o">+=</span><span class="w"> </span><span class="m m-Decimal">1</span><span class="p">;</span>

assert<span class="p">(</span><span class="kt">false</span><span class="p">);</span><span class="w"> </span><span class="c1">// require(false) if `--optimistic_loop` is set</span>

after_original_while_loop_end<span class="o">:</span><span class="w"> </span><span class="p">...</span>
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
</section>
</section>


           </div>
          </div>
          <footer><div class="rst-footer-buttons" role="navigation" aria-label="Footer">
        <a href="out-of-resources/timeout-theory.html" class="btn btn-neutral float-left" title="Timeouts in Certora Prover - Theoretical Background" accesskey="p" rel="prev"><span class="fa fa-arrow-circle-left" aria-hidden="true"></span> Previous</a>
        <a href="checking.html" class="btn btn-neutral float-right" title="Checking Specifications" accesskey="n" rel="next">Next <span class="fa fa-arrow-circle-right" aria-hidden="true"></span></a>
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