<!DOCTYPE html><html class="writer-html5" lang="en" data-content_root="../../../"><head>
  <meta charset="utf-8"><meta name="viewport" content="width=device-width, initial-scale=1">

  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>GUI Release Notes — Certora Prover Documentation 0.0 documentation</title>
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
    <link rel="next" title="Sunbeam: Verification for Soroban" href="../../sunbeam/index.html">
    <link rel="prev" title="Prover Release Notes" href="prover_changelog.html"> 
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
<li class="toctree-l3"><a class="reference internal" href="prover_changelog.html">Prover Release Notes</a></li>
<li class="toctree-l3 current" aria-expanded="true"><a class="reference internal current" href="#" aria-expanded="true"><button class="toctree-expand" title="Open/close menu"></button>GUI Release Notes</a><ul>
<li class="toctree-l4"><a class="reference internal" href="#apr-10-2025">4.3.0 (Apr 10, 2025)</a></li>
<li class="toctree-l4"><a class="reference internal" href="#mar-13-2025">4.0.2 (Mar 13, 2025)</a></li>
<li class="toctree-l4"><a class="reference internal" href="#feb-19-2025">4.0.0 (Feb 19, 2025)</a></li>
<li class="toctree-l4"><a class="reference internal" href="#jan-12-2025">3.1.1 (Jan 12, 2025)</a></li>
<li class="toctree-l4"><a class="reference internal" href="#nov-18-2024">3.0.2 (Nov 18, 2024)</a></li>
<li class="toctree-l4"><a class="reference internal" href="#nov-6-2024">2.4.4 (Nov 6, 2024)</a></li>
<li class="toctree-l4"><a class="reference internal" href="#oct-6-2024">2.4.1 (Oct 6, 2024)</a></li>
<li class="toctree-l4"><a class="reference internal" href="#sep-2-2024">2.3.2 (Sep 2, 2024)</a></li>
<li class="toctree-l4"><a class="reference internal" href="#jul-24-2024">2.2.0 (Jul 24, 2024)</a></li>
<li class="toctree-l4"><a class="reference internal" href="#jul-8-2024">2.1.6 (Jul 8, 2024)</a></li>
<li class="toctree-l4"><a class="reference internal" href="#may-15-2024">2.0.1 (May 15, 2024)</a></li>
<li class="toctree-l4"><a class="reference internal" href="#apr-11-2024">1.0.0 (Apr 11, 2024)</a></li>
<li class="toctree-l4"><a class="reference internal" href="#mar-11-2024">0.8.0 (Mar 11, 2024)</a></li>
<li class="toctree-l4"><a class="reference internal" href="#feb-12-2024">0.7.0 (Feb 12, 2024)</a></li>
<li class="toctree-l4"><a class="reference internal" href="#jan-31-2024">0.6.0 (Jan 31, 2024)</a></li>
<li class="toctree-l4"><a class="reference internal" href="#nov-26-2023">0.5.7 (Nov 26, 2023)</a></li>
<li class="toctree-l4"><a class="reference internal" href="#feb-11-2024">0.5.62 (Feb 11, 2024)</a></li>
<li class="toctree-l4"><a class="reference internal" href="#october-24-2023">0.5.6 (October 24, 2023)</a></li>
</ul>
</li>
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
      <li class="breadcrumb-item active">GUI Release Notes</li>
      <li class="wy-breadcrumbs-aside">
            <a href="../../../_sources/docs/prover/changelog/gui_changelog.md.txt" rel="nofollow"> View page source</a>
      </li>
  </ul>
  <hr>
</div>
          <div role="main" class="document" itemscope="itemscope" itemtype="http://schema.org/Article">
           <div itemprop="articleBody">
             
  <section id="gui-release-notes">
<h1><a class="toc-backref" href="#id24" role="doc-backlink">GUI Release Notes</a><a class="headerlink" href="#gui-release-notes" title="Link to this heading"></a></h1>
<nav class="contents" id="contents">
<p class="topic-title">Contents</p>
<ul class="simple">
<li><p><a class="reference internal" href="#gui-release-notes" id="id24">GUI Release Notes</a></p>
<ul>
<li><p><a class="reference internal" href="#apr-10-2025" id="id25">4.3.0 (Apr 10, 2025)</a></p>
<ul>
<li><p><a class="reference internal" href="#features" id="id26">Features</a></p></li>
<li><p><a class="reference internal" href="#fixed-bugs" id="id27">Fixed Bugs</a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#mar-13-2025" id="id28">4.0.2 (Mar 13, 2025)</a></p>
<ul>
<li><p><a class="reference internal" href="#id1" id="id29">Features</a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#feb-19-2025" id="id30">4.0.0 (Feb 19, 2025)</a></p>
<ul>
<li><p><a class="reference internal" href="#id2" id="id31">Features</a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#jan-12-2025" id="id32">3.1.1 (Jan 12, 2025)</a></p>
<ul>
<li><p><a class="reference internal" href="#id3" id="id33">Features</a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#nov-18-2024" id="id34">3.0.2 (Nov 18, 2024)</a></p>
<ul>
<li><p><a class="reference internal" href="#id4" id="id35">Features</a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#nov-6-2024" id="id36">2.4.4 (Nov 6, 2024)</a></p>
<ul>
<li><p><a class="reference internal" href="#id5" id="id37">Features</a></p></li>
<li><p><a class="reference internal" href="#id6" id="id38">Fixed Bugs</a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#oct-6-2024" id="id39">2.4.1 (Oct 6, 2024)</a></p>
<ul>
<li><p><a class="reference internal" href="#id7" id="id40">Features</a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#sep-2-2024" id="id41">2.3.2 (Sep 2, 2024)</a></p>
<ul>
<li><p><a class="reference internal" href="#id8" id="id42">Features</a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#jul-24-2024" id="id43">2.2.0 (Jul 24, 2024)</a></p>
<ul>
<li><p><a class="reference internal" href="#id9" id="id44">Features</a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#jul-8-2024" id="id45">2.1.6 (Jul 8, 2024)</a></p>
<ul>
<li><p><a class="reference internal" href="#id10" id="id46">Features</a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#may-15-2024" id="id47">2.0.1 (May 15, 2024)</a></p>
<ul>
<li><p><a class="reference internal" href="#id11" id="id48">Features</a></p></li>
<li><p><a class="reference internal" href="#id12" id="id49">Fixed Bugs</a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#apr-11-2024" id="id50">1.0.0 (Apr 11, 2024)</a></p>
<ul>
<li><p><a class="reference internal" href="#id13" id="id51">Features</a></p></li>
<li><p><a class="reference internal" href="#id14" id="id52">Fixed Bugs</a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#mar-11-2024" id="id53">0.8.0 (Mar 11, 2024)</a></p>
<ul>
<li><p><a class="reference internal" href="#id15" id="id54">Features</a></p></li>
<li><p><a class="reference internal" href="#id16" id="id55">Fixed Bugs</a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#feb-12-2024" id="id56">0.7.0 (Feb 12, 2024)</a></p>
<ul>
<li><p><a class="reference internal" href="#id17" id="id57">Fixed Bugs</a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#jan-31-2024" id="id58">0.6.0 (Jan 31, 2024)</a></p>
<ul>
<li><p><a class="reference internal" href="#id18" id="id59">Features</a></p></li>
<li><p><a class="reference internal" href="#id19" id="id60">Fixed Bugs</a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#nov-26-2023" id="id61">0.5.7 (Nov 26, 2023)</a></p>
<ul>
<li><p><a class="reference internal" href="#id20" id="id62">Features</a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#feb-11-2024" id="id63">0.5.62 (Feb 11, 2024)</a></p>
<ul>
<li><p><a class="reference internal" href="#id21" id="id64">Fixed Bugs</a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#october-24-2023" id="id65">0.5.6 (October 24, 2023)</a></p>
<ul>
<li><p><a class="reference internal" href="#id22" id="id66">Features</a></p></li>
<li><p><a class="reference internal" href="#id23" id="id67">Fixed Bugs</a></p></li>
</ul>
</li>
</ul>
</li>
</ul>
</nav>
<section id="apr-10-2025">
<h2><a class="toc-backref" href="#id25" role="doc-backlink">4.3.0 (Apr 10, 2025)</a><a class="headerlink" href="#apr-10-2025" title="Link to this heading"></a></h2>
<section id="features">
<h3><a class="toc-backref" href="#id26" role="doc-backlink">Features</a><a class="headerlink" href="#features" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[feat] Rule Report - Navigating to report with completed state, will now mark this job as “opened” in the Dashboard job list.</p></li>
<li><p>[feat] Rule Report - State-Diff: introducing the option to compare the state of the storage between different snapshots within the call trace. This option will aid users in understanding counter examples and debugging problems.</p></li>
<li><p>[feat] Rule Report - Full-screen Notifications Tab: Added a new full-screen (expanded) tab state to the notification panel for improved readability and navigation. Users can now easily switch between collapsed, small, and full-screen views to better manage long notifications.</p></li>
<li><p>[feat] Dashboard - Jobs list will now highlight unopened jobs. Jobs will be marked as “opened” by opening a report in a completed state, or by marking this manually in the dashboard.</p></li>
<li><p>[feat] Dashboard - Job list will now present the run_source of a job and enable filtering by run_source</p></li>
</ul>
</section>
<section id="fixed-bugs">
<h3><a class="toc-backref" href="#id27" role="doc-backlink">Fixed Bugs</a><a class="headerlink" href="#fixed-bugs" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[bug] Rule Report - Log out from Rule Report is now working as expected</p></li>
<li><p>[bug] Dashboard - Canceling a job from the Dashboard is now working as expected</p></li>
</ul>
</section>
</section>
<section id="mar-13-2025">
<h2><a class="toc-backref" href="#id28" role="doc-backlink">4.0.2 (Mar 13, 2025)</a><a class="headerlink" href="#mar-13-2025" title="Link to this heading"></a></h2>
<section id="id1">
<h3><a class="toc-backref" href="#id29" role="doc-backlink">Features</a><a class="headerlink" href="#id1" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[feat] Rule Report - Added icons and highlighter for Solana reports.</p></li>
<li><p>[feat] Rule Report - Improved Call Trace and Variables readability by truncating long values</p></li>
<li><p>[feat] Dashboard - Added tooltips for column headers</p></li>
</ul>
</section>
</section>
<section id="feb-19-2025">
<h2><a class="toc-backref" href="#id30" role="doc-backlink">4.0.0 (Feb 19, 2025)</a><a class="headerlink" href="#feb-19-2025" title="Link to this heading"></a></h2>
<section id="id2">
<h3><a class="toc-backref" href="#id31" role="doc-backlink">Features</a><a class="headerlink" href="#id2" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[feat] Rule Report - Improved call trace filtering &amp; navigation, to provide more flexibility and ease of use. You can now toggle between search and filter modes. Additionally, you can navigate results via the up/down arrows, similar to CTRL+F in a browser, to move through matches efficiently.</p></li>
<li><p>[feat] Rule Report - Added click-to-copy variables in call trace and variables tab</p></li>
</ul>
</section>
</section>
<section id="jan-12-2025">
<h2><a class="toc-backref" href="#id32" role="doc-backlink">3.1.1 (Jan 12, 2025)</a><a class="headerlink" href="#jan-12-2025" title="Link to this heading"></a></h2>
<section id="id3">
<h3><a class="toc-backref" href="#id33" role="doc-backlink">Features</a><a class="headerlink" href="#id3" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[feat] Support for displaying numeric values in string, decimal, or hexadecimal formats in Call Trace and Variables tabs, with a dropdown to switch formats.</p></li>
<li><p>[feat] Persist column configuration (display selection and width) across browser sessions on the Prover Dashboard, including between tabs and logins.</p></li>
<li><p>[feat] Added call traces and TAC dumps for sanity rules in Rule Report.</p></li>
</ul>
</section>
</section>
<section id="nov-18-2024">
<h2><a class="toc-backref" href="#id34" role="doc-backlink">3.0.2 (Nov 18, 2024)</a><a class="headerlink" href="#nov-18-2024" title="Link to this heading"></a></h2>
<section id="id4">
<h3><a class="toc-backref" href="#id35" role="doc-backlink">Features</a><a class="headerlink" href="#id4" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[feat] Improved formatting of the call trace: The call trace highlights values of the counter examples as gray boxes and provides tooltips indicating the semantics of the value (e.g. if the value is a return value or a parameter of a function call).</p></li>
<li><p>[feat] The rule tree automatically opens a node if it only contains a single child element. This reduces the number of user interactions required to get to the call trace and find the counter example.</p></li>
</ul>
</section>
</section>
<section id="nov-6-2024">
<h2><a class="toc-backref" href="#id36" role="doc-backlink">2.4.4 (Nov 6, 2024)</a><a class="headerlink" href="#nov-6-2024" title="Link to this heading"></a></h2>
<section id="id5">
<h3><a class="toc-backref" href="#id37" role="doc-backlink">Features</a><a class="headerlink" href="#id5" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[feat] Adding support for syntax highlighting of Rust files in the code editor</p></li>
<li><p>[feat] Flags in the config tab link to the flags in the documentation.</p></li>
</ul>
</section>
<section id="id6">
<h3><a class="toc-backref" href="#id38" role="doc-backlink">Fixed Bugs</a><a class="headerlink" href="#id6" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[bug] The re-run button was reported to not function for non-Certora users. This has been fixed.</p></li>
</ul>
</section>
</section>
<section id="oct-6-2024">
<h2><a class="toc-backref" href="#id39" role="doc-backlink">2.4.1 (Oct 6, 2024)</a><a class="headerlink" href="#oct-6-2024" title="Link to this heading"></a></h2>
<section id="id7">
<h3><a class="toc-backref" href="#id40" role="doc-backlink">Features</a><a class="headerlink" href="#id7" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[feat] Rule progress indicator: The progress of individual rules will be displayed in the tree view. Each node in the rule tree shows how many children have been completed already.</p></li>
<li><p>[feat] Re-run feature is available to all users. Upon a timeout of a rule, the user is able to re-run the particular rule with a portfolio of configurations aiming to solve the timeout.</p></li>
</ul>
</section>
</section>
<section id="sep-2-2024">
<h2><a class="toc-backref" href="#id41" role="doc-backlink">2.3.2 (Sep 2, 2024)</a><a class="headerlink" href="#sep-2-2024" title="Link to this heading"></a></h2>
<section id="id8">
<h3><a class="toc-backref" href="#id42" role="doc-backlink">Features</a><a class="headerlink" href="#id8" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[feat] Global Notifications New UI</p></li>
</ul>
</section>
</section>
<section id="jul-24-2024">
<h2><a class="toc-backref" href="#id43" role="doc-backlink">2.2.0 (Jul 24, 2024)</a><a class="headerlink" href="#jul-24-2024" title="Link to this heading"></a></h2>
<section id="id9">
<h3><a class="toc-backref" href="#id44" role="doc-backlink">Features</a><a class="headerlink" href="#id9" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[feat] Job execution status in browser tab</p></li>
</ul>
</section>
</section>
<section id="jul-8-2024">
<h2><a class="toc-backref" href="#id45" role="doc-backlink">2.1.6 (Jul 8, 2024)</a><a class="headerlink" href="#jul-8-2024" title="Link to this heading"></a></h2>
<section id="id10">
<h3><a class="toc-backref" href="#id46" role="doc-backlink">Features</a><a class="headerlink" href="#id10" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[bugfix] Call trace performance improvements</p></li>
<li><p>[feat] Re-run feature: A rule that timed out can be re-submitted as individual job (experimental, for selected users only)</p></li>
<li><p>[feat] Allow the user to logout from rule report</p></li>
</ul>
</section>
</section>
<section id="may-15-2024">
<h2><a class="toc-backref" href="#id47" role="doc-backlink">2.0.1 (May 15, 2024)</a><a class="headerlink" href="#may-15-2024" title="Link to this heading"></a></h2>
<section id="id11">
<h3><a class="toc-backref" href="#id48" role="doc-backlink">Features</a><a class="headerlink" href="#id11" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[feat] Support for jump to source from variables tab</p></li>
<li><p>[feat] Support for jump to source from live statistics tab</p></li>
<li><p>[feat] Allow the call trace to be expanded to full screen</p></li>
</ul>
</section>
<section id="id12">
<h3><a class="toc-backref" href="#id49" role="doc-backlink">Fixed Bugs</a><a class="headerlink" href="#id12" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[fix] Expansion bug on the main UI grid</p></li>
<li><p>[fix] Fixes for the call trace tracking points</p></li>
</ul>
</section>
</section>
<section id="apr-11-2024">
<h2><a class="toc-backref" href="#id50" role="doc-backlink">1.0.0 (Apr 11, 2024)</a><a class="headerlink" href="#apr-11-2024" title="Link to this heading"></a></h2>
<section id="id13">
<h3><a class="toc-backref" href="#id51" role="doc-backlink">Features</a><a class="headerlink" href="#id13" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[feat] Jump To Source: Animation to highlight already selected line on button click</p></li>
<li><p>[feat] New Job Configuration Tab that provides details on all arguments and inputs of a job that has been executed with (main contract, solidity version, all Prover flags and CLI options)</p></li>
<li><p>[feat] Browser tab title now indicates the main contract and the message of the job to simplify identification of a job</p></li>
<li><p>[feat] Files with extension <code class="docutils literal notranslate"><span class="pre">.yul</span></code> - <a class="reference external" href="https://docs.soliditylang.org/en/latest/yul.html">Yul files</a> - can be displayed in the editor</p></li>
</ul>
</section>
<section id="id14">
<h3><a class="toc-backref" href="#id52" role="doc-backlink">Fixed Bugs</a><a class="headerlink" href="#id14" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[fix] When a job has been canceled or halted, only rules that were running are being displayed as killed</p></li>
</ul>
</section>
</section>
<section id="mar-11-2024">
<h2><a class="toc-backref" href="#id53" role="doc-backlink">0.8.0 (Mar 11, 2024)</a><a class="headerlink" href="#mar-11-2024" title="Link to this heading"></a></h2>
<section id="id15">
<h3><a class="toc-backref" href="#id54" role="doc-backlink">Features</a><a class="headerlink" href="#id15" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[feat] Jump To Source Feature (works only in combination with Certora version later than 7.1.0)</p></li>
<li><p>[feat] New tooltips on labels for the call trace</p></li>
</ul>
</section>
<section id="id16">
<h3><a class="toc-backref" href="#id55" role="doc-backlink">Fixed Bugs</a><a class="headerlink" href="#id16" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[fix] Fixed tracking points</p></li>
<li><p>[fix] Fixed sharing button</p></li>
</ul>
</section>
</section>
<section id="feb-12-2024">
<h2><a class="toc-backref" href="#id56" role="doc-backlink">0.7.0 (Feb 12, 2024)</a><a class="headerlink" href="#feb-12-2024" title="Link to this heading"></a></h2>
<section id="id17">
<h3><a class="toc-backref" href="#id57" role="doc-backlink">Fixed Bugs</a><a class="headerlink" href="#id17" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[fix] Fixed bug when collapsing the left pane of the main grid</p></li>
<li><p>[fix] Fixed bug when collapsing entries in the call trace</p></li>
</ul>
</section>
</section>
<section id="jan-31-2024">
<h2><a class="toc-backref" href="#id58" role="doc-backlink">0.6.0 (Jan 31, 2024)</a><a class="headerlink" href="#jan-31-2024" title="Link to this heading"></a></h2>
<section id="id18">
<h3><a class="toc-backref" href="#id59" role="doc-backlink">Features</a><a class="headerlink" href="#id18" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[feat] Live Difficulty Statistics</p></li>
<li><p>[feat] Adding tool tips to status</p></li>
</ul>
</section>
<section id="id19">
<h3><a class="toc-backref" href="#id60" role="doc-backlink">Fixed Bugs</a><a class="headerlink" href="#id19" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[fix] Fixed file contents were shown to be loading for indefinite time</p></li>
</ul>
</section>
</section>
<section id="nov-26-2023">
<h2><a class="toc-backref" href="#id61" role="doc-backlink">0.5.7 (Nov 26, 2023)</a><a class="headerlink" href="#nov-26-2023" title="Link to this heading"></a></h2>
<section id="id20">
<h3><a class="toc-backref" href="#id62" role="doc-backlink">Features</a><a class="headerlink" href="#id20" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[feat] Improvements on naming for global / rule notifications</p></li>
</ul>
</section>
</section>
<section id="feb-11-2024">
<h2><a class="toc-backref" href="#id63" role="doc-backlink">0.5.62 (Feb 11, 2024)</a><a class="headerlink" href="#feb-11-2024" title="Link to this heading"></a></h2>
<section id="id21">
<h3><a class="toc-backref" href="#id64" role="doc-backlink">Fixed Bugs</a><a class="headerlink" href="#id21" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[fix] Fixed removed links to deprecated Certora Forum</p></li>
</ul>
</section>
</section>
<section id="october-24-2023">
<h2><a class="toc-backref" href="#id65" role="doc-backlink">0.5.6 (October 24, 2023)</a><a class="headerlink" href="#october-24-2023" title="Link to this heading"></a></h2>
<section id="id22">
<h3><a class="toc-backref" href="#id66" role="doc-backlink">Features</a><a class="headerlink" href="#id22" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[feat] Shareable report button</p></li>
<li><p>[feat] Foldable call trace</p></li>
<li><p>[feat] Added view of <code class="docutils literal notranslate"><span class="pre">.conf</span></code> files in the source files tab</p></li>
<li><p>[feat] New Tracking Points feature in the call trace</p></li>
<li><p>[feat] Added support for Witness examples view</p></li>
<li><p>[feat] Added link to the unsat core page inside info tab</p></li>
<li><p>[feat] Added job status at the top level</p></li>
<li><p>[feat] Default first load of the report shows the spec file and rules tab only</p></li>
<li><p>[feat] Display the report version in the info tab</p></li>
<li><p>[feat] Added a floating column option for the main sidebar</p></li>
<li><p>[feat] Added animated icons for jobs status in progress</p></li>
<li><p>[feat] Files tab keeps expanded files state</p></li>
<li><p>[feat] Improved filter, filter highlight, and search highlight functionality inside call resolutions</p></li>
<li><p>[feat] Added code editor scroll position to state</p></li>
<li><p>[feat] Added columns width to local storage</p></li>
<li><p>[feat] Removed cancel job button from the report</p></li>
<li><p>[feat] Removed auto-scroll in call Trace</p></li>
<li><p>[feat] Improved drop filters</p></li>
<li><p>[feat] Improved component’s state handling</p></li>
<li><p>[feat] Added upload failed view</p></li>
</ul>
</section>
<section id="id23">
<h3><a class="toc-backref" href="#id67" role="doc-backlink">Fixed Bugs</a><a class="headerlink" href="#id23" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p>[bugfix] Fixed the issue of selected file not being shown in the file tree</p></li>
<li><p>[bugfix] Fixed call resolution empty state issue</p></li>
<li><p>[bugfix] Fixed global problems empty state issue</p></li>
<li><p>[bugfix] Support for view of files with same name in different folders</p></li>
<li><p>[bugfix] Support file opening twice</p></li>
<li><p>[bugfix] Fixed handling collapse functionality when data is filtered</p></li>
<li><p>[bugfix] Fixed Firefox warnings on the source files tab</p></li>
<li><p>[bugfix] Fixed filter and collapse on contracts and global call resolution tabs to be consistent</p></li>
<li><p>[bugfix] Fixed contracts tab to show more/less and line breaks</p></li>
<li><p>[bugfix] Fixed UI breaking when selecting a new rule</p></li>
<li><p>[bugfix] Fixed issue of multi counter example shown without call trace</p></li>
<li><p>[bugfix] Fixed call resolution opening two items by default instead of one</p></li>
<li><p>[bugfix] Fixed view of job run time to excluded the time the job waited in the queue</p></li>
<li><p>[bugfix] Fixed variables sorting order</p></li>
</ul>
</section>
</section>
</section>


           </div>
          </div>
          <footer><div class="rst-footer-buttons" role="navigation" aria-label="Footer">
        <a href="prover_changelog.html" class="btn btn-neutral float-left" title="Prover Release Notes" accesskey="p" rel="prev"><span class="fa fa-arrow-circle-left" aria-hidden="true"></span> Previous</a>
        <a href="../../sunbeam/index.html" class="btn btn-neutral float-right" title="Sunbeam: Verification for Soroban" accesskey="n" rel="next">Next <span class="fa fa-arrow-circle-right" aria-hidden="true"></span></a>
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