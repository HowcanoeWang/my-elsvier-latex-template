# Elsevier LaTeX Template Notes

## Submission file layout

Elsevier Editorial Manager does not accept submissions with nested subfolders. Figures, tables, bibliography files, and style files should all stay in the same directory.

## Document class and package setup

The default template uses the `elsarticle` document class in `preprint` mode with Harvard-style citations. If you need review spacing, or a specific journal layout such as `1p`, `3p`, or `5p`, change the options in the `\documentclass` line instead of adding extra template comments back into `main.tex`.

```latex
\documentclass[preprint,12pt,authoryear]{elsarticle}

\usepackage{amssymb}
\usepackage{amsmath}
\usepackage{lineno}
\usepackage{natbib}
\usepackage{graphicx}
\usepackage{mathptmx}
\usepackage[breaklinks]{hyperref}
\usepackage[hyphenbreaks]{breakurl}
\usepackage{setspace}
\usepackage{indentfirst}

\journal{Artificial Intelligence in Agriculture}
```

Common document class variants:

```latex
\documentclass[authoryear,preprint,review,12pt]{elsarticle}
\documentclass[final,1p,times,authoryear]{elsarticle}
\documentclass[final,1p,times,twocolumn,authoryear]{elsarticle}
\documentclass[final,3p,times,authoryear]{elsarticle}
\documentclass[final,3p,times,twocolumn,authoryear]{elsarticle}
\documentclass[final,5p,times,authoryear]{elsarticle}
\documentclass[final,5p,times,twocolumn,authoryear]{elsarticle}
```

## Front matter structure

`frontmatter` is where title, author information, affiliations, abstract, graphical abstract, highlights, and keywords are defined. If you need corresponding-author notes, author footnotes, title notes, or author-homepage links, use commands such as `\corref`, `\cortext`, `\fnref`, `\fntext`, `\tnoteref`, `\tnotetext`, `\ead`, and `\ead[url]` inside this block.

For multiple affiliations, assign labels in `\author[...]` and `\affiliation[...]` so authors can be linked explicitly to institutions. Add the paper title immediately after `\begin{frontmatter}` with `\title{Your Paper Title}`.

```latex
\begin{frontmatter}

\title{Your Paper Title}

\author[1]{Author One\corref{cor1}}
\author[1]{Author Two}
\cortext[cor1]{Corresponding author}
\ead{name@example.com}

\affiliation[1]{organization={Institution Name},
            addressline={Street Address},
            city={City},
            postcode={Postcode},
            state={State},
            country={Country}}

\begin{abstract}
Abstract text.
\end{abstract}

\begin{graphicalabstract}
% \includegraphics{grabs}
\end{graphicalabstract}

\begin{highlights}
\item Research highlight 1
\item Research highlight 2
\end{highlights}

\begin{keyword}
keyword1 \sep keyword2 \sep keyword3
\end{keyword}

\end{frontmatter}
```

Keywords should be separated with `\sep`. If the target journal requires PACS or MSC classification, add them in the same block using the journal's requested format.

## Line numbers and spacing

Line numbers are typically enabled for review submissions. Double spacing can be turned on when required by the journal or supervisor.

```latex
\linenumbers
% \doublespacing
```

## Sectioning and cross-references

Use `\section`, `\subsection`, and `\subsubsection` for normal structure, and pair them with `\label` plus `\ref` for cross-references.

```latex
\section{Example Section}
\label{sec1}

Section text. See Subsection \ref{subsec1}.

\subsection{Example Subsection}
\label{subsec1}

Subsection text.
```

## Mathematics

The template already loads `amsmath`, so you can use inline math, numbered equations, unnumbered equations, and aligned multi-line formulas directly.

```latex
This is an example for the symbol $\alpha$.

\begin{equation}
f(x) = (x+a)(x+b)
\end{equation}

\begin{equation*}
f(x) = (x+a)(x+b)
\end{equation*}

\begin{align}
f(x) &= (x+a)(x+b) \\
     &= x^2 + (a+b)x + ab
\end{align}
```

## Tables and figures

Use `table` with `tabular` for structured data and `figure` with `\includegraphics` for images. Keep figure files in the same directory as the main source when preparing a submission package.

```latex
\begin{table}[t]
\centering
\begin{tabular}{l c r}
1 & 2 & 3 \\
4 & 5 & 6 \\
7 & 8 & 9 \\
\end{tabular}
\caption{Table Caption}
\label{tab:1}
\end{table}
```

```latex
\begin{figure}[t]
\centering
\includegraphics{your-figure-filename}
\caption{Figure Caption}
\label{fig:1}
\end{figure}
```

## Citations and bibliography

The template uses `natbib`, so `\citet{...}` produces textual citations and `\citep{...}` produces parenthetical citations. Bibliography data should live in `references.bib`, and the `.bst` file in this repository is already configured for Elsevier Harvard style.

```latex
Example citation: \citet{author2022}, \citep{author2022}.

\bibliographystyle{elsarticle-harv}
\bibliography{references}
```

## Appendix

Appendices start after `\appendix`, and then continue with normal section commands.

```latex
\appendix
\section{Example Appendix}
\label{app:1}

Appendix text.
```
