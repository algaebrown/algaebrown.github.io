---
layout: default
title: About Hsuan-Lin Her
---

<div class="post">
	<h1 class="pageTitle">About Hsuan-Lin Her</h1>
	<img src="{{ '/assets/img/her.jpg' | prepend: site.baseurl }}" alt="">
	<p class="intro">Hsuan-Lin is a Medical Student from Taiwan, who is interested in explaining the concept of disease with molecules and sequences.</p>

   <h2>Current research focus: Antibiotic resistance</h2>
   <p>Antibiotic resistance is a huge problem, especially in my country, Taiwan. Due to the health insurance policy, we have inexpensive access to medical care, resulting in overuse of antibiotics and emergence of resistant pathogens. During my rotation in the Intensive Care Unit, I saw a number patients fighting against resistant pathogens. Once patients have carbapenem-resistant pathogens, we are left with few choices. Health and technologies had advanced so much, but people are still dying from untreatable infections. Therefore, I chose to investigate this topic as my undergradate reseach.</p>
   <p>My supervisor is Dr. Yu-Wei Wu in Taipei Medical University, Graduate Institue of Biomedical Informatics. He works primarily on metagenomics. He is super supportive and always gives me a lot of helpful advice!</p>
   
   <h3>Project: A pan-genome based network to assess resistant potential of hypothetical genes</h3>
   
   <p>In our previous study, we trained a model to predict antibiotic resistance by absense-presence pattern of genes. In that study, we found a number of hypothetical proteins that are significantly related to resistance. We wanted to know about their functions, so that new drugs can be made based on that. </p>
   <p>Networks are very important methods to find out pathways or genes related to disease. There are co-expression networks, protein-interaction networks, and even integrated versions of them (such as EcoliNet, PseudomonasNet). However, when I query my hypothetical genes using those built networks, I found that those nets do not contain the genes I am looking for. Therefore, to find out what those genes are doing, I decided to build my own network.</p>
   <p>Building my own netorks seems mission impossible for me. Where should I get data from? No one would do yeast-two-hybrid for hypothetical proteins! But it turned out evolution had leave us a lot of information in the genomes. And now there are so many genoms in NCBI! Co-inheritance and distance can infer some functional relationships. What‘s more exciting is that RNA-seq can detect unknown species of RNA. So probably I can find something out from those data!</p>
   <p>This idea is very mad. And there are some problems I had thought of （and still did not have good answer). First, maybe most of them they are pseudogenes. Second, since our network is based on pan-genome clusters. In each gene cluster there has some mutations. How good can a representing gene speak for all members of the same clusters? </p>
   <p> Let‘s see what I can find out. </p>
   
   <h3>Project: Predicitng Antibiotic Resistance Based on Pan-genome</h3>
   <p> We aimed at building an integrated method of to predict antibiotic resistance based on interpretable feature and model. Given the importance of horizotal gene transfer, the pan-genome, a concept describing all possible genes by a species, is the excellent way to view resistance. We build a model based on the absence-presence pattern. We select the best set of genes using genetic algorithm for the prediction.</p>
   <p><a href="https://www.ncbi.nlm.nih.gov/pubmed/29949970">Our paper </a></p>
   <p> In this study, genomes with resistance annotation was downloaded from PATRIC. At the time of project initiation, the data was relatively scarce. But now there are more and more data. Also, the gene pools for genetic algorithm selection was limited to known resistance genes. Single nucleotide variation and sequence difference within gene clusters were not considered. Last but not least, the gene selected from genetic algorithms were not explainable by current knowledge of drug mechanism. We hope to improve those in future studies. </p>
   
   
   
   


	
</div>
