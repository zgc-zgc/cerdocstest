<!DOCTYPE html><html class="" lang="en" data-content_root="../"><head><meta charset="utf-8">
    <meta name="viewport" content="width=device-width,initial-scale=1">
    <meta name="color-scheme" content="light dark"><meta name="viewport" content="width=device-width, initial-scale=1">
<link rel="index" title="Index" href="../genindex.html"><link rel="search" title="Search" href="../search.html"><link rel="next" title="2.5. Parametric rules" href="parametric.html"><link rel="prev" title="2.3. ERC20 Example - Basics" href="erc20_example.html">

    <!-- Generated with Sphinx 7.4.5 and Furo 2024.05.06 -->
        <title>2.4. ERC20 Example - preconditions - Certora Prover Tutorials</title>
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
</style><script async="" type="text/javascript" src="/_/static/javascript/readthedocs-addons.js"></script><meta name="readthedocs-project-slug" content="certora-cvl2-tutorials-package"><meta name="readthedocs-version-slug" content="latest"><meta name="readthedocs-resolver-filename" content="/lesson2_started/preconditions.html"><meta name="readthedocs-http-status" content="200"><style type="text/css">.CtxtMenu_InfoClose {  top:.2em; right:.2em;}
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

mjx-c.mjx-c2265::before {
  padding: 0.636em 0.778em 0.138em 0;
  content: "\2265";
}
</style></head>
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
<li class="toctree-l2"><a class="reference internal" href="erc20_example.html">2.3. ERC20 Example - Basics</a></li>
<li class="toctree-l2 current current-page"><a class="current reference internal" href="#">2.4. ERC20 Example - preconditions</a></li>
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
          <section id="erc20-example-preconditions">
<h1><span class="section-number">2.4. </span>ERC20 Example - preconditions<a class="headerlink" href="#erc20-example-preconditions" title="Link to this heading">¶</a></h1>
<p>We demonstrate how sometimes preconditions are needed to avoid unwanted
over-approximation. We use the same <a class="reference external" href="https://github.com/Certora/tutorials-code/blob/master/lesson2_started/erc20/ERC20.sol">ERC20.sol</a>
contract as before.</p>
<section id="total-supply-rule">
<h2>Total supply rule<a class="headerlink" href="#total-supply-rule" title="Link to this heading">¶</a></h2>
<p>Consider the following property: <em>The total supply of the token</em> <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="0" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2265"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo>≥</mo></math></mjx-assistive-mml></mjx-container></span>
<em>the balance of any single user.</em></p>
<p>This property is asserted in the rule <code class="docutils literal notranslate"><span class="pre">totalSupplyAfterMint</span></code> of
<a class="reference external" href="https://github.com/Certora/tutorials-code/blob/master/lesson2_started/erc20/TotalGreaterThanUser.spec">TotalGreaterThanUser.spec</a>.
In this case the assertion is only that the property holds after <code class="docutils literal notranslate"><span class="pre">mint</span></code>:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre><span></span><span class="c1">/// @title Total supply after mint is at least the balance of the receiving account</span>
<span class="k">rule</span><span class="w"> </span><span class="nc">totalSupplyAfterMint</span><span class="p">(</span><span class="kt">address</span><span class="w"> </span>account<span class="p">,</span><span class="w"> </span><span class="kt">uint256</span><span class="w"> </span>amount<span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kt">env</span><span class="w"> </span>e<span class="p">;</span><span class="w"> </span>
<span class="w">    </span>
<span class="w">    </span>mint<span class="p">(</span>e<span class="p">,</span><span class="w"> </span>account<span class="p">,</span><span class="w"> </span>amount<span class="p">);</span>
<span class="w">    </span>
<span class="w">    </span><span class="kt">uint256</span><span class="w"> </span>userBalanceAfter<span class="w"> </span><span class="o">=</span><span class="w"> </span>balanceOf<span class="p">(</span>account<span class="p">);</span>
<span class="w">    </span><span class="kt">uint256</span><span class="w"> </span>totalAfter<span class="w"> </span><span class="o">=</span><span class="w"> </span>totalSupply<span class="p">();</span>
<span class="w">    </span>
<span class="w">    </span><span class="c1">// Verify that the total supply of the system is at least the current balance of the account.</span>
<span class="w">    </span><span class="kr">assert</span><span class="w"> </span>totalAfter<span class="w"> </span><span class="o">&gt;=</span><span class="w">  </span>userBalanceAfter<span class="p">,</span><span class="w"> </span><span class="s2">"total supply is less than a user's balance"</span><span class="p">;</span>
<span class="p">}</span>
</pre></div>
</div>
<p>Let’s run this rule:</p>
<div class="highlight-sh notranslate"><div class="highlight"><pre><span></span>certoraRun<span class="w"> </span>ERC20.sol<span class="w"> </span>--verify<span class="w"> </span>ERC20:TotalGreaterThanUser.spec<span class="w"> </span>--solc<span class="w"> </span>solc8.0<span class="w"> </span>--rule<span class="w"> </span>totalSupplyAfterMint
</pre></div>
</div>
<div class="admonition tip">
<p class="admonition-title">Tip</p>
<p>The <code class="docutils literal notranslate"><span class="pre">--rule</span></code> argument allows running one specific rule from the entire spec file.</p>
</div>
</section>
<section id="helper-variables">
<span id="index-0"></span><h2>Helper variables<a class="headerlink" href="#helper-variables" title="Link to this heading">¶</a></h2>
<p>As you discovered, the Prover finds that the rule is violated.
Understanding the counter-example in this case can be difficult.
Adding additional variables to the rule can help understand the counter-example.</p>
<p>Try adding the <em>helper variables</em> <code class="docutils literal notranslate"><span class="pre">userBalanceBefore</span></code> and <code class="docutils literal notranslate"><span class="pre">totalBefore</span></code> before
calling <code class="docutils literal notranslate"><span class="pre">mint</span></code>. Re-run the rule and see if you now understand the counter-example.</p>
<details class="sd-sphinx-override sd-dropdown sd-card sd-mb-3 sd-fade-in-slide-down">
<summary class="sd-summary-title sd-card-header">
<span class="sd-summary-text">Hint</span><span class="sd-summary-state-marker sd-summary-chevron-right"><svg version="1.1" width="1.5em" height="1.5em" class="sd-octicon sd-octicon-chevron-right" viewBox="0 0 24 24" aria-hidden="true"><path d="M8.72 18.78a.75.75 0 0 1 0-1.06L14.44 12 8.72 6.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018l6.25 6.25a.75.75 0 0 1 0 1.06l-6.25 6.25a.75.75 0 0 1-1.06 0Z"></path></svg></span></summary><div class="sd-summary-content sd-card-body docutils">
<p class="sd-card-text">Try adding the following lines before calling <code class="docutils literal notranslate"><span class="pre">mint</span></code>:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre><span></span><span class="kt">uint256</span><span class="w"> </span>userBalanceBefore<span class="w"> </span><span class="o">=</span><span class="w"> </span>balanceOf<span class="p">(</span>account<span class="p">);</span>
<span class="kt">uint256</span><span class="w"> </span>totalBefore<span class="w"> </span><span class="o">=</span><span class="w"> </span>totalSupply<span class="p">();</span>
</pre></div>
</div>
</div>
</details></section>
<section id="over-approximation">
<span id="index-1"></span><h2>Over-approximation<a class="headerlink" href="#over-approximation" title="Link to this heading">¶</a></h2>
<p>The Prover assumes <em>all possible input values</em> as a starting state, even those that can
never be reached. In other words, the Prover <em>over-approximates</em> the possible states
of the system. This over-approximation protects the Prover from erroneously claiming
that a rule passes. But it may result sometimes in wrong violations, like this case.</p>
<p>Here, the rule is violated when the initial state’s <code class="docutils literal notranslate"><span class="pre">totalSupply</span></code> is less than the
current balance of <code class="docutils literal notranslate"><span class="pre">account</span></code>. Even though such a state is unreachable by any route of
action by any user, the tool still considers this initial state as a valid state.</p>
<p>This is not a mistake but a designed behavior of the Certora Prover.
It’s designed to over-approximate states to avoid missing paths that lead to bugs
(false positives). However, doing so leads to evaluating states that might not be
reachable (false negatives), as shown in this example.
In the upcoming lessons, we will learn how to prove that such states are never feasible.</p>
</section>
<section id="preconditions">
<span id="index-2"></span><h2>Preconditions<a class="headerlink" href="#preconditions" title="Link to this heading">¶</a></h2>
<p>By adding <em>preconditions</em>, one can eliminate infeasible states and put constraints on
values. The Rule <code class="docutils literal notranslate"><span class="pre">totalSupplyAfterMintWithPrecondition</span></code> is a copy of
<code class="docutils literal notranslate"><span class="pre">totalSupplyAfterMint</span></code> with an additional constraint, shown in emphasis below:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre><span></span><span class="cm">/** @title Total supply after mint is at least the balance of the receiving account, with</span>
<span class="cm"> *  precondition.</span>
<span class="cm"> */</span>
<span class="k">rule</span><span class="w"> </span><span class="nc">totalSupplyAfterMintWithPrecondition</span><span class="p">(</span><span class="kt">address</span><span class="w"> </span>account<span class="p">,</span><span class="w"> </span><span class="kt">uint256</span><span class="w"> </span>amount<span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kt">env</span><span class="w"> </span>e<span class="p">;</span><span class="w"> </span>
<span class="w">    </span>
<span class="w">    </span><span class="c1">// Assume that in the current state before calling mint, the total supply of the </span>
<span class="w">    </span><span class="c1">// system is at least the user balance.</span>
<span class="hll"><span class="w">    </span><span class="kt">uint256</span><span class="w"> </span>userBalanceBefore<span class="w"> </span><span class="o">=</span><span class="w">  </span>balanceOf<span class="p">(</span>account<span class="p">);</span>
</span><span class="w">    </span><span class="kt">uint256</span><span class="w"> </span>totalBefore<span class="w"> </span><span class="o">=</span><span class="w"> </span>totalSupply<span class="p">();</span>
<span class="w">    </span><span class="kr">require</span><span class="w"> </span>totalBefore<span class="w"> </span><span class="o">&gt;=</span><span class="w"> </span>userBalanceBefore<span class="p">;</span><span class="w"> </span>
<span class="w">    </span>
<span class="w">    </span>mint<span class="p">(</span>e<span class="p">,</span><span class="w"> </span>account<span class="p">,</span><span class="w"> </span>amount<span class="p">);</span>
<span class="w">    </span>
<span class="w">    </span><span class="kt">uint256</span><span class="w"> </span>userBalanceAfter<span class="w"> </span><span class="o">=</span><span class="w"> </span>balanceOf<span class="p">(</span>account<span class="p">);</span>
<span class="w">    </span><span class="kt">uint256</span><span class="w"> </span>totalAfter<span class="w"> </span><span class="o">=</span><span class="w"> </span>totalSupply<span class="p">();</span>
<span class="w">    </span>
<span class="w">    </span><span class="c1">// Verify that the total supply of the system is at least the current balance of the account.</span>
<span class="w">    </span><span class="kr">assert</span><span class="w"> </span>totalAfter<span class="w"> </span><span class="o">&gt;=</span><span class="w"> </span>userBalanceAfter<span class="p">,</span><span class="w"> </span><span class="s2">"total supply is less than a user's balance "</span><span class="p">;</span>
<span class="p">}</span>
</pre></div>
</div>
<p>The Prover will now assume that in the initial state, i.e. before calling <code class="docutils literal notranslate"><span class="pre">mint()</span></code>,
the total supply is at least the user’s balance. Now run the rule
<code class="docutils literal notranslate"><span class="pre">totalSupplyAfterMintWithPrecondition</span></code>:</p>
<div class="highlight-sh notranslate"><div class="highlight"><pre><span></span>certoraRun<span class="w"> </span>ERC20.sol<span class="w"> </span>--verify<span class="w"> </span>ERC20:TotalGreaterThanUser.spec<span class="w"> </span>--solc<span class="w"> </span>solc8.0<span class="w"> </span>--rule<span class="w"> </span>totalSupplyAfterMintWithPrecondition<span class="w"> </span>--msg<span class="w"> </span><span class="s2">"running with precondition"</span>
</pre></div>
</div>
<div class="admonition tip">
<p class="admonition-title">Tip</p>
<p>The <code class="docutils literal notranslate"><span class="pre">--msg</span></code> flag adds a message description to your run. It can help you recognize
a specific run. You will see the message in the run results, and in the jobs list
(<a class="reference external" href="https://prover.certora.com/">prover.certora.com</a>).</p>
</div>
</section>
<section id="a-note-on-cvl-variables">
<span id="index-3"></span><h2>A note on CVL variables<a class="headerlink" href="#a-note-on-cvl-variables" title="Link to this heading">¶</a></h2>
<p>Unlike Solidity, in CVL an uninitialized variable can have <em>any</em> value, though its
possible values are constrained by CVL <code class="code highlight cvl docutils literal highlight-cvl"><span class="kr">require</span></code> statements in the rule.
Additionally, CVL variables are <em>immutable</em>, so they cannot be changed in the course
of the rule.</p>
<p>We will later meet another kind of variables in CVL which can be modified. These are
called <em>ghost</em> variables and we will meet them in <a class="reference internal" href="../lesson4_invariants/index.html#lesson4-invariants"><span class="std std-ref">Invariants and Ghosts</span></a>.</p>
</section>
</section>

        </article>
      </div>
      <footer>
        
        <div class="related-pages">
          <a class="next-page" href="parametric.html">
              <div class="page-info">
                <div class="context">
                  <span>Next</span>
                </div>
                <div class="title"><span class="section-number">2.5. </span>Parametric rules</div>
              </div>
              <svg class="furo-related-icon"><use href="#svg-arrow-right"></use></svg>
            </a>
          <a class="prev-page" href="erc20_example.html">
              <svg class="furo-related-icon"><use href="#svg-arrow-right"></use></svg>
              <div class="page-info">
                <div class="context">
                  <span>Previous</span>
                </div>
                
                <div class="title"><span class="section-number">2.3. </span>ERC20 Example - Basics</div>
                
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
<li><a class="reference internal" href="#">2.4. ERC20 Example - preconditions</a><ul>
<li><a class="reference internal" href="#total-supply-rule">Total supply rule</a></li>
<li><a class="reference internal" href="#helper-variables">Helper variables</a></li>
<li><a class="reference internal" href="#over-approximation">Over-approximation</a></li>
<li><a class="reference internal" href="#preconditions">Preconditions</a></li>
<li><a class="reference internal" href="#a-note-on-cvl-variables">A note on CVL variables</a></li>
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
    <script async="async" src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>
    
</body></html>