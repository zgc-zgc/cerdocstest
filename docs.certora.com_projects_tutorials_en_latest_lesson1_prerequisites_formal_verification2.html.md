<!DOCTYPE html><html class="" lang="en" data-content_root="../"><head><meta charset="utf-8">
    <meta name="viewport" content="width=device-width,initial-scale=1">
    <meta name="color-scheme" content="light dark"><meta name="viewport" content="width=device-width, initial-scale=1">
<link rel="index" title="Index" href="../genindex.html"><link rel="search" title="Search" href="../search.html"><link rel="next" title="2. Getting Started" href="../lesson2_started/index.html"><link rel="prev" title="1.2. Introduction to predicate logic" href="propositional_logic.html">

    <!-- Generated with Sphinx 7.4.5 and Furo 2024.05.06 -->
        <title>1.3. Introduction to formal verification - Certora Prover Tutorials</title>
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
</style><script async="" type="text/javascript" src="/_/static/javascript/readthedocs-addons.js"></script><meta name="readthedocs-project-slug" content="certora-cvl2-tutorials-package"><meta name="readthedocs-version-slug" content="latest"><meta name="readthedocs-resolver-filename" content="/lesson1_prerequisites/formal_verification.html"><meta name="readthedocs-http-status" content="200"></head>
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
    <img class="sidebar-logo only-light" src="../_static/logo.svg" alt="Light Logo">
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
<li class="toctree-l1 current has-children"><a class="reference internal" href="index.html">1. Background and Prerequisites</a><input checked="" class="toctree-checkbox" id="toctree-checkbox-1" name="toctree-checkbox-1" role="switch" type="checkbox"><label for="toctree-checkbox-1"><div class="visually-hidden">Toggle navigation of 1. Background and Prerequisites</div><i class="icon"><svg><use href="#svg-arrow-right"></use></svg></i></label><ul class="current">
<li class="toctree-l2"><a class="reference internal" href="background.html">1.1. Background</a></li>
<li class="toctree-l2"><a class="reference internal" href="propositional_logic.html">1.2. Introduction to predicate logic</a></li>
<li class="toctree-l2 current current-page"><a class="current reference internal" href="#">1.3. Introduction to formal verification</a></li>
</ul>
</li>
<li class="toctree-l1 has-children"><a class="reference internal" href="../lesson2_started/index.html">2. Getting Started</a><input class="toctree-checkbox" id="toctree-checkbox-2" name="toctree-checkbox-2" role="switch" type="checkbox"><label for="toctree-checkbox-2"><div class="visually-hidden">Toggle navigation of 2. Getting Started</div><i class="icon"><svg><use href="#svg-arrow-right"></use></svg></i></label><ul>
<li class="toctree-l2"><a class="reference internal" href="../lesson2_started/installation.html">2.1. Installation and Setup</a></li>
<li class="toctree-l2"><a class="reference internal" href="../lesson2_started/overview.html">2.2. Technology Overview</a></li>
<li class="toctree-l2"><a class="reference internal" href="../lesson2_started/erc20_example.html">2.3. ERC20 Example - Basics</a></li>
<li class="toctree-l2"><a class="reference internal" href="../lesson2_started/preconditions.html">2.4. ERC20 Example - preconditions</a></li>
<li class="toctree-l2"><a class="reference internal" href="../lesson2_started/parametric.html">2.5. Parametric rules</a></li>
<li class="toctree-l2"><a class="reference internal" href="../lesson2_started/config_files.html">2.6. Using config files</a></li>
<li class="toctree-l2"><a class="reference internal" href="../lesson2_started/vacuity.html">2.7. Vacuity</a></li>
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
          <section id="introduction-to-formal-verification">
<span id="sec-introduction-to-formal"></span><h1><span class="section-number">1.3. </span>Introduction to formal verification<a class="headerlink" href="#introduction-to-formal-verification" title="Link to this heading">¶</a></h1>
<p>Formal verification is about <em>proving</em> <a class="reference external" href="https://en.wikipedia.org/wiki/Correctness_(computer_science)">correctness</a> of algorithms using <em>formal methods</em>.
You can read more about this on <a class="reference external" href="https://en.wikipedia.org/wiki/Formal_verification">Wikipedia - Formal verification</a>. Here we will instead
show an example.</p>
<p class="rubric">Example:</p>
<p>Consider the <cite>Birth Months riddle</cite> (from <a class="reference external" href="https://www.braingle.com/">Braingle</a>), reproduced below, we will use
formal verification to find a solution, and also to prove that this solution is unique.</p>
<div class="highlight-text notranslate"><div class="highlight"><pre><span></span>Four sisters, Sara, Ophelia, Nora, and Dawn, were each born in a different one of
the months September, October, November, and December.

"This is terrible," said Ophelia one day. "None of us have an initial that matches
the initial of her birth month."

"I don't mind at all," replied the girl who was born in September.

"That's easy for you to say," said Nora. "It would at least be cool if the initial
of my birth month was a vowel, but no."

In which month was each girl born?
</pre></div>
</div>
<section id="finding-a-solution">
<h2>Finding a solution<a class="headerlink" href="#finding-a-solution" title="Link to this heading">¶</a></h2>
<section id="step-1">
<h3>Step 1<a class="headerlink" href="#step-1" title="Link to this heading">¶</a></h3>
<p>The first step is to translate the riddle into a more formal form.
Here is a description of the months as numbers in CVL:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre><span></span><span class="c1">// The months</span>
<span class="kt">definition</span><span class="w"> </span><span class="nf">September</span><span class="p">()</span><span class="w"> </span><span class="kr">returns</span><span class="w"> </span><span class="kt">uint8</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="m m-Decimal">9</span><span class="p">;</span>
<span class="kt">definition</span><span class="w"> </span><span class="nf">October</span><span class="p">()</span><span class="w"> </span><span class="kr">returns</span><span class="w"> </span><span class="kt">uint8</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="m m-Decimal">10</span><span class="p">;</span>
<span class="kt">definition</span><span class="w"> </span><span class="nf">November</span><span class="p">()</span><span class="w"> </span><span class="kr">returns</span><span class="w"> </span><span class="kt">uint8</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="m m-Decimal">11</span><span class="p">;</span>
<span class="kt">definition</span><span class="w"> </span><span class="nf">December</span><span class="p">()</span><span class="w"> </span><span class="kr">returns</span><span class="w"> </span><span class="kt">uint8</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="m m-Decimal">12</span><span class="p">;</span>
</pre></div>
</div>
<p>We use the sisters’ names as parameters (whose value is the birth month of that sister):</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre><span></span><span class="k">rule</span><span class="w"> </span><span class="nc">sistersBirthMonths</span><span class="p">(</span>
<span class="w">    </span><span class="kt">uint8</span><span class="w"> </span>Sara<span class="p">,</span>
<span class="w">    </span><span class="kt">uint8</span><span class="w"> </span>Ophelia<span class="p">,</span>
<span class="w">    </span><span class="kt">uint8</span><span class="w"> </span>Nora<span class="p">,</span>
<span class="w">    </span><span class="kt">uint8</span><span class="w"> </span>Dawn
<span class="p">)</span><span class="w"> </span><span class="p">{</span>
</pre></div>
</div>
</section>
<section id="step-2">
<h3>Step 2<a class="headerlink" href="#step-2" title="Link to this heading">¶</a></h3>
<p>We add all the data in the riddle. For example, saying that Sarah was born in
either September, October, November or December is:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre><span></span><span class="w">    </span><span class="kr">require</span><span class="w"> </span>Sara<span class="w"> </span><span class="o">&gt;=</span><span class="w"> </span>September<span class="p">()</span><span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span>Sara<span class="w"> </span><span class="o">&lt;=</span><span class="w"> </span>December<span class="p">();</span>
</pre></div>
</div>
<p>Each sister was born in one of the four months:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre><span></span><span class="w">    </span><span class="kr">require</span><span class="w"> </span>Sara<span class="w"> </span><span class="o">&gt;=</span><span class="w"> </span>September<span class="p">()</span><span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span>Sara<span class="w"> </span><span class="o">&lt;=</span><span class="w"> </span>December<span class="p">();</span>
<span class="w">    </span><span class="kr">require</span><span class="w"> </span>Ophelia<span class="w"> </span><span class="o">&gt;=</span><span class="w"> </span>September<span class="p">()</span><span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span>Ophelia<span class="w"> </span><span class="o">&lt;=</span><span class="w"> </span>December<span class="p">();</span>
<span class="w">    </span><span class="kr">require</span><span class="w"> </span>Nora<span class="w"> </span><span class="o">&gt;=</span><span class="w"> </span>September<span class="p">()</span><span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span>Nora<span class="w"> </span><span class="o">&lt;=</span><span class="w"> </span>December<span class="p">();</span>
<span class="w">    </span><span class="kr">require</span><span class="w"> </span>Dawn<span class="w"> </span><span class="o">&gt;=</span><span class="w"> </span>September<span class="p">()</span><span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span>Dawn<span class="w"> </span><span class="o">&lt;=</span><span class="w"> </span>December<span class="p">();</span>
</pre></div>
</div>
<p>Each sister’s initial is different from the initial of her birth month:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre><span></span><span class="w">    </span><span class="kr">require</span><span class="w"> </span><span class="p">(</span>
<span class="w">        </span>Sara<span class="w"> </span><span class="o">!=</span><span class="w"> </span>September<span class="p">()</span><span class="w"> </span><span class="o">&amp;&amp;</span>
<span class="w">        </span>Ophelia<span class="w"> </span><span class="o">!=</span><span class="w"> </span>October<span class="p">()</span><span class="w"> </span><span class="o">&amp;&amp;</span>
<span class="w">        </span>Nora<span class="w"> </span><span class="o">!=</span><span class="w"> </span>November<span class="p">()</span><span class="w"> </span><span class="o">&amp;&amp;</span>
<span class="w">        </span>Dawn<span class="w"> </span><span class="o">!=</span><span class="w"> </span>December<span class="p">()</span>
<span class="w">    </span><span class="p">);</span>
</pre></div>
</div>
<p>Clues about Ophelia and Nora:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre><span></span><span class="w">    </span><span class="c1">// Ophelia is not the girl who was born in September</span>
<span class="w">    </span><span class="kr">require</span><span class="w"> </span>Ophelia<span class="w"> </span><span class="o">!=</span><span class="w"> </span>September<span class="p">();</span>

<span class="w">    </span><span class="c1">// Nora is not the girl who was born in September</span>
<span class="w">    </span><span class="kr">require</span><span class="w"> </span>Nora<span class="w"> </span><span class="o">!=</span><span class="w"> </span>September<span class="p">();</span>

<span class="w">    </span><span class="c1">// Nora's birth month does not start with a vowel</span>
<span class="w">    </span><span class="kr">require</span><span class="w"> </span>Nora<span class="w"> </span><span class="o">!=</span><span class="w"> </span>October<span class="p">();</span>
</pre></div>
</div>
<p>The sisters were born on different months:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre><span></span><span class="w">    </span><span class="kr">require</span><span class="w"> </span><span class="p">(</span>
<span class="w">        </span>Sara<span class="w"> </span><span class="o">!=</span><span class="w"> </span>Ophelia<span class="w"> </span><span class="o">&amp;&amp;</span>
<span class="w">        </span>Sara<span class="w"> </span><span class="o">!=</span><span class="w"> </span>Nora<span class="w"> </span><span class="o">&amp;&amp;</span>
<span class="w">        </span>Sara<span class="w"> </span><span class="o">!=</span><span class="w"> </span>Dawn<span class="w"> </span><span class="o">&amp;&amp;</span>
<span class="w">        </span>Ophelia<span class="w"> </span><span class="o">!=</span><span class="w"> </span>Nora<span class="w"> </span><span class="o">&amp;&amp;</span>
<span class="w">        </span>Ophelia<span class="w"> </span><span class="o">!=</span><span class="w"> </span>Dawn<span class="w"> </span><span class="o">&amp;&amp;</span>
<span class="w">        </span>Nora<span class="w"> </span><span class="o">!=</span><span class="w"> </span>Dawn
<span class="w">    </span><span class="p">);</span>
</pre></div>
</div>
</section>
<section id="step-3">
<h3>Step 3<a class="headerlink" href="#step-3" title="Link to this heading">¶</a></h3>
<p>We ask for a solution that satisfies all these requirements, using the CVL statement:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre><span></span><span class="w">    </span><span class="kr">satisfy</span><span class="w"> </span><span class="kr">true</span><span class="p">;</span>
</pre></div>
</div>
</section>
<section id="step-4">
<h3>Step 4<a class="headerlink" href="#step-4" title="Link to this heading">¶</a></h3>
<p>The entire rule is found in <a class="reference external" href="https://github.com/Certora/tutorials-code/blob/master/lesson1_prerequisites/formal_verification/sisters.spec">sisters.spec</a>. Running the Certora Prover
on this rule would provide a solution (if one exists). You will learn about
running the Certora Prover in Lesson 2 <a class="reference internal" href="../lesson2_started/index.html#lesson2-started"><span class="std std-ref">Getting Started</span></a>, in particular in Section
<a class="reference internal" href="../lesson2_started/erc20_example.html#sec-running-the-prover"><span class="std std-ref">Running the Prover</span></a>. For now we will provide the answer given by the
Certora Prover, which looks like this:</p>
<div class="highlight-text notranslate"><div class="highlight"><pre><span></span>*----------------------------------- ... --------------*
|Rule name          |Verified     |        |Local vars |
|-------------------|-------------|- ... --|-----------|
|sistersBirthMonths |Not violated |        |Dawn=9     |
|                   |             |        |Nora=12    |
|                   |             |        |Ophelia=11 |
|                   |             |        |Sara=10    |
|                   |             |        | ...       |
*----------------------------------- ... --------------*
</pre></div>
</div>
<p>So, Sara was born in October, Ophelia was born in November, Nora was born in December,
and Dawn was born in September.</p>
<div class="admonition-if-you-want-to-run-the-certora-prover-yourself admonition">
<p class="admonition-title">If you want to run the Certora Prover yourself</p>
<p>Go to the folder <a class="reference external" href="https://github.com/Certora/tutorials-code/tree/master/lesson1_prerequisites/formal_verification">lesson1_prerequisites/formal_verification/</a> and enter:</p>
<div class="highlight-sh notranslate"><div class="highlight"><pre><span></span>certoraRun<span class="w"> </span>Empty.sol<span class="w"> </span>--verify<span class="w"> </span>Empty:sisters.spec<span class="w"> </span>--solc<span class="w"> </span>solc8.0<span class="w"> </span>--rule<span class="w"> </span>sistersBirthMonths
</pre></div>
</div>
</div>
</section>
</section>
<section id="proving-the-solution-is-unique">
<h2>Proving the solution is unique<a class="headerlink" href="#proving-the-solution-is-unique" title="Link to this heading">¶</a></h2>
<p>To prove the solution is unique, we build another rule, called <code class="docutils literal notranslate"><span class="pre">solutionIsUnique</span></code>,
containing all the requirements above. However, instead of the <code class="code highlight cvl docutils literal highlight-cvl"><span class="kr">satisfy</span><span class="w"> </span><span class="kr">true</span><span class="p">;</span></code>
statement we add the assertion that the only solution is the one we found:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre><span></span><span class="w">    </span><span class="kr">assert</span><span class="w"> </span><span class="p">(</span>
<span class="w">        </span>Sara<span class="w"> </span><span class="o">==</span><span class="w"> </span>October<span class="p">()</span><span class="w"> </span><span class="o">&amp;&amp;</span>
<span class="w">        </span>Ophelia<span class="w"> </span><span class="o">==</span><span class="w"> </span>November<span class="p">()</span><span class="w"> </span><span class="o">&amp;&amp;</span>
<span class="w">        </span>Nora<span class="w"> </span><span class="o">==</span><span class="w"> </span>December<span class="p">()</span><span class="w"> </span><span class="o">&amp;&amp;</span>
<span class="w">        </span>Dawn<span class="w"> </span><span class="o">==</span><span class="w"> </span>September<span class="p">()</span>
<span class="w">    </span><span class="p">);</span>
</pre></div>
</div>
<p>If the assertion is violated, the Prover will provide a counter-example to the assertion.
Such a counter-example would be another solution, showing the previous solution is not
unique.</p>
<p>Running the Certora Prover on this new rule simply returns:</p>
<div class="highlight-text notranslate"><div class="highlight"><pre><span></span>*---------------------------------- ...
|Rule name        |Verified     |
|-----------------|-------------|-- ...
|solutionIsUnique |Not violated |
</pre></div>
</div>
<p>Which proves the solution is unique.</p>
<div class="admonition-to-run-the-certora-prover-on-this-rule admonition">
<p class="admonition-title">To run the Certora Prover on this rule</p>
<p>Go to the folder <a class="reference external" href="https://github.com/Certora/tutorials-code/tree/master/lesson1_prerequisites/formal_verification">lesson1_prerequisites/formal_verification/</a> and enter:</p>
<div class="highlight-sh notranslate"><div class="highlight"><pre><span></span>certoraRun<span class="w"> </span>Empty.sol<span class="w"> </span>--verify<span class="w"> </span>Empty:sisters.spec<span class="w"> </span>--solc<span class="w"> </span>solc8.0<span class="w"> </span>--rule<span class="w"> </span>solutionIsUnique
</pre></div>
</div>
</div>
<p>This rule is also found at <a class="reference external" href="https://github.com/Certora/tutorials-code/blob/master/lesson1_prerequisites/formal_verification/sisters.spec">sisters.spec</a>. Here is the complete rule:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre><span></span><span class="c1">/// @title Verify that the solution is unique</span>
<span class="k">rule</span><span class="w"> </span><span class="nc">solutionIsUnique</span><span class="p">(</span>
<span class="w">    </span><span class="kt">uint8</span><span class="w"> </span>Sara<span class="p">,</span>
<span class="w">    </span><span class="kt">uint8</span><span class="w"> </span>Ophelia<span class="p">,</span>
<span class="w">    </span><span class="kt">uint8</span><span class="w"> </span>Nora<span class="p">,</span>
<span class="w">    </span><span class="kt">uint8</span><span class="w"> </span>Dawn
<span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="c1">// Each sister was born in one of the four months</span>
<span class="w">    </span><span class="kr">require</span><span class="w"> </span>Sara<span class="w"> </span><span class="o">&gt;=</span><span class="w"> </span>September<span class="p">()</span><span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span>Sara<span class="w"> </span><span class="o">&lt;=</span><span class="w"> </span>December<span class="p">();</span>
<span class="w">    </span><span class="kr">require</span><span class="w"> </span>Ophelia<span class="w"> </span><span class="o">&gt;=</span><span class="w"> </span>September<span class="p">()</span><span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span>Ophelia<span class="w"> </span><span class="o">&lt;=</span><span class="w"> </span>December<span class="p">();</span>
<span class="w">    </span><span class="kr">require</span><span class="w"> </span>Nora<span class="w"> </span><span class="o">&gt;=</span><span class="w"> </span>September<span class="p">()</span><span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span>Nora<span class="w"> </span><span class="o">&lt;=</span><span class="w"> </span>December<span class="p">();</span>
<span class="w">    </span><span class="kr">require</span><span class="w"> </span>Dawn<span class="w"> </span><span class="o">&gt;=</span><span class="w"> </span>September<span class="p">()</span><span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span>Dawn<span class="w"> </span><span class="o">&lt;=</span><span class="w"> </span>December<span class="p">();</span>

<span class="w">    </span><span class="c1">// "None of us have an initial that matches the initial of her birth month."</span>
<span class="w">    </span><span class="kr">require</span><span class="w"> </span><span class="p">(</span>
<span class="w">        </span>Sara<span class="w"> </span><span class="o">!=</span><span class="w"> </span>September<span class="p">()</span><span class="w"> </span><span class="o">&amp;&amp;</span>
<span class="w">        </span>Ophelia<span class="w"> </span><span class="o">!=</span><span class="w"> </span>October<span class="p">()</span><span class="w"> </span><span class="o">&amp;&amp;</span>
<span class="w">        </span>Nora<span class="w"> </span><span class="o">!=</span><span class="w"> </span>November<span class="p">()</span><span class="w"> </span><span class="o">&amp;&amp;</span>
<span class="w">        </span>Dawn<span class="w"> </span><span class="o">!=</span><span class="w"> </span>December<span class="p">()</span>
<span class="w">    </span><span class="p">);</span>

<span class="w">    </span><span class="c1">// Ophelia is not the girl who was born in September</span>
<span class="w">    </span><span class="kr">require</span><span class="w"> </span>Ophelia<span class="w"> </span><span class="o">!=</span><span class="w"> </span>September<span class="p">();</span>

<span class="w">    </span><span class="c1">// Nora is not the girl who was born in September</span>
<span class="w">    </span><span class="kr">require</span><span class="w"> </span>Nora<span class="w"> </span><span class="o">!=</span><span class="w"> </span>September<span class="p">();</span>

<span class="w">    </span><span class="c1">// Nora's birth month does not start with a vowel</span>
<span class="w">    </span><span class="kr">require</span><span class="w"> </span>Nora<span class="w"> </span><span class="o">!=</span><span class="w"> </span>October<span class="p">();</span>

<span class="w">    </span><span class="c1">// The sisters were born on different months</span>
<span class="w">    </span><span class="kr">require</span><span class="w"> </span><span class="p">(</span>
<span class="w">        </span>Sara<span class="w"> </span><span class="o">!=</span><span class="w"> </span>Ophelia<span class="w"> </span><span class="o">&amp;&amp;</span>
<span class="w">        </span>Sara<span class="w"> </span><span class="o">!=</span><span class="w"> </span>Nora<span class="w"> </span><span class="o">&amp;&amp;</span>
<span class="w">        </span>Sara<span class="w"> </span><span class="o">!=</span><span class="w"> </span>Dawn<span class="w"> </span><span class="o">&amp;&amp;</span>
<span class="w">        </span>Ophelia<span class="w"> </span><span class="o">!=</span><span class="w"> </span>Nora<span class="w"> </span><span class="o">&amp;&amp;</span>
<span class="w">        </span>Ophelia<span class="w"> </span><span class="o">!=</span><span class="w"> </span>Dawn<span class="w"> </span><span class="o">&amp;&amp;</span>
<span class="w">        </span>Nora<span class="w"> </span><span class="o">!=</span><span class="w"> </span>Dawn
<span class="w">    </span><span class="p">);</span>

<span class="w">    </span><span class="kr">assert</span><span class="w"> </span><span class="p">(</span>
<span class="w">        </span>Sara<span class="w"> </span><span class="o">==</span><span class="w"> </span>October<span class="p">()</span><span class="w"> </span><span class="o">&amp;&amp;</span>
<span class="w">        </span>Ophelia<span class="w"> </span><span class="o">==</span><span class="w"> </span>November<span class="p">()</span><span class="w"> </span><span class="o">&amp;&amp;</span>
<span class="w">        </span>Nora<span class="w"> </span><span class="o">==</span><span class="w"> </span>December<span class="p">()</span><span class="w"> </span><span class="o">&amp;&amp;</span>
<span class="w">        </span>Dawn<span class="w"> </span><span class="o">==</span><span class="w"> </span>September<span class="p">()</span>
<span class="w">    </span><span class="p">);</span>
<span class="p">}</span>
</pre></div>
</div>
</section>
</section>

        </article>
      </div>
      <footer>
        
        <div class="related-pages">
          <a class="next-page" href="../lesson2_started/index.html">
              <div class="page-info">
                <div class="context">
                  <span>Next</span>
                </div>
                <div class="title"><span class="section-number">2. </span>Getting Started</div>
              </div>
              <svg class="furo-related-icon"><use href="#svg-arrow-right"></use></svg>
            </a>
          <a class="prev-page" href="propositional_logic.html">
              <svg class="furo-related-icon"><use href="#svg-arrow-right"></use></svg>
              <div class="page-info">
                <div class="context">
                  <span>Previous</span>
                </div>
                
                <div class="title"><span class="section-number">1.2. </span>Introduction to predicate logic</div>
                
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
<li><a class="reference internal" href="#">1.3. Introduction to formal verification</a><ul>
<li><a class="reference internal" href="#finding-a-solution">Finding a solution</a><ul>
<li><a class="reference internal" href="#step-1">Step 1</a></li>
<li><a class="reference internal" href="#step-2">Step 2</a></li>
<li><a class="reference internal" href="#step-3">Step 3</a></li>
<li><a class="reference internal" href="#step-4">Step 4</a></li>
</ul>
</li>
<li><a class="reference internal" href="#proving-the-solution-is-unique">Proving the solution is unique</a></li>
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