# 文本語意與統計學


* 文本解析，不管基於何種目的，在第一個層次大概不脫離 **描述、比較、分類**工作。




## 文本統計 

一般討論文本解析時所涉及到的統計技術，主要是 **描述分析** (descriptive analysis) 與 **推論分析** (predictive analysis)。

法國的資料分析傳統 (`Textometrie`，最近改稱 `Lexicometrie`) 與歐洲的量化語言學 (`quantatitive linguistics`) 則更強調**多變量的統計技術**，與語言法則的分佈 (Lebart et al. 1998) (<http://textometrie.ens-lyon.fr/?lang=en>)。

> - Descriptive methods show patterns and similarities but not effects on any outcome or behaviour. 
> - Predictive methods are required to show what effects are.



> Descriptive analytics makes up a very large part of text analytics. These methods show broad patterns, count items, or shows what is near another item. This form of analytics does not show what influences an outcome and by how much. The business of predictive analytics, however, is doing just that – showing what leads to a change in some target variable, such as liking, preference or behaviour, and how strong those influences are likely to be.

* 參考套件 `koRpus`, `qdap` 


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