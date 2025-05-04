<!DOCTYPE html><html class="writer-html5" lang="en" data-content_root="../../"><head>
  <meta charset="utf-8"><meta name="viewport" content="width=device-width, initial-scale=1">

  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>User Guide For Sunbeam — Certora Prover Documentation 0.0 documentation</title>
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
    <link rel="next" title="Troubleshooting" href="troubleshooting.html">
    <link rel="prev" title="Installation" href="installation.html"> 
</head>

<body class="wy-body-for-nav"> 
  <div class="wy-grid-for-nav">
    <nav data-toggle="wy-nav-shift" class="wy-nav-side">
      <div class="wy-side-scroll">
        <div class="wy-side-nav-search">

          
          
          <a href="../../index.html" class="icon icon-home">
            Certora Prover Documentation
              <img src="../../_static/Certora_Logo_Black.svg" class="logo" alt="Logo">
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
<li class="toctree-l1 current" aria-expanded="true"><a class="reference internal" href="index.html"><button class="toctree-expand" title="Open/close menu"></button>Sunbeam: Verification for Soroban</a><ul class="" aria-expanded="false">
<li class="toctree-l2"><a class="reference internal" href="installation.html">Installation</a></li>
<li class="toctree-l2 current" aria-expanded="true"><a class="reference internal current" href="#" aria-expanded="true"><button class="toctree-expand" title="Open/close menu"></button>User Guide For Sunbeam</a><ul>
<li class="toctree-l3"><a class="reference internal" href="#what-is-sunbeam">What is Sunbeam?</a></li>
<li class="toctree-l3"><a class="reference internal" href="#writing-specs">Writing Specs</a></li>
<li class="toctree-l3"><a class="reference internal" href="#rules-and-assertions">Rules and assertions</a></li>
<li class="toctree-l3"><a class="reference internal" href="#nondet">Nondet</a></li>
<li class="toctree-l3"><a class="reference internal" href="#examples">Examples</a></li>
<li class="toctree-l3"><a class="reference internal" href="#running-sunbeam">Running Sunbeam</a></li>
<li class="toctree-l3"><a class="reference internal" href="#after-running-sunbeam">After running Sunbeam</a></li>
</ul>
</li>
<li class="toctree-l2"><a class="reference internal" href="troubleshooting.html">Troubleshooting</a></li>
</ul>
</li>
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
          <li class="breadcrumb-item"><a href="index.html">Sunbeam: Verification for Soroban</a></li>
      <li class="breadcrumb-item active">User Guide For Sunbeam</li>
      <li class="wy-breadcrumbs-aside">
            <a href="../../_sources/docs/sunbeam/usage.rst.txt" rel="nofollow"> View page source</a>
      </li>
  </ul>
  <hr>
</div>
          <div role="main" class="document" itemscope="itemscope" itemtype="http://schema.org/Article">
           <div itemprop="articleBody">
             
  <section id="user-guide-for-sunbeam">
<h1>User Guide For Sunbeam<a class="headerlink" href="#user-guide-for-sunbeam" title="Link to this heading"></a></h1>
<p>Before reading this, make sure you have followed the installation guide.</p>
<section id="what-is-sunbeam">
<h2>What is Sunbeam?<a class="headerlink" href="#what-is-sunbeam" title="Link to this heading"></a></h2>
<p>Sunbeam is a tool for formally verifying Soroban smart contracts written in Rust. It allows you to write specifications describing the behavior and invariants of your contract, then mathematically proves that your code adheres to those specifications. A recent <a class="reference external" href="https://certora.vercel.app/blog/formally-verifying-webassembly">blog</a> explains the core technology behind Sunbeam.</p>
</section>
<section id="writing-specs">
<h2>Writing Specs<a class="headerlink" href="#writing-specs" title="Link to this heading"></a></h2>
<p>Specifications for Sunbeam are written as Rust functions. We use Certora’s <a class="reference external" href="https://github.com/Certora/cvlr">Cavalier spec library</a> which relies on Rust macros. You may also require some of the <a class="reference external" href="https://github.com/Certora/cvlr-soroban/">Soroban specific macros</a>.</p>
</section>
<section id="rules-and-assertions">
<h2>Rules and assertions<a class="headerlink" href="#rules-and-assertions" title="Link to this heading"></a></h2>
<p>A specification is simply a function annotated with the <code class="docutils literal notranslate"><span class="pre">#[rule]</span></code> attribute. These rules make assertions about your smart contract code using the <code class="docutils literal notranslate"><span class="pre">cvlr_assert!</span></code>, <code class="docutils literal notranslate"><span class="pre">cvlr_assume!</span></code> and <code class="docutils literal notranslate"><span class="pre">cvlr_satisfy!</span></code> macros. For example:</p>
<div class="highlight-rust notranslate"><div class="highlight"><pre id="codecell0"><span></span><span class="cp">#[rule]</span>
<span class="k">fn</span><span class="w"> </span><span class="nf">transfer_is_correct</span><span class="p">(</span><span class="n">e</span><span class="p">:</span><span class="w"> </span><span class="nc">Env</span><span class="p">,</span><span class="w"> </span><span class="n">to</span><span class="p">:</span><span class="w"> </span><span class="nc">Address</span><span class="p">,</span><span class="w"> </span><span class="n">from</span><span class="p">:</span><span class="w"> </span><span class="nc">Address</span><span class="p">,</span><span class="w"> </span><span class="n">amount</span><span class="p">:</span><span class="w"> </span><span class="kt">i64</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="n">cvlr_assume</span><span class="o">!</span><span class="p">(</span>
<span class="w">        </span><span class="n">e</span><span class="p">.</span><span class="n">storage</span><span class="p">().</span><span class="n">persistent</span><span class="p">().</span><span class="n">has</span><span class="p">(</span><span class="o">&amp;</span><span class="n">from</span><span class="p">)</span><span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span><span class="n">e</span><span class="p">.</span><span class="n">storage</span><span class="p">().</span><span class="n">persistent</span><span class="p">().</span><span class="n">has</span><span class="p">(</span><span class="o">&amp;</span><span class="n">to</span><span class="p">)</span><span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span><span class="n">to</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="n">from</span><span class="p">);</span>
<span class="w">    </span><span class="kd">let</span><span class="w"> </span><span class="n">balance_from_before</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">Token</span><span class="p">::</span><span class="n">balance</span><span class="p">(</span><span class="o">&amp;</span><span class="n">e</span><span class="p">,</span><span class="w"> </span><span class="n">from</span><span class="p">.</span><span class="n">clone</span><span class="p">());</span>
<span class="w">    </span><span class="kd">let</span><span class="w"> </span><span class="n">balance_to_before</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">Token</span><span class="p">::</span><span class="n">balance</span><span class="p">(</span><span class="o">&amp;</span><span class="n">e</span><span class="p">,</span><span class="w"> </span><span class="n">to</span><span class="p">.</span><span class="n">clone</span><span class="p">());</span>
<span class="w">    </span><span class="n">Token</span><span class="p">::</span><span class="n">transfer</span><span class="p">(</span><span class="o">&amp;</span><span class="n">e</span><span class="p">,</span><span class="w"> </span><span class="n">from</span><span class="p">.</span><span class="n">clone</span><span class="p">(),</span><span class="w"> </span><span class="n">to</span><span class="p">.</span><span class="n">clone</span><span class="p">(),</span><span class="w"> </span><span class="n">amount</span><span class="p">);</span>
<span class="w">    </span><span class="kd">let</span><span class="w"> </span><span class="n">balance_from_after</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">Token</span><span class="p">::</span><span class="n">balance</span><span class="p">(</span><span class="o">&amp;</span><span class="n">e</span><span class="p">,</span><span class="w"> </span><span class="n">from</span><span class="p">.</span><span class="n">clone</span><span class="p">());</span>
<span class="w">    </span><span class="kd">let</span><span class="w"> </span><span class="n">balance_to_after</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">Token</span><span class="p">::</span><span class="n">balance</span><span class="p">(</span><span class="o">&amp;</span><span class="n">e</span><span class="p">,</span><span class="w"> </span><span class="n">to</span><span class="p">.</span><span class="n">clone</span><span class="p">());</span>
<span class="w">    </span><span class="n">cvlr_assert</span><span class="o">!</span><span class="p">(</span>
<span class="w">        </span><span class="p">(</span><span class="n">balance_to_after</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="n">balance_to_before</span><span class="w"> </span><span class="o">+</span><span class="w"> </span><span class="n">amount</span><span class="p">)</span>
<span class="w">            </span><span class="o">&amp;&amp;</span><span class="w"> </span><span class="p">(</span><span class="n">balance_from_after</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="n">balance_from_before</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="n">amount</span><span class="p">)</span>
<span class="w">    </span><span class="p">);</span>
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
<p>Depending on the property you prove, it is possible that you may need to define “ghost variables” that are intended only for verification. A Ghost variable offers a way to annotate the program to track additional information that can be useful for verification. A simple example can be found <a class="reference external" href="https://github.com/Certora/reflector-subscription-contract/blob/51944577dc4536e9cf9711db6e125fe1e2254054/src/lib.rs#L44">here</a>. We encourage you to look into its usage to understand how you may use a similar approach.</p>
</section>
<section id="nondet">
<h2>Nondet<a class="headerlink" href="#nondet" title="Link to this heading"></a></h2>
<p>When formally verifying real-world programs, it is not uncommon to encounter “solver timeouts”. This means that the underlying SMT solver timed out and was not able to verify the property. One way to mitigate this is by “summarizing the code” — this is often done by replacing some parts of the code (e.g., a function body) with something else that is easier for SMT solvers to handle while being a sound overapproximation of the original logic of the code.</p>
<p>A common summary that is often used is <code class="docutils literal notranslate"><span class="pre">nondet</span></code>. This essentially allows the prover to use a nondeterministically chosen value instead of performing a more complex computation or function call. Sunbeams’s spec language, Cavalier provides <cite>nondet</cite> implementations for various primitive types. Additional ones for Soroban are also provided in <a class="reference external" href="https://github.com/Certora/cvlr-soroban/blob/main/cvlr-soroban/src/nondet.rs">cvlr-soroban</a>. More can be added to this repository as needed.</p>
<p>You can also implement <code class="docutils literal notranslate"><span class="pre">nondet</span></code> for user-defined types like so:</p>
<div class="highlight-rust notranslate"><div class="highlight"><pre id="codecell1"><span></span><span class="c1">// Example from the Blend protocol</span>
<span class="k">pub</span><span class="w"> </span><span class="k">struct</span><span class="w"> </span><span class="nc">Q4W</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="k">pub</span><span class="w"> </span><span class="n">amount</span><span class="p">:</span><span class="w"> </span><span class="kt">i128</span><span class="p">,</span>
<span class="w">    </span><span class="k">pub</span><span class="w"> </span><span class="n">exp</span><span class="p">:</span><span class="w"> </span><span class="kt">u64</span><span class="p">,</span>
<span class="p">}</span>

<span class="k">impl</span><span class="w"> </span><span class="n">cvlr</span><span class="p">::</span><span class="n">nondet</span><span class="p">::</span><span class="n">Nondet</span><span class="w"> </span><span class="k">for</span><span class="w"> </span><span class="n">Q4W</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="k">fn</span><span class="w"> </span><span class="nf">nondet</span><span class="p">()</span><span class="w"> </span><span class="p">-&gt;</span><span class="w"> </span><span class="nc">Self</span><span class="w"> </span><span class="p">{</span>
<span class="w">        </span><span class="bp">Self</span><span class="w"> </span><span class="p">{</span>
<span class="w">            </span><span class="n">amount</span><span class="p">:</span><span class="w"> </span><span class="nc">cvlr</span><span class="p">::</span><span class="n">nondet</span><span class="p">(),</span>
<span class="w">            </span><span class="n">exp</span><span class="p">:</span><span class="w"> </span><span class="nc">cvlr</span><span class="p">::</span><span class="n">nondet</span><span class="p">()</span>
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
</section>
<section id="examples">
<h2>Examples<a class="headerlink" href="#examples" title="Link to this heading"></a></h2>
<p>We encourage users to check out the <a class="reference external" href="https://certora-sunbeam-tutorials.readthedocs-hosted.com/en/latest/">Sunbeam Tutorials</a> for learning more about how to use the tool.</p>
</section>
<section id="running-sunbeam">
<h2>Running Sunbeam<a class="headerlink" href="#running-sunbeam" title="Link to this heading"></a></h2>
<p>As the tutorial shows, the easiest way to run Sunbeam is via <code class="docutils literal notranslate"><span class="pre">conf</span></code> files which provide all the arguments and flags required for Sunbeam. We recommend making a directory for your project where you can save these files. Then you can run the tool like so:</p>
<div class="highlight-bash notranslate"><div class="highlight"><pre id="codecell2"><span></span><span class="nb">cd</span><span class="w"> </span>projects/path/to/conf/files
certoraSorobanProver<span class="w"> </span>filename.conf
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell2">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>Typically a conf file looks like this:</p>
<div class="highlight-json notranslate"><div class="highlight"><pre id="codecell3"><span></span><span class="p">{</span>
<span class="w">    </span><span class="nt">"build_script"</span><span class="p">:</span><span class="w"> </span><span class="s2">"../certora_build.py"</span><span class="p">,</span>
<span class="w">    </span><span class="nt">"process"</span><span class="p">:</span><span class="w"> </span><span class="s2">"emv"</span><span class="p">,</span>
<span class="w">    </span><span class="nt">"rule"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span>
<span class="w">        </span><span class="s2">"init_balance"</span><span class="p">,</span>
<span class="w">        </span><span class="s2">"transfer_is_correct"</span><span class="p">,</span>
<span class="w">        </span><span class="s2">"transfer_no_effect_on_other"</span><span class="p">,</span>
<span class="w">        </span><span class="s2">"transfer_fails_if_low_balance"</span>
<span class="w">    </span><span class="p">]</span>
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
<p>The <code class="docutils literal notranslate"><span class="pre">rule</span></code> field has the names the rust functions corresponding to the <code class="docutils literal notranslate"><span class="pre">rules</span></code> you wrote for verifying properties of the smart contract. During setup,  we encourage you to make a  <code class="docutils literal notranslate"><span class="pre">certora_build.py</span></code> script similar to the one in the <a class="reference external" href="https://github.com/Certora/sunbeam-tutorials/blob/main/projects/token/certora_build.py">tutorial</a>. You will likely need to only adapt the global variables at the top of the script according to your project:</p>
<div class="highlight-python notranslate"><div class="highlight"><pre id="codecell4"><span></span><span class="c1"># Command to run for compiling the rust project.</span>
<span class="n">COMMAND</span> <span class="o">=</span> <span class="s2">"just build"</span>

<span class="c1"># JSON FIELDS</span>
<span class="n">PROJECT_DIR</span> <span class="o">=</span> <span class="p">(</span><span class="n">SCRIPT_DIR</span><span class="p">)</span><span class="o">.</span><span class="n">resolve</span><span class="p">()</span>
<span class="n">SOURCES</span> <span class="o">=</span> <span class="p">[</span><span class="s2">"src/path/to/rust/files/*.rs"</span><span class="p">,</span> <span class="s2">"Cargo.toml"</span><span class="p">]</span>
<span class="n">EXECUTABLES</span> <span class="o">=</span> <span class="s2">"target/wasm32-unknown-unknown/release/wasm_file_name.wasm"</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell4">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p><code class="docutils literal notranslate"><span class="pre">SOURCES</span></code> lets the user control all the source files that they would like to see in the report. <code class="docutils literal notranslate"><span class="pre">EXECUTABLES</span></code> has the WASM binary file that is to be verified. <code class="docutils literal notranslate"><span class="pre">COMMAND</span></code> tells Sunbeam how to compile the project. In this example, we used <code class="docutils literal notranslate"><span class="pre">just</span></code> to compile the project, so it says <code class="docutils literal notranslate"><span class="pre">just</span> <span class="pre">build</span></code> but it could also be <code class="docutils literal notranslate"><span class="pre">make</span></code> or <code class="docutils literal notranslate"><span class="pre">cargo</span> <span class="pre">build</span> <span class="pre">--release</span></code>, etc.</p>
<p>Alternatively, you can also compile the project on your own and provide a path to the binary directly in the <code class="docutils literal notranslate"><span class="pre">conf</span></code> file:</p>
<div class="highlight-json notranslate"><div class="highlight"><pre id="codecell5"><span></span><span class="p">{</span>
<span class="w">    </span><span class="nt">"files"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="s2">"target/wasm32-unknown-unknown/release/wasm_file_name.wasm"</span><span class="p">],</span>
<span class="w">    </span><span class="nt">"process"</span><span class="p">:</span><span class="w"> </span><span class="s2">"emv"</span><span class="p">,</span>
<span class="w">    </span><span class="nt">"rule"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span>
<span class="w">        </span><span class="s2">"init_balance"</span><span class="p">,</span>
<span class="w">        </span><span class="s2">"transfer_is_correct"</span><span class="p">,</span>
<span class="w">        </span><span class="s2">"transfer_no_effect_on_other"</span><span class="p">,</span>
<span class="w">        </span><span class="s2">"transfer_fails_if_low_balance"</span>
<span class="w">    </span><span class="p">]</span>
<span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell5">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
<section id="after-running-sunbeam">
<h2>After running Sunbeam<a class="headerlink" href="#after-running-sunbeam" title="Link to this heading"></a></h2>
<p>Once you run Sunbeam as described above, it will send a verification job to Certora’s cloud. You will receive a link to a report page for example something like <a class="reference external" href="https://prover.certora.com/output/33158/43d2f53488204780bcb004e91be562a9/?anonymousKey=21e6b9c505d1c3eecb004bcdf5778b53b8197a41">this</a>. The page shows the status of the rules, provides a call trace when there is a counter example, and also shows the rust source code.</p>
</section>
</section>


           </div>
          </div>
          <footer><div class="rst-footer-buttons" role="navigation" aria-label="Footer">
        <a href="installation.html" class="btn btn-neutral float-left" title="Installation" accesskey="p" rel="prev"><span class="fa fa-arrow-circle-left" aria-hidden="true"></span> Previous</a>
        <a href="troubleshooting.html" class="btn btn-neutral float-right" title="Troubleshooting" accesskey="n" rel="next">Next <span class="fa fa-arrow-circle-right" aria-hidden="true"></span></a>
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