<!DOCTYPE html><html class="writer-html5" lang="en" data-content_root="./"><head>
  <meta charset="utf-8"><meta name="viewport" content="width=device-width, initial-scale=1">

  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Certora Prover Documentation — Certora Prover Documentation 0.0 documentation</title>
      <link rel="stylesheet" type="text/css" href="_static/pygments.css?v=80d5e7a1">
      <link rel="stylesheet" type="text/css" href="_static/css/theme.css?v=19f00094">
      <link rel="stylesheet" type="text/css" href="_static/copybutton.css?v=76b2166b">
      <link rel="stylesheet" type="text/css" href="_static/custom.css?v=098d337b">
      <link rel="stylesheet" type="text/css" href="_static/sphinx-design.min.css?v=87e54e7c">

  
  <!--[if lt IE 9]>
    <script src="_static/js/html5shiv.min.js"></script>
  <![endif]-->
  
        <script src="_static/jquery.js?v=5d32c60e"></script>
        <script src="_static/_sphinx_javascript_frameworks_compat.js?v=2cd50e6c"></script>
        <script src="_static/documentation_options.js?v=837179f8"></script>
        <script src="_static/doctools.js?v=9a2dae69"></script>
        <script src="_static/sphinx_highlight.js?v=dc90522c"></script>
        <script src="_static/clipboard.min.js?v=a7894cd8"></script>
        <script src="_static/copybutton.js?v=f281be69"></script>
        <script src="_static/design-tabs.js?v=f930bc37"></script>
        <script async="async" src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>
    <script src="_static/js/theme.js"></script>
    <link rel="index" title="Index" href="genindex.html">
    <link rel="search" title="Search" href="search.html">
    <link rel="next" title="Certora User’s Guide" href="docs/user-guide/index.html"> 
<style type="text/css">.CtxtMenu_InfoClose {  top:.2em; right:.2em;}
.CtxtMenu_InfoContent {  overflow:auto; text-align:left; font-size:80%;  padding:.4em .6em; border:1px inset; margin:1em 0px;  max-height:20em; max-width:30em; background-color:#EEEEEE;  white-space:normal;}
.CtxtMenu_Info.CtxtMenu_MousePost {outline:none;}
.CtxtMenu_Info {  position:fixed; left:50%; width:auto; text-align:center;  border:3px outset; padding:1em 2em; background-color:#DDDDDD;  color:black;  cursor:default; font-family:message-box; font-size:120%;  font-style:normal; text-indent:0; text-transform:none;  line-height:normal; letter-spacing:normal; word-spacing:normal;  word-wrap:normal; white-space:nowrap; float:none; z-index:201;  border-radius: 15px;                     /* Opera 10.5 and IE9 */  -webkit-border-radius:15px;               /* Safari and Chrome */  -moz-border-radius:15px;                  /* Firefox */  -khtml-border-radius:15px;                /* Konqueror */  box-shadow:0px 10px 20px #808080;         /* Opera 10.5 and IE9 */  -webkit-box-shadow:0px 10px 20px #808080; /* Safari 3 & Chrome */  -moz-box-shadow:0px 10px 20px #808080;    /* Forefox 3.5 */  -khtml-box-shadow:0px 10px 20px #808080;  /* Konqueror */  filter:progid:DXImageTransform.Microsoft.dropshadow(OffX=2, OffY=2, Color="gray", Positive="true"); /* IE */}
</style><style type="text/css">.CtxtMenu_MenuClose {  position:absolute;  cursor:pointer;  display:inline-block;  border:2px solid #AAA;  border-radius:18px;  -webkit-border-radius: 18px;             /* Safari and Chrome */  -moz-border-radius: 18px;                /* Firefox */  -khtml-border-radius: 18px;              /* Konqueror */  font-family: "Courier New", Courier;  font-size:24px;  color:#F0F0F0}
.CtxtMenu_MenuClose span {  display:block; background-color:#AAA; border:1.5px solid;  border-radius:18px;  -webkit-border-radius: 18px;             /* Safari and Chrome */  -moz-border-radius: 18px;                /* Firefox */  -khtml-border-radius: 18px;              /* Konqueror */  line-height:0;  padding:8px 0 6px     /* may need to be browser-specific */}
.CtxtMenu_MenuClose:hover {  color:white!important;  border:2px solid #CCC!important}
.CtxtMenu_MenuClose:hover span {  background-color:#CCC!important}
.CtxtMenu_MenuClose:hover:focus {  outline:none}
</style><style type="text/css">.CtxtMenu_Menu {  position:absolute;  background-color:white;  color:black;  width:auto; padding:5px 0px;  border:1px solid #CCCCCC; margin:0; cursor:default;  font: menu; text-align:left; text-indent:0; text-transform:none;  line-height:normal; letter-spacing:normal; word-spacing:normal;  word-wrap:normal; white-space:nowrap; float:none; z-index:201;  border-radius: 5px;                     /* Opera 10.5 and IE9 */  -webkit-border-radius: 5px;             /* Safari and Chrome */  -moz-border-radius: 5px;                /* Firefox */  -khtml-border-radius: 5px;              /* Konqueror */  box-shadow:0px 10px 20px #808080;         /* Opera 10.5 and IE9 */  -webkit-box-shadow:0px 10px 20px #808080; /* Safari 3 & Chrome */  -moz-box-shadow:0px 10px 20px #808080;    /* Forefox 3.5 */  -khtml-box-shadow:0px 10px 20px #808080;  /* Konqueror */}
.CtxtMenu_MenuItem {  padding: 1px 2em;  background:transparent;}
.CtxtMenu_MenuArrow {  position:absolute; right:.5em; padding-top:.25em; color:#666666;  font-family: null; font-size: .75em}
.CtxtMenu_MenuActive .CtxtMenu_MenuArrow {color:white}
.CtxtMenu_MenuArrow.CtxtMenu_RTL {left:.5em; right:auto}
.CtxtMenu_MenuCheck {  position:absolute; left:.7em;  font-family: null}
.CtxtMenu_MenuCheck.CtxtMenu_RTL { right:.7em; left:auto }
.CtxtMenu_MenuRadioCheck {  position:absolute; left: .7em;}
.CtxtMenu_MenuRadioCheck.CtxtMenu_RTL {  right: .7em; left:auto}
.CtxtMenu_MenuInputBox {  padding-left: 1em; right:.5em; color:#666666;  font-family: null;}
.CtxtMenu_MenuInputBox.CtxtMenu_RTL {  left: .1em;}
.CtxtMenu_MenuComboBox {  left:.1em; padding-bottom:.5em;}
.CtxtMenu_MenuSlider {  left: .1em;}
.CtxtMenu_SliderValue {  position:absolute; right:.1em; padding-top:.25em; color:#333333;  font-size: .75em}
.CtxtMenu_SliderBar {  outline: none; background: #d3d3d3}
.CtxtMenu_MenuLabel {  padding: 1px 2em 3px 1.33em;  font-style:italic}
.CtxtMenu_MenuRule {  border-top: 1px solid #DDDDDD;  margin: 4px 3px;}
.CtxtMenu_MenuDisabled {  color:GrayText}
.CtxtMenu_MenuActive {  background-color: #606872;  color: white;}
.CtxtMenu_MenuDisabled:focus {  background-color: #E8E8E8}
.CtxtMenu_MenuLabel:focus {  background-color: #E8E8E8}
.CtxtMenu_ContextMenu:focus {  outline:none}
.CtxtMenu_ContextMenu .CtxtMenu_MenuItem:focus {  outline:none}
.CtxtMenu_SelectionMenu {  position:relative; float:left;  border-bottom: none; -webkit-box-shadow:none; -webkit-border-radius:0px; }
.CtxtMenu_SelectionItem {  padding-right: 1em;}
.CtxtMenu_Selection {  right: 40%; width:50%; }
.CtxtMenu_SelectionBox {  padding: 0em; max-height:20em; max-width: none;  background-color:#FFFFFF;}
.CtxtMenu_SelectionDivider {  clear: both; border-top: 2px solid #000000;}
.CtxtMenu_Menu .CtxtMenu_MenuClose {  top:-10px; left:-10px}
</style><style id="MJX-CHTML-styles">
mjx-container[jax="CHTML"] {
  line-height: 0;
}

mjx-container [space="1"] {
  margin-left: .111em;
}

mjx-container [space="2"] {
  margin-left: .167em;
}

mjx-container [space="3"] {
  margin-left: .222em;
}

mjx-container [space="4"] {
  margin-left: .278em;
}

mjx-container [space="5"] {
  margin-left: .333em;
}

mjx-container [rspace="1"] {
  margin-right: .111em;
}

mjx-container [rspace="2"] {
  margin-right: .167em;
}

mjx-container [rspace="3"] {
  margin-right: .222em;
}

mjx-container [rspace="4"] {
  margin-right: .278em;
}

mjx-container [rspace="5"] {
  margin-right: .333em;
}

mjx-container [size="s"] {
  font-size: 70.7%;
}

mjx-container [size="ss"] {
  font-size: 50%;
}

mjx-container [size="Tn"] {
  font-size: 60%;
}

mjx-container [size="sm"] {
  font-size: 85%;
}

mjx-container [size="lg"] {
  font-size: 120%;
}

mjx-container [size="Lg"] {
  font-size: 144%;
}

mjx-container [size="LG"] {
  font-size: 173%;
}

mjx-container [size="hg"] {
  font-size: 207%;
}

mjx-container [size="HG"] {
  font-size: 249%;
}

mjx-container [width="full"] {
  width: 100%;
}

mjx-box {
  display: inline-block;
}

mjx-block {
  display: block;
}

mjx-itable {
  display: inline-table;
}

mjx-row {
  display: table-row;
}

mjx-row > * {
  display: table-cell;
}

mjx-mtext {
  display: inline-block;
}

mjx-mstyle {
  display: inline-block;
}

mjx-merror {
  display: inline-block;
  color: red;
  background-color: yellow;
}

mjx-mphantom {
  visibility: hidden;
}

_::-webkit-full-page-media, _:future, :root mjx-container {
  will-change: opacity;
}

mjx-assistive-mml {
  position: absolute !important;
  top: 0px;
  left: 0px;
  clip: rect(1px, 1px, 1px, 1px);
  padding: 1px 0px 0px 0px !important;
  border: 0px !important;
  display: block !important;
  width: auto !important;
  overflow: hidden !important;
  -webkit-touch-callout: none;
  -webkit-user-select: none;
  -khtml-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

mjx-assistive-mml[display="block"] {
  width: 100% !important;
}

mjx-c::before {
  display: block;
  width: 0;
}

.MJX-TEX {
  font-family: MJXZERO, MJXTEX;
}

.TEX-B {
  font-family: MJXZERO, MJXTEX-B;
}

.TEX-I {
  font-family: MJXZERO, MJXTEX-I;
}

.TEX-MI {
  font-family: MJXZERO, MJXTEX-MI;
}

.TEX-BI {
  font-family: MJXZERO, MJXTEX-BI;
}

.TEX-S1 {
  font-family: MJXZERO, MJXTEX-S1;
}

.TEX-S2 {
  font-family: MJXZERO, MJXTEX-S2;
}

.TEX-S3 {
  font-family: MJXZERO, MJXTEX-S3;
}

.TEX-S4 {
  font-family: MJXZERO, MJXTEX-S4;
}

.TEX-A {
  font-family: MJXZERO, MJXTEX-A;
}

.TEX-C {
  font-family: MJXZERO, MJXTEX-C;
}

.TEX-CB {
  font-family: MJXZERO, MJXTEX-CB;
}

.TEX-FR {
  font-family: MJXZERO, MJXTEX-FR;
}

.TEX-FRB {
  font-family: MJXZERO, MJXTEX-FRB;
}

.TEX-SS {
  font-family: MJXZERO, MJXTEX-SS;
}

.TEX-SSB {
  font-family: MJXZERO, MJXTEX-SSB;
}

.TEX-SSI {
  font-family: MJXZERO, MJXTEX-SSI;
}

.TEX-SC {
  font-family: MJXZERO, MJXTEX-SC;
}

.TEX-T {
  font-family: MJXZERO, MJXTEX-T;
}

.TEX-V {
  font-family: MJXZERO, MJXTEX-V;
}

.TEX-VB {
  font-family: MJXZERO, MJXTEX-VB;
}

mjx-stretchy-v mjx-c, mjx-stretchy-h mjx-c {
  font-family: MJXZERO, MJXTEX-S1, MJXTEX-S4, MJXTEX, MJXTEX-A ! important;
}

@font-face /* 0 */ {
  font-family: MJXZERO;
  src: url("https://cdn.jsdelivr.net/npm/mathjax@3/es5/output/chtml/fonts/woff-v2/MathJax_Zero.woff") format("woff");
}

@font-face /* 1 */ {
  font-family: MJXTEX;
  src: url("https://cdn.jsdelivr.net/npm/mathjax@3/es5/output/chtml/fonts/woff-v2/MathJax_Main-Regular.woff") format("woff");
}

@font-face /* 2 */ {
  font-family: MJXTEX-B;
  src: url("https://cdn.jsdelivr.net/npm/mathjax@3/es5/output/chtml/fonts/woff-v2/MathJax_Main-Bold.woff") format("woff");
}

@font-face /* 3 */ {
  font-family: MJXTEX-I;
  src: url("https://cdn.jsdelivr.net/npm/mathjax@3/es5/output/chtml/fonts/woff-v2/MathJax_Math-Italic.woff") format("woff");
}

@font-face /* 4 */ {
  font-family: MJXTEX-MI;
  src: url("https://cdn.jsdelivr.net/npm/mathjax@3/es5/output/chtml/fonts/woff-v2/MathJax_Main-Italic.woff") format("woff");
}

@font-face /* 5 */ {
  font-family: MJXTEX-BI;
  src: url("https://cdn.jsdelivr.net/npm/mathjax@3/es5/output/chtml/fonts/woff-v2/MathJax_Math-BoldItalic.woff") format("woff");
}

@font-face /* 6 */ {
  font-family: MJXTEX-S1;
  src: url("https://cdn.jsdelivr.net/npm/mathjax@3/es5/output/chtml/fonts/woff-v2/MathJax_Size1-Regular.woff") format("woff");
}

@font-face /* 7 */ {
  font-family: MJXTEX-S2;
  src: url("https://cdn.jsdelivr.net/npm/mathjax@3/es5/output/chtml/fonts/woff-v2/MathJax_Size2-Regular.woff") format("woff");
}

@font-face /* 8 */ {
  font-family: MJXTEX-S3;
  src: url("https://cdn.jsdelivr.net/npm/mathjax@3/es5/output/chtml/fonts/woff-v2/MathJax_Size3-Regular.woff") format("woff");
}

@font-face /* 9 */ {
  font-family: MJXTEX-S4;
  src: url("https://cdn.jsdelivr.net/npm/mathjax@3/es5/output/chtml/fonts/woff-v2/MathJax_Size4-Regular.woff") format("woff");
}

@font-face /* 10 */ {
  font-family: MJXTEX-A;
  src: url("https://cdn.jsdelivr.net/npm/mathjax@3/es5/output/chtml/fonts/woff-v2/MathJax_AMS-Regular.woff") format("woff");
}

@font-face /* 11 */ {
  font-family: MJXTEX-C;
  src: url("https://cdn.jsdelivr.net/npm/mathjax@3/es5/output/chtml/fonts/woff-v2/MathJax_Calligraphic-Regular.woff") format("woff");
}

@font-face /* 12 */ {
  font-family: MJXTEX-CB;
  src: url("https://cdn.jsdelivr.net/npm/mathjax@3/es5/output/chtml/fonts/woff-v2/MathJax_Calligraphic-Bold.woff") format("woff");
}

@font-face /* 13 */ {
  font-family: MJXTEX-FR;
  src: url("https://cdn.jsdelivr.net/npm/mathjax@3/es5/output/chtml/fonts/woff-v2/MathJax_Fraktur-Regular.woff") format("woff");
}

@font-face /* 14 */ {
  font-family: MJXTEX-FRB;
  src: url("https://cdn.jsdelivr.net/npm/mathjax@3/es5/output/chtml/fonts/woff-v2/MathJax_Fraktur-Bold.woff") format("woff");
}

@font-face /* 15 */ {
  font-family: MJXTEX-SS;
  src: url("https://cdn.jsdelivr.net/npm/mathjax@3/es5/output/chtml/fonts/woff-v2/MathJax_SansSerif-Regular.woff") format("woff");
}

@font-face /* 16 */ {
  font-family: MJXTEX-SSB;
  src: url("https://cdn.jsdelivr.net/npm/mathjax@3/es5/output/chtml/fonts/woff-v2/MathJax_SansSerif-Bold.woff") format("woff");
}

@font-face /* 17 */ {
  font-family: MJXTEX-SSI;
  src: url("https://cdn.jsdelivr.net/npm/mathjax@3/es5/output/chtml/fonts/woff-v2/MathJax_SansSerif-Italic.woff") format("woff");
}

@font-face /* 18 */ {
  font-family: MJXTEX-SC;
  src: url("https://cdn.jsdelivr.net/npm/mathjax@3/es5/output/chtml/fonts/woff-v2/MathJax_Script-Regular.woff") format("woff");
}

@font-face /* 19 */ {
  font-family: MJXTEX-T;
  src: url("https://cdn.jsdelivr.net/npm/mathjax@3/es5/output/chtml/fonts/woff-v2/MathJax_Typewriter-Regular.woff") format("woff");
}

@font-face /* 20 */ {
  font-family: MJXTEX-V;
  src: url("https://cdn.jsdelivr.net/npm/mathjax@3/es5/output/chtml/fonts/woff-v2/MathJax_Vector-Regular.woff") format("woff");
}

@font-face /* 21 */ {
  font-family: MJXTEX-VB;
  src: url("https://cdn.jsdelivr.net/npm/mathjax@3/es5/output/chtml/fonts/woff-v2/MathJax_Vector-Bold.woff") format("woff");
}
</style></head>

<body class="wy-body-for-nav"> 
  <div class="wy-grid-for-nav">
    <nav data-toggle="wy-nav-shift" class="wy-nav-side">
      <div class="wy-side-scroll">
        <div class="wy-side-nav-search">

          
          
          <a href="#" class="icon icon-home">
            Certora Prover Documentation
              <img src="_static/Certora_Logo_Black.svg" class="logo" alt="Logo">
          </a>
<div role="search">
  <form id="rtd-search-form" class="wy-form" action="search.html" method="get">
    <input type="text" name="q" placeholder="Search docs" aria-label="Search docs">
    <input type="hidden" name="check_keywords" value="yes">
    <input type="hidden" name="area" value="default">
  </form>
</div>
        </div><div class="wy-menu wy-menu-vertical" data-spy="affix" role="navigation" aria-label="Navigation menu">
              <p class="caption" role="heading"><span class="caption-text">Contents</span></p>
<ul>
<li class="toctree-l1"><a class="reference internal" href="docs/user-guide/index.html">Certora User’s Guide</a></li>
<li class="toctree-l1"><a class="reference internal" href="docs/cvl/index.html">The Certora Verification Language</a></li>
<li class="toctree-l1"><a class="reference internal" href="docs/prover/index.html">The Certora Prover</a></li>
<li class="toctree-l1"><a class="reference internal" href="docs/sunbeam/index.html">Sunbeam: Verification for Soroban</a></li>
<li class="toctree-l1"><a class="reference internal" href="docs/solana/index.html">The Certora Solana Prover</a></li>
<li class="toctree-l1"><a class="reference internal" href="docs/gambit/index.html">Gambit: Mutation Generator for Solidity</a></li>
</ul>
<p class="caption" role="heading"><span class="caption-text">Additional information</span></p>
<ul>
<li class="toctree-l1"><a class="reference internal" href="docs/equiv-check/index.html">The Certora Equivalence Checker</a></li>
<li class="toctree-l1"><a class="reference internal" href="docs/whitepaper/index.html">Certora Technology White Paper</a></li>
</ul>
<ul>
<li class="toctree-l1"><a class="reference internal" href="genindex.html">Index</a></li>
</ul>

        </div>
      </div>
    </nav>

    <section data-toggle="wy-nav-shift" class="wy-nav-content-wrap"><nav class="wy-nav-top" aria-label="Mobile navigation menu">
          <i data-toggle="wy-nav-top" class="fa fa-bars"></i>
          <a href="#">Certora Prover Documentation</a>
      </nav>

      <div class="wy-nav-content">
        <div class="rst-content">
          <div role="navigation" aria-label="Page navigation">
  <ul class="wy-breadcrumbs">
      <li><a href="#" class="icon icon-home" aria-label="Home"></a></li>
      <li class="breadcrumb-item active">Certora Prover Documentation</li>
      <li class="wy-breadcrumbs-aside">
            <a href="_sources/index.rst.txt" rel="nofollow"> View page source</a>
      </li>
  </ul>
  <hr>
</div>
          <div role="main" class="document" itemscope="itemscope" itemtype="http://schema.org/Article">
           <div itemprop="articleBody">
             
  <section id="certora-prover-documentation">
<h1>Certora Prover Documentation<a class="headerlink" href="#certora-prover-documentation" title="Link to this heading"></a></h1>
<section id="contents">
<h2>Contents<a class="headerlink" href="#contents" title="Link to this heading"></a></h2>
<ul class="simple">
<li><p><a class="reference internal" href="docs/user-guide/index.html"><span class="doc">Certora User’s Guide</span></a> – explains how to use the Prover to verify smart
contracts. Organized by topic and focuses on the most useful features.</p></li>
<li><p><a class="reference internal" href="docs/cvl/index.html"><span class="doc">The Certora Verification Language</span></a> – a reference manual for CVL.</p></li>
<li><p><a class="reference internal" href="docs/prover/index.html"><span class="doc">The Certora Prover</span></a> – a reference manual for the Certora Prover.</p></li>
<li><p><a class="reference internal" href="docs/sunbeam/index.html"><span class="doc">Sunbeam: Verification for Soroban</span></a> – instructions for installing and using <em>Certora Sunbeam</em>
for formal verification of <a class="reference external" href="https://stellar.org/soroban">Soroban</a> contracts.</p></li>
<li><p><a class="reference internal" href="docs/solana/index.html"><span class="doc">The Certora Solana Prover</span></a> – instructions for installing and using <em>Certora Solana Prover</em></p></li>
<li><p><a class="reference internal" href="docs/gambit/index.html"><span class="doc">Gambit: Mutation Generator for Solidity</span></a> – use mutation testing to improve you specifications.</p></li>
</ul>
<div class="toctree-wrapper compound">
</div>
</section>
<section id="learning-resources">
<h2>Learning resources<a class="headerlink" href="#learning-resources" title="Link to this heading"></a></h2>
<section id="certora-prover">
<h3>Certora Prover<a class="headerlink" href="#certora-prover" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p><a class="reference internal" href="docs/user-guide/index.html"><span class="doc">Certora User’s Guide</span></a> (in this Documentation).</p></li>
<li><p><a class="reference external" href="https://docs.certora.com/projects/tutorials">Certora Prover Tutorials</a> – learning to use the Prover and CVL through exercises.</p></li>
<li><p><a class="reference external" href="https://github.com/Certora/Examples/">Certora Prover and CVL Examples Repository</a> – learn CVL from examples.</p></li>
<li><p><a class="reference internal" href="docs/user-guide/tutorials.html"><span class="doc">Tutorial and Workshops</span></a> – lists workshops and tutorials that
cover basic Prover usage.</p></li>
</ul>
</section>
<section id="certora-sunbeam">
<h3>Certora Sunbeam<a class="headerlink" href="#certora-sunbeam" title="Link to this heading"></a></h3>
<ul class="simple">
<li><p><a class="reference external" href="https://certora-sunbeam-tutorials.readthedocs-hosted.com/en/latest/">Certora Sunbeam Tutorials</a> – a set of exercises using Soroban contracts in Rust.</p></li>
</ul>
<div class="toctree-wrapper compound">
<p class="caption" role="heading"><span class="caption-text">Additional information</span></p>
<ul>
<li class="toctree-l1"><a class="reference internal" href="docs/equiv-check/index.html">The Certora Equivalence Checker</a></li>
<li class="toctree-l1"><a class="reference internal" href="docs/whitepaper/index.html">Certora Technology White Paper</a></li>
</ul>
</div>
<div class="toctree-wrapper compound">
</div>
</section>
</section>
<section id="contacting-certora">
<span id="contact"></span><h2>Contacting Certora<a class="headerlink" href="#contacting-certora" title="Link to this heading"></a></h2>
<p>If you have questions about Certora’s products, the best ways to contact us is
on our <a class="reference external" href="https://discord.com/channels/795999272293236746/1104825071450718338">Help Desk channel on Discord</a>.</p>
<p>For sales, please use the <a class="reference external" href="https://www.certora.com/#Request_Early_Access">contact form on our website</a>.</p>
</section>
</section>


           </div>
          </div>
          <footer><div class="rst-footer-buttons" role="navigation" aria-label="Footer">
        <a href="docs/user-guide/index.html" class="btn btn-neutral float-right" title="Certora User’s Guide" accesskey="n" rel="next">Next <span class="fa fa-arrow-circle-right" aria-hidden="true"></span></a>
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