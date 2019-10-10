

# Recognizing hematopoietic cell types

## Immunophenotype
- [Nature 2016 ATAC-seq Table S1](https://www.nature.com/articles/ng.3646#supplementary-information)


## marker gene
[haematosphere](https://haemosphere.org/about): include human mouse homologs
[Lineage-specific marker gene for various dataset and literature](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5899604/)



# ATAC-seq
- [HOMER package](): `annotatePeaks.pl` recognized promoter and enhancer
- [nature 2016 Table S3, S4](https://www.nature.com/articles/ng.3646#supplementary-information) Provide TF and motifs already

# deconvolution
- CIBERSORT

# enhancer-enhancer, enhancer-promoter relationship
- EpiTensor(co-chromatin accessible)
- long non-coding RNA might help put then together (read Sheng Zhong's paper) and their RNA-DNA interation technology
- PLAC-seq by Bing Ren

# pathways
- KEGG
- Reactome
- PANTHER

# cytokine-ligand database
[Cells Talk](http://www.cells-talk.com/)
[FANTOM]

## done signature matrix
- [Nature 2016 ATAC-seq Table S2](https://www.nature.com/articles/ng.3646#supplementary-information)
- [MSC 2010 Table S1](https://www.embopress.org/doi/full/10.1038/msb.2010.71)


# Literature summary
1. [Lineage-specific and single-cell chromatin accessibility charts human hematopoiesis and leukemia evolution](https://www.nature.com/articles/ng.3646#supplementary-information)

- ATAC-seq on human (healthy and diseased, FACs data available)
- Enhancers are lineage specific (region data available), can CIBERSORT deconvolute them
- From these chromatin accessible region --> find motifs --> find key transcription factors: (GATA, RUNX, SPI1, PAX)
- but motifs are highly similar among TFs how do we know which is which?
	- further use RNA-seq (see which TF is present) + ATAC-seq (what motif is available)
	- Some show high correlation but some don't (HOX), they say something like "complex acessibility" which I don't understand. Maybe need other proteins to help? need epigenome modifiers?
	
- then they move on to see the variants(from GWAS) in regulatory region and at what stage they are avaiable
- they see the ATAC-seq in leukemoia patient and found higher heterogenity within cell types
    - they found leukemic cells are a mix of cellular states from different normal cell's enhancers

2. [Dynamic interaction networks in a hierarchically organized tissue](https://www.embopress.org/doi/full/10.1038/msb.2010.71)
- found pathways upregulated and downregulated v.s. stem cell expansion
    - a list of activating and repressing cytokines [Table S9-11]
- enrich downstream pathway from a literature curated gene sets about stem cell self renewal [Table S14]
    - gene set --> PPI --> enrich for KEGG and PATHER pathway 
	- find shared pathway molecules in stimulatory and inhibitory cytokines
3. [A 3D Atlas of Hematopoietic Stem and Progenitor Cell Expansion by Multi-dimensional RNA-Seq Analysis](https://www.sciencedirect.com/science/article/pii/S2211124719304954)
- single and bulk RNA-seq on developing zebrafish caudal something (resemble fetal liver), as well as GEO-seq
- close crosstalk between HSPC and endothelial cells --> developmental crosstalk
- region specific signalling pathway (Table S2) as well as ligand-receptor pair based on GEO-seq(Table S3)
- cross talk between ligand receptor pair between different tissue (neural, muscle, blood vessel)
- cell cycle features correlate with lineage??

4. [Haemopedia: An Expression Atlas of Murine Hematopoietic Cells](https://www.cell.com/stem-cell-reports/fulltext/S2213-6711(16)30131-X?_returnURL=https%3A%2F%2Flinkinghub.elsevier.com%2Fretrieve%2Fpii%2FS221367111630131X%3Fshowall%3Dtrue#secsectitle0145)
- a list of FACs markers Table S2
- a list of lineage specific genes Table S5
- a list of lineage specific genes that are enriched in specific perturbations Table S6
- lineage specific genes that are also max in human Table S7

5. [Huamn protein atlas, the blood atlas](https://www.proteinatlas.org/humanproteome/blood/blood+cells+summary)

6. [](https://www.ncbi.nlm.nih.gov/pubmed/26095048)