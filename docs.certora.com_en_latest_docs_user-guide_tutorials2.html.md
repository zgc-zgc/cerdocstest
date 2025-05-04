<!DOCTYPE html><html class="writer-html5" lang="en" data-content_root="../../"><head>
  <meta charset="utf-8"><meta name="viewport" content="width=device-width, initial-scale=1">

  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Tutorial and Workshops — Certora Prover Documentation 0.0 documentation</title>
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
    <link rel="next" title="Running the Certora Prover" href="running.html">
    <link rel="prev" title="Installing an EVM compiler and VS Code Extension" href="install_evm_compiler.html"> 
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
<li class="toctree-l2 current" aria-expanded="true"><a class="reference internal current" href="#" aria-expanded="true"><button class="toctree-expand" title="Open/close menu"></button>Tutorial and Workshops</a><ul>
<li class="toctree-l3"><a class="reference internal" href="#tutorial">Tutorial</a></li>
<li class="toctree-l3"><a class="reference internal" href="#examples">Examples</a></li>
<li class="toctree-l3"><a class="reference internal" href="#stanford-defi-security-summit">Stanford DeFi Security Summit</a></li>
<li class="toctree-l3"><a class="reference internal" href="#ethcc-paris">EthCC Paris</a></li>
<li class="toctree-l3"><a class="reference internal" href="#aave-community-day">Aave Community Day</a></li>
</ul>
</li>
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
<li class="toctree-l2"><a class="reference internal" href="gaps.html">Understanding gaps between high and low level code</a></li>
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
      <li class="breadcrumb-item active">Tutorial and Workshops</li>
      <li class="wy-breadcrumbs-aside">
            <a href="../../_sources/docs/user-guide/tutorials.md.txt" rel="nofollow"> View page source</a>
      </li>
  </ul>
  <hr>
</div>
          <div role="main" class="document" itemscope="itemscope" itemtype="http://schema.org/Article">
           <div itemprop="articleBody">
             
  <section id="tutorial-and-workshops">
<h1>Tutorial and Workshops<a class="headerlink" href="#tutorial-and-workshops" title="Link to this heading"></a></h1>
<section id="tutorial">
<span id="id1"></span><h2>Tutorial<a class="headerlink" href="#tutorial" title="Link to this heading"></a></h2>
<p>The Certora Tutorial is a series of guided lessons that covers installation and
basic usage of the Certora Prover.</p>
<p>It is available <a class="reference external" href="https://docs.certora.com/projects/tutorials">here</a>.</p>
<p>The Tutorial is organized as a series of lessons and exercises.  You are
encouraged to clone the <a class="reference external" href="https://github.com/Certora/tutorials-code">git repository</a> and work through the exercises yourself.</p>
</section>
<section id="examples">
<h2>Examples<a class="headerlink" href="#examples" title="Link to this heading"></a></h2>
<p>A set of examples featuring CVL are available on <a class="reference external" href="https://github.com/Certora/Examples">github</a>.</p>
</section>
<section id="stanford-defi-security-summit">
<span id="stanford"></span><h2>Stanford DeFi Security Summit<a class="headerlink" href="#stanford-defi-security-summit" title="Link to this heading"></a></h2>
<p><a class="reference external" href="https://www.youtube.com/playlist?list=PLKtu7wuOMP9Wp_O8kylKbtFYgM8HVTGIA">The Stanford DeFi Security Summit, August 2022</a> is a recorded 2-day workshop that
covers basic Prover usage with several hands-on examples.  It covers the
following topics:</p>
<div class="wy-table-responsive"><table class="docutils align-default">
<thead>
<tr class="row-odd"><th class="head"><p>Video</p></th>
<th class="head"><p>Slides</p></th>
</tr>
</thead>
<tbody>
<tr class="row-even"><td><p><a class="reference external" href="https://youtu.be/1bbI-i2Y0BA">Overview                   </a></p></td>
<td><p></p></td>
</tr>
<tr class="row-odd"><td><p><a class="reference external" href="https://youtu.be/siEDkMNbl5o">Installation and setup     </a></p></td>
<td><p>(<a class="reference download internal" download="" href="../../_downloads/5b01f3549271d3828006c2a611e29c4e/02-setup.pdf"><code class="xref download docutils literal notranslate"><span class="pre">slides</span></code></a>)</p></td>
</tr>
<tr class="row-even"><td><p><a class="reference external" href="https://youtu.be/siEDkMNbl5o?t=1076">Writing basic rules        </a></p></td>
<td><p>(<a class="reference download internal" download="" href="../../_downloads/268bf797ccddc7df3b4a7393e150cee3/03-rules.pdf"><code class="xref download docutils literal notranslate"><span class="pre">slides</span></code></a>)</p></td>
</tr>
<tr class="row-odd"><td><p><a class="reference external" href="https://youtu.be/siEDkMNbl5o?t=2840">Writing parametric rules   </a></p></td>
<td><p>(<a class="reference download internal" download="" href="../../_downloads/0b224e7bf801b01ec6405fd16e85b86e/04-parametric.pdf"><code class="xref download docutils literal notranslate"><span class="pre">slides</span></code></a>)</p></td>
</tr>
<tr class="row-even"><td><p><a class="reference external" href="https://youtu.be/gkK3KeD7AQw">Invariants                 </a></p></td>
<td><p>(<a class="reference download internal" download="" href="../../_downloads/dfde1c098cbf5480a6c7c3b4c7c254bd/05-invariants.pdf"><code class="xref download docutils literal notranslate"><span class="pre">slides</span></code></a>)</p></td>
</tr>
<tr class="row-odd"><td><p>Ghosts and hooks (<a class="reference external" href="https://youtu.be/gkK3KeD7AQw?t=2993">part 1</a>, <a class="reference external" href="https://youtu.be/fHHVoRNocdE">part 2</a>)</p></td>
<td><p>(<a class="reference download internal" download="" href="../../_downloads/5c9e390835b183a0f181aa9f4345b353/06-ghosts.pdf"><code class="xref download docutils literal notranslate"><span class="pre">slides</span></code></a>)</p></td>
</tr>
<tr class="row-even"><td><p><a class="reference external" href="https://youtu.be/DcbBSab3s3E?t=80">Hyperproperties            </a></p></td>
<td><p>(<a class="reference download internal" download="" href="../../_downloads/b03ef9216c924c7d43ace2cbfb9c5d44/07-hyperproperties.pdf"><code class="xref download docutils literal notranslate"><span class="pre">slides</span></code></a>)</p></td>
</tr>
<tr class="row-odd"><td><p><a class="reference external" href="https://youtu.be/DcbBSab3s3E?t=374">Designing specifications   </a></p></td>
<td><p>(<a class="reference download internal" download="" href="../../_downloads/261821f49e09d1527573ae9858995527/08-design.pdf"><code class="xref download docutils literal notranslate"><span class="pre">slides</span></code></a>)</p></td>
</tr>
<tr class="row-even"><td><p><a class="reference external" href="https://youtu.be/vg6da3A7lSs">The Certora Prover pipeline</a></p></td>
<td><p>(<a class="reference download internal" download="" href="../../_downloads/7ef350bb9818a0b10467fa47e9e22877/09-pipeline.pdf"><code class="xref download docutils literal notranslate"><span class="pre">slides</span></code></a>)</p></td>
</tr>
<tr class="row-odd"><td><p><a class="reference external" href="https://youtu.be/9QuS_8cL91w">SMT solvers                </a></p></td>
<td><p>(<a class="reference download internal" download="" href="../../_downloads/c76664d62417cfcd2e962a8ab82f8d0f/10-smt.pdf"><code class="xref download docutils literal notranslate"><span class="pre">slides</span></code></a>)</p></td>
</tr>
</tbody>
</table></div>
<p>The covered examples are available in the <a class="reference external" href="https://github.com/Certora/Examples">CVL examples repository</a>.</p>
</section>
<section id="ethcc-paris">
<span id="paris"></span><h2>EthCC Paris<a class="headerlink" href="#ethcc-paris" title="Link to this heading"></a></h2>
<p><a class="reference external" href="https://www.youtube.com/playlist?list=PLKtu7wuOMP9XHbjAevkw2nL29YMubqEFj">EthCC Paris, July 2022</a> is an earlier 3-day workshop in a similar
style that covers the same material and a few additional topics:</p>
<div class="wy-table-responsive"><table class="docutils align-default">
<thead>
<tr class="row-odd"><th class="head"><p>Video</p></th>
<th class="head"><p>Notes</p></th>
</tr>
</thead>
<tbody>
<tr class="row-even"><td><p><a class="reference external" href="https://www.youtube.com/watch?v=sdEfc-58CUE&amp;amp;list=PLKtu7wuOMP9XHbjAevkw2nL29YMubqEFj&amp;amp;index=1&amp;amp;t=1s">Overview                    </a></p></td>
<td><p></p></td>
</tr>
<tr class="row-odd"><td><p><a class="reference external" href="https://www.youtube.com/watch?v=CwCX0TuDfTE&amp;amp;list=PLKtu7wuOMP9XHbjAevkw2nL29YMubqEFj&amp;amp;index=2&amp;amp;t=2s">Installation and setup      </a></p></td>
<td><p></p></td>
</tr>
<tr class="row-even"><td><p><a class="reference external" href="https://www.youtube.com/watch?v=66Gjzgl87L8&amp;amp;list=PLKtu7wuOMP9XHbjAevkw2nL29YMubqEFj&amp;amp;index=3&amp;amp;t=21s">Writing basic rules         </a></p></td>
<td><p></p></td>
</tr>
<tr class="row-odd"><td><p><a class="reference external" href="https://www.youtube.com/watch?v=gMjELxgMY30&amp;amp;list=PLKtu7wuOMP9XHbjAevkw2nL29YMubqEFj&amp;amp;index=4&amp;amp;t=534s">Writing parametric rules    </a></p></td>
<td><p></p></td>
</tr>
<tr class="row-even"><td><p><a class="reference external" href="https://www.youtube.com/watch?v=VqboepMVbg4&amp;amp;list=PLKtu7wuOMP9XHbjAevkw2nL29YMubqEFj&amp;amp;index=5&amp;amp;t=2s">Invariants                  </a></p></td>
<td><p></p></td>
</tr>
<tr class="row-odd"><td><p><a class="reference external" href="https://www.youtube.com/watch?v=WR8eAQZzd8Y&amp;amp;list=PLKtu7wuOMP9XHbjAevkw2nL29YMubqEFj&amp;amp;index=6">Multicontract verification  </a></p></td>
<td><p>Not covered in Stanford workshop</p></td>
</tr>
<tr class="row-even"><td><p><a class="reference external" href="https://www.youtube.com/watch?v=jAiBUebBs88&amp;amp;list=PLKtu7wuOMP9XHbjAevkw2nL29YMubqEFj&amp;amp;index=7">The Certora Prover pipeline </a></p></td>
<td><p></p></td>
</tr>
<tr class="row-odd"><td><p><a class="reference external" href="https://www.youtube.com/watch?v=f3K-68k7vig&amp;amp;list=PLKtu7wuOMP9XHbjAevkw2nL29YMubqEFj&amp;amp;index=8">Designing specifications    </a></p></td>
<td><p></p></td>
</tr>
<tr class="row-even"><td><p><a class="reference external" href="https://www.youtube.com/watch?v=GLGXQSaE5b4&amp;amp;list=PLKtu7wuOMP9XHbjAevkw2nL29YMubqEFj&amp;amp;index=9">Liquidity pool example      </a></p></td>
<td><p>Not covered in Stanford workshop</p></td>
</tr>
<tr class="row-odd"><td><p><a class="reference external" href="https://www.youtube.com/watch?v=csTe6ub3Jwg&amp;amp;list=PLKtu7wuOMP9XHbjAevkw2nL29YMubqEFj&amp;amp;index=10">Checking the spec           </a></p></td>
<td><p>Not covered in Stanford workshop</p></td>
</tr>
<tr class="row-even"><td><p><a class="reference external" href="https://www.youtube.com/watch?v=NQ1ZQnlYFOQ&amp;amp;list=PLKtu7wuOMP9XHbjAevkw2nL29YMubqEFj&amp;amp;index=11">Ghosts and hooks            </a></p></td>
<td><p></p></td>
</tr>
</tbody>
</table></div>
<p>The last day of the workshop was devoted to an extended exercise verifying the
version 3 of the Aave Token:</p>
<div class="wy-table-responsive"><table class="docutils align-default">
<thead>
<tr class="row-odd"><th class="head"><p>Video</p></th>
</tr>
</thead>
<tbody>
<tr class="row-even"><td><p><a class="reference external" href="https://www.youtube.com/watch?v=BGdHsvQMmy8&amp;amp;list=PLKtu7wuOMP9XHbjAevkw2nL29YMubqEFj&amp;amp;index=12&amp;amp;t=1618s">Aave token overview         </a></p></td>
</tr>
<tr class="row-odd"><td><p><a class="reference external" href="https://www.youtube.com/watch?v=_YW-uReng44&amp;amp;list=PLKtu7wuOMP9XHbjAevkw2nL29YMubqEFj&amp;amp;index=13&amp;amp;t=25s">Aave token properties       </a></p></td>
</tr>
<tr class="row-even"><td><p><a class="reference external" href="https://www.youtube.com/watch?v=Epe90JSmNqc&amp;amp;list=PLKtu7wuOMP9XHbjAevkw2nL29YMubqEFj&amp;amp;index=14">Aave token setup            </a></p></td>
</tr>
<tr class="row-odd"><td><p><a class="reference external" href="https://www.youtube.com/watch?v=IPasjUOFUdA&amp;amp;list=PLKtu7wuOMP9XHbjAevkw2nL29YMubqEFj&amp;amp;index=15">Aave token exercise         </a></p></td>
</tr>
</tbody>
</table></div>
</section>
<section id="aave-community-day">
<h2>Aave Community Day<a class="headerlink" href="#aave-community-day" title="Link to this heading"></a></h2>
<p><a class="reference external" href="https://www.youtube.com/playlist?list=PLKtu7wuOMP9WOLJNPafbrd0lehfc7yxso">Aave Community Day, April 2022</a> is a condensed 3-hour workshop with
fewer exercises.</p>
</section>
</section>


           </div>
          </div>
          <footer><div class="rst-footer-buttons" role="navigation" aria-label="Footer">
        <a href="install_evm_compiler.html" class="btn btn-neutral float-left" title="Installing an EVM compiler and VS Code Extension" accesskey="p" rel="prev"><span class="fa fa-arrow-circle-left" aria-hidden="true"></span> Previous</a>
        <a href="running.html" class="btn btn-neutral float-right" title="Running the Certora Prover" accesskey="n" rel="next">Next <span class="fa fa-arrow-circle-right" aria-hidden="true"></span></a>
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