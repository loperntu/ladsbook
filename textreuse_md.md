# 重複文本偵測

- text reuse 可以用 [`textreuse`](https://github.com/ropensci/textreuse) 來練習。

```r
> library(textreuse)
> dir <- system.file("extdata/legal", package = "textreuse")
> corpus <- TextReuseCorpus(dir = dir, 
    meta = list(title = "Civil procedure"),
    tokenizer = tokenize_ngrams, n = 7)
```
```
> coprus
TextReuseCorpus
Number of documents: 3 
hash_func : hash_string 
title : Civil procedure 
tokenizer : tokenize_ngrams 
```


