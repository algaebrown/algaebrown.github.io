---
layout: post
title: "Creating Exon, Intron, UTR features from Gencode GRCh38 (Canonical transcript only)"
date: 2018-09-13
tags: [literature, bacteriology, biology, pangenome]
category: antibiotic resistance
---

[.gff Comprehensive gene annotation here](https://www.gencodegenes.org/human/)

[known canoncial transcript from UCSC genome browser](http://genome.ucsc.edu/cgi-bin/hgTables?hgsid=725869661_wEKn8bV7KmsR6WJ9W6jIT45len1r&clade=mammal&org=Human&db=hg38&hgta_group=genes&hgta_track=knownGene&hgta_table=knownCanonical&hgta_regionType=genome&position=chr1%3A11%2C102%2C837-11%2C267%2C747&hgta_outputType=primaryTable&hgta_outFileName=)



# find Ensembl transcript ID that appears in knownCanonical.txt, output to gencode_filtered
awk 'ARGIND == 1 {save[$5] = 1} ARGIND == 2 {split($9,fields, ":"); if(fields[2] in save) {print}}' knownCanonical.txt gencode.v33.annotation.gff3 > gencode_filtered.gff3




# from gencode_filtered extract only "exon"
awk '{ if ($3 == "exon"){ print } }' gencode_filtered.gff3 > gencode_exon.gff3



awk 'ARGIND == 1 {save[$5] = 1} ARGIND == 2 {split($9,fields, ";"); a = fields[1];b = gensub(/ID=/, "", 1, a);if(b in save) {print}}' knownCanonical.txt gencode.v33.annotation.gff3 > gencode_filtered_for_transcript.gff3

awk '{ if ($3 == "transcript"){ print } }' gencode_filter_for_transcript.gff3> gencode_transcript.gff3

bedtools subtract -a gencode_transcript.gff3 -b gencode_exon.gff3 > gencode_intron.gff3



cat gencode.v33.annotation.gff3 | grep prime_UTR > gencode_utr.gff3

awk 'ARGIND == 1 {save[$5] = 1} ARGIND == 2 {split($9,fields, ";"); a = fields[1];b = substr(a,9) ;if(b in save) {print}}' knownCanonical.txt gencode_utr.gff3 > gencode_utr_filtered.gff3

# combine into 1 file
cat gencode_exon.gff3 > gencode_combine_correct.gff3
cat gencode_intron.gff3 >> gencode_combine_correct.gff3
cat gencode_utr_filtered.gff3 >> gencode_combine_correct.gff3
```