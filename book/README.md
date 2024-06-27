# SpringerBriefs MRI to FEM vol. 2

This repository contains the source code and instructions for how to add your chapter to the MRI to FEM vol. 2 SpringerBriefs book.

## Guidelines for authors

All authors should read section 2.3 - 2.9 in the [instruction manual](../template/guideline/authinst.pdf) for details on how to format their chapter.
You can also have a look at the [reference guide](../template/guideline/refguide.pdf) which contains more information about the available environments.

### Labels and references

We want to keep labels consistent. The table below show the conventions used for the different types of labels. We will make final edits to make sure there are no conflicting labels. For figures, tables, sections, equations and theorems, use the labeling as outlined below.

|     Type | Label starts with |       Example label (hf) |
| -------: | ----------------: | -----------------------: |
|   Figure |             `fig` |       `\label{fig:cell}` |
|    Table |             `tab` | `\label{tab:parameters}` |
|  Section |             `sec` |      `\label{sec:model}` |
| Equation |              `eq` |       `\label{eq:model}` |
|  Theorem |             `thm` |      `\label{thm:model}` |

Use `\eqref` to reference equations, and use `\ref` otherwise.

### Bibliography

We use a central bib-file for references. It is located at [here](./bibliography.bib).
To find the BibTex entry, you can search on Google scholar (or any other search engine for papers), select BibTex and copy all the fields in the `.bib`-file.
Usually, it is easiest to find the correct format on the journal's web-page. Remember to add any DOI (Digital Object Identifier) to the bibliography, as it makes it easier
for anyone to look up the publication.

If you need to cite a chapter in this book then add the following entry to your `.bib`-file:

```
@incollection{mri2fem2,
  author       = {Authors of the chapters you want to cite},
  title        = {The title of the chapter you want to cite},
  booktitle    = {MRI2FEM II: from magnetic resonance images to computational brain mechanics},
  publisher    = {Springer},
  doi          = {xxxx/yyy-zzz}
  year         = 2023,
  editor       = {Rognes, Marie E and Vinje, Vegard and Dokken, Jørgen and Valnes, Lars Magnus and Mardal, Kent-Andre}
}
```

## Adding your chapter to the book

Make sure that you are working on your own branch before pushing, i.e. that you have done

```
git clone git@github.com:meg-simula/2023-mri2fem-ii.git
git checkout -b <username>/<chapter name>
```

In order to add your chapter to the book please do the following

1. Create a new sub-folder in the folder named `book2/chapters`, and put all your files in this folder.

   - Make sure that your main latex document is called `main.tex`.
   - Do not use `\include` or `\input`. Instead you should have one single LaTex file (i.e `main.tex`).
   - Do not use spaces in the names of files or folder. Use an underscore (`_`) instead.

2. Remove all code in your latex document that is defined outside the document (including `\begin{document}` and `\end{document}`), such as packages and new commands.

   - Please consult the example chapters for details.
   - If you are using any fancy packages, then you can add these in the latex file called [`packages.tex`](packages.tex).
   - If you have defined your own commands then put these commands in the latex file called [`commands.tex`](commands.tex).
   - Add the path to your figures in a block inside `graphicspath` (see example chapters)
   - For you references use the full path to the `.bib`-file and use the style `spbasic` (`\bibliographystyle{spbasic}`)

3. Include your main latex file in the file called [`book.tex`](book.tex).

   - Add the line `\include{chapters/<name of chapter>/main}` between thee command `\mainmatter` and `\backmatter`.

4. Add your name, email and affiliation to the list of contributors
   - Edit the file [contriblist.tex](contriblist.tex)

### Verify successful compilation

You can check that your chapter is successfully compiled by typing

```bash
make clean
make
```

in the root directory of this repo. In order for this to work you need to also have some latex packages installed.

#### Optional (use docker)

It is also possible to compile the document within a docker container, by first building a docker image using the provided [`Dockerfile`](Dockerfile) or using the existing image `ghcr.io/scientificcomputing/latex-full:2023-11-07a`.
This is useful if you are using Windows or you don't have all the required LaTex packages already installed.

If you execute command

```bash
docker run -ti --name emi_book -v "$(pwd):/home/shared" -w  ghcr.io/scientificcomputing/latex-full:2023-11-07a
```

in the root directory of this repository, you will spin up a container with all necessary latex packages pre-installed.

### Finished

Before deadline of a submission (draft, final or revised version), verify that everything looks good and submit a pull request. Click on `"Pull requests"->"New pull request"``, and select your branch in the box to the right, and the main branch to the left. Finally press "Create pull request".

This will make Github compile the book, and if successful upload it to "Actions"->"Build latex book and upload artifact"->"Your commit message"->"book". If the action is not successful, please recompile locally and check that all required files are uploaded.
