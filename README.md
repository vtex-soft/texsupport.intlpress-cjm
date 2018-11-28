# LaTeX author support for the International Press journal *Cambridge Journal of Mathematics* (*CJM*)

## Table of Contents

* [About](#about)
* [Package content](#package-content)
* [Setup](#setup)
* [Options](#options)
* [Recomended usage of `ipart` package](#recomended-usage-of-ipart-package)
* [Submission](#submission)
* [Bug reports](#bug-reports)

## About

Author support service provides LaTeX style files and `*.tex` file templates designed for International Press journal
[Cambridge Journal of Mathematics (CJM)](http://www.intlpress.com/CJM/) articles.

## Package content

The following files are given in the repository (or directly in `*.zip` archive):

* `ipart.cls`, `imsart.sty` - LaTeX style files designed for International Press journal articles.
  Please do not change them. These files are already loaded in the respective template files;
* `imsart-number.bst`, `imsart-nameyear.bst` - suggested BibTeX[^1] related bibliography styles.
  If your bibliography is structured in BibTeX format, loading your `*.bib` file
  and one of provided BibTeX styles allows you to get the final format of the bibliography.
* `cjm-template.tex` - topmatter template (should be used for article preparation);
* `cjm-sample.tex` - journal sample article;
* `cjm-sample.pdf` - journal sample article (PDF file);

[^1]: The following link provides information about BibTeX usage: [http://www.bibtex.org/Using/](http://www.bibtex.org/Using/).

## Setup
* Clone the repository or download the `*.zip` archive. Rename the package to `<your-project-name>`.
* Install `ipart.cls`, `imsart.sty`, `imsart-number.bst`, `imsart-nameyear.bst` in your TeX system (suggested directory: `ipart`).
* Use the file `cjm-template.tex` to start your article as a template.
* Use the file `cjm-sample.tex` as a reference for how to prepare a topmatter of your article.

## Recommended usage of `ipart` package

Use `cjm-template.tex` as a template.

### Document class options

For the CJM journal `cjm` option must be set in a `\documentclass[]{ipart}`:
```latex
\documentclass[cjm]{ipart}
```

### LaTeX document preamble content

The preamble of your LaTeX document should look like this:

```latex
\documentclass[cjm]{ipart}

\arxiv{math.PR/0000000}

\begin{document}

    \begin{frontmatter}

        \title{A Sample Document\protect\thanksref{T1}}
        \thankstext{T1}{Footnote to the title with the `thankstext' command.}

        \begin{aug}
            \author{\fnms{First} \snm{Author}\thanksref{t2}\ead[label=e1]{first@somewhere.com}},
            \address{Address of the First Author\\
                     Country\\
                     \printead{e1}}
            \author{\fnms{Second} \snm{Author}\ead[label=e2]{second@somewhere.com}}
            \address{Address of the Second authors\\
                     Country\\
                     \printead{e2}}
            \and
            \author{\fnms{Third} \snm{Author}
                    \ead[label=e3]{third@somewhere.com}%
                    \ead[label=u1,url]{http://www.foo.com}}
            \address{Address of the Third author\\
                     Country\\
                     \printead{e3}\\
                     \printead{u1}}

            \thankstext{t2}{Footnote to the first author with the `thankstext' command.}
        \end{aug}

        \begin{abstract}
            ...
        \end{abstract}

        \begin{keyword}[class=AMS]  % please indicate appropriate AMS codes
            \kwd[Primary ]{00K00}
            \kwd{00K01}
            \kwd[; secondary ]{00K02}
        \end{keyword}

        \begin{keyword}
            \kwd{sample}
            \kwd{\LaTeX}
        \end{keyword}

        \tableofcontents

    \end{frontmatter}

    Your publication content

\end{document}
```

### Comments

* Labels **T1**, **t2** are used for thanks;
* Labels **e1**, **e2**, **e3**, **u1** are used to print electronic addresses.
If `hyperref` package is used, they will be made into hyperlinks;

## Submission

Submit one single file as a zip archive.
Pack your root folder `<your-project-name>` with files and subfolders.

## Bug reports

Please submit bug report or feature requests at
[github](https://github.com/vtex-soft/texsupport.intlpress-cjm/issues) page.