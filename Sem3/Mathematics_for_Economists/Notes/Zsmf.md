---
title: Mathematics for Economists
author: Leon Muscat
keywords: [CS, Analysis, Statistics]
subtitle: To introduce mathematical and statistical concepts and tools used in economics and finance.
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
  \usepackage{stmaryrd}
  \usepackage{polynom}
  \usepackage{tikz}
  \usepackage{forest}
  \usetikzlibrary{shapes,backgrounds,angles}
  \tikzset{vector/.style = {ultra thick, ->, >=stealth, cap=round},}
  \usepackage{unicode-math}
  \setmathfont{latinmodern-math.otf} % default
  \setmathfont[range=\setminus]{Asana-Math.otf}

  \newtcolorbox{info-box}{colback=cyan!5!white,arc=0pt,outer arc=0pt,colframe=cyan!60!black}
  \newtcolorbox{warning-box}{colback=orange!5!white,arc=0pt,outer arc=0pt,colframe=orange!80!black}
  \newtcolorbox{error-box}{colback=red!5!white,arc=0pt,outer arc=0pt,colframe=red!75!black}
  \setcounter{section}{-1}
  \newcommand\N{\ensuremath{\mathbb{N}}}
  \newcommand\Z{\ensuremath{\mathbb{Z}}}
  \newcommand\Q{\ensuremath{\mathbb{Q}}}
  \newcommand\R{\ensuremath{\mathbb{R}}}
  \newcommand\C{\ensuremath{\mathbb{C}}}
  \newcommand\K{\ensuremath{\mathbb{K}}}
  \newcommand\F{\ensuremath{\mathbb{F}}}

  % --- Normal colors ---
  \definecolor{xred}{HTML}{BD4242}
  \definecolor{xblue}{HTML}{4268BD}
  \definecolor{xgreen}{HTML}{52B256}
  \definecolor{xpurple}{HTML}{7F52B2}
  \definecolor{xorange}{HTML}{FD9337}
  \definecolor{xdotted}{HTML}{999999}
  \definecolor{xgray}{HTML}{777777}
  \definecolor{xcyan}{HTML}{80F5DC}
  \definecolor{xpink}{HTML}{F690EA}
  \definecolor{xgrayblue}{HTML}{49B095}
  \definecolor{xgraycyan}{HTML}{5AA1B9}

  % --- Dark colors ---
  \colorlet{xdarkred}{red!85!black}
  \colorlet{xdarkblue}{xblue!85!black}
  \colorlet{xdarkgreen}{xgreen!85!black}
  \colorlet{xdarkpurple}{xpurple!85!black}
  \colorlet{xdarkorange}{xorange!85!black}
  \colorlet{xdarkcyan}{xcyan!85!black}
  ```
pandoc-latex-environment:
tcolorbox: [box]
info-box: [info]
warning-box: [warning]
error-box: [error]
---

# Taylor Polynomials

## 

# Complex Numbers

The real numbers include all numbers one can imagine except for $\sqrt{-1}$. Therefore, the imaginary number $i$ is introduced, which is defined as $i^2 = -1$.

Set of complex numbers: $\mathbb{C} = \{x + iy | x,y \in \mathbb{R}\}$. The term $x$ is called the real part (Re$(z) = x$) and $y$ the imaginary part (Im$(z) = y$) of the complex number $z = x + i y$. A complex number can be illustrated in the Gaussian plane:
$$
\begin{tikzpicture}
  \draw [->] (-3,0) -- (3,0) node [right] {Real Axis};
  \draw [->] (0,-3) -- (0,3) node [above] {Imaginary Axis};
  \node [black] at (1,0) [below] {$1$};
  \node [black] at (2,0) [below] {$2$};
  \node [black] at (-1,0) [below] {$-1$};
  \node [black] at (-2,0) [below] {$-2$};
  \node [black] at (0,1) [left] {$i$};
  \node [black] at (0,2) [left] {$2i$};
  \node [black] at (0,-1) [left] {$-i$};
  \node [black] at (0,-2) [left] {$-2i$};
  \draw [->, xblue, line width=0.5mm] (0,0) -- (1.5,0) node [above right] {$x$};
  \draw [->, xred, line width=0.5mm] (0,0) -- (0,1.5) node [above right] {$x * i$};
  \draw [->, xgreen, line width=0.5mm] (0,0) -- (-1.5,0) node [above] {$x * (-1)$};
\end{tikzpicture}
$$

Every complex number $z$ has a conjugate complex number $$\overline{z} = z^* = x - i y$$ The real and imaginary parts can therefore be written as $$\text{Re}(z) = \frac{z + \overline{z}}{2}, \quad \text{Im}(z) = \frac{z - \overline{z}}{2 i}$$ The magnitude of a complex number is $$|z| = \sqrt{z\overline{z}} = \sqrt{x^2 + y^2}$$ This can be explained by the Gaussian plane. A vector $z$ forms a triangle with its real and imaginary parts. The length can then be calculated using the Pythagorean theorem:
$$
\begin{tikzpicture}
  \draw [->] (-2,0) -- (2,0) node [right] {Real Axis};
  \draw [->] (0,-2) -- (0,2) node [above] {Imaginary Axis};
  \draw [vector, blue, line width=0.5mm] (0,0) -- (1.5,1) node [above right] {$z$};
  \draw [black, line width=0.3mm] (1.5,0) -- (1.5,1) node [below right] {Im$(z)$};
  \draw [black, line width=0.3mm] (0,0) -- (1.5,0) node [below left] {$Re(z)$};
\end{tikzpicture}
$$
$$
r = \sqrt{\text{Im}(z)^2 + \text{Re}(z)^2}  
$$

## Euler Form

Complex numbers can also be represented in polar or Euler form:
$$
\begin{tikzpicture}[scale=2.0]
  		\def\xmax{2.0}
		\def\ymax{1.6}
		\def\R{1.9}
		\def\ang{35}
		\coordinate (O) at (0,0);
		\coordinate (R) at (\ang:\R);
		\coordinate (-R) at (-\ang:\R);
		\coordinate (X) at ({\R*cos(\ang)},0);
		\coordinate (Y) at (0,{\R*sin(\ang)});
		\coordinate (-Y) at (0,{-\R*sin(\ang)});
		\node[fill=xdarkblue,circle,inner sep=0.8] (R') at (R) {};
		\node[xdarkblue,right=0.2] at (R') {$z=x+iy=re^{i\theta}$};
		\draw[dashed,xdarkblue]
		(Y) -- (R') --++ (0,{0.1-\R*sin(\ang)});
		\draw[->,line width=0.9] (-0.65*\xmax,0) -- (\xmax+0.05,0) node[right] {Re};
		\draw[->,line width=0.9] (0,-\ymax) -- (0,\ymax+0.05) node[left] {Im};
		\draw[vector] (O) -- (R') node[pos=0.55, above, rotate=\ang, scale=0.8] {$r = \sqrt{x^2 + y^2}$};
		% \draw pic[->,"$\theta$",xdarkblue,draw=xdarkblue,angle radius=23,angle eccentricity=1.24]
  {angle = X--O--R};
\end{tikzpicture}
$$
$$\theta = \begin{cases}\arccos(\frac{x}{r}) & \text{if } y \geq 0 \\ -\arccos(\frac{x}{r}) & \text{if } y < 0\end{cases}$$

$r e^{i\theta}$ is the representation of $z$ in polar form. The angle $\theta$ is called the argument and indicates the direction of the complex number. The real number $r$ indicates the length of the complex number.

The following rules apply for the polar form of a complex number:

1. $z_1 z_2 = (r_1 r_2) e^{i (\theta_1 + \theta_2)}$
2. $z^n = r^n e^{i n \theta} = r^n (\cos(n \theta) + i \sin(n \theta))$

## Root of a Complex Number

Calculating the solutions of $\sqrt{4}$ results in two solutions $x_1 = 2, x_2 = -2$. In the same sense, there are several solutions when extracting the root of a complex number $w^n = z$. The following formula applies:
$$w_k = \sqrt[^n]{r_z} e^{i (\frac{\theta z}{n} + 2\pi \frac{k}{n})} \quad (k=0,1,\dots,n-1)$$
k goes through all the whole numbers from 0 to $n-1$, after which the solutions repeat. In total, there are $n$ solutions. If $z=1$, the $n$ solutions of the equation $w^n = 1$ are called the $n$th roots of unity.

## Complex Logarithm

The complex logarithm is the inverse function to the exponentiation in the complex numbers. The complex logarithm $\text{Ln}$ of a complex number $z = x + i y$ is defined as:
$$\text{Ln}(z) = \text{ln}(|z|) + i \, \text{arg}(z)$$

## De Moivre's Theorem

This theorem, named after Abraham de Moivre, is particularly important for calculating powers of complex numbers. It states that for every real number $n$ and every complex number $z$ in the form $z = r (\cos \theta + i \sin \theta)$, the following applies:
$$z^n = r^n (\cos (n \theta) + i \sin (n \theta))$$

This equation is particularly important when calculating the $n$th root of a complex number, as it can be used to calculate the individual solutions.

## Complex Exponentials

For any complex number $z = a + b i$, the complex exponential $e^z$ is the limit of the infinite series
$$e^z = 1 + \frac{1}{1!} z^1 + \frac{1}{2!} z^2 + \dots$$

This can also be written as $exp(z) = \sum_{n=0}^{\infty} \frac{z^n}{n!}$.

### Euler's identity

If $z$ is imaginery, then we get 

$$
\begin{equation}
e^z &= 1 + $\frac{1}{1!}  i b^1 + \frac{1}{2!} i b^2 + \dots
&= 1 + i b - \frac{b^2}{2!} - i \frac{b^3}{3!} + \frac{b^4}{4!} + i \frac{b^5}{5!} - \dots
&= (1 - \frac{b^2}{2!} + \frac{b^4}{4!} - \dots) + i (b - \frac{b^3}{3!} + \frac{b^5}{5!} - \dots)
&= cos(b) + i sin(b)
\end{equation}
$$

In particular, taking $b = \pi$, then $e^{i \pi} = cos(\pi) + i \sin(\pi) = -1$. 

We can also infer the following:
$$e^{a + b i} = e^a e^{b i} = e^a (cos(b) + i sin(b)).$$

## Application of complex numbers

Solving a second-order linear difference equations $x_n+a_1 x_{n-1}+a_2 x_{n-2}=0$.

In general, we have the solution
$$
x_n=c \lambda_1^n+d \lambda_2^n,
$$
where $c, d \in \mathbb{R}$ are chosen based on the two initial conditions on $x_0$ and $x_1$, and
$$
\lambda_{1,2}=\frac{-a_1 \pm \sqrt{a_1^2-4 a_2}}{2}
$$
are the characteristic roots or eigenvalues which solve the quadratic equation
$$
\lambda^2+a_1 \lambda+a_2=0 .
$$
If $a_1^2<4 a_2$, the characteristic roots are conjugate complex numbers
$$
\lambda_{1,2}=\mathrm{h} \pm \mathrm{i} v
$$
for some $h, v \in \mathbb{R}$, where
$$
\mathrm{h}=-\frac{\mathrm{a}_1}{2} \quad \text { and } \quad v=\frac{\sqrt{4 \mathrm{a}_2-\mathrm{a}_1^2}}{2} .
$$
The solution therefore becomes
$$
x_n=c(h+i v)^n+d(h-i v)^n.
$$

We can calculate the polar form of the solution $x_n=c(h+i v)^n+d(h-i v)^n$:

Using De Moivre's Theorem, we get
$$
\left(\lambda_{1,2}\right)^n=(h \pm v i)^n=r^n(\cos n \theta \pm i \sin n \theta),
$$
where
$$
r=\sqrt{h^2+v^2}=\frac{\sqrt{a_1^2+4 a_2-a_1^2}}{2}=\sqrt{a_2}
$$
and $\theta \in[0,2 \pi)$ satisfies
$$
\cos \theta=\frac{h}{r}=-\frac{a_1}{2 \sqrt{a_2}} \quad \text { and } \quad \sin \theta=\frac{v}{r}=\sqrt{1-\frac{a_1^2}{4 a_2}} .
$$
The solution can then be transformed as follows:
$$
\begin{aligned}
x_n & =\operatorname{cr}^n(\cos n \theta+i \sin n \theta)+d r^n(\cos n \theta-i \sin n \theta) \\
& =r^n[(c+d) \cos n \theta+(c-d) i \sin n \theta] \\
& =r^n e \cos n \theta+f \sin n \theta
\end{aligned}
$$
where we set $e=c+d$ and $f=i(c-d)$ for shorthand.

