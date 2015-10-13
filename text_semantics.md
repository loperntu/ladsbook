# 文本統計與語意表徵


* 文本解析，不管基於何種目的，在第一個層次大概不脫離 **描述、比較、分類** 工作。
* 為了達到更進一步的文本「語意」訊息，常常需要對於文本進行**形式表徵處理 **(representation)。在 (以前的) 語言學中最常利用**邏輯**，最近則利用**向量**。
* 這個步驟在機器學習的脈絡，常當成是 **特徵提取與降維** (feature extraction/dimensions reduction) 的步驟。




## 文本統計 

* 一般討論文本解析時所涉及到的統計技術，主要是 **描述分析** (descriptive analysis) 與 **推論分析** (predictive analysis)。
    * 描述統計處理文本的表層量化資訊、關聯與分佈。
    * 推論統計則涉及影響因素、假說的顯著與否，推論的信心等。


* 法國的資料分析傳統 (`Textometrie`，最近改稱 `Lexicometrie`) 與歐洲的量化語言學 (`quantatitive linguistics`) 則更強調**多變量的統計技術**，與語言法則的分佈 (Lebart et al. 1998) (<http://textometrie.ens-lyon.fr/?lang=en>)。主張比較全域的計量觀察。

```
 R 的相關參考套件 `koRpus`, `qdap`,`quanteda`,`languageR`,`zipfR` `textometry` 等等。
```

先從一般的文本統計開始

### 各種單位的頻率
* feature tokens and types
* feature n-grams

```{r}
library(ngramr)
library(ggplot2)
lines <- ngrami(c("line chart", "line graph"), 
    year_start = 1913)
ggplot(lines, aes(Year, Frequency, colour = Phrase)) + 
    theme_minimal() +
    geom_line(lwd = 1)
```



### 詞彙的變異量度 Measures of Lexical Variety

* 詞彙豐富度 (vocabulary richness) 對於理解文本特性有一定的幫助，在文體風格偵測或文本難易度量度上也有應用。
* 最常用，但是很簡化的一種量度式子叫做 **TTR** (Type-Token Ratio):

$$
\frac{num.of.types}{num.of.tokens}
$$

* H. Baayen (大神要拜) 提出了一個 $$P$$ measure。



### TF-IDF

* `tf-idf` (term frequency - inverse document frequency) 是從 Information Retrieval 的領域發展出來的常用「特徵」，用來表示一個語詞對於文集中的一份文件的重要性。`tf` 是詞頻，`idf` 是逆向文件頻率。


## Global dimenstions of text








---
### 文本多變量分析的降維
#### Factor analysis

- 統計學的因子分析 Factor analysis 可以用來 reducing the number of words in a set of documents to a more manageable level. 

> Factors analysis finds communalities in questions or other items, including the way text appears in documents. Factors can capture groups of questions that reflect some underlying idea, or groups of words that tend to appear together.(Stuhl, 2015)






## 文本語意表徵 (represention)




---
### 邏輯語意




### 分佈語意 

- distributional semantics：語意的向量表達

語意的向量空間模式 (Vector Space Model，VSM) 在 IR/text mining 領域中應用廣泛。



> Treating words as vectors means that we are ignoring the order of the words and the meanings that they might take from the words around them. This may seem like a great deal to disregard, but in the more advanced forms of analysis, and in particular predictive analytical methods, the ways words are present (and absent) alone can give us a great deal of information, and allow us to build powerful models that can forecast or predict liking, preference and even behaviour.(Stuhl, 2015)


## `word2vector` 


`tmcn.word2vec`: R interface to word2vec
