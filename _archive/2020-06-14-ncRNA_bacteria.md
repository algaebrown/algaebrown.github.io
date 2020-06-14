---
layout: post
title:  "Bacterial non-coding RNA and RNA-binding proteins"
description:
date:   2020-06-14
tags: [Biology, RNA]
category: biology
tagline: 
---
# What are Non-coding RNAs

RNAs are once considered the intermediate between DNA and protein. But now more and more RNAs that don't serve as a tranlation template are discovered. Because they don't "code for protein", they are termed non-coding RNA (ncRNA). 

# Why are non-coding RNAs important?
Many non-coding RNAs have establish function in **eukaryotes**. For example, micro-RNA(miRNA) can get some proteins to regulate expressed RNAs; long non-coding RNAs(ncRNA) are shown to modulate 3D structure of the genome. There are even more examples. Many of them have established roles in cancer and various diseases. 

Non-coding RNAs in **prokaryotes**, are not as commonly discussed. But they do exist and are implicated in **regulating virulence, resistance and multiple important biological process**. 

# Bacterial transcriptional regulation: more than transcription factors.
A recent group revealed that only 20% of transcriptional response are explained by transcription factors [1]. They use a strain of Mycoplasma with minimal genome, puturb many DNA associated proteins, and measure the transcriptional repsonse. Other factors include DNA supercoiling, chromosome topology, associated moonlighting proteins, RNA degradation and metablic control can all affect transcriptional consequences. Within those, RNA-mediated mechanism has a modest effect(5-10%) on global transcription response. They discovered some putative elements that can affect translational termination. However, most of the ncRNAs discovered in this studies don't have a large effect on transcriptome. 

# How do non-coding RNAs work in prokaryotes?
[2][3]
Dicovered mechanisms are pretty similar to the eukaryotic version:

1. Affect translation
2. Affect mRNA stability
3. Regulate other transcriptional regulator
4. Sequester RNA-binding protein

## Affect translation
[2][3]

Non-coding RNAs can affect multiple steps in translation. They can hide or expose the ribosome binding site (by themselved or by inducing some secondary structure). Sometimes they don't do it themselves, the hire some RNA-binding proteins to do so. They can mimic Rho-independent translation termination signal to stop translation, or they can occupy Rho's binding site and stop the termination.

## Affect mRNA stability
[2][3]

They can recruit RNA helicase to degrade the mRNA, or stabilize some protective secondary structures.

## Regulate other transcriptional regulator
[2][3]
The above mechanisms can happen on transcriptional regulators, resulting in change in their expression and therefore their target's expression. 

## Sequester RNA-binding protein
[2][3]
Many RNA-binding proteins have regulatory functions on mRNAs. They might degrade it, or stabilize it. The non-coding RNA can act as a decoy site, diminishing the level of RNA-binding to mRNAs, and thus affect downstream transcriptional response.

All of those mechanisms can stack into layers of hierachies. In my opinion, this pose the challenge of detecting global responses from one single ncRNA. The inherent transcriptional noise can hinder the small and indirect effect of a single RNA species. Experimental pertubation can be resolved by numerous positive and negative control circuits.

# How to find ncRNA in bacterial genomes?

## Large scale sequencing experiments [6]
RNA-seq and microarray offer a way of unbias discovery. However, due to their small size,processing of 3' and 5' end and non-uniform coverage across longer transcript (compared to shorter miRNAs), reliable detection of full length transcript is not easy.

## Bioinformatic predictions. [6]
1. Based on evolutionary conservation: Functional important elements in the genome tend to have lower mutation rate. Since ncRNA commonly arise from intergenitc regions, by finding conserved sequences in there, we can have a list of ncRNA candidates.
2. Based on co-evolution: Many ncRNA form secondary structures to exert their function. Within the base pairing region, if one nucleotide changes, its partner would have to change accordingly. Therefore, if we see two nucleotide that always mutate together, then it is likely they form some secondary structure.

## Experimental Validation
Nothern blot is the gold standard method to validate the existent and expression level of some ncRNA. It detects RNA species by first seperating the denatured RNA by gel electrophoresis, and then hybirdize the target using complementary RNA probe. The problem with nothern blot is that it is not high throughput, and might require significant amount of ncRNA.

## Exsiting database
[BSRD: a repository for bacterial small regulatory RNA](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3531160/)

# Probing the function of ncRNA
From the known mechanisms, we know that these aspects are important for ncRNA function:
1. protein bound to the ncRNA: protein centric approach include in vivo CLIP-seq; in vitro RNA compete, RNA Bind-n-Seq.
2. ncRNA secondary structure: in slico prediction methods, experimental methods such as hiCLIP, iSHAPE, PARIS, MARIO, CLASH......
3. interaction of ncRNA to its target: methods measuring intramolecular RNA-interaction usually can detect intermolecular interaction as well.

# Difference between prokaryotes and eukaryotes
The above aspect of ncRNA are usually shared by both prokaryotes and eukaryotes, but these two types of organism still have some fundemental difference.

- Eukaryotes have nucleus while prokaryotes don't: In Eukaryotes, mRNAs has to be spliced and exported to cytosol before they reach the ribosome. In Prokaryotes, transcription and translation are coupled.
- They use different translation factors.
- They have different gene arrangements: prokaryotes have polycistronic RNAs.

All these aspects need to be considered when probing the ncRNA function in prokaryotes.


# Reference
1. Yus, E., Lloréns-Rico, V., Martínez, S., Gallo, C., Eilers, H., Blötz, C., Stülke, J., Lluch-Senar, M., & Serrano, L. (2019). Determination of the Gene Regulatory Network of a Genome-Reduced Bacterium Highlights Alternative Regulation Independent of Transcription Factors. Cell Systems, 9(2), 143-158.e13. https://doi.org/10.1016/j.cels.2019.07.001
2. Dutta, T., & Srivastava, S. (2018). Small RNA-mediated regulation in bacteria: A growing palette of diverse mechanisms. Gene, 656, 60–72. https://doi.org/10.1016/j.gene.2018.02.068
3. Holmqvist, E., & Vogel, J. (2018). RNA-binding proteins in bacteria. Nature Reviews Microbiology, 16(10), 601–615. 
4. Van Assche, E., Van Puyvelde, S., Vanderleyden, J., & Steenackers, H. P. (2015). RNA-binding proteins involved in post-transcriptional regulation in bacteria. Frontiers in Microbiology, 6. https://doi.org/10.3389/fmicb.2015.00141
https://doi.org/10.1038/s41579-018-0049-5
5. Tsai, C.-H., Liao, R., Chou, B., Palumbo, M., & Contreras, L. M. (2015). Genome-Wide Analyses in Bacteria Show Small-RNA Enrichment for Long and Conserved Intergenic Regions. Journal of Bacteriology, 197(1), 40–50. https://doi.org/10.1128/JB.02359-14
6. Leonard, S., Meyer, S., Lacour, S., Nasser, W., Hommais, F., & Reverchon, S. (2019). APERO: A genome-wide approach for identifying bacterial small RNAs from RNA-Seq data. Nucleic Acids Research, 47(15), e88–e88. https://doi.org/10.1093/nar/gkz485




