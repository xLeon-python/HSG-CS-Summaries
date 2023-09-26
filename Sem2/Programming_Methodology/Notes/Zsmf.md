---
title: Programming Methodology
author: Leon Muscat
keywords: [CS]
subtitle: The fundamental principles and concepts of object‑oriented programming.
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

# Introduction

In this course, students will learn about the fundamental principles and concepts of object‑oriented programming (with Java).

## Learning Goals

Students of this course should be able to...

* Understand the abstractions of object‑oriented programming languages
* Differentiate among various abstractions (e.g., classes, interfaces, abstract classes, methods) and choose them appropriately
* Write programs using object‑oriented design principles and best practices, such as encapsulation and code reuse
* Identify and use the syntax and semantics of basic and advanced constructs in the Java programming language
* Master advanced programming concepts such as concurrent programming, generic programming, metaprogramming and reflection, network programming.

## Exam

### Group Project

A group programming project makes up 20% of the final grade. The specification of the project will be released incrementally over the semester. The groups should be made up of 3 students, but each student has to fully understand all of the project, as students are evaluated individually. 

Every student has to write a project report with 3000 words max. The report should cover the program design, a critical discussion of the implementation and its limitations, an evaluation of the group's progress and a statement of the personal contribution to the group project.

After the project has been handed it, each group has to give a 20 minute code presentation with a live demo. The presentation should cover the ideas and design decisions, the structure of the code, the limitations of the solution and how the workload was shared among the group members. As all group members are assessed individually, the time should be split equal among group members. No slides are required, as long as the code and documentation is structured. 

### Final Exam

The central final exam makes up 80% of the grade. The only permitted aid is a TI-30 series calculator.

## Literature

"Starting Out with Java: From Control Structures through Objects", 7th Edition, Tony Gaddis, 2020, Pearson.

"Java: An Introduction to Problem Solving and Programming", 8th Edition, Walter Savitch, San Diego, 2018, Pearson.

"Java Concurrency in Practice", Brian Goetz, 2006, Addison‑Wesley Professional.

# Java Basics

A basic Java guide can be found [here](https://www.edureka.co/blog/cheatsheets/java-cheat-sheet/). The PDF is included below (see figure \ref{java-cheatsheet}).

![Java Basics Cheat Sheet \label{java-cheatsheet}](./images/Java-CheatSheet_Edureka.pdf)
