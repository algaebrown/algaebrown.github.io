---
layout: post
title:  "Integrating multiple single cell datasets"
description:
date:   2019-10-01
tags: [algorithm, data science, single cell, bioinformatics]
category: algorithm
tagline: 
---

This post is about integrating multiple single cell datasets. For example, when we have two sets of single cell data, one from a healthy perons, the other from a person with certain disease, how can we integrate those two data so that we can compare the cellular composition? More boradly, how do I integrate single cell datasets from different species (mouse v.s. human), different molecular species (RNA-seq v.s. ATAC-seq, if they are not done jointly)? More practically, how to I integrate single cell experiments from different batch, that is, experiments done today and a year ago.

This is not a trivial question. Why? First, when we run experiments in different settings, for example, using different sequencing machine, library preperation, sequencing depth, the results can be different. We might mistake RNAs with more reads having higher expression despite its due to higher local coverage. Even if we try our best to control those factors, sometimes we still observe technical noise in our data. In that way, if we just pour cells from two different sets into a low dimensional space, likely will we see clusters of cells delineated by batch. Second, single cell sequencing, due to small amount of materials (DNA/RNA), the data quality itself is not good. There are a lot of drop-outs, that is, undetected RNAs. Say patient one and two all have their marrows biopsied and we ran single cell experiment on them. Cell of the same type in patient one drop gene A,B,C while the other droped D,E,F, making their expression values look different. The noisy nature of single cell experiment as well as the inherent technical noise makes integrating data a non-trivial question.

How do we deal with that? Here I will compare a few published approach and talk a bit about the principles behind.