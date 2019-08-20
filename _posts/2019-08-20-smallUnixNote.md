---
layout: post
title:  "Some little Unix notes for myself"
date:   2019-08-20
---

1. When tab completion does not work
- maybe it's because you're using a different shell
- `echo $SHELL` to confirm
- 上次不知道為什麼預設的就是 sh 而不是我喜歡的 bash

2. Some computers don't eat `.bashrc`
- they might prefer `.bash_profile`
- add `source $HOME/.bashrc` to `.bash_profile` to make it work again

3. dos2unix
- 因為在 cluster 上 jupyter notebook 要 port forward 來 forward 去，所以學姐分享給我一份 shell script 是她寫來 forward 的東西
- 但是他把 shell script 傳到 email 寄給我，我 download 下來一直出現 syntax error
- 後來發現可能因為是他是 mac 我是 unix 的 shell 所以格式不同
- use `dos2unix` to fix the shell script

4. when you can't sudo
- 在 `make` 以前 先 `./configure --prefix $HOME/WHATEVER_YOU_WANT`
- [reference](https://unix.stackexchange.com/questions/149451/install-r-in-my-own-directory)

5. working on clusters 還在學 OTZ
- need to specify how much memory you want
- some very useful guide [here]('https://github.com/BIMSBbioinfo/intro2UnixandSGE/blob/master/sun_grid_engine_for_beginners/how_to_submit_a_job_using_qsub.md')
- 在 shell script 裡可以 `#$` 設定 qsub的參數
