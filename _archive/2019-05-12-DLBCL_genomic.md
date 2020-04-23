---
layout: post
title:  "When Bioinformatics meets lymphoma/leukemia: Genomics + DLBCL"
date:   2019-05-12
---

我在臨床病理科過得開心極了，因為我看到 Bioinformatics 和醫學一起發生的地方就是這裡。臨床病理科最大的業務之一就是幫忙診斷血液科的病，所以要看很多基因的東西，但即使到了現在，大部分的分子診斷都還是靠 Karyotyping、FISH、microarray在進行，Next generation sequencing 的東西要出場不是一件常見的事情，可能是考慮到價錢，也可能是沒有人可以分析等等。

我覺得 Sequencing 可以給我們的比這些傳統的方法多得很多，有這麼多沒有辦法回答的問題，秘密有可能就藏在裡面吧！所以我想要來看看 Genomics 會怎麼改變未來血液疾病的治療呢？

# 疾病：Diffuse Large B Cell Lymphoma
今天看的文章所關注的疾病叫做 Diffuse Large B Cell Lymphoma (DLBCL)，是最常見的一種 Lymphoma。DLBCL 在所有 Lymphoma 裡面不算是最壞的，大部分的人在經過標準治療－R-CHOP 以後都可以控制住，但是他們發現有一群病人特別容易復發，而且復發以後疾病就會變得很難控制。過去有人用基因的表現把 DLBCL 再分為兩群，叫 ABC-DLBCL 和 GCB-DLBCL，但即使這樣，還是沒辦法把病人按照後續的 outcome 做很好的分群。

# 為什麼要分群？
我覺得，如果可以分出一群很壞的 DLBCL，那麼或許我們可以出發尋找比 R-CHOP 還要更厲害的治療計畫，讓這一群人不用走到最後那一步。

# 用什麼資料分群？
這篇主要使用的是 Genomic data，就是 DNA 序列。他並不是把全基因體都定序，只有定 Whole exome，也就是會變出蛋白質的部分。不定全基因體的原因可能是因為太貴，也可能因為我們對不變成蛋白質的序列了解不多，所以定出來的東西不一定能分析出什麼。

# 怎麼分析 Genomic 的資料？

## Step 0: 處理定序的資料

### Quality control, filtering, mapping to reference genome

### 有些檢體泡過福馬林(!)

## Step 1: 找出造成 DLBCL 的壞壞基因

### 為什麼要這麼做？
如果假設我們把所有人的所有基因都對齊，找出不一樣的地方，用這些不同的地方來做分群，那麼會摻雜很多雜訊。因為人跟人本來就有很多不一樣的地方，有人吸空氣就會胖，有人吃一大堆也不會胖。我想說的是－**並不是每一個不同的地方，都和 DLBCL 有關係、都是壞壞基因**，所以我們必須要好好的挑出真的和 DLBCL 有關的基因們，再來做分群，這樣會比較棒。

### 要怎麼找？
很直覺的方法就是用動物或細胞，把某個基因變很多，或變不見，看看誰會得癌症。可是基因很多，變的方式很多，你可以把他完全變不見，也可以只變掉幾個點，這樣的話實驗永遠都做不完。所以我們必須要用電腦去找出「最有可能」的那些。

我覺得這篇文章的亮點之一就是他找基因的方式，讓我們來看看壞壞基因可能會有那些特徵：
1. 壞壞基因會擁有「後天的突變」，因為這些病人不是一出生就有 DLBCL。要找出那些突變是後天的，代表我們要和病人正常的組織比較。(To find somatic mutations)
2. 壞壞基因比其他基因擁有更多突變。(Cancer associated genes tend to have higher mutational frequencies)
3. 這些突變在蛋白 3D 結構上面會聚集在一起，因為 Sequence - Structure - Function/Phenotype。發生在重要位置的東西，對表現型會有重要的影響。

1. 找出後天的突變(Somatic mutation)，需要有正常組織配對。
可惜在這個研究中不是每個人都有拿到正常組織的檢體，在這樣的情況下他們逼不得已只好使用其他的正常檢體做比較，並且移除常見的先天變異(Germline mutation)。
2. 找出顯著較多突變的基因。
他們使用的工具叫 [MutSigCV](https://www.nature.com/articles/nature12213#methods-summary)，大意來說，因為每個人、每種癌症、每個 genome region 、基因的表現量都有不同的突變機率，這個 tool 在做的事就是讓不同人、不同癌症、不同 genomic region 有不同的背景突變率，藉此找出真正突變多的基因。
3. 找出在蛋白結構上的集中突變
他們使用的工具叫 [CLUMP](https://www.pnas.org/content/112/40/E5486.long#sec-14)，會找出每個 Protein 的突變 residue 彼此之間有多集中。距離有使用突變的頻率加權。至於多「集中」叫做集中？做這個 tool 的人產生了多筆「均勻突變」的假 data，並使用這筆假 data 也計算出 集中度，再用統計去找出顯著的值(FDR)。

看到這裡你可能覺得，都聽你說！搞不好找到的根本都是一堆垃圾。所以他們有對比之前已知的 tumor supressor gene, oncogene，也做了很多生物的討論。

### 壞壞基因的突變打哪來？
為什麼正常的 genome 不會累積這麼多突變？因為 cancer cell 裡面很多 DNA repair mechanism 壞掉、因為可能有特別多的 Reactive Oxygen Species，在 B cell lymphoma 中還有一個特別的叫做 Somatic hypermutation(SHM)，這些都是會讓突變率更高的。

每一種累積突變的方式都有他們喜歡的變法，可能跟其中的生物化學機轉有關，譬如說 AID (其中一種 SHM)就喜歡在某些 motif 做 deamination 之類的。[Signature Analyzer](https://www.nature.com/articles/ncomms9866)收集了 30 個 CLL genome，嘗試去解出這些 pattern。

其實我一開始很疑惑會什麼他們要做這樣的分析，就算知道某個壞壞基因是因為 somatic hypermutation 另一個是因為別的 mechanism 有什麼樣的幫助嗎？

### 壞壞基因不是只有突變
壞壞基因之所以壞，不只是因為單點的突變，還有可能是因為斷掉、染色體的重組、或是份數變多等等的。這篇相較於以前不同的就是他們囊括多種變異，而不只專注在點突變。至於要怎麼在碎片的資料中翻出這些變異、而且要告訴我們是只有一條染色體有變，還是兩條都變，或是三條都變(癌症的 karyotype 常常都怪怪的)，就要仰賴各種 variant calling tool。

## Step 2: 分群
資料處理通常是最麻煩然後無聊的步驟(但是很重要耶怎麼辦)，不過到這裡我們已經可以畫出一張超大表格了：

## Step 3: 分群

### 分群的方法

### 排出每一個分群的基因變壞順序

## Step 4: 根據分群預測存活

# 他們的發現

# 可能有的問題

# 我覺得很可惜的地方

# 應用到臨床的可能性