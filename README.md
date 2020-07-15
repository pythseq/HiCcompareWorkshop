<!--[![Build Status](https://travis-ci.org/dozmorovlab/HiCcompareWorkshop.svg?branch=master)](https://travis-ci.com/github/dozmorovlab/HiCcompareWorkshop/builds)-->

![.github/workflows/basic_checks.yaml](https://github.com/mdozmorov/HiCcompareWorkshop/workflows/.github/workflows/basic_checks.yaml/badge.svg)

# Detection of Differentially Interacting Chromatin Regions From Multiple Hi-C Datasets

### Instructor name and contact information

- Mikhail Dozmorov (mikhail.dozmorov@vcuhealth.org)

### Workshop Description

This workshop will introduce methods for the comparative (aka differential) analysis of the three-dimensional (3D) structure of the genome using data generated by high-throughput chromatin conformation capture (Hi-C) technologies. Hi-C data allows for insights into the genome-wide 3D genomic interactions which play an important role in regulating gene expression and other genomic processes. Just as differential expression analyses using RNA-seq data have become a routine part of genomic experiments, we expect the differential analysis of genomic interactions to become a common task. This workflow will help a novice learn to perform differential analysis of two or more Hi-C datasets and interpret the results of the differential genomic interactions.  

This workshop is based on [Stansfield et al., “R Tutorial: Detection of Differentially Interacting Chromatin Regions From Multiple Hi-C Datasets.”](https://currentprotocols.onlinelibrary.wiley.com/doi/abs/10.1002/cpbi.76). 

### Pre-requisites

* Basic knowledge of R syntax and command-line tools
* Familiarity with Hi-C chromatin conformation capture technology
* Understanding of Hi-C data properties (distance-dependent decay of interaction frequencies, biases)
* Familiarity with specialized (`.hic` [http://aidenlab.org/data.html](http://aidenlab.org/data.html), `.cool` [ftp://cooler.csail.mit.edu/coolers](ftp://cooler.csail.mit.edu/coolers)) and text-based (sparse upper-triangular, full square matrix) Hi-C data formats is desirable

### _R_ / _Bioconductor_ packages used

* [HiCcompare](https://www.bioconductor.org/packages/HiCcompare)
* [multiHiCcompare](https://bioconductor.org/packages/multiHiCcompare)

### Time outline

The workshop duration is 55 min. Approximate timing of activities:

| Activity                                              | Time |
|-------------------------------------------------------|------|
| Overview                                              | 5m   |
| Data representation and manipulation                  | 10m  |
| Differential analysis of Hi-C data                    | 10m  |
| Interpretation of Hi-C differences                    | 15m  |
| Questions and answers session                         | 15m  |

### Learning Goals

* Get familiar with Hi-C data import into R
* Understand the visualization of biases between pairs of Hi-C datasets using Mean-Distance (MD) plot
* Learn the Loess-based normalization strategy that minimizes between-dataset differences
* Perform differential analysis of $2 \times 2$ groups of Hi-C data, accounting for covariates, if needed
* Visualize and understand interaction frequency differences
* Get familiar with approaches for interpretation of chromatin interaction differences in the context of genes and gene expression differences

# Installation

```
if(!require(devtools)) install.packages("devtools")
devtools::install_github(repo = "mdozmorov/HiCcompareWorkshop", build_vignettes = TRUE)
```

If installation fails due to missing packages, install them like:

```
if(!require(BiocManager)) install.packages("BiocManager")
BiocManager::install("multiHiCcompare")
BiocManager::install("clusterProfiler")
BiocManager::install("ROntoTools")
BiocManager::install("DO.db")
```

[HiCcompareWorkshop pkgdown website](https://mdozmorov.github.io/HiCcompareWorkshop/)

[HiCcompareWorkshop Docker image](https://hub.docker.com/repository/docker/mdozmorov/hiccompareworkshop)

This workshop has been developed to be presented at the [Bioconductor Virtual Conference 2020](https://bioc2020.bioconductor.org/), July 30, 2020, 10:00-10:55am

