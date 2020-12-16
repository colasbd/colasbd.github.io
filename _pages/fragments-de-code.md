---
layout: myBasicLayout
#layout: splash
classes: wide

header:
  show_overlay_excerpt: false
  overlay_image: /assets/images/backgrounds/header_12.jpg
  #overlay_image: /assets/images/milky-way.jpg
  #caption: "" #Voie lactée"
  #overlay_filter: rgba(1, 17, 47, 0.2)
  #overlay_color: "#907ab3"

author_profile: no
permalink: /fragments-de-code/
title: "Fragments de code"
---

*Voici quelques fragments de code qui pourront être utiles.*


## Une suite récurrente

![image-title-here](dessin_suite_recurrente_1.pdf){:class="img-responsive" width="80%"}


```
\documentclass[tikz]{standalone}

\usepackage{mathrsfs}
\usepackage{amssymb}
\usepackage{tkz-fct}
\usetikzlibrary{math}
\usetikzlibrary{calc}

\begin{document}

\begin{tikzpicture}[scale=3]
\tkzInit[xmin=-1.25,xmax=3,ymax=2]

\draw[->, ] (-1.25,0) -- (3,0) node[above left]{$x$} node[below left]{$I$};
\draw[->, ] (0,-0.25) -- (0,2.25) node[below right]{$y$} node[below left]{$\mathbb{R}$};
    
\tkzFct[ultra thick, color=blue!50!black, samples=1000]{sqrt(\x+1)}
\tkzFct[samples=2, color=black, thick]{x}
\node[above] at (2,2) {$y=x$};
\node[above,color=blue!50!black] at (3,2) {$\mathscr{C}_f$};

\tikzmath{
function f(\u) {
	return sqrt(1+\u);
	};
real \u0, \u1, \u2, \u3, \u4;
\u0=-.5;
\u1=f(\u0);
\u2=f(\u1);
\u3=f(\u2);
\u4=f(\u3);
}
\newcount\j
\foreach \i in {0}{
	\pgfmathsetcount{\j}{\i+1}
	\draw[dashed,line width=.2pt] (\u\i,0) node[below] {$u_\i$} -- (\u\i,{f(\u\i)}) -- (0,{f(\u\i)}) node[above left]
 {$u_{\the\j}$};
 }
\foreach \i in {1,2,3}{
	\pgfmathsetcount{\j}{\i+1}
	\draw[dashed,line width=.2pt] (\u\i,0) node[below] {$u_\i$} -- (\u\i,{f(\u\i)}) -- (0,{f(\u\i)}) node[left]
 {$u_{\the\j}$};
}

\draw[ultra thick, blue!60] 
(\u0,0) -- (\u0,\u1) 
-- (\u1,\u1) -- (\u1,\u2) 
-- (\u2,\u2) -- (\u2,\u3)  
-- (\u3,\u3) -- (\u3,\u4)  
-- (\u4,\u4);
\end{tikzpicture}

\end{document}
```




## Une autre suite récurrente

![image-title-here](dessin_suite_recurrente_2.pdf){:class="img-responsive" width="80%"}


```
\documentclass[tikz]{standalone}

\usepackage{mathrsfs}
\usepackage{amssymb}
\usepackage{tkz-fct}

\usetikzlibrary{math}
\usetikzlibrary{calc}

\begin{document}
\begin{tikzpicture}[scale=3]
\tkzInit[xmin=-0.5,xmax=2.75,ymax=2]

\draw[->, ] (-0.75,0) -- (3,0) node[above]{$x$} node[below left]{$I$};
\draw[->, ] (0,-0.5) -- (0,2.25) node[right]{$y$} node[below left]{$\mathbb{R}$};
    
\tkzFct[ultra thick, color=blue!50!black, samples=1000]{1/((\x+1)*(\x+1))}
\tkzFct[samples=2, color=black, thick]{x}
\node[above] at (2,2) {$y=x$};
\node[above,color=blue!50!black] at (2.5,0.15) {$\mathscr{C}_f$};

\tikzmath{
function f(\u) {
	return 1/((\u+1)*(\u+1));
	};
real \u0, \u1, \u2, \u3, \u4;
\u0=-.25;
\u1=f(\u0);
\u2=f(\u1);
\u3=f(\u2);
\u4=f(\u3);
\u5=f(\u4);
\u6=f(\u5);
}
\newcount\j
\foreach \i in {0}{
	\pgfmathsetcount{\j}{\i+1}
	\draw[dashed,line width=.2pt] (\u\i,0) node[below] {$u_\i$} -- (\u\i,{f(\u\i)}) -- (0,{f(\u\i)}) 
	node[above left] {$u_{\the\j}$};
}

\foreach \i in {1,2,3,4,5}{
	\pgfmathsetcount{\j}{\i+1}
	\draw[dashed,line width=.2pt] (\u\i,0) node[below] {$u_\i$} -- (\u\i,{f(\u\i)}) -- (0,{f(\u\i)}) 
	node[left] {$u_{\the\j}$};
}

\draw[ultra thick, blue!60] 
(\u0,0) -- (\u0,\u1)
-- (\u1,\u1) -- (\u1,\u2) 
-- (\u2,\u2) -- (\u2,\u3) 
-- (\u3,\u3) -- (\u3,\u4)
-- (\u4,\u4) -- (\u4,\u5)
-- (\u5,\u5) -- (\u5,\u6)
-- (\u6,\u6) ;
\end{tikzpicture}

\end{document}
```