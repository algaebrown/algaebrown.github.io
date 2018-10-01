---
layout: post
title:  "Why long reads?"
date:   2018-09-19
---

1. Now:
- the sequences we have are based on parallel short-reads
- we know about a diseased genome by resequencing, that is, sequence by short read, then compare to a reference genome

2. Problem with short read and resequencing
- cannot detect small indel
- cannot detect structural variation?
- there is coverage bias: sequence with rich AT or GC are sequenced more
- the phase of mutation over a long range?
- large architecture of polymorphic copy number variation ?

3. Alternative: de novo assembly
- de novo means to "do it without reference genome"
- it's impossible to achieve with short reads

4. de novo method 1: whole genome shutgun and assembly(WGSA) - let's merge reads with max overlap
- there are problems: imbalanced coverage, repetitive sequence

5. Some popular mammalian genomes are sequenced using a "clone-by-clon based sequencing"
- sequence is broke up to 200-kb, cloned into bacterial artificial chromosome
- Each baterial artificial chromosome is sequenced.
- Because bacterial artificial chromosome as different sequence compositions, the cloned part is unique, making complete assembly possible

6. de novo assembly algorithms
- overlap-layout-consensus(OLC): iteratively merge overlapping reads.
    - repeats < read length will be resolved
    - as read length increase, resolution of sequencing increase
    - eats up a lot of memory as need to store pairwise overlaps
    
- de burjin graph: cut into small pieces called k-mer
    - no need to store pairwise overlap
    - a graph structure to represent repeats
    - but repeats > k-mer will not be seen

- string graph: don't cut to k-mer, cut the overlap


7. The technology of long reads: synthetic or single molecule sequencing
- single molecule sequencing (SMS) has problesm of low accuracy
    - therefore de burjin graph is a bad choive for its assembly
    
8. Problem with diploid genome: sometimes the two copies have different sequence (heterozygosity)
- solve with **reference graph**
    - edge = sequence
    - node = branching point
    
- role of **paired-end sequence**
    - [fragement, reads, paired end sequence](http://www.frontiersin.org/files/Articles/77572/fgene-05-00005-HTML/image_m/fgene-05-00005-g001.jpg)
