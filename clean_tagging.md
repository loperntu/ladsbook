# 文本清理與自動訊息標注



## 文本清理
Cleaning up texts (Stuhl, 2105): Steps


- stop words (such as the, of, and, a, to, and so on) must be removed. These words do not contain any meanings that will help the analysis, and they can occur so frequently that that they swamp all the words that do have meaning.
- words must be made regular, by a process sometimes called **stemming**.
- Spelling errors need to be corrected using a dictionary. Plurals must be singularized. Idiomatic expressions need to be resolved. Tenses need to be made uniform so that the same word does not reappear many times with minor variations.
– **Lemmatization** is a special type of stemming that regularizes words while trying to figure out their part of speech. How words get reduced to a stem may differ depending on how the words are used. For instance, the noun ‘moped’ should not be stemmed into the form ‘mope’, while the verb ‘moped’ should.
- With text that people have typed in themselves online, we will need to remove all the nonsensical or obviously non-useful comments, such as ‘nothing’ or ‘what?’ or ‘no comment’ or ‘fjjfjfjfjfjfj’, that we find appearing in commentary. Phrases such as these make up a surprisingly large percentage of online responses.

```
噪訊的定義，取決於妳的研究目的。
```

- Depending on the stemming program, we may also look for word pairs or larger groups of words (eg ‘not good’ or ‘not bad’ or ‘South Gas Works’). We will discuss this process directly below.
- Programs may remove infrequent words. Some have a setting you can adjust to screen words based on how often they appear. For instance, the 100 or so words that made up the entire table excerpted in Figure 2.1 all appeared in at least 1 per cent of all individual documents. Eliminating infrequent words helps reduce the overall analytical burden considerably.


## Tokenization


```
前述作法預設了 token 的「存在」，但是在中文與其他字詞邊界不明顯的語言，tokenization 變成了一個研究的主題。
```



- The words taken from a block of text sometimes are called tokens, and the process of identifying the words is sometimes called tokenization.


## 詞類自動標記 POS tagging


- English part of speech tagging with`openNLP`(which implements the Penn Treebank tag set.) 
See <http://www.ling.upenn.edu/courses/Fall_2003/ling001/penn_treebank_pos.html>.



```{r}
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
collapse=" ")) # Need sentence and word tokens first
sent_token_annotator <- Maxent_Sent_Token_Annotator() word_token_annotator <- Maxent_Word_Token_Annotator() a2 <- annotate(words, list(sent_token_annotator,
                               word_token_annotator))
# now pos tags
pos_tag_annotator <- Maxent_POS_Tag_Annotator()
a3 <- annotate(words, pos_tag_annotator, a2)
a3w <- subset(a3, type == "word")
tags <- sapply(a3w$features, `[[`, "POS")
tagged_text <- paste(sprintf("%s/%s", words[a3w], tags),
collapse=" ") write(tagged_text, paste("data/taggedCorpus/",
files.v[i], ".txt", sep=""))
}

```







