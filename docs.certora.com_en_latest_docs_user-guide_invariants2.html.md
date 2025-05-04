<!DOCTYPE html><html class="writer-html5" lang="en" data-content_root="../../"><head>
  <meta charset="utf-8"><meta name="viewport" content="width=device-width, initial-scale=1">

  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Invariants — Certora Prover Documentation 0.0 documentation</title>
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
    <link rel="next" title="Parametric rules" href="parametric.html">
    <link rel="prev" title="Producing Positive Examples" href="satisfy.html"> 
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

mjx-math {
  display: inline-block;
  text-align: left;
  line-height: 0;
  text-indent: 0;
  font-style: normal;
  font-weight: normal;
  font-size: 100%;
  font-size-adjust: none;
  letter-spacing: normal;
  border-collapse: collapse;
  word-wrap: normal;
  word-spacing: normal;
  white-space: nowrap;
  direction: ltr;
  padding: 1px 0;
}

mjx-container[jax="CHTML"][display="true"] {
  display: block;
  text-align: center;
  margin: 1em 0;
}

mjx-container[jax="CHTML"][display="true"][width="full"] {
  display: flex;
}

mjx-container[jax="CHTML"][display="true"] mjx-math {
  padding: 0;
}

mjx-container[jax="CHTML"][justify="left"] {
  text-align: left;
}

mjx-container[jax="CHTML"][justify="right"] {
  text-align: right;
}

mjx-mi {
  display: inline-block;
  text-align: left;
}

mjx-c {
  display: inline-block;
}

mjx-utext {
  display: inline-block;
  padding: .75em 0 .2em 0;
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

mjx-c.mjx-c1D465.TEX-I::before {
  padding: 0.442em 0.572em 0.011em 0;
  content: "x";
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
<li class="toctree-l1 current" aria-expanded="true"><a class="reference internal" href="index.html"><button class="toctree-expand" title="Open/close menu"></button>Certora User’s Guide</a><ul class="" aria-expanded="false">
<li class="toctree-l2"><a class="reference internal" href="install.html">Installation</a></li>
<li class="toctree-l2"><a class="reference internal" href="install_evm_compiler.html">Installing an EVM compiler and VS Code Extension</a></li>
<li class="toctree-l2"><a class="reference internal" href="tutorials.html">Tutorial and Workshops</a></li>
<li class="toctree-l2"><a class="reference internal" href="running.html">Running the Certora Prover</a></li>
<li class="toctree-l2"><a class="reference internal" href="properties/index.html">Designing Good Specifications</a></li>
<li class="toctree-l2"><a class="reference internal" href="satisfy.html">Producing Positive Examples</a></li>
<li class="toctree-l2 current" aria-expanded="true"><a class="reference internal current" href="#" aria-expanded="true"><button class="toctree-expand" title="Open/close menu"></button>Invariants</a><ul>
<li class="toctree-l3"><a class="reference internal" href="#teams-example">Teams example</a></li>
<li class="toctree-l3"><a class="reference internal" href="#simple-invariants"><button class="toctree-expand" title="Open/close menu"></button>Simple invariants</a><ul>
<li class="toctree-l4"><a class="reference internal" href="#no-team-for-address-zero">No team for address zero</a></li>
<li class="toctree-l4"><a class="reference internal" href="#the-leader-is-part-of-the-team">The leader is part of the team</a></li>
</ul>
</li>
<li class="toctree-l3"><a class="reference internal" href="#using-preserved-blocks-inside-invariants"><button class="toctree-expand" title="Open/close menu"></button>Using preserved blocks inside invariants</a><ul>
<li class="toctree-l4"><a class="reference internal" href="#a-team-not-created-has-no-players">A team not created has no players</a></li>
<li class="toctree-l4"><a class="reference internal" href="#a-team-has-at-most-three-players">A team has at most three players</a></li>
</ul>
</li>
</ul>
</li>
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
      <li class="breadcrumb-item active">Invariants</li>
      <li class="wy-breadcrumbs-aside">
            <a href="../../_sources/docs/user-guide/invariants.rst.txt" rel="nofollow"> View page source</a>
      </li>
  </ul>
  <hr>
</div>
          <div role="main" class="document" itemscope="itemscope" itemtype="http://schema.org/Article">
           <div itemprop="articleBody">
             
  <section id="invariants">
<span id="index-0"></span><h1>Invariants<a class="headerlink" href="#invariants" title="Link to this heading"></a></h1>
<p>An <a class="reference internal" href="glossary.html#term-invariant"><span class="xref std std-term">invariant</span></a> is a property of the contract’s storage state that should
hold between calls to the contract. For example, in some ERC20 contracts the balance
of <code class="code highlight solidity docutils literal highlight-solidity"><span class="kt">address</span><span class="p">(</span><span class="m m-Decimal">0</span><span class="p">)</span></code> is always zero.</p>
<p>Below, we provide examples of using invariants. You can read more about invariants
in <a class="reference internal" href="../cvl/invariants.html#invariants"><span class="std std-ref">Invariants (from The Certora Verification Language)</span></a>.</p>
<section id="teams-example">
<h2>Teams example<a class="headerlink" href="#teams-example" title="Link to this heading"></a></h2>
<p>The <a class="reference external" href="https://github.com/Certora/Examples/blob/7dfc379423202c90cf284eb42800b97cf5c95d83/CVLByExample/Teams/ITeams.sol">ITeams</a> interface, shown below,
is an interface for managing teams consisting of two players and a team leader.</p>
<details class="sd-sphinx-override sd-dropdown sd-card sd-mb-3">
<summary class="sd-summary-title sd-card-header">
<span class="sd-summary-text"><a class="reference external" href="https://github.com/Certora/Examples/blob/7dfc379423202c90cf284eb42800b97cf5c95d83/CVLByExample/Teams/ITeams.sol">ITeams interface</a></span><span class="sd-summary-state-marker sd-summary-chevron-right"><svg version="1.1" width="1.5em" height="1.5em" class="sd-octicon sd-octicon-chevron-right" viewBox="0 0 24 24" aria-hidden="true"><path d="M8.72 18.78a.75.75 0 0 1 0-1.06L14.44 12 8.72 6.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018l6.25 6.25a.75.75 0 0 1 0 1.06l-6.25 6.25a.75.75 0 0 1-1.06 0Z"></path></svg></span></summary><div class="sd-summary-content sd-card-body docutils">
<div class="highlight-solidity notranslate"><div class="highlight"><pre id="codecell0"><span></span>interface<span class="w"> </span>ITeams<span class="w"> </span><span class="p">{</span>

<span class="w">    </span><span class="c1">/// @return The team id of the player</span>
<span class="w">    </span><span class="c1">/// @notice Return value of 0 means the player has not been assigned to a team</span>
<span class="w">    </span><span class="kt">function</span><span class="w"> </span><span class="nv">teamOf</span><span class="p">(</span><span class="kt">address</span><span class="w"> </span><span class="nv">player</span><span class="p">)</span><span class="w"> </span><span class="kt">external</span><span class="w"> </span>view<span class="w"> </span><span class="kt">returns</span><span class="w"> </span><span class="p">(</span><span class="kt">uint8</span><span class="p">);</span>

<span class="w">    </span><span class="c1">/// @return The team leader</span>
<span class="w">    </span><span class="c1">/// @notice Return value of zero means the team has not been created</span>
<span class="w">    </span><span class="kt">function</span><span class="w"> </span><span class="nv">leaderOf</span><span class="p">(</span><span class="kt">uint8</span><span class="w"> </span><span class="nv">teamId</span><span class="p">)</span><span class="w"> </span><span class="kt">external</span><span class="w"> </span>view<span class="w"> </span><span class="kt">returns</span><span class="w"> </span><span class="p">(</span><span class="kt">address</span><span class="p">);</span>

<span class="w">    </span><span class="c1">/// @dev Players must not be assigned to any team</span>
<span class="w">    </span><span class="c1">/// @dev The team must not exist before the call</span>
<span class="w">    </span><span class="kt">function</span><span class="w"> </span><span class="nv">createTeam</span><span class="p">(</span>
<span class="w">        </span><span class="kt">address</span><span class="w"> </span><span class="nv">leader</span><span class="p">,</span>
<span class="w">        </span><span class="kt">address</span><span class="w"> </span><span class="nv">playerA</span><span class="p">,</span>
<span class="w">        </span><span class="kt">address</span><span class="w"> </span><span class="nv">playerB</span><span class="p">,</span>
<span class="w">        </span><span class="kt">uint8</span><span class="w"> </span><span class="nv">teamId</span>
<span class="w">    </span><span class="p">)</span><span class="w"> </span><span class="kt">external</span><span class="p">;</span>

<span class="w">    </span><span class="c1">/// @notice Change the team's leader</span>
<span class="w">    </span><span class="c1">/// @dev Only the current leader may call this function</span>
<span class="w">    </span><span class="c1">/// @dev The new leader must be a member of the tem</span>
<span class="w">    </span><span class="kt">function</span><span class="w"> </span><span class="nv">changeLeader</span><span class="p">(</span><span class="kt">address</span><span class="w"> </span><span class="nv">newLeader</span><span class="p">)</span><span class="w"> </span><span class="kt">external</span><span class="p">;</span>
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
</div>
</details><p>A contract implementing this interface should satisfy the following properties:</p>
<ol class="arabic simple">
<li><p>Each team has three <em>different</em> players, one of which is the team leader.</p></li>
<li><p>Each player can belong only to one team.</p></li>
<li><p>A team is identified by a unique id between 1 and 255.</p></li>
<li><p>A player having team-id 0 indicates this player has no assigned team.</p></li>
<li><p>Address zero cannot be part of a team.</p></li>
<li><p>If a team has not been created yet, it will have <code class="code highlight solidity docutils literal highlight-solidity"><span class="kt">address</span><span class="p">(</span><span class="m m-Decimal">0</span><span class="p">)</span></code> as a team
leader.</p></li>
</ol>
<p>Next we translate these properties to CVL invariants. You can find the entire
spec in <a class="reference external" href="https://github.com/Certora/Examples/blob/7dfc379423202c90cf284eb42800b97cf5c95d83/CVLByExample/Teams/Teams.spec">The team of zero is zero</a>.</p>
<ul class="simple">
<li><p>To run the spec on a correct implementation of <code class="code highlight solidity docutils literal highlight-solidity">ITeams</code> use
<a class="reference external" href="https://github.com/Certora/Examples/blob/7dfc379423202c90cf284eb42800b97cf5c95d83/CVLByExample/Teams/correct.conf">correct.conf</a>, which will use the
implementation in <a class="reference external" href="https://github.com/Certora/Examples/blob/7dfc379423202c90cf284eb42800b97cf5c95d83/CVLByExample/Teams/Teams.sol">Teams.sol</a>.</p></li>
<li><p>To see the spec discover bugs, use
<a class="reference external" href="https://github.com/Certora/Examples/blob/7dfc379423202c90cf284eb42800b97cf5c95d83/CVLByExample/Teams/buggy.conf">buggy.conf</a>. This will run the spec
against the buggy implementation in
<a class="reference external" href="https://github.com/Certora/Examples/blob/7dfc379423202c90cf284eb42800b97cf5c95d83/CVLByExample/Teams/TeamsBugs.sol">TeamsBugs.sol</a>.</p></li>
</ul>
</section>
<section id="simple-invariants">
<h2>Simple invariants<a class="headerlink" href="#simple-invariants" title="Link to this heading"></a></h2>
<section id="no-team-for-address-zero">
<span id="id1"></span><h3>No team for address zero<a class="headerlink" href="#no-team-for-address-zero" title="Link to this heading"></a></h3>
<p>We can readily deduce from the properties that <code class="code highlight solidity docutils literal highlight-solidity">teamOf<span class="p">(</span><span class="kt">address</span><span class="p">(</span><span class="m m-Decimal">0</span><span class="p">))</span></code> must be
zero. Here it is written as an invariant:</p>
<div class="literal-block-wrapper docutils container" id="id2">
<div class="code-block-caption"><span class="caption-text"><a class="reference external" href="https://github.com/Certora/Examples/blob/7dfc379423202c90cf284eb42800b97cf5c95d83/CVLByExample/Teams/Teams.spec">The team of zero is zero</a></span><a class="headerlink" href="#id2" title="Link to this code"></a></div>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell1"><span></span><span class="kr">methods</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kd">function</span><span class="w"> </span><span class="nf">teamOf</span><span class="p">(</span><span class="kt">address</span><span class="p">)</span><span class="w"> </span><span class="kr">external</span><span class="w"> </span><span class="kr">returns</span><span class="w"> </span><span class="p">(</span><span class="kt">uint8</span><span class="p">)</span><span class="w"> </span><span class="kr">envfree</span><span class="p">;</span>
<span class="w">    </span><span class="kd">function</span><span class="w"> </span><span class="nf">leaderOf</span><span class="p">(</span><span class="kt">uint8</span><span class="p">)</span><span class="w"> </span><span class="kr">external</span><span class="w"> </span><span class="kr">returns</span><span class="w"> </span><span class="p">(</span><span class="kt">address</span><span class="p">)</span><span class="w"> </span><span class="kr">envfree</span><span class="p">;</span>
<span class="p">}</span>

<span class="c1">/// @title Address zero is not in any team</span>
<span class="k">invariant</span><span class="w"> </span><span class="nc">addressZeroNotPlayer</span><span class="p">()</span>
<span class="w">    </span>teamOf<span class="p">(</span><span class="m m-Decimal">0</span><span class="p">)</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">;</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell1">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</div>
<p>We declared the functions <code class="code highlight solidity docutils literal highlight-solidity">teamOf</code> and <code class="code highlight solidity docutils literal highlight-solidity">leaderOf</code> as <code class="code highlight cvl docutils literal highlight-cvl"><span class="kr">envfree</span></code>
to remove the need for an <code class="code highlight cvl docutils literal highlight-cvl"><span class="kt">env</span></code> type argument.</p>
</section>
<section id="the-leader-is-part-of-the-team">
<h3>The leader is part of the team<a class="headerlink" href="#the-leader-is-part-of-the-team" title="Link to this heading"></a></h3>
<p>Another invariant property is that the team-id of the leader of team <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="0" style="font-size: 116.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>x</mi></math></mjx-assistive-mml></mjx-container></span> is
<span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="1" style="font-size: 116.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>x</mi></math></mjx-assistive-mml></mjx-container></span>. This only holds if <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="2" style="font-size: 116.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>x</mi></math></mjx-assistive-mml></mjx-container></span> is not zero and the leader is not
<code class="code highlight solidity docutils literal highlight-solidity"><span class="kt">address</span><span class="p">(</span><span class="m m-Decimal">0</span><span class="p">)</span></code>. Here is the property written as an invariant:</p>
<div class="literal-block-wrapper docutils container" id="id3">
<div class="code-block-caption"><span class="caption-text"><a class="reference external" href="https://github.com/Certora/Examples/blob/7dfc379423202c90cf284eb42800b97cf5c95d83/CVLByExample/Teams/Teams.spec">The team’s leader is part of the team</a></span><a class="headerlink" href="#id3" title="Link to this code"></a></div>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell2"><span></span><span class="c1">/// @title The team's leader is part of the team</span>
<span class="k">invariant</span><span class="w"> </span><span class="nc">leaderBelongsToTeam</span><span class="p">(</span><span class="kt">uint8</span><span class="w"> </span>teamId<span class="p">)</span>
<span class="w">    </span><span class="p">(</span>teamId<span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span>leaderOf<span class="p">(</span>teamId<span class="p">)</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">)</span><span class="w"> </span><span class="o">=&gt;</span><span class="w"> </span>teamOf<span class="p">(</span>leaderOf<span class="p">(</span>teamId<span class="p">))</span><span class="w"> </span><span class="o">==</span><span class="w"> </span>teamId<span class="p">;</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell2">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</div>
</section>
</section>
<section id="using-preserved-blocks-inside-invariants">
<span id="index-1"></span><h2>Using preserved blocks inside invariants<a class="headerlink" href="#using-preserved-blocks-inside-invariants" title="Link to this heading"></a></h2>
<p>Sometimes additional conditions are needed to prove invariants. These additional
conditions are given using preserved blocks, see <a class="reference internal" href="../cvl/invariants.html#preserved"><span class="std std-ref">Preserved blocks</span></a>. Here are two
examples using preserved blocks.</p>
<section id="a-team-not-created-has-no-players">
<h3>A team not created has no players<a class="headerlink" href="#a-team-not-created-has-no-players" title="Link to this heading"></a></h3>
<p>Before team <code class="code highlight solidity docutils literal highlight-solidity">i</code> is created, <code class="code highlight solidity docutils literal highlight-solidity">leaderOf<span class="p">(</span>i<span class="p">)</span></code> must be
<code class="code highlight solidity docutils literal highlight-solidity"><span class="kt">address</span><span class="p">(</span><span class="m m-Decimal">0</span><span class="p">)</span></code>. In such a case, there should be no players in team <code class="code highlight solidity docutils literal highlight-solidity">i</code>.
We can write this condition as:</p>
<div class="literal-block-wrapper docutils container" id="id4">
<div class="code-block-caption"><span class="caption-text"><a class="reference external" href="https://github.com/Certora/Examples/blob/7dfc379423202c90cf284eb42800b97cf5c95d83/CVLByExample/Teams/NoPreserved.spec">nonExistTeamHasNoPlayers without preserved block</a></span><a class="headerlink" href="#id4" title="Link to this code"></a></div>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell3"><span></span><span class="cm">/** @title If a team does not exist it has not players</span>
<span class="cm"> *  This invariant cannot be proven without a preserved block.</span>
<span class="cm"> */</span>
<span class="k">invariant</span><span class="w"> </span><span class="nc">nonExistTeamHasNoPlayers</span><span class="p">(</span><span class="kt">uint8</span><span class="w"> </span>teamId<span class="p">,</span><span class="w"> </span><span class="kt">address</span><span class="w"> </span>player<span class="p">)</span>
<span class="w">    </span><span class="p">(</span>teamId<span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span>leaderOf<span class="p">(</span>teamId<span class="p">)</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">)</span><span class="w"> </span><span class="o">=&gt;</span><span class="w"> </span>teamOf<span class="p">(</span>player<span class="p">)</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span>teamId<span class="p">;</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell3">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</div>
<p>Running this rule, the Prover will find the following violation,
which you can see in this rule report <a class="reference external" href="https://prover.certora.com/output/98279/65d0cd795ba640d6bdd7877074fca175?anonymousKey=55ad7f5a7130e367993082addf32fc7898494db3">nonExistTeamHasNoPlayers violation report</a>.
The function called is <code class="code highlight solidity docutils literal highlight-solidity">changeLeader<span class="p">(</span><span class="kt">address</span><span class="p">(</span><span class="m m-Decimal">0</span><span class="p">))</span></code>, changing the leader
from address <code class="code highlight solidity docutils literal highlight-solidity">a</code> (where <code class="code highlight solidity docutils literal highlight-solidity">a</code> is not zero) to zero.
Before the call <code class="code highlight solidity docutils literal highlight-solidity"><span class="kt">address</span><span class="p">(</span><span class="m m-Decimal">0</span><span class="p">)</span></code> is a member of team <code class="code highlight solidity docutils literal highlight-solidity">i</code>, where
<code class="code highlight solidity docutils literal highlight-solidity">i<span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="m m-Decimal">0</span></code>. After the call the left hand side of the invariant condition
holds true: <code class="code highlight cvl docutils literal highlight-cvl">i<span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span>leaderOf<span class="p">(</span>i<span class="p">)</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="m m-Decimal">0</span></code>. But the right hand side
is false for <code class="code highlight cvl docutils literal highlight-cvl">player<span class="w"> </span><span class="o">=</span><span class="w"> </span>a</code>, since <code class="code highlight cvl docutils literal highlight-cvl">teamOf<span class="p">(</span>a<span class="p">)</span><span class="w"> </span><span class="o">=</span><span class="w"> </span>i</code>. The violation is expressed
in the following table, showing the change in state.</p>
<div class="wy-table-responsive"><table class="docutils align-default">
<thead>
<tr class="row-odd"><th class="head stub"></th>
<th class="head"><p>Pre call state</p></th>
<th class="head"><p>Post call state</p></th>
</tr>
</thead>
<tbody>
<tr class="row-even"><th class="stub"><p><code class="code highlight solidity docutils literal highlight-solidity">leaderOf<span class="p">(</span>i<span class="p">)</span></code></p></th>
<td><p><code class="code highlight solidity docutils literal highlight-solidity">a</code></p></td>
<td><p><code class="code highlight solidity docutils literal highlight-solidity"><span class="m m-Decimal">0</span></code></p></td>
</tr>
<tr class="row-odd"><th class="stub"><p><code class="code highlight solidity docutils literal highlight-solidity">teamOf<span class="p">(</span>a<span class="p">)</span></code></p></th>
<td><p><code class="code highlight solidity docutils literal highlight-solidity">i</code></p></td>
<td><p><code class="code highlight solidity docutils literal highlight-solidity">i</code></p></td>
</tr>
<tr class="row-even"><th class="stub"><p><code class="code highlight solidity docutils literal highlight-solidity">teamOf<span class="p">(</span><span class="m m-Decimal">0</span><span class="p">)</span></code></p></th>
<td><p><code class="code highlight solidity docutils literal highlight-solidity">i</code></p></td>
<td><p><code class="code highlight solidity docutils literal highlight-solidity">i</code></p></td>
</tr>
</tbody>
</table></div>
<p>In order for the invariant to be proved, we need to require that the team of
<code class="code highlight solidity docutils literal highlight-solidity"><span class="kt">address</span><span class="p">(</span><span class="m m-Decimal">0</span><span class="p">)</span></code> is zero. We’ll do that using a preserved block. Since
we already proved this in <a class="reference internal" href="#no-team-for-address-zero"><span class="std std-ref">No team for address zero</span></a>, we can simply
<span class="target" id="index-2"></span>require that the invariant
<code class="code highlight cvl docutils literal highlight-cvl">addressZeroNotPlayer</code> holds, like so:</p>
<div class="literal-block-wrapper docutils container" id="id5">
<div class="code-block-caption"><span class="caption-text"><a class="reference external" href="https://github.com/Certora/Examples/blob/7dfc379423202c90cf284eb42800b97cf5c95d83/CVLByExample/Teams/Teams.spec">Non created team has no players</a></span><a class="headerlink" href="#id5" title="Link to this code"></a></div>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell4"><span></span><span class="c1">/// @title If a team does not exist it has not players</span>
<span class="k">invariant</span><span class="w"> </span><span class="nc">nonExistTeamHasNoPlayers</span><span class="p">(</span><span class="kt">uint8</span><span class="w"> </span>teamId<span class="p">,</span><span class="w"> </span><span class="kt">address</span><span class="w"> </span>player<span class="p">)</span>
<span class="w">    </span><span class="p">(</span>teamId<span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span>leaderOf<span class="p">(</span>teamId<span class="p">)</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">)</span><span class="w"> </span><span class="o">=&gt;</span><span class="w"> </span>teamOf<span class="p">(</span>player<span class="p">)</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span>teamId
<span class="w">    </span><span class="p">{</span>
<span class="w">        </span><span class="kr">preserved</span><span class="w"> </span><span class="p">{</span>
<span class="w">            </span><span class="kr">requireInvariant</span><span class="w"> </span>addressZeroNotPlayer<span class="p">();</span>
<span class="w">        </span><span class="p">}</span>
<span class="w">    </span><span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell4">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</div>
<div class="admonition seealso">
<p class="admonition-title">See also</p>
<p>To read more on <code class="code highlight cvl docutils literal highlight-cvl"><span class="kr">requireInvariant</span></code> and its soundness, see
<a class="reference internal" href="../cvl/invariants.html#invariant-induction"><span class="std std-ref">Invariants and induction</span></a>.</p>
</div>
</section>
<section id="a-team-has-at-most-three-players">
<h3>A team has at most three players<a class="headerlink" href="#a-team-has-at-most-three-players" title="Link to this heading"></a></h3>
<p>Here is how we phrase this property:</p>
<blockquote>
<div><p>Let <code class="code highlight cvl docutils literal highlight-cvl">a</code>, <code class="code highlight cvl docutils literal highlight-cvl">b</code>, <code class="code highlight cvl docutils literal highlight-cvl">c</code> and <code class="code highlight cvl docutils literal highlight-cvl">d</code> be four different addresses, and suppose
that <code class="code highlight cvl docutils literal highlight-cvl">a</code>, <code class="code highlight cvl docutils literal highlight-cvl">b</code> and <code class="code highlight cvl docutils literal highlight-cvl">c</code> are all on the same non-zero team <code class="code highlight cvl docutils literal highlight-cvl">i</code>.
Then <code class="code highlight cvl docutils literal highlight-cvl">d</code> does not belong to team <code class="code highlight cvl docutils literal highlight-cvl">i</code>.</p>
</div></blockquote>
<section id="helper-functions">
<h4>Helper functions<a class="headerlink" href="#helper-functions" title="Link to this heading"></a></h4>
<p>To enhance readability we’ll define two helper functions:</p>
<ol class="arabic simple">
<li><p>A function checking that four addresses are different,
called <code class="code highlight cvl docutils literal highlight-cvl">fourDifferentAddresses</code>.</p></li>
<li><p>A function checking that three addresses are on the same team, called <code class="code highlight cvl docutils literal highlight-cvl">sameTeam</code>.</p></li>
</ol>
<p>Their definitions are given below.</p>
<details class="sd-sphinx-override sd-dropdown sd-card sd-mb-3">
<summary class="sd-summary-title sd-card-header">
<span class="sd-summary-text"><a class="reference external" href="https://github.com/Certora/Examples/blob/7dfc379423202c90cf284eb42800b97cf5c95d83/CVLByExample/Teams/Teams.spec">fourDifferentAddresses</a></span><span class="sd-summary-state-marker sd-summary-chevron-right"><svg version="1.1" width="1.5em" height="1.5em" class="sd-octicon sd-octicon-chevron-right" viewBox="0 0 24 24" aria-hidden="true"><path d="M8.72 18.78a.75.75 0 0 1 0-1.06L14.44 12 8.72 6.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018l6.25 6.25a.75.75 0 0 1 0 1.06l-6.25 6.25a.75.75 0 0 1-1.06 0Z"></path></svg></span></summary><div class="sd-summary-content sd-card-body docutils">
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell5"><span></span><span class="c1">/// @return If the four addresses are all different from each other</span>
<span class="kt">function</span><span class="w"> </span><span class="nf">fourDifferentAddresses</span><span class="p">(</span>
<span class="w">    </span><span class="kt">address</span><span class="w"> </span>a<span class="p">,</span>
<span class="w">    </span><span class="kt">address</span><span class="w"> </span>b<span class="p">,</span>
<span class="w">    </span><span class="kt">address</span><span class="w"> </span>c<span class="p">,</span>
<span class="w">    </span><span class="kt">address</span><span class="w"> </span>d
<span class="p">)</span><span class="w"> </span><span class="kr">returns</span><span class="w"> </span><span class="kt">bool</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kr">return</span><span class="w"> </span><span class="p">(</span>
<span class="w">        </span>a<span class="w"> </span><span class="o">!=</span><span class="w"> </span>b<span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span>a<span class="w"> </span><span class="o">!=</span><span class="w"> </span>c<span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span>a<span class="w"> </span><span class="o">!=</span><span class="w"> </span>d<span class="w"> </span><span class="o">&amp;&amp;</span>
<span class="w">        </span>b<span class="w"> </span><span class="o">!=</span><span class="w"> </span>c<span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span>b<span class="w"> </span><span class="o">!=</span><span class="w"> </span>d<span class="w"> </span><span class="o">&amp;&amp;</span>
<span class="w">        </span>c<span class="w"> </span><span class="o">!=</span><span class="w"> </span>d
<span class="w">    </span><span class="p">);</span>
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
</div>
</details><details class="sd-sphinx-override sd-dropdown sd-card sd-mb-3">
<summary class="sd-summary-title sd-card-header">
<span class="sd-summary-text"><a class="reference external" href="https://github.com/Certora/Examples/blob/7dfc379423202c90cf284eb42800b97cf5c95d83/CVLByExample/Teams/Teams.spec">sameTeam</a></span><span class="sd-summary-state-marker sd-summary-chevron-right"><svg version="1.1" width="1.5em" height="1.5em" class="sd-octicon sd-octicon-chevron-right" viewBox="0 0 24 24" aria-hidden="true"><path d="M8.72 18.78a.75.75 0 0 1 0-1.06L14.44 12 8.72 6.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018l6.25 6.25a.75.75 0 0 1 0 1.06l-6.25 6.25a.75.75 0 0 1-1.06 0Z"></path></svg></span></summary><div class="sd-summary-content sd-card-body docutils">
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell6"><span></span><span class="c1">/// @return If all players are on the same team</span>
<span class="kt">function</span><span class="w"> </span><span class="nf">sameTeam</span><span class="p">(</span><span class="kt">address</span><span class="w"> </span>a<span class="p">,</span><span class="w"> </span><span class="kt">address</span><span class="w"> </span>b<span class="p">,</span><span class="w"> </span><span class="kt">address</span><span class="w"> </span>c<span class="p">)</span><span class="w"> </span><span class="kr">returns</span><span class="w"> </span><span class="kt">bool</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kr">return</span><span class="w"> </span>teamOf<span class="p">(</span>a<span class="p">)</span><span class="w"> </span><span class="o">==</span><span class="w"> </span>teamOf<span class="p">(</span>b<span class="p">)</span><span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span>teamOf<span class="p">(</span>b<span class="p">)</span><span class="w"> </span><span class="o">==</span><span class="w"> </span>teamOf<span class="p">(</span>c<span class="p">);</span>
<span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell6">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</div>
</details></section>
<section id="the-rule">
<h4>The rule<a class="headerlink" href="#the-rule" title="Link to this heading"></a></h4>
<p>Here is the complete rule.</p>
<div class="literal-block-wrapper docutils container" id="id6">
<div class="code-block-caption"><span class="caption-text"><a class="reference external" href="https://github.com/Certora/Examples/blob/7dfc379423202c90cf284eb42800b97cf5c95d83/CVLByExample/Teams/Teams.spec">A team has at most three players</a></span><a class="headerlink" href="#id6" title="Link to this code"></a></div>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell7"><span></span><span class="c1">/// @title A team has at most three players</span>
<span class="k">invariant</span><span class="w"> </span><span class="nc">teamHasMaxThreePlayers</span><span class="p">(</span><span class="kt">address</span><span class="w"> </span>a<span class="p">,</span><span class="w"> </span><span class="kt">address</span><span class="w"> </span>b<span class="p">,</span><span class="w"> </span><span class="kt">address</span><span class="w"> </span>c<span class="p">,</span><span class="w"> </span><span class="kt">address</span><span class="w"> </span>d<span class="p">)</span>
<span class="w">    </span><span class="p">(</span>
<span class="w">        </span>teamOf<span class="p">(</span>a<span class="p">)</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span>
<span class="w">        </span>fourDifferentAddresses<span class="p">(</span>a<span class="p">,</span><span class="w"> </span>b<span class="p">,</span><span class="w"> </span>c<span class="p">,</span><span class="w"> </span>d<span class="p">)</span><span class="w"> </span><span class="o">&amp;&amp;</span>
<span class="w">        </span>sameTeam<span class="p">(</span>a<span class="p">,</span><span class="w"> </span>b<span class="p">,</span><span class="w"> </span>c<span class="p">)</span>
<span class="w">        </span><span class="o">=&gt;</span><span class="w"> </span>teamOf<span class="p">(</span>d<span class="p">)</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span>teamOf<span class="p">(</span>a<span class="p">)</span>
<span class="w">    </span><span class="p">)</span>
<span class="w">    </span><span class="p">{</span>
<span class="w">        </span><span class="kr">preserved</span><span class="w"> </span>createTeam<span class="p">(</span>
<span class="w">            </span><span class="kt">address</span><span class="w"> </span>leader<span class="p">,</span>
<span class="w">            </span><span class="kt">address</span><span class="w"> </span>playerA<span class="p">,</span>
<span class="w">            </span><span class="kt">address</span><span class="w"> </span>playerB<span class="p">,</span>
<span class="w">            </span><span class="kt">uint8</span><span class="w"> </span>teamId
<span class="w">        </span><span class="p">)</span><span class="w"> </span>with<span class="w"> </span><span class="p">(</span><span class="kt">env</span><span class="w"> </span>e<span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">            </span><span class="kr">requireInvariant</span><span class="w"> </span>nonExistTeamHasNoPlayers<span class="p">(</span>teamId<span class="p">,</span><span class="w"> </span>a<span class="p">);</span>
<span class="w">            </span><span class="kr">requireInvariant</span><span class="w"> </span>nonExistTeamHasNoPlayers<span class="p">(</span>teamId<span class="p">,</span><span class="w"> </span>b<span class="p">);</span>
<span class="w">            </span><span class="kr">requireInvariant</span><span class="w"> </span>nonExistTeamHasNoPlayers<span class="p">(</span>teamId<span class="p">,</span><span class="w"> </span>c<span class="p">);</span>
<span class="w">            </span><span class="kr">requireInvariant</span><span class="w"> </span>nonExistTeamHasNoPlayers<span class="p">(</span>teamId<span class="p">,</span><span class="w"> </span>d<span class="p">);</span>
<span class="w">        </span><span class="p">}</span>
<span class="w">    </span><span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell7">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</div>
<p>As you can see, we used a different preserved block here. This preserved block adds
a pre-condition only when verifying the invariant on the function <code class="code highlight cvl docutils literal highlight-cvl">createTeam</code>
using environment <code class="code highlight cvl docutils literal highlight-cvl"><span class="kt">env</span><span class="w"> </span>e</code>. Without this preserved block, the Prover may assume
that the team had players <em>before it was created</em>.</p>
<div class="admonition seealso">
<p class="admonition-title">See also</p>
<p>You can find out more about preserved blocks in <a class="reference internal" href="../cvl/invariants.html#preserved"><span class="std std-ref">Preserved blocks</span></a> section.</p>
</div>
</section>
</section>
</section>
</section>


           </div>
          </div>
          <footer><div class="rst-footer-buttons" role="navigation" aria-label="Footer">
        <a href="satisfy.html" class="btn btn-neutral float-left" title="Producing Positive Examples" accesskey="p" rel="prev"><span class="fa fa-arrow-circle-left" aria-hidden="true"></span> Previous</a>
        <a href="parametric.html" class="btn btn-neutral float-right" title="Parametric rules" accesskey="n" rel="next">Next <span class="fa fa-arrow-circle-right" aria-hidden="true"></span></a>
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