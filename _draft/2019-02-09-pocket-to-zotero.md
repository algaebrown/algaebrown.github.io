---
layout: post
title: converting pocket list to zotero
date: 2019-02-09
---
1. export pocket list to html from its website
2. extract the all `href` by:
```
sed -n 's/.*href="\([^"]*\).*/\1/p' FILENAME > OUTPUT_FILE
```
3. 
```
curl -s URL | grep prism.doi
```
