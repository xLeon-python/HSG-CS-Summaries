---
title: Entwurf von Softwaresystemen
author: Leon Muscat
keywords: [CS]
subtitle: subtitle here
numbersections: true
lang: en
titlepage: true
titlepage-rule-color: 360049
titlepage-background: ../../background.pdf
toc: true
toc-own-page: true
float-placement-figure: H
caption-justification: centering
colorlinks: true
header-includes:
- |
  ```{=latex}
  \usepackage{tcolorbox}
  \usepackage{amsmath, commath, bm}

  \newtcolorbox{info-box}{colback=cyan!5!white,arc=0pt,outer arc=0pt,colframe=cyan!60!black}
  \newtcolorbox{warning-box}{colback=orange!5!white,arc=0pt,outer arc=0pt,colframe=orange!80!black}
  \newtcolorbox{error-box}{colback=red!5!white,arc=0pt,outer arc=0pt,colframe=red!75!black}
  \setcounter{section}{-1}
  ```
pandoc-latex-environment:
tcolorbox: [box]
info-box: [info]
warning-box: [warning]
error-box: [error]
---
