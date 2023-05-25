# LaTex_VSCode_EndNote
**A guide for setting up LaTex on VS Code with EndNote.**

## Preliminaries
This repository assumes the user has some familiarity using LaTeX, VS Code and EndNote.

For information on how to use are install the required software please visit:
* [VS Code](https://code.visualstudio.com/)
* [EndNote](https://endnote.com/)
* [LaTeX](https://www.latex-project.org/)/[LaTeX Workshop](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop)

<sup>In this repo we will be using LaTeX Workshop</sup>

## Set Up LaTeX Workshop

On VS Code, install [LaTeX Workshop](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop) extension. To do this: 
* Click `Extensions` on the primary side bar (Ctrl+Shift+X)
* Search `LaTeX`
* Click `LaTeX Workshop`
* Click `Install`

### Requirements

[LaTeX Workshop](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop) has some requirements.
* [TeX Live](https://www.tug.org/texlive/). Follow the guidelines on how to insall Tex Live for your Preferred Platform.
[Click Here](https://github.com/James-Yu/LaTeX-Workshop/wiki/Install#requirements) for further information and other optional software.

### Configure

After installing LaTeX workshop Requires some configuration. To do this: 
* Open the VS Code Command (`Shift` + `Ctrl` + `P` Windows) or (`Shift` + `Cmd` + `P` macOS)
* Search `Open User Settings JSON`
* Click on the file
* Now copy and paste the following inside the brackets {} of your `settings.json` file)


<details><summary>JSON</summary>
  <p>
  
```
"latex-workshop.latex.tools": [
        {
         "name": "latexmk",
         "command": "latexmk",
         "args": [
          "-synctex=1",
          "-interaction=nonstopmode",
          "-file-line-error",
          "-pdf",
          "-outdir=%OUTDIR%",
          "%DOC%"
         ],
         "env": {}
        },
        {
         "name": "xelatex",
         "command": "xelatex",
         "args": [
          "-synctex=1",
          "-interaction=nonstopmode",
          "-file-line-error",
          "%DOC%"
         ],
         "env": {}
        },
        {
         "name": "pdflatex",
         "command": "pdflatex",
         "args": [
          "-synctex=1",
          "-interaction=nonstopmode",
          "-file-line-error",
          "%DOC%"
         ],
         "env": {}
        },
        {
         "name": "bibtex",
         "command": "bibtex",
         "args": [
          "%DOCFILE%"
         ],
         "env": {}
        }
       ],

    "latex-workshop.latex.recipes": [
        {
            "name": "pdflatex ➞ bibtex ➞ pdflatex`×2",
            "tools": [
             "pdflatex",
             "bibtex",
             "pdflatex",
             "pdflatex"
            ]
           },
        {
         "name": "pdfLaTeX",
         "tools": [
          "pdflatex"
         ]
        },
        {
         "name": "latexmk 🔃",
         "tools": [
          "latexmk"
         ]
        },
        {
         "name": "xelatex",
         "tools": [
          "xelatex"
         ]
        },
        {
        "name": "xelatex ➞ bibtex ➞ xelatex`×2",
        "tools": [
          "xelatex",
          "bibtex",
          "xelatex",
          "xelatex"
         ]
        }
    ]
```
  
</p>
</details>

<sup>If your `settings.json` already has code in it add a `,` to the end of the last line before `}` and copy the new code after the `,` and before `}`</sup>

LaTeX Workshop is now ready to use in VS Code

## Using EndNote with LaTeX
To use EndNote with LaTeX, the EndNote library can be exported as BibTeX. First EndNote has to be configured to do this:
* Open your EndNote Library and click `Tools`
* Click `Output Styles`
* Click `Open Style Manager`
* Scroll and tick the box `BibTeX Export`

Export EndNote as BibTeX. To do this:
* Click `File`
* Click `Export`
* File name: `YOUR_FILE_NAME.bib`
* Save as type: `Text File (*.txt)`
* Output style: `BibTeX Export`
* Untick `Export Selcted References`

<sup>Note: if you only want to export the references you had selected before starting to export, tick `Export Selcted References` </sup>









