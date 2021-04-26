


<img src="{{ '/assets/img/her.jpg' | prepend: site.baseurl }}" alt="">
	<p class="intro">
   <h1> Some Q&As about me. </h1>
   # Interpretable Autoencoder to Embed Single-cell data
![alt text](/assets/img/vnn.png)
Single-cell technology is revolutionizing our understanding of biology. However, current visualization methods are disconnected with biological insights. It is impossible to tell the functional difference between two clusters by looking at the axes (UMAP-1 and UMAP-2). Therefore, I proposed to directly embed cells into interpretable dimensions. First, I trimmed the Gene Ontology(GO), retaining only a small number of informative terms. Then, I built an autoencoder, where each neuron corresponds to a term. As a result, the learned embedded will be in the space GO terms - which directly provides biological meaning. The extracted embedding was able to retain populational sturcture. Looking closer at each axes, it successfully tells us the biggest different between glutaminergic neuron and other cell types are "glutamate carboxylase activity".

# Single Cell Secretome in Haematopoietic Stem Cells
![alt text](/assets/img/hema.png)


# Estimating KIR copy number from Whole Exome Sequencing data
![alt text](/assets/img/kir.png)
Immunotherapy is changing our way to view cancer. To understand the heterogenous immune response to tumors between patients, we must be able to first accurately measure their genotype. KIR genes is a receptor on natural killer cells. Which haplotype of KIR we have will affect the outcome in many diseases, such as hepatitis, autoimmunity and transplant rejections. 

However, the KIR allele is pretty messy in the current genome coordinate. Previouly, Rachel Marty was able to impute KIR copy number using k-mer counts. She also discovered that the counts are severely affected by different exome capture kit used. To solve this problem, I used a technique called integrated NMF(iNMF) and nearest neighbor to remove the batch effect within dataset. iNMF decompose the k-mers into factors of co-varying k-mers. It also identifying co-varying k-mers in each dataset, and find a common sharing pattern between datasets. Removing the unshared portion, which we assume are the batch effects, we can impute the original k-mer, and infer copy number with a greater accuracy.
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

