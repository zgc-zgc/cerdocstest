<!DOCTYPE html><html class="" lang="en" data-content_root="../"><head><meta charset="utf-8">
    <meta name="viewport" content="width=device-width,initial-scale=1">
    <meta name="color-scheme" content="light dark"><meta name="viewport" content="width=device-width, initial-scale=1">
<link rel="index" title="Index" href="../genindex.html"><link rel="search" title="Search" href="../search.html"><link rel="next" title="1.3. Introduction to formal verification" href="formal_verification.html"><link rel="prev" title="1.1. Background" href="background.html">

    <!-- Generated with Sphinx 7.4.5 and Furo 2024.05.06 -->
        <title>1.2. Introduction to predicate logic - Certora Prover Tutorials</title>
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
</style><script async="" type="text/javascript" src="/_/static/javascript/readthedocs-addons.js"></script><meta name="readthedocs-project-slug" content="certora-cvl2-tutorials-package"><meta name="readthedocs-version-slug" content="latest"><meta name="readthedocs-resolver-filename" content="/lesson1_prerequisites/propositional_logic.html"><meta name="readthedocs-http-status" content="200"><style type="text/css">.CtxtMenu_InfoClose {  top:.2em; right:.2em;}
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
  text-align: left;
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

mjx-mspace {
  display: inline-block;
  text-align: left;
}

mjx-mrow {
  display: inline-block;
  text-align: left;
}

mjx-TeXAtom {
  display: inline-block;
  text-align: left;
}

mjx-mtable {
  display: inline-block;
  text-align: center;
  vertical-align: .25em;
  position: relative;
  box-sizing: border-box;
  border-spacing: 0;
  border-collapse: collapse;
}

mjx-mstyle[size="s"] mjx-mtable {
  vertical-align: .354em;
}

mjx-labels {
  position: absolute;
  left: 0;
  top: 0;
}

mjx-table {
  display: inline-block;
  vertical-align: -.5ex;
  box-sizing: border-box;
}

mjx-table > mjx-itable {
  vertical-align: middle;
  text-align: left;
  box-sizing: border-box;
}

mjx-labels > mjx-itable {
  position: absolute;
  top: 0;
}

mjx-mtable[justify="left"] {
  text-align: left;
}

mjx-mtable[justify="right"] {
  text-align: right;
}

mjx-mtable[justify="left"][side="left"] {
  padding-right: 0 ! important;
}

mjx-mtable[justify="left"][side="right"] {
  padding-left: 0 ! important;
}

mjx-mtable[justify="right"][side="left"] {
  padding-right: 0 ! important;
}

mjx-mtable[justify="right"][side="right"] {
  padding-left: 0 ! important;
}

mjx-mtable[align] {
  vertical-align: baseline;
}

mjx-mtable[align="top"] > mjx-table {
  vertical-align: top;
}

mjx-mtable[align="bottom"] > mjx-table {
  vertical-align: bottom;
}

mjx-mtable[side="right"] mjx-labels {
  min-width: 100%;
}

mjx-mtr {
  display: table-row;
  text-align: left;
}

mjx-mtr[rowalign="top"] > mjx-mtd {
  vertical-align: top;
}

mjx-mtr[rowalign="center"] > mjx-mtd {
  vertical-align: middle;
}

mjx-mtr[rowalign="bottom"] > mjx-mtd {
  vertical-align: bottom;
}

mjx-mtr[rowalign="baseline"] > mjx-mtd {
  vertical-align: baseline;
}

mjx-mtr[rowalign="axis"] > mjx-mtd {
  vertical-align: .25em;
}

mjx-mtd {
  display: table-cell;
  text-align: center;
  padding: .215em .4em;
}

mjx-mtd:first-child {
  padding-left: 0;
}

mjx-mtd:last-child {
  padding-right: 0;
}

mjx-mtable > * > mjx-itable > *:first-child > mjx-mtd {
  padding-top: 0;
}

mjx-mtable > * > mjx-itable > *:last-child > mjx-mtd {
  padding-bottom: 0;
}

mjx-tstrut {
  display: inline-block;
  height: 1em;
  vertical-align: -.25em;
}

mjx-labels[align="left"] > mjx-mtr > mjx-mtd {
  text-align: left;
}

mjx-labels[align="right"] > mjx-mtr > mjx-mtd {
  text-align: right;
}

mjx-mtd[extra] {
  padding: 0;
}

mjx-mtd[rowalign="top"] {
  vertical-align: top;
}

mjx-mtd[rowalign="center"] {
  vertical-align: middle;
}

mjx-mtd[rowalign="bottom"] {
  vertical-align: bottom;
}

mjx-mtd[rowalign="baseline"] {
  vertical-align: baseline;
}

mjx-mtd[rowalign="axis"] {
  vertical-align: .25em;
}

mjx-mn {
  display: inline-block;
  text-align: left;
}

mjx-munder {
  display: inline-block;
  text-align: left;
}

mjx-over {
  text-align: left;
}

mjx-munder:not([limits="false"]) {
  display: inline-table;
}

mjx-munder > mjx-row {
  text-align: left;
}

mjx-under {
  padding-bottom: .1em;
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

mjx-c.mjx-c1D443.TEX-I::before {
  padding: 0.683em 0.751em 0 0;
  content: "P";
}

mjx-c.mjx-c1D444.TEX-I::before {
  padding: 0.704em 0.791em 0.194em 0;
  content: "Q";
}

mjx-c.mjx-c1D445.TEX-I::before {
  padding: 0.683em 0.759em 0.021em 0;
  content: "R";
}

mjx-c.mjx-c3D::before {
  padding: 0.583em 0.778em 0.082em 0;
  content: "=";
}

mjx-c.mjx-c2227::before {
  padding: 0.598em 0.667em 0.022em 0;
  content: "\2227";
}

mjx-c.mjx-c27F9::before {
  padding: 0.525em 1.638em 0.024em 0;
  content: "\27F9";
}

mjx-c.mjx-c28::before {
  padding: 0.75em 0.389em 0.25em 0;
  content: "(";
}

mjx-c.mjx-c2228::before {
  padding: 0.598em 0.667em 0.022em 0;
  content: "\2228";
}

mjx-c.mjx-c29::before {
  padding: 0.75em 0.389em 0.25em 0;
  content: ")";
}

mjx-c.mjx-c1D446.TEX-I::before {
  padding: 0.705em 0.645em 0.022em 0;
  content: "S";
}

mjx-c.mjx-cAC::before {
  padding: 0.356em 0.667em 0 0;
  content: "\AC";
}

mjx-c.mjx-c1D434.TEX-I::before {
  padding: 0.716em 0.75em 0 0;
  content: "A";
}

mjx-c.mjx-c1D435.TEX-I::before {
  padding: 0.683em 0.759em 0 0;
  content: "B";
}

mjx-c.mjx-c1D436.TEX-I::before {
  padding: 0.705em 0.76em 0.022em 0;
  content: "C";
}

mjx-c.mjx-c1D45B.TEX-I::before {
  padding: 0.442em 0.6em 0.011em 0;
  content: "n";
}

mjx-c.mjx-c1D453.TEX-I::before {
  padding: 0.705em 0.55em 0.205em 0;
  content: "f";
}

mjx-c.mjx-c3A::before {
  padding: 0.43em 0.278em 0 0;
  content: ":";
}

mjx-c.mjx-c2115.TEX-A::before {
  padding: 0.683em 0.722em 0.02em 0;
  content: "N";
}

mjx-c.mjx-c2192::before {
  padding: 0.511em 1em 0.011em 0;
  content: "\2192";
}

mjx-c.mjx-c7B::before {
  padding: 0.75em 0.5em 0.25em 0;
  content: "{";
}

mjx-c.mjx-c74::before {
  padding: 0.615em 0.389em 0.01em 0;
  content: "t";
}

mjx-c.mjx-c72::before {
  padding: 0.442em 0.392em 0 0;
  content: "r";
}

mjx-c.mjx-c75::before {
  padding: 0.442em 0.556em 0.011em 0;
  content: "u";
}

mjx-c.mjx-c65::before {
  padding: 0.448em 0.444em 0.011em 0;
  content: "e";
}

mjx-c.mjx-c2C::before {
  padding: 0.121em 0.278em 0.194em 0;
  content: ",";
}

mjx-c.mjx-c20::before {
  padding: 0 0.25em 0 0;
  content: " ";
}

mjx-c.mjx-c66::before {
  padding: 0.705em 0.372em 0 0;
  content: "f";
}

mjx-c.mjx-c61::before {
  padding: 0.448em 0.5em 0.011em 0;
  content: "a";
}

mjx-c.mjx-c6C::before {
  padding: 0.694em 0.278em 0 0;
  content: "l";
}

mjx-c.mjx-c73::before {
  padding: 0.448em 0.394em 0.011em 0;
  content: "s";
}

mjx-c.mjx-c7D::before {
  padding: 0.75em 0.5em 0.25em 0;
  content: "}";
}

mjx-c.mjx-c7B.TEX-S3::before {
  padding: 1.45em 0.75em 0.949em 0;
  content: "{";
}

mjx-c.mjx-c69::before {
  padding: 0.669em 0.278em 0 0;
  content: "i";
}

mjx-c.mjx-cA0::before {
  padding: 0 0.25em 0 0;
  content: "\A0";
}

mjx-c.mjx-c7C::before {
  padding: 0.75em 0.278em 0.249em 0;
  content: "|";
}

mjx-c.mjx-c33::before {
  padding: 0.665em 0.5em 0.022em 0;
  content: "3";
}

mjx-c.mjx-c6F::before {
  padding: 0.448em 0.5em 0.01em 0;
  content: "o";
}

mjx-c.mjx-c68::before {
  padding: 0.694em 0.556em 0 0;
  content: "h";
}

mjx-c.mjx-c77::before {
  padding: 0.431em 0.722em 0.011em 0;
  content: "w";
}

mjx-c.mjx-c1D465.TEX-I::before {
  padding: 0.442em 0.572em 0.011em 0;
  content: "x";
}

mjx-c.mjx-c2208::before {
  padding: 0.54em 0.667em 0.04em 0;
  content: "\2208";
}

mjx-c.mjx-c2203::before {
  padding: 0.694em 0.556em 0 0;
  content: "\2203";
}

mjx-c.mjx-c2E::before {
  padding: 0.12em 0.278em 0 0;
  content: ".";
}

mjx-c.mjx-c31::before {
  padding: 0.666em 0.5em 0 0;
  content: "1";
}

mjx-c.mjx-c32::before {
  padding: 0.666em 0.5em 0 0;
  content: "2";
}

mjx-c.mjx-c34::before {
  padding: 0.677em 0.5em 0 0;
  content: "4";
}

mjx-c.mjx-c22EF::before {
  padding: 0.31em 1.172em 0 0;
  content: "\22EF";
}

mjx-c.mjx-c22C1.TEX-S2::before {
  padding: 0.95em 1.111em 0.45em 0;
  content: "\22C1";
}

mjx-c.mjx-c2B::before {
  padding: 0.583em 0.778em 0.082em 0;
  content: "+";
}

mjx-c.mjx-c2200::before {
  padding: 0.694em 0.556em 0.022em 0;
  content: "\2200";
}

mjx-c.mjx-c22C0.TEX-S2::before {
  padding: 0.95em 1.111em 0.45em 0;
  content: "\22C0";
}

mjx-c.mjx-c1D454.TEX-I::before {
  padding: 0.442em 0.477em 0.205em 0;
  content: "g";
}

mjx-c.mjx-c27FA::before {
  padding: 0.525em 1.858em 0.024em 0;
  content: "\27FA";
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
    <img class="sidebar-logo only-light" src="../_static/logo.svg" alt="Light Logo" width="164" height="42">
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
<li class="toctree-l1 current has-children"><a class="reference internal" href="index.html">1. Background and Prerequisites</a><input checked="" class="toctree-checkbox" id="toctree-checkbox-1" name="toctree-checkbox-1" role="switch" type="checkbox"><label for="toctree-checkbox-1"><div class="visually-hidden">Toggle navigation of 1. Background and Prerequisites</div><i class="icon"><svg><use href="#svg-arrow-right"></use></svg></i></label><ul class="current">
<li class="toctree-l2"><a class="reference internal" href="background.html">1.1. Background</a></li>
<li class="toctree-l2 current current-page"><a class="current reference internal" href="#">1.2. Introduction to predicate logic</a></li>
<li class="toctree-l2"><a class="reference internal" href="formal_verification.html">1.3. Introduction to formal verification</a></li>
</ul>
</li>
<li class="toctree-l1 has-children"><a class="reference internal" href="../lesson2_started/index.html">2. Getting Started</a><input class="toctree-checkbox" id="toctree-checkbox-2" name="toctree-checkbox-2" role="switch" type="checkbox"><label for="toctree-checkbox-2"><div class="visually-hidden">Toggle navigation of 2. Getting Started</div><i class="icon"><svg><use href="#svg-arrow-right"></use></svg></i></label><ul>
<li class="toctree-l2"><a class="reference internal" href="../lesson2_started/installation.html">2.1. Installation and Setup</a></li>
<li class="toctree-l2"><a class="reference internal" href="../lesson2_started/overview.html">2.2. Technology Overview</a></li>
<li class="toctree-l2"><a class="reference internal" href="../lesson2_started/erc20_example.html">2.3. ERC20 Example - Basics</a></li>
<li class="toctree-l2"><a class="reference internal" href="../lesson2_started/preconditions.html">2.4. ERC20 Example - preconditions</a></li>
<li class="toctree-l2"><a class="reference internal" href="../lesson2_started/parametric.html">2.5. Parametric rules</a></li>
<li class="toctree-l2"><a class="reference internal" href="../lesson2_started/config_files.html">2.6. Using config files</a></li>
<li class="toctree-l2"><a class="reference internal" href="../lesson2_started/vacuity.html">2.7. Vacuity</a></li>
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
          <section id="introduction-to-predicate-logic">
<span id="id1"></span><h1><span class="section-number">1.2. </span>Introduction to predicate logic<a class="headerlink" href="#introduction-to-predicate-logic" title="Link to this heading">¶</a></h1>
<p>This section provides a basic introduction to predicates, propositional logic and
quantifiers. These basic concepts of mathematical logic are useful when doing
formal verification, and in particular when working with the Prover.
If you are familiar with these concepts, feel free to skip this section.
If you wish to test your knowledge, use the <a class="reference internal" href="#propositional-logic-quiz"><span class="std std-ref">Quiz</span></a> below.</p>
<div class="admonition seealso">
<p class="admonition-title">See also</p>
<p>You can find further information about these subjects in:</p>
<ol class="arabic simple">
<li><p>Chapter 1 of <a class="reference external" href="http://web.mit.edu/gleitz/www/Introduction%20to%20Logic%20-%20P.%20Suppes%20(1957)%20WW.pdf">Introduction to Logic (written by Patrick Suppes)</a></p></li>
<li><p>Chapter 3.1 of <a class="reference external" href="http://discrete.openmathbooks.org/dmoi2/sec_propositional.html">Discrete Mathematics - An Open Introduction</a></p></li>
</ol>
</div>
<div class="admonition tip">
<p class="admonition-title">Tip</p>
<p>At the end of this section there is a handy table containing the common symbols for
the logical operators and quantifiers introduced here. See
<a class="reference internal" href="#logical-operators-table"><span class="std std-ref">Logical operators and quantifiers table</span></a>.</p>
</div>
<section id="propositional-logic">
<span id="index-0"></span><h2>Propositional logic<a class="headerlink" href="#propositional-logic" title="Link to this heading">¶</a></h2>
<p><em>Propositional logic</em> is the basis of mathematical logic, dealing with boolean variables
and operations.</p>
<section id="propositions">
<span id="index-1"></span><h3>Propositions<a class="headerlink" href="#propositions" title="Link to this heading">¶</a></h3>
<p>We can think of a <em>proposition</em> as a function where:</p>
<ol class="arabic simple">
<li><p>all inputs have type <code class="docutils literal notranslate"><span class="pre">bool</span></code></p></li>
<li><p>the return type is also <code class="docutils literal notranslate"><span class="pre">bool</span></code></p></li>
<li><p>only logical operators are allowed in the body of the function</p></li>
</ol>
<section id="example">
<h4>Example:<a class="headerlink" href="#example" title="Link to this heading">¶</a></h4>
<p>Consider the proposition <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="0" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D443 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>P</mi></math></mjx-assistive-mml></mjx-container></span> which is “<span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="1" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D444 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>Q</mi></math></mjx-assistive-mml></mjx-container></span> and <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="2" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D445 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>R</mi></math></mjx-assistive-mml></mjx-container></span>”.
In mathematical notation this is <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="3" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D443 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c3D"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="4"><mjx-c class="mjx-c1D444 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2227"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="3"><mjx-c class="mjx-c1D445 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>P</mi><mo>=</mo><mi>Q</mi><mo>∧</mo><mi>R</mi></math></mjx-assistive-mml></mjx-container></span>, and in CVL we can write it as:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre><span></span><span class="kt">function</span><span class="w"> </span><span class="nf">P</span><span class="p">(</span><span class="kt">bool</span><span class="w"> </span>Q<span class="p">,</span><span class="w"> </span><span class="kt">bool</span><span class="w"> </span>R<span class="p">)</span><span class="w"> </span><span class="kr">returns</span><span class="w"> </span><span class="kt">bool</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kr">return</span><span class="w"> </span>Q<span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span>R<span class="p">;</span>
<span class="p">}</span>
</pre></div>
</div>
<p>More informally, we can simply write this proposition as a boolean expression:</p>
<p><code class="code highlight cvl docutils literal highlight-cvl"><span class="kt">bool</span><span class="w"> </span>P<span class="w"> </span><span class="o">=</span><span class="w"> </span>Q<span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span>R<span class="p">;</span></code></p>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>The definition for a proposition given here is not the classical one.
However, it is equivalent and easier to explain in our context.</p>
</div>
</section>
</section>
<section id="the-implication-operator">
<h3>The implication operator<a class="headerlink" href="#the-implication-operator" title="Link to this heading">¶</a></h3>
<p>In propositional logic, the statement <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="4" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D443 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>P</mi></math></mjx-assistive-mml></mjx-container></span> <em>implies</em> <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="5" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D444 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>Q</mi></math></mjx-assistive-mml></mjx-container></span> means that
if <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="6" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D443 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>P</mi></math></mjx-assistive-mml></mjx-container></span> is true then <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="7" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D444 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>Q</mi></math></mjx-assistive-mml></mjx-container></span> is also true. Hence the statement is true
when either both <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="8" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D443 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>P</mi></math></mjx-assistive-mml></mjx-container></span> and <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="9" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D444 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>Q</mi></math></mjx-assistive-mml></mjx-container></span> are true, or when <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="10" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D443 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>P</mi></math></mjx-assistive-mml></mjx-container></span> is false.
A complete truth table is given below in <a class="reference internal" href="#example-implication-table"><span class="std std-ref">Example: Implication truth table</span></a>.</p>
<p>In mathematical notation the statement is <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="11" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D443 TEX-I"></mjx-c></mjx-mi><mjx-mstyle><mjx-mspace style="width: 0.278em;"></mjx-mspace></mjx-mstyle><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c27F9"></mjx-c></mjx-mo><mjx-mstyle><mjx-mspace style="width: 0.278em;"></mjx-mspace></mjx-mstyle><mjx-mi class="mjx-i" space="4"><mjx-c class="mjx-c1D444 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>P</mi><mstyle scriptlevel="0"><mspace width="0.278em"></mspace></mstyle><mo stretchy="false">⟹</mo><mstyle scriptlevel="0"><mspace width="0.278em"></mspace></mstyle><mi>Q</mi></math></mjx-assistive-mml></mjx-container></span>, and in CVL the syntax
is <code class="code highlight cvl docutils literal highlight-cvl">P<span class="w"> </span><span class="o">=&gt;</span><span class="w"> </span>Q</code>.</p>
</section>
<section id="examples">
<h3>Examples<a class="headerlink" href="#examples" title="Link to this heading">¶</a></h3>
<p>Here are some more examples, shown in mathematical notation and in CVL side by side.</p>
<div class="sd-container-fluid sd-sphinx-override sd-mb-4 docutils">
<div class="sd-row sd-row-cols-2 sd-row-cols-xs-2 sd-row-cols-sm-2 sd-row-cols-md-2 sd-row-cols-lg-2 sd-g-1 sd-g-xs-1 sd-g-sm-1 sd-g-md-1 sd-g-lg-1 docutils">
<div class="sd-col sd-d-flex-row docutils">
<div class="sd-card sd-sphinx-override sd-w-100 sd-shadow-sm docutils">
<div class="sd-card-body docutils">
<div class="sd-card-title sd-font-weight-bold docutils">
Math</div>
<p class="sd-card-text"><span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="12" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D444 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2228"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="3"><mjx-c class="mjx-c1D445 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo><mjx-mstyle><mjx-mspace style="width: 0.278em;"></mjx-mspace></mjx-mstyle><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c27F9"></mjx-c></mjx-mo><mjx-mstyle><mjx-mspace style="width: 0.278em;"></mjx-mspace></mjx-mstyle><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D443 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2227"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="3"><mjx-c class="mjx-c1D446 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo stretchy="false">(</mo><mi>Q</mi><mo>∨</mo><mi>R</mi><mo stretchy="false">)</mo><mstyle scriptlevel="0"><mspace width="0.278em"></mspace></mstyle><mo stretchy="false">⟹</mo><mstyle scriptlevel="0"><mspace width="0.278em"></mspace></mstyle><mo stretchy="false">(</mo><mi>P</mi><mo>∧</mo><mi>S</mi><mo stretchy="false">)</mo></math></mjx-assistive-mml></mjx-container></span></p>
</div>
</div>
</div>
<div class="sd-col sd-d-flex-row docutils">
<div class="sd-card sd-sphinx-override sd-w-100 sd-shadow-sm docutils">
<div class="sd-card-body docutils">
<div class="sd-card-title sd-font-weight-bold docutils">
CVL</div>
<p class="sd-card-text"><code class="code highlight cvl docutils literal highlight-cvl"><span class="p">(</span>Q<span class="w"> </span><span class="o">||</span><span class="w"> </span>R<span class="p">)</span><span class="w"> </span><span class="o">=&gt;</span><span class="w"> </span><span class="p">(</span>P<span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span>S<span class="p">)</span></code></p>
</div>
</div>
</div>
</div>
</div>
<div class="sd-container-fluid sd-sphinx-override sd-mb-4 docutils">
<div class="sd-row sd-row-cols-2 sd-row-cols-xs-2 sd-row-cols-sm-2 sd-row-cols-md-2 sd-row-cols-lg-2 sd-g-1 sd-g-xs-1 sd-g-sm-1 sd-g-md-1 sd-g-lg-1 docutils">
<div class="sd-col sd-d-flex-row docutils">
<div class="sd-card sd-sphinx-override sd-w-100 sd-shadow-sm docutils">
<div class="sd-card-body docutils">
<div class="sd-card-title sd-font-weight-bold docutils">
Math</div>
<p class="sd-card-text"><span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="13" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D443 TEX-I"></mjx-c></mjx-mi><mjx-mstyle><mjx-mspace style="width: 0.278em;"></mjx-mspace></mjx-mstyle><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c27F9"></mjx-c></mjx-mo><mjx-mstyle><mjx-mspace style="width: 0.278em;"></mjx-mspace></mjx-mstyle><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D444 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2228"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="3"><mjx-c class="mjx-c1D445 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2227"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-n"><mjx-c class="mjx-cAC"></mjx-c></mjx-mi><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D443 TEX-I"></mjx-c></mjx-mi><mjx-mstyle><mjx-mspace style="width: 0.278em;"></mjx-mspace></mjx-mstyle><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c27F9"></mjx-c></mjx-mo><mjx-mstyle><mjx-mspace style="width: 0.278em;"></mjx-mspace></mjx-mstyle><mjx-mi class="mjx-i" space="4"><mjx-c class="mjx-c1D446 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo stretchy="false">(</mo><mi>P</mi><mstyle scriptlevel="0"><mspace width="0.278em"></mspace></mstyle><mo stretchy="false">⟹</mo><mstyle scriptlevel="0"><mspace width="0.278em"></mspace></mstyle><mo stretchy="false">(</mo><mi>Q</mi><mo>∨</mo><mi>R</mi><mo stretchy="false">)</mo><mo stretchy="false">)</mo><mo>∧</mo><mo stretchy="false">(</mo><mi mathvariant="normal">¬</mi><mi>P</mi><mstyle scriptlevel="0"><mspace width="0.278em"></mspace></mstyle><mo stretchy="false">⟹</mo><mstyle scriptlevel="0"><mspace width="0.278em"></mspace></mstyle><mi>S</mi><mo stretchy="false">)</mo></math></mjx-assistive-mml></mjx-container></span></p>
</div>
</div>
</div>
<div class="sd-col sd-d-flex-row docutils">
<div class="sd-card sd-sphinx-override sd-w-100 sd-shadow-sm docutils">
<div class="sd-card-body docutils">
<div class="sd-card-title sd-font-weight-bold docutils">
CVL</div>
<p class="sd-card-text"><code class="code highlight cvl docutils literal highlight-cvl"><span class="p">(</span>P<span class="w"> </span><span class="o">=&gt;</span><span class="w"> </span><span class="p">(</span>Q<span class="w"> </span><span class="o">||</span><span class="w"> </span>R<span class="p">))</span><span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span><span class="p">(</span><span class="o">!</span>P<span class="w"> </span><span class="o">=&gt;</span><span class="w"> </span>S<span class="p">)</span></code></p>
</div>
</div>
</div>
</div>
</div>
</section>
<section id="truth-tables">
<h3>Truth tables<a class="headerlink" href="#truth-tables" title="Link to this heading">¶</a></h3>
<p>Since the variables of a proposition are all boolean, we can enumerate them in a table
and find the output for every set of inputs. This is known as a <em>truth table</em>.</p>
<section id="example-implication-truth-table">
<span id="example-implication-table"></span><h4>Example: Implication truth table<a class="headerlink" href="#example-implication-truth-table" title="Link to this heading">¶</a></h4>
<p>Here is the truth table for the proposition <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="14" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D434 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>A</mi></math></mjx-assistive-mml></mjx-container></span> defined as
“<span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="15" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D435 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>B</mi></math></mjx-assistive-mml></mjx-container></span> implies <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="16" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D436 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>C</mi></math></mjx-assistive-mml></mjx-container></span>”. In mathematical notation this is
<span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="17" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D434 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c3D"></mjx-c></mjx-mo><mjx-mrow space="4"><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D435 TEX-I"></mjx-c></mjx-mi><mjx-mstyle><mjx-mspace style="width: 0.278em;"></mjx-mspace></mjx-mstyle><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c27F9"></mjx-c></mjx-mo><mjx-mstyle><mjx-mspace style="width: 0.278em;"></mjx-mspace></mjx-mstyle><mjx-mi class="mjx-i" space="4"><mjx-c class="mjx-c1D436 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo></mjx-mrow></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>A</mi><mo>=</mo><mrow data-mjx-texclass="INNER"><mo data-mjx-texclass="OPEN">(</mo><mi>B</mi><mstyle scriptlevel="0"><mspace width="0.278em"></mspace></mstyle><mo stretchy="false">⟹</mo><mstyle scriptlevel="0"><mspace width="0.278em"></mspace></mstyle><mi>C</mi><mo data-mjx-texclass="CLOSE">)</mo></mrow></math></mjx-assistive-mml></mjx-container></span> and in CVL:</p>
<p><code class="code highlight cvl docutils literal highlight-cvl"><span class="kt">bool</span><span class="w"> </span>A<span class="w"> </span><span class="o">=</span><span class="w"> </span>B<span class="w"> </span><span class="o">=&gt;</span><span class="w"> </span>C<span class="p">;</span></code>.</p>
<div class="table-wrapper docutils container" id="id4">
<span id="truth-table-for-implication"></span><span id="truth-table-for-implication"></span><table class="docutils align-default" id="id4" style="width: 30">
<caption><span class="caption-text">Truth table for implication</span><a class="headerlink" href="#id4" title="Link to this table">¶</a></caption>
<thead>
<tr class="row-odd"><th class="head"><p>B</p></th>
<th class="head"><p>C</p></th>
<th class="head"><p>A</p></th>
</tr>
</thead>
<tbody>
<tr class="row-even"><td><p>false</p></td>
<td><p>false</p></td>
<td><p>true</p></td>
</tr>
<tr class="row-odd"><td><p>false</p></td>
<td><p>true</p></td>
<td><p>true</p></td>
</tr>
<tr class="row-even"><td><p>true</p></td>
<td><p>false</p></td>
<td><p>false</p></td>
</tr>
<tr class="row-odd"><td><p>true</p></td>
<td><p>true</p></td>
<td><p>true</p></td>
</tr>
</tbody>
</table>
</div>
<p>The truth table describes the action of the implication operator <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="18" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mstyle><mjx-mspace style="width: 0.278em;"></mjx-mspace></mjx-mstyle><mjx-mo class="mjx-n"><mjx-c class="mjx-c27F9"></mjx-c></mjx-mo><mjx-mstyle><mjx-mspace style="width: 0.278em;"></mjx-mspace></mjx-mstyle></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mstyle scriptlevel="0"><mspace width="0.278em"></mspace></mstyle><mo stretchy="false">⟹</mo><mstyle scriptlevel="0"><mspace width="0.278em"></mspace></mstyle></math></mjx-assistive-mml></mjx-container></span>.</p>
</section>
</section>
</section>
<section id="predicates">
<span id="index-2"></span><h2>Predicates<a class="headerlink" href="#predicates" title="Link to this heading">¶</a></h2>
<p>We can think of a <em>predicate</em> as a function whose return type is <code class="docutils literal notranslate"><span class="pre">bool</span></code>, i.e.
returns either <code class="docutils literal notranslate"><span class="pre">true</span></code> or <code class="docutils literal notranslate"><span class="pre">false</span></code>.</p>
<section id="id2">
<h3>Example:<a class="headerlink" href="#id2" title="Link to this heading">¶</a></h3>
<p>The function <em>“is</em> <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="19" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>n</mi></math></mjx-assistive-mml></mjx-container></span> <em>divisible by 3”</em> is a predicate. Here is the function in
mathematical notation:</p>
<div class="math-wrapper docutils container">
<div class="math notranslate nohighlight">
<mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" display="true" tabindex="0" ctxtmenu_counter="20" style="font-size: 119%; position: relative;"><mjx-math display="true" class="MJX-TEX" aria-hidden="true" style="margin-left: 0px; margin-right: 0px;"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D453 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c3A"></mjx-c></mjx-mo><mjx-texatom space="4" texclass="ORD"><mjx-mi class="mjx-ds mjx-b"><mjx-c class="mjx-c2115 TEX-A"></mjx-c></mjx-mi></mjx-texatom><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c2192"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c7B"></mjx-c></mjx-mo><mjx-mtext class="mjx-n"><mjx-c class="mjx-c74"></mjx-c><mjx-c class="mjx-c72"></mjx-c><mjx-c class="mjx-c75"></mjx-c><mjx-c class="mjx-c65"></mjx-c><mjx-c class="mjx-c2C"></mjx-c><mjx-c class="mjx-c20"></mjx-c><mjx-c class="mjx-c66"></mjx-c><mjx-c class="mjx-c61"></mjx-c><mjx-c class="mjx-c6C"></mjx-c><mjx-c class="mjx-c73"></mjx-c><mjx-c class="mjx-c65"></mjx-c></mjx-mtext><mjx-mo class="mjx-n"><mjx-c class="mjx-c7D"></mjx-c></mjx-mo><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mstyle><mjx-mspace style="width: 1em;"></mjx-mspace></mjx-mstyle><mjx-mi class="mjx-i" space="2"><mjx-c class="mjx-c1D453 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c3D"></mjx-c></mjx-mo><mjx-mrow space="4"><mjx-mo class="mjx-s3"><mjx-c class="mjx-c7B TEX-S3"></mjx-c></mjx-mo><mjx-mtable style="min-width: 7.041em;"><mjx-table><mjx-itable><mjx-mtr><mjx-mtd style="text-align: left; padding-right: 0.5em; padding-bottom: 0.1em;"><mjx-mtext class="mjx-n"><mjx-c class="mjx-c74"></mjx-c><mjx-c class="mjx-c72"></mjx-c><mjx-c class="mjx-c75"></mjx-c><mjx-c class="mjx-c65"></mjx-c></mjx-mtext><mjx-tstrut></mjx-tstrut></mjx-mtd><mjx-mtd style="text-align: left; padding-left: 0.5em; padding-bottom: 0.1em;"><mjx-mtext class="mjx-n"><mjx-c class="mjx-c69"></mjx-c><mjx-c class="mjx-c66"></mjx-c><mjx-c class="mjx-cA0"></mjx-c></mjx-mtext><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c7C"></mjx-c></mjx-mo><mjx-mn class="mjx-n"><mjx-c class="mjx-c33"></mjx-c></mjx-mn><mjx-tstrut></mjx-tstrut></mjx-mtd></mjx-mtr><mjx-mtr><mjx-mtd style="text-align: left; padding-right: 0.5em; padding-top: 0.1em;"><mjx-mtext class="mjx-n"><mjx-c class="mjx-c66"></mjx-c><mjx-c class="mjx-c61"></mjx-c><mjx-c class="mjx-c6C"></mjx-c><mjx-c class="mjx-c73"></mjx-c><mjx-c class="mjx-c65"></mjx-c></mjx-mtext><mjx-tstrut></mjx-tstrut></mjx-mtd><mjx-mtd style="text-align: left; padding-left: 0.5em; padding-top: 0.1em;"><mjx-mtext class="mjx-n"><mjx-c class="mjx-c6F"></mjx-c><mjx-c class="mjx-c74"></mjx-c><mjx-c class="mjx-c68"></mjx-c><mjx-c class="mjx-c65"></mjx-c><mjx-c class="mjx-c72"></mjx-c><mjx-c class="mjx-c77"></mjx-c><mjx-c class="mjx-c69"></mjx-c><mjx-c class="mjx-c73"></mjx-c><mjx-c class="mjx-c65"></mjx-c></mjx-mtext><mjx-tstrut></mjx-tstrut></mjx-mtd></mjx-mtr></mjx-itable></mjx-table></mjx-mtable><mjx-mo class="mjx-n" style="vertical-align: 0.25em;"></mjx-mo></mjx-mrow></mjx-math><mjx-assistive-mml unselectable="on" display="block"><math xmlns="http://www.w3.org/1998/Math/MathML" display="block"><mi>f</mi><mo>:</mo><mrow data-mjx-texclass="ORD"><mi mathvariant="double-struck">N</mi></mrow><mo accent="false" stretchy="false">→</mo><mo fence="false" stretchy="false">{</mo><mtext>true, false</mtext><mo fence="false" stretchy="false">}</mo><mo>,</mo><mstyle scriptlevel="0"><mspace width="1em"></mspace></mstyle><mi>f</mi><mo stretchy="false">(</mo><mi>n</mi><mo stretchy="false">)</mo><mo>=</mo><mrow data-mjx-texclass="INNER"><mo data-mjx-texclass="OPEN">{</mo><mtable columnalign="left left" columnspacing="1em" rowspacing=".2em"><mtr><mtd><mtext>true</mtext></mtd><mtd><mtext>if&nbsp;</mtext><mi>n</mi><mo data-mjx-texclass="ORD" fence="false" stretchy="false">|</mo><mn>3</mn></mtd></mtr><mtr><mtd><mtext>false</mtext></mtd><mtd><mtext>otherwise</mtext></mtd></mtr></mtable><mo data-mjx-texclass="CLOSE" fence="true" stretchy="true" symmetric="true"></mo></mrow></math></mjx-assistive-mml></mjx-container></div></div>
<div class="literal-block-wrapper docutils container" id="id5">
<div class="code-block-caption"><span class="caption-text">In CVL it looks like this:</span><a class="headerlink" href="#id5" title="Link to this code">¶</a></div>
<div class="highlight-cvl notranslate"><div class="highlight"><pre><span></span><span class="kt">function</span><span class="w"> </span><span class="nf">f</span><span class="p">(</span><span class="kt">int</span><span class="w"> </span>n<span class="p">)</span><span class="w"> </span><span class="kr">returns</span><span class="w"> </span><span class="kt">bool</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kr">return</span><span class="w"> </span><span class="m m-Decimal">3</span><span class="w"> </span><span class="o">*</span><span class="w"> </span><span class="p">(</span>n<span class="w"> </span><span class="o">/</span><span class="w"> </span><span class="m m-Decimal">3</span><span class="p">)</span><span class="w"> </span><span class="o">==</span><span class="w"> </span>n<span class="p">;</span>
<span class="p">}</span>
</pre></div>
</div>
</div>
</section>
</section>
<section id="quantifiers">
<span id="index-3"></span><h2>Quantifiers<a class="headerlink" href="#quantifiers" title="Link to this heading">¶</a></h2>
<p>The statement
<em>“there exists a natural number</em> <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="21" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>n</mi></math></mjx-assistive-mml></mjx-container></span> <em>which is divisible by 3”</em> is an example of
a <em>quantifier</em>. This statement is true, since <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="22" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c3D"></mjx-c></mjx-mo><mjx-mn class="mjx-n" space="4"><mjx-c class="mjx-c33"></mjx-c></mjx-mn></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>n</mi><mo>=</mo><mn>3</mn></math></mjx-assistive-mml></mjx-container></span> is indeed divisible by <em>3</em>.
In general, given a predicate <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="23" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D453 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>f</mi><mo stretchy="false">(</mo><mi>x</mi><mo stretchy="false">)</mo></math></mjx-assistive-mml></mjx-container></span> where <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="24" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>x</mi></math></mjx-assistive-mml></mjx-container></span> belongs to some set <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="25" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D446 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>S</mi></math></mjx-assistive-mml></mjx-container></span>,
we can use a quantifier on <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="26" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D453 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>f</mi></math></mjx-assistive-mml></mjx-container></span> to make a statement in one of two ways.</p>
<section id="exists">
<h3>Exists<a class="headerlink" href="#exists" title="Link to this heading">¶</a></h3>
<p>We can claim <em>“there exists</em> <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="27" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c2208"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="4"><mjx-c class="mjx-c1D446 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>x</mi><mo>∈</mo><mi>S</mi></math></mjx-assistive-mml></mjx-container></span> <em>such that</em> <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="28" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D453 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>f</mi><mo stretchy="false">(</mo><mi>x</mi><mo stretchy="false">)</mo></math></mjx-assistive-mml></mjx-container></span> <em>holds”</em>. This is
the <em>exists</em> quantifier, denoted <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="29" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-n"><mjx-c class="mjx-c2203"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi mathvariant="normal">∃</mi></math></mjx-assistive-mml></mjx-container></span>. In mathematical notation this statement
is:</p>
<div class="math-wrapper docutils container">
<div class="math notranslate nohighlight">
<mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" display="true" tabindex="0" ctxtmenu_counter="30" style="font-size: 119%; position: relative;"><mjx-math display="true" class="MJX-TEX" aria-hidden="true" style="margin-left: 0px; margin-right: 0px;"><mjx-mi class="mjx-n"><mjx-c class="mjx-c2203"></mjx-c></mjx-mi><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c2208"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="4"><mjx-c class="mjx-c1D446 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2E"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="2"><mjx-c class="mjx-c1D453 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="block"><math xmlns="http://www.w3.org/1998/Math/MathML" display="block"><mi mathvariant="normal">∃</mi><mi>x</mi><mo>∈</mo><mi>S</mi><mo>.</mo><mi>f</mi><mo stretchy="false">(</mo><mi>x</mi><mo stretchy="false">)</mo></math></mjx-assistive-mml></mjx-container></div>
</div>
<p>The exists quantifier can be thought of as a using the <em>or</em> operator over all
<span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="31" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c2208"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="4"><mjx-c class="mjx-c1D446 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>x</mi><mo>∈</mo><mi>S</mi></math></mjx-assistive-mml></mjx-container></span>. For example, the statement <em>“there exists a natural number</em> <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="32" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>n</mi></math></mjx-assistive-mml></mjx-container></span>
<em>which is divisible by 3”</em> is the same as:</p>
<div class="math-wrapper docutils container">
<div class="math notranslate nohighlight">
<mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" display="true" tabindex="0" ctxtmenu_counter="33" style="font-size: 119%; position: relative;"><mjx-math display="true" class="MJX-TEX" aria-hidden="true" style="margin-left: 0px; margin-right: 0px;"><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mn class="mjx-n"><mjx-c class="mjx-c31"></mjx-c></mjx-mn><mjx-mo class="mjx-n"><mjx-c class="mjx-c7C"></mjx-c></mjx-mo><mjx-mn class="mjx-n"><mjx-c class="mjx-c33"></mjx-c></mjx-mn><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2228"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mn class="mjx-n"><mjx-c class="mjx-c32"></mjx-c></mjx-mn><mjx-mo class="mjx-n"><mjx-c class="mjx-c7C"></mjx-c></mjx-mo><mjx-mn class="mjx-n"><mjx-c class="mjx-c33"></mjx-c></mjx-mn><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2228"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mn class="mjx-n"><mjx-c class="mjx-c33"></mjx-c></mjx-mn><mjx-mo class="mjx-n"><mjx-c class="mjx-c7C"></mjx-c></mjx-mo><mjx-mn class="mjx-n"><mjx-c class="mjx-c33"></mjx-c></mjx-mn><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2228"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mn class="mjx-n"><mjx-c class="mjx-c34"></mjx-c></mjx-mn><mjx-mo class="mjx-n"><mjx-c class="mjx-c7C"></mjx-c></mjx-mo><mjx-mn class="mjx-n"><mjx-c class="mjx-c33"></mjx-c></mjx-mn><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="2"><mjx-c class="mjx-c22EF"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c3D"></mjx-c></mjx-mo><mjx-munder space="4"><mjx-row><mjx-base style="padding-left: 0.148em;"><mjx-mo class="mjx-lop"><mjx-c class="mjx-c22C1 TEX-S2"></mjx-c></mjx-mo></mjx-base></mjx-row><mjx-row><mjx-under style="padding-top: 0.167em;"><mjx-texatom size="s" texclass="ORD"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2208"></mjx-c></mjx-mo><mjx-texatom texclass="ORD"><mjx-mi class="mjx-ds mjx-b"><mjx-c class="mjx-c2115 TEX-A"></mjx-c></mjx-mi></mjx-texatom></mjx-texatom></mjx-under></mjx-row></mjx-munder><mjx-mi class="mjx-i" space="2"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c7C"></mjx-c></mjx-mo><mjx-mn class="mjx-n"><mjx-c class="mjx-c33"></mjx-c></mjx-mn></mjx-math><mjx-assistive-mml unselectable="on" display="block"><math xmlns="http://www.w3.org/1998/Math/MathML" display="block"><mo stretchy="false">(</mo><mn>1</mn><mo data-mjx-texclass="ORD" fence="false" stretchy="false">|</mo><mn>3</mn><mo stretchy="false">)</mo><mo>∨</mo><mo stretchy="false">(</mo><mn>2</mn><mo data-mjx-texclass="ORD" fence="false" stretchy="false">|</mo><mn>3</mn><mo stretchy="false">)</mo><mo>∨</mo><mo stretchy="false">(</mo><mn>3</mn><mo data-mjx-texclass="ORD" fence="false" stretchy="false">|</mo><mn>3</mn><mo stretchy="false">)</mo><mo>∨</mo><mo stretchy="false">(</mo><mn>4</mn><mo data-mjx-texclass="ORD" fence="false" stretchy="false">|</mo><mn>3</mn><mo stretchy="false">)</mo><mo>⋯</mo><mo>=</mo><munder><mo data-mjx-texclass="OP">⋁</mo><mrow data-mjx-texclass="ORD"><mi>n</mi><mo>∈</mo><mrow data-mjx-texclass="ORD"><mi mathvariant="double-struck">N</mi></mrow></mrow></munder><mi>n</mi><mo data-mjx-texclass="ORD" fence="false" stretchy="false">|</mo><mn>3</mn></math></mjx-assistive-mml></mjx-container></div>
</div>
<p>Solidity code realizing this is:</p>
<div class="highlight-solidity notranslate"><div class="highlight"><pre><span></span><span class="kt">function</span><span class="w"> </span><span class="nv">existsDivisibleByThree</span><span class="p">()</span><span class="w"> </span><span class="kt">external</span><span class="w"> </span><span class="kt">returns</span><span class="w"> </span><span class="p">(</span><span class="kt">bool</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">  </span><span class="kt">for</span><span class="w"> </span><span class="p">(</span><span class="kt">uint256</span><span class="w"> </span><span class="nv">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="m m-Decimal">1</span><span class="p">;</span><span class="w"> </span>i<span class="w"> </span><span class="o">&lt;</span><span class="w"> </span>type<span class="p">(</span><span class="kt">uint256</span><span class="p">).</span>max<span class="p">;</span><span class="w"> </span>i<span class="o">++</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kt">if</span><span class="w"> </span><span class="p">(</span>i<span class="w"> </span><span class="o">%</span><span class="w"> </span><span class="m m-Decimal">3</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">)</span><span class="w"> </span><span class="kt">return</span><span class="w"> </span><span class="kt">true</span><span class="p">;</span>
<span class="w">  </span><span class="p">}</span>
<span class="w">  </span><span class="kt">return</span><span class="w"> </span><span class="kt">false</span><span class="p">;</span>
<span class="p">}</span>
</pre></div>
</div>
<p>In CVL we have the keyword <code class="docutils literal notranslate"><span class="pre">exists</span></code>, for example:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre><span></span><span class="kr">require</span><span class="w"> </span><span class="p">(</span><span class="kr">exists</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>n<span class="p">.</span><span class="w"> </span><span class="p">(</span>n<span class="w"> </span><span class="o">%</span><span class="w"> </span><span class="m m-Decimal">3</span><span class="p">)</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">);</span>
</pre></div>
</div>
</section>
<section id="for-all">
<h3>For all<a class="headerlink" href="#for-all" title="Link to this heading">¶</a></h3>
<p>The <em>forall</em> quantifier requires that the predicate be satisfied by all possible inputs.
An example of this is the statement:
<em>“for all natural numbers</em> <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="34" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>n</mi></math></mjx-assistive-mml></mjx-container></span> <em>either</em> <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="35" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>n</mi></math></mjx-assistive-mml></mjx-container></span> <em>is even, or</em> <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="36" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2B"></mjx-c></mjx-mo><mjx-mn class="mjx-n" space="3"><mjx-c class="mjx-c31"></mjx-c></mjx-mn></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>n</mi><mo>+</mo><mn>1</mn></math></mjx-assistive-mml></mjx-container></span>
<em>is even”</em>. The forall quantifier is denoted <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="37" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-n"><mjx-c class="mjx-c2200"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi mathvariant="normal">∀</mi></math></mjx-assistive-mml></mjx-container></span>, so the statement in
mathematical notation is:</p>
<div class="math-wrapper docutils container">
<div class="math notranslate nohighlight">
<mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" display="true" tabindex="0" ctxtmenu_counter="38" style="font-size: 119%; position: relative;"><mjx-math display="true" class="MJX-TEX" aria-hidden="true" style="margin-left: 0px; margin-right: 0px;"><mjx-mi class="mjx-n"><mjx-c class="mjx-c2200"></mjx-c></mjx-mi><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c2208"></mjx-c></mjx-mo><mjx-texatom space="4" texclass="ORD"><mjx-mi class="mjx-ds mjx-b"><mjx-c class="mjx-c2115 TEX-A"></mjx-c></mjx-mi></mjx-texatom><mjx-mo class="mjx-n"><mjx-c class="mjx-c2E"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="2"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c7C"></mjx-c></mjx-mo><mjx-mn class="mjx-n"><mjx-c class="mjx-c32"></mjx-c></mjx-mn><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2228"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2B"></mjx-c></mjx-mo><mjx-mn class="mjx-n" space="3"><mjx-c class="mjx-c31"></mjx-c></mjx-mn><mjx-mo class="mjx-n"><mjx-c class="mjx-c7C"></mjx-c></mjx-mo><mjx-mn class="mjx-n"><mjx-c class="mjx-c32"></mjx-c></mjx-mn><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="block"><math xmlns="http://www.w3.org/1998/Math/MathML" display="block"><mi mathvariant="normal">∀</mi><mi>n</mi><mo>∈</mo><mrow data-mjx-texclass="ORD"><mi mathvariant="double-struck">N</mi></mrow><mo>.</mo><mo stretchy="false">(</mo><mi>n</mi><mo data-mjx-texclass="ORD" fence="false" stretchy="false">|</mo><mn>2</mn><mo stretchy="false">)</mo><mo>∨</mo><mo stretchy="false">(</mo><mi>n</mi><mo>+</mo><mn>1</mn><mo data-mjx-texclass="ORD" fence="false" stretchy="false">|</mo><mn>2</mn><mo stretchy="false">)</mo></math></mjx-assistive-mml></mjx-container></div>
</div>
<p>In general, given a predicate <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="39" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D453 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>f</mi><mo stretchy="false">(</mo><mi>x</mi><mo stretchy="false">)</mo></math></mjx-assistive-mml></mjx-container></span> where <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="40" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c2208"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="4"><mjx-c class="mjx-c1D446 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>x</mi><mo>∈</mo><mi>S</mi></math></mjx-assistive-mml></mjx-container></span>, we can form the
statement <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="41" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-n"><mjx-c class="mjx-c2200"></mjx-c></mjx-mi><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c2208"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="4"><mjx-c class="mjx-c1D446 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2E"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="2"><mjx-c class="mjx-c1D453 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi mathvariant="normal">∀</mi><mi>x</mi><mo>∈</mo><mi>S</mi><mo>.</mo><mi>f</mi><mo stretchy="false">(</mo><mi>x</mi><mo stretchy="false">)</mo></math></mjx-assistive-mml></mjx-container></span>. The forall quantifier is the same as using
the <em>and</em> operator on <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="42" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D453 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>f</mi><mo stretchy="false">(</mo><mi>x</mi><mo stretchy="false">)</mo></math></mjx-assistive-mml></mjx-container></span> for all <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="43" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c2208"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="4"><mjx-c class="mjx-c1D446 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>x</mi><mo>∈</mo><mi>S</mi></math></mjx-assistive-mml></mjx-container></span>, in mathematical notation:</p>
<div class="math-wrapper docutils container">
<div class="math notranslate nohighlight">
<mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" display="true" tabindex="0" ctxtmenu_counter="44" style="font-size: 119%; position: relative;"><mjx-math display="true" class="MJX-TEX" aria-hidden="true" style="margin-left: 0px; margin-right: 0px;"><mjx-mi class="mjx-n"><mjx-c class="mjx-c2200"></mjx-c></mjx-mi><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c2208"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="4"><mjx-c class="mjx-c1D446 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2E"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="2"><mjx-c class="mjx-c1D453 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c3D"></mjx-c></mjx-mo><mjx-munder space="4"><mjx-row><mjx-base style="padding-left: 0.111em;"><mjx-mo class="mjx-lop"><mjx-c class="mjx-c22C0 TEX-S2"></mjx-c></mjx-mo></mjx-base></mjx-row><mjx-row><mjx-under style="padding-top: 0.167em;"><mjx-texatom size="s" texclass="ORD"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2208"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D446 TEX-I"></mjx-c></mjx-mi></mjx-texatom></mjx-under></mjx-row></mjx-munder><mjx-mi class="mjx-i" space="2"><mjx-c class="mjx-c1D453 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="block"><math xmlns="http://www.w3.org/1998/Math/MathML" display="block"><mi mathvariant="normal">∀</mi><mi>x</mi><mo>∈</mo><mi>S</mi><mo>.</mo><mi>f</mi><mo stretchy="false">(</mo><mi>x</mi><mo stretchy="false">)</mo><mo>=</mo><munder><mo data-mjx-texclass="OP">⋀</mo><mrow data-mjx-texclass="ORD"><mi>x</mi><mo>∈</mo><mi>S</mi></mrow></munder><mi>f</mi><mo stretchy="false">(</mo><mi>x</mi><mo stretchy="false">)</mo></math></mjx-assistive-mml></mjx-container></div>
</div>
<p>The negation of a forall statement can be given in the form of an exists statement,
like this (the negation is denoted by the symbol <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="45" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-n"><mjx-c class="mjx-cAC"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi mathvariant="normal">¬</mi></math></mjx-assistive-mml></mjx-container></span>):</p>
<div class="math-wrapper docutils container">
<div class="math notranslate nohighlight">
<mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" display="true" tabindex="0" ctxtmenu_counter="46" style="font-size: 119%; position: relative;"><mjx-math display="true" class="MJX-TEX" aria-hidden="true" style="margin-left: 0px; margin-right: 0px;"><mjx-mi class="mjx-n"><mjx-c class="mjx-cAC"></mjx-c></mjx-mi><mjx-mrow space="2"><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-n"><mjx-c class="mjx-c2200"></mjx-c></mjx-mi><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c2208"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="4"><mjx-c class="mjx-c1D446 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2E"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="2"><mjx-c class="mjx-c1D453 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo></mjx-mrow><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c3D"></mjx-c></mjx-mo><mjx-mi class="mjx-n" space="4"><mjx-c class="mjx-c2203"></mjx-c></mjx-mi><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c2208"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="4"><mjx-c class="mjx-c1D446 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2E"></mjx-c></mjx-mo><mjx-mi class="mjx-n" space="2"><mjx-c class="mjx-cAC"></mjx-c></mjx-mi><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D453 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="block"><math xmlns="http://www.w3.org/1998/Math/MathML" display="block"><mi mathvariant="normal">¬</mi><mrow data-mjx-texclass="INNER"><mo data-mjx-texclass="OPEN">(</mo><mi mathvariant="normal">∀</mi><mi>x</mi><mo>∈</mo><mi>S</mi><mo>.</mo><mi>f</mi><mo stretchy="false">(</mo><mi>x</mi><mo stretchy="false">)</mo><mo data-mjx-texclass="CLOSE">)</mo></mrow><mo>=</mo><mi mathvariant="normal">∃</mi><mi>x</mi><mo>∈</mo><mi>S</mi><mo>.</mo><mi mathvariant="normal">¬</mi><mi>f</mi><mo stretchy="false">(</mo><mi>x</mi><mo stretchy="false">)</mo></math></mjx-assistive-mml></mjx-container></div>
</div>
<p>This comes in handy when writing code realizing a forall statement.</p>
<section id="id3">
<h4>Example:<a class="headerlink" href="#id3" title="Link to this heading">¶</a></h4>
<p>Here is the solidity code realizing the statement <em>“for all</em> <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="47" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>n</mi></math></mjx-assistive-mml></mjx-container></span> <em>either</em> <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="48" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>n</mi></math></mjx-assistive-mml></mjx-container></span>
<em>is even, or</em> <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="49" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2B"></mjx-c></mjx-mo><mjx-mn class="mjx-n" space="3"><mjx-c class="mjx-c31"></mjx-c></mjx-mn></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>n</mi><mo>+</mo><mn>1</mn></math></mjx-assistive-mml></mjx-container></span> <em>is even”</em>:</p>
<div class="highlight-solidity notranslate"><div class="highlight"><pre><span></span><span class="kt">function</span><span class="w"> </span><span class="nv">allAreEven</span><span class="p">()</span><span class="w"> </span><span class="kt">external</span><span class="w"> </span><span class="kt">returns</span><span class="w"> </span><span class="p">(</span><span class="kt">bool</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">  </span><span class="kt">for</span><span class="w"> </span><span class="p">(</span><span class="kt">uint256</span><span class="w"> </span><span class="nv">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="m m-Decimal">1</span><span class="p">;</span><span class="w"> </span>i<span class="w"> </span><span class="o">&lt;</span><span class="w"> </span>type<span class="p">(</span><span class="kt">uint256</span><span class="p">).</span>max<span class="p">;</span><span class="w"> </span>i<span class="o">++</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="kt">if</span><span class="w"> </span><span class="p">(</span>i<span class="w"> </span><span class="o">%</span><span class="w"> </span><span class="m m-Decimal">2</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span><span class="p">(</span>i<span class="w"> </span><span class="o">+</span><span class="w"> </span><span class="m m-Decimal">1</span><span class="p">)</span><span class="w"> </span><span class="o">%</span><span class="m m-Decimal">2</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">)</span><span class="w"> </span><span class="kt">return</span><span class="w"> </span><span class="kt">false</span><span class="p">;</span>
<span class="w">  </span><span class="p">}</span>
<span class="w">  </span><span class="kt">return</span><span class="w"> </span><span class="kt">true</span><span class="p">;</span>
<span class="p">}</span>
</pre></div>
</div>
<p>In CVL we have the keyword <code class="docutils literal notranslate"><span class="pre">forall</span></code>, for example:</p>
<div class="highlight-cvl notranslate"><div class="highlight"><pre><span></span><span class="kr">require</span><span class="w"> </span><span class="p">(</span><span class="kr">forall</span><span class="w"> </span><span class="kt">uint</span><span class="w"> </span>n<span class="p">.</span><span class="w"> </span><span class="p">(</span>n<span class="w"> </span><span class="o">%</span><span class="w"> </span><span class="m m-Decimal">2</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">)</span><span class="w"> </span><span class="o">||</span><span class="w"> </span><span class="p">((</span>n<span class="w"> </span><span class="o">+</span><span class="w"> </span><span class="m m-Decimal">1</span><span class="p">)</span><span class="w"> </span><span class="o">%</span><span class="w"> </span><span class="m m-Decimal">2</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="m m-Decimal">0</span><span class="p">));</span>
</pre></div>
</div>
</section>
</section>
</section>
<section id="vacuity">
<span id="index-4"></span><h2>Vacuity<a class="headerlink" href="#vacuity" title="Link to this heading">¶</a></h2>
<p>Consider the statement:
<em>“For all</em> <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="50" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c2208"></mjx-c></mjx-mo><mjx-texatom space="4" texclass="ORD"><mjx-mi class="mjx-ds mjx-b"><mjx-c class="mjx-c2115 TEX-A"></mjx-c></mjx-mi></mjx-texatom></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>n</mi><mo>∈</mo><mrow data-mjx-texclass="ORD"><mi mathvariant="double-struck">N</mi></mrow></math></mjx-assistive-mml></mjx-container></span> <em>if both</em> <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="51" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>n</mi></math></mjx-assistive-mml></mjx-container></span> <em>and</em> <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="52" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2B"></mjx-c></mjx-mo><mjx-mn class="mjx-n" space="3"><mjx-c class="mjx-c31"></mjx-c></mjx-mn></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>n</mi><mo>+</mo><mn>1</mn></math></mjx-assistive-mml></mjx-container></span>
<em>are even, then</em> <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="53" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c3D"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="4"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2B"></mjx-c></mjx-mo><mjx-mn class="mjx-n" space="3"><mjx-c class="mjx-c32"></mjx-c></mjx-mn></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>n</mi><mo>=</mo><mi>n</mi><mo>+</mo><mn>2</mn></math></mjx-assistive-mml></mjx-container></span> <em>“</em>. In mathematical notation:</p>
<div class="math-wrapper docutils container">
<div class="math notranslate nohighlight">
<mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" display="true" tabindex="0" ctxtmenu_counter="54" style="font-size: 119%; position: relative;"><mjx-math display="true" class="MJX-TEX" aria-hidden="true" style="margin-left: 0px; margin-right: 0px;"><mjx-mi class="mjx-n"><mjx-c class="mjx-c2200"></mjx-c></mjx-mi><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c2208"></mjx-c></mjx-mo><mjx-texatom space="4" texclass="ORD"><mjx-mi class="mjx-ds mjx-b"><mjx-c class="mjx-c2115 TEX-A"></mjx-c></mjx-mi></mjx-texatom><mjx-mo class="mjx-n"><mjx-c class="mjx-c2E"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="2"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c7C"></mjx-c></mjx-mo><mjx-mn class="mjx-n"><mjx-c class="mjx-c32"></mjx-c></mjx-mn><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2227"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2B"></mjx-c></mjx-mo><mjx-mn class="mjx-n" space="3"><mjx-c class="mjx-c31"></mjx-c></mjx-mn><mjx-mo class="mjx-n"><mjx-c class="mjx-c7C"></mjx-c></mjx-mo><mjx-mn class="mjx-n"><mjx-c class="mjx-c32"></mjx-c></mjx-mn><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo><mjx-mstyle><mjx-mspace style="width: 0.278em;"></mjx-mspace></mjx-mstyle><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c27F9"></mjx-c></mjx-mo><mjx-mstyle><mjx-mspace style="width: 0.278em;"></mjx-mspace></mjx-mstyle><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c3D"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="4"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2B"></mjx-c></mjx-mo><mjx-mn class="mjx-n" space="3"><mjx-c class="mjx-c32"></mjx-c></mjx-mn><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="block"><math xmlns="http://www.w3.org/1998/Math/MathML" display="block"><mi mathvariant="normal">∀</mi><mi>n</mi><mo>∈</mo><mrow data-mjx-texclass="ORD"><mi mathvariant="double-struck">N</mi></mrow><mo>.</mo><mo stretchy="false">(</mo><mi>n</mi><mo data-mjx-texclass="ORD" fence="false" stretchy="false">|</mo><mn>2</mn><mo stretchy="false">)</mo><mo>∧</mo><mo stretchy="false">(</mo><mi>n</mi><mo>+</mo><mn>1</mn><mo data-mjx-texclass="ORD" fence="false" stretchy="false">|</mo><mn>2</mn><mo stretchy="false">)</mo><mstyle scriptlevel="0"><mspace width="0.278em"></mspace></mstyle><mo stretchy="false">⟹</mo><mstyle scriptlevel="0"><mspace width="0.278em"></mspace></mstyle><mo stretchy="false">(</mo><mi>n</mi><mo>=</mo><mi>n</mi><mo>+</mo><mn>2</mn><mo stretchy="false">)</mo></math></mjx-assistive-mml></mjx-container></div>
</div>
<p>Surprisingly, this statement is <strong>true</strong>. Because for every <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="55" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>n</mi></math></mjx-assistive-mml></mjx-container></span> the
part <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="56" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c7C"></mjx-c></mjx-mo><mjx-mn class="mjx-n"><mjx-c class="mjx-c32"></mjx-c></mjx-mn><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2227"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2B"></mjx-c></mjx-mo><mjx-mn class="mjx-n" space="3"><mjx-c class="mjx-c31"></mjx-c></mjx-mn><mjx-mo class="mjx-n"><mjx-c class="mjx-c7C"></mjx-c></mjx-mo><mjx-mn class="mjx-n"><mjx-c class="mjx-c32"></mjx-c></mjx-mn><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo stretchy="false">(</mo><mi>n</mi><mo data-mjx-texclass="ORD" fence="false" stretchy="false">|</mo><mn>2</mn><mo stretchy="false">)</mo><mo>∧</mo><mo stretchy="false">(</mo><mi>n</mi><mo>+</mo><mn>1</mn><mo data-mjx-texclass="ORD" fence="false" stretchy="false">|</mo><mn>2</mn><mo stretchy="false">)</mo></math></mjx-assistive-mml></mjx-container></span> is always <strong>false</strong>, so by the
<a class="reference internal" href="#truth-table-for-implication"><span class="std std-ref">Truth table for implication</span></a> the implication is <strong>true</strong>.</p>
<p>In general, given a statement of the form <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="57" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-n"><mjx-c class="mjx-c2200"></mjx-c></mjx-mi><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c2208"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="4"><mjx-c class="mjx-c1D446 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2E"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="2"><mjx-c class="mjx-c1D453 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo><mjx-mstyle><mjx-mspace style="width: 0.278em;"></mjx-mspace></mjx-mstyle><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c27F9"></mjx-c></mjx-mo><mjx-mstyle><mjx-mspace style="width: 0.278em;"></mjx-mspace></mjx-mstyle><mjx-mi class="mjx-i" space="4"><mjx-c class="mjx-c1D454 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi mathvariant="normal">∀</mi><mi>x</mi><mo>∈</mo><mi>S</mi><mo>.</mo><mi>f</mi><mo stretchy="false">(</mo><mi>x</mi><mo stretchy="false">)</mo><mstyle scriptlevel="0"><mspace width="0.278em"></mspace></mstyle><mo stretchy="false">⟹</mo><mstyle scriptlevel="0"><mspace width="0.278em"></mspace></mstyle><mi>g</mi><mo stretchy="false">(</mo><mi>x</mi><mo stretchy="false">)</mo></math></mjx-assistive-mml></mjx-container></span>
where <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="58" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D453 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>f</mi></math></mjx-assistive-mml></mjx-container></span> and <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="59" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D454 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>g</mi></math></mjx-assistive-mml></mjx-container></span> are predicates, we say the statement <em>holds vacuously</em>
(or <em>is satisfied vacuously</em>)
if <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="60" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-n"><mjx-c class="mjx-c2200"></mjx-c></mjx-mi><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c2208"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="4"><mjx-c class="mjx-c1D446 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2E"></mjx-c></mjx-mo><mjx-mi class="mjx-n" space="2"><mjx-c class="mjx-cAC"></mjx-c></mjx-mi><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D453 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi mathvariant="normal">∀</mi><mi>x</mi><mo>∈</mo><mi>S</mi><mo>.</mo><mi mathvariant="normal">¬</mi><mi>f</mi><mo stretchy="false">(</mo><mi>x</mi><mo stretchy="false">)</mo></math></mjx-assistive-mml></mjx-container></span>. This means there is not even a single
element <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="61" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c2208"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="4"><mjx-c class="mjx-c1D446 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>x</mi><mo>∈</mo><mi>S</mi></math></mjx-assistive-mml></mjx-container></span> for which <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="62" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D453 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D465 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>f</mi><mo stretchy="false">(</mo><mi>x</mi><mo stretchy="false">)</mo></math></mjx-assistive-mml></mjx-container></span> holds.</p>
<p>While this may seem like an edge case, it can easily occur that heaping conditions
on a statement ends with the statement being satisfied vacuously.</p>
</section>
<section id="logical-operators-and-quantifiers">
<h2>Logical operators and quantifiers<a class="headerlink" href="#logical-operators-and-quantifiers" title="Link to this heading">¶</a></h2>
<div class="table-wrapper docutils container" id="id6">
<span id="logical-operators-table"></span><span id="index-5"></span><span id="logical-operators-table"></span><span id="index-5"></span><table class="docutils align-default" id="id6">
<caption><span class="caption-text">Logical operators and quantifiers table</span><a class="headerlink" href="#id6" title="Link to this table">¶</a></caption>
<thead>
<tr class="row-odd"><th class="head stub"><p>Name</p></th>
<th class="head"><p>Math symbol</p></th>
<th class="head"><p>CVL</p></th>
<th class="head"><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="row-even"><th class="stub"><p>and</p></th>
<td><p><span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="63" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2227"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo>∧</mo></math></mjx-assistive-mml></mjx-container></span></p></td>
<td><p><code class="docutils literal notranslate"><span class="pre">&amp;&amp;</span></code></p></td>
<td><p>And operation</p></td>
</tr>
<tr class="row-odd"><th class="stub"><p>or</p></th>
<td><p><span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="64" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2228"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo>∨</mo></math></mjx-assistive-mml></mjx-container></span></p></td>
<td><p><code class="docutils literal notranslate"><span class="pre">||</span></code></p></td>
<td><p>Or operation</p></td>
</tr>
<tr class="row-even"><th class="stub"><p>implies</p></th>
<td><p><span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="65" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mstyle><mjx-mspace style="width: 0.278em;"></mjx-mspace></mjx-mstyle><mjx-mo class="mjx-n"><mjx-c class="mjx-c27F9"></mjx-c></mjx-mo><mjx-mstyle><mjx-mspace style="width: 0.278em;"></mjx-mspace></mjx-mstyle></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mstyle scriptlevel="0"><mspace width="0.278em"></mspace></mstyle><mo stretchy="false">⟹</mo><mstyle scriptlevel="0"><mspace width="0.278em"></mspace></mstyle></math></mjx-assistive-mml></mjx-container></span></p></td>
<td><p><code class="docutils literal notranslate"><span class="pre">=&gt;</span></code></p></td>
<td><p>Implication operation</p></td>
</tr>
<tr class="row-odd"><th class="stub"><p>not</p></th>
<td><p><span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="66" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-n"><mjx-c class="mjx-cAC"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi mathvariant="normal">¬</mi></math></mjx-assistive-mml></mjx-container></span></p></td>
<td><p><code class="docutils literal notranslate"><span class="pre">!</span></code></p></td>
<td><p>Negation operation</p></td>
</tr>
<tr class="row-even"><th class="stub"><p>if and only if</p></th>
<td><p><span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="67" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mo class="mjx-n"><mjx-c class="mjx-c27FA"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo stretchy="false">⟺</mo></math></mjx-assistive-mml></mjx-container></span></p></td>
<td><p><code class="docutils literal notranslate"><span class="pre">&lt;=&gt;</span></code>
(also <code class="code highlight cvl docutils literal highlight-cvl"><span class="o">==</span></code>, see below)</p></td>
<td><p>Equality of booleans</p></td>
</tr>
<tr class="row-odd"><th class="stub"><p>forall</p></th>
<td><p><span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="68" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-n"><mjx-c class="mjx-c2200"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi mathvariant="normal">∀</mi></math></mjx-assistive-mml></mjx-container></span></p></td>
<td><p><code class="docutils literal notranslate"><span class="pre">forall</span></code></p></td>
<td><p>For all elements in a set, it holds that …</p></td>
</tr>
<tr class="row-even"><th class="stub"><p>exist</p></th>
<td><p><span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="69" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-n"><mjx-c class="mjx-c2203"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi mathvariant="normal">∃</mi></math></mjx-assistive-mml></mjx-container></span></p></td>
<td><p><code class="docutils literal notranslate"><span class="pre">exist</span></code></p></td>
<td><p>There exists an element in a set, such that …</p></td>
</tr>
</tbody>
</table>
</div>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>The <em>“if and only if”</em> operator is the same as euqality of booleans, meaning
<span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="70" style="font-size: 119.2%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D443 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c27FA"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="4"><mjx-c class="mjx-c1D444 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>P</mi><mo stretchy="false">⟺</mo><mi>Q</mi></math></mjx-assistive-mml></mjx-container></span> is the same as <code class="code highlight cvl docutils literal highlight-cvl">P<span class="w"> </span><span class="o">==</span><span class="w"> </span>Q</code>.</p>
</div>
</section>
<section id="quiz">
<span id="propositional-logic-quiz"></span><h2>Quiz<a class="headerlink" href="#quiz" title="Link to this heading">¶</a></h2>
<p>Test your knowledge with our quiz below (additional questions can be found on the
first part of the <a class="reference external" href="https://docs.google.com/document/d/19lLWqTrm_bzDdY9Uk-LpTSkgabk9WGtuCTPLDzSoraM/edit?usp=sharing">Secureum Quiz</a>).</p>
<ol class="arabic simple">
<li><p>When is the expression <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="71" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D443 TEX-I"></mjx-c></mjx-mi><mjx-mstyle><mjx-mspace style="width: 0.278em;"></mjx-mspace></mjx-mstyle><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c27F9"></mjx-c></mjx-mo><mjx-mstyle><mjx-mspace style="width: 0.278em;"></mjx-mspace></mjx-mstyle><mjx-mi class="mjx-i" space="4"><mjx-c class="mjx-c1D444 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>P</mi><mstyle scriptlevel="0"><mspace width="0.278em"></mspace></mstyle><mo stretchy="false">⟹</mo><mstyle scriptlevel="0"><mspace width="0.278em"></mspace></mstyle><mi>Q</mi></math></mjx-assistive-mml></mjx-container></span> <em>false</em>?</p>
<ol class="arabic simple">
<li><p>When <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="72" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-n"><mjx-c class="mjx-cAC"></mjx-c></mjx-mi><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D443 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2227"></mjx-c></mjx-mo><mjx-mi class="mjx-n" space="3"><mjx-c class="mjx-cAC"></mjx-c></mjx-mi><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D444 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi mathvariant="normal">¬</mi><mi>P</mi><mo>∧</mo><mi mathvariant="normal">¬</mi><mi>Q</mi></math></mjx-assistive-mml></mjx-container></span> is true
(i.e. when both <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="73" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D443 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>P</mi></math></mjx-assistive-mml></mjx-container></span> and <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="74" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D444 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>Q</mi></math></mjx-assistive-mml></mjx-container></span> are false)</p></li>
<li><p>When <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="75" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D443 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2227"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="3"><mjx-c class="mjx-c1D444 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>P</mi><mo>∧</mo><mi>Q</mi></math></mjx-assistive-mml></mjx-container></span> is true</p></li>
<li><p>When <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="76" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-n"><mjx-c class="mjx-cAC"></mjx-c></mjx-mi><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D443 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2227"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="3"><mjx-c class="mjx-c1D444 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi mathvariant="normal">¬</mi><mi>P</mi><mo>∧</mo><mi>Q</mi></math></mjx-assistive-mml></mjx-container></span> is true</p></li>
<li><p>None of the above</p></li>
</ol>
</li>
<li><p>When is the expression <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="77" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D443 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2227"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="3"><mjx-c class="mjx-c1D444 TEX-I"></mjx-c></mjx-mi><mjx-mtext class="mjx-n"><mjx-c class="mjx-cA0"></mjx-c></mjx-mtext><mjx-mstyle><mjx-mspace style="width: 0.278em;"></mjx-mspace></mjx-mstyle><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c27F9"></mjx-c></mjx-mo><mjx-mstyle><mjx-mspace style="width: 0.278em;"></mjx-mspace></mjx-mstyle><mjx-mi class="mjx-i" space="4"><mjx-c class="mjx-c1D443 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>P</mi><mo>∧</mo><mi>Q</mi><mtext>&nbsp;</mtext><mstyle scriptlevel="0"><mspace width="0.278em"></mspace></mstyle><mo stretchy="false">⟹</mo><mstyle scriptlevel="0"><mspace width="0.278em"></mspace></mstyle><mi>P</mi></math></mjx-assistive-mml></mjx-container></span> <em>true</em>?</p>
<ol class="arabic simple">
<li><p>Always (it is true in all cases)</p></li>
<li><p>Never (it is false in all cases)</p></li>
<li><p>True for some cases and false for others</p></li>
<li><p>None of the above</p></li>
</ol>
</li>
<li><p>When is the expression
<span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="78" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mrow><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D443 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2227"></mjx-c></mjx-mo><mjx-mrow space="3"><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D444 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2228"></mjx-c></mjx-mo><mjx-mi class="mjx-n" space="3"><mjx-c class="mjx-cAC"></mjx-c></mjx-mi><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D443 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo></mjx-mrow><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo></mjx-mrow><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2227"></mjx-c></mjx-mo><mjx-mi class="mjx-n" space="3"><mjx-c class="mjx-cAC"></mjx-c></mjx-mi><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D444 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mrow data-mjx-texclass="INNER"><mo data-mjx-texclass="OPEN">(</mo><mi>P</mi><mo>∧</mo><mrow data-mjx-texclass="INNER"><mo data-mjx-texclass="OPEN">(</mo><mi>Q</mi><mo>∨</mo><mi mathvariant="normal">¬</mi><mi>P</mi><mo data-mjx-texclass="CLOSE">)</mo></mrow><mo data-mjx-texclass="CLOSE">)</mo></mrow><mo>∧</mo><mi mathvariant="normal">¬</mi><mi>Q</mi></math></mjx-assistive-mml></mjx-container></span> <em>true</em>?</p>
<ol class="arabic simple">
<li><p>Always (it is true in all cases)</p></li>
<li><p>Never (it is false in all cases)</p></li>
<li><p>True for some cases and false for others</p></li>
</ol>
</li>
<li><p>If we know that the expression <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="79" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D443 TEX-I"></mjx-c></mjx-mi><mjx-mstyle><mjx-mspace style="width: 0.278em;"></mjx-mspace></mjx-mstyle><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c27F9"></mjx-c></mjx-mo><mjx-mstyle><mjx-mspace style="width: 0.278em;"></mjx-mspace></mjx-mstyle><mjx-mrow space="4"><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D443 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2227"></mjx-c></mjx-mo><mjx-mi class="mjx-n" space="3"><mjx-c class="mjx-cAC"></mjx-c></mjx-mi><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D444 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo></mjx-mrow></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>P</mi><mstyle scriptlevel="0"><mspace width="0.278em"></mspace></mstyle><mo stretchy="false">⟹</mo><mstyle scriptlevel="0"><mspace width="0.278em"></mspace></mstyle><mrow data-mjx-texclass="INNER"><mo data-mjx-texclass="OPEN">(</mo><mi>P</mi><mo>∧</mo><mi mathvariant="normal">¬</mi><mi>Q</mi><mo data-mjx-texclass="CLOSE">)</mo></mrow></math></mjx-assistive-mml></mjx-container></span> is
<em>true</em>, and that <span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="80" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D443 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>P</mi></math></mjx-assistive-mml></mjx-container></span> is <em>true</em>, then we can deduce that:</p>
<ol class="arabic simple">
<li><p><span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="81" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D444 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>Q</mi></math></mjx-assistive-mml></mjx-container></span> is true</p></li>
<li><p><span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="82" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D444 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>Q</mi></math></mjx-assistive-mml></mjx-container></span> is false</p></li>
<li><p><span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="83" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D444 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>Q</mi></math></mjx-assistive-mml></mjx-container></span> can be either true or false (we can deduce nothing)</p></li>
</ol>
</li>
</ol>
<details class="sd-sphinx-override sd-dropdown sd-card sd-mb-3 sd-fade-in-slide-down">
<summary class="sd-summary-title sd-card-header">
<span class="sd-summary-text">Answers</span><span class="sd-summary-state-marker sd-summary-chevron-right"><svg version="1.1" width="1.5em" height="1.5em" class="sd-octicon sd-octicon-chevron-right" viewBox="0 0 24 24" aria-hidden="true"><path d="M8.72 18.78a.75.75 0 0 1 0-1.06L14.44 12 8.72 6.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018l6.25 6.25a.75.75 0 0 1 0 1.06l-6.25 6.25a.75.75 0 0 1-1.06 0Z"></path></svg></span></summary><div class="sd-summary-content sd-card-body docutils">
<ol class="arabic simple">
<li><ol class="arabic simple" start="4">
<li><p class="sd-card-text">None of the above</p></li>
</ol>
</li>
<li><ol class="arabic simple">
<li><p class="sd-card-text">Always</p></li>
</ol>
</li>
<li><ol class="arabic simple" start="2">
<li><p class="sd-card-text">Never</p></li>
</ol>
</li>
<li><ol class="arabic simple" start="2">
<li><p class="sd-card-text"><span class="math notranslate nohighlight"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="84" style="font-size: 119%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D444 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>Q</mi></math></mjx-assistive-mml></mjx-container></span> is false</p></li>
</ol>
</li>
</ol>
</div>
</details></section>
</section>

        </article>
      </div>
      <footer>
        
        <div class="related-pages">
          <a class="next-page" href="formal_verification.html">
              <div class="page-info">
                <div class="context">
                  <span>Next</span>
                </div>
                <div class="title"><span class="section-number">1.3. </span>Introduction to formal verification</div>
              </div>
              <svg class="furo-related-icon"><use href="#svg-arrow-right"></use></svg>
            </a>
          <a class="prev-page" href="background.html">
              <svg class="furo-related-icon"><use href="#svg-arrow-right"></use></svg>
              <div class="page-info">
                <div class="context">
                  <span>Previous</span>
                </div>
                
                <div class="title"><span class="section-number">1.1. </span>Background</div>
                
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
<li><a class="reference internal" href="#">1.2. Introduction to predicate logic</a><ul>
<li><a class="reference internal" href="#propositional-logic">Propositional logic</a><ul>
<li><a class="reference internal" href="#propositions">Propositions</a><ul>
<li><a class="reference internal" href="#example">Example:</a></li>
</ul>
</li>
<li><a class="reference internal" href="#the-implication-operator">The implication operator</a></li>
<li><a class="reference internal" href="#examples">Examples</a></li>
<li><a class="reference internal" href="#truth-tables">Truth tables</a><ul>
<li><a class="reference internal" href="#example-implication-truth-table">Example: Implication truth table</a></li>
</ul>
</li>
</ul>
</li>
<li><a class="reference internal" href="#predicates">Predicates</a><ul>
<li><a class="reference internal" href="#id2">Example:</a></li>
</ul>
</li>
<li><a class="reference internal" href="#quantifiers">Quantifiers</a><ul>
<li><a class="reference internal" href="#exists">Exists</a></li>
<li><a class="reference internal" href="#for-all">For all</a><ul>
<li><a class="reference internal" href="#id3">Example:</a></li>
</ul>
</li>
</ul>
</li>
<li><a class="reference internal" href="#vacuity">Vacuity</a></li>
<li><a class="reference internal" href="#logical-operators-and-quantifiers">Logical operators and quantifiers</a></li>
<li><a class="reference internal" href="#quiz">Quiz</a></li>
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