<!DOCTYPE html><html class="" lang="en" data-content_root="../"><head><meta charset="utf-8">
    <meta name="viewport" content="width=device-width,initial-scale=1">
    <meta name="color-scheme" content="light dark"><meta name="viewport" content="width=device-width, initial-scale=1">
<link rel="index" title="Index" href="../genindex.html"><link rel="search" title="Search" href="../search.html"><link rel="next" title="3. Understanding violations" href="../lesson3_violations/index.html"><link rel="prev" title="2.6. Using config files" href="config_files.html">

    <!-- Generated with Sphinx 7.4.5 and Furo 2024.05.06 -->
        <title>2.7. Vacuity - Certora Prover Tutorials</title>
      <link rel="stylesheet" type="text/css" href="../_static/pygments.css?v=a746c00c">
    <link rel="stylesheet" type="text/css" href="../_static/styles/furo.css?v=387cc868">
    <link rel="stylesheet" type="text/css" href="../_static/graphviz.css?v=fd3f3429">
    <link rel="stylesheet" type="text/css" href="../_static/sphinx-design.min.css?v=87e54e7c">
    <link rel="stylesheet" type="text/css" href="../_static/styles/furo-extensions.css?v=36a5483c">
    
    


<style>
  body {
    --color-code-background: #f8f8f8;
  --color-code-foreground: black;
  
  }
  @media not print {
    body[data-theme="dark"] {
      --color-code-background: #202020;
  --color-code-foreground: #d0d0d0;
  
    }
    @media (prefers-color-scheme: dark) {
      body:not([data-theme="light"]) {
        --color-code-background: #202020;
  --color-code-foreground: #d0d0d0;
  
      }
    }
  }
</style><script async="" type="text/javascript" src="/_/static/javascript/readthedocs-addons.js"></script><meta name="readthedocs-project-slug" content="certora-cvl2-tutorials-package"><meta name="readthedocs-version-slug" content="latest"><meta name="readthedocs-resolver-filename" content="/lesson2_started/vacuity.html"><meta name="readthedocs-http-status" content="200"></head>
  <body data-theme="auto">
    
    <script>
      document.body.dataset.theme = localStorage.getItem("theme") || "auto";
    </script>
    

<svg xmlns="http://www.w3.org/2000/svg" style="display: none;">
  <symbol id="svg-toc" viewBox="0 0 24 24">
    <title>Contents</title>
    <svg stroke="currentColor" fill="currentColor" stroke-width="0" viewBox="0 0 1024 1024">
      <path d="M408 442h480c4.4 0 8-3.6 8-8v-56c0-4.4-3.6-8-8-8H408c-4.4 0-8 3.6-8 8v56c0 4.4 3.6 8 8 8zm-8 204c0 4.4 3.6 8 8 8h480c4.4 0 8-3.6 8-8v-56c0-4.4-3.6-8-8-8H408c-4.4 0-8 3.6-8 8v56zm504-486H120c-4.4 0-8 3.6-8 8v56c0 4.4 3.6 8 8 8h784c4.4 0 8-3.6 8-8v-56c0-4.4-3.6-8-8-8zm0 632H120c-4.4 0-8 3.6-8 8v56c0 4.4 3.6 8 8 8h784c4.4 0 8-3.6 8-8v-56c0-4.4-3.6-8-8-8zM115.4 518.9L271.7 642c5.8 4.6 14.4.5 14.4-6.9V388.9c0-7.4-8.5-11.5-14.4-6.9L115.4 505.1a8.74 8.74 0 0 0 0 13.8z"></path>
    </svg>
  </symbol>
  <symbol id="svg-menu" viewBox="0 0 24 24">
    <title>Menu</title>
    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="feather-menu">
      <line x1="3" y1="12" x2="21" y2="12"></line>
      <line x1="3" y1="6" x2="21" y2="6"></line>
      <line x1="3" y1="18" x2="21" y2="18"></line>
    </svg>
  </symbol>
  <symbol id="svg-arrow-right" viewBox="0 0 24 24">
    <title>Expand</title>
    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="feather-chevron-right">
      <polyline points="9 18 15 12 9 6"></polyline>
    </svg>
  </symbol>
  <symbol id="svg-sun" viewBox="0 0 24 24">
    <title>Light mode</title>
    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1" stroke-linecap="round" stroke-linejoin="round" class="feather-sun">
      <circle cx="12" cy="12" r="5"></circle>
      <line x1="12" y1="1" x2="12" y2="3"></line>
      <line x1="12" y1="21" x2="12" y2="23"></line>
      <line x1="4.22" y1="4.22" x2="5.64" y2="5.64"></line>
      <line x1="18.36" y1="18.36" x2="19.78" y2="19.78"></line>
      <line x1="1" y1="12" x2="3" y2="12"></line>
      <line x1="21" y1="12" x2="23" y2="12"></line>
      <line x1="4.22" y1="19.78" x2="5.64" y2="18.36"></line>
      <line x1="18.36" y1="5.64" x2="19.78" y2="4.22"></line>
    </svg>
  </symbol>
  <symbol id="svg-moon" viewBox="0 0 24 24">
    <title>Dark mode</title>
    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1" stroke-linecap="round" stroke-linejoin="round" class="icon-tabler-moon">
      <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
      <path d="M12 3c.132 0 .263 0 .393 0a7.5 7.5 0 0 0 7.92 12.446a9 9 0 1 1 -8.313 -12.454z"></path>
    </svg>
  </symbol>
  <symbol id="svg-sun-half" viewBox="0 0 24 24">
    <title>Auto light/dark mode</title>
    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1" stroke-linecap="round" stroke-linejoin="round" class="icon-tabler-shadow">
      <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
      <circle cx="12" cy="12" r="9"></circle>
      <path d="M13 12h5"></path>
      <path d="M13 15h4"></path>
      <path d="M13 18h1"></path>
      <path d="M13 9h4"></path>
      <path d="M13 6h1"></path>
    </svg>
  </symbol>
  <symbol id="svg-sun-with-moon" viewBox="0 0 24 24">
    <title>Auto light/dark, in light mode</title>
    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1" stroke-linecap="round" stroke-linejoin="round" class="icon-custom-derived-from-feather-sun-and-tabler-moon">
      <path style="opacity: 50%" d="M 5.411 14.504 C 5.471 14.504 5.532 14.504 5.591 14.504 C 3.639 16.319 4.383 19.569 6.931 20.352 C 7.693 20.586 8.512 20.551 9.25 20.252 C 8.023 23.207 4.056 23.725 2.11 21.184 C 0.166 18.642 1.702 14.949 4.874 14.536 C 5.051 14.512 5.231 14.5 5.411 14.5 L 5.411 14.504 Z"></path>
      <line x1="14.5" y1="3.25" x2="14.5" y2="1.25"></line>
      <line x1="14.5" y1="15.85" x2="14.5" y2="17.85"></line>
      <line x1="10.044" y1="5.094" x2="8.63" y2="3.68"></line>
      <line x1="19" y1="14.05" x2="20.414" y2="15.464"></line>
      <line x1="8.2" y1="9.55" x2="6.2" y2="9.55"></line>
      <line x1="20.8" y1="9.55" x2="22.8" y2="9.55"></line>
      <line x1="10.044" y1="14.006" x2="8.63" y2="15.42"></line>
      <line x1="19" y1="5.05" x2="20.414" y2="3.636"></line>
      <circle cx="14.5" cy="9.55" r="3.6"></circle>
    </svg>
  </symbol>
  <symbol id="svg-moon-with-sun" viewBox="0 0 24 24">
    <title>Auto light/dark, in dark mode</title>
    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1" stroke-linecap="round" stroke-linejoin="round" class="icon-custom-derived-from-feather-sun-and-tabler-moon">
      <path d="M 8.282 7.007 C 8.385 7.007 8.494 7.007 8.595 7.007 C 5.18 10.184 6.481 15.869 10.942 17.24 C 12.275 17.648 13.706 17.589 15 17.066 C 12.851 22.236 5.91 23.143 2.505 18.696 C -0.897 14.249 1.791 7.786 7.342 7.063 C 7.652 7.021 7.965 7 8.282 7 L 8.282 7.007 Z"></path>
      <line style="opacity: 50%" x1="18" y1="3.705" x2="18" y2="2.5"></line>
      <line style="opacity: 50%" x1="18" y1="11.295" x2="18" y2="12.5"></line>
      <line style="opacity: 50%" x1="15.316" y1="4.816" x2="14.464" y2="3.964"></line>
      <line style="opacity: 50%" x1="20.711" y1="10.212" x2="21.563" y2="11.063"></line>
      <line style="opacity: 50%" x1="14.205" y1="7.5" x2="13.001" y2="7.5"></line>
      <line style="opacity: 50%" x1="21.795" y1="7.5" x2="23" y2="7.5"></line>
      <line style="opacity: 50%" x1="15.316" y1="10.184" x2="14.464" y2="11.036"></line>
      <line style="opacity: 50%" x1="20.711" y1="4.789" x2="21.563" y2="3.937"></line>
      <circle style="opacity: 50%" cx="18" cy="7.5" r="2.169"></circle>
    </svg>
  </symbol>
  <symbol id="svg-pencil" viewBox="0 0 24 24">
    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1" stroke-linecap="round" stroke-linejoin="round" class="icon-tabler-pencil-code">
      <path d="M4 20h4l10.5 -10.5a2.828 2.828 0 1 0 -4 -4l-10.5 10.5v4"></path>
      <path d="M13.5 6.5l4 4"></path>
      <path d="M20 21l2 -2l-2 -2"></path>
      <path d="M17 17l-2 2l2 2" <="" svg="">
  </path></svg></symbol>
  <symbol id="svg-eye" viewBox="0 0 24 24">
    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1" stroke-linecap="round" stroke-linejoin="round" class="icon-tabler-eye-code">
      <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
      <path d="M10 12a2 2 0 1 0 4 0a2 2 0 0 0 -4 0"></path>
      <path d="M11.11 17.958c-3.209 -.307 -5.91 -2.293 -8.11 -5.958c2.4 -4 5.4 -6 9 -6c3.6 0 6.6 2 9 6c-.21 .352 -.427 .688 -.647 1.008"></path>
      <path d="M20 21l2 -2l-2 -2"></path>
      <path d="M17 17l-2 2l2 2"></path>
    </svg>
  </symbol>
</svg>

<input type="checkbox" class="sidebar-toggle" name="__navigation" id="__navigation">
<input type="checkbox" class="sidebar-toggle" name="__toc" id="__toc">
<label class="overlay sidebar-overlay" for="__navigation">
  <div class="visually-hidden">Hide navigation sidebar</div>
</label>
<label class="overlay toc-overlay" for="__toc">
  <div class="visually-hidden">Hide table of contents sidebar</div>
</label>

<a class="skip-to-content muted-link" href="#furo-main-content">Skip to content</a>



<div class="page">
  <header class="mobile-header">
    <div class="header-left">
      <label class="nav-overlay-icon" for="__navigation">
        <div class="visually-hidden">Toggle site navigation sidebar</div>
        <i class="icon"><svg><use href="#svg-menu"></use></svg></i>
      </label>
    </div>
    <div class="header-center">
      <a href="../index.html"><div class="brand">Certora Prover Tutorials</div></a>
    </div>
    <div class="header-right">
      <div class="theme-toggle-container theme-toggle-header">
        <button class="theme-toggle">
          <div class="visually-hidden">Toggle Light / Dark / Auto color theme</div>
          <svg class="theme-icon-when-auto-light"><use href="#svg-sun-with-moon"></use></svg>
          <svg class="theme-icon-when-auto-dark"><use href="#svg-moon-with-sun"></use></svg>
          <svg class="theme-icon-when-dark"><use href="#svg-moon"></use></svg>
          <svg class="theme-icon-when-light"><use href="#svg-sun"></use></svg>
        </button>
      </div>
      <label class="toc-overlay-icon toc-header-icon" for="__toc">
        <div class="visually-hidden">Toggle table of contents sidebar</div>
        <i class="icon"><svg><use href="#svg-toc"></use></svg></i>
      </label>
    </div>
  </header>
  <aside class="sidebar-drawer">
    <div class="sidebar-container">
      
      <div class="sidebar-sticky"><a class="sidebar-brand" href="../index.html">
  
  <div class="sidebar-logo-container">
    <img class="sidebar-logo only-light" src="../_static/logo.svg" alt="Light Logo" width="164" height="42">
    <img class="sidebar-logo only-dark" src="../_static/logo.svg" alt="Dark Logo">
  </div>
  
  <span class="sidebar-brand-text">Certora Prover Tutorials</span>
  
</a><form class="sidebar-search-container" method="get" action="../search.html" role="search">
  <input class="sidebar-search" placeholder="Search" name="q" aria-label="Search">
  <input type="hidden" name="check_keywords" value="yes">
  <input type="hidden" name="area" value="default">
</form>
<div id="searchbox"></div><div class="sidebar-scroll"><div class="sidebar-tree">
  <p class="caption" role="heading"><span class="caption-text">Contents:</span></p>
<ul class="current">
<li class="toctree-l1 has-children"><a class="reference internal" href="../lesson1_prerequisites/index.html">1. Background and Prerequisites</a><input class="toctree-checkbox" id="toctree-checkbox-1" name="toctree-checkbox-1" role="switch" type="checkbox"><label for="toctree-checkbox-1"><div class="visually-hidden">Toggle navigation of 1. Background and Prerequisites</div><i class="icon"><svg><use href="#svg-arrow-right"></use></svg></i></label><ul>
<li class="toctree-l2"><a class="reference internal" href="../lesson1_prerequisites/background.html">1.1. Background</a></li>
<li class="toctree-l2"><a class="reference internal" href="../lesson1_prerequisites/propositional_logic.html">1.2. Introduction to predicate logic</a></li>
<li class="toctree-l2"><a class="reference internal" href="../lesson1_prerequisites/formal_verification.html">1.3. Introduction to formal verification</a></li>
</ul>
</li>
<li class="toctree-l1 current has-children"><a class="reference internal" href="index.html">2. Getting Started</a><input checked="" class="toctree-checkbox" id="toctree-checkbox-2" name="toctree-checkbox-2" role="switch" type="checkbox"><label for="toctree-checkbox-2"><div class="visually-hidden">Toggle navigation of 2. Getting Started</div><i class="icon"><svg><use href="#svg-arrow-right"></use></svg></i></label><ul class="current">
<li class="toctree-l2"><a class="reference internal" href="installation.html">2.1. Installation and Setup</a></li>
<li class="toctree-l2"><a class="reference internal" href="overview.html">2.2. Technology Overview</a></li>
<li class="toctree-l2"><a class="reference internal" href="erc20_example.html">2.3. ERC20 Example - Basics</a></li>
<li class="toctree-l2"><a class="reference internal" href="preconditions.html">2.4. ERC20 Example - preconditions</a></li>
<li class="toctree-l2"><a class="reference internal" href="parametric.html">2.5. Parametric rules</a></li>
<li class="toctree-l2"><a class="reference internal" href="config_files.html">2.6. Using config files</a></li>
<li class="toctree-l2 current current-page"><a class="current reference internal" href="#">2.7. Vacuity</a></li>
</ul>
</li>
<li class="toctree-l1 has-children"><a class="reference internal" href="../lesson3_violations/index.html">3. Understanding violations</a><input class="toctree-checkbox" id="toctree-checkbox-3" name="toctree-checkbox-3" role="switch" type="checkbox"><label for="toctree-checkbox-3"><div class="visually-hidden">Toggle navigation of 3. Understanding violations</div><i class="icon"><svg><use href="#svg-arrow-right"></use></svg></i></label><ul>
<li class="toctree-l2"><a class="reference internal" href="../lesson3_violations/erc20_bugs.html">3.1. Fixing ERC20 spec</a></li>
<li class="toctree-l2"><a class="reference internal" href="../lesson3_violations/borda_bugs.html">3.2. Borda count election</a></li>
<li class="toctree-l2"><a class="reference internal" href="../lesson3_violations/reward_challenge.html">3.3. Reward Challenge : Missing Spec bounty</a></li>
</ul>
</li>
<li class="toctree-l1 has-children"><a class="reference internal" href="../lesson4_invariants/index.html">4. Invariants and Ghosts</a><input class="toctree-checkbox" id="toctree-checkbox-4" name="toctree-checkbox-4" role="switch" type="checkbox"><label for="toctree-checkbox-4"><div class="visually-hidden">Toggle navigation of 4. Invariants and Ghosts</div><i class="icon"><svg><use href="#svg-arrow-right"></use></svg></i></label><ul>
<li class="toctree-l2"><a class="reference internal" href="../lesson4_invariants/invariants/simple.html">4.1. Simple invariants examples</a></li>
<li class="toctree-l2"><a class="reference internal" href="../lesson4_invariants/invariants/auction.html">4.2. Basic exercises</a></li>
<li class="toctree-l2"><a class="reference internal" href="../lesson4_invariants/invariants/preserved.html">4.3. Preserved blocks</a></li>
<li class="toctree-l2"><a class="reference internal" href="../lesson4_invariants/ghosts/basics.html">4.4. Ghosts and hooks</a></li>
<li class="toctree-l2"><a class="reference internal" href="../lesson4_invariants/ghosts/exercises.html">4.5. Ghost exercises</a></li>
</ul>
</li>
</ul>
<ul>
<li class="toctree-l1"><a class="reference internal" href="../genindex.html">Index</a></li>
</ul>

</div>
</div>

      </div>
      
    </div>
  </aside>
  <div class="main">
    <div class="content">
      <div class="article-container">
        <a href="#" class="back-to-top muted-link">
          <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24">
            <path d="M13 20h-2V8l-5.5 5.5-1.42-1.42L12 4.16l7.92 7.92-1.42 1.42L13 8v12z"></path>
          </svg>
          <span>Back to top</span>
        </a>
        <div class="content-icon-container">
          <div class="theme-toggle-container theme-toggle-content">
            <button class="theme-toggle">
              <div class="visually-hidden">Toggle Light / Dark / Auto color theme</div>
              <svg class="theme-icon-when-auto-light"><use href="#svg-sun-with-moon"></use></svg>
              <svg class="theme-icon-when-auto-dark"><use href="#svg-moon-with-sun"></use></svg>
              <svg class="theme-icon-when-dark"><use href="#svg-moon"></use></svg>
              <svg class="theme-icon-when-light"><use href="#svg-sun"></use></svg>
            </button>
          </div>
          <label class="toc-overlay-icon toc-content-icon" for="__toc">
            <div class="visually-hidden">Toggle table of contents sidebar</div>
            <i class="icon"><svg><use href="#svg-toc"></use></svg></i>
          </label>
        </div>
        <article role="main" id="furo-main-content">
          <section id="vacuity">
<span id="sec-vacuity"></span><h1><span class="section-number">2.7. </span>Vacuity<a class="headerlink" href="#vacuity" title="Link to this heading">¶</a></h1>
<section id="introduction">
<h2>Introduction<a class="headerlink" href="#introduction" title="Link to this heading">¶</a></h2>
<p>A rule is called <em>vacuous</em> if there are no computation paths satisfying the necessary
requirements (excluding the rule’s assertions). The Prover can find no counter-examples
for such rules, since there are no examples whatsoever for such rules.
By default, the Prover will mark such rules as <em>verfied</em>, but they are in fact
meaningless.</p>
<p>The solution is to use the Prover’s built-in <em>rule sanity</em>. Adding
<code class="docutils literal notranslate"><span class="pre">--rule_sanity</span> <span class="pre">basic</span></code> to the command line, or <code class="docutils literal notranslate"><span class="pre">"rule_sanity":</span> <span class="pre">"basic"</span></code> to the
config file will cause the Prover to check if the rules being verified are
vacuous.</p>
</section>
<section id="simple-example">
<h2>Simple Example<a class="headerlink" href="#simple-example" title="Link to this heading">¶</a></h2>
<p>Here is a simple example for a vacuous rule, containing contradictory requirements.</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre><span></span><span class="k">rule</span><span class="w"> </span><span class="nc">simpleVacuousRule</span><span class="p">(</span><span class="kt">uint256</span><span class="w"> </span>x<span class="p">,</span><span class="w"> </span><span class="kt">uint256</span><span class="w"> </span>y<span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="c1">// Contradictory requirement</span>
<span class="w">    </span><span class="kr">require</span><span class="w"> </span><span class="p">(</span>x<span class="w"> </span><span class="o">&gt;</span><span class="w"> </span>y<span class="p">)</span><span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span><span class="p">(</span>y<span class="w"> </span><span class="o">&gt;</span><span class="w"> </span>x<span class="p">);</span>
<span class="w">    </span><span class="kr">assert</span><span class="w"> </span><span class="kr">false</span><span class="p">;</span><span class="w">  </span><span class="c1">// Should always fail</span>
<span class="p">}</span>
</pre></div>
</div>
<p>When running without <code class="docutils literal notranslate"><span class="pre">rule_sanity</span></code>, the Prover will mark this rule as <em>verified</em>
since it has no counter-example, even though the assertion can never be satisfied.
When using <code class="docutils literal notranslate"><span class="pre">rule_sanity</span></code> the Prover will indicate this rule fails sanity checks.</p>
</section>
<section id="reverting-computation-paths">
<span id="index-0"></span><h2>Reverting computation paths<a class="headerlink" href="#reverting-computation-paths" title="Link to this heading">¶</a></h2>
<p>By default, the Prover ignores computation paths that result in a revert. So, by default
the Prover considers only those computation paths where all Solidity <code class="code highlight solidity docutils literal highlight-solidity"><span class="kt">require</span></code>
statements are satisfied. Moreover, any overflow or underflow paths are ignored
(when using Solidity versions that revert on overflow and underflow).</p>
<p>To include computation paths that result in a revert, use the operator
<code class="code highlight cvl docutils literal highlight-cvl"><span class="ow">@withrevert</span></code> when calling a Solidity function, e.g.
<code class="code highlight cvl docutils literal highlight-cvl">someFunction<span class="ow">@withrevert</span><span class="p">(</span>args<span class="p">)</span></code>. CVL has a builtin boolean variable
<code class="code highlight cvl docutils literal highlight-cvl"><span class="nb">lastReverted</span></code> that is true if the <em>last</em> Solidity function called reverted
(whether it used <code class="code highlight cvl docutils literal highlight-cvl"><span class="ow">@withrevert</span></code> or not).</p>
<p>Note that if the call <code class="code highlight cvl docutils literal highlight-cvl">someFunction<span class="ow">@withrevert</span><span class="p">(</span>args<span class="p">)</span></code> does revert, its return
value will be arbitrary, and all Solidity variables will also revert.</p>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>In <a class="reference internal" href="../lesson4_invariants/ghosts/basics.html#lesson4-ghosts-basics"><span class="std std-ref">Ghosts and hooks</span></a> we will learn about <em>ghost variables</em>, which are
roughly CVL global variables. When a Solidity function reverts, all ghost
variables also revert.</p>
</div>
</section>
<section id="more-examples">
<h2>More examples<a class="headerlink" href="#more-examples" title="Link to this heading">¶</a></h2>
<p>We’ll use the following simple contract, the code is found in
<a class="reference external" href="https://github.com/Certora/tutorials-code/blob/master/lesson2_started/vacuity/Vacuous.sol">Vacuous.sol</a>.</p>
<div class="highlight-solidity notranslate"><div class="highlight"><pre><span></span><span class="k">pragma solidity</span><span class="w"> </span><span class="o">^</span><span class="k">0.8.0</span><span class="p">;</span>

<span class="c1">/// @title Examples of vacuous rules</span>
<span class="k">contract</span><span class="w"> </span><span class="ni">Vacuous</span><span class="w"> </span><span class="p">{</span>

<span class="w">  </span><span class="kt">mapping</span><span class="w"> </span><span class="p">(</span><span class="kt">address</span><span class="w"> </span><span class="o">=&gt;</span><span class="w"> </span><span class="kt">uint256</span><span class="p">)</span><span class="w"> </span><span class="kt">public</span><span class="w"> </span>amounts<span class="p">;</span>
<span class="w">  </span><span class="kt">uint256</span><span class="w"> </span><span class="k">public </span><span class="nv">immutable</span><span class="w"> </span>maximalAmount<span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="m m-Decimal">1000</span><span class="p">;</span>

<span class="w">  </span><span class="kt">function</span><span class="w"> </span><span class="nv">add</span><span class="p">(</span><span class="kt">address</span><span class="w"> </span><span class="nv">user</span><span class="p">,</span><span class="w"> </span><span class="kt">uint256</span><span class="w"> </span><span class="nv">amount</span><span class="p">)</span><span class="w"> </span><span class="kt">public</span><span class="w"> </span><span class="kt">returns</span><span class="w"> </span><span class="p">(</span><span class="kt">uint256</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kt">require</span><span class="p">(</span>amounts<span class="p">[</span>user<span class="p">]</span><span class="w"> </span><span class="o">+</span><span class="w"> </span>amount<span class="w"> </span><span class="o">&lt;=</span><span class="w"> </span>maximalAmount<span class="p">);</span>
<span class="w">    </span>amounts<span class="p">[</span>user<span class="p">]</span><span class="w"> </span><span class="o">+=</span><span class="w"> </span>amount<span class="p">;</span>
<span class="w">    </span><span class="kt">return</span><span class="w"> </span>amounts<span class="p">[</span>user<span class="p">];</span>
<span class="w">  </span><span class="p">}</span>

<span class="w">  </span><span class="kt">function</span><span class="w"> </span><span class="nv">sub</span><span class="p">(</span><span class="kt">address</span><span class="w"> </span><span class="nv">user</span><span class="p">,</span><span class="w"> </span><span class="kt">uint256</span><span class="w"> </span><span class="nv">amount</span><span class="p">)</span><span class="w"> </span><span class="kt">public</span><span class="w"> </span><span class="kt">returns</span><span class="w"> </span><span class="p">(</span><span class="kt">uint256</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span>amounts<span class="p">[</span>user<span class="p">]</span><span class="w"> </span><span class="o">-=</span><span class="w"> </span>amount<span class="p">;</span>
<span class="w">    </span><span class="kt">return</span><span class="w"> </span>amounts<span class="p">[</span>user<span class="p">];</span>
<span class="w">  </span><span class="p">}</span>
<span class="p">}</span>
</pre></div>
</div>
<p>The following CVL examples are from
<a class="reference external" href="https://github.com/Certora/tutorials-code/blob/master/lesson2_started/vacuity/Vacuous.spec">Vacuous.spec</a>. In the same folder
there are also two config files for running this spec. One config file without
<code class="docutils literal notranslate"><span class="pre">rule_sanity</span></code>: <a class="reference external" href="https://github.com/Certora/tutorials-code/blob/master/lesson2_started/vacuity/Vacuous.conf">Vacuous.conf</a>,
while the other uses basic <code class="docutils literal notranslate"><span class="pre">rule_sanity</span></code>:
<a class="reference external" href="https://github.com/Certora/tutorials-code/blob/master/lesson2_started/vacuity/Vacuous_sanity.conf">Vacuous_sanity.conf</a>.</p>
<section id="vacuous-rule">
<h3>Vacuous rule<a class="headerlink" href="#vacuous-rule" title="Link to this heading">¶</a></h3>
<p>The following rule is vacuous. It will be verified when running without <code class="docutils literal notranslate"><span class="pre">rule_sanity</span></code>.</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre><span></span><span class="k">rule</span><span class="w"> </span><span class="nc">subtleVacuousRule</span><span class="p">(</span><span class="kt">address</span><span class="w"> </span>user<span class="p">,</span><span class="w"> </span><span class="kt">uint256</span><span class="w"> </span>amount<span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kt">uint256</span><span class="w"> </span>userAmount<span class="w"> </span><span class="o">=</span><span class="w"> </span>amounts<span class="p">(</span>user<span class="p">);</span>
<span class="w">    </span><span class="kr">require</span><span class="w"> </span>amount<span class="w"> </span><span class="o">&gt;</span><span class="w"> </span>userAmount<span class="p">;</span>
<span class="w">    </span>sub<span class="p">(</span>user<span class="p">,</span><span class="w"> </span>amount<span class="p">);</span>
<span class="w">    </span><span class="kr">assert</span><span class="w"> </span><span class="kr">false</span><span class="p">;</span><span class="w">  </span><span class="c1">// Should always fail</span>
<span class="p">}</span>
</pre></div>
</div>
<p>Do you understand why this rule is vacuous?</p>
<details class="sd-sphinx-override sd-dropdown sd-card sd-mb-3 sd-fade-in-slide-down">
<summary class="sd-summary-title sd-card-header">
<span class="sd-summary-text">Answer</span><span class="sd-summary-state-marker sd-summary-chevron-right"><svg version="1.1" width="1.5em" height="1.5em" class="sd-octicon sd-octicon-chevron-right" viewBox="0 0 24 24" aria-hidden="true"><path d="M8.72 18.78a.75.75 0 0 1 0-1.06L14.44 12 8.72 6.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018l6.25 6.25a.75.75 0 0 1 0 1.06l-6.25 6.25a.75.75 0 0 1-1.06 0Z"></path></svg></span></summary><div class="sd-summary-content sd-card-body docutils">
<p class="sd-card-text">In the specified Solidity version, underflow will cause a revert.
The <code class="code highlight cvl docutils literal highlight-cvl"><span class="kr">require</span></code> statement in the rule forces underflow in the
Solidity <code class="code highlight solidity docutils literal highlight-solidity">sub</code> function. In the specified Solidity compileer version,
this underflow will cause a revert.</p>
</div>
</details></section>
<section id="using-withrevert">
<h3>Using withrevert<a class="headerlink" href="#using-withrevert" title="Link to this heading">¶</a></h3>
<p>This is similar to the previous example, but here we call <code class="code highlight solidity docutils literal highlight-solidity">sub</code> using the
<code class="code highlight cvl docutils literal highlight-cvl"><span class="ow">@withrevert</span></code> operator. We assert that the function will always revert.
This rule is correctly verified.</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre><span></span><span class="k">rule</span><span class="w"> </span><span class="nc">revertingRule</span><span class="p">(</span><span class="kt">address</span><span class="w"> </span>user<span class="p">,</span><span class="w"> </span><span class="kt">uint256</span><span class="w"> </span>amount<span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kt">uint256</span><span class="w"> </span>userAmount<span class="w"> </span><span class="o">=</span><span class="w"> </span>amounts<span class="p">(</span>user<span class="p">);</span>
<span class="w">    </span><span class="kr">require</span><span class="w"> </span>amount<span class="w"> </span><span class="o">&gt;</span><span class="w"> </span>userAmount<span class="p">;</span>
<span class="w">    </span>sub<span class="ow">@withrevert</span><span class="p">(</span>user<span class="p">,</span><span class="w"> </span>amount<span class="p">);</span>
<span class="w">    </span><span class="kr">assert</span><span class="w"> </span><span class="nb">lastReverted</span><span class="p">;</span>
<span class="p">}</span>
</pre></div>
</div>
</section>
</section>
</section>

        </article>
      </div>
      <footer>
        
        <div class="related-pages">
          <a class="next-page" href="../lesson3_violations/index.html">
              <div class="page-info">
                <div class="context">
                  <span>Next</span>
                </div>
                <div class="title"><span class="section-number">3. </span>Understanding violations</div>
              </div>
              <svg class="furo-related-icon"><use href="#svg-arrow-right"></use></svg>
            </a>
          <a class="prev-page" href="config_files.html">
              <svg class="furo-related-icon"><use href="#svg-arrow-right"></use></svg>
              <div class="page-info">
                <div class="context">
                  <span>Previous</span>
                </div>
                
                <div class="title"><span class="section-number">2.6. </span>Using config files</div>
                
              </div>
            </a>
        </div>
        <div class="bottom-of-page">
          <div class="left-details">
            <div class="copyright">
                Copyright © 2023, Certora, Inc
            </div>
            Made with <a href="https://www.sphinx-doc.org/">Sphinx</a> and <a class="muted-link" href="https://pradyunsg.me">@pradyunsg</a>'s
            
            <a href="https://github.com/pradyunsg/furo">Furo</a>
            
          </div>
          <div class="right-details">
            
          </div>
        </div>
        
      </footer>
    </div>
    <aside class="toc-drawer">
      
      
      <div class="toc-sticky toc-scroll">
        <div class="toc-title-container">
          <span class="toc-title">
            On this page
          </span>
        </div>
        <div class="toc-tree-container">
          <div class="toc-tree">
            <ul>
<li><a class="reference internal" href="#">2.7. Vacuity</a><ul>
<li><a class="reference internal" href="#introduction">Introduction</a></li>
<li><a class="reference internal" href="#simple-example">Simple Example</a></li>
<li><a class="reference internal" href="#reverting-computation-paths">Reverting computation paths</a></li>
<li><a class="reference internal" href="#more-examples">More examples</a><ul>
<li><a class="reference internal" href="#vacuous-rule">Vacuous rule</a></li>
<li><a class="reference internal" href="#using-withrevert">Using withrevert</a></li>
</ul>
</li>
</ul>
</li>
</ul>

          </div>
        </div>
      </div>
      
      
    </aside>
  </div>
</div><script src="../_static/documentation_options.js?v=b4795bba"></script>
    <script src="../_static/doctools.js?v=9a2dae69"></script>
    <script src="../_static/sphinx_highlight.js?v=dc90522c"></script>
    <script src="../_static/scripts/furo.js?v=4e2eecee"></script>
    <script src="../_static/design-tabs.js?v=f930bc37"></script>
    
</body></html>