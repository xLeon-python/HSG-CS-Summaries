---
title: Statistics for Data Science
author: Leon Muscat
keywords: [CS, Statistics, Data Science]
subtitle: A random variable is neither random nor variable.
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

# Exercices

## Week1

### Problem 1

For any continious function (continious at $x$) $f(x)$, we have $\lim_{x -> c} f(x) = f(\lim_{x->c} x)$. This means, we can let $x$ go to infinity within $f(x)$.

For instance,
$$\lim_{x->\infty} \ln (\frac{e^x - e^{-x}}{e^{-x} - e^x} + 2)$$
becomes
$$\ln (\frac{-1}{1} + 2) = 0$$

### Problem 2

Let $A \in \Omega$, then $A \subseteq \Omega$ and $A^c \subseteq \Omega$. This means that if $A \in 2^{\Omega}$, then $A^c \in 2^{\Omega}$. This, the **power set is closed under complements**.

Consider a finite number of elements of the power set: $A_1, A_2, \dots A_n \in 2^{\Omega}$. Then, $A_i \subseteq \Omega$ for all $i=1, \dots, n$. Furthermore, $\cup_{i=1}^n A_i \subseteq \Omega$. This means  $\cup_{i=1}^n A_i \in 2^{\Omega}$. So the power set is **closed under finite unions**.
Lastly, $\emptyset \in 2^{\Omega}$, thus wer have a $\sigma$-Algebra. \square 
