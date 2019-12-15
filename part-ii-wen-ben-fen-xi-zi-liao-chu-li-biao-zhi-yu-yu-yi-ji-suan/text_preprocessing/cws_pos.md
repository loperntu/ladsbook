# 自動分詞與詞類標記

## Tokenization

* The words taken from a block of text sometimes are called tokens, and the process of identifying the words is sometimes called tokenization.

```text
前述作法預設了 token 的「存在」，但是在中文與其他字詞邊界不明顯的語言，tokenization 變成了一個研究的主題。
```

* **中文分詞（斷詞）** Chinese word segmentation 可以看成是 tokenization 的一個特例，但是涉及更深一層的語言與認知互動。
* 中文分詞演算法從早期的 `最大匹配查找`一直到隨著巨量訓練語料庫出現後的各種`統計機器學習模式` \(e.g., Conditional Ramdom Field\) 已經有很大的進展。\(如果不管語言學的討論\)
* 主要面對的兩大問題是
  * 結構性的歧義消解
  * 新詞識別 

## Stemmatization

* 詞幹 \(stem\)
* 
```r
libray(SnowballC)
```

## 詞類自動標記 POS tagging

* 詞類是句法的概念。在文本解析的重要性上可以用 **named entity recognition** 來解釋。比方說， "the word general can be a job title as in the highest-ranking general, but in the general opinion it is not a job title. In the first example general is a noun, and in the second it is an adjective. If a part-of- speech tagger has already added these annotations, the named entity recognizer can use them to improve its precision."\(Wilcock, 2009\).
* 實作上， English part of speech tagging with`openNLP`\(which implements the Penn Treebank tag set.\) 

  See [http://www.ling.upenn.edu/courses/Fall\_2003/ling001/penn\_treebank\_pos.html](http://www.ling.upenn.edu/courses/Fall_2003/ling001/penn_treebank_pos.html).

```text
library(openNLP)
library(NLP)
library(XML)

inputDir <- "data/XMLAuthorCorpus"
files.v <- dir(path=inputDir, pattern=".*xml")

for(i in 1:length(files.v)){
    doc.object <- xmlTreeParse(file.path(inputDir, 
                  files.v[i]), useInternalNodes=TRUE)
    paras <- getNodeSet(doc.object,"/d:TEI/d:text/d:body//d:p",
                  c(d = "http://www.tei-c.org/ns/1.0")) 
    words <- as.String(paste(sapply(paras,xmlValue),
                collapse=" ")) 

# Need sentence and word tokens first
sent_token_annotator <- Maxent_Sent_Token_Annotator() 
word_token_annotator <- Maxent_Word_Token_Annotator() 

a2 <- annotate(words, list(sent_token_annotator,
                            word_token_annotator))

# now pos tags
pos_tag_annotator <- Maxent_POS_Tag_Annotator()
a3 <- annotate(words, pos_tag_annotator, a2)
a3w <- subset(a3, type == "word")
tags <- sapply(a3w$features, `[[`, "POS")
tagged_text <- paste(sprintf("%s/%s", words[a3w], tags),
                collapse=" ") 

write(tagged_text, paste("data/taggedCorpus/", files.v[i], ".txt", sep=""))
}
```

