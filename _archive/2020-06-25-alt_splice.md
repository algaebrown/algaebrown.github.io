---
layout: post
title:  "Differential Splicing Tools"
description:
date:   2020-06-25
tags: [RNA]
category: biology
tagline: 
---
# Why are isoforms important?
- Isoforms from the same gene can have different levels of activity.
- Isoform switching are widespread in differentiation, cancer and neurodegenerative diseases.

# Why they might not be as important?
- study show that most "expressed" isoforms are not detectable in mass spectrometry. It might be due to the detection limit of MS.

# Gaps in studying isoform
- For most isoforms their functional consequences are unknown.

# Why it is hard
- Read length of short-read sequencing is not long enough cross multiple intron and exons. Reads from different isoform may just all look the same. 
- Sequencing errors and variants.
- Non-uniform coverage in introns
- Non-uniform coverage in lowly expressed transcripts. Lowly expressed isoform might have very little read. Inadequate sequencing depth may just miss some of these isoforms.
- mismapping problem: miRNA and snoRNA derived from introns. They have the same sequence, so during mapping some miRNA become multi-mapped.
- Annotated transcripts are not all the isoforms. New isoforms are continued to be discovered by RNA-seq.

# Types:
1. Exon based analysis: DEXSeq, edgeR, JunctionSeq, limma
2. Splice Event based analysis: dSpliceType, MAJIQ, rMATs, SUPPA, IRFinder, BRIE
3. Full length isofom based analysis: de novo transcriptome assembly or by alignment: cuffdiff, DiffSplice, RSEM, HTSeq, feature counts...



# Alignment method
1. use STAR (intron aware aligner) to align to the **genome**: RSEM; Cufflink; HTSeq, feature counts, eXpress, TIGAR2(long read)
2. use STAR to directly align to the **transcriptome**: NRP
3. Use pseudoaligners: Kallisto, sailfish, Salmon

# Novel transcript discovery method
- Stringtie, SLIDE, iReckon

# Event calling

# Evaluation
- Novel transcript
- How number of sample affect the result
- How depth of read affect the result
- How complexity of gene affect the result
- How length of gene affect the result
- Similarity between tools
- 

# gold standard
- qPCR validated events

# Reference
1. https://www.biostars.org/p/178032/
2. https://academic.oup.com/bib/article-abstract/20/2/471/4524048?redirectedFrom=fulltext