---
layout: post
title: "Debug Diary: Running MaxEntScan"
description: What to do if cannot find the entry point of some software :(
date: 2021-09-24
category: Whining
tag: []
---

# MaxEntScan
- is an algorithm to score splice site strength

# Installation
I was able to install it with conda
```
conda create -n maxentscan
conda activate maxentscan
conda install -c bioconda maxentscan
```

The reason to use conda is that the Perl dependency is not easy to handle if I install by myself. Since someone has already solved it, why not use it?

# But there is no documentation in how to run the program
- The only thing I can find is this, the server in Burge Lab's website. http://hollywood.mit.edu/burgelab/maxent/Xmaxentscan_scoreseq.html
- Then I found link [Download perl wrappers](http://hollywood.mit.edu/burgelab/maxent/download/)

# Running the command in READTHIS does not work
[LINK TO READTHIS](http://hollywood.mit.edu/burgelab/maxent/download/fordownload/)
```
perl score5.pl test5 
perl score3.pl test3
```
returns "can't open perl script "score3": No such file or directory"

I figured that the script is not added to the path, and to do this I need to find where conda puts the script.

## Locating the script

Thus, in the `maxentscan` env, I typed:

```
which perl
```

as I know the perl is installed along with maxentscan. And knowing where perl is can help me find where the script is located.

Apparently `perl` is located in `~/miniconda3/envs/maxentscan/bin/perl`.

Therefore the script is likely in `~/miniconda3/envs/maxentscan/bin/`

I went there `cd ~/miniconda3/envs/maxentscan/bin/` and was able to locate the 2 scripts, but named differently. (WHY!!!!!)

they are named `maxentscan_score3.pl` and `maxentscan_score5.pl`

# Running the script

Usually those scripts will have a help message when you call them with nothing.

But it doesn't.

```
maxentscan_score5.pl
maxentscan_score3.pl -h 
maxentscan_score3.pl --help 
```
will only show "can't open", which is confusing.

Assuming that this is the same script as the one on the Burge lab website, I download the test data:

```
wget http://hollywood.mit.edu/burgelab/maxent/download/fordownload/test3
wget http://hollywood.mit.edu/burgelab/maxent/download/fordownload/test5
```

and test it
```
maxentscan_score3.pl test3
```

returns: "ctctactactatctatctagatc 6.71"

It worked.

# TLDR How do I run MaxEntScan if I install via conda?

```
conda create -n maxentscan
conda activate maxentscan
conda install -c bioconda maxentscan
wget http://hollywood.mit.edu/burgelab/maxent/download/fordownload/test3
wget http://hollywood.mit.edu/burgelab/maxent/download/fordownload/test5
maxentscan_score3.pl test3
```

# It turns out that there is already a python wrapper of it.
- [NovaSplice](https://github.com/aryakaul/novasplice)
- [pymaxent]


# Running it transcriptome wide
maxentscan takes a fasta file which contains the 5'ss or 3'ss sequence of designated length. 

Referencing to NovaSplice's way to generate `exon_junction.bed` I wrote the following script:

First I find all the exons
```
from pybedtools import BedTool
coord=BedTool('/home/hsher/gencode_coords/gencode.v33.annotation.gff3')

# generate intron by subtracting exon from intron
exons=coord.filter(lambda x: x[2]=='exon').saveas()
```

Then for every exon, a 3'ss is at the 5' end of the exon. 5'ss is at the 3' end of an exon.
I save those intervals along with its name to a list.
```
all_5ss=[]
all_3ss=[]
for exon in exons:
    
    
    if exon.strand == '+':
        ss3_start = exon.start-20
        ss3_end = exon.start+3
        ss3_site = exon.start
        
        ss5_start=exon.end-3
        ss5_end=exon.end+6
        ss5_site = exon.end
    if exon.strand == '-':
        ss5_start = exon.start-6
        ss5_end = exon.start+3
        ss5_site = exon.start
        
        ss3_start = exon.end-3
        ss3_end = exon.end+20
        
        ss3_site = exon.end
    
    all_5ss.append([exon.chrom, ss5_start, ss5_end, exon.strand, exon.attrs['transcript_id'], exon.attrs['gene_id'], ss5_site])
    all_3ss.append([exon.chrom, ss3_start, ss3_end, exon.strand, exon.attrs['transcript_id'], exon.attrs['gene_id'], ss3_site])
```
Convert the list to bedtools and use `BedTool getfastq` to fetch the sequence.
```
import pandas as pd
df5=pd.DataFrame(all_5ss, columns = ['chrom', 'start', 'end', 'strand', 'transcript_id', 'gene_id'])
b=BedTool.from_dataframe(df5[['chrom', 'start', 'end',  'transcript_id', 'gene_id', 'strand']])
x = b.sequence(fi='/home/hsher/gencode_coords/GRCh38.p13.genome.fa', s = True,
               fo='/home/hsher/gencode_coords/gencode.v33.5ss.fasta')

df3=pd.DataFrame(all_3ss, columns = ['chrom', 'start', 'end', 'strand', 'transcript_id', 'gene_id'])
b=BedTool.from_dataframe(df3[['chrom', 'start', 'end',  'transcript_id', 'gene_id', 'strand']])
x = b.sequence(fi='/home/hsher/gencode_coords/GRCh38.p13.genome.fa', s = True,
              fo='/home/hsher/gencode_coords/gencode.v33.3ss.fasta')
```

Looking at the output:
```
(maxentscan) [hsher@tscc-login2 ~]$ head /home/hsher/gencode_coords/gencode.v33.5ss.fasta
>chr1:12224-12233(+)
CCAGTAAGT
>chr1:12718-12727(+)
GAGGTGAGA
>chr1:14406-14415(+)
CTGCTCAGT
>chr1:12054-12063(+)
GAGCACTGG
>chr1:12224-12233(+)
```

This file can now be fed into `score5.pl`:

```
maxentscan_score5.pl /home/hsher/gencode_coords/gencode.v33.5ss.fasta
```


However, I am not a big fan of the output format, because we lost the genomic coordinate, and will make downstream analysis hard:
```
CCAGTAAGT       9.09
GAGGTGAGA       7.66
CTGCTCAGT       -1.67
GAGCACTGG       -13.87
CCAGTAAGT       9.09
CTTGTGAGT       7.15
TAGGCAAGC       1.14
GAAGTTCAC       -12.10
GAAGAAATG       -7.27
GTGAGCGTG       -27.71
```

Also, sequences with 'N' will crash the program :)
```
# this crashes maxentscan
>chr4:9272911-9272920(+)
AGATCNNNN
```

## So I filtered sequences with N, and did a bit of wrangling
```
# find unique 5ss sequences without N
unique_5ss=df5.loc[~df5['seq'].str.contains('N'),'seq'].unique()

# write to file
import os
with open('/home/hsher/gencode_coords/unique_5ss.txt', 'w') as f:
    for seq in unique_5ss:
        f.write(seq+'\n')
```

Then feed to maxentscan
```
maxentscan_score5.pl /home/hsher/gencode_coords/unique_5ss.txt > /home/hsher/gencode_coords/unique_5ss.maxentscore
```

read the file back to python pandas dataframe and map to the original dataframe with genome coordinates

```
score5 = pd.read_csv('/home/hsher/gencode_coords/unique_5ss.maxentscore', sep = '\t', index_col = 0, names= ['score'])
df5['maxentscore']=df5['seq'].map(score5['score'])
```

# Final output

|    | chrom   |   start |   end | strand   | transcript_id     | gene_id           | seq       |   maxentscore |
|---:|:--------|--------:|------:|:---------|:------------------|:------------------|:----------|--------------:|
|  0 | chr1    |   12224 | 12233 | +        | ENST00000456328.2 | ENSG00000223972.5 | CCAGTAAGT |          9.09 |
|  1 | chr1    |   12718 | 12727 | +        | ENST00000456328.2 | ENSG00000223972.5 | GAGGTGAGA |          7.66 |
|  2 | chr1    |   14406 | 14415 | +        | ENST00000456328.2 | ENSG00000223972.5 | CTGCTCAGT |         -1.67 |
|  3 | chr1    |   12054 | 12063 | +        | ENST00000450305.2 | ENSG00000223972.5 | GAGCACTGG |        -13.87 |
|  4 | chr1    |   12224 | 12233 | +        | ENST00000450305.2 | ENSG00000223972.5 | CCAGTAAGT |          9.09 |
