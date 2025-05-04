<!DOCTYPE html><html class="writer-html5" lang="en" data-content_root="../../../"><head>
  <meta charset="utf-8"><meta name="viewport" content="width=device-width, initial-scale=1">

  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>CLI Options — Certora Prover Documentation 0.0 documentation</title>
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
        <script async="async" src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>
    <script src="../../../_static/js/theme.js"></script>
    <link rel="index" title="Index" href="../../../genindex.html">
    <link rel="search" title="Search" href="../../../search.html">
    <link rel="next" title="Configuration (Conf) Files" href="conf-file-api.html">
    <link rel="prev" title="Certora Prover CLI" href="index.html"> 
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

mjx-msup {
  display: inline-block;
  text-align: left;
}

mjx-mn {
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

mjx-TeXAtom {
  display: inline-block;
  text-align: left;
}

mjx-mo {
  display: inline-block;
  text-align: left;
}

mjx-stretchy-h {
  display: inline-table;
  width: 100%;
}

mjx-stretchy-h > * {
  display: table-cell;
  width: 0;
}

mjx-stretchy-h > * > mjx-c {
  display: inline-block;
  transform: scalex(1.0000001);
}

mjx-stretchy-h > * > mjx-c::before {
  display: inline-block;
  width: initial;
}

mjx-stretchy-h > mjx-ext {
  /* IE */ overflow: hidden;
  /* others */ overflow: clip visible;
  width: 100%;
}

mjx-stretchy-h > mjx-ext > mjx-c::before {
  transform: scalex(500);
}

mjx-stretchy-h > mjx-ext > mjx-c {
  width: 0;
}

mjx-stretchy-h > mjx-beg > mjx-c {
  margin-right: -.1em;
}

mjx-stretchy-h > mjx-end > mjx-c {
  margin-left: -.1em;
}

mjx-stretchy-v {
  display: inline-block;
}

mjx-stretchy-v > * {
  display: block;
}

mjx-stretchy-v > mjx-beg {
  height: 0;
}

mjx-stretchy-v > mjx-end > mjx-c {
  display: block;
}

mjx-stretchy-v > * > mjx-c {
  transform: scaley(1.0000001);
  transform-origin: left center;
  overflow: hidden;
}

mjx-stretchy-v > mjx-ext {
  display: block;
  height: 100%;
  box-sizing: border-box;
  border: 0px solid transparent;
  /* IE */ overflow: hidden;
  /* others */ overflow: visible clip;
}

mjx-stretchy-v > mjx-ext > mjx-c::before {
  width: initial;
  box-sizing: border-box;
}

mjx-stretchy-v > mjx-ext > mjx-c {
  transform: scaleY(500) translateY(.075em);
  overflow: visible;
}

mjx-mark {
  display: inline-block;
  height: 0px;
}

mjx-mi {
  display: inline-block;
  text-align: left;
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

mjx-c.mjx-c32::before {
  padding: 0.666em 0.5em 0 0;
  content: "2";
}

mjx-c.mjx-c35::before {
  padding: 0.666em 0.5em 0.022em 0;
  content: "5";
}

mjx-c.mjx-c36::before {
  padding: 0.666em 0.5em 0.022em 0;
  content: "6";
}

mjx-c.mjx-c2212::before {
  padding: 0.583em 0.778em 0.082em 0;
  content: "\2212";
}

mjx-c.mjx-c31::before {
  padding: 0.666em 0.5em 0 0;
  content: "1";
}

mjx-c.mjx-c1D45B.TEX-I::before {
  padding: 0.442em 0.6em 0.011em 0;
  content: "n";
}
</style></head>

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
<li class="toctree-l2 current" aria-expanded="true"><a class="reference internal" href="index.html"><button class="toctree-expand" title="Open/close menu"></button>Certora Prover CLI</a><ul class="" aria-expanded="false">
<li class="toctree-l3 current" aria-expanded="true"><a class="reference internal current" href="#" aria-expanded="true">CLI Options</a></li>
<li class="toctree-l3"><a class="reference internal" href="#most-frequently-used-options"><button class="toctree-expand" title="Open/close menu"></button>Most frequently used options</a><ul>
<li class="toctree-l4"><a class="reference internal" href="#verify"><code class="docutils literal notranslate"><span class="pre">verify</span></code></a></li>
<li class="toctree-l4"><a class="reference internal" href="#msg"><code class="docutils literal notranslate"><span class="pre">msg</span></code></a></li>
<li class="toctree-l4"><a class="reference internal" href="#rule"><code class="docutils literal notranslate"><span class="pre">rule</span></code></a></li>
<li class="toctree-l4"><a class="reference internal" href="#exclude-rule"><code class="docutils literal notranslate"><span class="pre">exclude_rule</span></code></a></li>
<li class="toctree-l4"><a class="reference internal" href="#split-rules"><code class="docutils literal notranslate"><span class="pre">split_rules</span></code></a></li>
<li class="toctree-l4"><a class="reference internal" href="#method"><code class="docutils literal notranslate"><span class="pre">method</span></code></a></li>
<li class="toctree-l4"><a class="reference internal" href="#parametric-contracts"><code class="docutils literal notranslate"><span class="pre">parametric_contracts</span></code></a></li>
<li class="toctree-l4"><a class="reference internal" href="#wait-for-results"><code class="docutils literal notranslate"><span class="pre">wait_for_results</span></code></a></li>
</ul>
</li>
<li class="toctree-l3"><a class="reference internal" href="#options-affecting-the-type-of-verification-run"><button class="toctree-expand" title="Open/close menu"></button>Options affecting the type of verification run</a><ul>
<li class="toctree-l4"><a class="reference internal" href="#coverage-info"><code class="docutils literal notranslate"><span class="pre">coverage_info</span></code></a></li>
<li class="toctree-l4"><a class="reference internal" href="#foundry"><code class="docutils literal notranslate"><span class="pre">foundry</span></code></a></li>
<li class="toctree-l4"><a class="reference internal" href="#independent-satisfy"><code class="docutils literal notranslate"><span class="pre">independent_satisfy</span></code></a></li>
<li class="toctree-l4"><a class="reference internal" href="#multi-assert-check"><code class="docutils literal notranslate"><span class="pre">multi_assert_check</span></code></a></li>
<li class="toctree-l4"><a class="reference internal" href="#multi-example"><code class="docutils literal notranslate"><span class="pre">multi_example</span></code></a></li>
<li class="toctree-l4"><a class="reference internal" href="#project-sanity"><code class="docutils literal notranslate"><span class="pre">project_sanity</span></code></a></li>
<li class="toctree-l4"><a class="reference internal" href="#rule-sanity"><code class="docutils literal notranslate"><span class="pre">rule_sanity</span></code></a></li>
<li class="toctree-l4"><a class="reference internal" href="#short-output"><code class="docutils literal notranslate"><span class="pre">short_output</span></code></a></li>
</ul>
</li>
<li class="toctree-l3"><a class="reference internal" href="#options-that-control-the-solidity-compiler"><button class="toctree-expand" title="Open/close menu"></button>Options that control the Solidity compiler</a><ul>
<li class="toctree-l4"><a class="reference internal" href="#solc-map"><code class="docutils literal notranslate"><span class="pre">compiler_map</span></code></a></li>
<li class="toctree-l4"><a class="reference internal" href="#ignore-solidity-warnings"><code class="docutils literal notranslate"><span class="pre">ignore_solidity_warnings</span></code></a></li>
<li class="toctree-l4"><a class="reference internal" href="#packages"><code class="docutils literal notranslate"><span class="pre">packages</span></code></a></li>
<li class="toctree-l4"><a class="reference internal" href="#packages-path"><code class="docutils literal notranslate"><span class="pre">packages_path</span></code></a></li>
<li class="toctree-l4"><a class="reference internal" href="#solc"><code class="docutils literal notranslate"><span class="pre">solc</span></code></a></li>
<li class="toctree-l4"><a class="reference internal" href="#solc-allow-path"><code class="docutils literal notranslate"><span class="pre">solc_allow_path</span></code></a></li>
<li class="toctree-l4"><a class="reference internal" href="#solc-evm-version"><code class="docutils literal notranslate"><span class="pre">solc_evm_version</span></code></a></li>
<li class="toctree-l4"><a class="reference internal" href="#solc-evm-version-map"><code class="docutils literal notranslate"><span class="pre">solc_evm_version_map</span></code></a></li>
<li class="toctree-l4"><a class="reference internal" href="#solc-optimize"><code class="docutils literal notranslate"><span class="pre">solc_optimize</span></code></a></li>
<li class="toctree-l4"><a class="reference internal" href="#solc-optimize-map"><code class="docutils literal notranslate"><span class="pre">solc_optimize_map</span></code></a></li>
<li class="toctree-l4"><a class="reference internal" href="#solc-via-ir"><code class="docutils literal notranslate"><span class="pre">solc_via_ir</span></code></a></li>
<li class="toctree-l4"><a class="reference internal" href="#solc-via-ir-map"><code class="docutils literal notranslate"><span class="pre">solc_via_ir_map</span></code></a></li>
<li class="toctree-l4"><a class="reference internal" href="#vyper"><code class="docutils literal notranslate"><span class="pre">vyper</span></code></a></li>
</ul>
</li>
<li class="toctree-l3"><a class="reference internal" href="#options-regarding-source-code-loops"><button class="toctree-expand" title="Open/close menu"></button>Options regarding source code loops</a><ul>
<li class="toctree-l4"><a class="reference internal" href="#loop-iter"><code class="docutils literal notranslate"><span class="pre">loop_iter</span></code></a></li>
<li class="toctree-l4"><a class="reference internal" href="#optimistic-loop"><code class="docutils literal notranslate"><span class="pre">optimistic_loop</span></code></a></li>
</ul>
</li>
<li class="toctree-l3"><a class="reference internal" href="#options-regarding-summarization"><button class="toctree-expand" title="Open/close menu"></button>Options regarding summarization</a><ul>
<li class="toctree-l4"><a class="reference internal" href="#auto-dispatcher"><code class="docutils literal notranslate"><span class="pre">auto_dispatcher</span></code></a></li>
<li class="toctree-l4"><a class="reference internal" href="#nondet-difficult-funcs"><code class="docutils literal notranslate"><span class="pre">nondet_difficult_funcs</span></code></a></li>
<li class="toctree-l4"><a class="reference internal" href="#nondet-minimal-difficulty"><code class="docutils literal notranslate"><span class="pre">nondet_minimal_difficulty</span></code></a></li>
<li class="toctree-l4"><a class="reference internal" href="#optimistic-summary-recursion"><code class="docutils literal notranslate"><span class="pre">optimistic_summary_recursion</span></code></a></li>
<li class="toctree-l4"><a class="reference internal" href="#summary-recursion-limit"><code class="docutils literal notranslate"><span class="pre">summary_recursion_limit</span></code></a></li>
</ul>
</li>
<li class="toctree-l3"><a class="reference internal" href="#options-regarding-hashing-of-unbounded-data"><button class="toctree-expand" title="Open/close menu"></button>Options regarding hashing of unbounded data</a><ul>
<li class="toctree-l4"><a class="reference internal" href="#optimistic-hashing"><code class="docutils literal notranslate"><span class="pre">optimistic_hashing</span></code></a></li>
<li class="toctree-l4"><a class="reference internal" href="#hashing-length-bound"><code class="docutils literal notranslate"><span class="pre">hashing_length_bound</span></code></a></li>
</ul>
</li>
<li class="toctree-l3"><a class="reference internal" href="#options-that-help-reduce-the-running-time"><button class="toctree-expand" title="Open/close menu"></button>Options that help reduce the running time</a><ul>
<li class="toctree-l4"><a class="reference internal" href="#compilation-steps-only"><code class="docutils literal notranslate"><span class="pre">compilation_steps_only</span></code></a></li>
<li class="toctree-l4"><a class="reference internal" href="#disable-local-type-checking"><code class="docutils literal notranslate"><span class="pre">disable_local_type_checking</span></code></a></li>
<li class="toctree-l4"><a class="reference internal" href="#global-timeout"><code class="docutils literal notranslate"><span class="pre">global_timeout</span></code></a></li>
<li class="toctree-l4"><a class="reference internal" href="#id37"><code class="docutils literal notranslate"><span class="pre">method</span></code></a></li>
<li class="toctree-l4"><a class="reference internal" href="#smt-timeout"><code class="docutils literal notranslate"><span class="pre">smt_timeout</span></code></a></li>
</ul>
</li>
<li class="toctree-l3"><a class="reference internal" href="#options-to-set-addresses-and-link-contracts"><button class="toctree-expand" title="Open/close menu"></button>Options to set addresses and link contracts</a><ul>
<li class="toctree-l4"><a class="reference internal" href="#address"><code class="docutils literal notranslate"><span class="pre">address</span></code></a></li>
<li class="toctree-l4"><a class="reference internal" href="#contract-extensions"><code class="docutils literal notranslate"><span class="pre">contract_extensions</span></code></a></li>
<li class="toctree-l4"><a class="reference internal" href="#contract-recursion-limit"><code class="docutils literal notranslate"><span class="pre">contract_recursion_limit</span></code></a></li>
<li class="toctree-l4"><a class="reference internal" href="#link"><code class="docutils literal notranslate"><span class="pre">link</span></code></a></li>
<li class="toctree-l4"><a class="reference internal" href="#optimistic-contract-recursion"><code class="docutils literal notranslate"><span class="pre">optimistic_contract_recursion</span></code></a></li>
<li class="toctree-l4"><a class="reference internal" href="#optimistic-fallback"><code class="docutils literal notranslate"><span class="pre">optimistic_fallback</span></code></a></li>
<li class="toctree-l4"><a class="reference internal" href="#struct-link"><code class="docutils literal notranslate"><span class="pre">struct_link</span></code></a></li>
</ul>
</li>
<li class="toctree-l3"><a class="reference internal" href="#options-for-job-metadata-and-dashboard-filtering"><button class="toctree-expand" title="Open/close menu"></button>Options for job metadata and dashboard filtering</a><ul>
<li class="toctree-l4"><a class="reference internal" href="#id46"><code class="docutils literal notranslate"><span class="pre">msg</span></code></a></li>
<li class="toctree-l4"><a class="reference internal" href="#protocol-author"><code class="docutils literal notranslate"><span class="pre">protocol_author</span></code></a></li>
<li class="toctree-l4"><a class="reference internal" href="#protocol-name"><code class="docutils literal notranslate"><span class="pre">protocol_name</span></code></a></li>
</ul>
</li>
<li class="toctree-l3"><a class="reference internal" href="#options-for-controlling-contract-creation"><button class="toctree-expand" title="Open/close menu"></button>Options for controlling contract creation</a><ul>
<li class="toctree-l4"><a class="reference internal" href="#dynamic-bound"><code class="docutils literal notranslate"><span class="pre">dynamic_bound</span></code></a></li>
<li class="toctree-l4"><a class="reference internal" href="#dynamic-dispatch"><code class="docutils literal notranslate"><span class="pre">dynamic_dispatch</span></code></a></li>
<li class="toctree-l4"><a class="reference internal" href="#prototype"><code class="docutils literal notranslate"><span class="pre">prototype</span></code></a></li>
</ul>
</li>
<li class="toctree-l3"><a class="reference internal" href="#version-options"><button class="toctree-expand" title="Open/close menu"></button>Version options</a><ul>
<li class="toctree-l4"><a class="reference internal" href="#version"><code class="docutils literal notranslate"><span class="pre">version</span></code></a></li>
<li class="toctree-l4"><a class="reference internal" href="#prover-version"><code class="docutils literal notranslate"><span class="pre">prover_version</span></code></a></li>
</ul>
</li>
<li class="toctree-l3"><a class="reference internal" href="#conf-file-options"><button class="toctree-expand" title="Open/close menu"></button>Conf file options</a><ul>
<li class="toctree-l4"><a class="reference internal" href="#override-base-config"><code class="docutils literal notranslate"><span class="pre">override_base_config</span></code></a></li>
</ul>
</li>
<li class="toctree-l3"><a class="reference internal" href="#advanced-options"><button class="toctree-expand" title="Open/close menu"></button>Advanced options</a><ul>
<li class="toctree-l4"><a class="reference internal" href="#java-args"><code class="docutils literal notranslate"><span class="pre">java_args</span></code></a></li>
<li class="toctree-l4"><a class="reference internal" href="#precise-bitwise-ops"><code class="docutils literal notranslate"><span class="pre">precise_bitwise_ops</span></code></a></li>
<li class="toctree-l4"><a class="reference internal" href="#prover-args"><code class="docutils literal notranslate"><span class="pre">prover_args</span></code></a></li>
<li class="toctree-l4"><a class="reference internal" href="#control-flow-splitting-options">Control flow splitting options</a></li>
</ul>
</li>
<li class="toctree-l3"><a class="reference internal" href="conf-file-api.html">Configuration (Conf) Files</a></li>
</ul>
</li>
<li class="toctree-l2"><a class="reference internal" href="../portal/using.html">Using the Certora Portal</a></li>
<li class="toctree-l2"><a class="reference internal" href="../changelog/index.html">Changelogs</a></li>
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
          <li class="breadcrumb-item"><a href="index.html">Certora Prover CLI</a></li>
      <li class="breadcrumb-item active">CLI Options</li>
      <li class="wy-breadcrumbs-aside">
            <a href="../../../_sources/docs/prover/cli/options.md.txt" rel="nofollow"> View page source</a>
      </li>
  </ul>
  <hr>
</div>
          <div role="main" class="document" itemscope="itemscope" itemtype="http://schema.org/Article">
           <div itemprop="articleBody">
             
  <section id="cli-options">
<span id="prover-cli-options"></span><h1><a class="toc-backref" href="#id65" role="doc-backlink">CLI Options</a><a class="headerlink" href="#cli-options" title="Link to this heading"></a></h1>
<p>The&nbsp;<code class="docutils literal notranslate"><span class="pre">certoraRun</span></code>&nbsp;utility invokes the Solidity compiler and afterwards sends the job to Certora’s servers.</p>
<p>The most commonly used command is:</p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell0"><span></span>certoraRun<span class="w"> </span>contractFile:contractName<span class="w"> </span>--verify<span class="w"> </span>contractName:specFile
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell0">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>If <code class="docutils literal notranslate"><span class="pre">contractFile</span></code> is named <code class="docutils literal notranslate"><span class="pre">contractName.sol</span></code>, the run command can be simplified to</p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell1"><span></span>certoraRun<span class="w"> </span>contractFile<span class="w"> </span>--verify<span class="w"> </span>contractName:specFile
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell1">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>A short summary of these options can be seen by invoking <code class="docutils literal notranslate"><span class="pre">certoraRun</span> <span class="pre">--help</span></code></p>
<p>For larger projects, the command line for running the Certora Prover can become large
and cumbersome. It is therefore recommended to use configuration files instead.
These are <a class="reference external" href="https://json5.org/">JSON5</a> files (with <code class="docutils literal notranslate"><span class="pre">.conf</span></code> extension) that hold the parameters and options for the Prover.
See <a class="reference internal" href="conf-file-api.html#conf-files"><span class="std std-ref">Configuration (Conf) Files</span></a> for more information.</p>
<nav class="contents" id="overview">
<p class="topic-title">Overview</p>
<ul class="simple">
<li><p><a class="reference internal" href="#cli-options" id="id65">CLI Options</a></p></li>
<li><p><a class="reference internal" href="#most-frequently-used-options" id="id66">Most frequently used options</a></p>
<ul>
<li><p><a class="reference internal" href="#verify" id="id67"><code class="docutils literal notranslate"><span class="pre">verify</span></code></a></p></li>
<li><p><a class="reference internal" href="#msg" id="id68"><code class="docutils literal notranslate"><span class="pre">msg</span></code></a></p></li>
<li><p><a class="reference internal" href="#rule" id="id69"><code class="docutils literal notranslate"><span class="pre">rule</span></code></a></p></li>
<li><p><a class="reference internal" href="#exclude-rule" id="id70"><code class="docutils literal notranslate"><span class="pre">exclude_rule</span></code></a></p></li>
<li><p><a class="reference internal" href="#split-rules" id="id71"><code class="docutils literal notranslate"><span class="pre">split_rules</span></code></a></p></li>
<li><p><a class="reference internal" href="#method" id="id72"><code class="docutils literal notranslate"><span class="pre">method</span></code></a></p></li>
<li><p><a class="reference internal" href="#parametric-contracts" id="id73"><code class="docutils literal notranslate"><span class="pre">parametric_contracts</span></code></a></p></li>
<li><p><a class="reference internal" href="#wait-for-results" id="id74"><code class="docutils literal notranslate"><span class="pre">wait_for_results</span></code></a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#options-affecting-the-type-of-verification-run" id="id75">Options affecting the type of verification run</a></p>
<ul>
<li><p><a class="reference internal" href="#coverage-info" id="id76"><code class="docutils literal notranslate"><span class="pre">coverage_info</span></code></a></p></li>
<li><p><a class="reference internal" href="#foundry" id="id77"><code class="docutils literal notranslate"><span class="pre">foundry</span></code></a></p></li>
<li><p><a class="reference internal" href="#independent-satisfy" id="id78"><code class="docutils literal notranslate"><span class="pre">independent_satisfy</span></code></a></p></li>
<li><p><a class="reference internal" href="#multi-assert-check" id="id79"><code class="docutils literal notranslate"><span class="pre">multi_assert_check</span></code></a></p></li>
<li><p><a class="reference internal" href="#multi-example" id="id80"><code class="docutils literal notranslate"><span class="pre">multi_example</span></code></a></p></li>
<li><p><a class="reference internal" href="#project-sanity" id="id81"><code class="docutils literal notranslate"><span class="pre">project_sanity</span></code></a></p></li>
<li><p><a class="reference internal" href="#rule-sanity" id="id82"><code class="docutils literal notranslate"><span class="pre">rule_sanity</span></code></a></p></li>
<li><p><a class="reference internal" href="#short-output" id="id83"><code class="docutils literal notranslate"><span class="pre">short_output</span></code></a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#options-that-control-the-solidity-compiler" id="id84">Options that control the Solidity compiler</a></p>
<ul>
<li><p><a class="reference internal" href="#solc-map" id="id85"><code class="docutils literal notranslate"><span class="pre">compiler_map</span></code></a></p></li>
<li><p><a class="reference internal" href="#ignore-solidity-warnings" id="id86"><code class="docutils literal notranslate"><span class="pre">ignore_solidity_warnings</span></code></a></p></li>
<li><p><a class="reference internal" href="#packages" id="id87"><code class="docutils literal notranslate"><span class="pre">packages</span></code></a></p></li>
<li><p><a class="reference internal" href="#packages-path" id="id88"><code class="docutils literal notranslate"><span class="pre">packages_path</span></code></a></p></li>
<li><p><a class="reference internal" href="#solc" id="id89"><code class="docutils literal notranslate"><span class="pre">solc</span></code></a></p></li>
<li><p><a class="reference internal" href="#solc-allow-path" id="id90"><code class="docutils literal notranslate"><span class="pre">solc_allow_path</span></code></a></p></li>
<li><p><a class="reference internal" href="#solc-evm-version" id="id91"><code class="docutils literal notranslate"><span class="pre">solc_evm_version</span></code></a></p></li>
<li><p><a class="reference internal" href="#solc-evm-version-map" id="id92"><code class="docutils literal notranslate"><span class="pre">solc_evm_version_map</span></code></a></p></li>
<li><p><a class="reference internal" href="#solc-optimize" id="id93"><code class="docutils literal notranslate"><span class="pre">solc_optimize</span></code></a></p></li>
<li><p><a class="reference internal" href="#solc-optimize-map" id="id94"><code class="docutils literal notranslate"><span class="pre">solc_optimize_map</span></code></a></p></li>
<li><p><a class="reference internal" href="#solc-via-ir" id="id95"><code class="docutils literal notranslate"><span class="pre">solc_via_ir</span></code></a></p></li>
<li><p><a class="reference internal" href="#solc-via-ir-map" id="id96"><code class="docutils literal notranslate"><span class="pre">solc_via_ir_map</span></code></a></p></li>
<li><p><a class="reference internal" href="#vyper" id="id97"><code class="docutils literal notranslate"><span class="pre">vyper</span></code></a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#options-regarding-source-code-loops" id="id98">Options regarding source code loops</a></p>
<ul>
<li><p><a class="reference internal" href="#loop-iter" id="id99"><code class="docutils literal notranslate"><span class="pre">loop_iter</span></code></a></p></li>
<li><p><a class="reference internal" href="#optimistic-loop" id="id100"><code class="docutils literal notranslate"><span class="pre">optimistic_loop</span></code></a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#options-regarding-summarization" id="id101">Options regarding summarization</a></p>
<ul>
<li><p><a class="reference internal" href="#auto-dispatcher" id="id102"><code class="docutils literal notranslate"><span class="pre">auto_dispatcher</span></code></a></p></li>
<li><p><a class="reference internal" href="#nondet-difficult-funcs" id="id103"><code class="docutils literal notranslate"><span class="pre">nondet_difficult_funcs</span></code></a></p></li>
<li><p><a class="reference internal" href="#nondet-minimal-difficulty" id="id104"><code class="docutils literal notranslate"><span class="pre">nondet_minimal_difficulty</span></code></a></p></li>
<li><p><a class="reference internal" href="#optimistic-summary-recursion" id="id105"><code class="docutils literal notranslate"><span class="pre">optimistic_summary_recursion</span></code></a></p></li>
<li><p><a class="reference internal" href="#summary-recursion-limit" id="id106"><code class="docutils literal notranslate"><span class="pre">summary_recursion_limit</span></code></a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#options-regarding-hashing-of-unbounded-data" id="id107">Options regarding hashing of unbounded data</a></p>
<ul>
<li><p><a class="reference internal" href="#optimistic-hashing" id="id108"><code class="docutils literal notranslate"><span class="pre">optimistic_hashing</span></code></a></p></li>
<li><p><a class="reference internal" href="#hashing-length-bound" id="id109"><code class="docutils literal notranslate"><span class="pre">hashing_length_bound</span></code></a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#options-that-help-reduce-the-running-time" id="id110">Options that help reduce the running time</a></p>
<ul>
<li><p><a class="reference internal" href="#compilation-steps-only" id="id111"><code class="docutils literal notranslate"><span class="pre">compilation_steps_only</span></code></a></p></li>
<li><p><a class="reference internal" href="#disable-local-type-checking" id="id112"><code class="docutils literal notranslate"><span class="pre">disable_local_type_checking</span></code></a></p></li>
<li><p><a class="reference internal" href="#global-timeout" id="id113"><code class="docutils literal notranslate"><span class="pre">global_timeout</span></code></a></p></li>
<li><p><a class="reference internal" href="#id37" id="id114"><code class="docutils literal notranslate"><span class="pre">method</span></code></a></p></li>
<li><p><a class="reference internal" href="#smt-timeout" id="id115"><code class="docutils literal notranslate"><span class="pre">smt_timeout</span></code></a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#options-to-set-addresses-and-link-contracts" id="id116">Options to set addresses and link contracts</a></p>
<ul>
<li><p><a class="reference internal" href="#address" id="id117"><code class="docutils literal notranslate"><span class="pre">address</span></code></a></p></li>
<li><p><a class="reference internal" href="#contract-extensions" id="id118"><code class="docutils literal notranslate"><span class="pre">contract_extensions</span></code></a></p></li>
<li><p><a class="reference internal" href="#contract-recursion-limit" id="id119"><code class="docutils literal notranslate"><span class="pre">contract_recursion_limit</span></code></a></p></li>
<li><p><a class="reference internal" href="#link" id="id120"><code class="docutils literal notranslate"><span class="pre">link</span></code></a></p></li>
<li><p><a class="reference internal" href="#optimistic-contract-recursion" id="id121"><code class="docutils literal notranslate"><span class="pre">optimistic_contract_recursion</span></code></a></p></li>
<li><p><a class="reference internal" href="#optimistic-fallback" id="id122"><code class="docutils literal notranslate"><span class="pre">optimistic_fallback</span></code></a></p></li>
<li><p><a class="reference internal" href="#struct-link" id="id123"><code class="docutils literal notranslate"><span class="pre">struct_link</span></code></a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#options-for-job-metadata-and-dashboard-filtering" id="id124">Options for job metadata and dashboard filtering</a></p>
<ul>
<li><p><a class="reference internal" href="#id46" id="id125"><code class="docutils literal notranslate"><span class="pre">msg</span></code></a></p></li>
<li><p><a class="reference internal" href="#protocol-author" id="id126"><code class="docutils literal notranslate"><span class="pre">protocol_author</span></code></a></p></li>
<li><p><a class="reference internal" href="#protocol-name" id="id127"><code class="docutils literal notranslate"><span class="pre">protocol_name</span></code></a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#options-for-controlling-contract-creation" id="id128">Options for controlling contract creation</a></p>
<ul>
<li><p><a class="reference internal" href="#dynamic-bound" id="id129"><code class="docutils literal notranslate"><span class="pre">dynamic_bound</span></code></a></p></li>
<li><p><a class="reference internal" href="#dynamic-dispatch" id="id130"><code class="docutils literal notranslate"><span class="pre">dynamic_dispatch</span></code></a></p></li>
<li><p><a class="reference internal" href="#prototype" id="id131"><code class="docutils literal notranslate"><span class="pre">prototype</span></code></a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#version-options" id="id132">Version options</a></p>
<ul>
<li><p><a class="reference internal" href="#version" id="id133"><code class="docutils literal notranslate"><span class="pre">version</span></code></a></p></li>
<li><p><a class="reference internal" href="#prover-version" id="id134"><code class="docutils literal notranslate"><span class="pre">prover_version</span></code></a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#conf-file-options" id="id135">Conf file options</a></p>
<ul>
<li><p><a class="reference internal" href="#override-base-config" id="id136"><code class="docutils literal notranslate"><span class="pre">override_base_config</span></code></a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#advanced-options" id="id137">Advanced options</a></p>
<ul>
<li><p><a class="reference internal" href="#java-args" id="id138"><code class="docutils literal notranslate"><span class="pre">java_args</span></code></a></p></li>
<li><p><a class="reference internal" href="#precise-bitwise-ops" id="id139"><code class="docutils literal notranslate"><span class="pre">precise_bitwise_ops</span></code></a></p></li>
<li><p><a class="reference internal" href="#prover-args" id="id140"><code class="docutils literal notranslate"><span class="pre">prover_args</span></code></a></p>
<ul>
<li><p><a class="reference internal" href="#enablestoragesplitting" id="id141"><code class="docutils literal notranslate"><span class="pre">enableStorageSplitting</span></code></a></p></li>
<li><p><a class="reference internal" href="#maxnumberofreachchecksbasedondomination" id="id142"><code class="docutils literal notranslate"><span class="pre">maxNumberOfReachChecksBasedOnDomination</span></code></a></p></li>
<li><p><a class="reference internal" href="#optimisticreturnsize" id="id143"><code class="docutils literal notranslate"><span class="pre">optimisticReturnsize</span></code></a></p></li>
<li><p><a class="reference internal" href="#smt-groundquantifiers" id="id144"><code class="docutils literal notranslate"><span class="pre">smt_groundQuantifiers</span></code></a></p></li>
<li><p><a class="reference internal" href="#superoptimisticreturnsize" id="id145"><code class="docutils literal notranslate"><span class="pre">superOptimisticReturnsize</span></code></a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#control-flow-splitting-options" id="id146">Control flow splitting options</a></p>
<ul>
<li><p><a class="reference internal" href="#depth" id="id147"><code class="docutils literal notranslate"><span class="pre">depth</span></code></a></p></li>
<li><p><a class="reference internal" href="#dontstopatfirstsplittimeout" id="id148"><code class="docutils literal notranslate"><span class="pre">dontStopAtFirstSplitTimeout</span></code></a></p></li>
<li><p><a class="reference internal" href="#mediumtimeout" id="id149"><code class="docutils literal notranslate"><span class="pre">mediumTimeout</span></code></a></p></li>
<li><p><a class="reference internal" href="#smt-initialsplitdepth" id="id150"><code class="docutils literal notranslate"><span class="pre">smt_initialSplitDepth</span></code></a></p></li>
</ul>
</li>
</ul>
</li>
</ul>
</nav>
</section>
<section id="most-frequently-used-options">
<h1><a class="toc-backref" href="#id66" role="doc-backlink">Most frequently used options</a><a class="headerlink" href="#most-frequently-used-options" title="Link to this heading"></a></h1>
<section id="verify">
<span id="id1"></span><h2><a class="toc-backref" href="#id67" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">verify</span></code></a><a class="headerlink" href="#verify" title="Link to this heading"></a></h2>
<p><strong>What does it do?</strong>
It runs formal verification of properties specified in a <code class="docutils literal notranslate"><span class="pre">.spec</span></code> file on a given contract. Each contract must have been declared in the input files or have the same name as the source code file it is in.</p>
<p><strong>When to use it?</strong>
When you wish to prove properties on the source code. This is by far the most common mode of the tool.</p>
<p><strong>Example - Command line</strong>
If we have a Solidity file <code class="docutils literal notranslate"><span class="pre">Bank.sol</span></code>, with a contract named <code class="docutils literal notranslate"><span class="pre">Bank</span></code> inside it, and a specification file called <code class="docutils literal notranslate"><span class="pre">Bank.spec</span></code>, the command would be:</p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell2"><span></span>certoraRun<span class="w"> </span>Bank.sol<span class="w"> </span>--verify<span class="w"> </span>Bank:Bank.spec
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell2">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p><strong>Example - Configuration file</strong></p>
<p>If we have a Solidity file with a contract named <code class="docutils literal notranslate"><span class="pre">Bank</span></code> inside it,
and a specification file called <code class="docutils literal notranslate"><span class="pre">Bank.spec</span></code>,
add the following line to the configuration file:</p>
<div class="highlight-json notranslate"><div class="highlight"><pre id="codecell3"><span></span><span class="nt">"verify"</span><span class="p">:</span><span class="w"> </span><span class="s2">"Bank:Bank.spec"</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell3">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
<section id="msg">
<span id="id2"></span><h2><a class="toc-backref" href="#id68" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">msg</span></code></a><a class="headerlink" href="#msg" title="Link to this heading"></a></h2>
<p><strong>What does it do?</strong>
Adds a message description to your run, similar to a commit message. This message will appear in the title of the completion email sent to you.</p>
<p><strong>When to use it?</strong>
Adding a message makes it easier to track several runs on <a class="reference external" href="https://prover.certora.com/">the Prover Dashboard</a>. It is very useful if you are running many verifications simultaneously. It is also helpful to keep track of a single file verification status over time, so we recommend always providing an informative message.</p>
<p><strong>Example - Command line</strong></p>
<p>To create the message above from the command line, use:</p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell4"><span></span>certoraRun<span class="w"> </span>Bank.sol<span class="w"> </span>--verify<span class="w"> </span>Bank:Bank.spec<span class="w"> </span>--msg<span class="w"> </span><span class="s1">'Removed an assertion'</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell4">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>You need to wrap your message in quotes in the command line if it contains spaces.</p>
</div>
<p><strong>Example - Configuration file</strong></p>
<p>To create the message above from the configuration file, use:</p>
<div class="highlight-json notranslate"><div class="highlight"><pre id="codecell5"><span></span><span class="nt">"msg"</span><span class="p">:</span><span class="w"> </span><span class="s2">"Removed an assertion"</span>
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
<section id="rule">
<span id="id3"></span><h2><a class="toc-backref" href="#id69" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">rule</span></code></a><a class="headerlink" href="#rule" title="Link to this heading"></a></h2>
<p><strong>What does it do?</strong>
Formally verifies one or more given properties instead of the whole specification file. An invariant can also be selected.</p>
<p><strong>When to use it?</strong>
This option saves a lot of run time. Use it whenever you care about only a
specific subset of a specification’s properties. The most common case is when
you add a new rule to an existing specification. The other is when code changes
cause a specific rule to fail; in the process of fixing the code, updating the
rule, and understanding counterexamples, you likely want to verify only that
specific rule.</p>
<p><strong>Rule Name Pattern</strong>
Rule names, like all CVL identifiers, have the same format as Solidity identifiers: they consist of a combination of letters, digits,
dollar signs and underscores, but cannot start with a digit (see <a class="reference external" href="https://docs.soliditylang.org/en/v0.8.16/path-resolution.html#allowed-paths">here</a>).
In addition, rule name patterns can include the wildcard <code class="docutils literal notranslate"><span class="pre">*</span></code> that can replace any sequence of valid identifier characters.
For example, the rule pattern <code class="docutils literal notranslate"><span class="pre">withdraw_*</span></code> can be used instead of listing all rules that start with the string <code class="docutils literal notranslate"><span class="pre">withdraw_</span></code>.</p>
<p><strong>Examples</strong>
If <code class="docutils literal notranslate"><span class="pre">Bank.spec</span></code> includes the following properties:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell6"><span></span><span class="k">invariant</span><span class="w"> </span><span class="nc">address_zero_cannot_become_an_account</span><span class="p">()</span>
<span class="k">rule</span><span class="w"> </span><span class="nc">withdraw_succeeds</span><span class="p">()</span>
<span class="k">rule</span><span class="w"> </span><span class="nc">withdraw_fails</span><span class="p">()</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell6">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>If we want to verify only <code class="docutils literal notranslate"><span class="pre">withdraw_succeeds</span></code>, we run the command</p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell7"><span></span>certoraRun<span class="w"> </span>Bank.sol<span class="w"> </span>--verify<span class="w"> </span>Bank:Bank.spec<span class="w"> </span>--rule<span class="w"> </span>withdraw_succeeds
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell7">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>If we want to verify both <code class="docutils literal notranslate"><span class="pre">withdraw_succeeds</span></code> and <code class="docutils literal notranslate"><span class="pre">withdraw_fails</span></code>, we run the command</p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell8"><span></span>certoraRun<span class="w"> </span>Bank.sol<span class="w"> </span>--verify<span class="w"> </span>Bank:Bank.spec<span class="w"> </span>--rule<span class="w"> </span>withdraw_succeeds<span class="w"> </span>withdraw_fails
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell8">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>Alternatively, to verify both <code class="docutils literal notranslate"><span class="pre">withdraw_succeeds</span></code> and <code class="docutils literal notranslate"><span class="pre">withdraw_fails</span></code>, we could
simply run  the command</p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell9"><span></span>certoraRun<span class="w"> </span>Bank.sol<span class="w"> </span>--verify<span class="w"> </span>Bank:Bank.spec<span class="w"> </span>--rule<span class="w"> </span>withdraw*
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell9">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>In the configuration file, it will look like this:</p>
<div class="highlight-json notranslate"><div class="highlight"><pre id="codecell10"><span></span><span class="nt">"rule"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="s2">"withdraw_succeeds"</span><span class="p">,</span><span class="w"> </span><span class="s2">"withdraw_fails"</span><span class="p">]</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell10">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>or</p>
<div class="highlight-json notranslate"><div class="highlight"><pre id="codecell11"><span></span><span class="nt">"rule"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="s2">"withdraw_*"</span><span class="p">]</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell11">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
<section id="exclude-rule">
<span id="id4"></span><h2><a class="toc-backref" href="#id70" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">exclude_rule</span></code></a><a class="headerlink" href="#exclude-rule" title="Link to this heading"></a></h2>
<p><strong>What does it do?</strong>
This flag is the opposite of <a class="reference internal" href="#rule"><span class="std std-ref">rule</span></a> - it allows you to specify a list of rules that <em>should not</em> be run.</p>
<p>You can filter out several rules or rule patterns.</p>
<p><strong>When to use it?</strong>
Use this flag when certain rules take too long to run or require a different configuration than the current verification run.</p>
<p><strong>Rule Name Pattern</strong>
Rule name or rule name with wildcards. See detailed specifications in <a class="reference internal" href="#rule"><span class="std std-ref">rule</span></a>.</p>
<p><strong>Examples</strong>
If <code class="docutils literal notranslate"><span class="pre">Bank.spec</span></code> includes the following properties:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell12"><span></span><span class="k">invariant</span><span class="w"> </span><span class="nc">address_zero_cannot_become_an_account</span><span class="p">()</span>
<span class="k">rule</span><span class="w"> </span><span class="nc">withdraw_succeeds</span><span class="p">()</span>
<span class="k">rule</span><span class="w"> </span><span class="nc">withdraw_fails</span><span class="p">()</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell12">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>If we want to skip checking <code class="docutils literal notranslate"><span class="pre">withdraw_succeeds</span></code> and <code class="docutils literal notranslate"><span class="pre">withdraw_fails</span></code>, we could run the command:</p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell13"><span></span>certoraRun<span class="w"> </span>Bank.sol<span class="w"> </span>--verify<span class="w"> </span>Bank:Bank.spec<span class="w"> </span>--exclude_rule<span class="w"> </span>withdraw*
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell13">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>or add to the conf file:</p>
<div class="highlight-json notranslate"><div class="highlight"><pre id="codecell14"><span></span><span class="nt">"exclude_rule"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="s2">"withdraw_*"</span><span class="p">]</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell14">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
<section id="split-rules">
<span id="id5"></span><h2><a class="toc-backref" href="#id71" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">split_rules</span></code></a><a class="headerlink" href="#split-rules" title="Link to this heading"></a></h2>
<p><strong>What does it do?</strong>
Typically, all rules (after being filtered by <a class="reference internal" href="#rule"><span class="std std-ref">rule</span></a> and <a class="reference internal" href="#exclude-rule"><span class="std std-ref">exclude_rule</span></a>) are evaluated in a single Prover job.
With <code class="docutils literal notranslate"><span class="pre">split_rules</span></code> the user can run specific rules on separate dedicated Prover jobs.
A new job will be created and executed for each rule that matches the rule patterns in
<code class="docutils literal notranslate"><span class="pre">split_rules</span></code> an additional job will be created for the rest of the rules.
After launching the generated jobs, the original job will return with a link to the dashboard,
listing the status of the generated jobs.</p>
<p>You can split several rules or rule patterns.</p>
<p><strong>When to use it?</strong>
This option is useful when some rules take a much longer time than the rest. Split the difficult rules to
their own dedicated Prover jobs will give them more resources that will potentially reduce their chance to
timeout and will decrease the time to get the final job result for the less computationally intensive rules.</p>
<p><strong>Rule Name Pattern</strong>
Rule name or rule name patterns. See detailed specifications in <a class="reference internal" href="#rule"><span class="std std-ref">rule</span></a>.</p>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>When used together with the <a class="reference internal" href="#rule"><span class="std std-ref">rule</span></a> option, the logic is to collect all rules
that match <code class="docutils literal notranslate"><span class="pre">rule</span></code> patterns and then subtract from them all rules that match
any <a class="reference internal" href="#exclude-rule"><span class="std std-ref">exclude_rule</span></a> patterns.</p>
</div>
<p><strong>Examples</strong>
If <code class="docutils literal notranslate"><span class="pre">Bank.spec</span></code> includes the following properties:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell15"><span></span><span class="k">invariant</span><span class="w"> </span><span class="nc">address_zero_cannot_become_an_account</span><span class="p">()</span>
<span class="k">rule</span><span class="w"> </span><span class="nc">withdraw_succeeds</span><span class="p">()</span>
<span class="k">rule</span><span class="w"> </span><span class="nc">withdraw_fails</span><span class="p">()</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell15">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>If we want to run the invariant on different Prover jobs we could run the command:</p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell16"><span></span>certoraRun<span class="w"> </span>Bank.sol<span class="w"> </span>--verify<span class="w"> </span>Bank:Bank.spec<span class="w"> </span>--split_rules<span class="w"> </span>address_zero_cannot_become_an_account
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell16">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>or add to the configuration file:</p>
<div class="highlight-json notranslate"><div class="highlight"><pre id="codecell17"><span></span><span class="nt">"split_rules"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="s2">"address_zero_cannot_become_an_account"</span><span class="p">]</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell17">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>The rest of the rules (<code class="docutils literal notranslate"><span class="pre">withdraw_succeeds</span></code> and <code class="docutils literal notranslate"><span class="pre">withdraw_fails</span></code>) will run together in a different Prover job.</p>
</section>
<section id="method">
<span id="id6"></span><h2><a class="toc-backref" href="#id72" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">method</span></code></a><a class="headerlink" href="#method" title="Link to this heading"></a></h2>
<p><strong>What does it do?</strong>
Only uses functions with the given method signature when instantiating
<a class="reference internal" href="../../user-guide/glossary.html#term-parametric-rule"><span class="xref std std-term">parametric rule</span></a>s and <a class="reference internal" href="../../user-guide/glossary.html#term-invariant"><span class="xref std std-term">invariant</span></a>s. The method signature is the ABI
representation of the method, optionally prepended by a contract name or
wildcard (<code class="docutils literal notranslate"><span class="pre">_</span></code>). If no contract is specified the primary contract is assumed, and
if the wildcard is used then all methods with this signature across all
contracts in the <a class="reference internal" href="../../user-guide/glossary.html#term-0"><span class="xref std std-term">scene</span></a> will be used.</p>
<p>You may provide multiple method signatures, in which case the Prover will run on
each of the listed methods.</p>
<p><strong>When to use it?</strong>
This option is useful when focusing on a specific counterexample; running on a
specific contract method saves time.</p>
<p><strong>Examples</strong>
Suppose we are verifying an ERC20 contract, and we have the following
<a class="reference internal" href="../../user-guide/glossary.html#term-parametric-rule"><span class="xref std std-term">parametric rule</span></a>:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell18"><span></span><span class="k">rule</span><span class="w"> </span><span class="nc">r</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kt">method</span><span class="w"> </span>f<span class="p">;</span><span class="w"> </span><span class="kt">env</span><span class="w"> </span>e<span class="p">;</span><span class="w"> </span><span class="kt">calldataarg</span><span class="w"> </span>args<span class="p">;</span>
<span class="w">    </span><span class="kt">address</span><span class="w"> </span>owner<span class="p">;</span><span class="w"> </span><span class="kt">address</span><span class="w"> </span>spender<span class="p">;</span>

<span class="w">    </span><span class="kt">mathint</span><span class="w"> </span>allowance_before<span class="w"> </span><span class="o">=</span><span class="w"> </span>allowance<span class="p">(</span>owner<span class="p">,</span><span class="w"> </span>spender<span class="p">);</span>
<span class="w">    </span>f<span class="p">(</span>e<span class="p">,</span>args<span class="p">);</span>
<span class="w">    </span><span class="kt">mathint</span><span class="w"> </span>allowance_after<span class="w">  </span><span class="o">=</span><span class="w"> </span>allowance<span class="p">(</span>owner<span class="p">,</span><span class="w"> </span>spender<span class="p">);</span>

<span class="w">    </span><span class="kr">assert</span><span class="w"> </span>allowance_after<span class="w"> </span><span class="o">&gt;</span><span class="w"> </span>allowance_before<span class="w"> </span><span class="o">=&gt;</span><span class="w"> </span>e<span class="p">.</span><span class="kc">msg.sender</span><span class="w"> </span><span class="o">==</span><span class="w"> </span>owner<span class="p">;</span>
<span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell18">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>If we discover a counterexample in the method <code class="docutils literal notranslate"><span class="pre">deposit(uint)</span></code> of contract <code class="docutils literal notranslate"><span class="pre">C</span></code>,
and wish to change the contract or the spec to rerun, we can just rerun on
the <code class="docutils literal notranslate"><span class="pre">C.deposit</span></code> method via the command:</p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell19"><span></span>certoraRun<span class="w"> </span>--method<span class="w"> </span><span class="s1">'C.deposit(uint)'</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell19">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>If we discover a counterexample in several methods, we could rerun just those via the command line:</p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell20"><span></span>certoraRun<span class="w"> </span>--method<span class="w"> </span><span class="s1">'deposit(uint)'</span><span class="w"> </span>--method<span class="w"> </span><span class="s1">'_.transfer(address,uint256)'</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell20">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>Many shells will interpret the <code class="docutils literal notranslate"><span class="pre">(</span></code> and <code class="docutils literal notranslate"><span class="pre">)</span></code> characters specially, so
the method signature argument will usually need to be quoted in the command line as in the above example.</p>
</div>
<p>In the configuration file we can add the following line:</p>
<div class="highlight-json notranslate"><div class="highlight"><pre id="codecell21"><span></span><span class="nt">"method"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="s2">"C.deposit(uint)"</span><span class="p">,</span><span class="w"> </span><span class="s2">"_.transfer(address,uint256)"</span><span class="p">]</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell21">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>In the last example the <code class="docutils literal notranslate"><span class="pre">transfer</span></code> method of all contracts in the
scene will be used, but only the <code class="docutils literal notranslate"><span class="pre">deposit</span></code> method of the primary contract.</p>
</section>
<section id="parametric-contracts">
<span id="id7"></span><h2><a class="toc-backref" href="#id73" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">parametric_contracts</span></code></a><a class="headerlink" href="#parametric-contracts" title="Link to this heading"></a></h2>
<div class="versionadded">
<p><span class="versionmodified added">Added in version 5.0: </span>Prior to version 5, method variables and invariants were only instantiated with
methods of <a class="reference internal" href="../../cvl/expr.html#currentcontract"><span class="std std-ref">Special variables and fields</span></a>.</p>
</div>
<p><strong>What does it do?</strong>
Only uses methods on the specified contract when instantiating
<a class="reference internal" href="../../user-guide/glossary.html#term-parametric-rule"><span class="xref std std-term">parametric rule</span></a>s or <a class="reference internal" href="../../user-guide/glossary.html#term-invariant"><span class="xref std std-term">invariant</span></a>s.
The contract name must be one of the contracts included in the <a class="reference internal" href="../../user-guide/glossary.html#term-0"><span class="xref std std-term">scene</span></a>.</p>
<p><strong>When to use it?</strong>
As with the <a class="reference internal" href="#rule"><span class="std std-ref">rule</span></a> and <a class="reference internal" href="#method"><span class="std std-ref">method</span></a> options, this option is used to
avoid rerunning the entire verification</p>
<p><strong>Example</strong>
Suppose you are working on a multicontract verification and wish to debug a
counterexample in a method of the <code class="docutils literal notranslate"><span class="pre">Underlying</span></code> contract defined in the file
<code class="docutils literal notranslate"><span class="pre">Example.sol</span></code>, you can execute the command:</p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell22"><span></span>certoraRun<span class="w"> </span>Main:Example.sol<span class="w"> </span>Underlying:Example.sol<span class="w"> </span>--verify<span class="w"> </span>Main:Example.spec<span class="w"> </span><span class="se">\</span>
<span class="w">    </span>--parametric_contracts<span class="w"> </span>Underlying
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell22">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>or add to the configuration file:</p>
<div class="highlight-json notranslate"><div class="highlight"><pre id="codecell23"><span></span><span class="nt">"parametric_contracts"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="s2">"Underlying"</span><span class="p">]</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell23">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
<section id="wait-for-results">
<span id="id8"></span><h2><a class="toc-backref" href="#id74" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">wait_for_results</span></code></a><a class="headerlink" href="#wait-for-results" title="Link to this heading"></a></h2>
<p><strong>Parameters</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell24"><span></span>ALL<span class="p">|</span>NONE
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell24">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p><strong>What does it do?</strong>
Wait for verification results after sending the verification request.
By default, the program exits after the request.
The return code will not be zero if the verification finds a violation.</p>
<p>In CI, the default behavior is different: the Prover waits for verification results,
and the return code will not be zero if a violation is found.
You can force the Prover not to wait for verification results by giving the parameter <code class="docutils literal notranslate"><span class="pre">NONE</span></code>.
In that case, the return code will be zero if the jobs were sent successfully.</p>
<p><strong>When to use it?</strong>
Use it to receive verification results in the terminal or a wrapping script.</p>
<p><strong>Example - Command line</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell25"><span></span>certoraRun<span class="w"> </span>Example.sol<span class="w"> </span>--verify<span class="w"> </span>Example:Example.spec<span class="w"> </span>--wait_for_results
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell25">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p><strong>Example - Configuration file</strong></p>
<div class="highlight-json notranslate"><div class="highlight"><pre id="codecell26"><span></span><span class="nt">"wait_for_results"</span><span class="p">:</span><span class="w"> </span><span class="s2">"ALL"</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell26">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
</section>
<section id="options-affecting-the-type-of-verification-run">
<h1><a class="toc-backref" href="#id75" role="doc-backlink">Options affecting the type of verification run</a><a class="headerlink" href="#options-affecting-the-type-of-verification-run" title="Link to this heading"></a></h1>
<section id="coverage-info">
<span id="id9"></span><h2><a class="toc-backref" href="#id76" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">coverage_info</span></code></a><a class="headerlink" href="#coverage-info" title="Link to this heading"></a></h2>
<p><strong>Usage</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell27"><span></span>--coverage_info<span class="w"> </span>&lt;none<span class="p">|</span>basic<span class="p">|</span>advanced&gt;
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell27">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p><strong>What does it do?</strong>
This option enables .sol and .spec coverage analysis and visualization.  The <code class="docutils literal notranslate"><span class="pre">--coverage_info</span></code> option may
be followed by one of <code class="docutils literal notranslate"><span class="pre">none</span></code>, <code class="docutils literal notranslate"><span class="pre">basic</span></code>, or <code class="docutils literal notranslate"><span class="pre">advanced</span></code>;
See <a class="reference internal" href="../checking/coverage-info.html"><span class="doc">Coverage Info</span></a> for more information about the analysis.</p>
<p><strong>When to use it?</strong>
We suggest using this option when you have finished (a subset of) your rules and the prover verified them. The analysis tells you which parts of the solidity input are covered by the rules, and also which parts of the rules are actually needed to prove the rules.</p>
<p><strong>Example</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell28"><span></span>certoraRun<span class="w"> </span>Bank.sol<span class="w"> </span>--verify<span class="w"> </span>Bank:Bank.spec<span class="w"> </span>--coverage_info<span class="w"> </span>advanced
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell28">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
<section id="foundry">
<span id="id10"></span><h2><a class="toc-backref" href="#id77" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">foundry</span></code></a><a class="headerlink" href="#foundry" title="Link to this heading"></a></h2>
<p><strong>What does it do?</strong>
Collects all test files in the project (files ending with <code class="docutils literal notranslate"><span class="pre">.t.sol</span></code>), and runs
the <a class="reference internal" href="../../cvl/foundry-integration.html#foundry-integration"><span class="std std-ref">Foundry Integration (Alpha)</span></a> on them (specifically, the
<code class="docutils literal notranslate"><span class="pre">verifyFoundryFuzzTestsNoRevert</span></code> builtin rule). As with the
<a class="reference internal" href="#project-sanity"><span class="std std-ref">project_sanity</span></a> option, the search is over files in the current git
repository if such exists, otherwise over all files in the tree under the
current working directory.</p>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>This option implicitly enables the <a class="reference internal" href="#auto-dispatcher"><span class="std std-ref">auto_dispatcher</span></a> option.</p>
</div>
<p><strong>When to use it?</strong>
When we want to run all Foundry fuzz tests in the project with the Prover.</p>
<p><strong>Example</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell29"><span></span>certoraRun<span class="w"> </span>--foundry
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell29">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
<section id="independent-satisfy">
<span id="id11"></span><h2><a class="toc-backref" href="#id78" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">independent_satisfy</span></code></a><a class="headerlink" href="#independent-satisfy" title="Link to this heading"></a></h2>
<p><strong>What does it do?</strong>
The independent satisfy mode checks each <a class="reference internal" href="../../cvl/statements.html#satisfy"><span class="std std-ref">satisfy statement</span></a> independently from all other satisfy statements that occurs in a rule.
Normally, each satisfy statement will be turned into a sub-rule (similarly to the <a class="reference internal" href="#multi-assert-check"><span class="std std-ref">multi_assert_check</span></a> mode),
but previously encountered satisfy statements will be still considered when creating a satisfying assignment.</p>
<p>As an illustrative example of the default mode, consider the following rule <code class="docutils literal notranslate"><span class="pre">R</span></code> that has two satisfy statements:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell30"><span></span><span class="k">rule</span><span class="w"> </span><span class="nc">R</span><span class="w"> </span><span class="p">{</span>
<span class="w">  </span><span class="kt">bool</span><span class="w"> </span>b<span class="p">;</span>
<span class="w">  </span><span class="kr">satisfy</span><span class="w"> </span>b<span class="p">,</span><span class="w"> </span><span class="s2">"R1"</span><span class="p">;</span>
<span class="w">  </span><span class="kr">satisfy</span><span class="w"> </span><span class="o">!</span>b<span class="p">,</span><span class="w"> </span><span class="s2">"R2"</span><span class="p">;</span>
<span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell30">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>The statements for “R1” and “R2” will actually create two sub-rules equivalent to:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell31"><span></span><span class="k">rule</span><span class="w"> </span><span class="nc">R1_default</span><span class="w"> </span><span class="p">{</span>
<span class="w">  </span><span class="kt">bool</span><span class="w"> </span>b<span class="p">;</span>
<span class="w">  </span><span class="kr">satisfy</span><span class="w"> </span>b<span class="p">,</span><span class="w"> </span><span class="s2">"R1"</span><span class="p">;</span>
<span class="p">}</span>

<span class="k">rule</span><span class="w"> </span><span class="nc">R2_default</span><span class="w"> </span><span class="p">{</span>
<span class="w">  </span><span class="kt">bool</span><span class="w"> </span>b<span class="p">;</span>
<span class="w">  </span><span class="c1">// Previous satisfy statements are required in default mode.</span>
<span class="w">  </span><span class="kr">require</span><span class="w"> </span>b<span class="p">;</span><span class="w"> </span><span class="c1">// R1</span>
<span class="w">  </span><span class="c1">// Due to requiring `b`, this satisfy statement is equivalent to 'satisfy b &amp;&amp; !b, "R2";'</span>
<span class="w">  </span><span class="kr">satisfy</span><span class="w"> </span><span class="o">!</span>b<span class="p">,</span><span class="w"> </span><span class="s2">"R2"</span><span class="p">;</span>
<span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell31">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>Without turning <code class="docutils literal notranslate"><span class="pre">independent_satisfy</span></code> mode on, <code class="docutils literal notranslate"><span class="pre">R2</span></code> would have failed, as it would try to satisfy <code class="docutils literal notranslate"><span class="pre">b</span> <span class="pre">&amp;&amp;</span> <span class="pre">!b</span></code>, an unsatisfiable contradiction.
Turning on the <code class="docutils literal notranslate"><span class="pre">independent_satisfy</span></code> mode will ignore all currently unchecked satisfy statements for each sub-rule.
It would also generate and check two sub-rules, but with a slight difference: <code class="docutils literal notranslate"><span class="pre">R1</span></code> where&nbsp;<code class="docutils literal notranslate"><span class="pre">b</span></code>&nbsp;is satisfied (by <code class="docutils literal notranslate"><span class="pre">b=true</span></code>) while <code class="docutils literal notranslate"><span class="pre">satisfy</span> <span class="pre">!b</span></code> is removed, and <code class="docutils literal notranslate"><span class="pre">R2</span></code> where <code class="docutils literal notranslate"><span class="pre">satisfy</span> <span class="pre">b</span></code> is removed, and&nbsp;<code class="docutils literal notranslate"><span class="pre">!b</span></code>&nbsp;is satisfied (by <code class="docutils literal notranslate"><span class="pre">b=false</span></code>).</p>
<p>The two <code class="docutils literal notranslate"><span class="pre">independent_satisfy</span></code> generated sub-rules will be equivalent to:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell32"><span></span><span class="k">rule</span><span class="w"> </span><span class="nc">R1_independent</span><span class="w"> </span><span class="p">{</span>
<span class="w">  </span><span class="kt">bool</span><span class="w"> </span>b<span class="p">;</span>
<span class="w">  </span><span class="kr">satisfy</span><span class="w"> </span>b<span class="p">,</span><span class="w"> </span><span class="s2">"R1"</span><span class="p">;</span>
<span class="p">}</span>

<span class="k">rule</span><span class="w"> </span><span class="nc">R2_independent</span><span class="w"> </span><span class="p">{</span>
<span class="w">  </span><span class="kt">bool</span><span class="w"> </span>b<span class="p">;</span>
<span class="w">  </span><span class="c1">// require b;</span>
<span class="w">  </span><span class="kr">satisfy</span><span class="w"> </span><span class="o">!</span>b<span class="p">,</span><span class="w"> </span><span class="s2">"R2"</span><span class="p">;</span>
<span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell32">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p><strong>When to use it?</strong>
When you have a rule with multiple satisfy statements, and you would like to demonstrate each statement separately.</p>
<p><strong>Example</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell33"><span></span>certoraRun<span class="w"> </span>Bank.sol<span class="w"> </span>--verify<span class="w"> </span>Bank:Bank.spec<span class="w"> </span>--independent_satisfy
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell33">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
<section id="multi-assert-check">
<span id="id12"></span><h2><a class="toc-backref" href="#id79" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">multi_assert_check</span></code></a><a class="headerlink" href="#multi-assert-check" title="Link to this heading"></a></h2>
<p><strong>What does it do?</strong>
This mode checks each assertion statement that occurs in a rule, separately. The check is done by decomposing each rule into multiple sub-rules, each of which checks one assertion, while it assumes all preceding assertions. In addition, all assertions that originate from the Solidity code (as opposed to those from the specification), are checked together by a designated, single sub-rule.</p>
<p>As an illustrative example, consider the following rule <code class="docutils literal notranslate"><span class="pre">R</span></code> that has two assertions:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell34"><span></span><span class="p">...</span>
<span class="kr">assert</span><span class="w"> </span>a1
<span class="p">...</span>
<span class="kr">assert</span><span class="w"> </span>a2
<span class="p">...</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell34">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>The <code class="docutils literal notranslate"><span class="pre">multi_assert_check</span></code> mode would generate and check two sub-rules: <code class="docutils literal notranslate"><span class="pre">R1</span></code> where&nbsp;<code class="docutils literal notranslate"><span class="pre">a1</span></code>&nbsp;is proved while <code class="docutils literal notranslate"><span class="pre">a2</span></code> is removed, and <code class="docutils literal notranslate"><span class="pre">R2</span></code> where <code class="docutils literal notranslate"><span class="pre">a1</span></code> is assumed (i.e., transformed into a requirement statement), and&nbsp;<code class="docutils literal notranslate"><span class="pre">a2</span></code>&nbsp;is proved.</p>
<p><code class="docutils literal notranslate"><span class="pre">R</span></code> passes if and only if, <code class="docutils literal notranslate"><span class="pre">R1</span></code> and <code class="docutils literal notranslate"><span class="pre">R2</span></code> both pass. In particular, in case <code class="docutils literal notranslate"><span class="pre">R1</span></code> (resp. <code class="docutils literal notranslate"><span class="pre">R2</span></code>) fails, the counter-example shows a violation of <code class="docutils literal notranslate"><span class="pre">a1</span></code> (resp. <code class="docutils literal notranslate"><span class="pre">a2</span></code>).</p>
<div class="admonition caution">
<p class="admonition-title">Caution</p>
<p>We suggest using this mode carefully. In general, as this mode generates and checks more rules, it may lead to worse running-time performance. Please see indications for use below.</p>
</div>
<p><strong>When to use it?</strong>
When you have a rule with multiple assertions:</p>
<ol class="arabic simple">
<li><p>As a timeout mitigation strategy: checking each assertion separately may, in some cases, perform better than checking all the assertions together and consequently solve timeouts.</p></li>
<li><p>If you wish to get multiple counter-examples in a single run of the tool, where each counter-example violates a different assertion in the rule.</p></li>
</ol>
<p><strong>Example</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell35"><span></span>certoraRun<span class="w"> </span>Bank.sol<span class="w"> </span>--verify<span class="w"> </span>Bank:Bank.spec<span class="w"> </span>--multi_assert_check
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell35">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
<section id="multi-example">
<h2><a class="toc-backref" href="#id80" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">multi_example</span></code></a><a class="headerlink" href="#multi-example" title="Link to this heading"></a></h2>
<p>Show several counterexamples for failed assert statements and several witnesses for verified satisfy statements.</p>
<p><strong>What does it do?</strong>
By default, the Prover returns a single example per rule, either a counterexample (for assert violations) or a witness (for satisfy verification). When this flag is enabled, the Prover will attempt to generate multiple examples from different control-flow paths or logical reasons, offering a broader view of the rule’s behavior.</p>
<p><strong>When to use it?</strong>
Use this flag when debugging complex rules where multiple, distinct scenarios might lead to failure or success. Seeing several examples can help identify different edge cases and refine in the specification or implementation.</p>
<p><strong>Example</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell36"><span></span>certoraRun<span class="w"> </span>MyContract.sol<span class="w"> </span>--verify<span class="w"> </span>MyContract:MyContract.spec<span class="w"> </span>--multi_example
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell36">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
<section id="project-sanity">
<span id="id13"></span><h2><a class="toc-backref" href="#id81" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">project_sanity</span></code></a><a class="headerlink" href="#project-sanity" title="Link to this heading"></a></h2>
<p><strong>What does it do?</strong>
Runs the builtin sanity rule on all methods in the project. If the Prover is run
from within a git project, all <code class="docutils literal notranslate"><span class="pre">.sol</span></code> files in the in the git repository are added
to the scene and the <a class="reference internal" href="../../cvl/builtin.html#built-in-sanity"><span class="std std-ref">builtin sanity rule</span></a> is run on
them. Otherwise, <em>all</em> <code class="docutils literal notranslate"><span class="pre">.sol</span></code> files in the tree under the current working
directory are collected.</p>
<p>Alternatively, a list of files can be provided in the <code class="docutils literal notranslate"><span class="pre">.conf</span></code> file and then the
builtin sanity rule will run on all methods of the specified files.</p>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>This option implicitly enables the <a class="reference internal" href="#auto-dispatcher"><span class="std std-ref">auto_dispatcher</span></a> option.</p>
</div>
<p><strong>When to use it?</strong>
Mostly used as a first step when starting to work on a new project, in order to
“get a feeling” of the complexity of the project for the tool, and what methods
may be hot spots for summarization etc.</p>
<p><strong>Example</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell37"><span></span>certoraRun<span class="w"> </span>--project_sanity
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell37">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
<section id="rule-sanity">
<span id="id14"></span><h2><a class="toc-backref" href="#id82" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">rule_sanity</span></code></a><a class="headerlink" href="#rule-sanity" title="Link to this heading"></a></h2>
<p><strong>Usage</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell38"><span></span>--rule_sanity<span class="w"> </span>&lt;none<span class="p">|</span>basic<span class="p">|</span>advanced&gt;
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell38">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p><strong>What does it do?</strong>
This option enables sanity checking for rules.  The <code class="docutils literal notranslate"><span class="pre">--rule_sanity</span></code> option may
be followed by one of <code class="docutils literal notranslate"><span class="pre">none</span></code>, <code class="docutils literal notranslate"><span class="pre">basic</span></code>, or <code class="docutils literal notranslate"><span class="pre">advanced</span></code>;
See <a class="reference internal" href="../checking/sanity.html"><span class="doc">Rule Sanity Checks</span></a> for more information about sanity checks.</p>
<p><strong>When to use it?</strong>
We suggest using this option routinely while developing rules.  It is also a
useful check if you notice rules passing surprisingly quickly or easily.</p>
<p><strong>Example</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell39"><span></span>certoraRun<span class="w"> </span>Bank.sol<span class="w"> </span>--verify<span class="w"> </span>Bank:Bank.spec<span class="w"> </span>--rule_sanity<span class="w"> </span>basic
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell39">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
<section id="short-output">
<span id="id15"></span><h2><a class="toc-backref" href="#id83" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">short_output</span></code></a><a class="headerlink" href="#short-output" title="Link to this heading"></a></h2>
<p><strong>What does it do?</strong>
Reduces the verbosity of the tool.</p>
<p><strong>When to use it?</strong>
When we do not care much for the output. It is recommended when running the tool in continuous integration.</p>
<p><strong>Example</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell40"><span></span>certoraRun<span class="w"> </span>Bank.sol<span class="w"> </span>--verify<span class="w"> </span>Bank:Bank.spec<span class="w"> </span>--short_output
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell40">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
</section>
<section id="options-that-control-the-solidity-compiler">
<h1><a class="toc-backref" href="#id84" role="doc-backlink">Options that control the Solidity compiler</a><a class="headerlink" href="#options-that-control-the-solidity-compiler" title="Link to this heading"></a></h1>
<section id="solc-map">
<span id="compiler-map"></span><span id="id16"></span><h2><a class="toc-backref" href="#id85" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">compiler_map</span></code></a><a class="headerlink" href="#solc-map" title="Link to this heading"></a></h2>
<p><strong>Usage</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell41"><span></span>--compiler_map<span class="w"> </span>&lt;contract&gt;<span class="o">=</span>&lt;version&gt;,...
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell41">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p><strong>What does it do?</strong>
Compiles every smart contract with a different compiler executable (Solidity version or Vyper). All used contracts must be listed.</p>
<p><strong>When to use it?</strong>
When different contracts have to be compiled for different Solidity versions.</p>
<p><strong>Example</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell42"><span></span>certoraRun<span class="w"> </span>Bank.sol<span class="w"> </span>Exchange.sol<span class="w"> </span>Token.vy<span class="w"> </span>--verify<span class="w"> </span>Bank:Bank.spec<span class="w"> </span>--compiler_map<span class="w"> </span><span class="nv">Bank</span><span class="o">=</span>solc4.25,Exchange<span class="o">=</span>solc6.7,Token<span class="o">=</span>vyper0.3.10
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell42">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
<section id="ignore-solidity-warnings">
<h2><a class="toc-backref" href="#id86" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">ignore_solidity_warnings</span></code></a><a class="headerlink" href="#ignore-solidity-warnings" title="Link to this heading"></a></h2>
<p><strong>What does it do?</strong>
This flag turns off the default behavior of treating certain Solidity compiler warnings as errors. When enabled, the tool will allow verification to proceed even if the Solidity compiler emits warnings.</p>
<p><strong>When to use it?</strong>
Use this flag if your contracts trigger non-critical compiler warnings you want to suppress during verification. This is especially useful for warnings irrelevant to formal verification or when using older code bases with known stylistic issues.</p>
<p>A common example is error 6321: <code class="docutils literal notranslate"><span class="pre">Unnamed</span> <span class="pre">return</span> <span class="pre">variable</span> <span class="pre">can</span> <span class="pre">remain</span> <span class="pre">unassigned</span></code>.
The Solidity compiler versions 0.7.6 and up emit this warning, which can be safely ignored in many contexts.</p>
<p><strong>Example</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell43"><span></span>certoraRun<span class="w"> </span>Token.sol<span class="w"> </span>--verify<span class="w"> </span>Token:Token.spec<span class="w"> </span>--ignore_solidity_warnings
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell43">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
<section id="packages">
<span id="id17"></span><h2><a class="toc-backref" href="#id87" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">packages</span></code></a><a class="headerlink" href="#packages" title="Link to this heading"></a></h2>
<p><strong>Usage</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell44"><span></span>--packages<span class="w"> </span>&lt;name&gt;<span class="o">=</span>&lt;path&gt;...
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell44">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p><strong>What does it do?</strong>
For each package, gets the path to a directory including that Solidity package.</p>
<p><strong>When to use it?</strong>
By default we look for the packages in <code class="docutils literal notranslate"><span class="pre">$NODE_PATH</span></code>. If there are packages are in several different directories, use <code class="docutils literal notranslate"><span class="pre">--packages</span></code>.</p>
<p><strong>Example</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell45"><span></span>certoraRun<span class="w"> </span>Bank.sol<span class="w"> </span>--verify<span class="w"> </span>Bank:Bank.spec<span class="w"> </span>--packages<span class="w"> </span>ds-stop<span class="o">=</span><span class="nv">$PWD</span>/lib/ds-token/lib/ds-stop/src<span class="w"> </span>ds-note<span class="o">=</span><span class="nv">$PWD</span>/lib/ds-token/lib/ds-stop/lib/ds-note/src
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell45">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>In Solidity projects, information about packages’ location is usually stored in <code class="docutils literal notranslate"><span class="pre">remappings.txt</span></code> file.</p>
</div>
</section>
<section id="packages-path">
<span id="id18"></span><h2><a class="toc-backref" href="#id88" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">packages_path</span></code></a><a class="headerlink" href="#packages-path" title="Link to this heading"></a></h2>
<p><strong>Usage</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell46"><span></span>--packages_path<span class="w"> </span>&lt;path&gt;
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell46">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p><strong>What does it do?</strong>
Gets the path to a directory including the Solidity packages.</p>
<p><strong>When to use it?</strong>
By default, we look for the packages in <code class="docutils literal notranslate"><span class="pre">$NODE_PATH</span></code>. If the packages are in any other directory, you must use <code class="docutils literal notranslate"><span class="pre">--packages_path</span></code>.</p>
<p><strong>Example</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell47"><span></span>certoraRun<span class="w"> </span>Bank.sol<span class="w"> </span>--verify<span class="w"> </span>Bank:Bank.spec<span class="w"> </span>--packages_path<span class="w"> </span>Solidity/packages
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell47">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
<section id="solc">
<span id="id19"></span><h2><a class="toc-backref" href="#id89" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">solc</span></code></a><a class="headerlink" href="#solc" title="Link to this heading"></a></h2>
<p><strong>Usage</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell48"><span></span>--solc<span class="w"> </span>&lt;solc_executable&gt;
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell48">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p><strong>What does it do?</strong>
This attribute tells the Prover which Solidity compiler to use. You may pass either:</p>
<ul class="simple">
<li><p>A full path to the compiler executable, e.g., <code class="docutils literal notranslate"><span class="pre">/usr/local/bin/solc8.19</span></code>, or</p></li>
<li><p>Just the executable’s name, e.g., <code class="docutils literal notranslate"><span class="pre">solc8.19</span></code>, in which case the tool will search for it in your system’s <code class="docutils literal notranslate"><span class="pre">$PATH</span></code>.</p></li>
</ul>
<p>This behavior mimics the shell’s resolution of commands (similar to how <code class="docutils literal notranslate"><span class="pre">which</span> <span class="pre">solc8.19</span></code> works).</p>
<p><strong>When to use it?</strong>
Use this option if your system has multiple Solidity versions installed and you want to select one explicitly. This is particularly useful when working with legacy contracts or caring about specific compiler version behaviors.</p>
<p><strong>Example</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell49"><span></span><span class="c1"># Use a compiler version from $PATH</span>
certoraRun<span class="w"> </span>Bank.sol<span class="w"> </span>--verify<span class="w"> </span>Bank:Bank.spec<span class="w"> </span>--solc<span class="w"> </span>solc8.19

<span class="c1"># Use full path to the compiler</span>
certoraRun<span class="w"> </span>Bank.sol<span class="w"> </span>--verify<span class="w"> </span>Bank:Bank.spec<span class="w"> </span>--solc<span class="w"> </span>/usr/local/bin/solc8.19
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell49">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
<section id="solc-allow-path">
<span id="id20"></span><h2><a class="toc-backref" href="#id90" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">solc_allow_path</span></code></a><a class="headerlink" href="#solc-allow-path" title="Link to this heading"></a></h2>
<p><strong>Usage</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell50"><span></span>--solc_allow_path<span class="w"> </span>&lt;path&gt;
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell50">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p><strong>What does it do?</strong>
Passes the value of this option as is to the solidity compiler’s option <code class="docutils literal notranslate"><span class="pre">--allow-paths</span></code>.
See <a class="reference external" href="https://docs.soliditylang.org/en/v0.8.16/path-resolution.html#allowed-paths">–allow-path specification</a></p>
<p><strong>When to use it?</strong>
When we want to add an additional location the Solidity compiler to load sources from</p>
<p><strong>Example</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell51"><span></span>certoraRun<span class="w"> </span>Bank.sol<span class="w"> </span>--verify<span class="w"> </span>Bank:Bank.spec<span class="w"> </span>--solc_allow_path<span class="w"> </span>~/Projects/Bank
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell51">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
<section id="solc-evm-version">
<span id="id21"></span><h2><a class="toc-backref" href="#id91" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">solc_evm_version</span></code></a><a class="headerlink" href="#solc-evm-version" title="Link to this heading"></a></h2>
<p><strong>Usage</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell52"><span></span>--solc_evm_version<span class="w"> </span>&lt;version&gt;
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell52">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p><strong>What does it do?</strong>
Passes the value of this option  to the solidity compiler’s option <code class="docutils literal notranslate"><span class="pre">--evm-version</span></code>.</p>
<p><strong>When to use it?</strong>
When we want to select the Solidity compiler EVM version</p>
<p><strong>Example</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell53"><span></span>certoraRun<span class="w"> </span>Bank.sol<span class="w"> </span>--verify<span class="w"> </span>Bank:Bank.spec<span class="w"> </span>--solc_evm_version<span class="w"> </span>Istanbul
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell53">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
<section id="solc-evm-version-map">
<span id="id22"></span><h2><a class="toc-backref" href="#id92" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">solc_evm_version_map</span></code></a><a class="headerlink" href="#solc-evm-version-map" title="Link to this heading"></a></h2>
<p><strong>Usage</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell54"><span></span>--solc_evm_version_map<span class="w"> </span>&lt;contract&gt;<span class="o">=</span>&lt;version&gt;,...
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell54">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p><strong>What does it do?</strong>
Set EVM version values when different files run with different EVM versions
Passes the value of this option as is to the solidity compiler’s option <code class="docutils literal notranslate"><span class="pre">--evm-version</span></code>.</p>
<p><strong>When to use it?</strong>
When different contracts have to be compiled with different Solidity EVM versions.</p>
<p><strong>Example</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell55"><span></span>certoraRun<span class="w"> </span>Bank.sol<span class="w"> </span>--verify<span class="w"> </span>Bank:Bank.spec<span class="w"> </span>--solc_evm_version_map<span class="w"> </span><span class="nv">Bank</span><span class="o">=</span>prague,Exchange<span class="o">=</span>cancun
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell55">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
<section id="solc-optimize">
<span id="id23"></span><h2><a class="toc-backref" href="#id93" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">solc_optimize</span></code></a><a class="headerlink" href="#solc-optimize" title="Link to this heading"></a></h2>
<p><strong>Usage</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell56"><span></span>--solc_optimize<span class="w"> </span>&lt;n&gt;
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell56">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p><strong>What does it do?</strong>
Passes the value of this option as is to the solidity compiler’s option <code class="docutils literal notranslate"><span class="pre">--optimize</span></code> and <code class="docutils literal notranslate"><span class="pre">--optimize-runs</span></code>.</p>
<p><strong>When to use it?</strong>
When we want to activate in the solidity compiler the opcode-based optimizer for the generated bytecode and control the
number of times the optimizer will be activated (if no value is set, the compiler’s default is 200 runs)</p>
<p><strong>Example</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell57"><span></span>certoraRun<span class="w"> </span>Bank.sol<span class="w"> </span>--verify<span class="w"> </span>Bank:Bank.spec<span class="w"> </span>--solc_optimize<span class="w"> </span><span class="m">300</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell57">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
<section id="solc-optimize-map">
<span id="id24"></span><h2><a class="toc-backref" href="#id94" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">solc_optimize_map</span></code></a><a class="headerlink" href="#solc-optimize-map" title="Link to this heading"></a></h2>
<p><strong>Usage</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell58"><span></span>--solc_optimize_map<span class="w"> </span>&lt;contract&gt;<span class="o">=</span>&lt;n&gt;,...
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell58">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p><strong>What does it do?</strong>
Set optimize values when different files run with different number of runs
Passes the value of this option as is to the solidity compiler’s option <code class="docutils literal notranslate"><span class="pre">--optimize</span></code> and <code class="docutils literal notranslate"><span class="pre">--optimize-runs</span></code>.</p>
<p><strong>When to use it?</strong>
When we want to activate in the solidity compiler the opcode-based optimizer for the generated bytecode and control the
number of times the optimizer will be activated (if no value is set, the compiler’s default is 200 runs)</p>
<p><strong>Example</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell59"><span></span>certoraRun<span class="w"> </span>Bank.sol<span class="w"> </span>--verify<span class="w"> </span>Bank:Bank.spec<span class="w"> </span>--solc_optimize_map<span class="w"> </span><span class="nv">Bank</span><span class="o">=</span><span class="m">200</span>,Exchange<span class="o">=</span><span class="m">300</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell59">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
<section id="solc-via-ir">
<span id="id25"></span><h2><a class="toc-backref" href="#id95" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">solc_via_ir</span></code></a><a class="headerlink" href="#solc-via-ir" title="Link to this heading"></a></h2>
<p><strong>What does it do?</strong>
Passes the value of this option  to the solidity compiler’s option <code class="docutils literal notranslate"><span class="pre">--via-ir</span></code>.</p>
<p><strong>When to use it?</strong>
When we want to enable the IR-based code generator</p>
<p><strong>Example</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell60"><span></span>certoraRun<span class="w"> </span>Bank.sol<span class="w"> </span>--verify<span class="w"> </span>Bank:Bank.spec<span class="w"> </span>--solc_via_ir
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell60">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
<section id="solc-via-ir-map">
<h2><a class="toc-backref" href="#id96" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">solc_via_ir_map</span></code></a><a class="headerlink" href="#solc-via-ir-map" title="Link to this heading"></a></h2>
<p><strong>Usage</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell61"><span></span>--solc_via_ir_map<span class="w"> </span>&lt;contract&gt;<span class="o">=</span>&lt;true<span class="p">|</span>false&gt;,...
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell61">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p><strong>What does it do?</strong>
This flag configures whether the Solidity compiler should enable the IR-based code generator per contract. It allows different contracts in the same project to be compiled with or without the <code class="docutils literal notranslate"><span class="pre">via-ir</span></code> option. This overrides <a class="reference internal" href="#solc-via-ir"><span class="std std-ref">solc_via_ir</span></a> on a per-contract basis.</p>
<p><strong>When to use it?</strong>
Use this when different contracts require different compilation pipelines. For instance, if one contract benefits from the IR pipeline (e.g., improved output or different optimization behavior) but another fails to compile with the IR pipeline, this flag lets you mix modes safely.</p>
<p><strong>Note</strong>
If <a class="reference internal" href="#solc-via-ir"><span class="std std-ref">solc_via_ir</span></a> is not set globally, no contracts will be compiled <code class="docutils literal notranslate"><span class="pre">via-ir</span></code> unless explicitly specified in this map.</p>
<p><strong>Example</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell62"><span></span>certoraRun<span class="w"> </span>A.sol<span class="w"> </span>B.sol<span class="w"> </span>--verify<span class="w"> </span>A:A.spec<span class="w"> </span><span class="se">\</span>
<span class="w">  </span>--solc_via_ir_map<span class="w"> </span><span class="nv">A</span><span class="o">=</span>true,B<span class="o">=</span><span class="nb">false</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell62">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>In this example, contract A is compiled with the <code class="docutils literal notranslate"><span class="pre">--via-ir</span></code> flag, while contract B is compiled without it.</p>
</section>
<section id="vyper">
<h2><a class="toc-backref" href="#id97" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">vyper</span></code></a><a class="headerlink" href="#vyper" title="Link to this heading"></a></h2>
<p><strong>Usage</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell63"><span></span>--vyper<span class="w"> </span>&lt;vyper_executable&gt;
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell63">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p><strong>What does it do?</strong>
This attribute tells the Prover which Vyper compiler to use. You may pass either:</p>
<ul class="simple">
<li><p>A full path to the compiler executable, e.g., <code class="docutils literal notranslate"><span class="pre">/usr/local/bin/vyper0.3.10</span></code>, or</p></li>
<li><p>Just the executable’s name, e.g., <code class="docutils literal notranslate"><span class="pre">vyper0.3.10</span></code>, in which case the tool will search for it in your system’s <code class="docutils literal notranslate"><span class="pre">$PATH</span></code>.</p></li>
</ul>
<p>This behavior mimics the shell’s resolution of commands (similar to how <code class="docutils literal notranslate"><span class="pre">which</span> <span class="pre">vyper0.3.10</span></code> works).</p>
<p><strong>When to use it?</strong>
Use this option if your system has multiple Vyper versions installed and you want to select one explicitly. This is particularly useful when working with legacy contracts or caring about specific compiler version behaviors.</p>
<p><strong>Example</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell64"><span></span><span class="c1"># Use a compiler version from $PATH</span>
certoraRun<span class="w"> </span>Bank.sol<span class="w"> </span>--verify<span class="w"> </span>Bank:Bank.spec<span class="w"> </span>--vyper<span class="w"> </span>vyper0.3.10

<span class="c1"># Use full path to the compiler</span>
certoraRun<span class="w"> </span>Bank.sol<span class="w"> </span>--verify<span class="w"> </span>Bank:Bank.spec<span class="w"> </span>--vyper<span class="w"> </span>/usr/local/bin/vyper0.3.10
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell64">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
</section>
<section id="options-regarding-source-code-loops">
<h1><a class="toc-backref" href="#id98" role="doc-backlink">Options regarding source code loops</a><a class="headerlink" href="#options-regarding-source-code-loops" title="Link to this heading"></a></h1>
<section id="loop-iter">
<span id="id26"></span><h2><a class="toc-backref" href="#id99" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">loop_iter</span></code></a><a class="headerlink" href="#loop-iter" title="Link to this heading"></a></h2>
<p><strong>Usage</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell65"><span></span>--loop_iter<span class="w"> </span>&lt;n&gt;
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell65">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p><strong>What does it do?</strong>
Sets the maximal number of loop iterations we verify for. The way the Certora Prover handles loops is by unrolling them - if the loop should be executed three times, it will copy the code inside the loop three times. This option sets the number of unrolls. Be aware that the run time grows exponentially by the number of loop iterations.</p>
<p><strong>When to use it?</strong>
The default number of loop iterations we unroll is one. However, in many cases, bugs only occur when there are several iterations. Common scenarios include iteration over list elements. Two, or in some cases three, is usually the most you will ever need to uncover bugs.</p>
<p><strong>Example</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell66"><span></span>certoraRun<span class="w"> </span>Bank.sol<span class="w"> </span>--verify<span class="w"> </span>Bank:Bank.spec<span class="w"> </span>--loop_iter<span class="w"> </span><span class="m">2</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell66">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
<section id="optimistic-loop">
<span id="id27"></span><h2><a class="toc-backref" href="#id100" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">optimistic_loop</span></code></a><a class="headerlink" href="#optimistic-loop" title="Link to this heading"></a></h2>
<p><strong>What does it do?</strong>
The Certora Prover unrolls loops - if the loop should be executed three times, it will copy the code inside the loop three times. After we finish the loop’s iterations, we add an assertion to verify we have actually finished running the loop. For example, in a <code class="docutils literal notranslate"><span class="pre">while</span> <span class="pre">(a</span> <span class="pre">&lt;</span> <span class="pre">b)</span></code> loop, after the loop’s unrolling, we add <code class="docutils literal notranslate"><span class="pre">assert</span> <span class="pre">a</span> <span class="pre">&gt;=</span> <span class="pre">b</span></code>. We call this assertion the <em>loop unwind condition</em>.
This option changes the assertions of the loop unwind condition to requirements (in the case above <code class="docutils literal notranslate"><span class="pre">require</span> <span class="pre">a</span> <span class="pre">&gt;=</span> <span class="pre">b</span></code>). That means, we ignore all the cases where the loop unwind condition does not hold, instead of considering them as a failure.</p>
<p><strong>When to use it?</strong>
When you have loops in your code and are getting a counterexample labeled <code class="docutils literal notranslate"><span class="pre">loop</span> <span class="pre">unwind</span> <span class="pre">condition</span></code>. In general, you need this flag whenever the number of loop iterations varies. It is usually a necessity if using <a class="reference internal" href="#loop-iter"><span class="std std-ref">loop_iter</span></a>.</p>
<div class="admonition caution">
<p class="admonition-title">Caution</p>
<p><code class="docutils literal notranslate"><span class="pre">--optimistic_loop</span></code> could cause <a class="reference internal" href="#rule-sanity"><span class="std std-ref">vacuous rules</span></a>.</p>
</div>
<p><strong>Example</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell67"><span></span>certoraRun<span class="w"> </span>Bank.sol<span class="w"> </span>--verify<span class="w"> </span>Bank:Bank.spec<span class="w"> </span>--optimistic_loop
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell67">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
</section>
<section id="options-regarding-summarization">
<h1><a class="toc-backref" href="#id101" role="doc-backlink">Options regarding summarization</a><a class="headerlink" href="#options-regarding-summarization" title="Link to this heading"></a></h1>
<section id="auto-dispatcher">
<span id="id28"></span><h2><a class="toc-backref" href="#id102" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">auto_dispatcher</span></code></a><a class="headerlink" href="#auto-dispatcher" title="Link to this heading"></a></h2>
<p><strong>What does it do?</strong>
In case a call’s callee cannot be precomputed but the called method’s sighash
can be (e.g. <code class="docutils literal notranslate"><span class="pre">MyInterface(addr).foo()</span></code> in solidity, where <code class="docutils literal notranslate"><span class="pre">addr</span></code> is some
<code class="docutils literal notranslate"><span class="pre">address</span></code> typed variable), the default behavior of the Prover in this case is to
Havoc. In this case the user can specify a <a class="reference internal" href="../../cvl/methods.html#dispatcher"><span class="std std-ref">DISPATCHER summaries</span></a> summary in the
<a class="reference internal" href="../../cvl/methods.html#methods-block"><span class="std std-ref">The Methods Block</span></a> so that the prover will inline all methods in the scene
that have this sighash.</p>
<p>This option will cause all such unknown callee with known sighash cases to behave
as if an <code class="docutils literal notranslate"><span class="pre">DISPATCHER(optimistic=true)</span></code> was added for that method in the methods
block.</p>
<p>One important difference from manually placing the <code class="docutils literal notranslate"><span class="pre">DISPATCHER</span></code> summary in the
methods block is that when it’s manually written there with <code class="docutils literal notranslate"><span class="pre">optimistic=true</span></code>
and no such function is found in the scene the Prover will exit with an error,
but when using the flag it will fall back to the default havoc.</p>
<p><strong>When to use it?</strong>
When there are many unresolved callee methods, or as a first step to solve
call resolution failures.</p>
<p><strong>Example</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell68"><span></span>certoraRun<span class="w"> </span>Bank.sol<span class="w"> </span>--verify<span class="w"> </span>Bank:Bank.spec<span class="w"> </span>--auto_dispatcher
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell68">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
<section id="nondet-difficult-funcs">
<span id="id29"></span><h2><a class="toc-backref" href="#id103" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">nondet_difficult_funcs</span></code></a><a class="headerlink" href="#nondet-difficult-funcs" title="Link to this heading"></a></h2>
<p><strong>What does it do?</strong>
When this option is set, the Prover will auto-summarize
view or pure internal functions that return a value type and are
currently not summarized, and that are found to be heuristically difficult
for the Prover.</p>
<p>For more information, see <a class="reference internal" href="../../user-guide/out-of-resources/timeout.html#detect-candidates-for-summarization"><span class="std std-ref">Detect candidates for summarization</span></a>.</p>
<p><strong>When to use it?</strong>
Using this option is recommended when beginning to work on a large code
base that includes functions that could be difficult for the Prover.
It can help the user get faster feedback, both in the form of faster
verification results, as well as highlighting potentially difficult functions.</p>
<p><strong>Example</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell69"><span></span>certoraRun<span class="w"> </span>Bank.sol<span class="w"> </span>--verify<span class="w"> </span>Bank:Bank.spec<span class="w"> </span>--nondet_difficult_funcs
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell69">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
<section id="nondet-minimal-difficulty">
<span id="id30"></span><h2><a class="toc-backref" href="#id104" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">nondet_minimal_difficulty</span></code></a><a class="headerlink" href="#nondet-minimal-difficulty" title="Link to this heading"></a></h2>
<p><strong>Usage</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell70"><span></span>--nondet_minimal_difficulty<span class="w"> </span>&lt;n&gt;
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell70">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p><strong>What does it do?</strong>
This option sets the minimal difficulty threshold for the auto-summarization mode enabled by <a class="reference internal" href="#nondet-difficult-funcs"><span class="std std-ref">nondet_difficult_funcs</span></a>.</p>
<p><strong>When to use it?</strong>
If the results of an initial run with <a class="reference internal" href="#nondet-difficult-funcs"><span class="std std-ref">nondet_difficult_funcs</span></a> were unsatisfactory,
one can adjust the default threshold to apply the auto-summarization to potentially more or fewer internal functions.</p>
<p>The notification in the rule report that contains the applied summaries will present the current threshold used by the Prover.</p>
<p><strong>Example</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell71"><span></span>certoraRun<span class="w"> </span>Bank.sol<span class="w"> </span>--verify<span class="w"> </span>Bank:Bank.spec<span class="w"> </span>--nondet_difficult_funcs<span class="w"> </span>--nondet_minimal_difficulty<span class="w"> </span><span class="m">20</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell71">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
<section id="optimistic-summary-recursion">
<span id="id31"></span><h2><a class="toc-backref" href="#id105" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">optimistic_summary_recursion</span></code></a><a class="headerlink" href="#optimistic-summary-recursion" title="Link to this heading"></a></h2>
<p><strong>What does it do?</strong>
In case there’s a call to some Solidity function within a summary, we may end up
with recursive calls to this summary. For example, if in the summary of <code class="docutils literal notranslate"><span class="pre">foo</span></code> we
call the Solidity function <code class="docutils literal notranslate"><span class="pre">bar</span></code>, and <code class="docutils literal notranslate"><span class="pre">bar</span></code>’s Solidity code contains a call to
<code class="docutils literal notranslate"><span class="pre">foo</span></code>, we’ll summarize <code class="docutils literal notranslate"><span class="pre">foo</span></code> again, which will lead to another call to <code class="docutils literal notranslate"><span class="pre">bar</span></code>
etc. In this case if this flag is set to <code class="docutils literal notranslate"><span class="pre">false</span></code> we may get an assertion failure
with a message along the lines of</p>
<div class="highlight-text notranslate"><div class="highlight"><pre id="codecell72"><span></span>Recursion limit (...) for calls to ..., reached during compilation of summary ...
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell72">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>Such recursion can also happen with <a class="reference internal" href="../../cvl/methods.html#dispatcher"><span class="std std-ref">dispatcher summaries</span></a> —
if a contract method <code class="docutils literal notranslate"><span class="pre">f</span></code> makes an unresolved external call to a different method
<code class="docutils literal notranslate"><span class="pre">f</span></code>, and if <code class="docutils literal notranslate"><span class="pre">f</span></code> is summarized with a <code class="docutils literal notranslate"><span class="pre">DISPATCHER</span></code> summary, then the Prover will
consider paths where <code class="docutils literal notranslate"><span class="pre">f</span></code> recursively calls itself. Without <code class="docutils literal notranslate"><span class="pre">--optimistic_summary_recursion</span></code>,
the Prover may report a rule violation with the following assert message:</p>
<div class="highlight-text notranslate"><div class="highlight"><pre id="codecell73"><span></span>When summarizing a call with dispatcher, found we already have it in the stack: ... consider removing its dispatcher summary.
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell73">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>The default behavior in this case is to assert that the recursion limit is not
reached (the limit is controlled by the <a class="reference internal" href="#summary-recursion-limit"><span class="std std-ref">summary_recursion_limit</span></a> flag).
With <code class="docutils literal notranslate"><span class="pre">--optimistic_summary_recursion</span></code>, the Prover will instead assume that the
limit is never reached.</p>
<p><strong>When to use it?</strong>
Use this flag when there is recursion due to summaries calling Solidity
functions, and this causes an undesired assertion failure. In this case one can
either make the limit larger (via <a class="reference internal" href="#summary-recursion-limit"><span class="std std-ref">summary_recursion_limit</span></a>) or set this
flag to <code class="docutils literal notranslate"><span class="pre">true</span></code>.</p>
<p><strong>Example</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell74"><span></span>certoraRun<span class="w"> </span>Bank.sol<span class="w"> </span>--verify<span class="w"> </span>Bank:Bank.spec<span class="w"> </span>--optimistic_summary_recursion
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell74">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<div class="admonition caution">
<p class="admonition-title">Caution</p>
<p>This flag could cause unsoundness - even if such recursion
<em>could</em> actually happen in the deployed contract, this code-path won’t be verified.</p>
</div>
</section>
<section id="summary-recursion-limit">
<span id="id32"></span><h2><a class="toc-backref" href="#id106" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">summary_recursion_limit</span></code></a><a class="headerlink" href="#summary-recursion-limit" title="Link to this heading"></a></h2>
<p><strong>Usage</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell75"><span></span>--summary_recursion_limit<span class="w"> </span>&lt;n&gt;
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell75">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p><strong>What does it do?</strong>
Summaries can cause recursion (see <a class="reference internal" href="#optimistic-summary-recursion"><span class="std std-ref">optimistic_summary_recursion</span></a>). This
option sets the summary recursion level, which is the number of recursive calls
that the Prover will consider.</p>
<p>If the Prover finds an execution in which a function is called recursively more
than the contract recursion limit, the Prover will report an assertion failure (unless
<a class="reference internal" href="#optimistic-summary-recursion"><span class="std std-ref">optimistic_summary_recursion</span></a> is set, in which case the execution
will be ignored).
The default value is zero (i.e. no recursion is allowed).</p>
<p><strong>When to use it?</strong></p>
<ol class="arabic simple">
<li><p>Use this option when there is recursion due to summaries calling Solidity
functions, and this leads to an assertion failure. In this case one can either
make the limit larger or set (via <a class="reference internal" href="#optimistic-summary-recursion"><span class="std std-ref">optimistic_summary_recursion</span></a>) flag
to <code class="docutils literal notranslate"><span class="pre">true</span></code>.</p></li>
<li><p>Use it if you get the following assertion failure, and disabling <a class="reference internal" href="#optimisticfallback"><span class="std std-ref">optimistic fallback</span></a> is not possible:</p></li>
</ol>
<div class="highlight-text notranslate"><div class="highlight"><pre id="codecell76"><span></span>When inlining a fallback function, found it was already on the stack. Consider disabling optimistic fallback mode.
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell76">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p><strong>Example</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell77"><span></span>certoraRun<span class="w"> </span>Bank.sol<span class="w"> </span>--verify<span class="w"> </span>Bank:Bank.spec<span class="w"> </span>--summary_recursion_limit<span class="w"> </span><span class="m">3</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell77">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
</section>
<section id="options-regarding-hashing-of-unbounded-data">
<h1><a class="toc-backref" href="#id107" role="doc-backlink">Options regarding hashing of unbounded data</a><a class="headerlink" href="#options-regarding-hashing-of-unbounded-data" title="Link to this heading"></a></h1>
<section id="optimistic-hashing">
<span id="id33"></span><h2><a class="toc-backref" href="#id108" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">optimistic_hashing</span></code></a><a class="headerlink" href="#optimistic-hashing" title="Link to this heading"></a></h2>
<p><strong>What does it do?</strong></p>
<p>When hashing data of potentially unbounded length (including unbounded arrays,
like <code class="docutils literal notranslate"><span class="pre">bytes</span></code>, <code class="docutils literal notranslate"><span class="pre">uint[]</span></code>, etc.):</p>
<ol class="arabic simple">
<li><p>If <code class="docutils literal notranslate"><span class="pre">optimistic_hashing</span></code> is set the Proves <em>assumes</em>
the data’s length is bounded by the <code class="docutils literal notranslate"><span class="pre">--hashing_length_bound</span></code> option.</p></li>
<li><p>If <code class="docutils literal notranslate"><span class="pre">optimistic_hashing</span></code> is not set, the Prover will check whether
the data’s length can exceed the <code class="docutils literal notranslate"><span class="pre">hashing_length_bound</span></code>, and report an
assertion violation if it can.</p></li>
</ol>
<p>See <a class="reference internal" href="../approx/hashing.html#hashing-unbounded"><span class="std std-ref">Hashing of unbounded data</span></a> for more details.</p>
<p><strong>When to use it?</strong></p>
<p>When the assertion regarding unbounded hashing is thrown, but it is acceptable for the Prover to ignore cases where the length hashed values exceeds the current bound.</p>
<p><strong>Example</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell78"><span></span>certoraRun<span class="w"> </span>Bank.sol<span class="w"> </span>--verify<span class="w"> </span>Bank:Bank.spec<span class="w"> </span>--optimistic_hashing
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell78">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
<section id="hashing-length-bound">
<span id="id34"></span><h2><a class="toc-backref" href="#id109" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">hashing_length_bound</span></code></a><a class="headerlink" href="#hashing-length-bound" title="Link to this heading"></a></h2>
<p><strong>Usage</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell79"><span></span>--hashing_length_bound<span class="w"> </span>&lt;n&gt;
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell79">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p><strong>What does it do?</strong></p>
<p>Constraint on the maximal length of otherwise unbounded data chunks that are being hashed. This constraint is either assumed or checked by the Prover, depending on whether <code class="docutils literal notranslate"><span class="pre">--optimistic_hashing</span></code> has been set. The bound is specified as a number of bytes.</p>
<p>The default value of this option is 224 (224 bytes correspond to 7 EVM machine words as 7 * 32 == 224).</p>
<p><strong>When to use it?</strong>
Reason to lower this value:</p>
<p>Lowering potentially improves SMT performance, especially if there are many occurrences of unbounded hashing in the program.</p>
<p>Reasons to raise this value:</p>
<ul class="simple">
<li><p>when <code class="docutils literal notranslate"><span class="pre">--optimistic_hashing</span></code> is not set: avoid the assertion being violated when the hashed values are actually bounded, but by a bound that is higher than the default value (in case of <code class="docutils literal notranslate"><span class="pre">--optimistic_hashing</span></code> being not set)</p></li>
<li><p>when <code class="docutils literal notranslate"><span class="pre">--optimistic_hashing</span></code> is set: find bugs that rely on a hashed array being at least of that length. (Optimistic hashing excludes all cases from the scope of verification where something being hashed is longer than this bound.)</p></li>
</ul>
<p><strong>Example</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell80"><span></span>certoraRun<span class="w"> </span>Bank.sol<span class="w"> </span>--verify<span class="w"> </span>Bank:Bank.spec<span class="w"> </span>--hashing_length_bound<span class="w"> </span><span class="m">128</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell80">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
</section>
<section id="options-that-help-reduce-the-running-time">
<h1><a class="toc-backref" href="#id110" role="doc-backlink">Options that help reduce the running time</a><a class="headerlink" href="#options-that-help-reduce-the-running-time" title="Link to this heading"></a></h1>
<section id="compilation-steps-only">
<span id="id35"></span><h2><a class="toc-backref" href="#id111" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">compilation_steps_only</span></code></a><a class="headerlink" href="#compilation-steps-only" title="Link to this heading"></a></h2>
<p><strong>What does it do?</strong>
Exits the program after source code and spec compilation without sending
a verification request to the cloud.</p>
<p><strong>When to use it?</strong>
Use it to check if the spec has correct syntax but do not wish
to send a verification request and wait for its results.</p>
<p>Here are a few example scenarios:</p>
<ol class="arabic simple">
<li><p>When writing hooks, ghosts, summaries, or CVL functions, you can verify the spec before continuing to write rules.</p></li>
<li><p>In CI, you can check CVL correctness after every PR but run the expensive and long verification only on nightly runs.</p></li>
<li><p>When you have no internet connection but still want to develop spec offline.</p></li>
</ol>
<p><strong>Example</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell81"><span></span>certoraRun<span class="w"> </span>Example.sol<span class="w"> </span>--verify<span class="w"> </span>Example:Example.spec<span class="w"> </span>--compilation_steps_only
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell81">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
<section id="disable-local-type-checking">
<h2><a class="toc-backref" href="#id112" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">disable_local_type_checking</span></code></a><a class="headerlink" href="#disable-local-type-checking" title="Link to this heading"></a></h2>
<p><strong>What does it do?</strong></p>
<p>This flag disables the local syntax and type checking of your CVL specifications before they are sent to the cloud for verification. When used, simple syntax or type errors will not be caught locally and will only become visible during the cloud run, potentially causing unnecessary delays and confusion.</p>
<p><strong>When to use it?</strong></p>
<p>This flag should only be used in rare cases when you believe the local syntax or type checking has produced an incorrect error, and you are confident that the specification is valid. Before using this flag, it is recommended to first attempt reinstalling the Prover by following the instructions in the <a class="reference internal" href="../../user-guide/install.html#installation"><span class="std std-ref">Installation</span></a> section. Using this flag is <strong>strongly discouraged</strong> as it bypasses an essential layer of error detection, increasing the likelihood of issues being encountered later during the verification process.</p>
<p><strong>Example</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell82"><span></span>certoraRun<span class="w"> </span>MyContract.sol<span class="w"> </span>--verify<span class="w"> </span>MyContract:MySpec<span class="w"> </span>--disable_local_typechecking
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell82">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<div class="admonition caution">
<p class="admonition-title">Caution</p>
<p>Avoid using this flag unless absolutely necessary. It is always better to fix syntax or type issues locally to ensure a smoother verification process.</p>
</div>
</section>
<section id="global-timeout">
<span id="id36"></span><h2><a class="toc-backref" href="#id113" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">global_timeout</span></code></a><a class="headerlink" href="#global-timeout" title="Link to this heading"></a></h2>
<p><strong>Usage</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell83"><span></span>--global_timeout<span class="w"> </span>&lt;seconds&gt;
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell83">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p><strong>What does it do?</strong></p>
<p>Sets the maximal timeout for the Prover.
Gets an integer input, which represents seconds.</p>
<p>The Certora Prover is bound to run a maximal time of 2 hours (7200 seconds).
Users may opt to set this number lower to facilitate faster iteration on specifications.
Values larger than two hours (7200 seconds) are ignored.</p>
<p>Jobs that exceed the global timeout will simply be terminated, so the result
reports may not be generated.</p>
<p>The global timeout is different from the <a class="reference internal" href="#smt-timeout"><span class="std std-ref">smt_timeout</span></a> option: the
<code class="docutils literal notranslate"><span class="pre">--smt_timeout</span></code> flag constrains the amount of time allocated to the processing
of each individual rule, while the <code class="docutils literal notranslate"><span class="pre">--global_timeout</span></code> flag constrains the
processing of the entire job, including static analysis and other
preprocessing.</p>
<p><strong>When to use it?</strong>
When running on just a few rules, or when willing to make faster iterations on specs without waiting too long for the entire set of rules to complete.</p>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>Even if in the shorter running time not all rules were processed, a second run may pull some results from cache, and therefore more results will be available.</p>
</div>
<p><strong>Example</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell84"><span></span>certoraRun<span class="w"> </span>Bank.sol<span class="w"> </span>--verify<span class="w"> </span>Bank:Bank.spec<span class="w"> </span>--global_timeout<span class="w"> </span><span class="m">60</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell84">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
<section id="id37">
<h2><a class="toc-backref" href="#id114" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">method</span></code></a><a class="headerlink" href="#id37" title="Link to this heading"></a></h2>
<p>See <a class="reference internal" href="#method"><span class="std std-ref">method</span></a></p>
</section>
<section id="smt-timeout">
<span id="id38"></span><h2><a class="toc-backref" href="#id115" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">smt_timeout</span></code></a><a class="headerlink" href="#smt-timeout" title="Link to this heading"></a></h2>
<p><strong>Usage</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell85"><span></span>--smt_timeout<span class="w"> </span>&lt;seconds&gt;
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell85">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p><strong>What does it do?</strong>
Sets the maximal timeout for all the
<a class="reference external" href="https://en.wikipedia.org/wiki/Satisfiability_modulo_theories">SMT solvers</a>.
Gets an integer input, which represents seconds.</p>
<p>The Certora Prover generates a logical formula from the specification and
source code. Then, it passes it on to an array of SMT solvers. The time it can
take for the SMT solvers to solve the equation is highly variable, and could
potentially be infinite. This is why they must be limited in run time.</p>
<p>The SMT timeout applies separately to each individual rule (or each method
for parametric rules). To set the global timeout, see <a class="reference internal" href="#global-timeout"><span class="std std-ref">global_timeout</span></a>.</p>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>While this is the most prominent timeout, this is not the only timeout that
applies to SMT solvers, for details see <a class="reference internal" href="#mediumtimeout"><span class="std std-ref">mediumTimeout</span></a> and
<a class="reference internal" href="../techniques/index.html#control-flow-splitting"><span class="std std-ref">Control flow splitting</span></a>.</p>
</div>
<p><strong>When to use it?</strong>
The default time out for the solvers is 300 seconds. There are two use cases for this option.
One is to decrease the timeout. This is useful for simple rules, that are solved quickly by the SMT solvers. Here, it is beneficial to reduce the timeout, so that when a new code breaks the specification, the tool will fail quickly. This is the more common use case.
The second use is when the solvers can prove the property, they just need more time. Usually, if the rule isn’t solved in 600 seconds, it will not be solved in 2,000 either. It is better to concentrate your efforts on simplifying the rule, the source code, add more summaries, or use other time-saving options. The prime causes for an increase of <code class="docutils literal notranslate"><span class="pre">--smt_timeout</span></code> are rules that are solved quickly, but time out when you add a small change, such as a requirement, or changing a strict inequality to a weak inequality.</p>
<p><strong>Example</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell86"><span></span>certoraRun<span class="w"> </span>Bank.sol<span class="w"> </span>--verify<span class="w"> </span>Bank:Bank.spec<span class="w"> </span>--smt_timeout<span class="w"> </span><span class="m">300</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell86">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
</section>
<section id="options-to-set-addresses-and-link-contracts">
<h1><a class="toc-backref" href="#id116" role="doc-backlink">Options to set addresses and link contracts</a><a class="headerlink" href="#options-to-set-addresses-and-link-contracts" title="Link to this heading"></a></h1>
<section id="address">
<span id="id39"></span><h2><a class="toc-backref" href="#id117" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">address</span></code></a><a class="headerlink" href="#address" title="Link to this heading"></a></h2>
<p><strong>Usage</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell87"><span></span>--address<span class="w"> </span>&lt;contract&gt;:&lt;address&gt;
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell87">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p><strong>What does it do?</strong>
Sets the address of a contract to a given address.</p>
<p><strong>When to use it?</strong>
When we have an external contract with a constant address. By default, the Python script assigns addresses as it sees fit to contracts.</p>
<p><strong>Example</strong></p>
<p>If we wish the <code class="docutils literal notranslate"><span class="pre">Oracle</span></code> contract to be at address 12, we use</p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell88"><span></span>certoraRun<span class="w"> </span>Bank.sol<span class="w"> </span>Oracle.sol<span class="w"> </span>--verify<span class="w"> </span>Bank:Bank.spec<span class="w"> </span>--address<span class="w"> </span>Oracle:12
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell88">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
<section id="contract-extensions">
<span id="id40"></span><h2><a class="toc-backref" href="#id118" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">contract_extensions</span></code></a><a class="headerlink" href="#contract-extensions" title="Link to this heading"></a></h2>
<p><strong>What does it do?</strong>
In order to support extendability and upgradeability of smart contracts, the proxy
pattern is used. In this patterns there is a base contract (the proxy) which delegate-calls
into “extension” contracts (read this
<a class="reference external" href="https://docs.openzeppelin.com/upgrades-plugins/1.x/proxies">explanation</a>
for more details).
This flag allows specifying that some contract is actually an extension of another one, to help the Prover
analyze low-level calls and resolve them correctly in this case.
In practice the Prover “moves” all the external function implementations from the
extension contract into the base contract, which means that to access them from CVL
one should use the <em>base</em> contract as the receiver, and not the extension contract.</p>
<p><strong>When to use it?</strong>
If you use the proxy pattern in your smart contracts.</p>
<p><strong>Example</strong>
Say we have a base contract <code class="docutils literal notranslate"><span class="pre">A</span></code> that uses an extension contract <code class="docutils literal notranslate"><span class="pre">B</span></code>.
Since in this pattern the storage of the two contracts may “overlap”, let’s also
assume they both have some <code class="docutils literal notranslate"><span class="pre">uint</span> <span class="pre">public</span> <span class="pre">n</span></code>.
In the .conf file one should add</p>
<div class="highlight-json notranslate"><div class="highlight"><pre id="codecell89"><span></span><span class="nt">"contract_extensions"</span><span class="p">:</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="nt">"A"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span>
<span class="w">        </span><span class="p">{</span>
<span class="w">            </span><span class="nt">"extension"</span><span class="p">:</span><span class="w"> </span><span class="s2">"B"</span><span class="p">,</span>
<span class="w">            </span><span class="nt">"exclude"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="s2">"n"</span><span class="p">]</span>
<span class="w">        </span><span class="p">}</span>
<span class="w">    </span><span class="p">]</span>
<span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell89">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>This tells the prover that <code class="docutils literal notranslate"><span class="pre">B</span></code> is an extension contract of <code class="docutils literal notranslate"><span class="pre">A</span></code>, but that it shouldn’t
“transfer” the getter for n from the extension into the base contract (since the base
contract already has such a function and this would cause a conflict).</p>
<p><a class="reference external" href="https://github.com/Certora/Examples/tree/master/CVLByExample/ExtensionContracts">For a more detailed example click here.</a></p>
</section>
<section id="contract-recursion-limit">
<span id="id41"></span><h2><a class="toc-backref" href="#id119" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">contract_recursion_limit</span></code></a><a class="headerlink" href="#contract-recursion-limit" title="Link to this heading"></a></h2>
<p><strong>Usage</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell90"><span></span>--contract_recursion_limit<span class="w"> </span>&lt;n&gt;
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell90">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p><strong>What does it do?</strong>
Contract inlining can cause recursion (see <a class="reference internal" href="#optimistic-contract-recursion"><span class="std std-ref">optimistic_contract_recursion</span></a>). This
option sets the contract recursion level, which is the number of recursive calls
that the Prover will consider when inlining contracts linked using, e.g., <code class="docutils literal notranslate"><span class="pre">--link</span></code> or <code class="docutils literal notranslate"><span class="pre">--struct_link</span></code>.</p>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>In this context, recursion refers to the state where the same <em>external</em> function
appears twice in the call stack.
Contracts can also exhibit recursive behavior due to recursive calls to <em>internal</em> functions,
which is unrelated to this option.</p>
</div>
<p>If a counterexample causes a function to be called recursively more than the
contract recursion limit, it will report an assertion failure (unless
<a class="reference internal" href="#optimistic-contract-recursion"><span class="std std-ref">optimistic_contract_recursion</span></a> is set, in which case the counterexample
will be ignored).
The default value is zero (i.e., no recursion is allowed).</p>
<p><strong>When to use it?</strong>
Use this option when after linking the resulting program may have paths
with recursive calls to external Solidity
functions, and this leads to a recursion-specific assertion failure,
showing the message <code class="docutils literal notranslate"><span class="pre">Contract</span> <span class="pre">recursion</span> <span class="pre">limit</span> <span class="pre">reached</span></code>.
In this case one can either
make the limit larger or set <code class="docutils literal notranslate"><span class="pre">--optimistic_contract_recursion</span></code> flag
to <code class="docutils literal notranslate"><span class="pre">true</span></code>.</p>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>Increasing the limit is not always sufficient,
as the code may in fact allow theoretically unbounded recursion.</p>
</div>
<p><strong>Example</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell91"><span></span>certoraRun<span class="w"> </span>Bank.sol<span class="w"> </span>--verify<span class="w"> </span>Bank:Bank.spec<span class="w"> </span>--contract_recursion_limit<span class="w"> </span><span class="m">3</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell91">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
<section id="link">
<span id="id42"></span><h2><a class="toc-backref" href="#id120" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">link</span></code></a><a class="headerlink" href="#link" title="Link to this heading"></a></h2>
<p><strong>Usage</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell92"><span></span>--struct_link<span class="w"> </span>&lt;contract&gt;:&lt;slot&gt;<span class="o">=</span>&lt;address&gt;
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell92">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p><strong>What does it do?</strong>
Links a slot in a contract with another contract.</p>
<p><strong>When to use it?</strong>
Many times a contract includes the address of another contract as one of its fields. If we do not use <code class="docutils literal notranslate"><span class="pre">--link</span></code>, it will be interpreted as any possible address, resulting in many nonsensical counterexamples.</p>
<p><strong>Example</strong>
Assume we have the contract <code class="docutils literal notranslate"><span class="pre">Bank.sol</span></code> with the following code snippet:
<code class="docutils literal notranslate"><span class="pre">IERC20</span> <span class="pre">public</span> <span class="pre">underlyingToken;</span></code></p>
<p>We have a contract <code class="docutils literal notranslate"><span class="pre">BankToken.sol</span></code>, and <code class="docutils literal notranslate"><span class="pre">underlyingToken</span></code> should be its address. To do that, we use:</p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell93"><span></span>certoraRun<span class="w"> </span>Bank.sol<span class="w"> </span>BankToken.sol<span class="w"> </span>--verify<span class="w"> </span>Bank:Bank.spec<span class="w"> </span>--link<span class="w"> </span>Bank:underlyingToken<span class="o">=</span>BankToken
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell93">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
<section id="optimistic-contract-recursion">
<span id="id43"></span><h2><a class="toc-backref" href="#id121" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">optimistic_contract_recursion</span></code></a><a class="headerlink" href="#optimistic-contract-recursion" title="Link to this heading"></a></h2>
<p><strong>What does it do?</strong>
Contract linking can cause recursion (see also <a class="reference internal" href="#contract-recursion-limit"><span class="std std-ref">contract_recursion_limit</span></a>).
This option sets the Prover to optimistically assume that recursion cannot go
beyond what is defined by <a class="reference internal" href="#contract-recursion-limit"><span class="std std-ref">contract_recursion_limit</span></a>,
but only if <a class="reference internal" href="#contract-recursion-limit"><span class="std std-ref">contract_recursion_limit</span></a> is set to a number higher than 0.</p>
<p><strong>When to use it?</strong></p>
<ol class="arabic simple">
<li><p>When the recursion due to contract linking is unbounded.</p></li>
<li><p>When we are interested only in a limited recursion depth due to contract linking.</p></li>
</ol>
<div class="admonition caution">
<p class="admonition-title">Caution</p>
<p>This flag could be another cause for unsoundness - even if such recursion
<em>could</em> actually happen in the deployed contract, this code-path won’t be verified
beyond the specified recursion limit (<a class="reference internal" href="#contract-recursion-limit"><span class="std std-ref">contract_recursion_limit</span></a>).</p>
</div>
<p><strong>Example</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell94"><span></span>certoraRun<span class="w"> </span>Bank.sol<span class="w"> </span>--verify<span class="w"> </span>Bank:Bank.spec<span class="w"> </span>--optimistic_contract_recursion<span class="w"> </span><span class="nb">true</span><span class="w"> </span>--contract_recursion_limit<span class="w"> </span><span class="m">1</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell94">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
<section id="optimistic-fallback">
<span id="optimisticfallback"></span><span id="id44"></span><h2><a class="toc-backref" href="#id122" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">optimistic_fallback</span></code></a><a class="headerlink" href="#optimistic-fallback" title="Link to this heading"></a></h2>
<p><strong>What does it do?</strong></p>
<p>This option controls how the Prover handles unresolved external calls with an empty input buffer (length 0). By default, such calls will havoc all storage state of external contracts. When <code class="docutils literal notranslate"><span class="pre">--optimistic_fallback</span></code> is enabled, these calls will instead:</p>
<ul class="simple">
<li><p>Execute the fallback function in the specified contract (if it exists).</p></li>
<li><p>Revert if no fallback function is available.</p></li>
<li><p>Execute a transfer if applicable.</p></li>
</ul>
<p>This modifies the behavior of <a class="reference internal" href="../../cvl/methods.html#auto-summary"><span class="std std-ref">AUTO summaries</span></a> by preventing unnecessary state havoc for empty input calls.</p>
<p><strong>When to use it?</strong></p>
<p>Enable this option to avoid spurious counter examples for external calls with empty input buffers.</p>
<p><strong>Example</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell95"><span></span>certoraRun<span class="w"> </span>Bank.sol<span class="w"> </span>--verify<span class="w"> </span>Bank:Bank.spec<span class="w"> </span>--optimistic_fallback
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell95">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
<section id="struct-link">
<span id="id45"></span><h2><a class="toc-backref" href="#id123" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">struct_link</span></code></a><a class="headerlink" href="#struct-link" title="Link to this heading"></a></h2>
<p><strong>Usage</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell96"><span></span>--struct_link<span class="w"> </span>&lt;contract&gt;:&lt;slot&gt;<span class="o">=</span>&lt;address&gt;
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell96">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p><strong>What does it do?</strong>
Links a slot in a struct with another contract. To do that you must calculate the slot number of the field you wish to replace.</p>
<p><strong>When to use it?</strong>
Many times a contract includes the address of another contract inside a field of one of its structs. If we do not use <code class="docutils literal notranslate"><span class="pre">--struct_link</span></code>, it will be interpreted as any possible address, resulting in many nonsensical counterexamples.</p>
<p><strong>Example</strong>
Assume we have the contract <code class="docutils literal notranslate"><span class="pre">Bank.sol</span></code> with the following code snippet:
<code class="docutils literal notranslate"><span class="pre">TokenPair</span> <span class="pre">public</span> <span class="pre">tokenPair;</span></code></p>
<p>Where <code class="docutils literal notranslate"><span class="pre">TokenPair</span></code> is</p>
<div class="highlight-solidity notranslate"><div class="highlight"><pre id="codecell97"><span></span><span class="kt">struct</span><span class="w"> </span><span class="nv">TokenPair</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span>IERC20<span class="w"> </span>tokenA<span class="p">;</span>
<span class="w">    </span>IERC20<span class="w"> </span>tokenB<span class="p">;</span>
<span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell97">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>We have two contracts <code class="docutils literal notranslate"><span class="pre">BankToken.sol</span></code> and <code class="docutils literal notranslate"><span class="pre">LoanToken.sol</span></code>. We want <code class="docutils literal notranslate"><span class="pre">tokenA</span></code> of the <code class="docutils literal notranslate"><span class="pre">tokenPair</span></code> to be <code class="docutils literal notranslate"><span class="pre">BankToken</span></code>, and <code class="docutils literal notranslate"><span class="pre">tokenB</span></code> to be <code class="docutils literal notranslate"><span class="pre">LoanToken</span></code>. Addresses take up only one slot. We assume <code class="docutils literal notranslate"><span class="pre">tokenPair</span></code> is the first field of Bank (so it starts at slot zero). To do that, we use:</p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell98"><span></span>certoraRun<span class="w"> </span>Bank.sol<span class="w"> </span>BankToken.sol<span class="w"> </span>LoanToken.sol<span class="w"> </span>--verify<span class="w"> </span>Bank:Bank.spec<span class="w"> </span>--struct_link<span class="w"> </span>Bank:0<span class="o">=</span>BankToken<span class="w"> </span>Bank:1<span class="o">=</span>LoanToken
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell98">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
</section>
<section id="options-for-job-metadata-and-dashboard-filtering">
<h1><a class="toc-backref" href="#id124" role="doc-backlink">Options for job metadata and dashboard filtering</a><a class="headerlink" href="#options-for-job-metadata-and-dashboard-filtering" title="Link to this heading"></a></h1>
<p>This section includes flags that annotate verification runs with additional metadata. These options don’t affect verification results but make it easier to track jobs, filter them in the <a class="reference external" href="https://prover.certora.com/">dashboard</a>, or manage runs across multiple protocols.</p>
<section id="id46">
<h2><a class="toc-backref" href="#id125" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">msg</span></code></a><a class="headerlink" href="#id46" title="Link to this heading"></a></h2>
<p>See <a class="reference internal" href="#msg"><span class="std std-ref">msg</span></a>.</p>
</section>
<section id="protocol-author">
<h2><a class="toc-backref" href="#id126" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">protocol_author</span></code></a><a class="headerlink" href="#protocol-author" title="Link to this heading"></a></h2>
<p><strong>Usage</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell99"><span></span>--protocol_author<span class="w"> </span>&lt;name&gt;
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell99">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p><strong>What does it do?</strong>
This option adds an author name to the job metadata, allowing you to filter or group verification runs by the protocol author in the <a class="reference external" href="https://prover.certora.com/">dashboard</a>.</p>
<p>If not explicitly provided, the Prover will attempt to extract the author from the author field in your <code class="docutils literal notranslate"><span class="pre">package.json</span></code> file (if it exists).</p>
<p><strong>When to use it?</strong>
Use this flag to help track who owns or has submitted each verification run, particularly in verification projects with multiple authors.</p>
<p><strong>Example</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell100"><span></span>certoraRun<span class="w"> </span>Bank.sol<span class="w"> </span>--verify<span class="w"> </span>Bank:Bank.spec<span class="w"> </span>--protocol_author<span class="w"> </span><span class="s2">"OpenDeFi Labs"</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell100">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
<section id="protocol-name">
<h2><a class="toc-backref" href="#id127" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">protocol_name</span></code></a><a class="headerlink" href="#protocol-name" title="Link to this heading"></a></h2>
<p><strong>Usage</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell101"><span></span>--protocol_name<span class="w"> </span>&lt;name&gt;
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell101">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p><strong>What does it do?</strong>
Sets the protocol name associated with the verification job. This name will appear in the <a class="reference external" href="https://prover.certora.com/">Prover dashboard</a> and can be used to filter or group related jobs. If this flag is not explicitly provided, the tool will attempt to use the name field from <code class="docutils literal notranslate"><span class="pre">package.json</span></code> if available.</p>
<p><strong>When to use it?</strong>
Use this flag to clearly label your jobs. This is especially useful when verifying multiple projects in parallel.</p>
<p><strong>Example</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell102"><span></span>certoraRun<span class="w"> </span>Vault.sol<span class="w"> </span>--verify<span class="w"> </span>Vault:Vault.spec<span class="w"> </span>--protocol_name<span class="w"> </span>MyDeFiProtocol
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell102">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
</section>
<section id="options-for-controlling-contract-creation">
<h1><a class="toc-backref" href="#id128" role="doc-backlink">Options for controlling contract creation</a><a class="headerlink" href="#options-for-controlling-contract-creation" title="Link to this heading"></a></h1>
<section id="dynamic-bound">
<span id="id47"></span><h2><a class="toc-backref" href="#id129" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">dynamic_bound</span></code></a><a class="headerlink" href="#dynamic-bound" title="Link to this heading"></a></h2>
<p><strong>Usage</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell103"><span></span>--dynamic_bound<span class="w"> </span>&lt;n&gt;
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell103">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p><strong>What does it do?</strong>
If set to zero (the default), contract creation (via the <code class="docutils literal notranslate"><span class="pre">new</span></code> statement or the <code class="docutils literal notranslate"><span class="pre">create</span></code>/<code class="docutils literal notranslate"><span class="pre">create2</span></code> instructions) will result in a havoc, like any other unresolved external call. If non-zero, then dynamic contract creation will be modeled with cloning, where each contract will be cloned at most n times.</p>
<p><strong>When to use it?</strong>
When you wish to model contract creation, that is, simulating the actual creation of the contract. Without it, <code class="docutils literal notranslate"><span class="pre">create</span></code> and <code class="docutils literal notranslate"><span class="pre">create2</span></code> commands simply return a fresh address; the Prover does not model their storage, code, constructors, immutables, etc. Any interaction with these generated addresses is modeled imprecisely with conservative havoc.</p>
<p><strong>Example</strong>
Suppose a contract <code class="docutils literal notranslate"><span class="pre">C</span></code> creates a new instance of a contract <code class="docutils literal notranslate"><span class="pre">Foo</span></code>, and you wish to inline the constructor of <code class="docutils literal notranslate"><span class="pre">Foo</span></code> at the creation site.</p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell104"><span></span>certoraRun<span class="w"> </span>C.sol<span class="w"> </span>Foo.sol<span class="w"> </span>--verify<span class="w"> </span>C:C.spec<span class="w"> </span>--dynamic_bound<span class="w"> </span><span class="m">1</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell104">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
<section id="dynamic-dispatch">
<span id="id48"></span><h2><a class="toc-backref" href="#id130" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">dynamic_dispatch</span></code></a><a class="headerlink" href="#dynamic-dispatch" title="Link to this heading"></a></h2>
<p><strong>What does it do?</strong>
By default, contract method invocations on newly created instances remain unresolved, requiring explicit <a class="reference internal" href="../../cvl/methods.html#dispatcher"><span class="std std-ref"> DISPATCHER</span></a> summaries for all such method calls.
With this option, the Prover will automatically apply the <code class="docutils literal notranslate"><span class="pre">DISPATCHER</span></code> summary on a best-effort basis for call sites where the receiver is proven to be a newly created contract.</p>
<p><strong>Limitations</strong></p>
<ul class="simple">
<li><p>This option only applies when the Prover can prove that the callee is a created contract.</p></li>
<li><p>If a contract instance is assigned from both a newly created contract and another source (e.g., storage), calls will remain unresolved. For example:</p></li>
</ul>
<div class="highlight-solidity notranslate"><div class="highlight"><pre id="codecell105"><span></span>MyFoo<span class="w"> </span>f<span class="p">;</span>
<span class="kt">if</span><span class="p">(</span><span class="o">*</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">   </span>f<span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="kt">new</span><span class="w"> </span>MyFoo<span class="p">(...);</span>
<span class="p">}</span><span class="w"> </span><span class="kt">else</span><span class="w"> </span><span class="p">{</span>
<span class="w">  </span>f<span class="w"> </span><span class="o">=</span><span class="w"> </span>storageStruct<span class="p">.</span>myFoo<span class="p">;</span>
<span class="p">}</span>
f<span class="p">.</span>bar<span class="p">();</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell105">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p><strong>When to use it?</strong>
Use this flag when you prefer not to manually add explicit <code class="docutils literal notranslate"><span class="pre">DISPATCHER</span></code> summaries for methods invoked by the created contract.</p>
<p><strong>Example</strong>
Suppose a contract <code class="docutils literal notranslate"><span class="pre">C</span></code> creates a new instance of a contract <code class="docutils literal notranslate"><span class="pre">Foo</span></code>, and you wish to inline the constructor of <code class="docutils literal notranslate"><span class="pre">Foo</span></code> at the creation site,
and <code class="docutils literal notranslate"><span class="pre">Foo</span></code> calls some method <code class="docutils literal notranslate"><span class="pre">m()</span></code> which you wish to automatically link to the newly created contract.</p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell106"><span></span>certoraRun<span class="w"> </span>C.sol<span class="w"> </span>Foo.sol<span class="w"> </span>--verify<span class="w"> </span>C:C.spec<span class="w"> </span>--dynamic_bound<span class="w"> </span><span class="m">1</span><span class="w"> </span>--dynamic_dispatch
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell106">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>You must also use the <a class="reference internal" href="#dynamic-bound"><span class="std std-ref">dynamic_bound</span></a> option.</p>
</div>
</section>
<section id="prototype">
<span id="id49"></span><h2><a class="toc-backref" href="#id131" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">prototype</span></code></a><a class="headerlink" href="#prototype" title="Link to this heading"></a></h2>
<p><strong>Usage</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell107"><span></span>--prototype<span class="w"> </span>&lt;hex<span class="w"> </span>string&gt;<span class="o">=</span>&lt;contract&gt;
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell107">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p><strong>What does it do?</strong>
Instructs the Prover to use a specific contract type for the return value from a call to <code class="docutils literal notranslate"><span class="pre">create</span></code> or <code class="docutils literal notranslate"><span class="pre">create2</span></code> on the given hexadecimal string as a prefix. The hexadecimal string represents proxy code that forwards calls to another contract. As we are using the prototype flag to skip calls to the proxy, no constructor code is being simulated for these contract creation resolutions.</p>
<p><strong>When to use it?</strong>
If you are verifying a contract creation that uses low level calls to <code class="docutils literal notranslate"><span class="pre">create</span></code> or <code class="docutils literal notranslate"><span class="pre">create2</span></code> for contract creation.</p>
<p><strong>Example</strong>
Suppose you have a contract <code class="docutils literal notranslate"><span class="pre">C</span></code> that creates another contract <code class="docutils literal notranslate"><span class="pre">Foo</span></code> like this:</p>
<div class="highlight-solidity notranslate"><div class="highlight"><pre id="codecell108"><span></span>assembly<span class="w"> </span><span class="p">{</span>
<span class="w">     </span>let<span class="w"> </span>ptr<span class="w"> </span><span class="o">:=</span><span class="w"> </span>mload<span class="p">(</span><span class="mh">0x40</span><span class="p">)</span>
<span class="w">     </span>mstore<span class="p">(</span>ptr<span class="p">,</span><span class="w"> </span><span class="mh">0x3d602d80600a3d3981f3363d3d373d3d3d363d73000000000000000000000000</span><span class="p">)</span>
<span class="w">     </span>mstore<span class="p">(</span>add<span class="p">(</span>ptr<span class="p">,</span><span class="w"> </span><span class="mh">0x14</span><span class="p">),</span><span class="w"> </span>shl<span class="p">(</span><span class="mh">0x60</span><span class="p">,</span><span class="w"> </span>implementation<span class="p">))</span>
<span class="w">     </span>mstore<span class="p">(</span>add<span class="p">(</span>ptr<span class="p">,</span><span class="w"> </span><span class="mh">0x28</span><span class="p">),</span><span class="w"> </span><span class="mh">0x5af43d82803e903d91602b57fd5bf30000000000000000000000000000000000</span><span class="p">)</span>
<span class="w">     </span>instance<span class="w"> </span><span class="o">:=</span><span class="w"> </span>create<span class="p">(</span><span class="m m-Decimal">0</span><span class="p">,</span><span class="w"> </span>ptr<span class="p">,</span><span class="w"> </span><span class="mh">0x37</span><span class="p">)</span>
<span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell108">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>Then you can set the string <code class="docutils literal notranslate"><span class="pre">3d602d80600a3d3981f3363d3d373d3d3d363d73</span></code> appearing in the first <code class="docutils literal notranslate"><span class="pre">mstore</span></code> after the <code class="docutils literal notranslate"><span class="pre">0x</span></code> prefix as a “prototype” for <code class="docutils literal notranslate"><span class="pre">Foo</span></code>.
The Prover will then be able to create a new instance of <code class="docutils literal notranslate"><span class="pre">Foo</span></code> at the point where the code creates it:</p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell109"><span></span>certoraRun<span class="w"> </span>C.sol<span class="w"> </span>Foo.sol<span class="w"> </span>--verify<span class="w"> </span>C:C.spec<span class="w"> </span>--prototype<span class="w"> </span><span class="nv">3d602d80600a3d3981f3363d3d373d3d3d363d73</span><span class="o">=</span>Foo<span class="w"> </span>--dynamic_bound<span class="w"> </span><span class="m">1</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell109">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>This argument has no effect if the <a class="reference internal" href="#dynamic-bound"><span class="std std-ref">dynamic bound</span></a> is zero.</p>
</div>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>The hex string must be:</p>
<ul class="simple">
<li><p>A strict prefix of the memory region passed to the create command.</p></li>
<li><p>Must be unique within each invocation of the tool.</p></li>
<li><p>Must not contain gaps, e.g., <code class="docutils literal notranslate"><span class="pre">3d602d80600a3d3981f3363d3d373d3d3d363d730000</span></code> in the above example will not work (those last four bytes will be overwritten) but <code class="docutils literal notranslate"><span class="pre">3d602d80600a3d3981f3363d3d373d3d3d363d</span></code> will.</p></li>
</ul>
</div>
</section>
</section>
<section id="version-options">
<h1><a class="toc-backref" href="#id132" role="doc-backlink">Version options</a><a class="headerlink" href="#version-options" title="Link to this heading"></a></h1>
<section id="version">
<span id="id50"></span><h2><a class="toc-backref" href="#id133" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">version</span></code></a><a class="headerlink" href="#version" title="Link to this heading"></a></h2>
<p><strong>What does it do?</strong>
Shows the version of the local installation of <code class="docutils literal notranslate"><span class="pre">certora-cli</span></code> you have.</p>
<p><strong>When to use it?</strong>
When you suspect you have an old installation. To install the newest version, use <code class="docutils literal notranslate"><span class="pre">pip</span> <span class="pre">install</span> <span class="pre">--upgrade</span> <span class="pre">certora-cli</span></code>.</p>
<p><strong>Example</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell110"><span></span>certoraRun<span class="w"> </span>--version
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell110">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
<section id="prover-version">
<h2><a class="toc-backref" href="#id134" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">prover_version</span></code></a><a class="headerlink" href="#prover-version" title="Link to this heading"></a></h2>
<p><strong>Usage</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell111"><span></span>--prover_version<span class="w"> </span>&lt;branch_name&gt;
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell111">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p><strong>What does it do?</strong>
This option lets you select a specific version of the Certora Prover by providing the name of a Git branch from the Prover repository. It does not accept individual commit hashes.</p>
<p><strong>When to use it?</strong>
Use this flag to reproduce behavior from an earlier version of the Prover, which is especially useful when features have been changed or deprecated in newer releases. The most common use case is specifying one of the release branches (e.g., release/10April2025) to match the behavior of a known version.</p>
</section>
</section>
<section id="conf-file-options">
<h1><a class="toc-backref" href="#id135" role="doc-backlink">Conf file options</a><a class="headerlink" href="#conf-file-options" title="Link to this heading"></a></h1>
<section id="override-base-config">
<span id="id51"></span><h2><a class="toc-backref" href="#id136" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">override_base_config</span></code></a><a class="headerlink" href="#override-base-config" title="Link to this heading"></a></h2>
<p><strong>What does it do?</strong>
Allows you to import flags from another conf file. The <code class="docutils literal notranslate"><span class="pre">--override_base_config</span></code> gets as a value a path to the imported conf file. If the path is relative, it is
relative to the current working directory, regardless of the original conf file’s location.
Flags in the imported conf file will be overridden if the same flag appears also in the original conf file
or in the command line. It is only possible to import from a single conf file and
the imported conf file cannot import from yet another conf file.</p>
<p><strong>When to use it?</strong>
When you want to use the same flags for multiple runs, but with some small changes. For example, you can have a base config
file with all the flags you need, and then create a new conf file that imports the base one
and overrides only the flags you want to change.</p>
<p>Using a base configuration file saves you from repeatedly writing the same flags in the command
line or other configuration files.</p>
<p><strong>Example</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell112"><span></span>certoraRun<span class="w"> </span>proj.conf<span class="w"> </span>--override_base_config<span class="w"> </span>confs/base_settings.conf
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell112">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p><strong>Example</strong>
To run verification using the Prover version from the April 10, 2025 release:</p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell113"><span></span>certoraRun<span class="w"> </span>MyContract.sol<span class="w"> </span>--verify<span class="w"> </span>MyContract:MySpec.spec<span class="w"> </span>--prover_version<span class="w"> </span>release/10April2025
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell113">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
</section>
<section id="advanced-options">
<h1><a class="toc-backref" href="#id137" role="doc-backlink">Advanced options</a><a class="headerlink" href="#advanced-options" title="Link to this heading"></a></h1>
<section id="java-args">
<span id="id52"></span><h2><a class="toc-backref" href="#id138" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">java_args</span></code></a><a class="headerlink" href="#java-args" title="Link to this heading"></a></h2>
<p><strong>What does it do?</strong></p>
<p>Allows setting configuring the underlying JVM.</p>
<p><strong>When to use it?</strong></p>
<p>Upon instruction from the Certora team.</p>
<p><strong>Example</strong></p>
<p><code class="docutils literal notranslate"><span class="pre">--java_args</span> <span class="pre">'"-Dcvt.default.parallelism=2"'</span></code> - will set the number of “tasks” that can run in parallel to 2.</p>
</section>
<section id="precise-bitwise-ops">
<span id="id53"></span><h2><a class="toc-backref" href="#id139" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">precise_bitwise_ops</span></code></a><a class="headerlink" href="#precise-bitwise-ops" title="Link to this heading"></a></h2>
<p><strong>What does it do?</strong>
This option models bitwise operations exactly, instead of using the default <a class="reference internal" href="../../user-guide/glossary.html#term-overapproximation"><span class="xref std std-term">overapproximation</span></a>. It is useful when the Prover reports a counterexample caused by incorrect modeling of bitwise operations, but enabling this option can significantly increase verification time.</p>
<p><strong>Limitations</strong></p>
<ul class="simple">
<li><p>This encoding does not model <code class="docutils literal notranslate"><span class="pre">mathint</span></code> precisely.</p></li>
<li><p>The maximum supported integer value is <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="0" style="font-size: 116.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-msup><mjx-mn class="mjx-n"><mjx-c class="mjx-c32"></mjx-c></mjx-mn><mjx-script style="vertical-align: 0.363em;"><mjx-texatom size="s" texclass="ORD"><mjx-mn class="mjx-n"><mjx-c class="mjx-c32"></mjx-c><mjx-c class="mjx-c35"></mjx-c><mjx-c class="mjx-c36"></mjx-c></mjx-mn></mjx-texatom></mjx-script></mjx-msup><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo><mjx-mn class="mjx-n" space="3"><mjx-c class="mjx-c31"></mjx-c></mjx-mn></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><msup><mn>2</mn><mrow data-mjx-texclass="ORD"><mn>256</mn></mrow></msup><mo>−</mo><mn>1</mn></math></mjx-assistive-mml></mjx-container></span>, effectively restricting <code class="docutils literal notranslate"><span class="pre">mathint</span></code> to a <code class="docutils literal notranslate"><span class="pre">uint256</span></code>.</p></li>
<li><p>There is currently no encoding that precisely models both bitwise operations and <code class="docutils literal notranslate"><span class="pre">mathint</span></code> simultaneously.</p></li>
</ul>
<p><strong>When to use it?</strong>
Use this option if a counterexample suggests that incorrect modeling of bitwise operations is affecting verification results.</p>
<p><strong>Example</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell114"><span></span>certoraRun<span class="w"> </span>Bank.sol<span class="w"> </span>--verify<span class="w"> </span>Bank:Bank.spec<span class="w"> </span>--precise_bitwise_ops
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell114">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
<section id="prover-args">
<span id="id54"></span><h2><a class="toc-backref" href="#id140" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">prover_args</span></code></a><a class="headerlink" href="#prover-args" title="Link to this heading"></a></h2>
<p>The <code class="docutils literal notranslate"><span class="pre">--prover_args</span></code> option allows you to provide fine-grained tuning options to the
Prover.  <code class="docutils literal notranslate"><span class="pre">--prover_args</span></code> receives a string containing Prover-specific options, and will be sent as-is to the Prover.
<code class="docutils literal notranslate"><span class="pre">--prover_args</span></code> cannot set Prover options that are set by standalone <code class="docutils literal notranslate"><span class="pre">certoraRun</span></code> options (e.g. the Prover option <code class="docutils literal notranslate"><span class="pre">--t</span></code> is
set by <code class="docutils literal notranslate"><span class="pre">--smt_timeout</span></code> therefore cannot appear in <code class="docutils literal notranslate"><span class="pre">--prover_args</span></code>). <code class="docutils literal notranslate"><span class="pre">--prover_args</span></code> value must be quoted.</p>
<section id="enablestoragesplitting">
<span id="id55"></span><h3><a class="toc-backref" href="#id141" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">enableStorageSplitting</span></code></a><a class="headerlink" href="#enablestoragesplitting" title="Link to this heading"></a></h3>
<p>This option disables the storage splitting optimization.</p>
<p><strong>Usage</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell115"><span></span>--prover_args<span class="w"> </span><span class="s1">'-enableStorageSplitting false'</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell115">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
<section id="maxnumberofreachchecksbasedondomination">
<span id="id56"></span><h3><a class="toc-backref" href="#id142" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">maxNumberOfReachChecksBasedOnDomination</span></code></a><a class="headerlink" href="#maxnumberofreachchecksbasedondomination" title="Link to this heading"></a></h3>
<p>This option sets the number of program points to test with the <code class="docutils literal notranslate"><span class="pre">deepSanity</span></code>
built-in rule.  See <a class="reference internal" href="../../cvl/builtin.html#built-in-deep-sanity"><span class="std std-ref">Thorough complexity checks — deepSanity</span></a>.</p>
<p><strong>Usage</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell116"><span></span>--prover_args<span class="w"> </span><span class="s1">'-maxNumberOfReachChecksBasedOnDomination &lt;n&gt;'</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell116">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
<section id="optimisticreturnsize">
<span id="id57"></span><h3><a class="toc-backref" href="#id143" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">optimisticReturnsize</span></code></a><a class="headerlink" href="#optimisticreturnsize" title="Link to this heading"></a></h3>
<p>This option determines whether <a class="reference internal" href="../../cvl/methods.html#havoc-summary"><span class="std std-ref">havoc summaries</span></a> assume
that the called method returns the correct number of return values.
It will set the value returned by the <code class="docutils literal notranslate"><span class="pre">RETURNSIZE</span></code> EVM instruction according to the
called method.</p>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>Certain conditions should hold in order for the option to take effect.
Namely, if there is a single candidate method in the havoc site,
and all instances of this method in the <a class="reference internal" href="../../user-guide/glossary.html#term-0"><span class="xref std std-term">scene</span></a> have exactly the same
expected number of return values, then the <code class="docutils literal notranslate"><span class="pre">RETURNSIZE</span></code> value will be set to
the expected size matching the methods in the scene.
Otherwise, <code class="docutils literal notranslate"><span class="pre">RETURNSIZE</span></code> will remain non-deterministic.</p>
</div>
<p><strong>Usage</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell117"><span></span>--prover_args<span class="w"> </span><span class="s1">'-optimisticReturnsize true'</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell117">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
<section id="smt-groundquantifiers">
<span id="id58"></span><h3><a class="toc-backref" href="#id144" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">smt_groundQuantifiers</span></code></a><a class="headerlink" href="#smt-groundquantifiers" title="Link to this heading"></a></h3>
<p>This option disables quantifier grounding.  See <a class="reference internal" href="../approx/grounding.html#grounding"><span class="std std-ref">Quantifier Grounding</span></a> for more
information.</p>
<p><strong>Usage</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell118"><span></span>--prover_args<span class="w"> </span><span class="s1">'-smt_groundQuantifiers false'</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell118">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
<section id="superoptimisticreturnsize">
<span id="id59"></span><h3><a class="toc-backref" href="#id145" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">superOptimisticReturnsize</span></code></a><a class="headerlink" href="#superoptimisticreturnsize" title="Link to this heading"></a></h3>
<p>This option determines whether <a class="reference internal" href="../../cvl/methods.html#havoc-summary"><span class="std std-ref">havoc summaries</span></a> assume
that the called method returns the correct number of return values.
It will set the value returned by the <code class="docutils literal notranslate"><span class="pre">RETURNSIZE</span></code> EVM instruction
to the size of the output buffer as specified by the summarized <code class="docutils literal notranslate"><span class="pre">CALL</span></code> instruction.</p>
<p><strong>Usage</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell119"><span></span>--prover_args<span class="w"> </span><span class="s1">'-superOptimisticReturnsize true'</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell119">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
</section>
<section id="control-flow-splitting-options">
<span id="id60"></span><h2><a class="toc-backref" href="#id146" role="doc-backlink">Control flow splitting options</a><a class="headerlink" href="#control-flow-splitting-options" title="Link to this heading"></a></h2>
<p>See <a class="reference internal" href="../techniques/index.html#control-flow-splitting"><span class="std std-ref">here</span></a> for an explanation of control flow splitting.</p>
<section id="depth">
<span id="id61"></span><h3><a class="toc-backref" href="#id147" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">depth</span></code></a><a class="headerlink" href="#depth" title="Link to this heading"></a></h3>
<p><strong>Usage</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell120"><span></span>--prover_args<span class="w"> </span><span class="s1">'-depth &lt;number&gt;'</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell120">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p><strong>What does it do?</strong></p>
<p>Sets the maximum splitting depth.</p>
<p><strong>When to use it?</strong></p>
<p>When the deepest <a class="reference internal" href="../../user-guide/glossary.html#term-split"><span class="xref std std-term">split</span></a>s are too heavy to solve, but not too high in
number, increasing this will lead to smaller, but more numerous
<a class="reference internal" href="../../user-guide/glossary.html#term-split-leaves"><span class="xref std std-term">split leaves</span></a>, which run at the full SMT timeout (as set by
<a class="reference internal" href="#smt-timeout"><span class="std std-ref">smt_timeout</span></a>).
Conversely, if run time is too high because there are too many splits,
decreasing this number means that more time is spent on fewer, but bigger split
leaves.
The default value for this option is 10.</p>
<p><strong>Example</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell121"><span></span>certoraRun<span class="w"> </span>Bank.sol<span class="w"> </span>--verify<span class="w"> </span>Bank:bank.spec<span class="w"> </span>--prover_args<span class="w"> </span><span class="s1">'-depth 5'</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell121">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
<section id="dontstopatfirstsplittimeout">
<span id="id62"></span><h3><a class="toc-backref" href="#id148" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">dontStopAtFirstSplitTimeout</span></code></a><a class="headerlink" href="#dontstopatfirstsplittimeout" title="Link to this heading"></a></h3>
<p><strong>Usage</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell122"><span></span>--prover_args<span class="w"> </span><span class="s1">'-dontStopAtFirstSplitTimeout &lt;true/false&gt;'</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell122">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p><strong>What does it do?</strong></p>
<p>We can tell the Certora Prover to continue even when the a <a class="reference internal" href="../../user-guide/glossary.html#term-split"><span class="xref std std-term">split</span></a> has had
a maximum-depth timeout. Note that this is only useful when there exists a
<a class="reference internal" href="../../user-guide/glossary.html#term-counterexample"><span class="xref std std-term">counterexample</span></a> for the rule under verification, since in order to prove
the absence of counterexamples (i.e. correctness), all splits need to be
counterexample-free. (In case of a rule using <code class="docutils literal notranslate"><span class="pre">satisfy</span></code> rather than <code class="docutils literal notranslate"><span class="pre">assert</span></code>,
the corresponding statements hold for <a class="reference internal" href="../../user-guide/glossary.html#term-witness-example"><span class="xref std std-term">witness example</span></a>s. In that case,
this option is only useful if the rule is correct.)</p>
<p><strong>When to use it?</strong></p>
<p>When looking for a SAT result and observing an <a class="reference internal" href="../../user-guide/out-of-resources/timeout.html#timeouts-introduction"><span class="std std-ref">SMT-type timeout</span></a>.
The default value for this option is <code class="docutils literal notranslate"><span class="pre">false</span></code>.</p>
<p><strong>Example</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell123"><span></span>certoraRun<span class="w"> </span>Bank.sol<span class="w"> </span>--verify<span class="w"> </span>Bank:bank.spec<span class="w"> </span>--prover_args<span class="w"> </span><span class="s1">'-dontStopAtFirstSplitTimeout true'</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell123">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
<section id="mediumtimeout">
<span id="id63"></span><h3><a class="toc-backref" href="#id149" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">mediumTimeout</span></code></a><a class="headerlink" href="#mediumtimeout" title="Link to this heading"></a></h3>
<p>The “medium timeout” determines how much time the SMT solver gets for checking a
<a class="reference internal" href="../../user-guide/glossary.html#term-split"><span class="xref std std-term">split</span></a> that is not a <a class="reference internal" href="../../user-guide/glossary.html#term-split-leaf"><span class="xref std std-term">split leaf</span></a>.
(For split leaves, the full <a class="reference internal" href="#smt-timeout"><span class="std std-ref">smt_timeout</span></a> is used.)</p>
<p><strong>Usage</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell124"><span></span>--prover_args<span class="w"> </span><span class="s1">'-mediumTimeout &lt;seconds&gt;'</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell124">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p><strong>What does it do?</strong></p>
<p>Sets the time that non-leaf splits get before being split again.</p>
<p><strong>When to use it?</strong></p>
<p>When a little more time can close some splitting subtrees early, this can save a
lot of time, since the subtree’s size is exponential in the remaining depth. On
the other hand, if something will be split further anyway, this can save the
run time spent on intermediate “TIMEOUT” results. Use
<a class="reference internal" href="#smt-initialsplitdepth"><span class="std std-ref">smt_initialSplitDepth</span></a> to eliminate that time investment altogether up to
a given depth.</p>
<p><strong>Example</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell125"><span></span>certoraRun<span class="w"> </span>Bank.sol<span class="w"> </span>--verify<span class="w"> </span>Bank:bank.spec<span class="w"> </span>--prover_args<span class="w"> </span><span class="s1">'-mediumTimeout 20'</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell125">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
<section id="smt-initialsplitdepth">
<span id="id64"></span><h3><a class="toc-backref" href="#id150" role="doc-backlink"><code class="docutils literal notranslate"><span class="pre">smt_initialSplitDepth</span></code></a><a class="headerlink" href="#smt-initialsplitdepth" title="Link to this heading"></a></h3>
<p>With this option, the splitting can be configured to skip the SMT solver-based checks
at low splitting levels, thus generating sub-<a class="reference internal" href="../../user-guide/glossary.html#term-split"><span class="xref std std-term">split</span></a>s up to a given depth immediately.</p>
<p><strong>Usage</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell126"><span></span>--prover_args<span class="w"> </span><span class="s1">'-smt_initialSplitDepth &lt;number&gt;'</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell126">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p><strong>What does it do?</strong></p>
<p>The first <code class="docutils literal notranslate"><span class="pre">&lt;number&gt;</span></code> split levels are not checked with the SMT solver, but rather
split immediately.</p>
<p><strong>When to use it?</strong></p>
<p>When there is a lot of overhead induced by processing and trying to solve splits
that are very hard, and thus run into a timeout anyway.</p>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>The number of splits generated here is equal to <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="1" style="font-size: 116.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-msup><mjx-mn class="mjx-n"><mjx-c class="mjx-c32"></mjx-c></mjx-mn><mjx-script style="vertical-align: 0.363em;"><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi></mjx-script></mjx-msup></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><msup><mn>2</mn><mi>n</mi></msup></math></mjx-assistive-mml></mjx-container></span> where <code class="docutils literal notranslate"><span class="pre">n</span></code> is the initial
splitting depth (assuming the program has enough branching points,
which is usually the case);
thus, low numbers are advisable. For instance setting this to 5 means that the
Prover will immediately produce 32 splits.</p>
</div>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>The <a class="reference internal" href="#depth"><span class="std std-ref">depth</span></a> setting has precedence over this setting. I.e., if <code class="docutils literal notranslate"><span class="pre">-depth</span></code>
is set to a lower value than <code class="docutils literal notranslate"><span class="pre">-smt_initialSplitDepth</span></code>, the initial splitting
will only proceed up to the splitting depth given via <code class="docutils literal notranslate"><span class="pre">-depth</span></code>.</p>
</div>
<p><strong>Example</strong></p>
<div class="highlight-sh notranslate"><div class="highlight"><pre id="codecell127"><span></span>certoraRun<span class="w"> </span>Bank.sol<span class="w"> </span>--verify<span class="w"> </span>Bank:bank.spec<span class="w"> </span>--prover_args<span class="w"> </span><span class="s1">'-smt_initialSplitDepth 3'</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell127">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
</section>
</section>
</section>


           </div>
          </div>
          <footer><div class="rst-footer-buttons" role="navigation" aria-label="Footer">
        <a href="index.html" class="btn btn-neutral float-left" title="Certora Prover CLI" accesskey="p" rel="prev"><span class="fa fa-arrow-circle-left" aria-hidden="true"></span> Previous</a>
        <a href="conf-file-api.html" class="btn btn-neutral float-right" title="Configuration (Conf) Files" accesskey="n" rel="next">Next <span class="fa fa-arrow-circle-right" aria-hidden="true"></span></a>
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