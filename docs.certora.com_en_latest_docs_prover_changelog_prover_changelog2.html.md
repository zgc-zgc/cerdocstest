<!DOCTYPE html><html class="writer-html5" lang="en" data-content_root="../../../"><head>
  <meta charset="utf-8"><meta name="viewport" content="width=device-width, initial-scale=1">

  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Prover Release Notes — Certora Prover Documentation 0.0 documentation</title>
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
    <link rel="next" title="GUI Release Notes" href="gui_changelog.html">
    <link rel="prev" title="Changelogs" href="index.html"> 
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
<li class="toctree-l2"><a class="reference internal" href="../checking/index.html">Checking Specifications</a></li>
<li class="toctree-l2"><a class="reference internal" href="../cli/index.html">Certora Prover CLI</a></li>
<li class="toctree-l2"><a class="reference internal" href="../portal/using.html">Using the Certora Portal</a></li>
<li class="toctree-l2 current" aria-expanded="true"><a class="reference internal" href="index.html"><button class="toctree-expand" title="Open/close menu"></button>Changelogs</a><ul class="" aria-expanded="false">
<li class="toctree-l3 current" aria-expanded="true"><a class="reference internal current" href="#" aria-expanded="true"><button class="toctree-expand" title="Open/close menu"></button>Prover Release Notes</a><ul>
<li class="toctree-l4"><a class="reference internal" href="#april-10-2025">7.28.0 (April 10, 2025)</a></li>
<li class="toctree-l4"><a class="reference internal" href="#mar-13-2025">7.26.0 (Mar 13, 2025)</a></li>
<li class="toctree-l4"><a class="reference internal" href="#feb-19-2025">7.25.2 (Feb 19, 2025)</a></li>
<li class="toctree-l4"><a class="reference internal" href="#jan-12-2025">7.22.2 (Jan 12, 2025)</a></li>
<li class="toctree-l4"><a class="reference internal" href="#december-12-2024">7.21.1 (December 12, 2024)</a></li>
<li class="toctree-l4"><a class="reference internal" href="#november-20-2024">7.20.1 (November 20, 2024)</a></li>
<li class="toctree-l4"><a class="reference internal" href="#october-8-2024">7.17.2 (October 8, 2024)</a></li>
<li class="toctree-l4"><a class="reference internal" href="#september-2-2024">7.14.2 (September 2, 2024)</a></li>
<li class="toctree-l4"><a class="reference internal" href="#july-25-2024">7.10.1 (July 25, 2024)</a></li>
<li class="toctree-l4"><a class="reference internal" href="#may-15-2024">7.6.3 (May 15, 2024)</a></li>
<li class="toctree-l4"><a class="reference internal" href="#april-11-2024">7.3.0 (April 11, 2024)</a></li>
<li class="toctree-l4"><a class="reference internal" href="#march-15-2024">7.0.7 (March 15, 2024)</a></li>
<li class="toctree-l4"><a class="reference internal" href="#february-2-2024">6.3.1 (February 2, 2024)</a></li>
<li class="toctree-l4"><a class="reference internal" href="#january-11-2024">6.1.3 (January 11, 2024)</a></li>
<li class="toctree-l4"><a class="reference internal" href="#november-21-2023">5.0.5 (November 21, 2023)</a></li>
<li class="toctree-l4"><a class="reference internal" href="#september-26-2023">4.13.1 (September 26, 2023)</a></li>
<li class="toctree-l4"><a class="reference internal" href="#september-17-2023">4.12.1 (September 17, 2023)</a></li>
<li class="toctree-l4"><a class="reference internal" href="#august-21-2023">4.10.1 (August 21, 2023)</a></li>
<li class="toctree-l4"><a class="reference internal" href="#august-13-2023">4.8.0 (August 13, 2023)</a></li>
<li class="toctree-l4"><a class="reference internal" href="#july-15-2023">4.5.1 (July 15, 2023)</a></li>
<li class="toctree-l4"><a class="reference internal" href="#july-2-2023">4.3.1 (July 2, 2023)</a></li>
<li class="toctree-l4"><a class="reference internal" href="#june-7-2023-cvl-2">4.0.5 (June 7, 2023) CVL 2</a></li>
</ul>
</li>
<li class="toctree-l3"><a class="reference internal" href="gui_changelog.html">GUI Release Notes</a></li>
</ul>
</li>
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
          <li class="breadcrumb-item"><a href="index.html">Changelogs</a></li>
      <li class="breadcrumb-item active">Prover Release Notes</li>
      <li class="wy-breadcrumbs-aside">
            <a href="../../../_sources/docs/prover/changelog/prover_changelog.md.txt" rel="nofollow"> View page source</a>
      </li>
  </ul>
  <hr>
</div>
          <div role="main" class="document" itemscope="itemscope" itemtype="http://schema.org/Article">
           <div itemprop="articleBody">
             
  <section id="prover-release-notes">
<span id="id1"></span><h1><a class="toc-backref" href="#id66" role="doc-backlink">Prover Release Notes</a><a class="headerlink" href="#prover-release-notes" title="Link to this heading"></a></h1>
<nav class="contents" id="contents">
<p class="topic-title">Contents</p>
<ul class="simple">
<li><p><a class="reference internal" href="#prover-release-notes" id="id66">Prover Release Notes</a></p>
<ul>
<li><p><a class="reference internal" href="#april-10-2025" id="id67">7.28.0 (April 10, 2025)</a></p>
<ul>
<li><p><a class="reference internal" href="#rule-report" id="id68">Rule Report</a></p></li>
<li><p><a class="reference internal" href="#cvlr" id="id69">CVLR</a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#mar-13-2025" id="id70">7.26.0 (Mar 13, 2025)</a></p>
<ul>
<li><p><a class="reference internal" href="#id2" id="id71">Rule Report</a></p></li>
<li><p><a class="reference internal" href="#cvl" id="id72">CVL</a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#feb-19-2025" id="id73">7.25.2 (Feb 19, 2025)</a></p>
<ul>
<li><p><a class="reference internal" href="#id3" id="id74">CVL</a></p></li>
<li><p><a class="reference internal" href="#prover" id="id75">Prover</a></p></li>
<li><p><a class="reference internal" href="#cli" id="id76">CLI</a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#jan-12-2025" id="id77">7.22.2 (Jan 12, 2025)</a></p>
<ul>
<li><p><a class="reference internal" href="#id4" id="id78">Rule Report</a></p></li>
<li><p><a class="reference internal" href="#dashboard" id="id79">Dashboard</a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#december-12-2024" id="id80">7.21.1 (December 12, 2024)</a></p></li>
<li><p><a class="reference internal" href="#november-20-2024" id="id81">7.20.1 (November 20, 2024)</a></p>
<ul>
<li><p><a class="reference internal" href="#id5" id="id82">CVL</a></p></li>
<li><p><a class="reference internal" href="#id6" id="id83">Rule Report</a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#october-8-2024" id="id84">7.17.2 (October 8, 2024)</a></p>
<ul>
<li><p><a class="reference internal" href="#id7" id="id85">CVL</a></p></li>
<li><p><a class="reference internal" href="#id8" id="id86">CLI</a></p></li>
<li><p><a class="reference internal" href="#id9" id="id87">Rule Report</a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#september-2-2024" id="id88">7.14.2 (September 2, 2024)</a></p>
<ul>
<li><p><a class="reference internal" href="#id10" id="id89">CVL</a></p></li>
<li><p><a class="reference internal" href="#id11" id="id90">Rule Report</a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#july-25-2024" id="id91">7.10.1 (July 25, 2024)</a></p>
<ul>
<li><p><a class="reference internal" href="#id12" id="id92">CVL</a></p></li>
<li><p><a class="reference internal" href="#id13" id="id93">Rule Report</a></p></li>
<li><p><a class="reference internal" href="#performance" id="id94">Performance</a></p></li>
<li><p><a class="reference internal" href="#id14" id="id95">CLI</a></p></li>
<li><p><a class="reference internal" href="#misc" id="id96">Misc</a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#may-15-2024" id="id97">7.6.3 (May 15, 2024)</a></p>
<ul>
<li><p><a class="reference internal" href="#id15" id="id98">CVL</a></p></li>
<li><p><a class="reference internal" href="#id16" id="id99">Rule Report</a></p></li>
<li><p><a class="reference internal" href="#id17" id="id100">Performance</a></p></li>
<li><p><a class="reference internal" href="#id18" id="id101">CLI</a></p></li>
<li><p><a class="reference internal" href="#id19" id="id102">Misc.</a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#april-11-2024" id="id103">7.3.0 (April 11, 2024)</a></p>
<ul>
<li><p><a class="reference internal" href="#id20" id="id104">CVL</a></p></li>
<li><p><a class="reference internal" href="#id21" id="id105">Rule Report</a></p></li>
<li><p><a class="reference internal" href="#id22" id="id106">Performance</a></p></li>
<li><p><a class="reference internal" href="#id23" id="id107">CLI</a></p></li>
<li><p><a class="reference internal" href="#mutation-testing" id="id108">Mutation Testing</a></p></li>
<li><p><a class="reference internal" href="#id24" id="id109">Misc.</a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#march-15-2024" id="id110">7.0.7 (March 15, 2024)</a></p>
<ul>
<li><p><a class="reference internal" href="#id25" id="id111">CVL</a></p></li>
<li><p><a class="reference internal" href="#id26" id="id112">Rule Report</a></p></li>
<li><p><a class="reference internal" href="#static-analysis-and-performance" id="id113">Static analysis and Performance</a></p></li>
<li><p><a class="reference internal" href="#id27" id="id114">Mutation Testing</a></p></li>
<li><p><a class="reference internal" href="#id28" id="id115">CLI</a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#february-2-2024" id="id116">6.3.1 (February 2, 2024)</a></p>
<ul>
<li><p><a class="reference internal" href="#id29" id="id117">CVL</a></p></li>
<li><p><a class="reference internal" href="#call-trace-and-rule-report" id="id118">Call Trace and Rule Report</a></p></li>
<li><p><a class="reference internal" href="#id30" id="id119">Static analysis and Performance</a></p></li>
<li><p><a class="reference internal" href="#id31" id="id120">Misc</a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#january-11-2024" id="id121">6.1.3 (January 11, 2024)</a></p>
<ul>
<li><p><a class="reference internal" href="#id32" id="id122">CVL</a></p></li>
<li><p><a class="reference internal" href="#id33" id="id123">Performance</a></p></li>
<li><p><a class="reference internal" href="#call-trace" id="id124">Call Trace</a></p></li>
<li><p><a class="reference internal" href="#id34" id="id125">Mutation Testing</a></p></li>
<li><p><a class="reference internal" href="#id35" id="id126">Misc</a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#november-21-2023" id="id127">5.0.5 (November 21, 2023)</a></p>
<ul>
<li><p><a class="reference internal" href="#id36" id="id128">CVL</a></p></li>
<li><p><a class="reference internal" href="#id37" id="id129">Performance</a></p></li>
<li><p><a class="reference internal" href="#id38" id="id130">Misc</a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#september-26-2023" id="id131">4.13.1 (September 26, 2023)</a></p></li>
<li><p><a class="reference internal" href="#september-17-2023" id="id132">4.12.1 (September 17, 2023)</a></p>
<ul>
<li><p><a class="reference internal" href="#id39" id="id133">CVL</a></p></li>
<li><p><a class="reference internal" href="#id40" id="id134">Performance</a></p></li>
<li><p><a class="reference internal" href="#call-trace-rule-report" id="id135">Call Trace &amp; Rule Report</a></p></li>
<li><p><a class="reference internal" href="#id41" id="id136">CLI</a></p></li>
<li><p><a class="reference internal" href="#mutation-verification" id="id137">Mutation Verification</a></p></li>
<li><p><a class="reference internal" href="#equivalence-checker" id="id138">Equivalence Checker</a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#august-21-2023" id="id139">4.10.1 (August 21, 2023)</a></p>
<ul>
<li><p><a class="reference internal" href="#id42" id="id140">CVL</a></p></li>
<li><p><a class="reference internal" href="#id43" id="id141">Mutation Verification</a></p></li>
<li><p><a class="reference internal" href="#timeouts-and-performance" id="id142">Timeouts and performance</a></p></li>
<li><p><a class="reference internal" href="#linking" id="id143">Linking</a></p></li>
<li><p><a class="reference internal" href="#vyper" id="id144">Vyper</a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#august-13-2023" id="id145">4.8.0 (August 13, 2023)</a></p>
<ul>
<li><p><a class="reference internal" href="#new-features-and-enhancements" id="id146">New features and enhancements</a></p>
<ul>
<li><p><a class="reference internal" href="#id44" id="id147">CVL</a></p></li>
<li><p><a class="reference internal" href="#id45" id="id148">Call Trace and Rule Report</a></p></li>
<li><p><a class="reference internal" href="#id46" id="id149">Performance</a></p></li>
<li><p><a class="reference internal" href="#mutation-verifier" id="id150">Mutation Verifier</a></p></li>
<li><p><a class="reference internal" href="#id47" id="id151">Equivalence Checker</a></p></li>
<li><p><a class="reference internal" href="#id48" id="id152">CLI</a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#bug-fixes" id="id153">Bug fixes</a></p>
<ul>
<li><p><a class="reference internal" href="#id49" id="id154">CVL</a></p></li>
<li><p><a class="reference internal" href="#id50" id="id155">Call Trace</a></p></li>
<li><p><a class="reference internal" href="#id51" id="id156">Mutation Verifier</a></p></li>
<li><p><a class="reference internal" href="#id52" id="id157">Misc.</a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#other-improvements" id="id158">Other improvements</a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#july-15-2023" id="id159">4.5.1 (July 15, 2023)</a></p>
<ul>
<li><p><a class="reference internal" href="#new-features" id="id160">New features</a></p>
<ul>
<li><p><a class="reference internal" href="#id53" id="id161">CVL</a></p></li>
<li><p><a class="reference internal" href="#id54" id="id162">Call Trace</a></p></li>
<li><p><a class="reference internal" href="#multi-contract-handling" id="id163">Multi-contract handling</a></p></li>
<li><p><a class="reference internal" href="#id55" id="id164">Mutation Verifier</a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#id56" id="id165">Bug fixes</a></p>
<ul>
<li><p><a class="reference internal" href="#id57" id="id166">CVL</a></p></li>
<li><p><a class="reference internal" href="#id58" id="id167">Performance</a></p></li>
<li><p><a class="reference internal" href="#ux" id="id168">UX</a></p></li>
</ul>
</li>
</ul>
</li>
<li><p><a class="reference internal" href="#july-2-2023" id="id169">4.3.1 (July 2, 2023)</a></p>
<ul>
<li><p><a class="reference internal" href="#id59" id="id170">New features</a></p>
<ul>
<li><p><a class="reference internal" href="#id60" id="id171">CVL</a></p></li>
<li><p><a class="reference internal" href="#calltrace" id="id172">CallTrace</a></p></li>
<li><p><a class="reference internal" href="#summarization" id="id173">Summarization</a></p></li>
<li><p><a class="reference internal" href="#id61" id="id174">Performance</a></p></li>
<li><p><a class="reference internal" href="#id62" id="id175">Other improvements</a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#id63" id="id176">Bug fixes</a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#june-7-2023-cvl-2" id="id177">4.0.5 (June 7, 2023) CVL 2</a></p>
<ul>
<li><p><a class="reference internal" href="#breaking-changes" id="id178">Breaking changes</a></p></li>
<li><p><a class="reference internal" href="#id64" id="id179">New features</a></p></li>
<li><p><a class="reference internal" href="#id65" id="id180">Other improvements</a></p></li>
</ul>
</li>
</ul>
</li>
</ul>
</nav>
<section id="april-10-2025">
<h2><a class="toc-backref" href="#id67" role="doc-backlink">7.28.0 (April 10, 2025)</a><a class="headerlink" href="#april-10-2025" title="Link to this heading"></a></h2>
<section id="rule-report">
<h3><a class="toc-backref" href="#id68" role="doc-backlink">Rule Report</a><a class="headerlink" href="#rule-report" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[feat] Pointer analysis failures now display precise source locations for internal functions in the Global Notification tab. Includes function names and Jump-To-Source links.</p></li>
<li><p>[feat] The Live Statistics panel now supports per-call difficulty metrics for Solana jobs, aiding the identification of complex functions.</p></li>
</ul>
</section>
<section id="cvlr">
<h3><a class="toc-backref" href="#id69" role="doc-backlink">CVLR</a><a class="headerlink" href="#cvlr" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[feat] Solana jobs now support <code class="docutils literal notranslate"><span class="pre">multi_assert_check</span></code>. Each assertion in a rule is verified separately, enabling better counterexample coverage and a timeout mitigation strategy.</p></li>
<li><p>[feat] Solana jobs now support <code class="docutils literal notranslate"><span class="pre">rule_sanity</span> <span class="pre">basic</span></code>, which performs vacuity checks to help detect trivially true rules.</p></li>
</ul>
</section>
</section>
<section id="mar-13-2025">
<h2><a class="toc-backref" href="#id70" role="doc-backlink">7.26.0 (Mar 13, 2025)</a><a class="headerlink" href="#mar-13-2025" title="Link to this heading"></a></h2>
<section id="id2">
<h3><a class="toc-backref" href="#id71" role="doc-backlink">Rule Report</a><a class="headerlink" href="#id2" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[feat] The Live Statistics panel now supports difficulty information for internal function calls, expanding on the existing support for external and public functions.</p></li>
<li><p>[feat] Jump-To-Source (JTS) is now available for Rust (CVLR) external calls and <code class="docutils literal notranslate"><span class="pre">cvlr_satisfy</span></code>.</p></li>
</ul>
</section>
<section id="cvl">
<h3><a class="toc-backref" href="#id72" role="doc-backlink">CVL</a><a class="headerlink" href="#cvl" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[feat] Introduced the <code class="docutils literal notranslate"><span class="pre">executingContract</span></code> keyword, which can be used in the methods block. It refers to <code class="docutils literal notranslate"><span class="pre">address(this)</span></code> at the call site where the CVL summary is applied.</p></li>
</ul>
</section>
</section>
<section id="feb-19-2025">
<h2><a class="toc-backref" href="#id73" role="doc-backlink">7.25.2 (Feb 19, 2025)</a><a class="headerlink" href="#feb-19-2025" title="Link to this heading"></a></h2>
<section id="id3">
<h3><a class="toc-backref" href="#id74" role="doc-backlink">CVL</a><a class="headerlink" href="#id3" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[feat] CVL now supports native summation over ghost mapping variables with the new <code class="docutils literal notranslate"><span class="pre">sum</span></code> and <code class="docutils literal notranslate"><span class="pre">usum</span></code> keywords.</p></li>
</ul>
</section>
<section id="prover">
<h3><a class="toc-backref" href="#id75" role="doc-backlink">Prover</a><a class="headerlink" href="#prover" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[feat] The new <code class="docutils literal notranslate"><span class="pre">--auto_dispatcher</span></code> flag enables the Prover to automatically resolve unresolved calls by looking for matching functions in the scene and invoking them. If no matching function is found, the call will still result in a havoc.</p></li>
</ul>
</section>
<section id="cli">
<h3><a class="toc-backref" href="#id76" role="doc-backlink">CLI</a><a class="headerlink" href="#cli" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[feat] The new <code class="docutils literal notranslate"><span class="pre">--split_rules</span></code> flag allows users to specify rules that will run in separate instances, reducing the risk of timeouts. Each rule matching the provided patterns runs in its own job with dedicated resources, while all other rules execute in a separate job. The CLI provides a dashboard link to track the status of all generated jobs.</p></li>
</ul>
</section>
</section>
<section id="jan-12-2025">
<h2><a class="toc-backref" href="#id77" role="doc-backlink">7.22.2 (Jan 12, 2025)</a><a class="headerlink" href="#jan-12-2025" title="Link to this heading"></a></h2>
<section id="id4">
<h3><a class="toc-backref" href="#id78" role="doc-backlink">Rule Report</a><a class="headerlink" href="#id4" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[feat] Support for displaying numeric values in string, decimal, or hexadecimal formats in Call Trace and Variables tabs, with a dropdown to switch formats.</p></li>
<li><p>[feat] Added call traces and TAC dumps for sanity rules in Rule Report.</p></li>
</ul>
</section>
<section id="dashboard">
<h3><a class="toc-backref" href="#id79" role="doc-backlink">Dashboard</a><a class="headerlink" href="#dashboard" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[feat] Persist column configuration (display selection and width) across browser sessions on the Prover Dashboard, including between tabs and logins.</p></li>
</ul>
</section>
</section>
<section id="december-12-2024">
<h2><a class="toc-backref" href="#id80" role="doc-backlink">7.21.1 (December 12, 2024)</a><a class="headerlink" href="#december-12-2024" title="Link to this heading"></a></h2>
<p>Various bug fixes and performance improvements.</p>
</section>
<section id="november-20-2024">
<h2><a class="toc-backref" href="#id81" role="doc-backlink">7.20.1 (November 20, 2024)</a><a class="headerlink" href="#november-20-2024" title="Link to this heading"></a></h2>
<section id="id5">
<h3><a class="toc-backref" href="#id82" role="doc-backlink">CVL</a><a class="headerlink" href="#id5" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[feat] Certora’s Foundry Integration lets you run Foundry fuzz tests as formal verification tests. If you already use forge test, you can leverage this integration to formally verify your tests or find counterexamples where they fail. Unlike fuzzing, formal verification provides guarantees for all inputs, not just randomized ones. Note that this integration is in alpha version and requires some CVL configuration.</p></li>
</ul>
</section>
<section id="id6">
<h3><a class="toc-backref" href="#id83" role="doc-backlink">Rule Report</a><a class="headerlink" href="#id6" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[feat] The Call Trace received a re-design. As part of the re-design, the Call Trace highlights values the Prover found to generate the counter example as gray boxes with tooltips that provides additional information of the semantics of the values. Alongside this change, we also updated the font of the Call Trace.</p></li>
<li><p>[feat] It’s now easier to navigate to the Call Trace for a rule as the rule tree automatically opens nodes that contain only a single child.</p></li>
<li><p>[feat] Within the Call Trace, we added support for assignments to and loads from Solidity variables, structs and arrays. For assignments to primitive types the Call Trace also displays the assigned value.</p></li>
<li><p>[feat] Prover flags listed in the configuration tab of the rule report now link to their documentation.</p></li>
</ul>
</section>
</section>
<section id="october-8-2024">
<h2><a class="toc-backref" href="#id84" role="doc-backlink">7.17.2 (October 8, 2024)</a><a class="headerlink" href="#october-8-2024" title="Link to this heading"></a></h2>
<section id="id7">
<h3><a class="toc-backref" href="#id85" role="doc-backlink">CVL</a><a class="headerlink" href="#id7" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[feat] A function can be called on a CVL variable of type address directly. In the following rule, the function <code class="docutils literal notranslate"><span class="pre">balanceOf</span></code> will be called on all contracts that define <code class="docutils literal notranslate"><span class="pre">balanceOf</span></code>:</p></li>
</ul>
<div class="highlight-default notranslate"><div class="highlight"><pre id="codecell0"><span></span>    <span class="n">env</span> <span class="n">e</span><span class="p">;</span>
    <span class="n">address</span> <span class="n">a</span><span class="p">;</span>
    <span class="k">assert</span> <span class="n">a</span><span class="o">.</span><span class="n">balanceOf</span><span class="p">(</span><span class="n">e</span><span class="p">)</span> <span class="o">&gt;</span> <span class="mi">0</span><span class="p">;</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell0">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>If no contract with such a function exists, a <code class="docutils literal notranslate"><span class="pre">require(false)</span></code> will be inserted, which may cause a vacuity.</p>
<ul class="simple">
<li><p>[feat] The Prover now supports verifying code called via proxy contracts. You can specify <code class="docutils literal notranslate"><span class="pre">extension_contracts</span></code> in the <code class="docutils literal notranslate"><span class="pre">.conf</span></code> file to define which contracts are being delegate-called by the proxy.</p></li>
<li><p>[bugfix] The <code class="docutils literal notranslate"><span class="pre">--rule</span></code> filtering now applies also to built-in rules.</p></li>
</ul>
</section>
<section id="id8">
<h3><a class="toc-backref" href="#id86" role="doc-backlink">CLI</a><a class="headerlink" href="#id8" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[feat] <code class="docutils literal notranslate"><span class="pre">prover_args</span></code> will now be validated locally before submitting the job to the cloud.</p></li>
<li><p>[deprecation] The <code class="docutils literal notranslate"><span class="pre">typechecker_args</span></code> option has been removed. Use the new Python CLI flag <code class="docutils literal notranslate"><span class="pre">--allow_solidity_calls_in_quantifiers</span></code> to allow Solidity calls in quantifiers.</p></li>
<li><p>[deprecation] The <code class="docutils literal notranslate"><span class="pre">--prover_args</span></code> flag  <code class="docutils literal notranslate"><span class="pre">-adaptiveSolverConfig</span> <span class="pre">false</span></code> was deprecated. The flag was mainly used in combination with <code class="docutils literal notranslate"><span class="pre">-smt_useNIA</span></code> true to run NIA solvers only. Instead, use: <code class="docutils literal notranslate"><span class="pre">--prover_args</span> <span class="pre">"-backendStrategy</span> <span class="pre">singleRace</span> <span class="pre">-smt_useLIA</span> <span class="pre">false</span> <span class="pre">-smt_useNIA</span> <span class="pre">true"</span></code>.</p></li>
</ul>
</section>
<section id="id9">
<h3><a class="toc-backref" href="#id87" role="doc-backlink">Rule Report</a><a class="headerlink" href="#id9" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[feat] Additional jump-to-source buttons were added to the Global Notifications, and some existing buttons were corrected. Specifically, buttons for these types of warnings were targeted: PTA failures, optimistic summary fallback fails, <code class="docutils literal notranslate"><span class="pre">InternalFuncMiss</span></code>, storage analysis failures, memory partitioning failures, and <code class="docutils literal notranslate"><span class="pre">StorageSplitter</span></code>.</p></li>
<li><p>[feat] Rule progress indicator: The progress of individual rules will be displayed in the tree view. Each node in the rule tree shows how many children have been completed already.</p></li>
</ul>
</section>
</section>
<section id="september-2-2024">
<h2><a class="toc-backref" href="#id88" role="doc-backlink">7.14.2 (September 2, 2024)</a><a class="headerlink" href="#september-2-2024" title="Link to this heading"></a></h2>
<section id="id10">
<h3><a class="toc-backref" href="#id89" role="doc-backlink">CVL</a><a class="headerlink" href="#id10" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[feat] Functions can now be called on address-typed variables, allowing methods to dispatch on all contracts that implement the specified function.</p></li>
<li><p>[feat] Added a new <code class="docutils literal notranslate"><span class="pre">ASSERT_FALSE</span></code> summary type to assert that a function call to the summarized function should never occur.</p></li>
<li><p>[feat] Introduced new syntax for summarizing unresolved calls with dispatch lists, offering more precise control over which functions are inlined for unresolved calls. The old syntax remains available but now triggers a deprecation warning.</p></li>
<li><p>[feat] Added <code class="docutils literal notranslate"><span class="pre">nativeCodesize</span></code>, enabling direct access to the result of the <code class="docutils literal notranslate"><span class="pre">extcodesize</span></code> instruction from CVL. It functions similarly to <code class="docutils literal notranslate"><span class="pre">nativeBalances</span></code> in terms of blockchain state comparison and manipulation.</p></li>
<li><p>[bugfix] Hooks are no longer inlined on the <code class="docutils literal notranslate"><span class="pre">reset_storage</span></code> command. This change may affect “induction base” cases for invariant rules that previously relied on implicit hook inlining.</p></li>
<li><p>[bugfix] Explicit casting to <code class="docutils literal notranslate"><span class="pre">mathint</span></code> is no longer required when comparing the result of an arithmetic operation with a non-<code class="docutils literal notranslate"><span class="pre">mathint</span></code> value. Non-<code class="docutils literal notranslate"><span class="pre">mathint</span></code> values are now implicitly cast to <code class="docutils literal notranslate"><span class="pre">mathint</span></code>.</p></li>
</ul>
</section>
<section id="id11">
<h3><a class="toc-backref" href="#id90" role="doc-backlink">Rule Report</a><a class="headerlink" href="#id11" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[feat] Global Notifications New UI</p></li>
</ul>
</section>
</section>
<section id="july-25-2024">
<h2><a class="toc-backref" href="#id91" role="doc-backlink">7.10.1 (July 25, 2024)</a><a class="headerlink" href="#july-25-2024" title="Link to this heading"></a></h2>
<section id="id12">
<h3><a class="toc-backref" href="#id92" role="doc-backlink">CVL</a><a class="headerlink" href="#id12" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[bugfix] Make builtin sanity rule also check auto-generated assertions such as unwinding loop unroll assertions.</p></li>
<li><p>[feat] <code class="docutils literal notranslate"><span class="pre">DISPATCHER(true)</span></code> summaries will hard fail on type checking if there is no method in the scene that should be dispatched to.</p></li>
<li><p>[feat] Adding a warning when a contract alias conflicts with a contract in the scene.</p></li>
<li><p>[feat] View functions of contracts <em>other</em> than the current contract are now also excluded when checking invariants.</p></li>
<li><p>[feat] It’s now possible to compare strings and bytes natively in CVL.</p></li>
<li><p>[feat] The dispatcher list summary now will also inline the fallback handler when using the <code class="docutils literal notranslate"><span class="pre">Contract._</span></code> syntax.</p></li>
<li><p>[feat] Transient storage support in invariants.</p></li>
<li><p>[feat] It’s now possible to also write CVL summaries that include structs.</p></li>
<li><p>[syntax check] The usage of the keyword <code class="docutils literal notranslate"><span class="pre">lastReverted</span></code> led to incorrect specifications in cases when the last call was not using the <code class="docutils literal notranslate"><span class="pre">@withrevert</span></code> syntax. During type checking, the CVL parser will now fail and report an error.</p></li>
<li><p>[feat] The dispatcher summary <code class="docutils literal notranslate"><span class="pre">DISPATCHER(false|true)</span></code> has been enhanced to also include fallbacks.</p></li>
<li><p>[feature] There are two new keywords <code class="docutils literal notranslate"><span class="pre">strong</span></code> and <code class="docutils literal notranslate"><span class="pre">weak</span></code> as prefix for <code class="docutils literal notranslate"><span class="pre">invariant</span></code>. A <code class="docutils literal notranslate"><span class="pre">strong</span> <span class="pre">invariant</span></code> is a regular <code class="docutils literal notranslate"><span class="pre">invariant</span></code> that will be additionally <code class="docutils literal notranslate"><span class="pre">asserted</span></code> before a havoc’d external unresolved call and <code class="docutils literal notranslate"><span class="pre">assumed</span></code> afterwards. <code class="docutils literal notranslate"><span class="pre">weak</span> <span class="pre">invariant</span></code> is an alias for <code class="docutils literal notranslate"><span class="pre">invariant</span></code> explicitly stating that the <code class="docutils literal notranslate"><span class="pre">invariant</span></code> will only hold pre- and post-method execution.</p></li>
<li><p>[feature] It’s now possible to write rules for Solidity functions whose name matches a CVL keyword.</p></li>
</ul>
</section>
<section id="id13">
<h3><a class="toc-backref" href="#id93" role="doc-backlink">Rule Report</a><a class="headerlink" href="#id13" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[feat] Ensuring storage snippets are shown even if there is no storage layout information.</p></li>
<li><p>[feat] Return statements of CVL functions are now shown in the call trace.</p></li>
<li><p>[feature] Model values for CVL-declared strings are now shown in the Variables Tab of the report.</p></li>
<li><p>[feature] Sanity rules are now explicitly shown as independent nodes in the rule view.</p></li>
<li><p>[feature] The browser tab icon in the rule report now displays the job execution status of a run: blue for running, green when the job has successfully been completed, and red when the job is halted or ends in an error state.</p></li>
<li><p>[feature] Improved display of ghost variable reads in the call trace.</p></li>
</ul>
</section>
<section id="performance">
<h3><a class="toc-backref" href="#id94" role="doc-backlink">Performance</a><a class="headerlink" href="#performance" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>The <code class="docutils literal notranslate"><span class="pre">-prover_args</span></code> option <code class="docutils literal notranslate"><span class="pre">-smt_easy_LIA</span></code> is now set to <code class="docutils literal notranslate"><span class="pre">true</span></code> by default.</p></li>
</ul>
</section>
<section id="id14">
<h3><a class="toc-backref" href="#id95" role="doc-backlink">CLI</a><a class="headerlink" href="#id14" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[feature] The <code class="docutils literal notranslate"><span class="pre">—method</span></code> flag now also accepts a list of methods.</p></li>
</ul>
</section>
<section id="misc">
<h3><a class="toc-backref" href="#id96" role="doc-backlink">Misc</a><a class="headerlink" href="#misc" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>Supporting precise bytemap semantics (unaligned reads, overlapping, etc.). Disabled by default, can be enabled via <code class="docutils literal notranslate"><span class="pre">-prover_args</span> <span class="pre">"-smt_preciseBytemaps</span> <span class="pre">true"</span></code>.</p></li>
</ul>
</section>
</section>
<section id="may-15-2024">
<h2><a class="toc-backref" href="#id97" role="doc-backlink">7.6.3 (May 15, 2024)</a><a class="headerlink" href="#may-15-2024" title="Link to this heading"></a></h2>
<section id="id15">
<h3><a class="toc-backref" href="#id98" role="doc-backlink">CVL</a><a class="headerlink" href="#id15" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[feat] Allow the use of contract aliases (<code class="docutils literal notranslate"><span class="pre">using</span> <span class="pre">ERC20</span> <span class="pre">as</span> <span class="pre">token</span></code>) that were defined in the imported spec files.</p></li>
<li><p>[feat] Can use <code class="docutils literal notranslate"><span class="pre">filtered</span></code> expressions for <code class="docutils literal notranslate"><span class="pre">builtin</span></code> rules</p></li>
<li><p>[bugfix] Always run <code class="docutils literal notranslate"><span class="pre">envfree</span></code> checks, even if rule filters are applied</p></li>
<li><p>[bugfix] <code class="docutils literal notranslate"><span class="pre">envfree</span></code> will be checked on the code after linking</p></li>
</ul>
</section>
<section id="id16">
<h3><a class="toc-backref" href="#id99" role="doc-backlink">Rule Report</a><a class="headerlink" href="#id16" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[feat] Support jump-to-source for calls, local variables, and storage accesses</p></li>
<li><p>[feat] Show structs passed to CVL functions in the call trace</p></li>
<li><p>[feat] Show loop statistics in the live difficulty tab</p></li>
<li><p>[feat] Show split-solving progress in live stats</p></li>
<li><p>[feat] Show a notification if there are unresolved calls that can be resolved with <code class="docutils literal notranslate"><span class="pre">--optimistic_fallback</span></code></p></li>
<li><p>[feat] Show more info on procedures with nonlinear operations</p></li>
<li><p>[UX] Prioritize <code class="docutils literal notranslate"><span class="pre">ERROR</span></code> states over other rule states</p></li>
</ul>
</section>
<section id="id17">
<h3><a class="toc-backref" href="#id100" role="doc-backlink">Performance</a><a class="headerlink" href="#id17" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[feat] The <code class="docutils literal notranslate"><span class="pre">-splitParallel</span></code> option will now enable the new parallel splitter</p></li>
</ul>
</section>
<section id="id18">
<h3><a class="toc-backref" href="#id101" role="doc-backlink">CLI</a><a class="headerlink" href="#id18" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[feat] Automatically set function-finder options depending on <code class="docutils literal notranslate"><span class="pre">solc</span></code> version and configuration</p></li>
<li><p>[feat] New option <code class="docutils literal notranslate"><span class="pre">--build_cache</span></code> for faster re-compilation of previously compiled Solidity code</p></li>
</ul>
</section>
<section id="id19">
<h3><a class="toc-backref" href="#id102" role="doc-backlink">Misc.</a><a class="headerlink" href="#id19" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[feat] Support for <code class="docutils literal notranslate"><span class="pre">MCOPY</span></code> EVM instruction</p></li>
</ul>
</section>
</section>
<section id="april-11-2024">
<h2><a class="toc-backref" href="#id103" role="doc-backlink">7.3.0 (April 11, 2024)</a><a class="headerlink" href="#april-11-2024" title="Link to this heading"></a></h2>
<section id="id20">
<h3><a class="toc-backref" href="#id104" role="doc-backlink">CVL</a><a class="headerlink" href="#id20" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[feat] An option to make autofinders for internal functions less likely to cause compilation failures, <code class="docutils literal notranslate"><span class="pre">--use_memory_safe_autofinders</span></code></p></li>
<li><p>[feat] <a class="reference internal" href="../../cvl/methods.html#catch-unresolved-calls-entry"><span class="std std-ref">Dispatch-list summarization for calls with unresolved method identifiers</span></a></p></li>
<li><p>[feat] Preliminary support for <code class="docutils literal notranslate"><span class="pre">tload</span></code>, <code class="docutils literal notranslate"><span class="pre">tstore</span></code> operations in inline-assembly Solidity and EVM, along with <code class="docutils literal notranslate"><span class="pre">ALL_TLOAD</span></code> and <code class="docutils literal notranslate"><span class="pre">ALL_TSTORE</span></code> hooks, see <a class="reference internal" href="../../cvl/transient.html#transient-storage"><span class="std std-ref">Transient Storage</span></a> and <a class="reference internal" href="../../cvl/hooks.html#rawhooks"><span class="std std-ref">Hooking on all storage loads or stores</span></a></p></li>
<li><p>[feat] <a class="reference internal" href="../../cvl/expr.html#direct-immutable-access"><span class="std std-ref">Support direct access to immutables, including private immutables</span></a></p></li>
<li><p>[feat] grounding of quantifiers supported with direct storage access expressions</p></li>
<li><p>[feat] Support asterisk (*) wildcard in <code class="docutils literal notranslate"><span class="pre">--rule</span></code>, and a new option for <code class="docutils literal notranslate"><span class="pre">--exclude_rule</span></code>, see <a class="reference internal" href="../cli/options.html#exclude-rule"><span class="std std-ref">exclude_rule</span></a></p></li>
<li><p>[feat] Support using <code class="docutils literal notranslate"><span class="pre">requireInvariant</span></code> with unused invariants from imported contracts</p></li>
<li><p>[feat] Support <code class="docutils literal notranslate"><span class="pre">blobhash</span></code> instruction and opcode hooks</p></li>
<li><p>[bugfix] Fix <code class="docutils literal notranslate"><span class="pre">--address</span></code> setting of fixed addresses to contracts to reflect in counterexamples properly</p></li>
<li><p>[bugfix] Fixes to internal function detection</p></li>
<li><p>[bugfix] Fix issue when dealing with contract-types</p></li>
<li><p>[bugfix] Support multiple havoc-assuming statements inside a rule, hook, or function</p></li>
<li><p>[bugfix] Support unary minus in quantifier expressions</p></li>
<li><p>[bugfix] A helper option for detecting internal functions with Yul-optimizations enabled, <code class="docutils literal notranslate"><span class="pre">--finder_friendly_optimizer</span></code></p></li>
<li><p>[bugfix] A collection of fixes to internal function detection and summarization</p></li>
<li><p>[bugfix] Support of summarization in old code using patterns like MakerDAO’s <code class="docutils literal notranslate"><span class="pre">note</span></code> modifier, enabled with <code class="docutils literal notranslate"><span class="pre">--prover_args</span> <span class="pre">'-rewriteMSizeAllocations</span> <span class="pre">true'</span></code> (the Global Warnings tab will advise when it’s recommended to be enabled)</p></li>
</ul>
</section>
<section id="id21">
<h3><a class="toc-backref" href="#id105" role="doc-backlink">Rule Report</a><a class="headerlink" href="#id21" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[feat] Improved presentation of arrays and arrays’ length in the call trace</p></li>
<li><p>[bugfix] Do not show rules as verified if the sanity check timed-out</p></li>
<li><p>[UX] Show internal functions that could not be detected (and as a result, summarized) in the global problems view</p></li>
<li><p>[UX] Avoid showing redundant and irrelevant analysis failures</p></li>
</ul>
</section>
<section id="id22">
<h3><a class="toc-backref" href="#id106" role="doc-backlink">Performance</a><a class="headerlink" href="#id22" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[bugfix] Better safe math optimization for multiplication by constants</p></li>
<li><p>[bugfix] Fixes to new parallel splitter mode</p></li>
</ul>
</section>
<section id="id23">
<h3><a class="toc-backref" href="#id107" role="doc-backlink">CLI</a><a class="headerlink" href="#id23" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[feat] <a class="reference internal" href="../cli/options.html#compilation-steps-only"><span class="std std-ref">compilation_steps_only</span></a> option is exposed (runs only compilation and type checking)</p></li>
<li><p>[feat] <a class="reference internal" href="../cli/options.html#precise-bitwise-ops"><span class="std std-ref">precise_bitwise_ops</span></a> to easily enable bit-vector theory solvers
Mutation Testing</p></li>
</ul>
</section>
<section id="mutation-testing">
<h3><a class="toc-backref" href="#id108" role="doc-backlink">Mutation Testing</a><a class="headerlink" href="#mutation-testing" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[feat] Allow omitting the <code class="docutils literal notranslate"><span class="pre">--conf</span></code> flag to perform collection only</p></li>
<li><p>[bugfix] Fix root directory issue for mutated files in subdirectories</p></li>
<li><p>[bugfix] Rules that failed sanity during the run on the original code but capture mutants will not be ignored when computing caught mutants</p></li>
</ul>
</section>
<section id="id24">
<h3><a class="toc-backref" href="#id109" role="doc-backlink">Misc.</a><a class="headerlink" href="#id24" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[feat] Preliminary support for running the Prover on <code class="docutils literal notranslate"><span class="pre">.yul</span></code> contracts</p></li>
<li><p>[bugfix] Assume strictly monotonic increasing free memory pointer, to avoid counterexamples due to overflow in memory access</p></li>
</ul>
</section>
</section>
<section id="march-15-2024">
<h2><a class="toc-backref" href="#id110" role="doc-backlink">7.0.7 (March 15, 2024)</a><a class="headerlink" href="#march-15-2024" title="Link to this heading"></a></h2>
<section id="id25">
<h3><a class="toc-backref" href="#id111" role="doc-backlink">CVL</a><a class="headerlink" href="#id25" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[feat] <code class="docutils literal notranslate"><span class="pre">if</span></code> conditions in CVL must be wrapped with parenthesis. Namely, <code class="docutils literal notranslate"><span class="pre">if</span> <span class="pre">cond</span></code> is illegal, use <code class="docutils literal notranslate"><span class="pre">if</span> <span class="pre">(cond)</span></code></p></li>
<li><p>[feat] It is no longer needed to specify the <code class="docutils literal notranslate"><span class="pre">STORAGE</span></code> keyword for <code class="docutils literal notranslate"><span class="pre">Sload</span></code> and <code class="docutils literal notranslate"><span class="pre">Sstore</span></code> hooks. Please find-replace in your current specs!</p></li>
<li><p>[feat] The default summarization policy for wildcard external functions (e.g. <code class="docutils literal notranslate"><span class="pre">_.foo(..)</span> <span class="pre">=&gt;</span></code>) is <code class="docutils literal notranslate"><span class="pre">UNRESOLVED</span></code>, meaning that the summary will only apply to calls to <code class="docutils literal notranslate"><span class="pre">foo</span></code> whose target contract is unknown. If you wish to apply to all call sites of <code class="docutils literal notranslate"><span class="pre">foo</span></code>, including for properly linked contracts, write <code class="docutils literal notranslate"><span class="pre">_.foo(..)</span> <span class="pre">=&gt;</span> <span class="pre">some_summary</span> <span class="pre">ALL;</span></code></p></li>
<li><p>[feat] Allow ‘tuple like’ syntax for assignments, e.g. <code class="docutils literal notranslate"><span class="pre">(x,y)</span> <span class="pre">=</span> <span class="pre">foo();</span></code></p></li>
<li><p>[feat] Support <code class="docutils literal notranslate"><span class="pre">blobbasefee</span></code> variable in environment variables</p></li>
<li><p>[feat] <a class="reference internal" href="../../user-guide/out-of-resources/timeout.html#detect-candidates-for-summarization"><span class="std std-ref">Auto-summarization mode for heuristically expensive internal functions</span></a></p></li>
<li><p>[feat] Support hooking on length of dynamic storage arrays</p></li>
<li><p>[feat] <a class="reference internal" href="../../cvl/expr.html#struct-comparison"><span class="std std-ref">Support basic struct comparison</span></a></p></li>
<li><p>[bugfix] Wildcards properly constrained when assigned e.g. in summarization</p></li>
<li><p>[bugfix] Ensure cleanliness of CVL strings in the last word</p></li>
<li><p>[bugfix] Unlinked immutables are properly constrained to respect their types</p></li>
<li><p>[bugfix] Correct invariant handling of the base case rule for Vyper contracts</p></li>
<li><p>[bugfix] Fix to <code class="docutils literal notranslate"><span class="pre">viewReentrancy</span></code> builtin rule crash</p></li>
<li><p>[bugfix] Better type checking of quantified expressions with definitions</p></li>
<li><p>[bugfix] Fix direct storage access to an array of structs</p></li>
<li><p>[bugfix] Fix for internal summaries using user-defined value types</p></li>
</ul>
</section>
<section id="id26">
<h3><a class="toc-backref" href="#id112" role="doc-backlink">Rule Report</a><a class="headerlink" href="#id26" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[feat] Display array length in variables tab</p></li>
<li><p>[feat] Display array length in CVL to CVL function calls</p></li>
<li><p>[bugfix] No false match on Vyper constructors in invariants and parametric rules</p></li>
<li><p>[bugfix] Consistent rule ordering</p></li>
<li><p>[bugfix] Show message in report when <code class="docutils literal notranslate"><span class="pre">--prover_args</span></code> are incorrect</p></li>
</ul>
</section>
<section id="static-analysis-and-performance">
<h3><a class="toc-backref" href="#id113" role="doc-backlink">Static analysis and Performance</a><a class="headerlink" href="#static-analysis-and-performance" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[feat] Automatic full unrolling of copy loops (no need to set <code class="docutils literal notranslate"><span class="pre">-copyLoopUnroll</span></code> option)</p></li>
<li><p>[bugfix] Proper deduplication of libraries imported by different scene-level contracts</p></li>
<li><p>[bugfix] Fix returns of static arrays</p></li>
<li><p>[bugfix] make hashing of <code class="docutils literal notranslate"><span class="pre">encodePacked</span></code> <code class="docutils literal notranslate"><span class="pre">bytes</span></code> result deterministic when <code class="docutils literal notranslate"><span class="pre">-enableCopyLoopRewrites</span></code> is set to true</p></li>
<li><p>[bugfix] Source-based call resolution is disabled by default except for constructor methods. Can be re-enabled with <code class="docutils literal notranslate"><span class="pre">--prover_args</span> <span class="pre">'-enableSolidityBasedInlining</span> <span class="pre">true'</span></code></p></li>
</ul>
</section>
<section id="id27">
<h3><a class="toc-backref" href="#id114" role="doc-backlink">Mutation Testing</a><a class="headerlink" href="#id27" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[feat] Instead of running with 2 <code class="docutils literal notranslate"><span class="pre">conf</span></code> files, one for the Prover and one for mutation, now the mutation settings are stored in the Prover <code class="docutils literal notranslate"><span class="pre">conf</span></code> under the key mutations</p></li>
<li><p>[feat] Relative paths to files to mutate are not relative to the mutation conf, but relative to current working directory</p></li>
<li><p>[feat] Nicer help message for <code class="docutils literal notranslate"><span class="pre">certoraMutate</span></code></p></li>
<li><p>[bugfix] Minor mutation testing <code class="docutils literal notranslate"><span class="pre">csv</span></code> output</p></li>
<li><p>[bugfix] Default to optimistically running all mutants, not waiting for the original run</p></li>
<li><p>[bugfix] Improved error messages for manual mutations</p></li>
</ul>
</section>
<section id="id28">
<h3><a class="toc-backref" href="#id115" role="doc-backlink">CLI</a><a class="headerlink" href="#id28" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[feat] Instead of <code class="docutils literal notranslate"><span class="pre">--prover_args</span> <span class="pre">'-optimisticFallback</span> <span class="pre">true'</span></code> use <code class="docutils literal notranslate"><span class="pre">--optimistic_fallback</span></code></p></li>
<li><p>[feat] Instead of <code class="docutils literal notranslate"><span class="pre">--prover_args</span> <span class="pre">'-contractRecursionLimit</span> <span class="pre">N'</span></code> use <code class="docutils literal notranslate"><span class="pre">--contract_recursion_limit</span> <span class="pre">N</span></code>, and a new flag <code class="docutils literal notranslate"><span class="pre">--optimistic_contract_recursion</span></code></p></li>
<li><p>[feat] New option <code class="docutils literal notranslate"><span class="pre">--compiler_map</span></code> behaving exactly like <code class="docutils literal notranslate"><span class="pre">--solc_map</span></code></p></li>
<li><p>[bugfix] Fix to <code class="docutils literal notranslate"><span class="pre">--address</span></code> when given without <code class="docutils literal notranslate"><span class="pre">0x</span></code> prefix</p></li>
</ul>
</section>
</section>
<section id="february-2-2024">
<h2><a class="toc-backref" href="#id116" role="doc-backlink">6.3.1 (February 2, 2024)</a><a class="headerlink" href="#february-2-2024" title="Link to this heading"></a></h2>
<section id="id29">
<h3><a class="toc-backref" href="#id117" role="doc-backlink">CVL</a><a class="headerlink" href="#id29" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[feat] <a class="reference internal" href="../../cvl/cvl2/changes.html#address-casting"><span class="std std-ref">Casting addresses to bytes32</span></a></p></li>
<li><p>[feat] <a class="reference internal" href="../../cvl/expr.html#ecrecover"><span class="std std-ref">ECRecover</span></a> builtin support</p></li>
<li><p>[feat] Optimistically assume the <code class="docutils literal notranslate"><span class="pre">extcodesize</span></code> is positive for calls that are summarized and with a non-<code class="docutils literal notranslate"><span class="pre">HAVOC</span></code> summary. This behavior can be disabled with <code class="docutils literal notranslate"><span class="pre">--prover_args</span> <span class="pre">'optimisticExtcodesize</span> <span class="pre">false'</span></code></p></li>
<li><p>[feat] Support direct storage access in quantifiers and axioms</p></li>
<li><p>[bugfix] Implication, bi-implication and ternary conditional operators are right-associative</p></li>
<li><p>[bugfix] <a class="reference internal" href="../../cvl/types.html#env"><span class="std std-ref">Fully support additional environment fields</span></a>. Namely, for <code class="docutils literal notranslate"><span class="pre">env</span> <span class="pre">e</span></code>, one can access <code class="docutils literal notranslate"><span class="pre">e.block.basefee</span></code>, <code class="docutils literal notranslate"><span class="pre">e.block.coinbase</span></code>, <code class="docutils literal notranslate"><span class="pre">e.block.difficulty</span></code>, <code class="docutils literal notranslate"><span class="pre">e.block.gaslimit</span></code> and <code class="docutils literal notranslate"><span class="pre">e.tx.origin</span></code></p></li>
<li><p>[bugfix] Properly enforce bounds on enums accessed using direct storage access</p></li>
<li><p>[bugfix] Fix a bug with structs being passed to summaries and not preserving their fields’ values</p></li>
<li><p>[bugfix] Avoid hook inlining due to direct storage access</p></li>
<li><p>[bugfix] Type checker will error in presence of non-boolean expressions in quantifiers’ bodies</p></li>
<li><p>[UX] Emit a global error in rule report if 0 rules are provided in the spec</p></li>
<li><p>[UX] Cast assertions in CVL are treated like regular user-provided assertions</p></li>
<li><p>[UX] Warn about, and ignore, unused <code class="docutils literal notranslate"><span class="pre">method</span></code> arguments</p></li>
<li><p>[UX] Prevent calling library functions from CVL</p></li>
</ul>
</section>
<section id="call-trace-and-rule-report">
<h3><a class="toc-backref" href="#id118" role="doc-backlink">Call Trace and Rule Report</a><a class="headerlink" href="#call-trace-and-rule-report" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[feat] Add presentation of direct storage reads and direct storage havocs, including showing the updates in the Storage State</p></li>
<li><p>[feat] When the user provided no assertion message, show the assert condition</p></li>
<li><p>[bugfix] More refined handling of branch snippets within loop iterations</p></li>
<li><p>[bugfix] Ensure we get the correct TAC dump link</p></li>
<li><p>[UX] Improved messages for assertions in builtin rules</p></li>
<li><p>[UX] New presentation for invariants</p></li>
<li><p>[UX] Branch snippets are now flattened, can be made hierarchical using <code class="docutils literal notranslate"><span class="pre">--prover_args</span> <span class="pre">'-flattenBranchesInCallTrace</span> <span class="pre">false'</span></code></p></li>
</ul>
</section>
<section id="id30">
<h3><a class="toc-backref" href="#id119" role="doc-backlink">Static analysis and Performance</a><a class="headerlink" href="#id30" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[feat] <code class="docutils literal notranslate"><span class="pre">abi.encodeCall</span></code> calls will be considered as copy-loops, thus will not require a higher <code class="docutils literal notranslate"><span class="pre">--loop_iter</span></code> if we enable the following option: <code class="docutils literal notranslate"><span class="pre">--prover_args</span> <span class="pre">'-enableCopyLoopRewrites</span> <span class="pre">true'</span></code></p></li>
<li><p>[feat] Better performance on last assertions in a rule if <code class="docutils literal notranslate"><span class="pre">--prover_args</span> <span class="pre">'-calltraceFreeOpt</span> <span class="pre">true'</span></code> is enabled</p></li>
</ul>
</section>
<section id="id31">
<h3><a class="toc-backref" href="#id120" role="doc-backlink">Misc</a><a class="headerlink" href="#id31" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[feat] Support Vyper v0.3.10</p></li>
<li><p>[bugfix] Various bug fixes to improve stability of the Prover (crashes, static analysis, and SMT solving)</p></li>
<li><p>[bugfix] Better support of importing user-defined types from Solidity imports even if they are not given in a consistent fashion by <code class="docutils literal notranslate"><span class="pre">solc</span></code></p></li>
</ul>
</section>
</section>
<section id="january-11-2024">
<h2><a class="toc-backref" href="#id121" role="doc-backlink">6.1.3 (January 11, 2024)</a><a class="headerlink" href="#january-11-2024" title="Link to this heading"></a></h2>
<section id="id32">
<h3><a class="toc-backref" href="#id122" role="doc-backlink">CVL</a><a class="headerlink" href="#id32" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[feat] Rules can now use both <code class="docutils literal notranslate"><span class="pre">satisfy</span></code> and <code class="docutils literal notranslate"><span class="pre">assert</span></code> statements together</p></li>
<li><p>[feat] An option for checking <code class="docutils literal notranslate"><span class="pre">satisfy</span></code> statements one-by-one instead of depending on previous <code class="docutils literal notranslate"><span class="pre">satisfy</span></code>-s, enabled with <code class="docutils literal notranslate"><span class="pre">--independent_satisfy</span></code></p></li>
<li><p>[feat] <a class="reference internal" href="../../cvl/ghosts.html#persistent-ghosts"><span class="std std-ref">Ghosts vs. persistent ghosts</span></a></p></li>
<li><p>[feat] support <code class="docutils literal notranslate"><span class="pre">selector</span></code> keyword in <code class="docutils literal notranslate"><span class="pre">CALL</span></code>-like hooks that can be compared to function selectors</p></li>
<li><p>[feat] New builtin function for hashing <code class="docutils literal notranslate"><span class="pre">keccak256</span></code> in CVL</p></li>
<li><p>[feat] Support method parameter filters when invariants are imported with <code class="docutils literal notranslate"><span class="pre">use</span></code></p></li>
<li><p>[feat] New options <a class="reference internal" href="../cli/options.html#optimistic-summary-recursion"><span class="std std-ref">optimistic_summary_recursion</span></a> and <a class="reference internal" href="../cli/options.html#summary-recursion-limit"><span class="std std-ref">summary_recursion_limit</span></a>.</p></li>
<li><p>[bugfix] improved error messages for hooks</p></li>
<li><p>[bugfix] Fix compile time checks for ghosts mappings axioms and bad CVL function calls therein</p></li>
<li><p>[bugfix] Make <code class="docutils literal notranslate"><span class="pre">CONSTANT</span></code> summaries of internal functions consistent</p></li>
<li><p>[bugfix] Allow Solidity struct fields named hook</p></li>
<li><p>[bugfix] Fix <code class="docutils literal notranslate"><span class="pre">to_bytes</span></code> in quantifiers</p></li>
<li><p>[bugfix] Better error message on struct decode failures</p></li>
<li><p>[bugfix] Proper typing of sub-expressions of bitwise shift operations within quantifiers</p></li>
<li><p>[UX] Nicer error messages for invalid use of <code class="docutils literal notranslate"><span class="pre">max_*</span></code> constants and hex literals</p></li>
<li><p>[UX] Sanity builtin rule now succeeds when the sanity check succeeds (using <code class="docutils literal notranslate"><span class="pre">satisfy</span></code> under the hood) (note this can swap the expected result if you use the builtin sanity rule often, but you no longer have to interpret a “violated” result as the good one)</p></li>
</ul>
</section>
<section id="id33">
<h3><a class="toc-backref" href="#id123" role="doc-backlink">Performance</a><a class="headerlink" href="#id33" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[feat] New optimization analysis. It can be configured to be more or less aggressive with the option <code class="docutils literal notranslate"><span class="pre">--prover_args</span> <span class="pre">'-intervals_rewriter</span> <span class="pre">INT'</span></code></p></li>
<li><p>[feat] New flag for better performance: <code class="docutils literal notranslate"><span class="pre">--prover_args</span> <span class="pre">'-enableCopyLoopRewrites</span> <span class="pre">true'</span></code>  - replaces copy loop code blocks with a single copy command. Decreases problem size and obviates loop unrolling for copy loops (i.e., more sound)</p></li>
<li><p>[feat] New flag for better performance: <code class="docutils literal notranslate"><span class="pre">--prover_args</span> <span class="pre">'-enableAggressivePartitionPruning</span> <span class="pre">true'</span></code> - for Solidity code that often manipulates - dynamic objects in memory</p></li>
</ul>
</section>
<section id="call-trace">
<h3><a class="toc-backref" href="#id124" role="doc-backlink">Call Trace</a><a class="headerlink" href="#call-trace" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[feat] Show branch source information (can be disabled with <code class="docutils literal notranslate"><span class="pre">--prover_args</span> <span class="pre">'-enableConditionalSnippets</span> <span class="pre">false'</span></code>)</p></li>
<li><p>[bugfix] Fix return value display for ghost reads</p></li>
</ul>
</section>
<section id="id34">
<h3><a class="toc-backref" href="#id125" role="doc-backlink">Mutation Testing</a><a class="headerlink" href="#id34" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[feat] Generate mutation configuration automatically</p></li>
<li><p>[UX] Expose errors emitted by Gambit</p></li>
<li><p>[UX] <code class="docutils literal notranslate"><span class="pre">certoraMutate</span></code> now uses <code class="docutils literal notranslate"><span class="pre">.mconf</span></code> files instead of <code class="docutils literal notranslate"><span class="pre">.conf</span></code></p></li>
</ul>
</section>
<section id="id35">
<h3><a class="toc-backref" href="#id126" role="doc-backlink">Misc</a><a class="headerlink" href="#id35" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[feat] enable the max constant loop unroll factor inferred with <code class="docutils literal notranslate"><span class="pre">--prover_args</span> <span class="pre">'-loopUnrollBoundGuessUpperLimit</span> <span class="pre">INT</span></code></p></li>
<li><p>[bugfix] Vyper fixes for static arrays, xor patterns, <code class="docutils literal notranslate"><span class="pre">ABI</span></code> fetching in old versions</p></li>
<li><p>[bugfix] Support for some older versions of Vyper (0.3.7 and earlier)</p></li>
<li><p>[bugfix] Better decompilation for try/catch in a loop</p></li>
<li><p>[bugfix] Fix to false negative tautology check</p></li>
<li><p>[bugfix] Better retry mechanism for job-submission by <code class="docutils literal notranslate"><span class="pre">certora-cli</span></code></p></li>
<li><p>[bugfix] Align with EVM by setting <code class="docutils literal notranslate"><span class="pre">x/0</span> <span class="pre">=</span> <span class="pre">0</span></code></p></li>
<li><p>[bugfix] Fix storage analysis when Solidity optimizer is enabled</p></li>
<li><p>[bugfix] Fixes in handling <code class="docutils literal notranslate"><span class="pre">solc</span></code>’s <code class="docutils literal notranslate"><span class="pre">--via-ir</span></code> optimizer mode</p></li>
<li><p>[UX] Fix wait time in CLI to 2:30 hours, to account for possible long queue times in CI runs</p></li>
</ul>
</section>
</section>
<section id="november-21-2023">
<h2><a class="toc-backref" href="#id127" role="doc-backlink">5.0.5 (November 21, 2023)</a><a class="headerlink" href="#november-21-2023" title="Link to this heading"></a></h2>
<p>Please find a list of the main changes in v5 here <a class="reference internal" href="../../cvl/v5-changes.html"><span class="doc">Certora CLI 5.0 Changes</span></a>.</p>
<section id="id36">
<h3><a class="toc-backref" href="#id128" role="doc-backlink">CVL</a><a class="headerlink" href="#id36" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[feat] Allowing calling Solidity functions from within CVL hooks</p></li>
<li><p>[feat] <a class="reference internal" href="../../cvl/expr.html#direct-storage-access"><span class="std std-ref">Direct storage access</span></a></p></li>
<li><p>[feat] Support for exhaustive parametric methods. Now <code class="docutils literal notranslate"><span class="pre">method</span> <span class="pre">f</span></code> calls will check for all methods in all contracts in Scene. The set of checked contracts can be limited with <code class="docutils literal notranslate"><span class="pre">--parametric_contracts</span> <span class="pre">Contract1</span> <span class="pre">Contract2</span></code></p></li>
<li><p>[bugfix] Disallow declaring method variables (aka <code class="docutils literal notranslate"><span class="pre">method</span> <span class="pre">f</span></code>; declarations) outside the top-level scope of a rule. They could still be declared as rule and CVL function arguments</p></li>
<li><p>[bugfix] Remove assume/assert notation from <code class="docutils literal notranslate"><span class="pre">DELETE</span></code> summary qualifiers</p></li>
<li><p>[bugfix] Disallow Solidity calls in CVL quantifier bodies</p></li>
<li><p>[bugfix] Support the ‘$’ sign in identifiers (specifically for Solidity functions)</p></li>
<li><p>[UX] When non-reverting calls lead to an ‘empty function’ because all paths revert, show an alert in the rule report</p></li>
</ul>
</section>
<section id="id37">
<h3><a class="toc-backref" href="#id129" role="doc-backlink">Performance</a><a class="headerlink" href="#id37" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[feat] New parallel splitter, can be enabled with <code class="docutils literal notranslate"><span class="pre">--prover_args</span> <span class="pre">'-newSplitParallel</span> <span class="pre">true'</span></code></p></li>
<li><p>[feat] A new option for potential help with timeouts <code class="docutils literal notranslate"><span class="pre">--prover_args</span> <span class="pre">'-calltraceFreeOpt</span> <span class="pre">true'</span></code></p></li>
<li><p>[feat] An option <code class="docutils literal notranslate"><span class="pre">-relaxedPointerSemantics</span></code> accepting a comma-separated list of <code class="docutils literal notranslate"><span class="pre">contract:methodWithoutParamTypes</span></code> pairs where the points-to analysis is allowed to be less strict</p></li>
<li><p>[feat] Better support for internal function summaries when <code class="docutils literal notranslate"><span class="pre">--via-ir</span></code> option is used, enabled with <code class="docutils literal notranslate"><span class="pre">--function_finder_mode</span> <span class="pre">relaxed</span></code></p></li>
<li><p>[bugfix] Errors for an optimization we call “Memory partitioning” will now show up as alerts in the Global Problems view</p></li>
</ul>
</section>
<section id="id38">
<h3><a class="toc-backref" href="#id130" role="doc-backlink">Misc</a><a class="headerlink" href="#id38" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[feat] Solana call trace basic support</p></li>
<li><p>[feat] Mutation testing: Allow <code class="docutils literal notranslate"><span class="pre">certoraMutate</span></code> to run with a link to an original run</p></li>
<li><p>[feat] Allow to skip <code class="docutils literal notranslate"><span class="pre">solc</span></code> warnings we consider errors (undefined return values) with <code class="docutils literal notranslate"><span class="pre">--contract_compiler_skip_severe_warning_as_error</span></code></p></li>
<li><p>[feat] <code class="docutils literal notranslate"><span class="pre">--send_only</span></code> is now the default mode except for CI users. Use <code class="docutils literal notranslate"><span class="pre">--wait_for_results</span></code> to force the old behavior</p></li>
<li><p>[bugfix] Fixes for: Vyper, loop unrolling, CVL, memory consumption, storage splitting</p></li>
<li><p>[bugfix] Remove support for native array theory in SMT</p></li>
<li><p>[bugfix] Mutation testing: only delete files created by the mutation tester</p></li>
<li><p>[UX] Old CLI format is now obsolete</p></li>
<li><p>[UX] CVL1 type checker is not run anymore for compatibility checks</p></li>
<li><p>[UX] <code class="docutils literal notranslate"><span class="pre">--solc_args</span></code> is deprecated</p></li>
</ul>
</section>
</section>
<section id="september-26-2023">
<h2><a class="toc-backref" href="#id131" role="doc-backlink">4.13.1 (September 26, 2023)</a><a class="headerlink" href="#september-26-2023" title="Link to this heading"></a></h2>
<p>Minor improvements.</p>
<ul class="simple">
<li><p>[feat] Present array length accesses in call  trace</p></li>
<li><p>[bugfix] Report timeouts of sanity checks</p></li>
</ul>
</section>
<section id="september-17-2023">
<h2><a class="toc-backref" href="#id132" role="doc-backlink">4.12.1 (September 17, 2023)</a><a class="headerlink" href="#september-17-2023" title="Link to this heading"></a></h2>
<section id="id39">
<h3><a class="toc-backref" href="#id133" role="doc-backlink">CVL</a><a class="headerlink" href="#id39" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[bugfix] fix to bitwise operations</p></li>
<li><p>[bugfix] verify range of <code class="docutils literal notranslate"><span class="pre">nativeBalances[addr]</span></code> values</p></li>
<li><p>[bugfix] no duplication of multi-dimensional ghosts with axioms</p></li>
<li><p>[feat] delete summary qualifiers for faster preprocessing and dealing with analysis-breaking external functions. If a function is never called from spec, it will not be processed. In cases where it is externally called from Solidity, the summary will apply.</p></li>
<li><p>[feat] greater flexibility of internal summaries - allows accepting as arguments and returning certain reference types: primitive arrays, <code class="docutils literal notranslate"><span class="pre">bytes</span></code>, and structs which may (in nested structs too) contain primitive arrays</p></li>
<li><p>[feat] support multiple return values from CVL functions</p></li>
<li><p>[bugfix] Support keywords as struct fields and user defined type names</p></li>
<li><p>[bugfix] Fix to multi-assert mode when multiple CVL asserts in a rule share the same message</p></li>
<li><p>[UX] Skip rules where all methods are filtered out</p></li>
<li><p>[bugfix] Do not drop quantifiers when instrumenting vacuity checks</p></li>
<li><p>[UX] Improved error messages for preserved block errors</p></li>
<li><p>[bugfix] Support invariant preserved blocks for functions with an argument which is an array of structs</p></li>
<li><p>[feat] New keyword: <code class="docutils literal notranslate"><span class="pre">executingContract</span></code> available inside opcode hooks</p></li>
<li><p>[bugfix] Applying the CALL opcode hook even if the balance transfer fails</p></li>
<li><p>[bugfix] Support assigning to a wildcard variable</p></li>
<li><p>[bugfix] Fail if CVL function is non-void and does not end with a return statement</p></li>
</ul>
</section>
<section id="id40">
<h3><a class="toc-backref" href="#id134" role="doc-backlink">Performance</a><a class="headerlink" href="#id40" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[feat] Optimizations for safe math handling, in particular for <code class="docutils literal notranslate"><span class="pre">solc</span></code> versions 8.19 and up</p></li>
<li><p>[feat] Better performance of <code class="docutils literal notranslate"><span class="pre">string</span></code> and array types</p></li>
</ul>
</section>
<section id="call-trace-rule-report">
<h3><a class="toc-backref" href="#id135" role="doc-backlink">Call Trace &amp; Rule Report</a><a class="headerlink" href="#call-trace-rule-report" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[feat] Show storage changed since the start</p></li>
<li><p>[feat] More frequent rule-report update</p></li>
<li><p>[bugfix] Rule running time to show time interval instead of sum of sub-rules intervals</p></li>
<li><p>[feat] Show state of ghosts together with contract state</p></li>
<li><p>[bugfix] Fix formatting of values of type <code class="docutils literal notranslate"><span class="pre">bytesN</span></code> and of storage locations</p></li>
</ul>
</section>
<section id="id41">
<h3><a class="toc-backref" href="#id136" role="doc-backlink">CLI</a><a class="headerlink" href="#id41" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[bugfix] link to CVL2 migration document fixed</p></li>
<li><p>[bugfix] support for other formats of protocol author in <code class="docutils literal notranslate"><span class="pre">package.json</span></code> files</p></li>
<li><p>[bugfix] fix error message when passing global timeout setting</p></li>
<li><p>[bugfix] less verbose prints in terminal</p></li>
<li><p>[UX] Validate rule names</p></li>
<li><p>[UX] Show number of splits solved per rule and their “weight”</p></li>
<li><p>[bugfix] Fixes to equivalence checker</p></li>
</ul>
</section>
<section id="mutation-verification">
<h3><a class="toc-backref" href="#id137" role="doc-backlink">Mutation Verification</a><a class="headerlink" href="#mutation-verification" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[bugfix] correct traversing of rules</p></li>
<li><p>[feat] improved csv output</p></li>
</ul>
</section>
<section id="equivalence-checker">
<h3><a class="toc-backref" href="#id138" role="doc-backlink">Equivalence Checker</a><a class="headerlink" href="#equivalence-checker" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[feat] Support void functions</p></li>
<li><p>[feat] Support compiler comparison</p></li>
<li><p>[bugfix] Making comparison more reliable in terms of initial state and with respect to low-level calls</p></li>
</ul>
</section>
</section>
<section id="august-21-2023">
<h2><a class="toc-backref" href="#id139" role="doc-backlink">4.10.1 (August 21, 2023)</a><a class="headerlink" href="#august-21-2023" title="Link to this heading"></a></h2>
<section id="id42">
<h3><a class="toc-backref" href="#id140" role="doc-backlink">CVL</a><a class="headerlink" href="#id42" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[feat] Support Solidity calls also from internal summaries</p></li>
<li><p>[feat] Allowing <code class="docutils literal notranslate"><span class="pre">with(env)</span></code> for summaries <a class="reference internal" href="../../cvl/methods.html#with-env"><span class="std std-ref">with(env e) clauses</span></a></p></li>
<li><p>[bugfix] <code class="docutils literal notranslate"><span class="pre">lastStorage</span></code> comparison fix for ghost maps</p></li>
<li><p>[bugfix] Bitwidth for <code class="docutils literal notranslate"><span class="pre">bytesK</span></code> variables is ensured, important for revert characteristic rules for methods accepting <code class="docutils literal notranslate"><span class="pre">bytesK</span></code></p></li>
<li><p>[bugfix] Fixing <code class="docutils literal notranslate"><span class="pre">struct</span></code>s encoding</p></li>
<li><p>[bugfix] Matching method summaries for methods accepting <code class="docutils literal notranslate"><span class="pre">interface</span></code>s</p></li>
<li><p>[bugfix] Some improvements to how quantifiers calling Solidity functions are handled</p></li>
</ul>
</section>
<section id="id43">
<h3><a class="toc-backref" href="#id141" role="doc-backlink">Mutation Verification</a><a class="headerlink" href="#id43" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[feat] Output CSV files of the results</p></li>
<li><p>[bugfix] Manual mutations work and support for multiple manual mutations</p></li>
<li><p>[bugfix] <code class="docutils literal notranslate"><span class="pre">certoraMutate</span></code> working when running from project’s root</p></li>
</ul>
</section>
<section id="timeouts-and-performance">
<h3><a class="toc-backref" href="#id142" role="doc-backlink">Timeouts and performance</a><a class="headerlink" href="#timeouts-and-performance" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[feat] Show informative messages about cache hits</p></li>
<li><p>[bugfix] fix hashes of constant strings in constructors vs. in executable bytecode</p></li>
</ul>
</section>
<section id="linking">
<h3><a class="toc-backref" href="#id143" role="doc-backlink">Linking</a><a class="headerlink" href="#linking" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[bugfix] Fixing source-based heuristics linking to decrease chance for wrong matches</p></li>
<li><p>[bugfix] Fixes to sighash resolution</p></li>
<li><p>[bugfix] Correct revert handling in dispatched calls</p></li>
</ul>
</section>
<section id="vyper">
<h3><a class="toc-backref" href="#id144" role="doc-backlink">Vyper</a><a class="headerlink" href="#vyper" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[bugfix] Support for versions below 0.2.16 (from before storage layout output was introduced in Vyper)</p></li>
</ul>
</section>
</section>
<section id="august-13-2023">
<h2><a class="toc-backref" href="#id145" role="doc-backlink">4.8.0 (August 13, 2023)</a><a class="headerlink" href="#august-13-2023" title="Link to this heading"></a></h2>
<section id="new-features-and-enhancements">
<h3><a class="toc-backref" href="#id146" role="doc-backlink">New features and enhancements</a><a class="headerlink" href="#new-features-and-enhancements" title="Link to this heading"></a></h3>
<section id="id44">
<h4><a class="toc-backref" href="#id147" role="doc-backlink">CVL</a><a class="headerlink" href="#id44" title="Link to this heading"></a></h4>
<ul class="simple">
<li><p>Better expressivity: <code class="docutils literal notranslate"><span class="pre">ALWAYS</span></code> summaries can get <code class="docutils literal notranslate"><span class="pre">bytesK</span></code> arguments, e.g. <code class="docutils literal notranslate"><span class="pre">...</span> <span class="pre">=&gt;</span> <span class="pre">ALWAYS(to_bytesK(...))</span></code></p></li>
<li><p>Support for <code class="docutils literal notranslate"><span class="pre">ALL_SLOAD</span></code> and <code class="docutils literal notranslate"><span class="pre">ALL_SSTORE</span></code> hooks (see <a class="reference internal" href="../../cvl/hooks.html#rawhooks"><span class="std std-ref">Hooking on all storage loads or stores</span></a>)</p></li>
<li><p>Improved ABI encoding/decoding in CVL</p></li>
<li><p>More efficient handling of skipped rules</p></li>
<li><p>Allow calling Solidity functions from expression summaries</p></li>
</ul>
</section>
<section id="id45">
<h4><a class="toc-backref" href="#id148" role="doc-backlink">Call Trace and Rule Report</a><a class="headerlink" href="#id45" title="Link to this heading"></a></h4>
<ul class="simple">
<li><p>Display havoced return values</p></li>
<li><p>Fixes to dump generation</p></li>
<li><p>Improved timeout visualization in TAC dumps</p></li>
<li><p>Fixes to presentation of quantified formulas in Call Trace</p></li>
<li><p>Better presentation of timeouts</p></li>
<li><p>Rule report will contain warnings about unused summaries</p></li>
<li><p>Display native balances</p></li>
<li><p>More friendly text for dispatcher-based resolutions</p></li>
<li><p>Improved ghost presentation</p></li>
</ul>
</section>
<section id="id46">
<h4><a class="toc-backref" href="#id149" role="doc-backlink">Performance</a><a class="headerlink" href="#id46" title="Link to this heading"></a></h4>
<ul class="simple">
<li><p>Rule cache is enabled</p></li>
<li><p>Reducing number of iterations of static analyses</p></li>
<li><p>Improved decompiler performance</p></li>
</ul>
</section>
<section id="mutation-verifier">
<h4><a class="toc-backref" href="#id150" role="doc-backlink">Mutation Verifier</a><a class="headerlink" href="#mutation-verifier" title="Link to this heading"></a></h4>
<ul class="simple">
<li><p>Manual mutants now supported in <code class="docutils literal notranslate"><span class="pre">certoraMutate</span></code></p></li>
</ul>
</section>
<section id="id47">
<h4><a class="toc-backref" href="#id151" role="doc-backlink">Equivalence Checker</a><a class="headerlink" href="#id47" title="Link to this heading"></a></h4>
<ul class="simple">
<li><p>Support for Vyper for the equivalence checker (<code class="docutils literal notranslate"><span class="pre">certoraEqCheck</span></code> utility)</p></li>
</ul>
</section>
<section id="id48">
<h4><a class="toc-backref" href="#id152" role="doc-backlink">CLI</a><a class="headerlink" href="#id48" title="Link to this heading"></a></h4>
<ul class="simple">
<li><p>Allowing more Solidity file names</p></li>
<li><p>More compact zip input to cloud</p></li>
<li><p>Users can reduce the global timeout below 2 hours using <a class="reference internal" href="../cli/options.html#global-timeout"><span class="std std-ref">global_timeout</span></a></p></li>
</ul>
</section>
</section>
<section id="bug-fixes">
<h3><a class="toc-backref" href="#id153" role="doc-backlink">Bug fixes</a><a class="headerlink" href="#bug-fixes" title="Link to this heading"></a></h3>
<section id="id49">
<h4><a class="toc-backref" href="#id154" role="doc-backlink">CVL</a><a class="headerlink" href="#id49" title="Link to this heading"></a></h4>
<ul class="simple">
<li><p>More graceful handling of bit-vector mode so that it emits less errors. It should be noted that numbers are forced to the 256-bit range and thus it is not recommended to use bit-vector mode.</p></li>
<li><p>Declaration of wildcard (i.e. <code class="docutils literal notranslate"><span class="pre">_</span></code>) variable names in rules or rule arguments is disallowed</p></li>
<li><p>Internal summaries - disallow <code class="docutils literal notranslate"><span class="pre">NONDET</span></code> summary on functions returning a pointer, as well as <code class="docutils literal notranslate"><span class="pre">HAVOC</span></code> or <code class="docutils literal notranslate"><span class="pre">HAVOC_ECF</span></code> summaries</p></li>
<li><p>Better checks on ghost axioms, especially if they refer to definitions</p></li>
<li><p>Fixing array literal assignments</p></li>
<li><p>Forbid assignments to array elements, i.e. <code class="docutils literal notranslate"><span class="pre">uint[]</span> <span class="pre">a;</span> <span class="pre">a[0]</span> <span class="pre">=</span> <span class="pre">x;</span></code> is disallowed</p></li>
<li><p>Internal summarization did not work in certain tricky cases involving loops and external calls</p></li>
<li><p>Fixing “Certora Prover Internal Error” sometimes appearing when reasoning on complex-typed arrays</p></li>
<li><p>Fixes for structs with contract types as fields</p></li>
</ul>
</section>
<section id="id50">
<h4><a class="toc-backref" href="#id155" role="doc-backlink">Call Trace</a><a class="headerlink" href="#id50" title="Link to this heading"></a></h4>
<ul class="simple">
<li><p>Fix call trace generation issues for <code class="docutils literal notranslate"><span class="pre">forall</span></code> expressions</p></li>
</ul>
</section>
<section id="id51">
<h4><a class="toc-backref" href="#id156" role="doc-backlink">Mutation Verifier</a><a class="headerlink" href="#id51" title="Link to this heading"></a></h4>
<ul class="simple">
<li><p>Correctly dealing with original runs where rules were originally violated</p></li>
</ul>
</section>
<section id="id52">
<h4><a class="toc-backref" href="#id157" role="doc-backlink">Misc.</a><a class="headerlink" href="#id52" title="Link to this heading"></a></h4>
<ul class="simple">
<li><p>Static analyses bug fixes</p></li>
<li><p>Fixes to read-only reentrancy rule</p></li>
<li><p>Avoiding an exception when <code class="docutils literal notranslate"><span class="pre">-dontStopAtFirstSplitTimeout</span></code> completes with all splits timing out</p></li>
</ul>
</section>
</section>
<section id="other-improvements">
<h3><a class="toc-backref" href="#id158" role="doc-backlink">Other improvements</a><a class="headerlink" href="#other-improvements" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>Better parallelism and utilization</p></li>
<li><p>Timeout cores and more difficulty&nbsp;traces and hints to study timeout causes</p></li>
<li><p>Support for Solidity compiler version 0.8.20 and up</p></li>
</ul>
</section>
</section>
<section id="july-15-2023">
<h2><a class="toc-backref" href="#id159" role="doc-backlink">4.5.1 (July 15, 2023)</a><a class="headerlink" href="#july-15-2023" title="Link to this heading"></a></h2>
<section id="new-features">
<h3><a class="toc-backref" href="#id160" role="doc-backlink">New features</a><a class="headerlink" href="#new-features" title="Link to this heading"></a></h3>
<section id="id53">
<h4><a class="toc-backref" href="#id161" role="doc-backlink">CVL</a><a class="headerlink" href="#id53" title="Link to this heading"></a></h4>
<ul class="simple">
<li><p>Better expressivity: Allow binding the called contract in summaries using <code class="docutils literal notranslate"><span class="pre">calledContract</span></code> (see <a class="reference internal" href="../../cvl/methods.html#expression-summary"><span class="std std-ref">Expression summaries</span></a>)</p></li>
<li><p>Ease of use: Support reading and passing complex array and struct types in CVL. For example, you can write now:</p></li>
</ul>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell1"><span></span><span class="kt">env</span><span class="w"> </span>e<span class="p">;</span>
<span class="kt">uint</span><span class="w"> </span>v<span class="p">;</span>
Test<span class="p">.</span>MyComplexStruct<span class="w"> </span>x<span class="p">;</span>
<span class="kt">uint</span><span class="p">[]</span><span class="w"> </span>thingArray<span class="w"> </span><span class="o">=</span><span class="w"> </span>x<span class="p">.</span>nested<span class="p">[</span>v<span class="p">].</span>thing<span class="p">;</span>
<span class="kr">require</span><span class="w"> </span>thingArray<span class="p">.</span>length<span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="m m-Decimal">3</span><span class="p">;</span>
<span class="kr">assert</span><span class="w"> </span>foo<span class="p">(</span>e<span class="p">,</span><span class="w"> </span>x<span class="p">,</span><span class="w"> </span>v<span class="p">)</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="m m-Decimal">3</span><span class="p">;</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell1">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>For the Solidity snippet of a contract <code class="docutils literal notranslate"><span class="pre">Test</span></code>:</p>
<div class="highlight-solidity notranslate"><div class="highlight"><pre id="codecell2"><span></span><span class="kt">struct</span><span class="w"> </span><span class="nv">MyComplexStruct</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span>MyInnerStruct<span class="p">[]</span><span class="w"> </span>nested<span class="p">;</span>
<span class="p">}</span>

<span class="kt">struct</span><span class="w"> </span><span class="nv">MyInnerStruct</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kt">uint</span><span class="p">[]</span><span class="w"> </span>thing<span class="p">;</span>
<span class="w">    </span><span class="kt">uint</span><span class="w"> </span><span class="nv">field</span><span class="p">;</span>
<span class="p">}</span>

<span class="kt">function</span><span class="w"> </span><span class="nv">foo</span><span class="p">(</span>MyComplexStruct<span class="w"> </span><span class="kt">memory</span><span class="w"> </span>z<span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span><span class="nv">x</span><span class="p">)</span><span class="w"> </span><span class="kt">external</span><span class="w"> </span><span class="kt">returns</span><span class="w"> </span><span class="p">(</span><span class="kt">uint</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kt">return</span><span class="w"> </span>z<span class="p">.</span>nested<span class="p">[</span>x<span class="p">].</span>thing<span class="p">.</span>length<span class="p">;</span>
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
<ul class="simple">
<li><p>Ease of use: Support access for storage variables whose type is either a primitive, a user defined value, or an enum</p></li>
<li><p>Ease of use: Enum types can be cast to integer types in CVL using the usual <code class="docutils literal notranslate"><span class="pre">assert_TYPE</span></code> and <code class="docutils literal notranslate"><span class="pre">require_TYPE</span></code> operators (see <a class="reference internal" href="../../cvl/cvl2/changes.html#cvl2-integer-types"><span class="std std-ref">Changes to integer types</span></a>)</p></li>
<li><p>A built-in rule for read-only reentrancy vulnerabilities</p></li>
</ul>
</section>
<section id="id54">
<h4><a class="toc-backref" href="#id162" role="doc-backlink">Call Trace</a><a class="headerlink" href="#id54" title="Link to this heading"></a></h4>
<ul class="simple">
<li><p>Better view of the storage state at storage assignments, storage restore points, and storage comparisons</p></li>
</ul>
</section>
<section id="multi-contract-handling">
<h4><a class="toc-backref" href="#id163" role="doc-backlink">Multi-contract handling</a><a class="headerlink" href="#multi-contract-handling" title="Link to this heading"></a></h4>
<ul class="simple">
<li><p>Improvements to the call resolution fallback mechanism in case main analyses fail, allowing linking and summarizations despite the failures</p></li>
<li><p>Introducing <code class="docutils literal notranslate"><span class="pre">summarizeExtLibraryCallsAsNonDetPreLinking</span></code> Prover option for easier setup of library-heavy code. See <a class="reference internal" href="../../user-guide/out-of-resources/timeout.html#library-timeouts"><span class="std std-ref">Library-based systems</span></a></p></li>
</ul>
</section>
<section id="id55">
<h4><a class="toc-backref" href="#id164" role="doc-backlink">Mutation Verifier</a><a class="headerlink" href="#id55" title="Link to this heading"></a></h4>
<ul class="simple">
<li><p>New and easier to use <code class="docutils literal notranslate"><span class="pre">certoraMutate</span></code>. See <a class="reference internal" href="../../gambit/mutation-verifier.html"><span class="doc">Using Gambit with the Prover</span></a></p></li>
</ul>
</section>
</section>
<section id="id56">
<h3><a class="toc-backref" href="#id165" role="doc-backlink">Bug fixes</a><a class="headerlink" href="#id56" title="Link to this heading"></a></h3>
<section id="id57">
<h4><a class="toc-backref" href="#id166" role="doc-backlink">CVL</a><a class="headerlink" href="#id57" title="Link to this heading"></a></h4>
<ul class="simple">
<li><p>Fix issue when CVL functions are invoked within ternary expressions</p></li>
<li><p>Fix evaluation of power expressions such as 2^256</p></li>
<li><p>Make sure CVL keywords can appear as struct fields and be accessible from CVL</p></li>
</ul>
</section>
<section id="id58">
<h4><a class="toc-backref" href="#id167" role="doc-backlink">Performance</a><a class="headerlink" href="#id58" title="Link to this heading"></a></h4>
<ul class="simple">
<li><p>Performance optimizations for the contract preprocessing step</p></li>
<li><p>Performance improvements in Prover</p></li>
<li><p>Performance improvements in CVL type checker (allows for faster job submission)</p></li>
</ul>
</section>
<section id="ux">
<h4><a class="toc-backref" href="#id168" role="doc-backlink">UX</a><a class="headerlink" href="#ux" title="Link to this heading"></a></h4>
<ul class="simple">
<li><p>Show primary contract under verification even when a job is queued but not yet started</p></li>
<li><p><a class="reference internal" href="../../cvl/methods.html#envfree"><span class="std std-ref">envfree</span></a> checks failures presented not just in rules section, but also in the problems view for highlighting</p></li>
<li><p>Make sure more files generated by <code class="docutils literal notranslate"><span class="pre">certoraRun</span></code> are stored in <code class="docutils literal notranslate"><span class="pre">.certora_internal</span></code></p></li>
<li><p>Allow equivalence checker to have the same function name appear in two contracts</p></li>
</ul>
</section>
</section>
</section>
<section id="july-2-2023">
<h2><a class="toc-backref" href="#id169" role="doc-backlink">4.3.1 (July 2, 2023)</a><a class="headerlink" href="#july-2-2023" title="Link to this heading"></a></h2>
<section id="id59">
<h3><a class="toc-backref" href="#id170" role="doc-backlink">New features</a><a class="headerlink" href="#id59" title="Link to this heading"></a></h3>
<section id="id60">
<h4><a class="toc-backref" href="#id171" role="doc-backlink">CVL</a><a class="headerlink" href="#id60" title="Link to this heading"></a></h4>
<ul class="simple">
<li><p>New builtin rules: <a class="reference internal" href="../../cvl/builtin.html#built-in-sanity"><span class="std std-ref">sanity</span></a> and <a class="reference internal" href="../../cvl/builtin.html#built-in-deep-sanity"><span class="std std-ref">deepSanity</span></a></p></li>
<li><p>Support a new keyword in CVL: <a class="reference internal" href="../../cvl/statements.html#satisfy"><span class="std std-ref">satisfy</span></a></p></li>
<li><p>User-defined types can appear in hook patterns</p></li>
<li><p>Support using <code class="docutils literal notranslate"><span class="pre">currentContract</span></code> in ghosts and quantified expressions</p></li>
<li><p>Support conversion of <code class="docutils literal notranslate"><span class="pre">uintN</span></code> to <code class="docutils literal notranslate"><span class="pre">bytesK</span></code> with casting <a class="reference internal" href="../../cvl/cvl2/changes.html#bytesn-support"><span class="std std-ref">Support for bytes1…bytes32</span></a></p></li>
<li><p>Support <a class="reference internal" href="../../cvl/expr.html#special-fields"><span class="std std-ref">nativeBalances</span></a> in CVL</p></li>
<li><p>Making access of user-defined-types (enums, structs, user-defined type values) in Solidity consistent, whether those types are declared in a contract or outside of a contract. Specifically, for a user-defined type that’s declared in a contract, the access to it in a spec file is <code class="docutils literal notranslate"><span class="pre">DeclaringContract.TypeName</span></code>. For top-level user-defined types (declared outside of any contract/library) the access is using the using contract <code class="docutils literal notranslate"><span class="pre">UsingContract.TypeName</span></code>.</p></li>
<li><p>Support for <a class="reference internal" href="../../cvl/hooks.html#opcode-hooks"><span class="std std-ref">EVM opcode hooks</span></a></p></li>
</ul>
</section>
<section id="calltrace">
<h4><a class="toc-backref" href="#id172" role="doc-backlink">CallTrace</a><a class="headerlink" href="#calltrace" title="Link to this heading"></a></h4>
<ul class="simple">
<li><p>Display CVL functions in Call Trace</p></li>
<li><p>CallTrace presenting skolemized variables for quantified expressions</p></li>
<li><p>Gather all setup labels in CallTrace to be under one label</p></li>
<li><p>Make CallTrace accept invocation of internal solidity functions from CVL</p></li>
</ul>
</section>
<section id="summarization">
<h4><a class="toc-backref" href="#id173" role="doc-backlink">Summarization</a><a class="headerlink" href="#summarization" title="Link to this heading"></a></h4>
<ul class="simple">
<li><p>Early summarization of internal functions for improved performance and precision</p></li>
<li><p><a class="reference internal" href="../../user-guide/out-of-resources/timeout.html#library-timeouts"><span class="std std-ref">“catch-all” summaries</span></a>. For example, given a library <code class="docutils literal notranslate"><span class="pre">L</span></code> on which we wish to apply the same summary for all external methods in <code class="docutils literal notranslate"><span class="pre">L</span></code>, write <code class="docutils literal notranslate"><span class="pre">function</span> <span class="pre">L._</span> <span class="pre">external</span> <span class="pre">=&gt;</span> <span class="pre">NONDET</span></code></p></li>
</ul>
</section>
<section id="id61">
<h4><a class="toc-backref" href="#id174" role="doc-backlink">Performance</a><a class="headerlink" href="#id61" title="Link to this heading"></a></h4>
<ul class="simple">
<li><p>More stable generation of formulas for more predictable, consistent running times of rules</p></li>
<li><p>Basic parallel splitting for improved running time of rule solving</p></li>
</ul>
</section>
<section id="id62">
<h4><a class="toc-backref" href="#id175" role="doc-backlink">Other improvements</a><a class="headerlink" href="#id62" title="Link to this heading"></a></h4>
<ul class="simple">
<li><p>Change default to new <code class="docutils literal notranslate"><span class="pre">certora-cli</span></code> API</p></li>
<li><p>Check for an invalid rule name (given with <code class="docutils literal notranslate"><span class="pre">--rule</span></code>) locally, before sending a request to the server</p></li>
<li><p>Adapt CVL AST serialization to JSON to enable LSP for CVL2</p></li>
<li><p>Visualize unsolved splits in timeouts</p></li>
</ul>
</section>
</section>
<section id="id63">
<h3><a class="toc-backref" href="#id176" role="doc-backlink">Bug fixes</a><a class="headerlink" href="#id63" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>Warn if <code class="docutils literal notranslate"><span class="pre">CONST</span></code> summary is applied to methods that return nothing</p></li>
<li><p>The type checker will fail if an internal method summary uses an inheriting contract name instead of the declaring contract name</p></li>
<li><p>Disallow shadowing of ghost variables</p></li>
<li><p>Support exists as a struct field in spec files</p></li>
<li><p><code class="docutils literal notranslate"><span class="pre">require_</span></code> and <code class="docutils literal notranslate"><span class="pre">assert_</span></code> casts disallowed in ghost axioms</p></li>
<li><p>CallTrace bug fixes</p></li>
</ul>
</section>
</section>
<section id="june-7-2023-cvl-2">
<h2><a class="toc-backref" href="#id177" role="doc-backlink">4.0.5 (June 7, 2023) CVL 2</a><a class="headerlink" href="#june-7-2023-cvl-2" title="Link to this heading"></a></h2>
<section id="breaking-changes">
<h3><a class="toc-backref" href="#id178" role="doc-backlink">Breaking changes</a><a class="headerlink" href="#breaking-changes" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>Upgrade to CVL 2 (see <a class="reference internal" href="../../cvl/cvl2/changes.html"><span class="doc">Changes Introduced in CVL 2</span></a> and <a class="reference internal" href="../../cvl/cvl2/migration.html"><span class="doc">CVL2 Migration Guide</span></a>)</p></li>
<li><p>Change the minimal python required version from 3.8.0 to 3.8.16</p></li>
</ul>
</section>
<section id="id64">
<h3><a class="toc-backref" href="#id179" role="doc-backlink">New features</a><a class="headerlink" href="#id64" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p><a class="reference internal" href="../../cvl/expr.html#storage-comparison"><span class="std std-ref">Comparing storage</span></a></p></li>
<li><p>Add support for Vyper</p></li>
<li><p>Support <code class="docutils literal notranslate"><span class="pre">CONSTANT</span></code> summaries for all non-dynamic return types</p></li>
<li><p>New <a class="reference internal" href="../../cvl/builtin.html#built-in"><span class="std std-ref">built-in rules</span></a> <code class="docutils literal notranslate"><span class="pre">sanity</span></code> and <code class="docutils literal notranslate"><span class="pre">deepSanity</span></code></p></li>
<li><p>Added <code class="docutils literal notranslate"><span class="pre">--protocol_name</span></code> and <code class="docutils literal notranslate"><span class="pre">--protocol_owner</span></code> flags</p></li>
</ul>
</section>
<section id="id65">
<h3><a class="toc-backref" href="#id180" role="doc-backlink">Other improvements</a><a class="headerlink" href="#id65" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>Performance improvements</p></li>
<li><p>Bug fixes and internal improvements</p></li>
<li><p>Improved error messages</p></li>
<li><p>Improved console output</p></li>
<li><p>Improved call resolution output</p></li>
</ul>
</section>
</section>
</section>


           </div>
          </div>
          <footer><div class="rst-footer-buttons" role="navigation" aria-label="Footer">
        <a href="index.html" class="btn btn-neutral float-left" title="Changelogs" accesskey="p" rel="prev"><span class="fa fa-arrow-circle-left" aria-hidden="true"></span> Previous</a>
        <a href="gui_changelog.html" class="btn btn-neutral float-right" title="GUI Release Notes" accesskey="n" rel="next">Next <span class="fa fa-arrow-circle-right" aria-hidden="true"></span></a>
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