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
   <p>My supervisor is Dr. Yu-Wei Wu in Taipei Medical University, Graduate Institue of Biomedical Informatics. He works primarily on metagenomics. He is super supportive and always gives me a lot of helpful advice! Check out <a href=“https://sites.google.com/site/yuwwubioinfo“>his profile</a>here.</p>
   
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
   
   
   
   <h1> Some Q&As about me. </h1>
   
   <h2>You said you are a medical student. Why do research? Why COMPUTATIONAL RESEARCH?</h2>

   <h3> Because I am looking for the rules of biology and disease</h3>
   <p> My interest of the microscopic view of life science started early. When I was in high school, chemistry and physics were my favorite subjects, because I just love the way those scientist view the world. Their world is constructed with simple rules, such as atoms, forces. The idea of atoms making up all the things around me is fascinating. How can that be possible that such a small and simple particle create living creatures and bodies that are so perfectly regulated?</p>
   
   <h3>There are too much we do not know about disease</h3>
   <p>In particular, I am interested in the dysregulated body - diseases. Because, my gradma lost her eyesight in her mid-thirties, and till now, none of us, nor the doctors know exactly what happened. Is it possible to find a simple rule like atoms, to explain what had gone through my grandma's body. As a result, I chose to go to medical school, the only major that will have a board knowledge about the disease and the human body. However, I was not satisfied by the current theories. In fact, most of the time in medical school, we learn how to deliver the "optimal" management - which is not always satisfying - and does not have much time to think at a lower level. We spend a lot of time memorising existing theories - lots of signalling pathways, available drugs, side effects...etc, and try to integrate them in our small human brain. The huge amount of information often fail to predict the results or even give an explanation of the phenomonon. Therefore, aimed at finding out the underlying rules and provide a more holostic view of diseases, I started to participate in researches labs.</p>

   <h3>The cell is too complex for a human brain. We need computers to integrate rules of the cell.</h3>
   <p>During my second year, I took biochemistry, cell biology and programming courses at the same time, due to the need of the research projects. Again, a lot of details flooded into my brain. I LOVE to know those pathways and protein structures, but I HATE to memorise them. It's impossible for a person to have a holisitic view of a cell. All that we can do is focus on a protein, or one pathway, at the DNA or RNA level...etc. But in the real cells, so many kinds of molecules float and interact, obeying the rules of chemistry. How would it be like to take a tour into the cell, and just observe what really happen. The programming course sparked my idea of an in silico cell. Computers can store a lot of information. They can as well, calculate a huge amount of data. Maybe it will be a good idea to let computers do the job, and let it tell me what will and had happened at the microscopic level.</p>
   <h3> So I started by journey in computational biology. It‘s tough for a biology background person. But I love it</h3>
   <p>As a result, I started my journey in bioinformatics. Working with sequences and molecules, I feel as if I were building a cell in the server. From the genomic level, we find all possible genes that can be acquired by a bateria, and then use that to predict the outcome - antibiotic resistance. Then we moved on to find the relations between genes - how they may interact - by digging the information retained in evolution, expression pattern and retrieve the known from literature. At first, working with servers - a mouse-free environment - was very challenging for me. Those mathematical representations of sequences and machine learning models are puzzling as well. However, with the aid of several friends, advisor and serials of online tutorials, I gradually get used to work and think as a computer scientist. </p>
    
   <h2> What do you want to do in the future?</h2>
    <p> In the near future, I want to pursue Ph.D. in computational biology with the emphasis on quantiative science. I am interested in various kinds of topics, especially but not limited to multi-omics integration. I hope those methods can be related to clinical problems. </p>
	
<h2>What is your ultimate research goal?</h2>
<p> My "dream" is to build an in silico cell that can tell a story of the normal and the dysregulated body. To do this, the integration of multiple omics data, biology knowledge and many computation, statistical methods are needed. It is a very huge task, and it will definetly not be done by a single team. Many teams are tackling this problem with at different angle. Some develop joint assay to analyze RNA and Chromatin at the same time. Others use a more statistical/machine learning approach. Still are more teams work with a more analytical modelling approach. I truly anticipate that day to come. And when the in silico cell model is present, I think it should not be available only for research use. I want to modify it into a video game to make more people understand the cell by seeing it, travelling inside it and even interacting with its components. I am CONFIDENT that "in silico cell" will be a hot online/mobile role palying game(RPG).</p>

<h2>What are the other things you do?</h2>
<p>I draw, take photos and cook. I spent a lot of time talking to, and learning from patients. I like spy novels and reptiles.</p>


	
</div>
