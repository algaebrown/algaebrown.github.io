---
layout: post
title:  "Common tools for processing biological data"
description:
date:   2019-09-16
tags: [unix, conda, R]
category: Unix
tagline: 
--
# Nucleotide sequencing
- align to exisiting genome
- de novo assembly (Steven Stalzberg)

## How to assembly
- de burjin graph
- wikipedia as a list of assmebler

## Align
- STAR
- Bowtie, Bowtie2
- TopHat

## how Fasta look like
- a header begining with `>`
- a sequence

## different genomic coordinate: 
[crossmap](https://academic.oup.com/bioinformatics/article/30/7/1006/234947)

- hg19, GCCh37,

## human pan-genome

## Quality control:
- FASTQ
- phred score
- fastqc, trimommetic revmoes the low quality bases

## The aligned:
- sam bam file

## Encode an alignment 
- CIGAR

## counting readins mapped to certain regions
- bedtools
- featureCounts
- Kallisto

## DIfferentially gene (RNA-seq)
- DESeq2
- limma
- edgeR
- sleuth

# Sequence variation
SNP, indel, large scale SNV

## data files
- VCF: SNP, indel by `GATK` or `VCFtool`
   - metadata: how data are generated
   - info about variants, ID, positions, RSID(Variant ID), subject ID(who get the variant)
- PLINK:
   - `.map` plain txt: line is a variant, 
   - `.ped` file: family ID,
- GFF/GTF

# single cell sequecing data
- CellRanger: 10X genomics
- Seurat, Monocle
- R and python

- UMAP and t-SNE

- how to deal with sparse: Scipy, R, HDF5

# Networking
- cytoscape, nDEX, stringDB
- networkx in python

- kEGG, reactome: cellular pathway
- BRENDA, BiGG, BioCyc: metabolic network
- DAVID, enricher: enrichment analysis

# Genome browser
- IGV (Integrated Genome Viewer)
- UCSC genome browser


