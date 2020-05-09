---
layout: post
title: "Why people are obsessed with long range information?"
description: 
date: 2020-05-09
category: technology
tag: [long reads, linked reads, structural variation, CSE283]
---
# Comparison of sequencing technologies (oversimplified)

|             | Sanger                                  | Illumina                                                                                                                                               | PacBio SMRT (Single Molecule, real-time sequencing) | Oxford Nanopore                                              | 10X                                                                                                                                                                                                                                                            | Optical mapping                                                                                                                                                                   |
|-------------|-----------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------|--------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|             | 1st generation sequencing               | short reads                                                                                                                                            | long reads                                          | long reads                                                   | linked reads = short reads + parallel barcoding                                                                                                                                                                                                                |                                                                                                                                                                                   |
| principle   | Sequencing by synthesis                 | Sequencing by synthesis                                                                                                                                | Sequence by synthesis                               | Ion current.                                                 | Microfluidics, barcoding, sequencing by synthesis.                                                                                                                                                                                                             | Microfluidics                                                                                                                                                                     |
|             | The added ddNTP will stop the reaction. | DNA is sheared to short pieces; while synthesizing, the incorpertaed nucleotide has dye attached to it. "clones of molecule" is visualize by the dye.  | "single molecule" is visualize by the dye.          | Measure the ion current when DNA bases crosses the membrane. | Microfluidis sort long fragments into beads. All large fragments are in the same bead has the same barcode. Although the reads are short, from the barcode we know which reads are from the same bead, inferring they might come from the same large fragment. | Linearized DNA molecule are cut by flourescent labelled restriction enzyme. The location of flourescence can infer long range information. But not the exact sequence in between. |
| read length |                                         | hundreds of b.p                                                                                                                                        | thousands b.p.                                      | thousands of b.p.                                            | thousands of b.p.                                                                                                                                                                                                                                              | 100 k.b. to 1Mb                                                                                                                                                                   |
| error rate  |                                         | 0.1 %                                                                                                                                                  | ~10%                                                | 10%                                                          | similar to short reads                                                                                                                                                                                                                                         |                                                                                                                                                                                   |

# How PacBio SMRT (Single Molecule, Real Time) sequencing works?
<iframe width="560" height="315" src="https://www.youtube.com/embed/_lD8JyAbwEo" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

# How Oxford Nanopore works
<iframe width="949" height="534" src="https://www.youtube.com/embed/RcP85JHLmnI" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

# How 10x Linked Reads work
[Link to video](https://10xgenomics.wistia.com/medias/f75ht43w1q)



# People are obsessed with "long range information (tens of thousands of b.p.)", why is that?

The purpose of long reads, linked reads and optical mapping are to get information across large regions of DNA? Why is this information important? Here are the reasons:

- **The genome has a lot of repetitive regions.** And short reads coming from those repeats all look very similar. Therefore it is hard to put back where exactly these short reads are from. If we can have longer reads that crosses the repetitive region, then it will be much easier.
- **The genome has many large variation: Structural Variation.** Large pieces (thousands of b.p.) of DNA might be inverted, duplicated, or simply having different number of copies. With short reads, although we might get reads crossing breakpoints, or have more reads aligning to the duplicated regions, these methods have limited sensitivity. Long range information seems to be a more direct way to detect these.
- **Haplotype phasing**: The human genome is diploid, meaning we have two copies of DNA that are *almost* the same. Say we have 2 positions, 5000 b.p. apart that are different, one being AT, the other being CG. To figure out which variants are on the same DNA is called haplotype phasing. Short reads will not be able to tell whether A and C or A and G is on the same copy of DNA.

# Reference
1. [Structural Variation in the sequencing era](https://www.nature.com/articles/s41576-019-0180-9)
