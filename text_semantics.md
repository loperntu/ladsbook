# 文本語意與統計學


* 文本解析，不管基於何種目的，在第一個層次大概不脫離 **描述、比較、分類** 工作。
* 為了達到更進一步的文本「語意」訊息，常常需要對於文本進行**形式表徵處理 **(representation)。在 (以前的) 語言學中最常利用**邏輯**，最近則利用**向量**。




## 文本統計 

* 一般討論文本解析時所涉及到的統計技術，主要是 **描述分析** (descriptive analysis) 與 **推論分析** (predictive analysis)。
    * 描述統計處理文本的表層量化資訊、關聯與分佈。
    * 推論統計則涉及影響因素、假說的顯著與否，推論的信心等。


* 法國的資料分析傳統 (`Textometrie`，最近改稱 `Lexicometrie`) 與歐洲的量化語言學 (`quantatitive linguistics`) 則更強調**多變量的統計技術**，與語言法則的分佈 (Lebart et al. 1998) (<http://textometrie.ens-lyon.fr/?lang=en>)。

```
 R 的相關參考套件 `koRpus`, `qdap`,`quanteda`,`languageR` 等等。
```

先從一般的文本統計開始
## 詞頻計量與分佈




(Baayen) 





---



### ngram
...

### 文本多變量分析的降維
...
#### Factor analysis

- 統計學的因子分析 Factor analysis 可以用來 reducing the number of words in a set of documents to a more manageable level. 

> Factors analysis finds communalities in questions or other items, including the way text appears in documents. Factors can capture groups of questions that reflect some underlying idea, or groups of words that tend to appear together.(Stuhl, 2015)











---
## 邏輯語意




## 分佈語意 

- distributional semantics：語意的向量表達

語意的向量空間模式 (Vector Space Model，VSM) 在 IR/text mining 領域中應用廣泛。



> Treating words as vectors means that we are ignoring the order of the words and the meanings that they might take from the words around them. This may seem like a great deal to disregard, but in the more advanced forms of analysis, and in particular predictive analytical methods, the ways words are present (and absent) alone can give us a great deal of information, and allow us to build powerful models that can forecast or predict liking, preference and even behaviour.(Stuhl, 2015)


## `word2vector` 