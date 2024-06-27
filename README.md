# The 2024 FEniCS Proceedings

## About the proceedings 

The proceedings of the FEniCS 2024 Conference (FEniCS 2024) will be published as a peer-reviewed edited volume by Springer Verlag in the open access book series Simula SpringerBriefs on Computing. This series aims to provide a concise introduction to select research topics for students or researchers entering new fields.  

## Aims and scope
The aim of the volume will be to give a glimpse of the current state-of-the-art in terms of development and applications of the FEniCS Project (FEniCS) software. Both theoretical and more application-oriented high-quality contributions are welcome. Each book chapter is expected to be accompanied by a FEniCS-based implementation or by a contribution to one or more of the FEniCS software components. 

## Editors
* Jørgen S. Dokken, Simula Research Laboratory, Norway
* Henrik Finsberg, Simula Research Laboratory, Norway
* Jack S. Hale, University of Luxembourg, Luxembourg
* Marie E. Rognes, Simula Research Laboratory, Norway
* Matthew W. Scroggs, University College London, UK 

Each contribution will be assigned to one or more editors. Each editor
will be responsible for the recruitment of reviewers and handling of
the review process of their assigned manuscripts.

## Review
All submissions will be subject to an initial editorial review, and if considered of sufficient quality and within the scope of the volume, peer-reviewed by two reviewers (single-blind) who can recommend; acceptance, revision or rejection. The final decision on acceptance or rejection will be made by the editors.


## Author instructions


### Preparing your chapter

To prepare your chapter, please create your own repository from the template (this repository):

  https://github.com/meg-simula/2024-fenics-proceedings

One-click option to create your own repository: 

  https://github.com/new?template_name=2024-fenics-proceedings&template_owner=meg-simula

To compile the book, run

```
$ cd book
$ make
```

Edit the sample chapter (chapters/chp1/...)

```
$ cd chapters/chp1
$ <edit> main.tex
$ <edit> bibliography.bib
$ mkdir graphics/
$ <add graphics>
```
### Submitting your contribution

To submit your contribution, send the generated book.pdf via email to Jørgen S. Dokken (dokken@simula.no).

### Chapter guidelines
* Each chapter should be no less than 6 and no more than 10 pages, including references
* Chapters should present original research
* Each chapter should include acknowledgments, including funding, as relevant.
* Each chapter should include an introductory abstract

Note that the Simula SpringerBriefs on Computing principles apply in
terms of open access (Creative Commons Attribution 4.0 International
License) and author rights (copyright remains with the
author(s)). Each accepted chapter will be assigned an individual DOI.

### Graphics requirements

* Place graphics under chapters/chp1/graphics
* Use vector graphics whenever possible

### Bibliography requirements

* Use BibTeX for the bibliography
* Make sure to include a DOI (whenever available) in each entry

### Supporting information and software

All chapters are expected to be accompanied by code released under an
open source initiative approved license and uploaded to e.g. GitHub or
GitLab alongside an upload to archival quality repository with a DOI
assigned e.g. Zenodo or figshare.
