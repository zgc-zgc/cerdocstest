<!DOCTYPE html><html class="writer-html5" lang="en" data-content_root="../../"><head>
  <meta charset="utf-8"><meta name="viewport" content="width=device-width, initial-scale=1">

  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Certora Verification Language for Rust (CVLR) — Certora Prover Documentation 0.0 documentation</title>
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
    <link rel="next" title="Solana-Specific Options / CLI Flags" href="options.html">
    <link rel="prev" title="Using the Solana Certora Prover" href="usage.html"> 
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
<li class="toctree-l1"><a class="reference internal" href="../sunbeam/index.html">Sunbeam: Verification for Soroban</a></li>
<li class="toctree-l1 current" aria-expanded="true"><a class="reference internal" href="index.html"><button class="toctree-expand" title="Open/close menu"></button>The Certora Solana Prover</a><ul class="" aria-expanded="false">
<li class="toctree-l2"><a class="reference internal" href="installation.html">Get started with the Solana Certora Prover</a></li>
<li class="toctree-l2"><a class="reference internal" href="usage.html">Using the Solana Certora Prover</a></li>
<li class="toctree-l2 current" aria-expanded="true"><a class="reference internal current" href="#" aria-expanded="true"><button class="toctree-expand" title="Open/close menu"></button>Certora Verification Language for Rust (CVLR)</a><ul>
<li class="toctree-l3"><a class="reference internal" href="#assertions">Assertions</a></li>
<li class="toctree-l3"><a class="reference internal" href="#assumptions">Assumptions</a></li>
<li class="toctree-l3"><a class="reference internal" href="#nondeterministic-values">Nondeterministic Values</a></li>
<li class="toctree-l3"><a class="reference internal" href="#cvlr-rules">CVLR Rules</a></li>
</ul>
</li>
<li class="toctree-l2"><a class="reference internal" href="options.html">Solana-Specific Options / CLI Flags</a></li>
<li class="toctree-l2"><a class="reference internal" href="output.html">Understanding Prover Output for Solana Programs</a></li>
<li class="toctree-l2"><a class="reference internal" href="sanity.html">Rule Sanity Checks (Solana)</a></li>
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
      <li class="breadcrumb-item active">Certora Verification Language for Rust (CVLR)</li>
      <li class="wy-breadcrumbs-aside">
            <a href="../../_sources/docs/solana/speclanguage.md.txt" rel="nofollow"> View page source</a>
      </li>
  </ul>
  <hr>
</div>
          <div role="main" class="document" itemscope="itemscope" itemtype="http://schema.org/Article">
           <div itemprop="articleBody">
             
  <section id="certora-verification-language-for-rust-cvlr">
<h1>Certora Verification Language for Rust (CVLR)<a class="headerlink" href="#certora-verification-language-for-rust-cvlr" title="Link to this heading"></a></h1>
<p>CVLR stands for Certora Verification Language for Rust. It is pronounced like “cavalier”.
CVLR provides the basic primitives for writing verification rules that specify
pre- and post-conditions for client code. Unlike CVL for Solidity, CVLR is
embedded in Rust. It is compiled by the Rust compiler and has simple operational
semantics.</p>
<p>CVLR is deployed to <a class="reference external" href="https://crates.io/crates/cvlr">crates.io</a>. The development version can be found at https://github.com/Certora/cvlr.
Please note that CVLR is independent from the Solana ecosystem, specific CVLR features for
Solana are maintained as part of the <a class="reference external" href="https://crates.io/crates/cvlr-solana">cvlr-solana</a> package.</p>
<section id="assertions">
<h2>Assertions<a class="headerlink" href="#assertions" title="Link to this heading"></a></h2>
<p>The simplest feature of CVLR is assertions. An assertion is written as
<code class="docutils literal notranslate"><span class="pre">cvlr_assert!(cond)</span></code>, where <code class="docutils literal notranslate"><span class="pre">cond</span></code> is the condition being asserted.
The semantics is the same as traditional asserts in Rust – an assertion is
violated if there is (a panic-free) execution that reaches <code class="docutils literal notranslate"><span class="pre">cvlr_assert!(cond)</span></code>
and in the current execution state <code class="docutils literal notranslate"><span class="pre">cond</span></code> is false.</p>
<p>For example, <code class="docutils literal notranslate"><span class="pre">cvlr_assert!(true)</span></code> is never violated, while <code class="docutils literal notranslate"><span class="pre">cvlr_assert!(false)</span></code>
is always violated when reached.</p>
<p>What makes <code class="docutils literal notranslate"><span class="pre">cvlr_assert!</span></code> special is that it is verified symbolically by the
Certora Prover. That is, the Prover returns <code class="docutils literal notranslate"><span class="pre">Violated</span></code> if there is an input and
an execution of the program that reaches that assertion and violates it.</p>
<p>Often, the intended meaning of an assertion is to not be violated, i.e., to
hold on all possible executions. However, sometimes it is useful to check
whether some execution is possible. In that case, the specification intends for
the assertion to be reachable. For such cases, CVLR provides a satisfy
assertion, called <code class="docutils literal notranslate"><span class="pre">cvlr_satisfy!(cond)</span></code>.</p>
<p>The semantics of <code class="docutils literal notranslate"><span class="pre">cvlr_satisfy!(cond)</span></code> is that it is <code class="docutils literal notranslate"><span class="pre">Violated</span></code> when it is
either not reached, or when every execution that reaches it, violates the
condition. For example, <code class="docutils literal notranslate"><span class="pre">cvlr_satisfy!(true)</span></code> is violated only if it is never
reachable (i.e., part of dead code), and <code class="docutils literal notranslate"><span class="pre">cvlr_satisfy!(false)</span></code> is always
violated.</p>
</section>
<section id="assumptions">
<h2>Assumptions<a class="headerlink" href="#assumptions" title="Link to this heading"></a></h2>
<p>Assumptions provide a way to restrict input to reflect some pre-condition. CVLR
provides an assumption macro <code class="docutils literal notranslate"><span class="pre">cvlr_assume!(cond)</span></code>. If an execution reaches
<code class="docutils literal notranslate"><span class="pre">cvlr_assume!(cond)</span></code>, it continues only if <code class="docutils literal notranslate"><span class="pre">cond</span></code> is true in the current program
state. Otherwise, the execution aborts.</p>
<p>For example, <code class="docutils literal notranslate"><span class="pre">cvlr_assume!(true)</span></code> is a noop, while <code class="docutils literal notranslate"><span class="pre">cvlr_assume!(false)</span></code> blocks
all executions that reach it.</p>
<p>A typical use of <code class="docutils literal notranslate"><span class="pre">cvlr_assume!</span></code> is to restrict a range of a value beyond the
restriction afforded by its type. For example, restricting the maximum value of
a variable to <code class="docutils literal notranslate"><span class="pre">100</span></code> can be done as follows:</p>
<div class="highlight-rust notranslate"><div class="highlight"><pre id="codecell0"><span></span><span class="kd">let</span><span class="w"> </span><span class="n">fee_bps</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">get_some_fee</span><span class="p">();</span>
<span class="n">cvlr_assume</span><span class="o">!</span><span class="p">(</span><span class="n">fee_bps</span><span class="w"> </span><span class="o">&lt;=</span><span class="w"> </span><span class="mi">100</span><span class="p">)</span>
<span class="c1">// computation reaches here only if fee_bps is no greater than 100</span>
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
<section id="nondeterministic-values">
<h2>Nondeterministic Values<a class="headerlink" href="#nondeterministic-values" title="Link to this heading"></a></h2>
<p>A specification must tell the Prover what are the (symbolic) inputs that the
Prover has to explore. Such values are called non-deterministic. The name comes
from the fact that the Prover chooses the values non-deterministically (i.e., not
following any specific pre-determined exploration scheme or probability
distribution). Nondet values are similar to <em>arbitrary</em> values in property-based
testing, except that they are not chosen randomly, but are explored
exhaustively via symbolic reasoning.</p>
<p>CVLR provides a generic function <code class="docutils literal notranslate"><span class="pre">nondet()</span></code> that can generate non-deterministic
values of all primitive integers. For example, <code class="docutils literal notranslate"><span class="pre">nondet::&lt;u64&gt;()</span></code> returns a
non-deterministic <code class="docutils literal notranslate"><span class="pre">u64</span></code>, and <code class="docutils literal notranslate"><span class="pre">nondet::&lt;u16&gt;()</span></code> returns a non-deterministic
<code class="docutils literal notranslate"><span class="pre">u16</span></code>.</p>
</section>
<section id="cvlr-rules">
<h2>CVLR Rules<a class="headerlink" href="#cvlr-rules" title="Link to this heading"></a></h2>
<p>Specifications are written as pre- and post-conditions in rules. A rule is
similar to a unit test. However, instead of being executed for some specific
input, the rule is symbolically analyzed for all possible
non-deterministic values.</p>
<p>In CVLR, rules are regular Rust functions, annotated with <code class="docutils literal notranslate"><span class="pre">#[rule]</span></code>.</p>
<p>A complete example of a specification with several rules is shown below.
The function being verified is <code class="docutils literal notranslate"><span class="pre">compute_fee</span></code>. We have included it in the spec
file for simplicity.</p>
<div class="highlight-rust notranslate"><div class="highlight"><pre id="codecell1"><span></span><span class="k">use</span><span class="w"> </span><span class="n">cvlr</span><span class="p">::</span><span class="n">prelude</span><span class="p">::</span><span class="o">*</span><span class="p">;</span>

<span class="k">pub</span><span class="w"> </span><span class="k">fn</span><span class="w"> </span><span class="nf">compute_fee</span><span class="p">(</span><span class="n">amount</span><span class="p">:</span><span class="w"> </span><span class="kt">u64</span><span class="p">,</span><span class="w"> </span><span class="n">fee_bps</span><span class="p">:</span><span class="w"> </span><span class="kt">u16</span><span class="p">)</span><span class="w"> </span><span class="p">-&gt;</span><span class="w"> </span><span class="nb">Option</span><span class="o">&lt;</span><span class="kt">u64</span><span class="o">&gt;</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="k">if</span><span class="w"> </span><span class="n">amount</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="mi">0</span><span class="w"> </span><span class="p">{</span><span class="w"> </span><span class="k">return</span><span class="w"> </span><span class="nb">None</span><span class="p">;</span><span class="w"> </span><span class="p">}</span>
<span class="w">    </span><span class="kd">let</span><span class="w"> </span><span class="n">fee</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">amount</span><span class="p">.</span><span class="n">checked_mul</span><span class="p">(</span><span class="n">fee_bps</span><span class="p">).</span><span class="n">checked_div</span><span class="p">(</span><span class="mi">10_000</span><span class="p">);</span>
<span class="w">    </span><span class="n">fee</span>
<span class="p">}</span>

<span class="cp">#[rule]</span>
<span class="k">pub</span><span class="w"> </span><span class="k">fn</span><span class="w"> </span><span class="nf">rule_fee_sanity</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<span class="w">   </span><span class="n">compute_fee</span><span class="p">(</span><span class="n">nondet</span><span class="p">(),</span><span class="w"> </span><span class="n">nondet</span><span class="p">()).</span><span class="n">unwrap</span><span class="p">();</span>
<span class="w">   </span><span class="n">cvlr_satisfy</span><span class="o">!</span><span class="p">(</span><span class="kc">true</span><span class="p">);</span><span class="w"> </span>
<span class="p">}</span>

<span class="cp">#[rule]</span>
<span class="k">pub</span><span class="w"> </span><span class="k">fn</span><span class="w"> </span><span class="nf">rule_fee_assessed</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kd">let</span><span class="w"> </span><span class="n">amt</span><span class="p">:</span><span class="w"> </span><span class="kt">u64</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">nondet</span><span class="p">();</span>
<span class="w">    </span><span class="kd">let</span><span class="w"> </span><span class="n">fee_bps</span><span class="p">:</span><span class="w"> </span><span class="kt">u16</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">nondet</span><span class="p">();</span>
<span class="w">    </span><span class="n">cvlr_assume</span><span class="o">!</span><span class="p">(</span><span class="n">fee_bps</span><span class="w"> </span><span class="o">&lt;=</span><span class="w"> </span><span class="mi">10_000</span><span class="p">);</span>
<span class="w">    </span><span class="kd">let</span><span class="w"> </span><span class="n">fee</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">compute_fee</span><span class="p">(</span><span class="n">amt</span><span class="p">,</span><span class="w"> </span><span class="n">fee_bps</span><span class="p">).</span><span class="n">unwrap</span><span class="p">();</span>
<span class="w">    </span><span class="n">clog</span><span class="o">!</span><span class="p">(</span><span class="n">amt</span><span class="p">,</span><span class="w"> </span><span class="n">fee_bps</span><span class="p">,</span><span class="w"> </span><span class="n">fee</span><span class="p">);</span>
<span class="w">    </span><span class="n">cvlr_assert</span><span class="o">!</span><span class="p">(</span><span class="n">fee</span><span class="w"> </span><span class="o">&lt;=</span><span class="w"> </span><span class="n">amt</span><span class="p">);</span>
<span class="w">    </span><span class="k">if</span><span class="w"> </span><span class="n">fee_bps</span><span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="mi">0</span><span class="w"> </span><span class="p">{</span><span class="w"> </span><span class="n">cvlr_assert</span><span class="o">!</span><span class="p">(</span><span class="n">fee</span><span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="mi">0</span><span class="p">);</span><span class="w"> </span><span class="p">}</span>
<span class="p">}</span>

<span class="cp">#[rule]</span>
<span class="k">pub</span><span class="w"> </span><span class="k">fn</span><span class="w"> </span><span class="nf">rule_fee_liveness</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kd">let</span><span class="w"> </span><span class="n">amt</span><span class="p">:</span><span class="w"> </span><span class="kt">u64</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">nondet</span><span class="p">();</span>
<span class="w">    </span><span class="kd">let</span><span class="w"> </span><span class="n">fee_bps</span><span class="p">:</span><span class="w"> </span><span class="kt">u16</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">nondet</span><span class="p">();</span>
<span class="w">    </span><span class="n">cvlr_assume</span><span class="o">!</span><span class="p">(</span><span class="n">fee_bps</span><span class="w"> </span><span class="o">&lt;=</span><span class="w"> </span><span class="mi">10_000</span><span class="p">);</span>
<span class="w">    </span><span class="kd">let</span><span class="w"> </span><span class="n">fee</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">compute_fee</span><span class="p">(</span><span class="n">amt</span><span class="p">,</span><span class="w"> </span><span class="n">fee_bps</span><span class="p">);</span>
<span class="w">    </span><span class="n">clog</span><span class="o">!</span><span class="p">(</span><span class="n">amt</span><span class="p">,</span><span class="w"> </span><span class="n">fee_bps</span><span class="p">,</span><span class="w"> </span><span class="n">fee</span><span class="p">);</span>
<span class="w">    </span><span class="k">if</span><span class="w"> </span><span class="n">fee</span><span class="p">.</span><span class="n">is_none</span><span class="p">()</span><span class="w"> </span><span class="p">{</span><span class="w"> </span><span class="n">cvlr_assert</span><span class="o">!</span><span class="p">(</span><span class="n">amt</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="mi">0</span><span class="p">);</span><span class="w"> </span><span class="p">}</span>
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
<p>The rule <code class="docutils literal notranslate"><span class="pre">rule_fee_sanity</span></code> checks that the function under verification has at
least one panic-free execution. A rule like that is called a sanity rule. It is
a good practice to start a specification with such a rule.</p>
<p>The rule <code class="docutils literal notranslate"><span class="pre">rule_fee_assessed</span></code> checks that a fee can be computed for an arbitrary amount.
It has two assertions. The first checks that the fee is never greater than
the amount. The second checks that the fee is always assessed when required.
The first assertion is not violated. However, the second is. Can you spot the bug?
Note that we have also added calls to the log macro <code class="docutils literal notranslate"><span class="pre">clog!</span></code> that is similar to
the <code class="docutils literal notranslate"><span class="pre">dbg!</span></code> macro in Rust. The <code class="docutils literal notranslate"><span class="pre">clog!</span></code> macro will instruct the Prover to produce the
values of the desired variables in any violating execution.</p>
<p>The rule <code class="docutils literal notranslate"><span class="pre">rule_fee_liveness</span></code> checks that the fee is always computed, except when
the fee rate is 0. This assertion is violated. Can you spot the bug?</p>
</section>
</section>


           </div>
          </div>
          <footer><div class="rst-footer-buttons" role="navigation" aria-label="Footer">
        <a href="usage.html" class="btn btn-neutral float-left" title="Using the Solana Certora Prover" accesskey="p" rel="prev"><span class="fa fa-arrow-circle-left" aria-hidden="true"></span> Previous</a>
        <a href="options.html" class="btn btn-neutral float-right" title="Solana-Specific Options / CLI Flags" accesskey="n" rel="next">Next <span class="fa fa-arrow-circle-right" aria-hidden="true"></span></a>
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