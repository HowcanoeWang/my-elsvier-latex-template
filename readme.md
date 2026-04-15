
## Can I using subfolders?
LaTeX submissions containing subfolders cannot be processed by EM. All submission files – including figures, tables, and style and bibliographic files – must be stored at the same folder level.

## Template modules

### 1. 基础文档类和常用包

```latex
%% 文档类（用于 Elsevier）
\documentclass[preprint,12pt,authoryear]{elsarticle}

%% 期刊名称（可选）
\journal{Artificial Intelligence in Agriculture}

%% 常用包
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
```

模板中的说明：



### 2. 前言（frontmatter）结构

```latex
%% 前言部分（标题、作者、单位、摘要等）
\begin{frontmatter}

\title{Your Paper Title}

\author[1]{Haozhou Wang\corref{cor1}}
\author[1]{Wei Guo}
\cortext[cor1]{Corresponding author}
\ead{haozhou-wang@g.ecc.u-tokyo.ac.jp}

\affiliation[1]{organization={Graduate School of Agricultural and Life Sciences, The University of Tokyo},
            addressline={1-1-1 Midori-cho},
            city={Nishi-Tokyo},
            postcode={188-0002},
            state={Tokyo},
            country={Japan}}

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

说明：

> keywords here, in the form: keyword \sep keyword
> 
> PACS codes here, in the form: \PACS code \sep code
> 
> MSC codes here, in the form: \MSC code \sep code
or \MSC[2008] code \sep code (2000 is the default)

### 4. 行号与双倍行距

```latex
%% 行号（用于审稿）
\linenumbers

%% 双倍行距（可选）
\doublespacing
```

### 5. 数学与公式示例

```latex
%% 行内数学
This is an example for the symbol $\alpha$.

%% 单行公式
\begin{equation}
f(x) = (x+a)(x+b)
\label{eq:1}
\end{equation}

%% 多行对齐公式
\begin{align}
f(x) &= (x+a)(x+b) \\
     &= x^2 + (a+b)x + ab
\label{eq:2}
\end{align}
```

### 6. 表格与图表模板

表格

```latex
\begin{table}[htbp]
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

图表

```
\begin{figure}[htbp]
\centering
\includegraphics{your-figure-filename}
\caption{Figure Caption}
\label{fig:1}
\end{figure}
```

### 7. 引用与参考文献

```latex
%% natbib 风格引用
Example citation: \citet{author2022}, \citep{author2022}.

%% 参考文献样式和数据库
\bibliographystyle{elsarticle-harv}
\bibliography{references}   % references.bib in BibTex format
```

### 8. 附录（可选）

```latex
\appendix
\section{Example Appendix}
\label{app:1}

Appendix text.
```