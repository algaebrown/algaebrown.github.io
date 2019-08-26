---
layout: post
title: "State of the art of hypothetical protein prediction in prokaryotes"
date: 2018-10-21
tags: [literature]
---

# Original Paper:
[Tackling Hypotheticals in Helminth Genomes](https://linkinghub.elsevier.com/retrieve/pii/S1471492217302817).
- Type: review article
- Organism: helmith

This article is about helmith. But what I care are prokaryotes. So I decide to make a note to record all aspects mentioned in this paper, but targeting **prokaryotes**.

# An silico approach based on gene expression data and GO term: gamma-AM
[Original Paper](http://arxiv.org/abs/1608.03672)
- Example: There are two sets of genes. Gene set A has both expression data and GO term. Set B has only expression data.
- Step 1: calculate the similarity between all genes within gene set A. The similarity is defined as "gamma distance".
    - gamma distance = (gamma)(distance between go terms) + (1-gamma)(distance between expression)
    - the gamma value decides the weighting (importance) of GO term.
- Step 2: cluster gene set A based on gamma distance
- Step 3: assign genes in set B into clusters that are formed by set A genes.
    - set B genes are assigned to the cluster if the centroid (with only expression data) is the closest.
- Step 4: infer GO term of the set B genes by referring to other set A members in the same cluster (cluster enrichment analysis)
- Note: this algorithm is not dedicated to helmith only. Applicable to bacteria.

# Methods Based On Domain, or the sequence homology
- homology: KEGG, Uniprot, BRENDA
- based on domain and sites: InterProScan
- The above ones have higher false negative due to poor convergence of sequence outside of the active site.

## Methods to improve false negative of homology models
- [PRIAM](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC275543/)
    - target: ** enzymes**
    - method:
        - group all available enzymes according to their EC number. (An EC number corresponds to one kind of activity. For example: alcohol dehydrogenase)
        - find the longest common sequence within a single EC group. This is called a **module**.
- EFICAZ and DETECT are also for **enzymes** only

# Method based on phylogenomics

# Other
- HMM
- 3D homology

# Methods only suitable for core genes (conserved hypothetical proteins)
- [Pathway reconstruction and pathway inference](https://doi.org/10.1186%2F1471-2105-5-76)
    - input: genome
    - output: pathways and genes involved
    - missed genes in the pathway can be the possible role of the hypothetical protein
- orthology based inference


# Validation of inference
- cDNA search in database
- RNA-Seq
    - Improved technology allow us to see the 5' end of RNA, enabling us to find the promoter and possibly find the whole operon
    
- Proteomics: LC MS/MS
- Functional genomics tools:
    - CRISPR
    - RNAi

# Hypothetical genes can be RNA?
- Do prokaryotes have ncRNA? YES
- What do they do? complement to mRNA and kill them. Associated with virulence, quorum sensing
- Tools to predict small RNA in prokaryotes? [Here](https://doi.org/10.1038%2Fsrep46070)
