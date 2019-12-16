---
author: Guido Pleßmann
title: Introducing the RLI \LaTeX{} beamer theme
subtitle: ...finally overcoming MS Powerpoint
institute: Reiner Lemoine Institut
classoption: aspectratio=169
date: \today
theme: rli
urlcolor: rlilinkcolor
header-includes:
- |
  \newcommand{\tel}{+49 (0)30 1208 434 72}
  \newcommand{\email}{guido.plessmann@rl-institut.de}
  \newcommand{\twitter}{\href{https://twitter.com/gplssm}{@gplssm}}
  \newcommand{\finalstatement}{}
  \tikzset{
  invisible/.style={opacity=0},
  visible on/.style={alt={#1{}{invisible}}},
  alt/.code args={<#1>#2#3}{%
    \alt<#1>{\pgfkeysalso{#2}}{\pgfkeysalso{#3}} % \pgfkeysalso doesn't change the path
  },
  }
---

# Hands-on instructions

Install required software

```bash
sudo apt get install texlive
sudo apt install texlive-xetex
sudo apt install texlive-latex-recommended
```

`sudo apt get install texlive-fonts-extra` (maybe required for fonts)

Clone the theme repo

```
git clone git@github.com:rl-institut/beamer_theme.git
```

Checkout the slides' source file of this talk: <https://github.com/gplssm/slides_introducing_latex_beamer_theme/blob/master/20191216_introducing_latex_beamer_plessmann.tex>



# Agenda

>#. Why? And what is \LaTeX{} beamer?
>#. How to use the theme `rli`
>#. More examples
>#. Outlook and how to contribute

# What is \LaTeX{} beamer?

\center
\onslide<2>{\includegraphics[width=.6\paperwidth]{img/what_is_latex_beamer_answered_wolfram-alpha.png}}

# What is \LaTeX{} beamer?

\center
\includegraphics[height=.85\paperheight]{img/what_is_latex_beamer_answered_google.png}

# What is \LaTeX{} beamer?

- Document class for \LaTeX{}
- Styled by themes
- Common \LaTeX{} features


# What is a beamer theme?

Sets the appearance for the slides

- Header and footer
- Fonts and color
- Title page
- Other defaults

As example, the beamer the _Berlin_

\begin{figure}
\begin{minipage}{0.2\textwidth}
\centering
\includegraphics[height=2.5cm]{img/Berlin-default-default-01.png}%
\end{minipage}%
\begin{minipage}{0.2\textwidth}
\centering
\includegraphics[height=2.5cm]{img/Berlin-default-default-02.png}%
\end{minipage}%
\begin{minipage}{0.2\textwidth}
\centering
\includegraphics[height=2.5cm]{img/Berlin-default-default-12.png}%
\end{minipage}%
\begin{minipage}{0.2\textwidth}
\centering
\includegraphics[height=2.5cm]{img/Berlin-default-default-17.png}%
\end{minipage}%
\begin{minipage}{0.2\textwidth}
\centering
\includegraphics[height=2.5cm]{img/Berlin-default-default-18.png}%
\end{minipage}%
\end{figure}

# Why is \LaTeX{} beamer good?

#. Content is separated from layout
#. Good typesetting, good defaults, nice math rendering
#. Source files (`.tex` or `.md`) is a text file, versionable, and gitable
#. Persistent design
#. Reusability of slides
#. Collaborative slides creation via GitHub
#. Theme can be improved by time

# Why markdown (through pandoc) is better!

#. Less formatting code
#. Simpler than \LaTeX{}
#. Popular markup language (GitHub, Redmine, Wikis)
#. Native \LaTeX{} code is always possible

# A minimal \LaTeX{} presentation

```latex
\documentclass[aspectratio=169]{beamer}

\usetheme{rli}
\title{Title}

\begin{document}
\frame{\titlepage}
\end{document}
```

compiled by 

```bash
xelatex slides.tex
```

# A minimal markdown presentation

A `slides.md` file containing the front matter

```markdown
---
title: Title
classoption: aspectratio=169
theme: rli
---
```

compiled by 

```bash
pandoc -t beamer --pdf-engine=xelatex -o slides.pdf slides.md
```

# Both results in ...

\center
![](img/minimal_markdown_slides_titlepage.pdf){ width=90% }

# A more senseful front matter

```markdown
---
author: Author Name
title: Title
subtitle: Subtitle
institute: Reiner Lemoine Institut
classoption: aspectratio=169
date: \today
theme: rli
urlcolor: rlilinkcolor
---
```


# Slide examples

See the [example slides]() in the theme repository: ...


# Useful links

- Example slides:
  - Markdown: <https://github.com/rl-institut/beamer_theme/blob/master/example-slides.md>
  - Latex: <https://github.com/rl-institut/beamer_theme/blob/master/example-slides.tex>
- PDF version of example slides: ...
- Rocket Chat channel: ...

# Things to work on

#. Consisten font colors
#. Fail-safe build of lastslide (and more improvements)
#. Simplified replacement of title graphic
#. Option to integrate partner logos
#. Distribution of theme style files (`*.sty` and `img/`)

Most urgent fix requests are here: <https://github.com/rl-institut/beamer_theme/milestone/2>

Please file issues there.

# How to contribute

- Highly welcome!
- Diverse tasks: readme/user guide, fixes, new features, code quality improvements, example slides 
- Workflow: <https://github.com/rl-institut/beamer_theme/blob/master/CONTRIBUTING.md>
- At least: please submit issues ;-)

# {.plain}

\insertendpagecontent