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




