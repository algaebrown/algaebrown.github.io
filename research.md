---
layout: default
title: research
---

# Research Focus: Antibiotic Resistance
Antibiotic resistance is a huge problem, especially in my country, Taiwan. Due to the health insurance policy, we have inexpensive access to medical care, resulting in overuse of antibiotics and emergence of resistant pathogens. During my rotation in the Intensive Care Unit, I saw a number patients fighting against resistant pathogens. Once patients have carbapenem-resistant pathogens, we are left with few choices. Health and technologies had advanced so much, but people are still dying from untreatable infections. Therefore, I chose to investigate this topic as my undergradate reseach.

My current advisor: [Dr. Yu-Wei Wu](https://sites.google.com/site/yuwwubioinfo/home) at Graduate Institue of Biomedical Informatics, Taipei Medical University

## Current Project: A Pan-genome Based Network to Assess Resistant Potential of Hypothetical Genes
![alt text](/assets/img/panNet.png)

In our previous study, we used student's t-test to identify gene clusters within the E.coli pan-genome that are correlated to resistance. Within the identifies gene clusters, some of them were hypothetical proteins. We wanted to know about their functions, and how their presence/absense leads to resistance, so that new drugs can be made based on that. 

Networks are very powerful methods to find out pathways or genes related to disease. There are co-expression networks, protein-interaction networks, and even integrated versions of them (termed **co-functional network**), such as [EcoliNet](https://www.ncbi.nlm.nih.gov/pubmed/25650278), [PseudomonasNet](https://www.nature.com/articles/srep26223#methods). However, when we queried the hypothetical genes using those built networks, it turned out those networks did not contain hypothetical protein of interest.

To infer functional relation of those hypothetical genes, I proposed to rebuild the co-functional network, that contains all the representing genes of the pan-genome. [Co-functional network](https://www.nature.com/articles/srep26223#methods) is based on **six types of information**: co-citation, co-expression, protein-protein interaction, protein domain sharing, co-inheritance and gene distance. Of all the six types of information for functional inference, **co-inheritance has the best chance to provide functional linkage**, as we could expect other kinds of data for hypothetical genes would be scarce.

To build co-inheritance network, a group of target genome has to be selected. The previous co-functional networks were based on reference genomes of prokaryotes, archaea, fungi and sometime eukaryotes. However, when searching for hypothetical protein homologs, those genomes generated no hits. We found out most homologs are harbored in closely related species, in this case are Enterobacteriae, Acinetobacter and Pseudomonas. Thus, those genomes are added as an additional set of target genome.

However, this additional set of target genome has very strong phylogenetic structures within, which will interfere co-inheritance analysis by confusing us with evolutionary events that occured at the root of the tree. We plan to integrate [phylogenetic independent contrast](https://www.r-phylo.org/wiki/HowTo/Phylogenetic_Independent_Contrasts) to correct this. Other limitations of our study include: unable to address the difference within a gene cluster, and problems related to local statistical methods, as described in this [review](https://www.nature.com/articles/nbt.2419).

## Project: Predicitng Antibiotic Resistance Based on Pan-genome
[Paper Full Text](https://www.ncbi.nlm.nih.gov/pubmed/29949970)

![Alt Text](/asset/img/ml_overview.png)
![Alt Text](/asset/img/why_pang.png)

We aimed at building an integrated method of to predict antibiotic resistance based on **interpretable** feature and model. Given the importance of **horizotal gene transfer, the pan-genome**, a concept describing all possible genes by a species, is the excellent way to view resistance. We build a model based on the absence-presence pattern. 

![Genetic Algr](/asset/img/genetic_algor.png)
![Final part](/asset/img/final_ml.png)

We select the best set of genes using genetic algorithm for the prediction. For each antibiotic, the model was built based on the selected set of features. We antiticipate the selected features to be correlated with antibiotic mechanism of action. But it turned out it does not.
 
In this study, genomes with resistance annotation was downloaded from PATRIC. At the time of project initiation, the data was relatively scarce. But now there are more and more data. Also, the gene pools for genetic algorithm selection was limited to known resistance genes. Single nucleotide variation and sequence difference within gene clusters were not considered. Last but not least, the gene selected from genetic algorithms were not explainable by current knowledge of drug mechanism. We hope to improve those in future studies. 


