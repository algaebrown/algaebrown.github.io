---
layout: post
title: "Predicting Evolution?"
date: 2018-09-13
tags: [literature]
---
I ran into this cool paper titled ["Predicting the evolution of Escherichia coli by a data-driven approach"](10.1038/s41467-018-05807-z) in my nature rss feed.
At first sight I was very fascinated by the fact that the authors may be able to predict the future.

# Summary
- Question
- Method
    - Material: all "lab evolution" and "E.coli" and "with whole genome sequencing" were included
    - Analysis:
        - data collection:
            - Environment = strain, medium, stress
            - Duration of experiment
        - data processing
            - "Mutator", strains with elevated mutation rate were excluded in most of the predictions unless specified. Exclusion was due to its distinct evolutionary process
            - Both genes and intergenic regions are involved. 
            - Insertion sequence (IS) elements
        - Model: Ensemble predictor (SVM, NB, ANN)
    
- Findings
- Results

## Learnings
1. gamma distribution indicate?
2. Network enrichment analysis?
- Gene enrichment analysis(GEA) is a term to describe: "Given a set of differentially expressed gene under certain condition, what group of functions are abundant?"
- Network enrichment analysis is replacing network with the function.
3. IS element
4. Spectral clusteing analysis
