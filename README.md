# LS2
 Code for the analysis of the splicing activity of LS2 and its mutants

## Overview

This repository contains gene expression and alternative splicing data from _Drosophila_ S2 cells in which the splicing factor LS2 had been transiently expressed. In addition to wildtype LS2, mutant versions of LS2 were also tested in their ability to regulate alternative splicing.  LS2 proteins were expressed as GFP fusions. Comparisons of alternative splicing patterns are therefore between GFP samples and GFP-LS2 fusion samples.

A manuscript describing this data can be found [here](https://www.biorxiv.org/content/10.1101/2020.08.15.252130v1).

Gene expression values for these RNAseq samples were calculated using [`kallisto`](https://pachterlab.github.io/kallisto/) and [`tximport`](https://bioconductor.org/packages/devel/bioc/vignettes/tximport/inst/doc/tximport.html).

Alternative splicing analyses were done using [`rMATS`](http://rnaseq-mats.sourceforge.net/).

## Code in this repository

There are two python scripts:

- rMATS_preptable.py
- rMATS\_motif\_cdf_se.py

rMATS_preptable.py takes an rMATS output table and prepares it for further use by adding some columns and splitting others.  It has been tested with:

- python 2.7.13
- pandas 0.24.2
- biopython 1.66

rMATS\_motif\_cdf_se.py takes a prepped rMATS table (from above) and counts occurrences of RNA sequence motifs near regulated exons. It has been tested with:

- python 2.7.13
- pandas 0.24.2
- biopython 1.66

There is one RMarkdown file:

- LS2analysis.Rmd

This file contains code to perform statistical analysis and plots of the gene expression and alternative splicing data. It has been tested with:

- R 3.6.3
- dplyr 1.0.0
- tximport 1.14.2
- readr 1.3.1
- biomaRt 2.42.1
- pheatmap 1.0.12
- ggplot2 3.3.2
- reshape2 1.4.4
- ggfortify 0.4.10
- RColorBrewer 1.1-2
- cowplot 1.0.0.9000
- UpSetR 1.4.0

## Data in this repository

Kallisto transcript quantifications of RNAseq samples can be found in `kallistoouts`. rMATS quantifications of alternative splicing differences between RNAseq samples can be found in `rMATS`.
