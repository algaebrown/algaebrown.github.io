---
layout: post
title: "Antibiotic resistance is more than resistance genes"
date: 2018-09-13
tags: [literature, bacteriology, biology, pangenome]
category: antibiotic resistance
---

When I started studying antibiotic resistance, all I know was resistance genes - proteins that help the bacteria evade the attack of antibiotics. Some of them help the cell get rid of the drug - by degrading them, or pumping them out. Others are mutated drug targets - those target genes are usually essential for bacteria survival. They might synthesize DNA or protein, or be an important part of the cell wall. Once mutated, the drug cannot bind, and lose its magic of inhibiting cell growth and survival. Those genes are collectively termed resistant genes. These resistant genes are usually drug-specific. Each gene are responsible for a subtype of drug of certain chemical structure. One of the famous ones are beta-lactamases. They degrade drugs that are penicillin's cousin. [1]

Where do those resistance genes come from. There are two ways - by mutation, or by horizontal gene transfer, that is, getting genes from plasmids, virus. I imagined that for a bacteria to acquire a mutation, or a new gene, it must need some time, before it is killed. But if those drugs hit the essential functions right in the head, how can the cell have time to gain a useful mutation, or borrow a new gene from some distant relatives?

This questions stayed in my mind for many years. But I never really addressed it in research, nor do I try to read anything about them. 

One day I ran pan-genome-wide-association analysis [2], a method to look for presence of which gene is associated with resistance. After harvasting a list of "putative resistant genes", I compare them to known resistance genes in the Comprehensive Antibiotic Resistant Database (CARD) [3]. Most of them are NOT already known resistant genes - which is good, and bad. The good thing is that it *might* lead to some discovery. The bad thing is - it can as well hint that your analysis is a problematic, so that you cannot reproduce well-established knowledge. Many putative resistant genes are shared by several drugs. Among them about 1/3 are of unkonwn function. Being optimistic, I try to cluster the putative genes based on what kind of drug they provide survival advantage. The result show - the putative genes is NOT AT ALL, EVEN A BIT, related to drug structure. It means those protein product are not directly in contact with the drug. And how can they be related to resistance, at all?

So I turned very pessimistic - it must be due to lack of data, so that we are getting a list of garbage genes. It can also be due to co-inheritance of genes, that some genes just come in cluster with others, and most of them in the group don't do anything with drugs. I look into the list of genes with all the annotations - there are a group of transcription factors, a bunch of phage stuffs, some toxin, some iron trasporter and seemingly unrelated metabolic genes.... they must all be noise!

But I came across an old review - A Global View on Antibiotic Resistance[4]. Instead of seeing antibiotics as a drug, the article starts by describing it as a **signalling molecule**. That is actually more true, if you stand in the shoe of some antibiotic-producing bacteria or fungi (if they ever wear a shoe). Those small molecules aren't made to treat infection! Once upon the time when we humans are still apes, these tiny cuties already live on earth, secreting those "antibiotics", maybe at a lower concentration. These molecules are like cell phones, or Facebook, or Instagram (for the younger generation!), that convey important message to their neighbors - "F* get out of my garden!" "Hosting potluck today" Therefore the genes that interact with the antibiotc **signalling molecule** on the other side are not just shields against weapons. Instead they are just like the **receptors** we know that modulate cell activity by changing what protein to produce, making the cell crawl, eat more and sleep... etc.

Seeing and thinking resistant genes as a receptor, we now start take another perspective. Think about the receptors in cancer cells. They swap the metabolic state, they change the gene expression, affecting almost every aspect of cell biology. Antibiotic resistant genes, may act this way too. 

# Biofilm

# Persister

# Metabolism
Traditionally, the change in metabolic state in resistant strains has been viewed as an adaptation due to hosting an extra genetic materia, the plasmid. To host the extra plasmid, the bacteria needs to eat more, synthesize more to replicate that extra piece of nucleotide sequence, express its protein and so on. But later people found out some resistant strains can utilize different kinds of sugar to grow! If it was just to host extra genetic material, why bother doing that? From then on, 



1. Blair, J. M. A., Webber, M. A., Baylay, A. J., Ogbolu, D. O., & Piddock, L. J. V. (2015). Molecular mechanisms of antibiotic resistance. Nature Reviews Microbiology, 13(1), 42–51. https://doi.org/10.1038/nrmicro3380
2. Brynildsrud, O., Bohlin, J., Scheffer, L., & Eldholm, V. (2016). Rapid scoring of genes in microbial pan-genome-wide association studies with Scoary. Genome Biology, 17(1), 238. https://doi.org/10.1186/s13059-016-1108-8
3. Jia, B., Raphenya, A. R., Alcock, B., Waglechner, N., Guo, P., Tsang, K. K., … McArthur, A. G. (2017). CARD 2017: Expansion and model-centric curation of the comprehensive antibiotic resistance database. Nucleic Acids Research, 45(D1), D566–D573. https://doi.org/10.1093/nar/gkw1004
4. Martinez, J. L., Fajardo, A., Garmendia, L., Hernandez, A., Linares, J. F., Martínez-Solano, L., & Sánchez, M. B. (2009). A global view of antibiotic resistance. FEMS Microbiology Reviews, 33(1), 44–65. https://doi.org/10.1111/j.1574-6976.2008.00142.x


