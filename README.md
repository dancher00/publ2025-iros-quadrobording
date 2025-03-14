# LaTeX Setup Guide for VS Code

## Prerequisites
1. Install [VS Code](https://code.visualstudio.com/)
2. Install [LaTeX](https://marketplace.cursorapi.com/items?itemName=mathematic.vscode-latex) extension
3.  Install [LaTeX Workshop](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop) extension
4. Install a TeX distribution:
   - Windows: [MiKTeX](https://miktex.org/download)
   - macOS: [MacTeX](https://www.tug.org/mactex/)
   - Linux: `sudo apt-get install texlive-full`

## VS Code Configuration

1. Open VS Code Settings (JSON):
   - Press `Ctrl + Shift + P` (Windows/Linux) or `Cmd + Shift + P` (macOS)
   - Type "settings json" and select "Preferences: Open Settings (JSON)"

2. Add the following configuration:

``` json
"latex-workshop.latex.tools": [
    {
        "name": "pdflatex",
        "command": "pdflatex",
        "args": [
            "-synctex=1",
            "-interaction=nonstopmode",
            "-file-line-error",
            "%DOC%"
        ]
    },
    {
        "name": "bibtex",
        "command": "bibtex",
        "args": [
            "%DOCFILE%"
        ]
    }
],
"latex-workshop.latex.recipes": [
    {
        "name": "pdflatex -> bibtex -> pdflatex*2",
        "tools": [
            "pdflatex",
            "bibtex",
            "pdflatex",
            "pdflatex"
        ]
    }
]
```

for autoclean use add this command in your vscode settings json:

```json
"latex-workshop.latex.autoClean.run": "onBuilt",
"latex-workshop.latex.clean.fileTypes": [
    "*.aux",
    "*.bbl",
    "*.blg",
    "*.idx",
    "*.ind",
    "*.lof",
    "*.lot",
    "*.out",
    "*.toc",
    "*.acn",
    "*.acr",
    "*.alg",
    "*.glg",
    "*.glo",
    "*.gls",
    "*.ist",
    "*.fls",
    "*.log",
    "*.fdb_latexmk",
    "*.snm",
    "*.synctex(busy)",
    "*.synctex.gz(busy)",
    "*.nav",
    "*.vrb",
    "*.run.xml",
    "*.bcf",
    "_minted*",
    "*.pyg",
    "*.gz"
],
"latex-workshop.latex.clean.subfolder.enabled": true,
"latex-workshop.latex.clean.method": "glob"
```


# Original README

April 2, 2003


IEEEtran.bst is the official BibTeX style for authors of the Institute of
Electrical and Electronics Engineers (IEEE) Transactions journals and
conferences. It also may have applications in other academic work such as
theses and technical reports.

IEEEtran.bst is a very comprehensive BibTeX style which provides many
features beyond the standard BibTeX styles - including full support
for references of online documents, patents, periodicals and standards.
See the provided user manual for detailed usage information.


 Enjoy!

Michael Shell
mshell@ece.gatech.edu

*******
Version 1.11 (2003/04/02) changes:

 1) Corrected problem with underscores in URLs when using url.sty.

No changes needed in the documentation.

Minor updates have been made to the IEEEfull.bib and IEEEabrv.bib 
string definitions. 



********************* Files **********************

README                 - This file.

IEEEtran.bst           - The IEEE BibTeX style file.

IEEEtranS.bst          - A version of IEEEtran.bst that sorts the
                         entries. May be of interest for (non-IEEE) work
                         such as theses. (Do not use for IEEE work.)

IEEEtran_bst_HOWTO.pdf - The user manual.

IEEEexample.bib        - An example BibTeX database that contains the
                         references shown in the user manual.

IEEEabrv.bib           - String definitions for the abbreviated names of
                         IEEE journals. (For use with IEEE work.)
                         
IEEEfull.bib           - String definitions for the full names of
                         IEEE journals. (Do not use for IEEE work.)

IEEEbcpat.bib          - Obsolete string definitions provided by older
                         versions of IEEE BibTeX .bst files. (Do not
                         use for IEEE work.)




**********************************************************************
 Legal Notice:
 This code and advice is offered as-is without any warranty either
 expressed or implied; without even the implied warranty of
 MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE!
 User assumes all risk.
 In no event shall IEEE or any contributor to this code
 be liable for any damages or losses, including, but not limited to,
 incidental, consequential, or any other damages, resulting from the
 use or misuse of any information contained here.
 
 All statements made here are the opinions of their respective
 authors and are not necessarily endorsed by the IEEE.

 This code/text is distributed under the Perl Artistic License 
 ( http://language.perl.com/misc/Artistic.html ) 
 and may be freely used, distributed and modified.
 Retain all contribution notices and credits.
**********************************************************************
