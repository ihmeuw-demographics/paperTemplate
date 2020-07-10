# paperTemplate

Template repository for scientific journal articles and associated materials

## Input data

Use the `data-raw` folder to save code that extracts or downloads the input
data used for your paper. This code can output data to the `data` directory.

Use the `data` directory to store input data. In this template, `.rds` files
in the `data` directory will not be tracked with git (see `.gitignore` file).

## Analysis

Use the `analysis` directory to save analysis code. Analysis should be split
into separate scripts appropriately. Operations that are common across analysis
scripts can be functionalized and saved to the `utils.R` file to minimize
repeated code.

Outputs of analysis can also be saved to the `data` directory as `.rds` files, 
or a new `results` directory can be created, as needed.

## Writing

Rmarkdown files are useful for paper writing, because code can be embedded
within, making number-plugging easier and more reproducible.

This template includes three Rmarkdown files:
1. manuscript
2. tables_figures
3. appendix

It may be appropriate to combine the tables and figures with the manuscript,
depending on how many tables/figures are included and how long they take to 
knit.

Go [here](https://rmarkdown.rstudio.com/lesson-1.html) for Rmarkdown 
instructions.

PDF output from knit Rmarkdown files are not tracked with git in this 
template. Use the `.gitignore` file if you want to change this.

## References

To save bibliographic information about sources used for your paper, use
a `.bib` file. This template includes `references.bib`. For information about 
`.bib` file syntax, go [here](http://web.mit.edu/rsi/www/pdfs/bibtex-format.pdf).

For information about citations in Rmarkdown, including instructions for
in-line citations, go [here](https://rmarkdown.rstudio.com/authoring_bibliographies_and_citations.html).

Reference styles can be managed using `.csl` files. This template includes
a `.csl` file for The Lancet, but other journal styles can be downloaded from
the [Zotero Style Repository](https://www.zotero.org/styles).

The `.bib` and `.csl` files are listed in the YAML header of all Rmarkdown 
documents that use references:

```
---
title: "manuscript"
author: "author"
date: "date"
output: pdf_document
bibliography: references.bib
csl: the-lancet.csl
---
```

## Figures

One recommended workflow for figures, represented in this template,
is to save functions for generating figures in a `figures` directory, one
per file, then load in data and call these functions within the Rmarkdown
files.

This process makes it easier to view the code for a specific figure,
and moves a lot of excess code out of the Rmarkdown file. Minimizing the amount
of code in Rmarkdown files makes it easier to read and focus on the text and
structure.