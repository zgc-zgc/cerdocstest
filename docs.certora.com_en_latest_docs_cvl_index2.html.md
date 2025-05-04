<!DOCTYPE html><html class="writer-html5" lang="en" data-content_root="../../"><head>
  <meta charset="utf-8"><meta name="viewport" content="width=device-width, initial-scale=1">

  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>The Certora Verification Language — Certora Prover Documentation 0.0 documentation</title>
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
        <script async="async" src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>
    <script src="../../_static/js/theme.js"></script>
    <link rel="index" title="Index" href="../../genindex.html">
    <link rel="search" title="Search" href="../../search.html">
    <link rel="next" title="Specification Files" href="overview.html">
    <link rel="prev" title="Glossary" href="../user-guide/glossary.html"> 
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
<li class="toctree-l1 current" aria-expanded="true"><a class="reference internal current" href="#" aria-expanded="true"><button class="toctree-expand" title="Open/close menu"></button>The Certora Verification Language</a><ul>
<li class="toctree-l2"><a class="reference internal" href="overview.html">Specification Files</a></li>
<li class="toctree-l2"><a class="reference internal" href="basics.html">Basic Syntax</a></li>
<li class="toctree-l2"><a class="reference internal" href="types.html">Types</a></li>
<li class="toctree-l2"><a class="reference internal" href="expr.html">Expressions</a></li>
<li class="toctree-l2"><a class="reference internal" href="statements.html">Statements</a></li>
<li class="toctree-l2"><a class="reference internal" href="imports.html">Import and Use Statements</a></li>
<li class="toctree-l2"><a class="reference internal" href="using.html">Using Statements</a></li>
<li class="toctree-l2"><a class="reference internal" href="methods.html">The Methods Block</a></li>
<li class="toctree-l2"><a class="reference internal" href="rules.html">Rules</a></li>
<li class="toctree-l2"><a class="reference internal" href="builtin.html">Built-in Rules</a></li>
<li class="toctree-l2"><a class="reference internal" href="functions.html">Functions</a></li>
<li class="toctree-l2"><a class="reference internal" href="invariants.html">Invariants</a></li>
<li class="toctree-l2"><a class="reference internal" href="sorts.html">Uninterpreted Sorts</a></li>
<li class="toctree-l2"><a class="reference internal" href="ghosts.html">Ghosts</a></li>
<li class="toctree-l2"><a class="reference internal" href="defs.html">Definitions</a></li>
<li class="toctree-l2"><a class="reference internal" href="hooks.html">Hooks</a></li>
<li class="toctree-l2"><a class="reference internal" href="transient.html">Transient Storage</a></li>
<li class="toctree-l2"><a class="reference internal" href="foundry-integration.html">Foundry Integration (Alpha)</a></li>
<li class="toctree-l2"><a class="reference internal" href="#changes-since-cvl-1"><button class="toctree-expand" title="Open/close menu"></button>Changes Since CVL 1</a><ul>
<li class="toctree-l3"><a class="reference internal" href="cvl2/changes.html">Changes Introduced in CVL 2</a></li>
<li class="toctree-l3"><a class="reference internal" href="cvl2/migration.html">CVL2 Migration Guide</a></li>
<li class="toctree-l3"><a class="reference internal" href="v5-changes.html">Certora CLI 5.0 Changes</a></li>
</ul>
</li>
</ul>
</li>
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
      <li class="breadcrumb-item active">The Certora Verification Language</li>
      <li class="wy-breadcrumbs-aside">
            <a href="../../_sources/docs/cvl/index.md.txt" rel="nofollow"> View page source</a>
      </li>
  </ul>
  <hr>
</div>
          <div role="main" class="document" itemscope="itemscope" itemtype="http://schema.org/Article">
           <div itemprop="articleBody">
             
  <section id="the-certora-verification-language">
<span id="cvl-language"></span><h1>The Certora Verification Language<a class="headerlink" href="#the-certora-verification-language" title="Link to this heading"></a></h1>
<p>The Certora Verification Language (often abbreviated CVL) is the language used
to write specifications for smart contracts.  This chapter describes the syntax
and semantics of CVL Specifications.</p>
<div class="toctree-wrapper compound">
<ul>
<li class="toctree-l1"><a class="reference internal" href="overview.html">Specification Files</a><ul>
<li class="toctree-l2"><a class="reference internal" href="overview.html#syntactic-conventions">Syntactic Conventions</a></li>
</ul>
</li>
<li class="toctree-l1"><a class="reference internal" href="basics.html">Basic Syntax</a><ul>
<li class="toctree-l2"><a class="reference internal" href="basics.html#comments">Comments</a></li>
<li class="toctree-l2"><a class="reference internal" href="basics.html#identifiers">Identifiers</a></li>
<li class="toctree-l2"><a class="reference internal" href="basics.html#literals">Literals</a></li>
</ul>
</li>
<li class="toctree-l1"><a class="reference internal" href="types.html">Types</a><ul>
<li class="toctree-l2"><a class="reference internal" href="types.html#syntax">Syntax</a></li>
<li class="toctree-l2"><a class="reference internal" href="types.html#solidity-types">Solidity Types</a></li>
<li class="toctree-l2"><a class="reference internal" href="types.html#additional-cvl-types">Additional CVL types</a></li>
<li class="toctree-l2"><a class="reference internal" href="types.html#conversions-between-cvl-and-solidity-types">Conversions between CVL and Solidity types</a></li>
</ul>
</li>
<li class="toctree-l1"><a class="reference internal" href="expr.html">Expressions</a><ul>
<li class="toctree-l2"><a class="reference internal" href="expr.html#syntax">Syntax</a></li>
<li class="toctree-l2"><a class="reference internal" href="expr.html#basic-operations">Basic operations</a></li>
<li class="toctree-l2"><a class="reference internal" href="expr.html#struct-comparison">Struct Comparison</a></li>
<li class="toctree-l2"><a class="reference internal" href="expr.html#extended-logical-operations">Extended logical operations</a></li>
<li class="toctree-l2"><a class="reference internal" href="expr.html#ghost-mapping-sums">Ghost Mapping Sums</a></li>
<li class="toctree-l2"><a class="reference internal" href="expr.html#accessing-fields-and-arrays">Accessing fields and arrays</a></li>
<li class="toctree-l2"><a class="reference internal" href="expr.html#contracts-method-signatures-and-their-properties">Contracts, method signatures and their properties</a></li>
<li class="toctree-l2"><a class="reference internal" href="expr.html#special-variables-and-fields">Special variables and fields</a></li>
<li class="toctree-l2"><a class="reference internal" href="expr.html#calling-contract-functions">Calling contract functions</a></li>
<li class="toctree-l2"><a class="reference internal" href="expr.html#comparing-storage">Comparing storage</a></li>
<li class="toctree-l2"><a class="reference internal" href="expr.html#direct-storage-access">Direct storage access</a></li>
<li class="toctree-l2"><a class="reference internal" href="expr.html#built-in-functions">Built-in Functions</a></li>
</ul>
</li>
<li class="toctree-l1"><a class="reference internal" href="statements.html">Statements</a><ul>
<li class="toctree-l2"><a class="reference internal" href="statements.html#syntax">Syntax</a></li>
<li class="toctree-l2"><a class="reference internal" href="statements.html#variable-declarations">Variable declarations</a></li>
<li class="toctree-l2"><a class="reference internal" href="statements.html#assert-and-require"><code class="docutils literal notranslate"><span class="pre">assert</span></code> and <code class="docutils literal notranslate"><span class="pre">require</span></code></a></li>
<li class="toctree-l2"><a class="reference internal" href="statements.html#satisfy-statements"><code class="docutils literal notranslate"><span class="pre">satisfy</span></code> statements</a></li>
<li class="toctree-l2"><a class="reference internal" href="statements.html#requireinvariant-statements"><code class="docutils literal notranslate"><span class="pre">requireInvariant</span></code> statements</a></li>
<li class="toctree-l2"><a class="reference internal" href="statements.html#havoc-statements">Havoc Statements</a></li>
<li class="toctree-l2"><a class="reference internal" href="statements.html#solidity-like-statements">Solidity-like Statements</a></li>
</ul>
</li>
<li class="toctree-l1"><a class="reference internal" href="imports.html">Import and Use Statements</a><ul>
<li class="toctree-l2"><a class="reference internal" href="imports.html#examples">Examples</a></li>
<li class="toctree-l2"><a class="reference internal" href="imports.html#syntax">Syntax</a></li>
</ul>
</li>
<li class="toctree-l1"><a class="reference internal" href="using.html">Using Statements</a><ul>
<li class="toctree-l2"><a class="reference internal" href="using.html#examples">Examples</a></li>
<li class="toctree-l2"><a class="reference internal" href="using.html#syntax">Syntax</a></li>
</ul>
</li>
<li class="toctree-l1"><a class="reference internal" href="methods.html">The Methods Block</a><ul>
<li class="toctree-l2"><a class="reference internal" href="methods.html#syntax">Syntax</a></li>
<li class="toctree-l2"><a class="reference internal" href="methods.html#methods-entry-patterns">Methods entry patterns</a></li>
<li class="toctree-l2"><a class="reference internal" href="methods.html#envfree-annotations"><code class="docutils literal notranslate"><span class="pre">envfree</span></code> annotations</a></li>
<li class="toctree-l2"><a class="reference internal" href="methods.html#optional-annotations"><code class="docutils literal notranslate"><span class="pre">optional</span></code> annotations</a></li>
<li class="toctree-l2"><a class="reference internal" href="methods.html#with-env-e-clauses"><code class="docutils literal notranslate"><span class="pre">with(env</span> <span class="pre">e)</span></code> clauses</a></li>
<li class="toctree-l2"><a class="reference internal" href="methods.html#summaries">Summaries</a></li>
</ul>
</li>
<li class="toctree-l1"><a class="reference internal" href="rules.html">Rules</a><ul>
<li class="toctree-l2"><a class="reference internal" href="rules.html#syntax">Syntax</a></li>
<li class="toctree-l2"><a class="reference internal" href="rules.html#overview">Overview</a></li>
<li class="toctree-l2"><a class="reference internal" href="rules.html#parametric-rules">Parametric rules</a></li>
<li class="toctree-l2"><a class="reference internal" href="rules.html#filters">Filters</a></li>
<li class="toctree-l2"><a class="reference internal" href="rules.html#multiple-assertions">Multiple assertions</a></li>
<li class="toctree-l2"><a class="reference internal" href="rules.html#rule-descriptions">Rule descriptions</a></li>
<li class="toctree-l2"><a class="reference internal" href="rules.html#how-rules-are-verified">How rules are verified</a></li>
</ul>
</li>
<li class="toctree-l1"><a class="reference internal" href="builtin.html">Built-in Rules</a><ul>
<li class="toctree-l2"><a class="reference internal" href="builtin.html#syntax">Syntax</a></li>
<li class="toctree-l2"><a class="reference internal" href="builtin.html#bad-loop-detection-msgvalueinlooprule">Bad loop detection — <code class="docutils literal notranslate"><span class="pre">msgValueInLoopRule</span></code></a></li>
<li class="toctree-l2"><a class="reference internal" href="builtin.html#delegate-call-detection-hasdelegatecalls">Delegate call detection — <code class="docutils literal notranslate"><span class="pre">hasDelegateCalls</span></code></a></li>
<li class="toctree-l2"><a class="reference internal" href="builtin.html#basic-setup-checks-sanity">Basic setup checks — <code class="docutils literal notranslate"><span class="pre">sanity</span></code></a></li>
<li class="toctree-l2"><a class="reference internal" href="builtin.html#thorough-complexity-checks-deepsanity">Thorough complexity checks — <code class="docutils literal notranslate"><span class="pre">deepSanity</span></code></a></li>
<li class="toctree-l2"><a class="reference internal" href="builtin.html#read-only-reentrancy-detection-viewreentrancy">Read-only reentrancy detection — <code class="docutils literal notranslate"><span class="pre">viewReentrancy</span></code></a></li>
</ul>
</li>
<li class="toctree-l1"><a class="reference internal" href="functions.html">Functions</a><ul>
<li class="toctree-l2"><a class="reference internal" href="functions.html#syntax">Syntax</a></li>
<li class="toctree-l2"><a class="reference internal" href="functions.html#examples">Examples</a></li>
<li class="toctree-l2"><a class="reference internal" href="functions.html#using-cvl-functions">Using CVL functions</a></li>
</ul>
</li>
<li class="toctree-l1"><a class="reference internal" href="invariants.html">Invariants</a><ul>
<li class="toctree-l2"><a class="reference internal" href="invariants.html#syntax">Syntax</a></li>
<li class="toctree-l2"><a class="reference internal" href="invariants.html#overview">Overview</a></li>
<li class="toctree-l2"><a class="reference internal" href="invariants.html#invariants-that-revert">Invariants that revert</a></li>
<li class="toctree-l2"><a class="reference internal" href="invariants.html#preserved-blocks">Preserved blocks</a></li>
<li class="toctree-l2"><a class="reference internal" href="invariants.html#filters">Filters</a></li>
<li class="toctree-l2"><a class="reference internal" href="invariants.html#induction-step-for-transient-storage">Induction Step for Transient Storage</a></li>
<li class="toctree-l2"><a class="reference internal" href="invariants.html#writing-an-invariant-as-a-rule">Writing an invariant as a rule</a></li>
<li class="toctree-l2"><a class="reference internal" href="invariants.html#invariants-and-induction">Invariants and induction</a></li>
</ul>
</li>
<li class="toctree-l1"><a class="reference internal" href="sorts.html">Uninterpreted Sorts</a><ul>
<li class="toctree-l2"><a class="reference internal" href="sorts.html#syntax-for-uninterpreted-sorts">Syntax for Uninterpreted Sorts</a></li>
<li class="toctree-l2"><a class="reference internal" href="sorts.html#example-usage">Example Usage</a></li>
<li class="toctree-l2"><a class="reference internal" href="sorts.html#using-uninterpreted-sorts-with-ghosts">Using Uninterpreted Sorts with Ghosts</a></li>
</ul>
</li>
<li class="toctree-l1"><a class="reference internal" href="ghosts.html">Ghosts</a><ul>
<li class="toctree-l2"><a class="reference internal" href="ghosts.html#syntax">Syntax</a></li>
<li class="toctree-l2"><a class="reference internal" href="ghosts.html#declaring-ghost-variables">Declaring ghost variables</a></li>
<li class="toctree-l2"><a class="reference internal" href="ghosts.html#ghost-functions">Ghost Functions</a></li>
<li class="toctree-l2"><a class="reference internal" href="ghosts.html#restrictions-on-ghost-definitions">Restrictions on ghost definitions</a></li>
<li class="toctree-l2"><a class="reference internal" href="ghosts.html#using-ghost-variables">Using ghost variables</a></li>
<li class="toctree-l2"><a class="reference internal" href="ghosts.html#ghost-axioms">Ghost axioms</a></li>
<li class="toctree-l2"><a class="reference internal" href="ghosts.html#restrictions-on-ghost-axioms">Restrictions on ghost axioms</a></li>
<li class="toctree-l2"><a class="reference internal" href="ghosts.html#ghosts-vs-persistent-ghosts">Ghosts vs. persistent ghosts</a></li>
</ul>
</li>
<li class="toctree-l1"><a class="reference internal" href="defs.html">Definitions</a><ul>
<li class="toctree-l2"><a class="reference internal" href="defs.html#basic-usage">Basic Usage</a></li>
<li class="toctree-l2"><a class="reference internal" href="defs.html#advanced-functionality">Advanced Functionality</a></li>
<li class="toctree-l2"><a class="reference internal" href="defs.html#filter-example">Filter Example</a></li>
<li class="toctree-l2"><a class="reference internal" href="defs.html#syntax">Syntax</a></li>
</ul>
</li>
<li class="toctree-l1"><a class="reference internal" href="hooks.html">Hooks</a><ul>
<li class="toctree-l2"><a class="reference internal" href="hooks.html#syntax">Syntax</a></li>
<li class="toctree-l2"><a class="reference internal" href="hooks.html#examples">Examples</a></li>
<li class="toctree-l2"><a class="reference internal" href="hooks.html#load-and-store-hooks">Load and store hooks</a></li>
<li class="toctree-l2"><a class="reference internal" href="hooks.html#evm-opcode-hooks">EVM opcode hooks</a></li>
<li class="toctree-l2"><a class="reference internal" href="hooks.html#hook-bodies">Hook bodies</a></li>
</ul>
</li>
<li class="toctree-l1"><a class="reference internal" href="transient.html">Transient Storage</a></li>
<li class="toctree-l1"><a class="reference internal" href="foundry-integration.html">Foundry Integration (Alpha)</a><ul>
<li class="toctree-l2"><a class="reference internal" href="foundry-integration.html#usage-automatic-setup">Usage (Automatic Setup)</a></li>
<li class="toctree-l2"><a class="reference internal" href="foundry-integration.html#usage-manual-setup">Usage (Manual Setup)</a></li>
<li class="toctree-l2"><a class="reference internal" href="foundry-integration.html#key-differences-vs-foundry-fuzz-testing">Key differences vs. Foundry fuzz testing</a></li>
<li class="toctree-l2"><a class="reference internal" href="foundry-integration.html#known-limitations">Known Limitations</a></li>
</ul>
</li>
</ul>
</div>
<section id="changes-since-cvl-1">
<h2>Changes Since CVL 1<a class="headerlink" href="#changes-since-cvl-1" title="Link to this heading"></a></h2>
<div class="toctree-wrapper compound">
<ul>
<li class="toctree-l1"><a class="reference internal" href="cvl2/changes.html">Changes Introduced in CVL 2</a><ul>
<li class="toctree-l2"><a class="reference internal" href="cvl2/changes.html#superficial-syntax-changes">Superficial syntax changes</a></li>
<li class="toctree-l2"><a class="reference internal" href="cvl2/changes.html#changes-to-methods-block-entries">Changes to methods block entries</a></li>
<li class="toctree-l2"><a class="reference internal" href="cvl2/changes.html#changes-to-integer-types">Changes to integer types</a></li>
<li class="toctree-l2"><a class="reference internal" href="cvl2/changes.html#changes-to-the-fallback-function">Changes to the fallback function</a></li>
<li class="toctree-l2"><a class="reference internal" href="cvl2/changes.html#removed-features">Removed features</a></li>
<li class="toctree-l2"><a class="reference internal" href="cvl2/changes.html#changes-to-the-command-line-interface-cli">Changes to the Command Line Interface (CLI)</a></li>
</ul>
</li>
<li class="toctree-l1"><a class="reference internal" href="cvl2/migration.html">CVL2 Migration Guide</a><ul>
<li class="toctree-l2"><a class="reference internal" href="cvl2/migration.html#step-0-install-cvl-2">Step 0: Install CVL 2</a></li>
<li class="toctree-l2"><a class="reference internal" href="cvl2/migration.html#step-1-skim-cvl-2-changes">Step 1: Skim CVL 2 changes</a></li>
<li class="toctree-l2"><a class="reference internal" href="cvl2/migration.html#step-2-run-the-migration-script">Step 2: Run the migration script</a></li>
<li class="toctree-l2"><a class="reference internal" href="cvl2/migration.html#step-3-fix-type-errors">Step 3: Fix type errors</a></li>
<li class="toctree-l2"><a class="reference internal" href="cvl2/migration.html#step-4-review-your-methods-blocks">Step 4: Review your <code class="docutils literal notranslate"><span class="pre">methods</span></code> blocks</a></li>
<li class="toctree-l2"><a class="reference internal" href="cvl2/migration.html#step-5-profit">Step 5: Profit!</a></li>
</ul>
</li>
<li class="toctree-l1"><a class="reference internal" href="v5-changes.html">Certora CLI 5.0 Changes</a><ul>
<li class="toctree-l2"><a class="reference internal" href="v5-changes.html#exhaustive-parametric-rules">Exhaustive parametric rules</a></li>
<li class="toctree-l2"><a class="reference internal" href="v5-changes.html#disallow-calls-to-contract-functions-in-quantified-expressions">Disallow calls to contract functions in quantified expressions</a></li>
<li class="toctree-l2"><a class="reference internal" href="v5-changes.html#method-variable-restrictions">Method variable restrictions</a></li>
<li class="toctree-l2"><a class="reference internal" href="v5-changes.html#new-delete-summary-syntax">New <code class="docutils literal notranslate"><span class="pre">DELETE</span></code> summary syntax</a></li>
<li class="toctree-l2"><a class="reference internal" href="v5-changes.html#cli-changes-new-parametric-contracts-attribute">CLI changes: New Parametric Contracts Attribute</a></li>
<li class="toctree-l2"><a class="reference internal" href="v5-changes.html#cli-changes-end-of-cvl1-deprecation-period">CLI changes: End of CVL1 Deprecation period</a></li>
</ul>
</li>
</ul>
</div>
</section>
</section>


           </div>
          </div>
          <footer><div class="rst-footer-buttons" role="navigation" aria-label="Footer">
        <a href="../user-guide/glossary.html" class="btn btn-neutral float-left" title="Glossary" accesskey="p" rel="prev"><span class="fa fa-arrow-circle-left" aria-hidden="true"></span> Previous</a>
        <a href="overview.html" class="btn btn-neutral float-right" title="Specification Files" accesskey="n" rel="next">Next <span class="fa fa-arrow-circle-right" aria-hidden="true"></span></a>
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