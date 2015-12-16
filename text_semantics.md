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

- `tf-idf` (term frequency - inverse document frequency) 是從 Information Retrieval 的領域發展出來的常用「特徵」，用來表示一個語詞對於文集中的一份文件的重要性。`tf` 是詞頻，`idf` 是逆向文件頻率。

$$
tf - idf=f_{ij} * log\left(\frac{n}{d_j}\right)
$$


- 假設一個文件有 10,000 個詞，其中「好」出現了 300 次。那麼「好」的 $$tf = \frac{300}{1000}=0.03$$。假定我們總共有 1,000 份文件，「好」出現在其中的 10 份。那麼 「好」的 $$idf = log(\frac{1000}{10})=2$$。最後得出 `tf-idf` $$= 0.03 * 2 = 0.06 $$

## Global dimenstions of text


---
- `tm` 套件提供一個將文本轉成 **文詞矩陣 (document-term matrix)** 的函式，方便後續各種計量分析與模式的處理。


```r
dtm <- DocumentTermMatrix(docs)
# convert rownames to filenames
rownames(dtm) <- filenames
# collapse matrix by summing over columns
freq <- colSums(as.matrix(dtm))
# length should be total number of terms
length(freq)
# create sort order (descending)
ord <- order(freq, decreasing=TRUE)
# List all terms in decreasing order of freq and write to disk
freq[ord]
write.csv(freq[ord],"word_freq.csv")
```







---
### 文本多變量分析的降維
#### Factor analysis

- 統計學的因子分析 Factor analysis 可以用來 reducing the number of words in a set of documents to a more manageable level. 

> Factors analysis finds communalities in questions or other items, including the way text appears in documents. Factors can capture groups of questions that reflect some underlying idea, or groups of words that tend to appear together.(Stuhl, 2015)






## 文本語意表徵 
semantic representation

對於語意表徵有許多想法，比方說`邏輯`、`向量`、`網路`或晚近的`量子語意`。

---
### 邏輯語意




### 分佈語意 
語意的向量表達


- 目前在認知科學、資訊檢索或計算語意學中，最常應用的是將詞義 (word meaning) 表達成在高維的語意空間中的向量 (vectors in a   high-dimensional semantic space) (Landauer et al, 2007)。
- 這種語意表徵式，通常稱為向量空間模式 (Vector Space Model) ，或分佈語意模式 (Distributional Semantic Models, DSM) 在 IR/text mining 領域中應用廣泛。

In  such  a  semantic  space,  words  that  are  similar  in
meaning will tend to be in similar areas of the space. Such
models are referred to as
Vector Semantic Models
or





- 


- 可以用 `LSAfun` (An R package for computations based on Latent Semantic Analysis) 來做入門練習。此套件使用了預先準備好了的 LSA 空間，提供以下功能 (Günther F et al. 2015)。如果要自行實際建構 LSA 空間，可使用 `lsa` 或其他套件。

    - Similarity Computations between words, word lists, and documents; 
    - Neighborhood Computations, such as obtaining a word's or document's most similar words, 
    - plotting such a neighborhood, as well as similarity structures for any word lists, in a two- or three-dimensional approximation using Multidimensional Scaling, 
    - Applied Functions, such as computing the coherence of a text, answering multiple choice questions and producing generic text summaries; and 
    - Composition Methods for obtaining vector representations for two-word phrases. 










> Treating words as vectors means that we are ignoring the order of the words and the meanings that they might take from the words around them. This may seem like a great deal to disregard, but in the more advanced forms of analysis, and in particular predictive analytical methods, the ways words are present (and absent) alone can give us a great deal of information, and allow us to build powerful models that can forecast or predict liking, preference and even behaviour.(Stuhl, 2015)


## `word2vector` 

`tmcn.word2vec`: R interface to word2vec








