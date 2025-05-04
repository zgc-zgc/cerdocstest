<!DOCTYPE html><html class="writer-html5" lang="en" data-content_root="../../../"><head>
  <meta charset="utf-8"><meta name="viewport" content="width=device-width, initial-scale=1">

  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>CVL2 Migration Guide — Certora Prover Documentation 0.0 documentation</title>
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
    <link rel="next" title="Certora CLI 5.0 Changes" href="../v5-changes.html">
    <link rel="prev" title="Changes Introduced in CVL 2" href="changes.html"> 
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
<li class="toctree-l1 current" aria-expanded="true"><a class="reference internal" href="../index.html"><button class="toctree-expand" title="Open/close menu"></button>The Certora Verification Language</a><ul class="" aria-expanded="false">
<li class="toctree-l2"><a class="reference internal" href="../overview.html">Specification Files</a></li>
<li class="toctree-l2"><a class="reference internal" href="../basics.html">Basic Syntax</a></li>
<li class="toctree-l2"><a class="reference internal" href="../types.html">Types</a></li>
<li class="toctree-l2"><a class="reference internal" href="../expr.html">Expressions</a></li>
<li class="toctree-l2"><a class="reference internal" href="../statements.html">Statements</a></li>
<li class="toctree-l2"><a class="reference internal" href="../imports.html">Import and Use Statements</a></li>
<li class="toctree-l2"><a class="reference internal" href="../using.html">Using Statements</a></li>
<li class="toctree-l2"><a class="reference internal" href="../methods.html">The Methods Block</a></li>
<li class="toctree-l2"><a class="reference internal" href="../rules.html">Rules</a></li>
<li class="toctree-l2"><a class="reference internal" href="../builtin.html">Built-in Rules</a></li>
<li class="toctree-l2"><a class="reference internal" href="../functions.html">Functions</a></li>
<li class="toctree-l2"><a class="reference internal" href="../invariants.html">Invariants</a></li>
<li class="toctree-l2"><a class="reference internal" href="../sorts.html">Uninterpreted Sorts</a></li>
<li class="toctree-l2"><a class="reference internal" href="../ghosts.html">Ghosts</a></li>
<li class="toctree-l2"><a class="reference internal" href="../defs.html">Definitions</a></li>
<li class="toctree-l2"><a class="reference internal" href="../hooks.html">Hooks</a></li>
<li class="toctree-l2"><a class="reference internal" href="../transient.html">Transient Storage</a></li>
<li class="toctree-l2"><a class="reference internal" href="../foundry-integration.html">Foundry Integration (Alpha)</a></li>
<li class="toctree-l2 current" aria-expanded="true"><a class="reference internal" href="../index.html#changes-since-cvl-1"><button class="toctree-expand" title="Open/close menu"></button>Changes Since CVL 1</a><ul class="" aria-expanded="false">
<li class="toctree-l3"><a class="reference internal" href="changes.html">Changes Introduced in CVL 2</a></li>
<li class="toctree-l3 current" aria-expanded="true"><a class="reference internal current" href="#" aria-expanded="true"><button class="toctree-expand" title="Open/close menu"></button>CVL2 Migration Guide</a><ul>
<li class="toctree-l4"><a class="reference internal" href="#step-0-install-cvl-2">Step 0: Install CVL 2</a></li>
<li class="toctree-l4"><a class="reference internal" href="#step-1-skim-cvl-2-changes">Step 1: Skim CVL 2 changes</a></li>
<li class="toctree-l4"><a class="reference internal" href="#step-2-run-the-migration-script">Step 2: Run the migration script</a></li>
<li class="toctree-l4"><a class="reference internal" href="#step-3-fix-type-errors">Step 3: Fix type errors</a></li>
<li class="toctree-l4"><a class="reference internal" href="#step-4-review-your-methods-blocks">Step 4: Review your <code class="docutils literal notranslate"><span class="pre">methods</span></code> blocks</a></li>
<li class="toctree-l4"><a class="reference internal" href="#step-5-profit">Step 5: Profit!</a></li>
</ul>
</li>
<li class="toctree-l3"><a class="reference internal" href="../v5-changes.html">Certora CLI 5.0 Changes</a></li>
</ul>
</li>
</ul>
</li>
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
          <li class="breadcrumb-item"><a href="../index.html">The Certora Verification Language</a></li>
      <li class="breadcrumb-item active">CVL2 Migration Guide</li>
      <li class="wy-breadcrumbs-aside">
            <a href="../../../_sources/docs/cvl/cvl2/migration.md.txt" rel="nofollow"> View page source</a>
      </li>
  </ul>
  <hr>
</div>
          <div role="main" class="document" itemscope="itemscope" itemtype="http://schema.org/Article">
           <div itemprop="articleBody">
             
  <section id="cvl2-migration-guide">
<h1>CVL2 Migration Guide<a class="headerlink" href="#cvl2-migration-guide" title="Link to this heading"></a></h1>
<p>This section gives a step-by-step process for migrating your specs from CVL 1 to
CVL 2.  It only addresses the changes that are most likely to arise; for full
details see <a class="reference internal" href="changes.html"><span class="doc">Changes Introduced in CVL 2</span></a>.</p>
<p>Here is an outline of the migration process:</p>
<nav class="contents local" id="contents">
<ul class="simple">
<li><p><a class="reference internal" href="#step-0-install-cvl-2" id="id3">Step 0: Install CVL 2</a></p></li>
<li><p><a class="reference internal" href="#step-1-skim-cvl-2-changes" id="id4">Step 1: Skim CVL 2 changes</a></p></li>
<li><p><a class="reference internal" href="#step-2-run-the-migration-script" id="id5">Step 2: Run the migration script</a></p></li>
<li><p><a class="reference internal" href="#step-3-fix-type-errors" id="id6">Step 3: Fix type errors</a></p></li>
<li><p><a class="reference internal" href="#step-4-review-your-methods-blocks" id="id7">Step 4: Review your <code class="docutils literal notranslate"><span class="pre">methods</span></code> blocks</a></p></li>
<li><p><a class="reference internal" href="#step-5-profit" id="id8">Step 5: Profit!</a></p></li>
</ul>
</nav>
<p>If you have any questions, please <a class="reference internal" href="../../../index.html#contact"><span class="std std-ref">ask for help</span></a>!</p>
<section id="step-0-install-cvl-2">
<h2><a class="toc-backref" href="#id3" role="doc-backlink">Step 0: Install CVL 2</a><a class="headerlink" href="#step-0-install-cvl-2" title="Link to this heading"></a></h2>
<p>The <code class="docutils literal notranslate"><span class="pre">certora-cli</span></code> python package will use CVL 2 starting with version 4.0.0.</p>
<p>If you aren’t ready to migrate your specs yet, Certora will continue supporting
CVL 1 for three months after the official release of CVL 2.  You can keep
using CVL 1 after the release of <code class="docutils literal notranslate"><span class="pre">certora-cli-4.0.0</span></code> by pinning your
<code class="docutils literal notranslate"><span class="pre">certora-cli</span></code> package to version <code class="docutils literal notranslate"><span class="pre">3.6.5</span></code>:</p>
<div class="highlight-default notranslate"><div class="highlight"><pre id="codecell0"><span></span><span class="n">pip</span> <span class="n">install</span> <span class="s1">'certora-cli&lt;4.0.0'</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell0">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>If you want to switch between the two versions, see the instructions for setting
up a virtual environment in <a class="reference internal" href="../../user-guide/install.html#beta-install"><span class="std std-ref">Installing the beta version (optional)</span></a>.</p>
</section>
<section id="step-1-skim-cvl-2-changes">
<h2><a class="toc-backref" href="#id4" role="doc-backlink">Step 1: Skim CVL 2 changes</a><a class="headerlink" href="#step-1-skim-cvl-2-changes" title="Link to this heading"></a></h2>
<p>We recommend at least skimming <a class="reference internal" href="changes.html"><span class="doc">Changes Introduced in CVL 2</span></a> to familiarize yourself with the
changes introduced by CVL 2.</p>
</section>
<section id="step-2-run-the-migration-script">
<h2><a class="toc-backref" href="#id5" role="doc-backlink">Step 2: Run the migration script</a><a class="headerlink" href="#step-2-run-the-migration-script" title="Link to this heading"></a></h2>
<p>Certora has written a simple script to aid in the conversion from CVL 1 to
CVL 2.  You can download the script <a class="reference external" href="https://gist.github.com/shellygr/c054a0ad569397ef4e19ec1d1d5afcdb">here</a>.</p>
<p>The script will automatically modify all <code class="docutils literal notranslate"><span class="pre">.spec</span></code> files in a directory.  The
script will modify the files in place, so make sure that you commit your files
before running it.</p>
<p>To run the script, place it in a file called <code class="docutils literal notranslate"><span class="pre">CVL1_to_CVL2.0_syntax_update.py</span></code>
and run it using the following command:</p>
<div class="highlight-default notranslate"><div class="highlight"><pre id="codecell1"><span></span><span class="n">python3</span> <span class="n">CVL1_to_CVL2</span><span class="mf">.0</span><span class="n">_syntax_update</span><span class="o">.</span><span class="n">py</span> <span class="o">-</span><span class="n">d</span> <span class="o">&lt;</span><span class="n">path</span><span class="o">&gt;</span> <span class="o">-</span><span class="n">r</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell1">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>Run <code class="docutils literal notranslate"><span class="pre">python3</span> <span class="pre">CVL1_to_CVL2.0_syntax_update.py</span> <span class="pre">--help</span></code> for further instructions.</p>
<p>The migration script only handles simple cases, and is not guaranteed to work.
Some manual work and adjustment may be needed after running the script. The
script may also make odd mistakes.</p>
<p>The script will attempt to make the following changes:</p>
<ul class="simple">
<li><p>replace <code class="docutils literal notranslate"><span class="pre">sinvoke</span> <span class="pre">f(...)</span></code> with <code class="docutils literal notranslate"><span class="pre">f(...)</span></code></p></li>
<li><p>replace <code class="docutils literal notranslate"><span class="pre">invoke</span> <span class="pre">f(...)</span></code> with <code class="docutils literal notranslate"><span class="pre">f@withrevert(...)</span></code></p></li>
<li><p>replace <code class="docutils literal notranslate"><span class="pre">f(...).selector</span></code> with <code class="docutils literal notranslate"><span class="pre">sig:f(...).selector</span></code></p></li>
<li><p>ensure that rules start with <code class="docutils literal notranslate"><span class="pre">rule</span></code></p></li>
<li><p>replace <code class="docutils literal notranslate"><span class="pre">static_assert</span></code> with <code class="docutils literal notranslate"><span class="pre">assert</span></code></p></li>
<li><p>replace <code class="docutils literal notranslate"><span class="pre">static_require</span></code> with <code class="docutils literal notranslate"><span class="pre">require</span></code></p></li>
<li><p>add <code class="docutils literal notranslate"><span class="pre">;</span></code> to the end of <code class="docutils literal notranslate"><span class="pre">pragma</span></code>, <code class="docutils literal notranslate"><span class="pre">import</span></code>, <code class="docutils literal notranslate"><span class="pre">using</span></code>, and <code class="docutils literal notranslate"><span class="pre">use</span></code> statements</p></li>
<li><p>add a <code class="docutils literal notranslate"><span class="pre">;</span></code> to the end of a methods block entry if it doesn’t seem to continue to the next line</p></li>
<li><p>add <code class="docutils literal notranslate"><span class="pre">function</span></code> to the beginning of a methods block entry</p></li>
<li><p>add <code class="docutils literal notranslate"><span class="pre">external</span></code> to unsummarized or <code class="docutils literal notranslate"><span class="pre">DISPATCHER</span></code> methods block entries</p></li>
<li><p>change <code class="docutils literal notranslate"><span class="pre">function</span> <span class="pre">f(...)</span></code> to <code class="docutils literal notranslate"><span class="pre">function</span> <span class="pre">_.f(...)</span></code> for summarized external functions</p></li>
</ul>
<p>In particular, as the script only consumes spec files, there are decisions that
it cannot make, as they are based on the Solidity code. Some of those are
listed here.</p>
</section>
<section id="step-3-fix-type-errors">
<h2><a class="toc-backref" href="#id6" role="doc-backlink">Step 3: Fix type errors</a><a class="headerlink" href="#step-3-fix-type-errors" title="Link to this heading"></a></h2>
<p>This is a good time to try running <code class="docutils literal notranslate"><span class="pre">certoraRun</span></code> on your spec.  The command-line
interface to <code class="docutils literal notranslate"><span class="pre">certoraRun</span></code> has not changed in CVL 2, so you should try to verify
your contract the same way you usually would.</p>
<p>If your spec verifies without errors, move on to
<a class="reference internal" href="#cvl2-migration-summaries"><span class="std std-ref">Step 4: Review your methods blocks</span></a>!  If <code class="docutils literal notranslate"><span class="pre">certoraRun</span></code> reports errors, you will need
to fix them manually.  Here are some of the more common errors that you may
come across:</p>
<nav class="contents local" id="id1">
<ul class="simple">
<li><p><a class="reference internal" href="#syntax-errors-introduced-by-the-migration-script" id="id9">Syntax errors introduced by the migration script</a></p></li>
<li><p><a class="reference internal" href="#type-errors-in-arithmetic-and-casts" id="id10">Type errors in arithmetic and casts</a></p></li>
<li><p><a class="reference internal" href="#using-statements" id="id11"><code class="docutils literal notranslate"><span class="pre">using</span></code> statements</a></p></li>
<li><p><a class="reference internal" href="#problems-with-certorafallback-or-invoke-fallback" id="id12">Problems with <code class="docutils literal notranslate"><span class="pre">certorafallback</span></code> or <code class="docutils literal notranslate"><span class="pre">invoke_fallback</span></code></a></p></li>
</ul>
</nav>
<p>This section contains specific advice for these situations; if you come across
problems that are not covered here, consult the <a class="reference internal" href="changes.html"><span class="doc">Changes Introduced in CVL 2</span></a> or ask!</p>
<section id="syntax-errors-introduced-by-the-migration-script">
<h3><a class="toc-backref" href="#id9" role="doc-backlink">Syntax errors introduced by the migration script</a><a class="headerlink" href="#syntax-errors-introduced-by-the-migration-script" title="Link to this heading"></a></h3>
<p>The migration script is not perfect, and can make syntax mistakes in some
cases, such as adding an extra semicolon or omitting a keyword.  We hope these
will be easy to identify and fix, but if you have syntax errors you can’t
understand, consult <a class="reference internal" href="changes.html#cvl2-superficial-syntax-changes"><span class="std std-ref">Superficial syntax changes</span></a>.</p>
</section>
<section id="type-errors-in-arithmetic-and-casts">
<h3><a class="toc-backref" href="#id10" role="doc-backlink">Type errors in arithmetic and casts</a><a class="headerlink" href="#type-errors-in-arithmetic-and-casts" title="Link to this heading"></a></h3>
<p>CVL 2 is more careful about converting between different integer types.  See
<a class="reference internal" href="changes.html#cvl2-integer-types"><span class="std std-ref">Changes to integer types</span></a> in the changes guide for complete details and
examples.</p>
<p>If you have errors that indicate problems with number types, try the following:</p>
<ul class="simple">
<li><p>Try to change most of your integers to <code class="docutils literal notranslate"><span class="pre">mathint</span></code>.  The only integers that
should <em>not</em> be <code class="docutils literal notranslate"><span class="pre">mathint</span></code> are those that you are passing as arguments to
contract functions.</p></li>
<li><p>If you have a type error in a <code class="docutils literal notranslate"><span class="pre">havoc</span> <span class="pre">...</span> <span class="pre">assuming</span></code> statement, consider using
the <a class="reference internal" href="../ghosts.html#ghost-variables"><span class="std std-ref">newer ghost variable syntax</span></a>.  This can avoid
potential vacuity pitfalls caused by mixing <code class="docutils literal notranslate"><span class="pre">to_mathint</span></code> and <code class="docutils literal notranslate"><span class="pre">havoc</span> <span class="pre">...</span> <span class="pre">assuming</span></code>.</p></li>
<li><p>If you need to modify the output of one contract function and pass it to
another contract function, you will need to think carefully about how you
want to handle overflow.  If you think the computation won’t go out of bounds,
you can use an <code class="docutils literal notranslate"><span class="pre">assert_</span></code> cast to assert that the value is in bounds.  If you
want to ignore cases where the value goes out of bounds, you can use a
<code class="docutils literal notranslate"><span class="pre">require_</span></code> cast (but think twice first: <code class="docutils literal notranslate"><span class="pre">require_</span></code> casts are dangerous!).
See <a class="reference internal" href="changes.html#cvl2-integer-types"><span class="std std-ref">Changes to integer types</span></a> for more details.</p></li>
</ul>
<div class="admonition warning">
<p class="admonition-title">Warning</p>
<p>Use <code class="docutils literal notranslate"><span class="pre">assert_</span></code> and <code class="docutils literal notranslate"><span class="pre">require_</span></code> casts sparingly!  <code class="docutils literal notranslate"><span class="pre">assert_</span></code> casts can lead to
unnecessary counterexamples, and <code class="docutils literal notranslate"><span class="pre">require_</span></code> casts can hide bugs in your contracts
(just as any <code class="docutils literal notranslate"><span class="pre">require</span></code> statement can).</p>
</div>
<ul>
<li><p>You cannot use <code class="docutils literal notranslate"><span class="pre">assert_</span></code> and <code class="docutils literal notranslate"><span class="pre">require_</span></code> casts inside
<a class="reference internal" href="../../user-guide/glossary.html#term-quantifier"><span class="xref std std-term">quantified statements</span></a>.
To solve that issue, you can introduce an additional universally quantified
variable of type <code class="docutils literal notranslate"><span class="pre">uint256</span></code>, and require it to be equal to the expression using
an upcast to <code class="docutils literal notranslate"><span class="pre">mathint</span></code>.</p>
<p>For example, if there is a ghost array access <code class="docutils literal notranslate"><span class="pre">forall</span> <span class="pre">uint</span> <span class="pre">x.</span> <span class="pre">a[x+1]</span> <span class="pre">==</span> <span class="pre">0</span></code>,
rewrite it as follows:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell2"><span></span><span class="kr">forall</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>x<span class="p">.</span><span class="w"> </span><span class="kr">forall</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>y<span class="p">.</span><span class="w"> </span><span class="nb">to_mathint</span><span class="p">(</span>y<span class="p">)</span><span class="w"> </span><span class="o">==</span><span class="w"> </span>x<span class="o">+</span><span class="m m-Decimal">1</span><span class="w"> </span><span class="o">=&gt;</span><span class="w"> </span>a<span class="p">[</span>y<span class="p">]</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="m m-Decimal">0</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell2">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</li>
</ul>
</section>
<section id="using-statements">
<h3><a class="toc-backref" href="#id11" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">using</span></code> statements</a><a class="headerlink" href="#using-statements" title="Link to this heading"></a></h3>
<p>Multi-contract declaration using <code class="docutils literal notranslate"><span class="pre">using</span></code> statements are not imported.  If you
have a spec <code class="docutils literal notranslate"><span class="pre">a.spec</span></code> importing <code class="docutils literal notranslate"><span class="pre">b.spec</span></code>, with <code class="docutils literal notranslate"><span class="pre">b.spec</span></code> declaring a
multicontract contract usage, which you need in <code class="docutils literal notranslate"><span class="pre">a.spec</span></code>, repeat the
declaration from <code class="docutils literal notranslate"><span class="pre">b.spec</span></code>, and rename the alias.</p>
<p><em>The next minor version of CVL2 will improve this behavior.</em></p>
</section>
<section id="problems-with-certorafallback-or-invoke-fallback">
<h3><a class="toc-backref" href="#id12" role="doc-backlink">Problems with <code class="docutils literal notranslate"><span class="pre">certorafallback</span></code> or <code class="docutils literal notranslate"><span class="pre">invoke_fallback</span></code></a><a class="headerlink" href="#problems-with-certorafallback-or-invoke-fallback" title="Link to this heading"></a></h3>
<p>CVL2 does not allow you to refer to the fallback function explicitly as it was
seldom used and not well-defined. The most common use case for having to refer
to the fallback was to check if a parametric method is the fallback function.
For that, one can use the <code class="docutils literal notranslate"><span class="pre">.isFallback</span></code> field of any variable of type <code class="docutils literal notranslate"><span class="pre">method</span></code>.</p>
<p>See <a class="reference internal" href="changes.html#cvl2-fallback-changes"><span class="std std-ref">Changes to the fallback function</span></a> for examples.</p>
</section>
</section>
<section id="step-4-review-your-methods-blocks">
<span id="cvl2-migration-summaries"></span><h2><a class="toc-backref" href="#id7" role="doc-backlink">Step 4: Review your <code class="docutils literal notranslate"><span class="pre">methods</span></code> blocks</a><a class="headerlink" href="#step-4-review-your-methods-blocks" title="Link to this heading"></a></h2>
<p>CVL 2 changes the requirements for and meanings of methods block entries; you
should manually review all of your methods block entries to make sure they have
the intended meanings.  Here are the things to consider:</p>
<nav class="contents local" id="id2">
<ul class="simple">
<li><p><a class="reference internal" href="#internal-and-external-methods" id="id13"><code class="docutils literal notranslate"><span class="pre">internal</span></code> and <code class="docutils literal notranslate"><span class="pre">external</span></code> methods</a></p></li>
<li><p><a class="reference internal" href="#receiver-contracts" id="id14">Receiver contracts</a></p></li>
</ul>
</nav>
<p>The remainder of this section describes these considerations.  See
<a class="reference internal" href="changes.html#cvl2-methods-blocks"><span class="std std-ref">Changes to methods block entries</span></a> for more details.</p>
<p>If you have complex methods blocks, we encourage you to examine the call
resolution tab on the rule report to double-check that your summaries are
applied as you expect them to be.</p>
<section id="internal-and-external-methods">
<h3><a class="toc-backref" href="#id13" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">internal</span></code> and <code class="docutils literal notranslate"><span class="pre">external</span></code> methods</a><a class="headerlink" href="#internal-and-external-methods" title="Link to this heading"></a></h3>
<p>In CVL 2, you must mark <code class="docutils literal notranslate"><span class="pre">methods</span></code> block entries as either <code class="docutils literal notranslate"><span class="pre">internal</span></code> or
<code class="docutils literal notranslate"><span class="pre">external</span></code>.  Unlike Solidity, you cannot mark entries as <code class="docutils literal notranslate"><span class="pre">private</span></code> or <code class="docutils literal notranslate"><span class="pre">public</span></code>.</p>
<p>The Prover does not distinguish between <code class="docutils literal notranslate"><span class="pre">private</span></code> and <code class="docutils literal notranslate"><span class="pre">internal</span></code> methods; if
you want to summarize a <code class="docutils literal notranslate"><span class="pre">private</span></code> method, use <code class="docutils literal notranslate"><span class="pre">internal</span></code> in the <code class="docutils literal notranslate"><span class="pre">methods</span></code> block.</p>
<p>To understand how to work with public Solidity methods, it is important to
understand how Solidity compiles public functions.  When a contract contains a
public method, the Solidity compiler generates an internal method that executes
the code, and an external method that calls the internal method.</p>
<p>You can add methods block entries for either (or both) of those methods, and
they will have different effects.  See <a class="reference internal" href="changes.html#cvl2-visibility"><span class="std std-ref">Required internal or external annotation</span></a> for the details.</p>
</section>
<section id="receiver-contracts">
<h3><a class="toc-backref" href="#id14" role="doc-backlink">Receiver contracts</a><a class="headerlink" href="#receiver-contracts" title="Link to this heading"></a></h3>
<p>In CVL 1, method summaries applied to all methods in all contracts that match
the specified signature.  In CVL 2, summaries only apply to one contract by
default.</p>
<p>You specify the receiver contract just before the method name.  For example, to
refer to the <code class="docutils literal notranslate"><span class="pre">exampleMethod</span></code> method of the <code class="docutils literal notranslate"><span class="pre">ExampleContract</span></code> contract, you would
write:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell3"><span></span><span class="kr">methods</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kd">function</span><span class="w"> </span><span class="nc">ExampleContract</span><span class="p">.</span><span class="nf">exampleMethod</span><span class="p">(</span><span class="kt">uint</span><span class="p">)</span><span class="w"> </span><span class="kr">external</span><span class="w"> </span><span class="kr">returns</span><span class="p">(</span><span class="kt">uint</span><span class="p">);</span>
<span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell3">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>If no contract is specified, the default contract is <code class="docutils literal notranslate"><span class="pre">currentContract</span></code>.</p>
<p>If you want to write an entry that applies to methods in all contracts with the
given signature, you can use the special <code class="docutils literal notranslate"><span class="pre">_</span></code> receiver:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell4"><span></span><span class="kr">methods</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kd">function</span><span class="w"> </span><span class="nc">_</span><span class="p">.</span><span class="nf">exampleMethod</span><span class="p">(</span><span class="kt">uint</span><span class="p">)</span><span class="w"> </span><span class="kr">external</span><span class="w"> </span><span class="kp">=&gt;</span><span class="w"> </span><span class="kc">NONDET</span><span class="p">;</span>
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
<p>Wildcard entries cannot specify return types.  If you summarize them with a CVL
function or ghost, you will need to supply an <code class="docutils literal notranslate"><span class="pre">expect</span></code> clause.  See
<a class="reference internal" href="changes.html#cvl2-wildcards"><span class="std std-ref">Summaries only apply to one contract by default</span></a> for details.</p>
</section>
</section>
<section id="step-5-profit">
<h2><a class="toc-backref" href="#id8" role="doc-backlink">Step 5: Profit!</a><a class="headerlink" href="#step-5-profit" title="Link to this heading"></a></h2>
<p>Hopefully this guide has helped you successfully migrate to CVL 2.  Although
the functional changes in CVL 2.0 are relatively small, the internal changes
lay the groundwork for many exciting features.  We promise that the effort
involved in migration will pay off in the next few releases!</p>
</section>
</section>


           </div>
          </div>
          <footer><div class="rst-footer-buttons" role="navigation" aria-label="Footer">
        <a href="changes.html" class="btn btn-neutral float-left" title="Changes Introduced in CVL 2" accesskey="p" rel="prev"><span class="fa fa-arrow-circle-left" aria-hidden="true"></span> Previous</a>
        <a href="../v5-changes.html" class="btn btn-neutral float-right" title="Certora CLI 5.0 Changes" accesskey="n" rel="next">Next <span class="fa fa-arrow-circle-right" aria-hidden="true"></span></a>
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