# utbm-latex-internship-report-covers

A LaTeX version of the UTBM internship report covers using TikZ.

You can compare [the original version](original-version.doc) and [the LaTeX version](latex-version.pdf).

# Warning

The LaTeX implementation I made is free but the covers belongs to the UTBM and can only be used with their authorization!

**UTBM and all UTBM-related trademarks and logos are trademarks or registered trademarks of University of Technology of Belfort-Montbéliard in France, other countries, or both.**

# Requirements

The package require the Tahoma font as the original covers use it.

To load the Tahoma font, the fontspec package is used which means the document must be compiled with *xelatex* or *lualatex* (at the moment not lualatex because of a [pgf bug](https://sourceforge.net/p/pgf/bugs/384/)).

# Installation

## Install the package

Copy the directory [utbmcovers](utbmcovers) inside one of your **texmf** directory: to follow the TDS (TeX Directory Structure), copy it in ``<texmf_folder>/tex/latex/``.

Your **texmf** directory is usually ``$HOME/texmf`` on Unix operating systems.

On Windows with MiKTeX you can find it in MiKTeX's options:
- Start menu -> MiKTeX -> MiKTeX settings
- The options window should open
- Go in the *Roots* panel
- Check *Show MiKTeX-maintained root directories*
- Take the path with the description: "CommonData, CommonConfig" (It is usually ``C:\ProgramData\MiKTeX\<version>``) or add the path you want

## Refresh the LaTeX databases

On Unix operating systems, in root:
```
$> mktexlsr
$> update-updmap --quiet
```

On Windows with MiKTeX
- Start menu -> MiKTeX -> MiKTeX settings
- Click *Refresh FNDB*
- Click *Update Formats*

# Usage

Include the package:
```latex
\usepackage{utbmcovers}
```
Configure the displayed information:
```
\setutbmfrontillustration{Illustration_file}
\setutbmtitle{Title}
\setutbmsubtitle{Subtitle}
...
```
Use ``\makeutbmfrontcover{}`` to print the front cover and ``\makeutbmbackcover{}`` to print the back cover.

See [latex-version.tex](latex-version.tex) for a complete example.

# Usage with upmethodology

The **tex-upmethodology** collection of packages available on [arakhne.org](http://www.arakhne.org/tex-upmethodology) and on [CTAN](https://www.ctan.org/pkg/upmethodology).

An upmethodology extension is included with the package, in your ``.tex`` document using the document class **upmethodology-document** put:
```latex
\UseExtension{utbmcovers}
```
before using the *utbmcovers* configuration functions.

See [latex-upmethodology-version.tex](latex-upmethodology-version.tex) for a complete example.

# Other resources

[utbm-beamer-theme](https://github.com/pinam45/utbm-beamer-theme): A LaTeX beamer version of the UTBM presentation theme using TikZ.
