---
layout: post
title:  "How to read a paper critically?"
date:   2019-02-03
---

相信是台灣學生的人，最討厭的就是聽到：「『現在的』台灣學生都...」為開頭的造句，其中最常被婊的點就是：**不會問問題**。的確，我們的確不是那麼愛問問題，我自己也發現自己常常「沒有問題」。對於研究或知識「沒有問題」，有時暗示的是我就**默默接受作者所陳述的**，而沒有仔細思考實驗—結果—解讀過程裡的環節，這樣的壞處是：不會提出問題，就難以有新的發現。

針對自己「不會問問題」的問題（饒舌ㄇ），我覺得有以下可能的原因：

1. 根本就看不懂或聽不懂
2. 看懂然後就接受，no critical thinking
3. 不好意思問

1 不是今天想要來分享的問題，3 只要加厚臉皮就好了。今天只想要討論 2: How to think CRITICALLY about a paper?

> You just need to think critically!


這是一句幹話，as if people are either born to think critically, or they will just **spontaneously** know how to someday. 

在 2018 年旁聽一堂課叫做癌症生物資訊學，有一半的時間，都是在 paper reading，老師開**電**的時候，有一句話我印象非常深刻:

> When you read a paper, you need to think of it as if you are the one writing the paper. Or imagine if you want to reproduce the result someday. (你在讀的時候，要把自己想成要寫一篇類似的 paper，或是要重複他們的結果)

過了好一陣子淹死在 paper 裡的日子裡以後，我好像，我是說「好像」知道他想表達啥了：

> 如果你今天要回答**同一個問題**，你會怎麼做呢？

所以，今天如果決定要精讀一篇，在看完 Abstract/Introduction 以後，不妨停下來想一想，這個問題**是我，我會怎麼回答**。我會想要做 X 實驗，預期得到 A 結果。進入 Method 的時候，就看看作者使用的 Y 方法，和自己的 X 有什麼不同，X 與 Y 的優缺點各是什麼？為什麼作者想要選用 Y 而不是 X？

這時候，恭喜你就已經提出了一個問題了：為什麼用 Y 不是 X？在回答這個問題的過程中，原本被動的閱讀就會轉為主動，因為會開始在內文尋找原因；有時，不一定會在內文寫，因為有些根本就是背景知識。這時候，能查則查，查不到則提出討論。透過這篇文獻的閱讀，已經可以學到 X 和 Y 的性質。

在看到實驗的結果，試著想像 raw data 是什麼？要做統計、機器學習，或使用任何一種廣義的數學的時候，**是我我要用什麼模型**、**我會怎麼視覺化結果**。看到結果，**我的結果是什麼？**，**這個結果會引發我再進一步去問出哪些問題？**接著就是比較自己和作者所用的，一邊補足知識，一邊思考作者的方法與結果的缺陷與亮點（這樣常常會容易的呼之欲出）。

在我閱讀我比較不熟悉的領域論文的時候，這個方法碰到的問題就是我根本想不到別的作法！這個問題，只能透過平常多讀、多看別的領域重要的 review article 來補足了。也就是回到的 1 的問題。

> 讀 paper 同時增進自己實力的方法，就是不停的電自己、找人討論、補足知識。
我想這是 **How** to read a paper critically 我目前找到最簡單的方法了。

## Case Study: Machine Learning Detects Pan-cancer Ras Pathway Activation in The Cancer Genome Atlas, Way et. al, Cell Reports, April 2018
[Full Text Link](https://www.cell.com/cell-reports/fulltext/S2211-1247(18)30389-9?_returnURL=https%3A%2F%2Flinkinghub.elsevier.com%2Fretrieve%2Fpii%2FS2211124718303899%3Fshowall%3Dtrue)

1. 這篇論文想要回答的問題是啥？
2. 你想要怎麼回答？（用什麼 Dataset，用什麼模型？）
3. 作者使用 Elastic Net Regression（掉在 supervised learning裡面）。Supervised Learning 這麼多種，他為什麼不用 Deep Learning, SVM?
4. Elastic Net Regression 是什麼？為什麼不用 Lasso and Ridge？
5. Training/Test 的 Y(答案，Ras pathway activity)是什麼？是你會用什麼？
6. 作者定義 Y(答案) 使用一些典型的 Oncogene/Supressor gene copy number change and known function-altering mutation? 為什麼這些可以代表 Ras pathway? 這樣有沒有什麼樣的問題？
7. X(input) 使用 gene expression，為什麼用？有沒有什麼潛在的毛病？
8. 作者怎麼 evaluate 他的 model？為什麼除了 TPR v.s. FPR 還有一個 Precision-Recall curve? 這兩個有什麼不同功用嗎？有做實驗或是用 external dataset 去驗證嗎？如果要做實驗/external dataset 的話要怎麼設計呢？
9. 作者怎麼去解讀他去 learn 的 feature？（這題已經回答了 3.)
10. 為什麼選用 Pan-cancer 去做 Dataset，而不是一個一個 cancer？他在結果中也有比較一個一個 cancer 和 pan-cancer 的結果，根據這個結果，可以說些什麼故事？
11. 回到問題 1，作者的答案是什麼？你的答案跟他一樣嗎？

還記得那時候我看完這篇是一個精疲力竭，但是同時也學到很多。這裡面很多問題其實都沒有答案，有很多可以去討論的。而有關 Machine Learning 的問題是花去我最多時間去想的，這一篇我最大的收穫是去重新複習 Regularization，ridge/lasso/elastic net 的性質，這也是其中最痛苦的部份。針對學習廣義的數學的困擾，我應該會再寫另一篇來分享～看我心情啦。

# 拓展到其他事情上面

另外一個被婊不會問問題的時候，就是臨床學習啦！其實道理也是一樣的！而且臨床的「問題」可以簡要分成兩大類：怎麼診斷和治療。
所以看到一個病人，譬如說：52歲阿伯胸悶呼吸喘。
1. 診斷：Hx、PE、Lab、Image 我想做什麼？學長做了哪些？有什麼不一樣？
2. 治療：同理

# 後記：為什麼會忽然想寫這個？
其實這只是我自己的一點小小的經驗，而且在 Bioinformatics、科研這條路上尚算資淺，在幾個月前初步有這些想法時，不寫的原因是覺得自己沒資格寫這種東西！！但是後來，我覺得正是因為我不會 → 學會一點的過程是最近，我所分享的東西可能比較容易讓有這些需求的人理解吧！畢竟，段數太高的人，說的話常常都很難理解，譬如說 ** you just need to think critically!** 這種已經完全內化在他裡面，沒辦法拆解成步驟了！

你也有什麼撇步可以跟我們分享嗎？一起加油成為 critical thinker 吧！:)







