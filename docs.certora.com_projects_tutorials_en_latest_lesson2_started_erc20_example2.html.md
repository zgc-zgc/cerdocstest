<!DOCTYPE html><html class="" lang="en" data-content_root="../"><head><meta charset="utf-8">
    <meta name="viewport" content="width=device-width,initial-scale=1">
    <meta name="color-scheme" content="light dark"><meta name="viewport" content="width=device-width, initial-scale=1">
<link rel="index" title="Index" href="../genindex.html"><link rel="search" title="Search" href="../search.html"><link rel="next" title="2.4. ERC20 Example - preconditions" href="preconditions.html"><link rel="prev" title="2.2. Technology Overview" href="overview.html">

    <!-- Generated with Sphinx 7.4.5 and Furo 2024.05.06 -->
        <title>2.3. ERC20 Example - Basics - Certora Prover Tutorials</title>
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
</style><script async="" type="text/javascript" src="/_/static/javascript/readthedocs-addons.js"></script><meta name="readthedocs-project-slug" content="certora-cvl2-tutorials-package"><meta name="readthedocs-version-slug" content="latest"><meta name="readthedocs-resolver-filename" content="/lesson2_started/erc20_example.html"><meta name="readthedocs-http-status" content="200"></head>
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
<li class="toctree-l1 has-children"><a class="reference internal" href="../lesson1_prerequisites/index.html">1. Background and Prerequisites</a><input class="toctree-checkbox" id="toctree-checkbox-1" name="toctree-checkbox-1" role="switch" type="checkbox"><label for="toctree-checkbox-1"><div class="visually-hidden">Toggle navigation of 1. Background and Prerequisites</div><i class="icon"><svg><use href="#svg-arrow-right"></use></svg></i></label><ul>
<li class="toctree-l2"><a class="reference internal" href="../lesson1_prerequisites/background.html">1.1. Background</a></li>
<li class="toctree-l2"><a class="reference internal" href="../lesson1_prerequisites/propositional_logic.html">1.2. Introduction to predicate logic</a></li>
<li class="toctree-l2"><a class="reference internal" href="../lesson1_prerequisites/formal_verification.html">1.3. Introduction to formal verification</a></li>
</ul>
</li>
<li class="toctree-l1 current has-children"><a class="reference internal" href="index.html">2. Getting Started</a><input checked="" class="toctree-checkbox" id="toctree-checkbox-2" name="toctree-checkbox-2" role="switch" type="checkbox"><label for="toctree-checkbox-2"><div class="visually-hidden">Toggle navigation of 2. Getting Started</div><i class="icon"><svg><use href="#svg-arrow-right"></use></svg></i></label><ul class="current">
<li class="toctree-l2"><a class="reference internal" href="installation.html">2.1. Installation and Setup</a></li>
<li class="toctree-l2"><a class="reference internal" href="overview.html">2.2. Technology Overview</a></li>
<li class="toctree-l2 current current-page"><a class="current reference internal" href="#">2.3. ERC20 Example - Basics</a></li>
<li class="toctree-l2"><a class="reference internal" href="preconditions.html">2.4. ERC20 Example - preconditions</a></li>
<li class="toctree-l2"><a class="reference internal" href="parametric.html">2.5. Parametric rules</a></li>
<li class="toctree-l2"><a class="reference internal" href="config_files.html">2.6. Using config files</a></li>
<li class="toctree-l2"><a class="reference internal" href="vacuity.html">2.7. Vacuity</a></li>
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
          <section id="erc20-example-basics">
<h1><span class="section-number">2.3. </span>ERC20 Example - Basics<a class="headerlink" href="#erc20-example-basics" title="Link to this heading">¶</a></h1>
<p>We show how to run a spec and how to interpret the results.</p>
<section id="erc20">
<h2>ERC20<a class="headerlink" href="#erc20" title="Link to this heading">¶</a></h2>
<p>Let’s take as an example a straightforward simple
<a class="reference external" href="https://ethereum.org/en/developers/docs/standards/tokens/erc-20/">ERC20</a>
implementation: <a class="reference external" href="https://github.com/Certora/tutorials-code/blob/master/lesson2_started/erc20/ERC20.sol">ERC20.sol</a>
(found in folder: <a class="reference external" href="https://github.com/Certora/tutorials-code/tree/master/lesson2_started/erc20">ERC20 lesson</a>).
The contract has a mapping from users to their balance and the total supply.
The primary operations are <code class="docutils literal notranslate"><span class="pre">transfer</span></code>, <code class="docutils literal notranslate"><span class="pre">mint</span></code>, <code class="docutils literal notranslate"><span class="pre">burn</span></code> and <code class="docutils literal notranslate"><span class="pre">approve</span></code>.
Here is a diagram of the contracts and interfaces:</p>
<div align="center" class="align-center"><div class="graphviz"><img src="../_images/graphviz-c1f021da59157e2b4e855b16d93794144b6975db.png" alt="digraph {
     graph [
     bgcolor=gray10 color=gold fontcolor=bisque label=&quot;ERC20 Implementation&quot;
     labelloc=t margin=0 rankdir=BT
 ]
     ERC20 [
     label=&quot;{ERC20 | ~onlyOwner\l | increaseAllowance\l | decreaseAllowance\l |
     deposit\l | withdraw\l}&quot;
     color=gold fontcolor=bisque fontname=&quot;DejaVu Sans Mono&quot; fontsize=8 shape=Mrecord
     tooltip=&quot;ERC20.sol&quot;
 ]
     IERC20 [
     label=&quot;{IERC20 | totalSupply\l | balanceOf\l | transfer\l | allowance\l |
     approve\l | transferFrom\l | mint\l | burn\l}&quot;
     color=greenyellow fontcolor=bisque fontname=&quot;DejaVu Sans Mono&quot; fontsize=8
     shape=Mrecord tooltip=&quot;IERC20.sol&quot;
 ]
     IERC20Metadata [
     label=&quot;{IERC20Metadata | name\l | symbol\l | decimals\l}&quot;
     color=greenyellow fontcolor=bisque fontname=&quot;DejaVu Sans Mono&quot; fontsize=8
     shape=Mrecord tooltip=&quot;IERC20Metadata.sol&quot;
 ]
     IERC20Metadata -> IERC20 [
     arrowhead=normal color=gold fontcolor=bisque fontname=&quot;DejaVu Sans Mono&quot;
     fontsize=8 style=solid
 ]
     ERC20 -> IERC20Metadata [
     arrowhead=normal color=gold fontcolor=bisque fontname=&quot;DejaVu Sans Mono&quot;
     fontsize=8 style=solid
 ]
}" class="graphviz" width="256" height="572"></div>
</div>
</section>
<section id="a-simple-rule">
<h2>A simple rule<a class="headerlink" href="#a-simple-rule" title="Link to this heading">¶</a></h2>
<p>Thinking about the function <code class="docutils literal notranslate"><span class="pre">transfer</span></code>, a basic property would be:</p>
<dl class="simple">
<dt><strong>Correct transfer functionality:</strong></dt><dd><p><em>The balance of the beneficiary is increased appropriately.</em></p>
</dd>
</dl>
<p>The rule <code class="docutils literal notranslate"><span class="pre">transferSpec</span></code> in <a class="reference external" href="https://github.com/Certora/tutorials-code/blob/master/lesson2_started/erc20/ERC20.spec">ERC20.spec</a>
(shown below) verifies this property. In fact, it verifies that the <code class="docutils literal notranslate"><span class="pre">transfer</span></code>
operation both decreases the balance of <code class="docutils literal notranslate"><span class="pre">msg.sender</span></code> by the transferred amount,
and increases the balance of the beneficiary.</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre><span></span><span class="cm">/** @title Transfer must move `amount` tokens from the caller's</span>
<span class="cm"> *  account to `recipient`</span>
<span class="cm"> */</span>
<span class="k">rule</span><span class="w"> </span><span class="nc">transferSpec</span><span class="p">(</span><span class="kt">address</span><span class="w"> </span>recipient<span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>amount<span class="p">)</span><span class="w"> </span><span class="p">{</span>

<span class="w">    </span><span class="kt">env</span><span class="w"> </span>e<span class="p">;</span>
<span class="w">    </span>
<span class="w">    </span><span class="c1">// `mathint` is a type that represents an integer of any size</span>
<span class="w">    </span><span class="kt">mathint</span><span class="w"> </span>balance_sender_before<span class="w"> </span><span class="o">=</span><span class="w"> </span>balanceOf<span class="p">(</span>e<span class="p">.</span><span class="kc">msg.sender</span><span class="p">);</span>
<span class="w">    </span><span class="kt">mathint</span><span class="w"> </span>balance_recip_before<span class="w"> </span><span class="o">=</span><span class="w"> </span>balanceOf<span class="p">(</span>recipient<span class="p">);</span>

<span class="w">    </span>transfer<span class="p">(</span>e<span class="p">,</span><span class="w"> </span>recipient<span class="p">,</span><span class="w"> </span>amount<span class="p">);</span>

<span class="w">    </span><span class="kt">mathint</span><span class="w"> </span>balance_sender_after<span class="w"> </span><span class="o">=</span><span class="w"> </span>balanceOf<span class="p">(</span>e<span class="p">.</span><span class="kc">msg.sender</span><span class="p">);</span>
<span class="w">    </span><span class="kt">mathint</span><span class="w"> </span>balance_recip_after<span class="w"> </span><span class="o">=</span><span class="w"> </span>balanceOf<span class="p">(</span>recipient<span class="p">);</span>

<span class="w">    </span><span class="c1">// Operations on mathints can never overflow nor underflow</span>
<span class="w">    </span><span class="kr">assert</span><span class="w"> </span>balance_sender_after<span class="w"> </span><span class="o">==</span><span class="w"> </span>balance_sender_before<span class="w"> </span><span class="o">-</span><span class="w"> </span>amount<span class="p">,</span>
<span class="w">        </span><span class="s2">"transfer must decrease sender's balance by amount"</span><span class="p">;</span>

<span class="w">    </span><span class="kr">assert</span><span class="w"> </span>balance_recip_after<span class="w"> </span><span class="o">==</span><span class="w"> </span>balance_recip_before<span class="w"> </span><span class="o">+</span><span class="w"> </span>amount<span class="p">,</span>
<span class="w">        </span><span class="s2">"transfer must increase recipient's balance by amount"</span><span class="p">;</span>
<span class="p">}</span>
</pre></div>
</div>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>Formal verification can provide complete coverage of the input space,
giving guarantees beyond what is possible from testing alone. All possible inputs
to the transfer function (all possible recipients and all possible amounts) are
taken into account. Additionally, all possible calling contexts are considered.
The Certora Prover represents the calling context through the struct
variable <code class="code highlight cvl docutils literal highlight-cvl"><span class="kt">env</span></code>. Declaring a single variable <code class="code highlight cvl docutils literal highlight-cvl">e</code> of type <code class="code highlight cvl docutils literal highlight-cvl"><span class="kt">env</span></code>
suffices to capture all aspects of the calling contexts. They can also be
addressed individually, some example aspects of the calling context are:</p>
<ul class="simple">
<li><p>“Who is the transfer from?” (<code class="code highlight cvl docutils literal highlight-cvl">e<span class="p">.</span><span class="kc">msg.sender</span></code>)</p></li>
<li><p>“In which block does the deposit occur?” (<code class="code highlight cvl docutils literal highlight-cvl">e<span class="p">.</span><span class="kc">block.number</span></code>)</p></li>
<li><p>“At which time does the deposit occur?” (<code class="code highlight cvl docutils literal highlight-cvl">e<span class="p">.</span><span class="kc">block.timestamp</span></code>)</p></li>
</ul>
</div>
<div class="admonition warning">
<p class="admonition-title">Warning</p>
<p>Every call to a contract function must receive an argument of type
<code class="code highlight cvl docutils literal highlight-cvl"><span class="kt">env</span></code> as its first parameter. We will later see that we can declare certain
functions as entirely independent of the environment
(using the <code class="code highlight cvl docutils literal highlight-cvl"><span class="kr">envfree</span></code> keyword). This will allow us to call such functions without
an <code class="code highlight cvl docutils literal highlight-cvl"><span class="kt">env</span></code> type parameter.</p>
</div>
</section>
<section id="running-the-prover">
<span id="sec-running-the-prover"></span><h2>Running the Prover<a class="headerlink" href="#running-the-prover" title="Link to this heading">¶</a></h2>
<p>Run the following command line (from the <a class="reference external" href="https://github.com/Certora/tutorials-code/tree/master/lesson2_started/erc20">ERC20 lesson</a>
folder):</p>
<div class="highlight-sh notranslate"><div class="highlight"><pre><span></span>certoraRun<span class="w"> </span>ERC20.sol<span class="w"> </span>--verify<span class="w"> </span>ERC20:ERC20.spec<span class="w"> </span>--solc<span class="w"> </span>solc8.0
</pre></div>
</div>
<p>This command triggers a verification run on the contract <code class="docutils literal notranslate"><span class="pre">ERC20</span></code> from the solidity
file <a class="reference external" href="https://github.com/Certora/tutorials-code/blob/master/lesson2_started/erc20/ERC20.sol">ERC20.sol</a>, checking all rules in the
specification file <a class="reference external" href="https://github.com/Certora/tutorials-code/blob/master/lesson2_started/erc20/ERC20.spec">ERC20.spec</a>.</p>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>It is recommended to use config files for running the Prover, see
<a class="reference internal" href="config_files.html#sec-using-config-files"><span class="std std-ref">Using config files</span></a>. Use the command line only for simple cases such as
this example.</p>
</div>
<p>The command proceeds in two steps:</p>
<section id="first-step">
<h3>First step<a class="headerlink" href="#first-step" title="Link to this heading">¶</a></h3>
<p>The solidity files are compiled with the specified solidity compiler, in this
case 0.8.0, and the specification file is checked for syntax errors.
This step happens on the local machine for fast feedback.
The <code class="docutils literal notranslate"><span class="pre">--solc</span></code> argument is optional (see <a class="reference external" href="https://docs.certora.com/en/latest/docs/prover/cli/options.html?highlight=--solc#options-that-control-the-solidity-compiler">Options that control the Solidity compiler</a>)
You can also use this option to provide a path to the Solidity compiler
executable file. The default is  <code class="docutils literal notranslate"><span class="pre">solc</span></code> executable.
You may also omit the <code class="docutils literal notranslate"><span class="pre">--solc</span></code>, if you use
<a class="reference external" href="https://github.com/crytic/solc-select">solc-select</a>, e.g.</p>
<div class="highlight-sh notranslate"><div class="highlight"><pre><span></span>solc-select<span class="w"> </span>use<span class="w"> </span><span class="m">0</span>.8.0
</pre></div>
</div>
</section>
<section id="second-step">
<h3>Second step<a class="headerlink" href="#second-step" title="Link to this heading">¶</a></h3>
<p>All necessary files are compressed and sent to Certora’s web server for
verification. Verification tasks can be very heavy, so running them on the cloud can
save time and resources.</p>
<div class="admonition tip">
<p class="admonition-title">Tip</p>
<p>To learn more about the syntax of the <code class="docutils literal notranslate"><span class="pre">certoraRun</span></code> command and its different
options use the <code class="docutils literal notranslate"><span class="pre">--help</span></code> flag:</p>
<div class="highlight-sh notranslate"><div class="highlight"><pre><span></span>certoraRun<span class="w"> </span>--help
</pre></div>
</div>
</div>
<div class="admonition tip">
<p class="admonition-title">Tip</p>
<p>If you are using MacOS and get a <code class="docutils literal notranslate"><span class="pre">Bad</span> <span class="pre">CPU</span> <span class="pre">type</span> <span class="pre">in</span> <span class="pre">executable</span></code> error,
you can fix it by installing Rosetta. Do this by executing the following in
your terminal:</p>
<div class="highlight-sh notranslate"><div class="highlight"><pre><span></span>softwareupdate<span class="w"> </span>--install-rosetta
</pre></div>
</div>
</div>
</section>
<section id="results">
<h3>Results<a class="headerlink" href="#results" title="Link to this heading">¶</a></h3>
<p>While running, the Prover will print various information to the console about the run.
In the end, the output will look similar to this:</p>
<div class="highlight-text notranslate"><div class="highlight"><pre><span></span>...
[INFO]: Process returned with 100

Job is completed! View the results at https://prover.certora.com/...
Finished verification request
ERROR: Prover found violations:
ERROR: [rule] transferSpec
</pre></div>
</div>
<p>This indicates the Prover found a violation in the rule <code class="docutils literal notranslate"><span class="pre">transferSpec</span></code>.
This violation is a counter example to the rule, and can be viewed in the given link.
Alternatively, you can go to <a class="reference external" href="https://prover.certora.com/">prover.certora.com</a> and
select this job’s link from the list of your recent jobs.
In the link you’ll see the verification report, which looks like this:</p>
<img alt="Report page" src="../_images/erc20_example_results.png" width="1327" height="938">
</section>
</section>
<section id="understanding-rule-violations">
<h2>Understanding rule violations<a class="headerlink" href="#understanding-rule-violations" title="Link to this heading">¶</a></h2>
<section id="viewing-the-counter-example">
<h3>Viewing the counter example<a class="headerlink" href="#viewing-the-counter-example" title="Link to this heading">¶</a></h3>
<p>The Certora Prover helps understand violations of properties by providing concrete
counter examples. To see the counter example, click the violated rule name in the
report page. You will see something like this:</p>
<img alt="Rule counter-example" src="../_images/understnding_rule_violations.png" width="1327" height="938">
<p>The counter-example shows values of the rule’s parameters and variables (on the right
hand side), and a call trace (in the middle).
You can investigate the call trace to see which functions were called, by clicking
on the <code class="docutils literal notranslate"><span class="pre">&gt;</span></code> symbol to open a detailed view.</p>
</section>
<section id="so-what-is-the-bug">
<h3>So, what is the bug?<a class="headerlink" href="#so-what-is-the-bug" title="Link to this heading">¶</a></h3>
<p>Notice that the value of <code class="code highlight cvl docutils literal highlight-cvl">recipient</code> is the same as the value of <code class="code highlight cvl docutils literal highlight-cvl">e<span class="p">.</span><span class="kc">msg.sender</span></code>.
We conclude that:</p>
<p class="rubric">The rule does not hold when a user transfers to himself</p>
<p>Indeed, when a user transfers balance to themselves, their balance should stay the same.
So there is an issue with the rule.</p>
</section>
<section id="fixing-and-re-running">
<h3>Fixing and re-running<a class="headerlink" href="#fixing-and-re-running" title="Link to this heading">¶</a></h3>
<p>Let’s fix the rule and see if this solves the issue. We already have a fixed version
in <a class="reference external" href="https://github.com/Certora/tutorials-code/blob/master/lesson2_started/erc20/ERC20Fixed.spec">ERC20Fixed.spec</a>, so we need only
run it to see if it fixes the issue. Run:</p>
<div class="highlight-sh notranslate"><div class="highlight"><pre><span></span>certoraRun<span class="w"> </span>ERC20.sol<span class="w"> </span>--verify<span class="w"> </span>ERC20:ERC20Fixed.spec<span class="w"> </span>--solc<span class="w"> </span>solc8.0
</pre></div>
</div>
</section>
</section>
<section id="exercise">
<h2>Exercise<a class="headerlink" href="#exercise" title="Link to this heading">¶</a></h2>
<p>Here is the <em>fixed rule</em>. Do you understand why it passes, while the previous failed?</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre><span></span><span class="c1">/// @title Transfer must move `amount` tokens from the caller's account to `recipient`</span>
<span class="k">rule</span><span class="w"> </span><span class="nc">transferSpec</span><span class="p">(</span><span class="kt">address</span><span class="w"> </span>recipient<span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>amount<span class="p">)</span><span class="w"> </span><span class="p">{</span>

<span class="w">    </span><span class="kt">env</span><span class="w"> </span>e<span class="p">;</span>
<span class="w">    </span>
<span class="w">    </span><span class="c1">// `mathint` is a type that represents an integer of any size</span>
<span class="w">    </span><span class="kt">mathint</span><span class="w"> </span>balance_sender_before<span class="w"> </span><span class="o">=</span><span class="w"> </span>balanceOf<span class="p">(</span>e<span class="p">.</span><span class="kc">msg.sender</span><span class="p">);</span>
<span class="w">    </span><span class="kt">mathint</span><span class="w"> </span>balance_recip_before<span class="w"> </span><span class="o">=</span><span class="w"> </span>balanceOf<span class="p">(</span>recipient<span class="p">);</span>

<span class="w">    </span>transfer<span class="p">(</span>e<span class="p">,</span><span class="w"> </span>recipient<span class="p">,</span><span class="w"> </span>amount<span class="p">);</span>

<span class="w">    </span><span class="kt">mathint</span><span class="w"> </span>balance_sender_after<span class="w"> </span><span class="o">=</span><span class="w"> </span>balanceOf<span class="p">(</span>e<span class="p">.</span><span class="kc">msg.sender</span><span class="p">);</span>
<span class="w">    </span><span class="kt">mathint</span><span class="w"> </span>balance_recip_after<span class="w"> </span><span class="o">=</span><span class="w"> </span>balanceOf<span class="p">(</span>recipient<span class="p">);</span>

<span class="w">    </span><span class="kt">address</span><span class="w"> </span>sender<span class="w"> </span><span class="o">=</span><span class="w"> </span>e<span class="p">.</span><span class="kc">msg.sender</span><span class="p">;</span><span class="w">  </span><span class="c1">// A convenient alias</span>

<span class="w">    </span><span class="c1">// Operations on mathints can never overflow or underflow. </span>
<span class="w">    </span><span class="kr">assert</span><span class="w"> </span>recipient<span class="w"> </span><span class="o">!=</span><span class="w"> </span>sender<span class="w"> </span><span class="o">=&gt;</span><span class="w"> </span>balance_sender_after<span class="w"> </span><span class="o">==</span><span class="w"> </span>balance_sender_before<span class="w"> </span><span class="o">-</span><span class="w"> </span>amount<span class="p">,</span>
<span class="w">        </span><span class="s2">"transfer must decrease sender's balance by amount"</span><span class="p">;</span>

<span class="w">    </span><span class="kr">assert</span><span class="w"> </span>recipient<span class="w"> </span><span class="o">!=</span><span class="w"> </span>sender<span class="w"> </span><span class="o">=&gt;</span><span class="w"> </span>balance_recip_after<span class="w"> </span><span class="o">==</span><span class="w"> </span>balance_recip_before<span class="w"> </span><span class="o">+</span><span class="w"> </span>amount<span class="p">,</span>
<span class="w">        </span><span class="s2">"transfer must increase recipient's balance by amount"</span><span class="p">;</span>
<span class="w">    </span>
<span class="w">    </span><span class="kr">assert</span><span class="w"> </span>recipient<span class="w"> </span><span class="o">==</span><span class="w"> </span>sender<span class="w"> </span><span class="o">=&gt;</span><span class="w"> </span>balance_sender_after<span class="w"> </span><span class="o">==</span><span class="w"> </span>balance_sender_before<span class="p">,</span>
<span class="w">        </span><span class="s2">"transfer must not change sender's balancer when transferring to self"</span><span class="p">;</span>
<span class="p">}</span>
</pre></div>
</div>
</section>
</section>

        </article>
      </div>
      <footer>
        
        <div class="related-pages">
          <a class="next-page" href="preconditions.html">
              <div class="page-info">
                <div class="context">
                  <span>Next</span>
                </div>
                <div class="title"><span class="section-number">2.4. </span>ERC20 Example - preconditions</div>
              </div>
              <svg class="furo-related-icon"><use href="#svg-arrow-right"></use></svg>
            </a>
          <a class="prev-page" href="overview.html">
              <svg class="furo-related-icon"><use href="#svg-arrow-right"></use></svg>
              <div class="page-info">
                <div class="context">
                  <span>Previous</span>
                </div>
                
                <div class="title"><span class="section-number">2.2. </span>Technology Overview</div>
                
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
<li><a class="reference internal" href="#">2.3. ERC20 Example - Basics</a><ul>
<li><a class="reference internal" href="#erc20">ERC20</a></li>
<li><a class="reference internal" href="#a-simple-rule">A simple rule</a></li>
<li><a class="reference internal" href="#running-the-prover">Running the Prover</a><ul>
<li><a class="reference internal" href="#first-step">First step</a></li>
<li><a class="reference internal" href="#second-step">Second step</a></li>
<li><a class="reference internal" href="#results">Results</a></li>
</ul>
</li>
<li><a class="reference internal" href="#understanding-rule-violations">Understanding rule violations</a><ul>
<li><a class="reference internal" href="#viewing-the-counter-example">Viewing the counter example</a></li>
<li><a class="reference internal" href="#so-what-is-the-bug">So, what is the bug?</a></li>
<li><a class="reference internal" href="#fixing-and-re-running">Fixing and re-running</a></li>
</ul>
</li>
<li><a class="reference internal" href="#exercise">Exercise</a></li>
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