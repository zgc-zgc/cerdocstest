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
    <link rel="next" title="Uninterpreted Sorts" href="sorts.html">
    <link rel="prev" title="Functions" href="functions.html"> 
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

mjx-c {
  display: inline-block;
}

mjx-utext {
  display: inline-block;
  padding: .75em 0 .2em 0;
}

mjx-msub {
  display: inline-block;
  text-align: left;
}

mjx-mi {
  display: inline-block;
  text-align: left;
}

mjx-mn {
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

mjx-c.mjx-c2200::before {
  padding: 0.694em 0.556em 0.022em 0;
  content: "\2200";
}

mjx-c.mjx-c21D2::before {
  padding: 0.525em 1em 0.024em 0;
  content: "\21D2";
}

mjx-c.mjx-c2227::before {
  padding: 0.598em 0.667em 0.022em 0;
  content: "\2227";
}

mjx-c.mjx-c1D443.TEX-I::before {
  padding: 0.683em 0.751em 0 0;
  content: "P";
}

mjx-c.mjx-c1D456.TEX-I::before {
  padding: 0.661em 0.345em 0.011em 0;
  content: "i";
}

mjx-c.mjx-c28::before {
  padding: 0.75em 0.389em 0.25em 0;
  content: "(";
}

mjx-c.mjx-c1D465.TEX-I::before {
  padding: 0.442em 0.572em 0.011em 0;
  content: "x";
}

mjx-c.mjx-c2C::before {
  padding: 0.121em 0.278em 0.194em 0;
  content: ",";
}

mjx-c.mjx-c1D45B.TEX-I::before {
  padding: 0.442em 0.6em 0.011em 0;
  content: "n";
}

mjx-c.mjx-c29::before {
  padding: 0.75em 0.389em 0.25em 0;
  content: ")";
}

mjx-c.mjx-c30::before {
  padding: 0.666em 0.5em 0.022em 0;
  content: "0";
}

mjx-c.mjx-c2B::before {
  padding: 0.583em 0.778em 0.082em 0;
  content: "+";
}

mjx-c.mjx-c31::before {
  padding: 0.666em 0.5em 0 0;
  content: "1";
}

mjx-c.mjx-c2227.TEX-B::before {
  padding: 0.604em 0.767em 0.017em 0;
  content: "\2227";
}

mjx-c.mjx-c1D410.TEX-B::before {
  padding: 0.696em 0.864em 0.193em 0;
  content: "Q";
}

mjx-c.mjx-c2E::before {
  padding: 0.12em 0.278em 0 0;
  content: ".";
}

mjx-c.mjx-c1D444.TEX-I::before {
  padding: 0.704em 0.791em 0.194em 0;
  content: "Q";
}

mjx-c.mjx-c1D457.TEX-I::before {
  padding: 0.661em 0.412em 0.204em 0;
  content: "j";
}

mjx-c.mjx-c1D453.TEX-I::before {
  padding: 0.705em 0.55em 0.205em 0;
  content: "f";
}
</style></head>

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
<li class="toctree-l1"><a class="reference internal" href="../user-guide/index.html">Certora User’s Guide</a></li>
<li class="toctree-l1 current" aria-expanded="true"><a class="reference internal" href="index.html"><button class="toctree-expand" title="Open/close menu"></button>The Certora Verification Language</a><ul class="" aria-expanded="false">
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
<li class="toctree-l2 current" aria-expanded="true"><a class="reference internal current" href="#" aria-expanded="true"><button class="toctree-expand" title="Open/close menu"></button>Invariants</a><ul>
<li class="toctree-l3"><a class="reference internal" href="#syntax">Syntax</a></li>
<li class="toctree-l3"><a class="reference internal" href="#overview">Overview</a></li>
<li class="toctree-l3"><a class="reference internal" href="#invariants-that-revert">Invariants that revert</a></li>
<li class="toctree-l3"><a class="reference internal" href="#preserved-blocks"><button class="toctree-expand" title="Open/close menu"></button>Preserved blocks</a><ul>
<li class="toctree-l4"><a class="reference internal" href="#contract-and-method-specific-preserved-blocks">Contract and method-specific preserved blocks</a></li>
<li class="toctree-l4"><a class="reference internal" href="#generic-preserved-blocks">Generic preserved blocks</a></li>
<li class="toctree-l4"><a class="reference internal" href="#binding-the-environment">Binding the environment</a></li>
</ul>
</li>
<li class="toctree-l3"><a class="reference internal" href="#filters">Filters</a></li>
<li class="toctree-l3"><a class="reference internal" href="#induction-step-for-transient-storage">Induction Step for Transient Storage</a></li>
<li class="toctree-l3"><a class="reference internal" href="#writing-an-invariant-as-a-rule">Writing an invariant as a rule</a></li>
<li class="toctree-l3"><a class="reference internal" href="#invariants-and-induction">Invariants and induction</a></li>
</ul>
</li>
<li class="toctree-l2"><a class="reference internal" href="sorts.html">Uninterpreted Sorts</a></li>
<li class="toctree-l2"><a class="reference internal" href="ghosts.html">Ghosts</a></li>
<li class="toctree-l2"><a class="reference internal" href="defs.html">Definitions</a></li>
<li class="toctree-l2"><a class="reference internal" href="hooks.html">Hooks</a></li>
<li class="toctree-l2"><a class="reference internal" href="transient.html">Transient Storage</a></li>
<li class="toctree-l2"><a class="reference internal" href="foundry-integration.html">Foundry Integration (Alpha)</a></li>
<li class="toctree-l2"><a class="reference internal" href="index.html#changes-since-cvl-1">Changes Since CVL 1</a></li>
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
          <li class="breadcrumb-item"><a href="index.html">The Certora Verification Language</a></li>
      <li class="breadcrumb-item active">Invariants</li>
      <li class="wy-breadcrumbs-aside">
            <a href="../../_sources/docs/cvl/invariants.md.txt" rel="nofollow"> View page source</a>
      </li>
  </ul>
  <hr>
</div>
          <div role="main" class="document" itemscope="itemscope" itemtype="http://schema.org/Article">
           <div itemprop="articleBody">
             
  <section id="invariants">
<span id="id1"></span><h1><a class="toc-backref" href="#id2" role="doc-backlink">Invariants</a><a class="headerlink" href="#invariants" title="Link to this heading"></a></h1>
<p>Invariants describe a property of the state of a contract that is always
expected to hold.</p>
<div class="admonition caution">
<p class="admonition-title">Caution</p>
<p>Certain features of invariants are <a class="reference internal" href="../user-guide/glossary.html#term-unsound"><span class="xref std std-term">unsound</span></a>: the invariant can be
verified by the Prover, but it may still be possible for the contract to
violate it.  The possible sources of unsoundness are <a class="reference internal" href="#preserved"><span class="std std-ref">Preserved blocks</span></a>,
<a class="reference internal" href="#invariant-filters"><span class="std std-ref">Filters</span></a>, and <a class="reference internal" href="#invariant-revert"><span class="std std-ref">Invariants that revert</span></a>.  Invariant proofs are
also unsound if some of the methods are filtered out using the
<a class="reference internal" href="../prover/cli/options.html#method"><span class="std std-ref">method</span></a> or <a class="reference internal" href="../prover/cli/options.html#parametric-contracts"><span class="std std-ref">parametric_contracts</span></a> flags.  See the linked sections for
details.</p>
</div>
<nav class="contents" id="contents">
<p class="topic-title">Contents</p>
<ul class="simple">
<li><p><a class="reference internal" href="#invariants" id="id2">Invariants</a></p>
<ul>
<li><p><a class="reference internal" href="#syntax" id="id3">Syntax</a></p></li>
<li><p><a class="reference internal" href="#overview" id="id4">Overview</a></p></li>
<li><p><a class="reference internal" href="#invariants-that-revert" id="id5">Invariants that revert</a></p></li>
<li><p><a class="reference internal" href="#preserved-blocks" id="id6">Preserved blocks</a></p>
<ul>
<li><p><a class="reference internal" href="#contract-and-method-specific-preserved-blocks" id="id7">Contract and method-specific preserved blocks</a></p></li>
<li><p><a class="reference internal" href="#generic-preserved-blocks" id="id8">Generic preserved blocks</a></p></li>
<li><p><a class="reference internal" href="#binding-the-environment" id="id9">Binding the environment</a></p></li>
</ul>
</li>
<li><p><a class="reference internal" href="#filters" id="id10">Filters</a></p></li>
<li><p><a class="reference internal" href="#induction-step-for-transient-storage" id="id11">Induction Step for Transient Storage</a></p></li>
<li><p><a class="reference internal" href="#writing-an-invariant-as-a-rule" id="id12">Writing an invariant as a rule</a></p></li>
<li><p><a class="reference internal" href="#invariants-and-induction" id="id13">Invariants and induction</a></p></li>
</ul>
</li>
</ul>
</nav>
<section id="syntax">
<h2><a class="toc-backref" href="#id3" role="doc-backlink">Syntax</a><a class="headerlink" href="#syntax" title="Link to this heading"></a></h2>
<p>The syntax for invariants is given by the following <a class="reference internal" href="overview.html#ebnf-syntax"><span class="std std-ref">EBNF grammar</span></a>:</p>
<div class="highlight-default notranslate"><div class="highlight"><pre id="codecell0"><span></span><span class="n">invariant</span> <span class="p">:</span><span class="o">:=</span> <span class="p">[</span> <span class="s2">"weak"</span> <span class="o">|</span> <span class="s2">"strong"</span> <span class="p">]</span> <span class="s2">"invariant"</span> <span class="nb">id</span>
              <span class="p">[</span> <span class="s2">"("</span> <span class="n">params</span> <span class="s2">")"</span> <span class="p">]</span>
              <span class="n">expression</span>
              <span class="p">[</span> <span class="s2">"filtered"</span> <span class="s2">"{"</span> <span class="nb">id</span> <span class="s2">"-&gt;"</span> <span class="n">expression</span> <span class="s2">"}"</span> <span class="p">]</span>
              <span class="p">[</span> <span class="s2">"{"</span> <span class="p">{</span> <span class="n">preserved_block</span> <span class="p">}</span> <span class="s2">"}"</span> <span class="p">]</span>

<span class="n">preserved_block</span> <span class="p">:</span><span class="o">:=</span> <span class="s2">"preserved"</span>
                    <span class="p">[</span> <span class="n">method_signature</span> <span class="p">]</span>
                    <span class="p">[</span> <span class="s2">"with"</span> <span class="s2">"("</span> <span class="n">params</span> <span class="s2">")"</span> <span class="p">]</span>
                    <span class="n">block</span>

<span class="n">method_signature</span> <span class="p">:</span><span class="o">:=</span> <span class="p">[</span> <span class="n">contract_name</span> <span class="s2">"."</span> <span class="p">]</span> <span class="nb">id</span>  <span class="s2">"("</span> <span class="p">[</span> <span class="n">evm_type</span> <span class="p">[</span> <span class="nb">id</span> <span class="p">]</span> <span class="p">{</span> <span class="s2">","</span> <span class="n">evm_type</span> <span class="p">[</span> <span class="nb">id</span> <span class="p">]</span> <span class="p">}</span> <span class="p">]</span> <span class="s2">")"</span>
                     <span class="o">|</span> <span class="s2">"fallback"</span> <span class="s2">"("</span> <span class="s2">")"</span>

<span class="n">contract_name</span> <span class="p">:</span><span class="o">:=</span> <span class="nb">id</span>
                <span class="o">|</span> <span class="s2">"_"</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell0">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>See <a class="reference internal" href="basics.html"><span class="doc">Basic Syntax</span></a> for the <code class="docutils literal notranslate"><span class="pre">id</span></code> production, <a class="reference internal" href="expr.html"><span class="doc">Expressions</span></a> for the <code class="docutils literal notranslate"><span class="pre">expression</span></code>
production, and <a class="reference internal" href="statements.html"><span class="doc">Statements</span></a> for the <code class="docutils literal notranslate"><span class="pre">block</span></code> production.</p>
</section>
<section id="overview">
<h2><a class="toc-backref" href="#id4" role="doc-backlink">Overview</a><a class="headerlink" href="#overview" title="Link to this heading"></a></h2>
<p>In CVL, we distinguish between strong and weak invariants.
A <em>weak</em> invariant is a property that is expected to be
true whenever a contract method is not currently executing.  This kind of
invariant is sometimes called a “representation invariant”. A <em>strong</em> invariant is
an invariant that also holds before and after execution of an unresolved call, i.e. a call that
potentially calls to another contract which could modify the current contract’s state.
Essentially, a strong invariants ensures to hold whenever control is yielded to an external function, providing enhanced security, especially for contracts without global locks.</p>
<p>Each invariant has a name, possibly followed by a set of parameters, followed
by a boolean expression.  We say the invariant <em>holds</em> if the expression
evaluates to true in every reachable state of the contract, and for all
possible values of the parameters.</p>
<p>While verifying a weak invariant, the Prover checks two things.  First, it checks
that the invariant is established after calling any constructor.  Second, it checks
that the invariant holds after the execution of any methods, assuming that it held
before the method was executed (if it does hold, we say the method <em>preserves</em> the invariant).
By default, an invariant will be checked for any <code class="docutils literal notranslate"><span class="pre">public</span></code> or <code class="docutils literal notranslate"><span class="pre">external</span></code>
(non-<code class="docutils literal notranslate"><span class="pre">view</span></code>/<code class="docutils literal notranslate"><span class="pre">pure</span></code>) method of any contract in the scene - the set of methods
an invariant will be checked for can be further configured by filters <a class="reference internal" href="#invariant-filters"><span class="std std-ref">Filters</span></a>
and by <a class="reference internal" href="../prover/cli/options.html#parametric-contracts"><span class="std std-ref">parametric_contracts</span></a>. <code class="docutils literal notranslate"><span class="pre">View</span></code> and <code class="docutils literal notranslate"><span class="pre">pure</span></code> methods are excluded from
invariant checking as by definition they cannot change the state
of their contract.</p>
<p>A strong invariant performs the same checks as a weak invariant - i.e. it will be checked for the constructor
and for any other method, it will be assumed before executing the method (pre-state) and asserted afterward execution of the method (post-state).
In addition to these steps, a strong invariant also asserts and assumes the invariant <em>during</em> method
execution at locations that potentially break the invariant. The invariant can be violated if there
is an unresolved external call that can modify the state of the current contract. To verify the strong invariant, for every unresolved external call <code class="docutils literal notranslate"><span class="pre">c</span></code>
(a call that will force the prover to havoc storage), a strong invariant will insert the following steps:</p>
<ol class="arabic simple">
<li><p><em>Before</em> the call <code class="docutils literal notranslate"><span class="pre">c</span></code>: Assert that the invariant holds - if the invariant does not hold due to some logic of the current method, this will yield a counter example that ends with the <code class="docutils literal notranslate"><span class="pre">assert</span></code> before <code class="docutils literal notranslate"><span class="pre">c</span></code>.</p></li>
<li><p><em>After</em> the call <code class="docutils literal notranslate"><span class="pre">c</span></code>: Assume the invariant holds. The semantics is that the call did not break the invariant.</p></li>
<li><p>In the case <code class="docutils literal notranslate"><span class="pre">c</span></code> is a <code class="docutils literal notranslate"><span class="pre">delegatecall</span></code>, after assuming the invariant in step 2, havoc the current’s contact storage and assert the invariant once more. This step simulates the scenario that a <code class="docutils literal notranslate"><span class="pre">delegatecall</span></code> modifies the current contract’s storage.</p></li>
</ol>
<p>A full example for <code class="docutils literal notranslate"><span class="pre">weak</span></code> and <code class="docutils literal notranslate"><span class="pre">strong</span> <span class="pre">invariant</span></code> can be found in our <a class="reference external" href="https://github.com/Certora/Examples/blob/cli-beta/CVLByExample/StrongInvariants/README.md">Examples Repository</a>.</p>
<p>If an invariant is proven, it is safe to assume that it holds in other rules
and invariants.  The
<a class="reference internal" href="statements.html#requireinvariant"><span class="std std-ref">requireInvariant command</span></a> makes it easy to add this
assumption to another rule, and is a quick way to rule out counterexamples that
start in impossible states.  See also <a class="reference internal" href="../user-guide/patterns/safe-assum.html"><span class="doc">Listing Safe Assumptions</span></a>.</p>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>Invariants are intended to describe the state of a contract at a particular
point in time.  Therefore, you should only use view functions inside of an
invariant.  Non-view functions are allowed, but the behavior is undefined.</p>
</div>
</section>
<section id="invariants-that-revert">
<span id="invariant-revert"></span><h2><a class="toc-backref" href="#id5" role="doc-backlink">Invariants that revert</a><a class="headerlink" href="#invariants-that-revert" title="Link to this heading"></a></h2>
<p>There is well-known unsoundness in the Prover’s handling of invariants that
occurs if an invariant expression reverts in the “before” state but not in the
“after” state.  In this case, the assumption that the invariant holds before
calling the contract method will revert, causing any counterexample to be
discarded.</p>
<p>For example, consider the following contract:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell1"><span></span>contract<span class="w"> </span>Example<span class="w"> </span><span class="p">{</span>
<span class="w">    </span>private<span class="w"> </span><span class="kt">uint</span><span class="p">[]</span><span class="w"> </span>a<span class="p">;</span>

<span class="w">    </span>public<span class="w"> </span><span class="kt">function</span><span class="w"> </span><span class="nf">add</span><span class="p">(</span><span class="kt">uint</span><span class="w"> </span>i<span class="p">)</span><span class="w"> </span><span class="kr">external</span><span class="w"> </span><span class="p">{</span>
<span class="w">        </span>a<span class="p">.</span>push<span class="p">(</span>i<span class="p">);</span>
<span class="w">    </span><span class="p">}</span>

<span class="w">    </span>public<span class="w"> </span><span class="kt">function</span><span class="w"> </span><span class="nf">get</span><span class="p">(</span><span class="kt">uint</span><span class="w"> </span>i<span class="p">)</span><span class="w"> </span><span class="kr">external</span><span class="w"> </span><span class="kr">returns</span><span class="p">(</span><span class="kt">uint</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">        </span><span class="kr">return</span><span class="w"> </span>a<span class="p">[</span>i<span class="p">];</span>
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
<p>This contract simply wraps an array of integers and allows you to add integers
to the array.  The following invariant states that all elements of the array are
0:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell2"><span></span><span class="k">invariant</span><span class="w"> </span><span class="nc">all_elements_are_zero</span><span class="p">(</span><span class="kt">uint</span><span class="w"> </span>i<span class="p">)</span><span class="w"> </span>get<span class="p">(</span>i<span class="p">)</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">;</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell2">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>This property is clearly false; you can invalidate it by calling <code class="docutils literal notranslate"><span class="pre">add(2)</span></code>.
Nevertheless, the invariant will pass.  The reason is that before a call to
<code class="docutils literal notranslate"><span class="pre">add</span></code> pushes a nonzero integer into <code class="docutils literal notranslate"><span class="pre">a[i]</span></code>, the length of <code class="docutils literal notranslate"><span class="pre">a</span></code> was <code class="docutils literal notranslate"><span class="pre">i-1</span></code>, so the
call to <code class="docutils literal notranslate"><span class="pre">get(i)</span></code> will revert.  Therefore, the Prover would discard the
counterexample instead of reporting it.
As above, an invariant stating that <code class="docutils literal notranslate"><span class="pre">supply()</span> <span class="pre">==</span> <span class="pre">token.totalSupply()</span></code> would be
verified, but a method on <code class="docutils literal notranslate"><span class="pre">token</span></code> might change the total supply without updating
the <code class="docutils literal notranslate"><span class="pre">SupplyTracker</span></code> contract.  Since the Prover only checks the main contract’s
methods for preservation, it will not report that the invariant can be
falsified.</p>
<p>For this reason, invariants that depend on the environment or on the state of
external contracts are a potential source of <a class="reference internal" href="../user-guide/glossary.html#term-unsound"><span class="xref std std-term">unsoundness</span></a>, and should be
used with care.</p>
<p>There is an additional source of unsoundness that occurs if the invariant
expression reverts in the before state but not in the after state.</p>
</section>
<section id="preserved-blocks">
<span id="preserved"></span><h2><a class="toc-backref" href="#id6" role="doc-backlink">Preserved blocks</a><a class="headerlink" href="#preserved-blocks" title="Link to this heading"></a></h2>
<p>Often, the proof that an invariant is preserved depends on another invariant,
or on an external assumption about the system.  These assumptions can be
written in <code class="docutils literal notranslate"><span class="pre">preserved</span></code> blocks.</p>
<div class="admonition caution">
<p class="admonition-title">Caution</p>
<p>Adding <code class="docutils literal notranslate"><span class="pre">require</span></code> statements to preserved blocks can be a source of
<a class="reference internal" href="../user-guide/glossary.html#term-unsound"><span class="xref std std-term">unsoundness</span></a>, since the invariants are only guaranteed to hold
if the requirements are true for every method invocation.</p>
</div>
<p>Recall that the Prover checks that a method preserves an invariant by first
requiring the invariant (the prestate check), then executing the method, and
then asserting the invariant (the poststate check).  Preserved blocks are
executed after the prestate check but before executing the method.  They
usually consist of <code class="docutils literal notranslate"><span class="pre">require</span></code> or <code class="docutils literal notranslate"><span class="pre">requireInvariant</span></code> statements, although other
commands are also possible.</p>
<p>Preserved blocks are listed after the invariant expression (and after the filter
block, if any), inside a set of curly braces (<code class="docutils literal notranslate"><span class="pre">{</span> <span class="pre">...</span> <span class="pre">}</span></code>).  Each preserved block
consists of the keyword <code class="docutils literal notranslate"><span class="pre">preserved</span></code> followed by an optional method signature,
an optional <code class="docutils literal notranslate"><span class="pre">with</span></code> declaration, and finally the block of commands to execute.</p>
<section id="contract-and-method-specific-preserved-blocks">
<h3><a class="toc-backref" href="#id7" role="doc-backlink">Contract and method-specific preserved blocks</a><a class="headerlink" href="#contract-and-method-specific-preserved-blocks" title="Link to this heading"></a></h3>
<p>The method signature of the preserved block may optionally contain a contract
name followed by a <code class="docutils literal notranslate"><span class="pre">.</span></code> character followed by a contract method name.</p>
<ul class="simple">
<li><p>In the case where the preserved block does not have a contract name but does
have a method name (not the <code class="docutils literal notranslate"><span class="pre">fallback</span></code> case), the preserved block will apply
only to methods that match in the main contract.
For example, here the preserved block will apply only to the method <code class="docutils literal notranslate"><span class="pre">withdrawExcess(address)</span></code> that appears in the main contract:</p></li>
</ul>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell3"><span></span><span class="k">invariant</span><span class="w"> </span><span class="nc">solvencyAsInv</span><span class="p">()</span><span class="w"> </span>asset<span class="p">.</span>balanceOf<span class="p">()</span><span class="w"> </span><span class="o">&gt;=</span><span class="w"> </span>internalAccounting<span class="p">()</span><span class="w"> </span><span class="p">{</span>
<span class="w">  </span><span class="kr">preserved</span><span class="w"> </span>withdrawExcess<span class="p">(</span><span class="kt">address</span><span class="w"> </span>token<span class="p">)</span><span class="w">  </span><span class="p">{</span>
<span class="w">      </span><span class="kr">require</span><span class="w"> </span>token<span class="w"> </span><span class="o">!=</span><span class="w"> </span>asset<span class="p">;</span><span class="w"> </span>
<span class="w">  </span><span class="p">}</span>
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
<ul class="simple">
<li><p>If the method signature includes a specific contract name, then the Prover
only applies the preserved block to the methods in the named contract.
For example, here the preserved block only applies to the <code class="docutils literal notranslate"><span class="pre">asset</span></code> contract method <code class="docutils literal notranslate"><span class="pre">transfer(address,uint)</span></code>. The preserved block does not apply to the <code class="docutils literal notranslate"><span class="pre">transfer(address,uint)</span></code> method in any other contract.</p></li>
</ul>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell4"><span></span><span class="k">invariant</span><span class="w"> </span><span class="nc">solvencyAsInv</span><span class="p">()</span><span class="w"> </span>asset<span class="p">.</span>balanceOf<span class="p">()</span><span class="w"> </span><span class="o">&gt;=</span><span class="w"> </span>internalAccounting<span class="p">()</span><span class="w"> </span><span class="p">{</span>
<span class="w">  </span><span class="kr">preserved</span><span class="w"> </span>asset<span class="p">.</span>transfer<span class="p">(</span><span class="kt">address</span><span class="w"> </span>x<span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>y<span class="p">)</span><span class="w"> </span>with<span class="w"> </span><span class="p">(</span><span class="kt">env</span><span class="w"> </span>e<span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">      </span><span class="kr">require</span><span class="w"> </span>e<span class="p">.</span><span class="kc">msg.sender</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="nb">currentContract</span><span class="w"> </span>
<span class="w">  </span><span class="p">}</span>
<span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell4">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<ul class="simple">
<li><p>If the contract name is the wildcard character <code class="docutils literal notranslate"><span class="pre">_</span></code>, the Prover applies the
preserved block to instances of the method in all contracts in the scene.
For example, this preserve block applies to all contracts containing a method matching the <code class="docutils literal notranslate"><span class="pre">transfer(address,uint)</span></code> method signature.</p></li>
</ul>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell5"><span></span><span class="k">invariant</span><span class="w"> </span><span class="nc">solvencyAsInv</span><span class="p">()</span><span class="w"> </span>asset<span class="p">.</span>balanceOf<span class="p">()</span><span class="w"> </span><span class="o">&gt;=</span><span class="w"> </span>internalAccounting<span class="p">()</span><span class="w"> </span><span class="p">{</span>
<span class="w">  </span><span class="kr">preserved</span><span class="w"> </span>_<span class="p">.</span>transfer<span class="p">(</span><span class="kt">address</span><span class="w"> </span>x<span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>y<span class="p">)</span><span class="w"> </span>with<span class="w"> </span><span class="p">(</span><span class="kt">env</span><span class="w"> </span>e<span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">      </span><span class="kr">require</span><span class="w"> </span>e<span class="p">.</span><span class="kc">msg.sender</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="nb">currentContract</span><span class="w"> </span>
<span class="w">  </span><span class="p">}</span>
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
<p>If an invariant has multiple preserved blocks with the same method signature
where one signature is more specific and the other is more general (as in
the <code class="docutils literal notranslate"><span class="pre">_.method</span></code> case), then the more specific preserved block will apply.</p>
<p>If a preserved block specifies a method signature, the signature must either be <code class="docutils literal notranslate"><span class="pre">fallback()</span></code> or
match one of the contract methods, and the preserved block only applies when
checking preservation of that contract method.  The <code class="docutils literal notranslate"><span class="pre">fallback()</span></code> preserved block
applies only to the <code class="docutils literal notranslate"><span class="pre">fallback()</span></code> function that should be defined in the contract.
The arguments of the method are in scope within the preserved block.</p>
</section>
<section id="generic-preserved-blocks">
<h3><a class="toc-backref" href="#id8" role="doc-backlink">Generic preserved blocks</a><a class="headerlink" href="#generic-preserved-blocks" title="Link to this heading"></a></h3>
<p>If there is no method signature, the preserved block is a default block that is
used for all methods that don’t have a specific preserved block, including the
<code class="docutils literal notranslate"><span class="pre">fallback()</span></code> method.  If an invariant has both a default preserved block and a
specific preserved block for a method, the specific preserved block is used;
the default preserved block will not be executed.</p>
</section>
<section id="binding-the-environment">
<h3><a class="toc-backref" href="#id9" role="doc-backlink">Binding the environment</a><a class="headerlink" href="#binding-the-environment" title="Link to this heading"></a></h3>
<p>The <code class="docutils literal notranslate"><span class="pre">with</span></code> declaration is used to give a name to the <a class="reference internal" href="../user-guide/glossary.html#term-environment"><span class="xref std std-term">environment</span></a> used
while invoking the method.  It can be used to restrict the transactions that are
considered.  For example, the following preserved block rules out
counterexamples where the <code class="docutils literal notranslate"><span class="pre">msg.sender</span></code> is the 0 address:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell6"><span></span><span class="k">invariant</span><span class="w"> </span><span class="nc">zero_address_has_no_balance</span><span class="p">()</span>
<span class="w">    </span>balanceOf<span class="p">(</span><span class="m m-Decimal">0</span><span class="p">)</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="m m-Decimal">0</span>
<span class="w">    </span><span class="p">{</span><span class="w"> </span><span class="kr">preserved</span><span class="w"> </span>with<span class="w"> </span><span class="p">(</span><span class="kt">env</span><span class="w"> </span>e<span class="p">)</span><span class="w"> </span><span class="p">{</span><span class="w"> </span><span class="kr">require</span><span class="w"> </span>e<span class="p">.</span><span class="kc">msg.sender</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">;</span><span class="w"> </span><span class="p">}</span><span class="w"> </span><span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell6">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>The variables defined as parameters to the invariant are also available in
preserved blocks, which allows restricting the arguments that are considered
when checking that a method preserves an invariant.  As always, you should use
caution when adding additional <code class="docutils literal notranslate"><span class="pre">require</span></code> statements, as they can rule out
important cases.</p>
<div class="admonition caution">
<p class="admonition-title">Caution</p>
<p>A common source of confusion is the difference between <code class="docutils literal notranslate"><span class="pre">env</span></code> parameters
to an invariant and the <code class="docutils literal notranslate"><span class="pre">env</span></code> variables defined by the <code class="docutils literal notranslate"><span class="pre">with</span></code> declaration.
Compare the following to the previous example:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell7"><span></span><span class="k">invariant</span><span class="w"> </span><span class="nc">zero_address_has_no_balance_v2</span><span class="p">(</span><span class="kt">env</span><span class="w"> </span>e<span class="p">)</span>
<span class="w">    </span>balanceOf<span class="p">(</span>e<span class="p">,</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">)</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="m m-Decimal">0</span>
<span class="w">    </span><span class="p">{</span><span class="w"> </span><span class="kr">preserved</span><span class="w"> </span><span class="p">{</span><span class="w"> </span><span class="kr">require</span><span class="w"> </span>e<span class="p">.</span><span class="kc">msg.sender</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">;</span><span class="w"> </span><span class="p">}</span><span class="w"> </span><span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell7">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>In this example, we require the <code class="docutils literal notranslate"><span class="pre">msg.sender</span></code> argument to <code class="docutils literal notranslate"><span class="pre">balanceOf</span></code> to be
nonzero, but makes no restrictions on the environment for the call to the method
we are checking for preservation.</p>
<p>To see why this is not the desired behavior, consider a <code class="docutils literal notranslate"><span class="pre">deposit</span></code> method that
increases the message sender’s balance.  When the
<code class="docutils literal notranslate"><span class="pre">zero_address_has_no_balance_v2</span></code> invariant is checked on <code class="docutils literal notranslate"><span class="pre">deposit</span></code>, the Prover
will effectively check the following (see <a class="reference internal" href="#invariant-as-rule"><span class="std std-ref">Writing an invariant as a rule</span></a>):</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell8"><span></span><span class="kt">env</span><span class="w"> </span>e<span class="p">;</span>
<span class="kr">require</span><span class="w"> </span>balanceOf<span class="p">(</span>e<span class="p">,</span><span class="m m-Decimal">0</span><span class="p">)</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">;</span>

<span class="kt">env</span><span class="w"> </span>calledEnv<span class="p">;</span>
<span class="kr">require</span><span class="w"> </span>e<span class="p">.</span><span class="kc">msg.sender</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">;</span><span class="w"> </span><span class="c1">// from the `preserved` block</span>
deposit<span class="p">(</span>calledEnv<span class="p">,</span><span class="w"> </span><span class="p">...);</span>

<span class="kr">assert</span><span class="w"> </span>balanceOf<span class="p">(</span>e<span class="p">,</span><span class="m m-Decimal">0</span><span class="p">)</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">;</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell8">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>Notice that the <code class="docutils literal notranslate"><span class="pre">calledEnv</span></code> is not restricted by the <code class="docutils literal notranslate"><span class="pre">preserved</span></code> block.</p>
<p>The Prover will report a violation with the <code class="docutils literal notranslate"><span class="pre">msg.sender</span></code> set to 0 in the call to <code class="docutils literal notranslate"><span class="pre">deposit</span></code>
and set to a nonzero value in the calls to <code class="docutils literal notranslate"><span class="pre">balanceOf</span></code>.  This counterexample is
not ruled out by the <code class="docutils literal notranslate"><span class="pre">preserved</span></code> block because the <code class="docutils literal notranslate"><span class="pre">preserved</span></code> block only
places restrictions on the environment passed to <code class="docutils literal notranslate"><span class="pre">balanceOf</span></code>.</p>
<p>In general, you should be cautious of invariants that depend on an environment.</p>
</div>
</section>
</section>
<section id="filters">
<span id="invariant-filters"></span><h2><a class="toc-backref" href="#id10" role="doc-backlink">Filters</a><a class="headerlink" href="#filters" title="Link to this heading"></a></h2>
<p>For performance reasons, you may want to avoid checking that an invariant is
preserved by a particular method or set of methods.  Invariant filters provide
a method for skipping verification on a method-by-method basis.</p>
<div class="admonition caution">
<p class="admonition-title">Caution</p>
<p>Filtering out methods while checking invariants is <a class="reference internal" href="../user-guide/glossary.html#term-unsound"><span class="xref std std-term">unsound</span></a>.  If you are
filtering out a method because the invariant doesn’t pass, consider using a
<code class="docutils literal notranslate"><span class="pre">preserved</span></code> block instead; this allows you to add assumptions in a fine-grained
way (although <code class="docutils literal notranslate"><span class="pre">preserved</span></code> blocks can also be unsound).</p>
</div>
<p>To filter out methods from an invariant, add a <code class="docutils literal notranslate"><span class="pre">filtered</span></code> block after the
expression defining the invariant.  The body of the <code class="docutils literal notranslate"><span class="pre">filtered</span></code> block must
contain a single filter of the form <code class="docutils literal notranslate"><span class="pre">var</span> <span class="pre">-&gt;</span> <span class="pre">expr</span></code>, where <code class="docutils literal notranslate"><span class="pre">var</span></code> is a variable
name, and <code class="docutils literal notranslate"><span class="pre">expr</span></code> is a boolean expression that may depend on <code class="docutils literal notranslate"><span class="pre">var</span></code>.</p>
<p>Before verifying that a method preserves an invariant, the <code class="docutils literal notranslate"><span class="pre">expr</span></code> is
evaluated with <code class="docutils literal notranslate"><span class="pre">var</span></code> bound to a <code class="docutils literal notranslate"><span class="pre">method</span></code> object.  This allows <code class="docutils literal notranslate"><span class="pre">expr</span></code> to refer
to the checked method using <code class="docutils literal notranslate"><span class="pre">var</span></code>’s fields, such as <code class="docutils literal notranslate"><span class="pre">var.selector</span></code>,
<code class="docutils literal notranslate"><span class="pre">var.contract</span></code>, and <code class="docutils literal notranslate"><span class="pre">var.isView</span></code>.  See <a class="reference internal" href="types.html#method-type"><span class="std std-ref">The method and calldataarg types</span></a> for a list of the
fields available on <code class="docutils literal notranslate"><span class="pre">method</span></code> objects.</p>
<p>If the expression evaluates to <code class="docutils literal notranslate"><span class="pre">false</span></code> with <code class="docutils literal notranslate"><span class="pre">var</span></code> replaced by a given method,
the Prover will not check that the method preserves the invariant.  For example,
the following invariant will not be checked on the <code class="docutils literal notranslate"><span class="pre">deposit(uint)</span></code>
method:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell9"><span></span><span class="k">invariant</span><span class="w"> </span><span class="nc">balance_is_0</span><span class="p">(</span><span class="kt">address</span><span class="w"> </span>a<span class="p">)</span>
<span class="w">    </span>balanceOf<span class="p">(</span>a<span class="p">)</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="m m-Decimal">0</span>
<span class="w">    </span><span class="kr">filtered</span><span class="w"> </span><span class="p">{</span>
<span class="w">        </span>f<span class="w"> </span><span class="o">-&gt;</span><span class="w"> </span>f<span class="p">.</span><span class="nb">selector</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="kd">sig</span><span class="o">:</span><span class="nf">deposit</span><span class="p">(</span><span class="kt">uint</span><span class="p">).</span><span class="nb">selector</span>
<span class="w">    </span><span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell9">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>In this example, when the variable <code class="docutils literal notranslate"><span class="pre">f</span></code> is bound to <code class="docutils literal notranslate"><span class="pre">deposit(uint)</span></code>, the
expression <code class="docutils literal notranslate"><span class="pre">f.selector</span> <span class="pre">!=</span> <span class="pre">sig:deposit(uint).selector</span></code> evaluates to <code class="docutils literal notranslate"><span class="pre">false</span></code>, so the
method will be skipped.</p>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>If there is a <a class="reference internal" href="#preserved"><span class="std std-ref">preserved block</span></a> for a method, the method will
be verified even if the filter would normally exclude it.</p>
</div>
</section>
<section id="induction-step-for-transient-storage">
<h2><a class="toc-backref" href="#id11" role="doc-backlink">Induction Step for Transient Storage</a><a class="headerlink" href="#induction-step-for-transient-storage" title="Link to this heading"></a></h2>
<p>With the introduction of transient storage in Solidity (<a class="reference external" href="https://eips.ethereum.org/EIPS/eip-1153">EIP-1153</a>,
Solidity contracts can now use a <code class="docutils literal notranslate"><span class="pre">tload</span></code> or <code class="docutils literal notranslate"><span class="pre">tstore</span></code> instruction to perform <code class="docutils literal notranslate"><span class="pre">load</span></code> and <code class="docutils literal notranslate"><span class="pre">store</span></code> on transient storage.
The transient storage will be reset after a transaction has terminated.</p>
<p>The Prover will automatically detect if any contract in the scene uses <code class="docutils literal notranslate"><span class="pre">tload</span></code> and <code class="docutils literal notranslate"><span class="pre">tstore</span></code>
and adds another induction step for transient storage. This induction step
verifies the invariant is independent from the transient storage, i.e, it will assume the
invariant in pre-state, perform a reset of the transient storage and <code class="docutils literal notranslate"><span class="pre">assert</span></code> the invariant
in post-state.</p>
</section>
<section id="writing-an-invariant-as-a-rule">
<span id="invariant-as-rule"></span><h2><a class="toc-backref" href="#id12" role="doc-backlink">Writing an invariant as a rule</a><a class="headerlink" href="#writing-an-invariant-as-a-rule" title="Link to this heading"></a></h2>
<p>Above we explained that verifying an invariant requires two checks: an
initial-state check that the constructor establishes the invariant, and a
preservation check that each method preserves the invariant.</p>
<p>Invariants are the only mechanism in CVL for specifying properties of
constructors, but <a class="reference internal" href="../user-guide/glossary.html#term-parametric-rule"><span class="xref std std-term">parametric rule</span></a>s can be used to write the
preservation check in a different way.  This is useful for two reasons: First,
it can help you understand what the preservation check is doing. Second, it
can help break down a complicated invariant by defining new intermediate
variables.</p>
<p>The following example demonstrates all of the features of invariants:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell10"><span></span><span class="k">invariant</span><span class="w"> </span><span class="nc">complex_example</span><span class="p">(</span><span class="kt">env</span><span class="w"> </span>e1<span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>arg<span class="p">)</span>
<span class="w">    </span>property_of<span class="p">(</span>e1<span class="p">,</span><span class="w"> </span>arg<span class="p">)</span>
<span class="w">    </span><span class="kr">filtered</span><span class="w"> </span><span class="p">{</span>
<span class="w">        </span>m<span class="w"> </span><span class="o">-&gt;</span><span class="w"> </span>m<span class="p">.</span><span class="nb">selector</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="kd">sig</span><span class="o">:</span><span class="nf">ignored</span><span class="p">(</span><span class="kt">uint</span><span class="p">,</span><span class="w"> </span><span class="kt">address</span><span class="p">).</span><span class="nb">selector</span>
<span class="w">    </span><span class="p">}</span>
<span class="w">    </span><span class="p">{</span>
<span class="w">        </span><span class="kr">preserved</span><span class="w"> </span>with<span class="w"> </span><span class="p">(</span><span class="kt">env</span><span class="w"> </span>e2<span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">            </span><span class="kr">require</span><span class="w"> </span>e2<span class="p">.</span><span class="kc">msg.sender</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">;</span>
<span class="w">        </span><span class="p">}</span>
<span class="w">        </span><span class="kr">preserved</span><span class="w"> </span>special_method<span class="p">(</span><span class="kt">address</span><span class="w"> </span>a<span class="p">)</span><span class="w"> </span>with<span class="w"> </span><span class="p">(</span><span class="kt">env</span><span class="w"> </span>e3<span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">            </span><span class="kr">require</span><span class="w"> </span>a<span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">;</span>
<span class="w">            </span><span class="kr">require</span><span class="w"> </span>e3<span class="p">.</span><span class="kc">block.timestamp</span><span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">;</span>
<span class="w">        </span><span class="p">}</span>
<span class="w">    </span><span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell10">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>The preservation check for this invariant could be written as a
<a class="reference internal" href="../user-guide/glossary.html#term-parametric-rule"><span class="xref std std-term">parametric rule</span></a> as follows:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell11"><span></span><span class="k">rule</span><span class="w"> </span><span class="nc">complex_example_as_rule</span><span class="p">(</span><span class="kt">env</span><span class="w"> </span>e1<span class="p">,</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>arg<span class="p">,</span><span class="w"> </span><span class="kt">method</span><span class="w"> </span>f<span class="p">)</span>
<span class="kr">filtered</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span>f<span class="w"> </span><span class="o">-&gt;</span><span class="w"> </span>f<span class="p">.</span><span class="nb">selector</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="kd">sig</span><span class="o">:</span><span class="nf">ignored</span><span class="p">(</span><span class="kt">uint</span><span class="p">,</span><span class="w"> </span><span class="kt">address</span><span class="p">).</span><span class="nb">selector</span>
<span class="p">}</span>
<span class="p">{</span>
<span class="w">    </span><span class="c1">// pre-state check</span>
<span class="w">    </span><span class="kr">require</span><span class="w"> </span>property_of<span class="p">(</span>e1<span class="p">,</span><span class="w"> </span>arg<span class="p">);</span>

<span class="w">    </span><span class="kr">if</span><span class="w"> </span><span class="p">(</span>f<span class="p">.</span><span class="nb">selector</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="kd">sig</span><span class="o">:</span><span class="nf">special_method</span><span class="p">(</span><span class="kt">address</span><span class="p">).</span><span class="nb">selector</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">        </span><span class="c1">// special_method preserved block</span>
<span class="w">        </span><span class="kt">address</span><span class="w"> </span>a<span class="p">;</span>
<span class="w">        </span><span class="kt">env</span><span class="w"> </span>e3<span class="p">;</span>
<span class="w">        </span><span class="kr">require</span><span class="w"> </span>a<span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">;</span>
<span class="w">        </span><span class="kr">require</span><span class="w"> </span>e3<span class="p">.</span><span class="kc">block.timestamp</span><span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">;</span>

<span class="w">        </span><span class="c1">// method execution</span>
<span class="w">        </span>special_method<span class="p">(</span>e3<span class="p">,</span><span class="w"> </span>a<span class="p">);</span>
<span class="w">    </span><span class="p">}</span><span class="w"> </span><span class="kr">else</span><span class="w"> </span><span class="p">{</span>
<span class="w">        </span><span class="c1">// general preserved block</span>
<span class="w">        </span><span class="kt">calldataarg</span><span class="w"> </span>args<span class="p">;</span>
<span class="w">        </span><span class="kt">env</span><span class="w"> </span>e2<span class="p">;</span>
<span class="w">        </span><span class="kr">require</span><span class="w"> </span>e2<span class="p">.</span><span class="kc">msg.sender</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">;</span>

<span class="w">        </span><span class="c1">// method execution</span>
<span class="w">        </span>f<span class="p">(</span>e2<span class="p">,</span><span class="w"> </span>args<span class="p">);</span>
<span class="w">    </span><span class="p">}</span>

<span class="w">    </span><span class="c1">// post-state check</span>
<span class="w">    </span><span class="kr">assert</span><span class="w"> </span>property_of<span class="p">(</span>e1<span class="p">,</span><span class="w"> </span>arg<span class="p">);</span>
<span class="p">}</span>
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
<section id="invariants-and-induction">
<span id="invariant-induction"></span><h2><a class="toc-backref" href="#id13" role="doc-backlink">Invariants and induction</a><a class="headerlink" href="#invariants-and-induction" title="Link to this heading"></a></h2>
<p>This section describes the logical justification for invariant checks.  You do
not need to understand this section to use the Prover correctly, but it helps
explain the connection between the invariant checks and mathematical proofs for
those who are familiar with writing proofs.  This section also justifies the
safety of arbitrary <code class="docutils literal notranslate"><span class="pre">requireInvariant</span></code> statements in <code class="docutils literal notranslate"><span class="pre">preserved</span></code> blocks.</p>
<p>This section assumes familiarity with basic proofs by induction.  We use the
symbols <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="0" style="font-size: 116.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-texatom texclass="ORD"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2200"></mjx-c></mjx-mo></mjx-texatom></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mrow data-mjx-texclass="ORD"><mo>∀</mo></mrow></math></mjx-assistive-mml></mjx-container></span>, <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="1" style="font-size: 116.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mo class="mjx-n"><mjx-c class="mjx-c21D2"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo stretchy="false">⇒</mo></math></mjx-assistive-mml></mjx-container></span>, and <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="2" style="font-size: 116.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2227"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo>∧</mo></math></mjx-assistive-mml></mjx-container></span> to stand for “for all”, “implies”,
and “and” respectively.</p>
<p>Consider an invariant <code class="docutils literal notranslate"><span class="pre">i(x)</span></code> that is verified by the Prover.  For the moment,
let’s assume that <code class="docutils literal notranslate"><span class="pre">i(x)</span></code> has no <code class="docutils literal notranslate"><span class="pre">preserved</span></code> blocks. We will prove that for all
reachable states of the contract, <code class="docutils literal notranslate"><span class="pre">i(x)</span></code> is <code class="docutils literal notranslate"><span class="pre">true</span></code>.</p>
<p>A state <code class="docutils literal notranslate"><span class="pre">s</span></code> is reachable if we can start with an newly created state (that is,
where all storage variables are 0), apply any constructor, and then call any
number of contract methods to produce <code class="docutils literal notranslate"><span class="pre">s</span></code>.</p>
<p>Let <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="3" style="font-size: 116.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-msub><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D443 TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: -0.15em; margin-left: -0.109em;"><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D456 TEX-I"></mjx-c></mjx-mi></mjx-script></mjx-msub><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="2"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><msub><mi>P</mi><mi>i</mi></msub><mo stretchy="false">(</mo><mi>x</mi><mo>,</mo><mi>n</mi><mo stretchy="false">)</mo></math></mjx-assistive-mml></mjx-container></span> be the statement “if we start from the newly created
state, apply any constructor, and then call <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="4" style="font-size: 116.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>n</mi></math></mjx-assistive-mml></mjx-container></span> contract methods, then
the resulting state satisfies <code class="docutils literal notranslate"><span class="pre">i(x)</span></code>.”  Our goal is then to prove
<span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="5" style="font-size: 116.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-texatom texclass="ORD"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2200"></mjx-c></mjx-mo></mjx-texatom><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-texatom space="2" texclass="ORD"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2200"></mjx-c></mjx-mo></mjx-texatom><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-msub space="2"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D443 TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: -0.15em; margin-left: -0.109em;"><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D456 TEX-I"></mjx-c></mjx-mi></mjx-script></mjx-msub><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="2"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mrow data-mjx-texclass="ORD"><mo>∀</mo></mrow><mi>n</mi><mo>,</mo><mrow data-mjx-texclass="ORD"><mo>∀</mo></mrow><mi>x</mi><mo>,</mo><msub><mi>P</mi><mi>i</mi></msub><mo stretchy="false">(</mo><mi>x</mi><mo>,</mo><mi>n</mi><mo stretchy="false">)</mo></math></mjx-assistive-mml></mjx-container></span>.  We will prove this by induction on <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="6" style="font-size: 116.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>n</mi></math></mjx-assistive-mml></mjx-container></span>.</p>
<p>In the base case we want to show that for any <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="7" style="font-size: 116.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>x</mi></math></mjx-assistive-mml></mjx-container></span>, if we apply any
constructor to the newly created contract, that the resulting state satisfies
<code class="docutils literal notranslate"><span class="pre">i(x)</span></code>.  This is exactly what the Prover verifies in the initial state check.
In other words, the initial state check proves that <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="8" style="font-size: 116.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-texatom texclass="ORD"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2200"></mjx-c></mjx-mo></mjx-texatom><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-msub space="2"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D443 TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: -0.15em; margin-left: -0.109em;"><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D456 TEX-I"></mjx-c></mjx-mi></mjx-script></mjx-msub><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mn class="mjx-n" space="2"><mjx-c class="mjx-c30"></mjx-c></mjx-mn><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mrow data-mjx-texclass="ORD"><mo>∀</mo></mrow><mi>x</mi><mo>,</mo><msub><mi>P</mi><mi>i</mi></msub><mo stretchy="false">(</mo><mi>x</mi><mo>,</mo><mn>0</mn><mo stretchy="false">)</mo></math></mjx-assistive-mml></mjx-container></span>.</p>
<p>For the inductive step, we assume that any <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="9" style="font-size: 116.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>n</mi></math></mjx-assistive-mml></mjx-container></span> contract calls produce a
state that satisfies <code class="docutils literal notranslate"><span class="pre">i(x)</span></code>, and we want to show that a state produced after
<span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="10" style="font-size: 116.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2B"></mjx-c></mjx-mo><mjx-mn class="mjx-n" space="3"><mjx-c class="mjx-c31"></mjx-c></mjx-mn></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>n</mi><mo>+</mo><mn>1</mn></math></mjx-assistive-mml></mjx-container></span> calls also satisfies <code class="docutils literal notranslate"><span class="pre">i(x)</span></code>.  This is exactly what the Prover
verifies in the preservation check: that if the state before the last method
call satisfies <code class="docutils literal notranslate"><span class="pre">i(x)</span></code> then after the last method call it still satisfies
<code class="docutils literal notranslate"><span class="pre">i(x)</span></code>.  In other words, the preservation check proves that
<span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="11" style="font-size: 116.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-texatom texclass="ORD"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2200"></mjx-c></mjx-mo></mjx-texatom><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-texatom space="2" texclass="ORD"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2200"></mjx-c></mjx-mo></mjx-texatom><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-msub space="2"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D443 TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: -0.15em; margin-left: -0.109em;"><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D456 TEX-I"></mjx-c></mjx-mi></mjx-script></mjx-msub><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="2"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c21D2"></mjx-c></mjx-mo><mjx-msub space="4"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D443 TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: -0.15em; margin-left: -0.109em;"><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D456 TEX-I"></mjx-c></mjx-mi></mjx-script></mjx-msub><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="2"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2B"></mjx-c></mjx-mo><mjx-mn class="mjx-n" space="3"><mjx-c class="mjx-c31"></mjx-c></mjx-mn><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mrow data-mjx-texclass="ORD"><mo>∀</mo></mrow><mi>n</mi><mo>,</mo><mrow data-mjx-texclass="ORD"><mo>∀</mo></mrow><mi>x</mi><mo>,</mo><msub><mi>P</mi><mi>i</mi></msub><mo stretchy="false">(</mo><mi>x</mi><mo>,</mo><mi>n</mi><mo stretchy="false">)</mo><mo stretchy="false">⇒</mo><msub><mi>P</mi><mi>i</mi></msub><mo stretchy="false">(</mo><mi>x</mi><mo>,</mo><mi>n</mi><mo>+</mo><mn>1</mn><mo stretchy="false">)</mo></math></mjx-assistive-mml></mjx-container></span>.</p>
<p>This completes the proof that together, the initial state check and the
preservation check ensure that the invariant <code class="docutils literal notranslate"><span class="pre">i</span></code> holds on all reachable states.</p>
<p>Now, let us consider preserved blocks.  Adding <code class="docutils literal notranslate"><span class="pre">require</span></code> statements to a
<code class="docutils literal notranslate"><span class="pre">preserved</span></code> block for invariant <code class="docutils literal notranslate"><span class="pre">i</span></code> adds an additional assumption <code class="docutils literal notranslate"><span class="pre">Q</span></code> to the
preservation check.  Now, instead of</p>
<div class="math notranslate nohighlight">
<mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" display="true" tabindex="0" ctxtmenu_counter="12" style="font-size: 116.9%; position: relative;"><mjx-math display="true" class="MJX-TEX" aria-hidden="true" style="margin-left: 0px; margin-right: 0px;"><mjx-texatom texclass="ORD"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2200"></mjx-c></mjx-mo></mjx-texatom><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-texatom space="2" texclass="ORD"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2200"></mjx-c></mjx-mo></mjx-texatom><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-msub space="2"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D443 TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: -0.15em; margin-left: -0.109em;"><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D456 TEX-I"></mjx-c></mjx-mi></mjx-script></mjx-msub><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="2"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c21D2"></mjx-c></mjx-mo><mjx-msub space="4"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D443 TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: -0.15em; margin-left: -0.109em;"><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D456 TEX-I"></mjx-c></mjx-mi></mjx-script></mjx-msub><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="2"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2B"></mjx-c></mjx-mo><mjx-mn class="mjx-n" space="3"><mjx-c class="mjx-c31"></mjx-c></mjx-mn><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="block"><math xmlns="http://www.w3.org/1998/Math/MathML" display="block"><mrow data-mjx-texclass="ORD"><mo>∀</mo></mrow><mi>n</mi><mo>,</mo><mrow data-mjx-texclass="ORD"><mo>∀</mo></mrow><mi>x</mi><mo>,</mo><msub><mi>P</mi><mi>i</mi></msub><mo stretchy="false">(</mo><mi>x</mi><mo>,</mo><mi>n</mi><mo stretchy="false">)</mo><mo stretchy="false">⇒</mo><msub><mi>P</mi><mi>i</mi></msub><mo stretchy="false">(</mo><mi>x</mi><mo>,</mo><mi>n</mi><mo>+</mo><mn>1</mn><mo stretchy="false">)</mo><mo>,</mo></math></mjx-assistive-mml></mjx-container></div>
<p>the preservation check only proves</p>
<div class="math notranslate nohighlight">
<mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" display="true" tabindex="0" ctxtmenu_counter="13" style="font-size: 116.9%; position: relative;"><mjx-math display="true" class="MJX-TEX" aria-hidden="true" style="margin-left: 0px; margin-right: 0px;"><mjx-texatom texclass="ORD"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2200"></mjx-c></mjx-mo></mjx-texatom><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-texatom space="2" texclass="ORD"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2200"></mjx-c></mjx-mo></mjx-texatom><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-msub space="2"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D443 TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: -0.15em; margin-left: -0.109em;"><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D456 TEX-I"></mjx-c></mjx-mi></mjx-script></mjx-msub><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="2"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo><mjx-texatom texclass="ORD"><mjx-mo class="mjx-b"><mjx-c class="mjx-c2227 TEX-B"></mjx-c></mjx-mo><mjx-mi class="mjx-b"><mjx-c class="mjx-c1D410 TEX-B"></mjx-c></mjx-mi></mjx-texatom><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c21D2"></mjx-c></mjx-mo><mjx-msub space="4"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D443 TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: -0.15em; margin-left: -0.109em;"><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D456 TEX-I"></mjx-c></mjx-mi></mjx-script></mjx-msub><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="2"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2B"></mjx-c></mjx-mo><mjx-mn class="mjx-n" space="3"><mjx-c class="mjx-c31"></mjx-c></mjx-mn><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo><mjx-mo class="mjx-n"><mjx-c class="mjx-c2E"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="block"><math xmlns="http://www.w3.org/1998/Math/MathML" display="block"><mrow data-mjx-texclass="ORD"><mo>∀</mo></mrow><mi>n</mi><mo>,</mo><mrow data-mjx-texclass="ORD"><mo>∀</mo></mrow><mi>x</mi><mo>,</mo><msub><mi>P</mi><mi>i</mi></msub><mo stretchy="false">(</mo><mi>x</mi><mo>,</mo><mi>n</mi><mo stretchy="false">)</mo><mrow data-mjx-texclass="ORD"><mo mathvariant="bold">∧</mo><mi mathvariant="bold">Q</mi></mrow><mo stretchy="false">⇒</mo><msub><mi>P</mi><mi>i</mi></msub><mo stretchy="false">(</mo><mi>x</mi><mo>,</mo><mi>n</mi><mo>+</mo><mn>1</mn><mo stretchy="false">)</mo><mo>.</mo></math></mjx-assistive-mml></mjx-container></div>
<p>The addition of the assumption <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="14" style="font-size: 116.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D444 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>Q</mi></math></mjx-assistive-mml></mjx-container></span> invalidates the above proof if we don’t
have reason to believe that <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="15" style="font-size: 116.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D444 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>Q</mi></math></mjx-assistive-mml></mjx-container></span> actually holds, which is why we caution
against adding <code class="docutils literal notranslate"><span class="pre">require</span></code> statements to <code class="docutils literal notranslate"><span class="pre">preserved</span></code> blocks.</p>
<p>However, it is important to note that adding <code class="docutils literal notranslate"><span class="pre">requireInvariant</span> <span class="pre">j(y)</span></code> to a
<code class="docutils literal notranslate"><span class="pre">preserved</span></code> block is safe (assuming that <code class="docutils literal notranslate"><span class="pre">j</span></code> is verified), even if the
<code class="docutils literal notranslate"><span class="pre">preserved</span></code> block for <code class="docutils literal notranslate"><span class="pre">j</span></code> requires the invariant <code class="docutils literal notranslate"><span class="pre">i</span></code>.  To demonstrate this, we
consider three examples.</p>
<p>For the first example, consider the spec</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell12"><span></span><span class="k">invariant</span><span class="w"> </span><span class="nc">i</span><span class="p">(</span><span class="kt">uint</span><span class="w"> </span>x<span class="p">)</span><span class="w"> </span><span class="p">...</span><span class="w"> </span><span class="p">{</span><span class="w"> </span><span class="kr">preserved</span><span class="w"> </span><span class="p">{</span><span class="w"> </span><span class="kr">requireInvariant</span><span class="w"> </span>i<span class="p">(</span>x<span class="p">);</span><span class="w"> </span><span class="p">}</span><span class="w"> </span><span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell12">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>Although this may seem like circular logic (we require <code class="docutils literal notranslate"><span class="pre">i</span></code> in the proof of
<code class="docutils literal notranslate"><span class="pre">i</span></code>), it is not.  The verification of the preservation check for <code class="docutils literal notranslate"><span class="pre">i</span></code> proves the
statement</p>
<div class="math notranslate nohighlight">
<mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" display="true" tabindex="0" ctxtmenu_counter="16" style="font-size: 116.9%; position: relative;"><mjx-math display="true" class="MJX-TEX" aria-hidden="true" style="margin-left: 0px; margin-right: 0px;"><mjx-texatom texclass="ORD"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2200"></mjx-c></mjx-mo></mjx-texatom><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-texatom space="2" texclass="ORD"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2200"></mjx-c></mjx-mo></mjx-texatom><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-msub space="2"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D443 TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: -0.15em; margin-left: -0.109em;"><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D456 TEX-I"></mjx-c></mjx-mi></mjx-script></mjx-msub><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="2"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2227"></mjx-c></mjx-mo><mjx-msub space="3"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D443 TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: -0.15em; margin-left: -0.109em;"><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D456 TEX-I"></mjx-c></mjx-mi></mjx-script></mjx-msub><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="2"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c21D2"></mjx-c></mjx-mo><mjx-msub space="4"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D443 TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: -0.15em; margin-left: -0.109em;"><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D456 TEX-I"></mjx-c></mjx-mi></mjx-script></mjx-msub><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="2"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2B"></mjx-c></mjx-mo><mjx-mn class="mjx-n" space="3"><mjx-c class="mjx-c31"></mjx-c></mjx-mn><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="block"><math xmlns="http://www.w3.org/1998/Math/MathML" display="block"><mrow data-mjx-texclass="ORD"><mo>∀</mo></mrow><mi>n</mi><mo>,</mo><mrow data-mjx-texclass="ORD"><mo>∀</mo></mrow><mi>x</mi><mo>,</mo><msub><mi>P</mi><mi>i</mi></msub><mo stretchy="false">(</mo><mi>x</mi><mo>,</mo><mi>n</mi><mo stretchy="false">)</mo><mo>∧</mo><msub><mi>P</mi><mi>i</mi></msub><mo stretchy="false">(</mo><mi>x</mi><mo>,</mo><mi>n</mi><mo stretchy="false">)</mo><mo stretchy="false">⇒</mo><msub><mi>P</mi><mi>i</mi></msub><mo stretchy="false">(</mo><mi>x</mi><mo>,</mo><mi>n</mi><mo>+</mo><mn>1</mn><mo stretchy="false">)</mo><mo>,</mo></math></mjx-assistive-mml></mjx-container></div>
<p>which is logically equivalent
to the preservation check without the <code class="docutils literal notranslate"><span class="pre">preserved</span></code> block (since <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="17" style="font-size: 116.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-msub><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D443 TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: -0.15em; margin-left: -0.109em;"><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D456 TEX-I"></mjx-c></mjx-mi></mjx-script></mjx-msub><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="2"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2227"></mjx-c></mjx-mo><mjx-msub space="3"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D443 TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: -0.15em; margin-left: -0.109em;"><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D456 TEX-I"></mjx-c></mjx-mi></mjx-script></mjx-msub><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="2"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><msub><mi>P</mi><mi>i</mi></msub><mo stretchy="false">(</mo><mi>x</mi><mo>,</mo><mi>n</mi><mo stretchy="false">)</mo><mo>∧</mo><msub><mi>P</mi><mi>i</mi></msub><mo stretchy="false">(</mo><mi>x</mi><mo>,</mo><mi>n</mi><mo stretchy="false">)</mo></math></mjx-assistive-mml></mjx-container></span>
is equivalent to just <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="18" style="font-size: 116.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-msub><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D443 TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: -0.15em; margin-left: -0.109em;"><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D456 TEX-I"></mjx-c></mjx-mi></mjx-script></mjx-msub><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="2"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><msub><mi>P</mi><mi>i</mi></msub><mo stretchy="false">(</mo><mi>x</mi><mo>,</mo><mi>n</mi><mo stretchy="false">)</mo></math></mjx-assistive-mml></mjx-container></span>).</p>
<p>For the second example, consider the following spec:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell13"><span></span><span class="k">invariant</span><span class="w"> </span><span class="nc">i</span><span class="p">(</span><span class="kt">uint</span><span class="w"> </span>x<span class="p">)</span><span class="w"> </span><span class="p">...</span><span class="w">  </span><span class="p">{</span><span class="w"> </span><span class="kr">preserved</span><span class="w"> </span><span class="p">{</span><span class="w"> </span><span class="kr">requireInvariant</span><span class="w"> </span>j<span class="p">(</span>x<span class="p">);</span><span class="w"> </span><span class="p">}</span><span class="w"> </span><span class="p">}</span>

<span class="k">invariant</span><span class="w"> </span><span class="nc">j</span><span class="p">(</span><span class="kt">uint</span><span class="w"> </span>x<span class="p">)</span><span class="w"> </span><span class="p">...</span><span class="w">  </span><span class="p">{</span><span class="w"> </span><span class="kr">preserved</span><span class="w"> </span><span class="p">{</span><span class="w"> </span><span class="kr">requireInvariant</span><span class="w"> </span>i<span class="p">(</span>x<span class="p">);</span><span class="w"> </span><span class="p">}</span><span class="w"> </span><span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell13">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>Verifying these invariants gives us the preservation check for <code class="docutils literal notranslate"><span class="pre">i</span></code>:</p>
<div class="math notranslate nohighlight">
<mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" display="true" tabindex="0" ctxtmenu_counter="19" style="font-size: 116.9%; position: relative;"><mjx-math display="true" class="MJX-TEX" aria-hidden="true" style="margin-left: 0px; margin-right: 0px;"><mjx-texatom texclass="ORD"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2200"></mjx-c></mjx-mo></mjx-texatom><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-texatom space="2" texclass="ORD"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2200"></mjx-c></mjx-mo></mjx-texatom><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-msub space="2"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D443 TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: -0.15em; margin-left: -0.109em;"><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D456 TEX-I"></mjx-c></mjx-mi></mjx-script></mjx-msub><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="2"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2227"></mjx-c></mjx-mo><mjx-msub space="3"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D443 TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: -0.15em; margin-left: -0.109em;"><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D457 TEX-I"></mjx-c></mjx-mi></mjx-script></mjx-msub><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="2"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c21D2"></mjx-c></mjx-mo><mjx-msub space="4"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D443 TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: -0.15em; margin-left: -0.109em;"><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D456 TEX-I"></mjx-c></mjx-mi></mjx-script></mjx-msub><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="2"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2B"></mjx-c></mjx-mo><mjx-mn class="mjx-n" space="3"><mjx-c class="mjx-c31"></mjx-c></mjx-mn><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="block"><math xmlns="http://www.w3.org/1998/Math/MathML" display="block"><mrow data-mjx-texclass="ORD"><mo>∀</mo></mrow><mi>n</mi><mo>,</mo><mrow data-mjx-texclass="ORD"><mo>∀</mo></mrow><mi>x</mi><mo>,</mo><msub><mi>P</mi><mi>i</mi></msub><mo stretchy="false">(</mo><mi>x</mi><mo>,</mo><mi>n</mi><mo stretchy="false">)</mo><mo>∧</mo><msub><mi>P</mi><mi>j</mi></msub><mo stretchy="false">(</mo><mi>x</mi><mo>,</mo><mi>n</mi><mo stretchy="false">)</mo><mo stretchy="false">⇒</mo><msub><mi>P</mi><mi>i</mi></msub><mo stretchy="false">(</mo><mi>x</mi><mo>,</mo><mi>n</mi><mo>+</mo><mn>1</mn><mo stretchy="false">)</mo></math></mjx-assistive-mml></mjx-container></div>
<p>and for <code class="docutils literal notranslate"><span class="pre">j</span></code>:</p>
<div class="math notranslate nohighlight">
<mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" display="true" tabindex="0" ctxtmenu_counter="20" style="font-size: 116.9%; position: relative;"><mjx-math display="true" class="MJX-TEX" aria-hidden="true" style="margin-left: 0px; margin-right: 0px;"><mjx-texatom texclass="ORD"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2200"></mjx-c></mjx-mo></mjx-texatom><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-texatom space="2" texclass="ORD"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2200"></mjx-c></mjx-mo></mjx-texatom><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-msub space="2"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D443 TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: -0.15em; margin-left: -0.109em;"><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D457 TEX-I"></mjx-c></mjx-mi></mjx-script></mjx-msub><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="2"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2227"></mjx-c></mjx-mo><mjx-msub space="3"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D443 TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: -0.15em; margin-left: -0.109em;"><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D456 TEX-I"></mjx-c></mjx-mi></mjx-script></mjx-msub><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="2"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c21D2"></mjx-c></mjx-mo><mjx-msub space="4"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D443 TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: -0.15em; margin-left: -0.109em;"><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D457 TEX-I"></mjx-c></mjx-mi></mjx-script></mjx-msub><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="2"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2B"></mjx-c></mjx-mo><mjx-mn class="mjx-n" space="3"><mjx-c class="mjx-c31"></mjx-c></mjx-mn><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="block"><math xmlns="http://www.w3.org/1998/Math/MathML" display="block"><mrow data-mjx-texclass="ORD"><mo>∀</mo></mrow><mi>n</mi><mo>,</mo><mrow data-mjx-texclass="ORD"><mo>∀</mo></mrow><mi>x</mi><mo>,</mo><msub><mi>P</mi><mi>j</mi></msub><mo stretchy="false">(</mo><mi>x</mi><mo>,</mo><mi>n</mi><mo stretchy="false">)</mo><mo>∧</mo><msub><mi>P</mi><mi>i</mi></msub><mo stretchy="false">(</mo><mi>x</mi><mo>,</mo><mi>n</mi><mo stretchy="false">)</mo><mo stretchy="false">⇒</mo><msub><mi>P</mi><mi>j</mi></msub><mo stretchy="false">(</mo><mi>x</mi><mo>,</mo><mi>n</mi><mo>+</mo><mn>1</mn><mo stretchy="false">)</mo></math></mjx-assistive-mml></mjx-container></div>
<p>Putting these together allows us to conclude</p>
<div class="math notranslate nohighlight">
<mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" display="true" tabindex="0" ctxtmenu_counter="21" style="font-size: 116.9%; position: relative;"><mjx-math display="true" class="MJX-TEX" aria-hidden="true" style="margin-left: 0px; margin-right: 0px;"><mjx-texatom texclass="ORD"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2200"></mjx-c></mjx-mo></mjx-texatom><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-texatom space="2" texclass="ORD"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2200"></mjx-c></mjx-mo></mjx-texatom><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-msub space="2"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D443 TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: -0.15em; margin-left: -0.109em;"><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D456 TEX-I"></mjx-c></mjx-mi></mjx-script></mjx-msub><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="2"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2227"></mjx-c></mjx-mo><mjx-msub space="3"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D443 TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: -0.15em; margin-left: -0.109em;"><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D457 TEX-I"></mjx-c></mjx-mi></mjx-script></mjx-msub><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="2"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c21D2"></mjx-c></mjx-mo><mjx-msub space="4"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D443 TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: -0.15em; margin-left: -0.109em;"><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D456 TEX-I"></mjx-c></mjx-mi></mjx-script></mjx-msub><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="2"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2B"></mjx-c></mjx-mo><mjx-mn class="mjx-n" space="3"><mjx-c class="mjx-c31"></mjx-c></mjx-mn><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2227"></mjx-c></mjx-mo><mjx-msub space="3"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D443 TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: -0.15em; margin-left: -0.109em;"><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D457 TEX-I"></mjx-c></mjx-mi></mjx-script></mjx-msub><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="2"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2B"></mjx-c></mjx-mo><mjx-mn class="mjx-n" space="3"><mjx-c class="mjx-c31"></mjx-c></mjx-mn><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="block"><math xmlns="http://www.w3.org/1998/Math/MathML" display="block"><mrow data-mjx-texclass="ORD"><mo>∀</mo></mrow><mi>n</mi><mo>,</mo><mrow data-mjx-texclass="ORD"><mo>∀</mo></mrow><mi>x</mi><mo>,</mo><msub><mi>P</mi><mi>i</mi></msub><mo stretchy="false">(</mo><mi>x</mi><mo>,</mo><mi>n</mi><mo stretchy="false">)</mo><mo>∧</mo><msub><mi>P</mi><mi>j</mi></msub><mo stretchy="false">(</mo><mi>x</mi><mo>,</mo><mi>n</mi><mo stretchy="false">)</mo><mo stretchy="false">⇒</mo><msub><mi>P</mi><mi>i</mi></msub><mo stretchy="false">(</mo><mi>x</mi><mo>,</mo><mi>n</mi><mo>+</mo><mn>1</mn><mo stretchy="false">)</mo><mo>∧</mo><msub><mi>P</mi><mi>j</mi></msub><mo stretchy="false">(</mo><mi>x</mi><mo>,</mo><mi>n</mi><mo>+</mo><mn>1</mn><mo stretchy="false">)</mo></math></mjx-assistive-mml></mjx-container></div>
<p>which is exactly what we need for an inductive proof of the statement
<span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="22" style="font-size: 116.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-texatom texclass="ORD"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2200"></mjx-c></mjx-mo></mjx-texatom><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-texatom space="2" texclass="ORD"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2200"></mjx-c></mjx-mo></mjx-texatom><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-msub space="2"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D443 TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: -0.15em; margin-left: -0.109em;"><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D456 TEX-I"></mjx-c></mjx-mi></mjx-script></mjx-msub><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="2"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2227"></mjx-c></mjx-mo><mjx-msub space="3"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D443 TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: -0.15em; margin-left: -0.109em;"><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D457 TEX-I"></mjx-c></mjx-mi></mjx-script></mjx-msub><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="2"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mrow data-mjx-texclass="ORD"><mo>∀</mo></mrow><mi>n</mi><mo>,</mo><mrow data-mjx-texclass="ORD"><mo>∀</mo></mrow><mi>x</mi><mo>,</mo><msub><mi>P</mi><mi>i</mi></msub><mo stretchy="false">(</mo><mi>x</mi><mo>,</mo><mi>n</mi><mo stretchy="false">)</mo><mo>∧</mo><msub><mi>P</mi><mi>j</mi></msub><mo stretchy="false">(</mo><mi>x</mi><mo>,</mo><mi>n</mi><mo stretchy="false">)</mo></math></mjx-assistive-mml></mjx-container></span>.  This statement then shows that both
<code class="docutils literal notranslate"><span class="pre">i(x)</span></code> and <code class="docutils literal notranslate"><span class="pre">j(x)</span></code> are true in all reachable states.</p>
<p>For the third example, consider the following spec:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre id="codecell14"><span></span><span class="k">invariant</span><span class="w"> </span><span class="nc">i</span><span class="p">(</span><span class="kt">uint</span><span class="w"> </span>x<span class="p">)</span><span class="w"> </span><span class="p">...</span><span class="w"> </span><span class="p">{</span><span class="w"> </span><span class="kr">preserved</span><span class="w"> </span><span class="p">{</span><span class="w"> </span><span class="kr">requireInvariant</span><span class="w"> </span>i<span class="p">(</span>f<span class="p">(</span>x<span class="p">));</span><span class="w"> </span><span class="p">}</span><span class="w"> </span><span class="p">}</span>
</pre><button class="copybtn o-tooltip--left" data-tooltip="Copy" data-clipboard-target="#codecell14">
      <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-copy" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
  <title>Copy to clipboard</title>
  <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
  <rect x="8" y="8" width="12" height="12" rx="2"></rect>
  <path d="M16 8v-2a2 2 0 0 0 -2 -2h-8a2 2 0 0 0 -2 2v8a2 2 0 0 0 2 2h2"></path>
</svg>
    </button></div>
</div>
<p>The preservation check now proves</p>
<div class="math notranslate nohighlight">
<mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" display="true" tabindex="0" ctxtmenu_counter="23" style="font-size: 116.9%; position: relative;"><mjx-math display="true" class="MJX-TEX" aria-hidden="true" style="margin-left: 0px; margin-right: 0px;"><mjx-texatom texclass="ORD"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2200"></mjx-c></mjx-mo></mjx-texatom><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-texatom space="2" texclass="ORD"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2200"></mjx-c></mjx-mo></mjx-texatom><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-msub space="2"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D443 TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: -0.15em; margin-left: -0.109em;"><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D456 TEX-I"></mjx-c></mjx-mi></mjx-script></mjx-msub><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="2"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2227"></mjx-c></mjx-mo><mjx-msub space="3"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D443 TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: -0.15em; margin-left: -0.109em;"><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D456 TEX-I"></mjx-c></mjx-mi></mjx-script></mjx-msub><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D453 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="2"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c21D2"></mjx-c></mjx-mo><mjx-msub space="4"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D443 TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: -0.15em; margin-left: -0.109em;"><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D456 TEX-I"></mjx-c></mjx-mi></mjx-script></mjx-msub><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="2"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2B"></mjx-c></mjx-mo><mjx-mn class="mjx-n" space="3"><mjx-c class="mjx-c31"></mjx-c></mjx-mn><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo><mjx-mo class="mjx-n"><mjx-c class="mjx-c2E"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="block"><math xmlns="http://www.w3.org/1998/Math/MathML" display="block"><mrow data-mjx-texclass="ORD"><mo>∀</mo></mrow><mi>n</mi><mo>,</mo><mrow data-mjx-texclass="ORD"><mo>∀</mo></mrow><mi>x</mi><mo>,</mo><msub><mi>P</mi><mi>i</mi></msub><mo stretchy="false">(</mo><mi>x</mi><mo>,</mo><mi>n</mi><mo stretchy="false">)</mo><mo>∧</mo><msub><mi>P</mi><mi>i</mi></msub><mo stretchy="false">(</mo><mi>f</mi><mo stretchy="false">(</mo><mi>x</mi><mo stretchy="false">)</mo><mo>,</mo><mi>n</mi><mo stretchy="false">)</mo><mo stretchy="false">⇒</mo><msub><mi>P</mi><mi>i</mi></msub><mo stretchy="false">(</mo><mi>x</mi><mo>,</mo><mi>n</mi><mo>+</mo><mn>1</mn><mo stretchy="false">)</mo><mo>.</mo></math></mjx-assistive-mml></mjx-container></div>
<p>Seeing that this gives us enough to write an inductive proof that
<span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="24" style="font-size: 116.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-texatom texclass="ORD"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2200"></mjx-c></mjx-mo></mjx-texatom><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-texatom space="2" texclass="ORD"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2200"></mjx-c></mjx-mo></mjx-texatom><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-msub space="2"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D443 TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: -0.15em; margin-left: -0.109em;"><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D456 TEX-I"></mjx-c></mjx-mi></mjx-script></mjx-msub><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="2"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mrow data-mjx-texclass="ORD"><mo>∀</mo></mrow><mi>n</mi><mo>,</mo><mrow data-mjx-texclass="ORD"><mo>∀</mo></mrow><mi>x</mi><mo>,</mo><msub><mi>P</mi><mi>i</mi></msub><mo stretchy="false">(</mo><mi>x</mi><mo>,</mo><mi>n</mi><mo stretchy="false">)</mo></math></mjx-assistive-mml></mjx-container></span> takes a little more effort, but it only requires a
simple trick.  Let <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="25" style="font-size: 116.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D444 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>Q</mi><mo stretchy="false">(</mo><mi>n</mi><mo stretchy="false">)</mo></math></mjx-assistive-mml></mjx-container></span> be the statement <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="26" style="font-size: 116.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-texatom texclass="ORD"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2200"></mjx-c></mjx-mo></mjx-texatom><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-msub space="2"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D443 TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: -0.15em; margin-left: -0.109em;"><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D456 TEX-I"></mjx-c></mjx-mi></mjx-script></mjx-msub><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="2"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mrow data-mjx-texclass="ORD"><mo>∀</mo></mrow><mi>x</mi><mo>,</mo><msub><mi>P</mi><mi>i</mi></msub><mo stretchy="false">(</mo><mi>x</mi><mo>,</mo><mi>n</mi><mo stretchy="false">)</mo></math></mjx-assistive-mml></mjx-container></span>.  We
prove <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="27" style="font-size: 116.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-texatom texclass="ORD"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2200"></mjx-c></mjx-mo></mjx-texatom><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="2"><mjx-c class="mjx-c1D444 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mrow data-mjx-texclass="ORD"><mo>∀</mo></mrow><mi>n</mi><mo>,</mo><mi>Q</mi><mo stretchy="false">(</mo><mi>n</mi><mo stretchy="false">)</mo></math></mjx-assistive-mml></mjx-container></span> by induction.</p>
<p>The base case comes directly from the initial state check for <code class="docutils literal notranslate"><span class="pre">i</span></code>.</p>
<p>For the inductive step, choose an arbitrary <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="28" style="font-size: 116.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>n</mi></math></mjx-assistive-mml></mjx-container></span> and assume <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="29" style="font-size: 116.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D444 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>Q</mi><mo stretchy="false">(</mo><mi>n</mi><mo stretchy="false">)</mo></math></mjx-assistive-mml></mjx-container></span>.
We want to show <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="30" style="font-size: 116.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D444 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2B"></mjx-c></mjx-mo><mjx-mn class="mjx-n" space="3"><mjx-c class="mjx-c31"></mjx-c></mjx-mn><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>Q</mi><mo stretchy="false">(</mo><mi>n</mi><mo>+</mo><mn>1</mn><mo stretchy="false">)</mo></math></mjx-assistive-mml></mjx-container></span>, i.e. that <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="31" style="font-size: 116.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-texatom texclass="ORD"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2200"></mjx-c></mjx-mo></mjx-texatom><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-msub space="2"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D443 TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: -0.15em; margin-left: -0.109em;"><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D456 TEX-I"></mjx-c></mjx-mi></mjx-script></mjx-msub><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="2"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2B"></mjx-c></mjx-mo><mjx-mn class="mjx-n" space="3"><mjx-c class="mjx-c31"></mjx-c></mjx-mn><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mrow data-mjx-texclass="ORD"><mo>∀</mo></mrow><mi>x</mi><mo>,</mo><msub><mi>P</mi><mi>i</mi></msub><mo stretchy="false">(</mo><mi>x</mi><mo>,</mo><mi>n</mi><mo>+</mo><mn>1</mn><mo stretchy="false">)</mo></math></mjx-assistive-mml></mjx-container></span>.  Fix an
arbitrary <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="32" style="font-size: 116.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>x</mi></math></mjx-assistive-mml></mjx-container></span>.  We can apply <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="33" style="font-size: 116.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D444 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>Q</mi><mo stretchy="false">(</mo><mi>n</mi><mo stretchy="false">)</mo></math></mjx-assistive-mml></mjx-container></span> to <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="34" style="font-size: 116.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>x</mi></math></mjx-assistive-mml></mjx-container></span> to conclude
<span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="35" style="font-size: 116.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-msub><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D443 TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: -0.15em; margin-left: -0.109em;"><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D456 TEX-I"></mjx-c></mjx-mi></mjx-script></mjx-msub><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="2"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><msub><mi>P</mi><mi>i</mi></msub><mo stretchy="false">(</mo><mi>x</mi><mo>,</mo><mi>n</mi><mo stretchy="false">)</mo></math></mjx-assistive-mml></mjx-container></span>.  We can also apply <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="36" style="font-size: 116.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D444 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>Q</mi><mo stretchy="false">(</mo><mi>n</mi><mo stretchy="false">)</mo></math></mjx-assistive-mml></mjx-container></span> to <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="37" style="font-size: 116.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D453 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>f</mi><mo stretchy="false">(</mo><mi>x</mi><mo stretchy="false">)</mo></math></mjx-assistive-mml></mjx-container></span> to conclude
<span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="38" style="font-size: 116.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-msub><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D443 TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: -0.15em; margin-left: -0.109em;"><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D456 TEX-I"></mjx-c></mjx-mi></mjx-script></mjx-msub><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D453 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="2"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><msub><mi>P</mi><mi>i</mi></msub><mo stretchy="false">(</mo><mi>f</mi><mo stretchy="false">(</mo><mi>x</mi><mo stretchy="false">)</mo><mo>,</mo><mi>n</mi><mo stretchy="false">)</mo></math></mjx-assistive-mml></mjx-container></span>.  These facts together with the preservation check show
<span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="39" style="font-size: 116.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-msub><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D443 TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: -0.15em; margin-left: -0.109em;"><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D456 TEX-I"></mjx-c></mjx-mi></mjx-script></mjx-msub><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="2"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2B"></mjx-c></mjx-mo><mjx-mn class="mjx-n" space="3"><mjx-c class="mjx-c31"></mjx-c></mjx-mn><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><msub><mi>P</mi><mi>i</mi></msub><mo stretchy="false">(</mo><mi>x</mi><mo>,</mo><mi>n</mi><mo>+</mo><mn>1</mn><mo stretchy="false">)</mo></math></mjx-assistive-mml></mjx-container></span>.  Since <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="40" style="font-size: 116.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>x</mi></math></mjx-assistive-mml></mjx-container></span> was arbitrary, we can conclude
<span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="41" style="font-size: 116.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-texatom texclass="ORD"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2200"></mjx-c></mjx-mo></mjx-texatom><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="2"><mjx-c class="mjx-c1D443 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="2"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2B"></mjx-c></mjx-mo><mjx-mn class="mjx-n" space="3"><mjx-c class="mjx-c31"></mjx-c></mjx-mn><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mrow data-mjx-texclass="ORD"><mo>∀</mo></mrow><mi>x</mi><mo>,</mo><mi>P</mi><mo stretchy="false">(</mo><mi>x</mi><mo>,</mo><mi>n</mi><mo>+</mo><mn>1</mn><mo stretchy="false">)</mo></math></mjx-assistive-mml></mjx-container></span>, which is <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="42" style="font-size: 116.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D444 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2B"></mjx-c></mjx-mo><mjx-mn class="mjx-n" space="3"><mjx-c class="mjx-c31"></mjx-c></mjx-mn><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>Q</mi><mo stretchy="false">(</mo><mi>n</mi><mo>+</mo><mn>1</mn><mo stretchy="false">)</mo></math></mjx-assistive-mml></mjx-container></span>.  This completes the inductive
step, and thus the proof.</p>
<p>The techniques used in these three examples can be used to demonstrate that it
is always logically sound to add a <code class="docutils literal notranslate"><span class="pre">requireInvariant</span></code> to a <code class="docutils literal notranslate"><span class="pre">preserved</span></code> block,
even for complicated interdependent invariants (as long as the required
invariants have been verified).</p>
</section>
</section>


           </div>
          </div>
          <footer><div class="rst-footer-buttons" role="navigation" aria-label="Footer">
        <a href="functions.html" class="btn btn-neutral float-left" title="Functions" accesskey="p" rel="prev"><span class="fa fa-arrow-circle-left" aria-hidden="true"></span> Previous</a>
        <a href="sorts.html" class="btn btn-neutral float-right" title="Uninterpreted Sorts" accesskey="n" rel="next">Next <span class="fa fa-arrow-circle-right" aria-hidden="true"></span></a>
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