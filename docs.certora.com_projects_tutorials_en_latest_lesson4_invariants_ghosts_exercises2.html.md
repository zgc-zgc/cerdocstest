<!DOCTYPE html><html class="" lang="en" data-content_root="../../"><head><meta charset="utf-8">
    <meta name="viewport" content="width=device-width,initial-scale=1">
    <meta name="color-scheme" content="light dark"><meta name="viewport" content="width=device-width, initial-scale=1">
<link rel="index" title="Index" href="../../genindex.html"><link rel="search" title="Search" href="../../search.html"><link rel="prev" title="4.4. Ghosts and hooks" href="basics.html">

    <!-- Generated with Sphinx 7.4.5 and Furo 2024.05.06 -->
        <title>4.5. Ghost exercises - Certora Prover Tutorials</title>
      <link rel="stylesheet" type="text/css" href="../../_static/pygments.css?v=a746c00c">
    <link rel="stylesheet" type="text/css" href="../../_static/styles/furo.css?v=387cc868">
    <link rel="stylesheet" type="text/css" href="../../_static/graphviz.css?v=fd3f3429">
    <link rel="stylesheet" type="text/css" href="../../_static/sphinx-design.min.css?v=87e54e7c">
    <link rel="stylesheet" type="text/css" href="../../_static/styles/furo-extensions.css?v=36a5483c">
    
    


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
</style><script async="" type="text/javascript" src="/_/static/javascript/readthedocs-addons.js"></script><meta name="readthedocs-project-slug" content="certora-cvl2-tutorials-package"><meta name="readthedocs-version-slug" content="latest"><meta name="readthedocs-resolver-filename" content="/lesson4_invariants/ghosts/exercises.html"><meta name="readthedocs-http-status" content="200"></head>
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
      <a href="../../index.html"><div class="brand">Certora Prover Tutorials</div></a>
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
      
      <div class="sidebar-sticky"><a class="sidebar-brand" href="../../index.html">
  
  <div class="sidebar-logo-container">
    <img class="sidebar-logo only-light" src="../../_static/logo.svg" alt="Light Logo" width="164" height="42">
    <img class="sidebar-logo only-dark" src="../../_static/logo.svg" alt="Dark Logo">
  </div>
  
  <span class="sidebar-brand-text">Certora Prover Tutorials</span>
  
</a><form class="sidebar-search-container" method="get" action="../../search.html" role="search">
  <input class="sidebar-search" placeholder="Search" name="q" aria-label="Search">
  <input type="hidden" name="check_keywords" value="yes">
  <input type="hidden" name="area" value="default">
</form>
<div id="searchbox"></div><div class="sidebar-scroll"><div class="sidebar-tree">
  <p class="caption" role="heading"><span class="caption-text">Contents:</span></p>
<ul class="current">
<li class="toctree-l1 has-children"><a class="reference internal" href="../../lesson1_prerequisites/index.html">1. Background and Prerequisites</a><input class="toctree-checkbox" id="toctree-checkbox-1" name="toctree-checkbox-1" role="switch" type="checkbox"><label for="toctree-checkbox-1"><div class="visually-hidden">Toggle navigation of 1. Background and Prerequisites</div><i class="icon"><svg><use href="#svg-arrow-right"></use></svg></i></label><ul>
<li class="toctree-l2"><a class="reference internal" href="../../lesson1_prerequisites/background.html">1.1. Background</a></li>
<li class="toctree-l2"><a class="reference internal" href="../../lesson1_prerequisites/propositional_logic.html">1.2. Introduction to predicate logic</a></li>
<li class="toctree-l2"><a class="reference internal" href="../../lesson1_prerequisites/formal_verification.html">1.3. Introduction to formal verification</a></li>
</ul>
</li>
<li class="toctree-l1 has-children"><a class="reference internal" href="../../lesson2_started/index.html">2. Getting Started</a><input class="toctree-checkbox" id="toctree-checkbox-2" name="toctree-checkbox-2" role="switch" type="checkbox"><label for="toctree-checkbox-2"><div class="visually-hidden">Toggle navigation of 2. Getting Started</div><i class="icon"><svg><use href="#svg-arrow-right"></use></svg></i></label><ul>
<li class="toctree-l2"><a class="reference internal" href="../../lesson2_started/installation.html">2.1. Installation and Setup</a></li>
<li class="toctree-l2"><a class="reference internal" href="../../lesson2_started/overview.html">2.2. Technology Overview</a></li>
<li class="toctree-l2"><a class="reference internal" href="../../lesson2_started/erc20_example.html">2.3. ERC20 Example - Basics</a></li>
<li class="toctree-l2"><a class="reference internal" href="../../lesson2_started/preconditions.html">2.4. ERC20 Example - preconditions</a></li>
<li class="toctree-l2"><a class="reference internal" href="../../lesson2_started/parametric.html">2.5. Parametric rules</a></li>
<li class="toctree-l2"><a class="reference internal" href="../../lesson2_started/config_files.html">2.6. Using config files</a></li>
<li class="toctree-l2"><a class="reference internal" href="../../lesson2_started/vacuity.html">2.7. Vacuity</a></li>
</ul>
</li>
<li class="toctree-l1 has-children"><a class="reference internal" href="../../lesson3_violations/index.html">3. Understanding violations</a><input class="toctree-checkbox" id="toctree-checkbox-3" name="toctree-checkbox-3" role="switch" type="checkbox"><label for="toctree-checkbox-3"><div class="visually-hidden">Toggle navigation of 3. Understanding violations</div><i class="icon"><svg><use href="#svg-arrow-right"></use></svg></i></label><ul>
<li class="toctree-l2"><a class="reference internal" href="../../lesson3_violations/erc20_bugs.html">3.1. Fixing ERC20 spec</a></li>
<li class="toctree-l2"><a class="reference internal" href="../../lesson3_violations/borda_bugs.html">3.2. Borda count election</a></li>
<li class="toctree-l2"><a class="reference internal" href="../../lesson3_violations/reward_challenge.html">3.3. Reward Challenge : Missing Spec bounty</a></li>
</ul>
</li>
<li class="toctree-l1 current has-children"><a class="reference internal" href="../index.html">4. Invariants and Ghosts</a><input checked="" class="toctree-checkbox" id="toctree-checkbox-4" name="toctree-checkbox-4" role="switch" type="checkbox"><label for="toctree-checkbox-4"><div class="visually-hidden">Toggle navigation of 4. Invariants and Ghosts</div><i class="icon"><svg><use href="#svg-arrow-right"></use></svg></i></label><ul class="current">
<li class="toctree-l2"><a class="reference internal" href="../invariants/simple.html">4.1. Simple invariants examples</a></li>
<li class="toctree-l2"><a class="reference internal" href="../invariants/auction.html">4.2. Basic exercises</a></li>
<li class="toctree-l2"><a class="reference internal" href="../invariants/preserved.html">4.3. Preserved blocks</a></li>
<li class="toctree-l2"><a class="reference internal" href="basics.html">4.4. Ghosts and hooks</a></li>
<li class="toctree-l2 current current-page"><a class="current reference internal" href="#">4.5. Ghost exercises</a></li>
</ul>
</li>
</ul>
<ul>
<li class="toctree-l1"><a class="reference internal" href="../../genindex.html">Index</a></li>
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
          <section id="ghost-exercises">
<span id="lesson4-ghost-excercises"></span><h1><span class="section-number">4.5. </span>Ghost exercises<a class="headerlink" href="#ghost-exercises" title="Link to this heading">¶</a></h1>
<section id="simple-voting-contract">
<h2>Simple voting contract<a class="headerlink" href="#simple-voting-contract" title="Link to this heading">¶</a></h2>
<p>This exercise refers to the simple
<a class="reference external" href="https://github.com/Certora/tutorials-code/blob/master/lesson4_invariants/simple_voting/Voting.sol">Voting</a> contract.</p>
<ol class="arabic simple">
<li><p>Use a ghost and an invariant to prove that if <code class="code highlight solidity docutils literal highlight-solidity">_hasVoted</code> changed then
the <code class="code highlight solidity docutils literal highlight-solidity">vote</code> method was called.</p></li>
<li><p>Use a ghost and an invariant to prove that the values of <code class="code highlight solidity docutils literal highlight-solidity">_hasVoted</code> can
only change from false to true.</p></li>
<li><p>Write a <em>complete spec</em> for the
<a class="reference external" href="https://github.com/Certora/tutorials-code/blob/master/lesson4_invariants/simple_voting/Voting.sol">Voting</a> contract, using ghosts,
invariants and rules.</p></li>
<li><p>Check that your spec passes without violations on
<a class="reference external" href="https://github.com/Certora/tutorials-code/blob/master/lesson4_invariants/simple_voting/Voting.sol">Voting</a> and also catches the
bugs in the five buggy implementations:</p>
<ul class="simple">
<li><p><a class="reference external" href="https://github.com/Certora/tutorials-code/blob/master/lesson4_invariants/simple_voting/VotingBug1.sol">VotingBug1.sol</a></p></li>
<li><p><a class="reference external" href="https://github.com/Certora/tutorials-code/blob/master/lesson4_invariants/simple_voting/VotingBug2.sol">VotingBug2.sol</a></p></li>
<li><p><a class="reference external" href="https://github.com/Certora/tutorials-code/blob/master/lesson4_invariants/simple_voting/VotingBug3.sol">VotingBug3.sol</a></p></li>
<li><p><a class="reference external" href="https://github.com/Certora/tutorials-code/blob/master/lesson4_invariants/simple_voting/VotingBug4.sol">VotingBug4.sol</a></p></li>
<li><p><a class="reference external" href="https://github.com/Certora/tutorials-code/blob/master/lesson4_invariants/simple_voting/VotingBug5.sol">VotingBug5.sol</a></p></li>
</ul>
</li>
<li><p>Check that your spec catches all mutations generated by <a class="reference external" href="https://docs.certora.com/en/latest/docs/gambit/index.html">Gambit</a> (see
<a class="reference internal" href="#lesson4-using-gambit"><span class="std std-ref">Using Gambit to test your spec</span></a> below, which provides an example using <a class="reference external" href="https://docs.certora.com/en/latest/docs/gambit/index.html">Gambit</a>).</p></li>
</ol>
<section id="hints">
<h3>Hints<a class="headerlink" href="#hints" title="Link to this heading">¶</a></h3>
<details class="sd-sphinx-override sd-dropdown sd-card sd-mb-3 sd-fade-in-slide-down">
<summary class="sd-summary-title sd-card-header">
<span class="sd-summary-text">Solution</span><span class="sd-summary-state-marker sd-summary-chevron-right"><svg version="1.1" width="1.5em" height="1.5em" class="sd-octicon sd-octicon-chevron-right" viewBox="0 0 24 24" aria-hidden="true"><path d="M8.72 18.78a.75.75 0 0 1 0-1.06L14.44 12 8.72 6.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018l6.25 6.25a.75.75 0 0 1 0 1.06l-6.25 6.25a.75.75 0 0 1-1.06 0Z"></path></svg></span></summary><div class="sd-summary-content sd-card-body docutils">
<p class="sd-card-text">The full solution is at
<a class="reference external" href="https://github.com/Certora/tutorials-code/blob/master/solutions/lesson4_invariants/simple_voting/Voting_solution.spec">Voting_solution.spec</a>.</p>
</div>
</details></section>
<section id="using-gambit-to-test-your-spec">
<span id="lesson4-using-gambit"></span><h3>Using Gambit to test your spec<a class="headerlink" href="#using-gambit-to-test-your-spec" title="Link to this heading">¶</a></h3>
<p><a class="reference external" href="https://docs.certora.com/en/latest/docs/gambit/index.html">Gambit</a> is a Certora tool that automatically generates random mutations (bugs) in the code.
This is useful for testing the coverage of your spec.
See the <a class="reference external" href="https://docs.certora.com/en/latest/docs/gambit/gambit.html">Mutant generation</a> page for Gambit installation instructions.</p>
<p>Gambit can be used with the Certora Prover to automatically run your spec on
<em>all generated mutations</em>. This is explained in detail in <a class="reference external" href="https://docs.certora.com/en/latest/docs/gambit/mutation-verifier.html">Using Gambit with the Prover</a>.
Here, we provide an example that runs
<a class="reference external" href="https://github.com/Certora/tutorials-code/blob/master/lesson4_invariants/simple_voting/Voting.spec">Voting.spec</a> on all mutations.</p>
<section id="gambit-example">
<h4>Gambit example<a class="headerlink" href="#gambit-example" title="Link to this heading">¶</a></h4>
<ol class="arabic">
<li><p>To run the Prover on all mutations we need a Prover configuration file
(see <a class="reference internal" href="../../lesson2_started/config_files.html#sec-using-config-files"><span class="std std-ref">Using config files</span></a>) with a <cite>mutations</cite> object.</p></li>
<li><p><a class="reference external" href="https://github.com/Certora/tutorials-code/blob/master/lesson4_invariants/simple_voting/Voting.conf">Voting.conf</a>
includes a simple <cite>mutations</cite> object.
It simply specifies the file to be mutated as
<a class="reference external" href="https://github.com/Certora/tutorials-code/blob/master/lesson4_invariants/simple_voting/Voting.sol">Voting.sol</a>.</p></li>
<li><p>From the <a class="reference external" href="https://github.com/Certora/tutorials-code/tree/master/lesson4_invariants/simple_voting">lesson4_invariants/simple_voting/</a> folder run the
following command:</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre><span></span>certoraMutate<span class="w"> </span>Voting.conf
</pre></div>
</div>
<p>This will run the
<a class="reference external" href="https://github.com/Certora/tutorials-code/blob/master/lesson4_invariants/simple_voting/Voting.spec">Voting.spec</a>
on all mutations (asynchronously), sending jobs to the server.</p>
</li>
<li><p>After all the verification jobs have been sent to the cloud, you can follow the progress of your
test at the <a class="reference external" href="https://prover.certora.com/mutations">Mutation Tests Dashboard</a>.</p>
<figure class="align-default" id="id3">
<img alt="Mutation tests dashboard" src="../../_images/mutation_test_started_dashboard.png" width="887" height="96">
<figcaption>
<p><span class="caption-text">Mutation tests dashboard</span><a class="headerlink" href="#id3" title="Link to this image">¶</a></p>
</figcaption>
</figure>
</li>
<li><p>View the report on the provided link once the test is completed.
Below is an example of a mutation test report.</p>
<figure class="align-default" id="id4">
<img alt="Mutation test report example" src="../../_images/mutation_testing.png">
<figcaption>
<p><span class="caption-text">Mutation test report example</span><a class="headerlink" href="#id4" title="Link to this image">¶</a></p>
</figcaption>
</figure>
</li>
</ol>
</section>
</section>
</section>
<section id="english-auction">
<h2>English auction<a class="headerlink" href="#english-auction" title="Link to this heading">¶</a></h2>
<p>This exercise is about the
<a class="reference external" href="https://github.com/Certora/tutorials-code/blob/master/lesson4_invariants/auction/EnglishAuction.sol">EnglishAuction.sol</a> contract.
We’ve met this contract before in the <a class="reference internal" href="../invariants/auction.html#lesson4-english-auction-basic"><span class="std std-ref">English auction basic exercise</span></a>. To
make it harder, we abandon the assumption that <code class="code highlight solidity docutils literal highlight-solidity"><span class="kt">address</span><span class="p">(</span><span class="m m-Decimal">0</span><span class="p">)</span></code> cannot place
a bid.</p>
<ol class="arabic simple">
<li><p>Use a ghost and a hook to indicate that someone placed some bid.</p></li>
<li><p>Prove that <code class="code highlight solidity docutils literal highlight-solidity">highestBid</code> is <strong>strictly greater</strong> than all other bids,
provided someone has placed a bid.</p></li>
</ol>
<section id="setup-note">
<h3>Setup note<a class="headerlink" href="#setup-note" title="Link to this heading">¶</a></h3>
<p>The <a class="reference external" href="https://github.com/Certora/tutorials-code/blob/master/lesson4_invariants/auction/EnglishAuction.sol">EnglishAuction</a> contract
calls other contracts. For example, it calls <code class="code highlight solidity docutils literal highlight-solidity">ERC721Mock<span class="p">.</span>transferFrom</code>.
If the Prover is not <em>certain</em> what code is called, it will over-approximate by assuming
anything can happen. In particular, this can cause ghost variables to have arbitrary
values. We will learn more about this in the next lesson.</p>
<p>For now, to avoid such issues, ensure you config file contains the following lines:</p>
<div class="highlight-json notranslate"><div class="highlight"><pre><span></span><span class="p">{</span>
<span class="w">    </span><span class="nt">"files"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span>
<span class="w">	</span><span class="c1">// Declare all three contracts</span>
<span class="w">        </span><span class="s2">"lesson4_invariants/auction/EnglishAuction.sol:EnglishAuction"</span><span class="p">,</span>
<span class="w">        </span><span class="s2">"lesson4_invariants/auction/EnglishAuction.sol:ERC721Mock"</span><span class="p">,</span>
<span class="w">        </span><span class="s2">"lesson4_invariants/auction/EnglishAuction.sol:ERC20Mock"</span>
<span class="w">    </span><span class="p">],</span>
<span class="w">    </span><span class="nt">"link"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span>
<span class="w">	</span><span class="c1">// Link EnglishAuction storage variables to contracts</span>
<span class="w">        </span><span class="s2">"EnglishAuction:nft=ERC721Mock"</span><span class="p">,</span>
<span class="w">	</span><span class="s2">"EnglishAuction:token=ERC20Mock"</span>
<span class="w">    </span><span class="p">],</span>
</pre></div>
</div>
<p>These lines will tell the Prover to <em>always</em> associate the <code class="code highlight solidity docutils literal highlight-solidity">EnglishAuction</code>
variables <code class="code highlight solidity docutils literal highlight-solidity">nft</code> and <code class="code highlight solidity docutils literal highlight-solidity">token</code> with the contracts <code class="code highlight solidity docutils literal highlight-solidity">ERC721Mock</code>
and <code class="code highlight solidity docutils literal highlight-solidity">ERC20Mock</code> respectively.</p>
</section>
<section id="id1">
<h3>Hints<a class="headerlink" href="#id1" title="Link to this heading">¶</a></h3>
<details class="sd-sphinx-override sd-dropdown sd-card sd-mb-3 sd-fade-in-slide-down">
<summary class="sd-summary-title sd-card-header">
<span class="sd-summary-text">Solution</span><span class="sd-summary-state-marker sd-summary-chevron-right"><svg version="1.1" width="1.5em" height="1.5em" class="sd-octicon sd-octicon-chevron-right" viewBox="0 0 24 24" aria-hidden="true"><path d="M8.72 18.78a.75.75 0 0 1 0-1.06L14.44 12 8.72 6.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018l6.25 6.25a.75.75 0 0 1 0 1.06l-6.25 6.25a.75.75 0 0 1-1.06 0Z"></path></svg></span></summary><div class="sd-summary-content sd-card-body docutils">
<p class="sd-card-text">The full solution is at
<a class="reference external" href="https://github.com/Certora/tutorials-code/blob/master/solutions/lesson4_invariants/auction/EnglishAuction_strict.spec">EnglishAuction_strict.spec</a>.</p>
</div>
</details></section>
</section>
<section id="funds-managers">
<h2>Funds managers<a class="headerlink" href="#funds-managers" title="Link to this heading">¶</a></h2>
<p>This exercise is for the <a class="reference external" href="https://github.com/Certora/tutorials-code/blob/master/lesson4_invariants/manager/Manager.sol">Manager.sol</a>
contract, which we’ve met in <a class="reference internal" href="../invariants/preserved.html#lesson4-invariants-funds-manages-preserved"><span class="std std-ref">Funds managers exercise</span></a>.
The exercise now is to prove that every active manager manages a fund. Use a ghost
when writing the invariants and verify them using the Certora Prover.</p>
<section id="id2">
<h3>Hints<a class="headerlink" href="#id2" title="Link to this heading">¶</a></h3>
<details class="sd-sphinx-override sd-dropdown sd-card sd-mb-3 sd-fade-in-slide-down">
<summary class="sd-summary-title sd-card-header">
<span class="sd-summary-text">Solution</span><span class="sd-summary-state-marker sd-summary-chevron-right"><svg version="1.1" width="1.5em" height="1.5em" class="sd-octicon sd-octicon-chevron-right" viewBox="0 0 24 24" aria-hidden="true"><path d="M8.72 18.78a.75.75 0 0 1 0-1.06L14.44 12 8.72 6.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018l6.25 6.25a.75.75 0 0 1 0 1.06l-6.25 6.25a.75.75 0 0 1-1.06 0Z"></path></svg></span></summary><div class="sd-summary-content sd-card-body docutils">
<p class="sd-card-text">The full solution is at
<a class="reference external" href="https://github.com/Certora/tutorials-code/blob/master/solutions/lesson4_invariants/manager/Manager_ghost.spec">Manager_ghost.spec</a>.</p>
</div>
</details></section>
</section>
</section>

        </article>
      </div>
      <footer>
        
        <div class="related-pages">
          
          <a class="prev-page" href="basics.html">
              <svg class="furo-related-icon"><use href="#svg-arrow-right"></use></svg>
              <div class="page-info">
                <div class="context">
                  <span>Previous</span>
                </div>
                
                <div class="title"><span class="section-number">4.4. </span>Ghosts and hooks</div>
                
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
<li><a class="reference internal" href="#">4.5. Ghost exercises</a><ul>
<li><a class="reference internal" href="#simple-voting-contract">Simple voting contract</a><ul>
<li><a class="reference internal" href="#hints">Hints</a></li>
<li><a class="reference internal" href="#using-gambit-to-test-your-spec">Using Gambit to test your spec</a><ul>
<li><a class="reference internal" href="#gambit-example">Gambit example</a></li>
</ul>
</li>
</ul>
</li>
<li><a class="reference internal" href="#english-auction">English auction</a><ul>
<li><a class="reference internal" href="#setup-note">Setup note</a></li>
<li><a class="reference internal" href="#id1">Hints</a></li>
</ul>
</li>
<li><a class="reference internal" href="#funds-managers">Funds managers</a><ul>
<li><a class="reference internal" href="#id2">Hints</a></li>
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
</div><script src="../../_static/documentation_options.js?v=b4795bba"></script>
    <script src="../../_static/doctools.js?v=9a2dae69"></script>
    <script src="../../_static/sphinx_highlight.js?v=dc90522c"></script>
    <script src="../../_static/scripts/furo.js?v=4e2eecee"></script>
    <script src="../../_static/design-tabs.js?v=f930bc37"></script>
    
</body></html>