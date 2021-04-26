---
layout: post
title:  "為什麼我愛生物資訊"
description: Why do I fall in love in Bioinforamtics? 
date:   2019-01-31
tags: [Bioinformatics, diary]
category: algorithm
tagline: 
---

People asked me all the time - **"As a medical student, why do you do bioinformatics?"** They often started guessing before I had my answer. "Ah! I know, you must be a programming geek!" or "You must hate experimental biology!" In fact, when I first stepped into research, I did not even know bioinformatics exist. I always had a hard time learning to code, and drown in those ugly equations for hundreds of nights. The only thing that bioinformatics appeals to me, is - **It seems to be the only way towards a cell in silico (in computer)**.

不管是在申請入學、還是 PGY 面試，或只是一般的聊天，都常常有人問我：「你是個醫學生，為什麼會想說要做生物資訊的專題？」常常別人的猜測是：「因為你很喜歡寫程式？」「因為你討厭做實驗？」其實剛開始做研究的我，既不是一開始就做生物資訊，也不知道世界上還有這個東西；我一點也不喜歡寫程式和算數學，但我會進到這個領域，是因為它能回答我的問題－這個問題是傳統的生物研究無法回答的—我想要在電腦裡造一顆細胞。

As a medical student, I had to memorize lots of stuffs, From pathways, pathophysiologies, to symptoms that seems to arise from a cascade of events from thousands of cells. However, even with all those knowledges, there are still lots of diseases we cannot explain, or prevent, not to say, treat. I always love the complexity of a cell. I love how those proteins "talk" to each other, without a word, but still intricately organize thousands of processes. This complexity is the gap between tons of researches and diseases. If we can model them, as a cell in silico, then, I can travel inside the cell, exploring the unresolved, and bring the gaps together. Moreover, if I had to go to medschool again, I hope I can spend less time using my brain as a database.

一顆電腦裡的細胞的想法，來自於課堂一千萬條需要背誦的生物知識—生化、病理學、到真正的疾病，複雜又精緻得讓人著迷，但要背起來考試，十分討厭。更討厭的是就算知道那麼「多」，許多疾病的發生還是無法解釋、更別說是治癒。如果電腦裡有著一顆細胞，可以把所有資訊都整合起來，包含序列、結構、還有我們所知的一切 ，然後我們想知道什麼，就用那台電腦模擬，就可以不用考試了！而且，我一直想要去細胞裡旅行，所以這顆細胞可以變成線上遊戲，然後我就可以進去玩了！

Those crazy thoughts gradually leads me onto the road of bioinformatics.
就是這種很神經病的想法，讓我慢慢走上這條路。

------
An in silico cells stayed as a thought without action. I had no idea where to start. I tried learning Linux and Python online. But as a beginner, it is hard to imagine how these syntax and commands could eventually lead to an in silico cell. I'm not very patient, so I gave up. 

有這個想法之後，它就惡狠狠的只停留在「一個想法」的階段，我實在不知道這麼大一個東西要從哪裡開始阿！我曾經嘗試線上學習 Python 和 Linux，但是做為一個初心者，實在很難想像這些生硬的指令怎麼樣會堆疊成一個細胞。我是一個很急躁的人，不久便放棄了這個計劃。

I continued experimental work - designing a diagnostic PCR primer for antibiotic resistant genes. To find a unique probe that hybridize to the gene of interest, but not to other DNAs, I had to repetitively query NCBI database and a website called primer 3 - by hand! I wasn't patient, again, and really hated the repetitve work. So I enrolled in a programming course, feeling determined. 

於是我就繼續當時在分子生物實驗室的實驗－設計並且測試能偵測抗藥性基因的引子。要設計具有專一性的引子，我需要不停地查詢 NCBI 的資料庫，以及一個名為 Primer 3 的網頁。現在回想起來覺得十分不可思議，但是當時一百條的序列，我的確是手動的複製貼上，再把結果貼回 excel 表格裏頭。我是一個急躁，且超級討厭重複工作的人，於是我下定決心，上了一堂醫資所的程式設計課，目標就是要自動化重複的工作。


Although I did not successfully automate anything in the end, my advisor soon discovered that I like keyboards more than pipettes. So he put me on a project he had in mind for long - predicting beta-lactamase activity from sequences. A senior in lab who had a background in engineering, pointed me to a field called "Machine Learning". It sounded just like black magic. I used to think, computers do what I told them to do. I will have them loop 1000 times. So in order to model an enzyme, I will first construct atoms, to amino acids, then to the whole protein. Given the biochemical parameters and equtaions, I would automate all the calculations. But what if I don't know all the exact parameters? It turns out the computer can learn some rules that we human's don't know. And those rules can work. The exposure to machine learning completely changed my thoughts on what computers can do. It seemed, an in silico cell is possible.

上完這堂課，我最後還是沒有成功做出我要的東西。回想起來，我根本學得不好，Object-oriented programming 其實就有點聽不懂，也自然不知道要如何使用別人做好的套件。但即使我學的很好，隨後我也發現，上完一堂課，跟把東西實踐在研究之中，是很有差距的事。吳瑞裕老師發現比起持著自動滴管，我似乎更喜歡跟電腦胡搞瞎搞。於是他讓我加入實驗室的另一個計畫－由蛋白質序列，預測活性。當時實驗室電機背景的黃胤凱學長，跟我介紹了機器學習，這個名詞聽起來就像是黑魔法。於是我的工作，就是把他跟老師得出的結論，翻譯成 matlab 語言，回家以後就看看 Andrew Ng 的機器學習影片，寫寫作業。學習機器學習，是一個很大的轉捩點－以前我總覺得，要模擬一顆細胞，必須從模擬一顆原子開始，逐漸堆積到生物化學的等級，但問題是，其中許多參數是未知、甚至無法測量。機器學習，讓我看到一點契機，雖然電腦不懂蛋白質在搞什麼，但是他可以學會一些人類也不知道的規則，用來預測我們想知道的結果。雖然並不知道確切要如何執行，但對於電腦裡的細胞，我又開始滿懷希望。

------

To become a machine learning expert - as the naive undergrad student - I need more hands-on experience, and more advising from people with a computing background. Thus, I enrolled in a class to meet more experts in the field. In the class, I proposed to do a parasite ovum classifier as the project, as that is what an usual 3rd year medical student would need to memerise for his/her exam. Dr. Chiu advised me not to do image processing at the first try, since those math are too sophisticated. So instead, we shoot for a classifier for pathologic heart sounds.

我經歷一段機器學習的狂熱時期，當時的我決定，若要專精機器學習，那我需要更多經驗，以及電資領域的更多指導。於是，在一堂機器學習的實體課中，同時困擾於寄生蟲跑台，我提出想要做一個蟲卵照片分類器。當時邱泓文老師建議我，一開始做數學不要那麼重的東西。於是最後，我們決定從心音的分類開始－電腦聽聲音，告訴我有病還是沒病。

He was right. Even with 1 dimensional waveforms, Neither can I understand how Fast Fourier Transform works, nor can I understand Viterbi Algorithm for audio segmentation. I could only had a rough intuition what those "functions" are outputting. Dr. Chiu was extemely patient. He drew a lot of diagrams explaining how features can be extracted. All I do is to translate his language into matlab code, without not knowing what happened inside the built in functions.

他說的沒錯，我的數學真的很爛，台灣的醫學院是高中畢業就直接就讀，大多也不會琢磨太多在基礎科學上。即使是一維的波型，我還是很難了解傅立葉轉換到底怎麼成功的，也不了解大會提供的 Viterbi Algorithm 是如何把心音的錄音切出周期來，我靠著邱老師耐心的講解，大略了解每一個函式會吐出什麼東西，然後我把他吐出來的數字，用 matlab 串一串，餵進一個短短淺淺的 neural network 裡面。


For the first time, I slaved my computer to complete something without an explicit rule. I attended the first conference ever with our modest performing model. 

這是我第一次奴役我的電腦，做一些沒有明顯規則的事情。

------
If Fourier transform can turn sounds into numbers for models to learn, then what is the appropriate "transform" for sequences and chemical structures? I wanted to get back to the original sequence to activity project, but something is still missing. I figured that other professors in the Graduate Institute of Bioinformatics at my school, might have an answer. Ideally, this must be someone who has worked with bacterial genomes computationally. And here I found Dr. Yu-Wei Wu. To be honest, at that time, I didn't even know what metagenomics is. Not to say understand what his paper: MaxBin does. After browsing his list of publication, I realized there's nothing I understand. This is good. This means I can learn lots of new things from him, although I wasn't sure what it is.

有了一個 machine learning 的小小期末報告，我開始想如果聲音是 Fourier transform 可以變成數字，那麼序列呢？化學結構呢？我那時就想，真正做生物資訊的人，應該會知道吧！就算查到了也有看沒有懂，所以我就找到了吳育瑋老師。那時候其實根本看不懂吳老師的研究在做什麼－一點也看不懂，但是因為完全看不懂，所以心裡就想應該可以跟他學到很多新的東西，雖然我還是不知道那個我想要學的東西到底是什麼。

We started our discussion from how to group genes together and create a binary vector. He suggested me to put together a proposal for the MoST student grant. Every week he introduced me to 1 topic in bioinformatics, such as alignment, Hidden markov model and de Brujin graphs at a high level, while I presented my naive results from feeding one prebuilt softwares to another. I tried reading many textbooks in bioinformatics algorithms. But those books were very hard to understand. 



Dr. Wu was tremendously patient, he started by giving me clear guidance On our first project, pan-genomic predicting of resistance, he 

With hands-on experience, I learned how to use Linux, and my programming skills reached another level (from level -1 to level 0). Problems encountered in research motivated me to read more on specific topics. As I read more, gradually can I understand more (from 5% to 10%). I started to imitate methods written on paper. , then gradually let me think more on my own.


跟他說～我在想要 predict 抗藥性，用所有的基因和藥物的結構，不知道要怎麼做ㄟ。然後就來來回回的討論，他先建議我看看 
k-mer，然後我也在慢慢的把別人做類似的事情的文章蒐集起來看過一遍，整理出別人還有用哪些 feature、模型、最好做到怎麼樣，然後我們要怎麼去做不一樣而且比別人更好，就這樣討論討論，把結論寫成一篇文章，這就是我的第一個大專生計劃。其實寫的時候，根本沒有把握可以做得出來，就只是一個大概的計畫吧，有很多細節和技能都是在後來才補上的。

在這個過程中，學了 python，還有怎麼在 linux 裡面   、multiprocessing，還有生物資訊的檔案們，等等。做到一半的時候老師靈光乍現，說想要用 pan-genome 這件事情來試看看，於是我們很快把文獻翻過一遍，確定沒人做過這件事，就做了。遇到很多困難，包含模型不怎麼樣，然後 mutation 這件事情要怎麼融合在這裡面之類的（因為 mutation 也很重要阿）問題，也碰壁很多次，譬如說化學結構的 feature 就是很長又很怪異，而且我們兩個人不是化學家，也不知道要怎麼去調校人家，最後只好果斷放棄。後來老師又靈光乍現說不然用 genetic algorithm 來試看看 feature selection 好了，結果就出現很好的結果，結果好是很好，可是當我們想要回頭解釋生物的時候，卻發現和已知的知識不符。

呀！建了一顆細胞，結果，和世界上真正的細胞很不一樣，這樣要怎麼說得過去呢？ Machine Learning 強大歸強大，但常常他跑出來的東西，我們也無法回朔 artificial neural network 在想些什麼，彷彿他自己建築了一個世界，表面跟地球一樣，可是裡頭運作的規則和我的世界完全是兩套，這樣他也無法幫我更了解世界或是細胞。要怎麼辦呢？

這時候，看到一篇論文，使用圖論發現了新的抗藥性基因。剛好在我們的 pan-genome 裡面，也有很多不知道在幹啥的基因，當下就有一種－這！就！是！我！要！的！於是，我把我們不知道的基因送進他們的網絡裡面，發現他們的網絡裡沒有我要的東西，所以我就很衝動的寫了第二個計畫，就是我要建我自己的網絡，我想到抗生素打中某個 node，然後死亡的訊息就這樣擴散開來，只有抗藥性的突變、或是新的基因（不知道從哪裡撿來的）、或是拷貝了兩份的基因，可以在網絡裡面擋住死亡的訊息，彷彿我們在偷窺 E.coli 裡面的事情對吧？這感覺越來越接近我心裡的細胞了。

在寫這個計畫，已經真的在所謂生物資訊的事情裡打滾一年，也知道自己的能力其實很有限，也預期到會吃很多苦、要學很多新東西，不過就是一股腦衝寫了就開始做了。痛苦是必然的（我現在就在裡面！好痛苦阿！），但是不知道為什麼想到細胞，再詭異的數學或是程式技能，我都願意學。

------

在這整個過程裡，有一些機會可以發表，也自然會看到別的人在幹啥，每次都是很大的刺激，特別是 ISMB 2018—生物資訊大年會。在那個會裡，我發現我活在自己研究的小世界，一點也不知道別人在幹麻。在那個會裡面，我發現現在除了 genome，RNA、RNA的修飾、二級結構、histone bind 在哪邊、甚至 DNA 堆疊起來成 chromsome 哪個區域靠近哪裡，有可能怎麼調控，都有巨量的資料和偵測的技術一直一直在發生，整本分子生物學的課本，都在某個角落有團隊在想辦法偵測和分析，他們分析腦細胞、血的細胞、各式各樣的細胞，連大便裡的細菌和代謝物都要拿出來一起看一看，甚至，可以做到一個一個細胞的解析度，甚至一個一個細胞一次看兩件事情（譬如說：RNA + 鬆鬆沒有被蛋白質纏住的地方），他們用這些資料，加上演算法、模型，去回答發育的問題、疾病的問題、植物的問題……等。我感覺，下個十年的生物，再也不是像以前一樣，以細胞和老鼠為主要的地方了。我覺得，下個十年，這些 sequencing and all kinds of high throughput assay，加上電腦和數學，要把整個醫學和生物都翻過一遍。Unbiased discovery，意即我們不再一個一個基因、一個一個蛋白去研究，我們可以一次看到細胞裡幾乎所有的某一類分子，甚至可以看到他的數量多或者是少；這樣的資訊會開啟很多可能性。

這讓我回朔到另一個要做電腦裡的細胞的理由—那就是生物體是極其複雜的，你看，pathway 傳的亂七八糟，每好幾個步驟就有精密的調控，要防止出包，這意謂的是每個「功能」、「表現型」都是由一大堆蛋白質和其他分子合作無間地完成，這種複雜度在傳統的 wet lab 實驗要去發現是極其辛苦的－假設已知有20個蛋白質，而3個合作才變出完整的功能，排列組合有多少種組合需要去嘗試呢？我不想算，但很多，對吧！而 unbiased discovery 正好可以一逞偷窺狂的欲望，一次很快的看光光，讓我們知道要去實驗 prove，要從哪裡開始好。接觸到這些新的科技，讓我更加確信生物資訊可以更好地回答我的問題－前提是我要能**掌握這些資料**。

這些資料很多，多到讓人用看得會很絕望，因此不能再倚賴這個基因「看起來在圖上面很重要」來挑東西，因此必須要學習用數字和算式來跟電腦表達自己想要的，讓他幫我看；這些資料有時候很亂，sequencing 訊號不好，讀出來的訊號是錯的、讀出來的片段是碎的，要怎麼挑、怎麼重組回去，每個都是問題；這些資料超大，使用不慎電腦就會昏死過去或是算到天荒地老都還沒算完，或是會有小白把硬碟塞爆，這些也都是問題。

而全部這些問題，都是生物資訊的問題。所以生物資訊這件事，從做一顆算更快的晶片、算更快的演算法、新的統計、機器學習，到一顆細胞和抗藥性的生物問題，全都包含在裡面。或許這也是為什麼我喜歡它的原因—永遠有更多可以去學，永遠都有很多創新的空間。

------

從一個神經病的想法走到這裡剛要進門，其實也不是說一開始就決定要走到這，也是一路撞牆撞到這裡還沒撞死所以在這。我想表達的是，完成一個目標，很少數的情形一個人可以從起始點就一直線的走到終點，繞來繞去，撞牆，回頭再來，這些都是很正常的。
至於為什麼會在這？我想這就是命吧～如果沒有碰到各式各樣能夠容忍甚至幫助瘋子的老師、學長姐、和同儕，也是很難找到這條路。這也意味著，尋找適合自己的夥伴以及懂得如何尋求幫助，也是繼續走下去非常關鍵的因素。
還有真的是夠喜歡這個問題，和這個領域！

很多人問我，要怎麼知道自己會不會喜歡研究、甚至是「生物資訊的研究」，其實**沒試過是不會知道的**。恰逢大專生季節，葉配一下，要怎麼知道會不會喜歡某個老師一起研究？那就把他的著作（挑幾篇近期重要的）好好看完，想像你要做這樣的東西，有興趣嗎？不排斥的話，就試看看吧。當然在看懂然後開始想像要怎麼做的時候，就會遭遇到很多困難，你樂意去克服嗎？enjoy 這個血淚的過程嗎？試試看，就會知道了！

至於要怎麼去克服生物人變成 BIOinformatics 的困難，下集待續！（如果還有下集的話。看我心情啦！）
