# 文本統計與語意表徵

* 文本解析，不管基於何種目的，在第一個層次大概不脫離 **描述、比較、分類** 工作。
* 為了達到更進一步的文本「語意」訊息，常常需要對於文本進行**形式表徵處理 **\(representation\)。在 \(以前的\) 語言學中最常利用**邏輯**，最近則利用**向量**。
* 這個步驟在機器學習的脈絡，常當成是 **特徵提取與降維** \(feature extraction/dimensions reduction\) 的步驟。

## 文本統計

* 一般討論文本解析時所涉及到的統計技術，主要是 **描述分析** \(descriptive analysis\) 與 **推論分析** \(predictive analysis\)。
  * 描述統計處理文本的表層量化資訊、關聯與分佈。
  * 推論統計則涉及影響因素、假說的顯著與否，推論的信心等。

* 法國的資料分析傳統 \(`Textometrie`，最近改稱 `Lexicometrie`\) 與歐洲的量化語言學 \(`quantatitive linguistics`\) 則更強調**多變量的統計技術**，與語言法則的分佈 \(Lebart et al. 1998\) \([http://textometrie.ens-lyon.fr/?lang=en](http://textometrie.ens-lyon.fr/?lang=en)\)。主張比較全域的計量觀察。

     R 的相關參考套件 `koRpus`, `qdap`,`quanteda`,`languageR`,`zipfR` `textometry` 等等。

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

* 詞彙豐富度 \(vocabulary richness\) 對於理解文本特性有一定的幫助，在文體風格偵測或文本難易度量度上也有應用。
* 最常用，但是很簡化的一種量度式子叫做 **TTR** \(Type-Token Ratio\):


$$
\frac{num.of.types}{num.of.tokens}
$$


* H. Baayen \(大神要拜\) 提出了一個 $$P$$ measure。

### TF-IDF

* `tf-idf` \(term frequency - inverse document frequency\) 是從 Information Retrieval 的領域發展出來的常用「特徵」，用來表示一個語詞對於文集中的一份文件的重要性。`tf` 是詞頻，`idf` 是逆向文件頻率。


$$
tf - idf=f_{ij} * log\left(\frac{n}{d_j}\right)
$$


* 假設一個文件有 10,000 個詞，其中「好」出現了 300 次。那麼「好」的 $$tf = \frac{300}{1000}=0.03$$。假定我們總共有 1,000 份文件，「好」出現在其中的 10 份。那麼 「好」的 $$idf = log(\frac{1000}{10})=2$$。最後得出 `tf-idf` $$= 0.03 * 2 = 0.06 $$

## Global dimenstions of text

---

### 文本多變量分析的降維

#### Factor analysis

* 統計學的因子分析 Factor analysis 可以用來 reducing the number of words in a set of documents to a more manageable level. 

> Factors analysis finds communalities in questions or other items, including the way text appears in documents. Factors can capture groups of questions that reflect some underlying idea, or groups of words that tend to appear together.\(Stuhl, 2015\)

## 

---

## 文本語意表徵

* Different **semantic representation** strongly influence the designs and selection of machine learning methods.

* 對於語意表徵有許多想法，比方說`邏輯`、`向量`、`網路`或晚近的`量子語意`。

---

### 邏輯語意

### 分佈語意

語意的向量表達

* 目前在認知科學、資訊檢索或計算語意學中，最常應用的是將詞義 \(word meaning\) 表達成在高維的語意空間中的向量 \(vectors in a   high-dimensional semantic space\) \(Landauer et al, 2007\)。
* 這種語意表徵式，通常稱為**向量空間模式** \(Vector Space Model\) ，或**分佈語意模式** \(Distributional Semantic Models, DSM\)。在計算與模擬詞義距離時有其方便。
* 模型的假說是：_distributional hypothesis_ \(Sahlgren,
  2008; Harris,1954\), 亦即近義詞出現的語境也接近。 

潛在語意分析 \(Latent Semantic Analysis, LSA\) 算是較被延伸與使用的一種分佈語意模式。演算法步驟大概是這樣：

\[1\]. 從文本語料庫建立一個矩陣 **tdm** \(term-by-document frequency matrix\)。 其中每一列 \(row\) 表達語料庫中出現的詞 \(word\)，每一行 \(column\) 則表達一份文件 \(document\)。而每個 cell $$m_{ij}$$ 則表示 word _i_ 出現在 document _j_ 的頻率。

* 要注意的是 word 可以是其他語詞單位 \(如 phrase\); document 也可以是其他文段 \(如 paragraph\)

\[2\]. 為了平衡高低頻度可能產生的影響，施用不同的 **weighting scheme**。

\[3\]. 施用 **SVD** \(single value decomposition\) 於這個 weighted matrix， 讓它變成


$$
M_{w} = U\Sigma V^{T}
$$


where $$U$$ is a $$m×r$$ orthogonal matrix, $$V$$ is a $$n×r$$ orthogonal matrix, and $$\Sigma$$ is a $$r×r$$ diagonal matrix..........

SVD 可以使得 LSA 獲得更基本的語意維度。

it finds a reduced dimensional representation of our matrix that emphasizes the strongest relationships and throws away the noise. In other words, it makes the best possible reconstruction of the matrix with the least possible information.

The trick in using SVD is in figuring out how many dimensions or “concepts” to use when approximating the matrix. Too few dimensions and important patterns are left out, too many and noise caused by random word choices will creep back in.

\[4\]. 施用降維計算 \(dimensionality reduction\) 刪除雜訊。

優缺點

* 假定了 Documents are represented as “bags of words”, where the order of the words in a document is not important, only how many times each word appears in a document.無法掌握句法 \(syntax\) 或詞序 \(word order\) 訊息。
* Concepts are represented as patterns of words that usually appear together in documents. For example “leash”, “treat”, and “obey” might usually appear in documents about dog training.
* Words are assumed to have only one meaning. This is clearly not the case \(banks could be river banks or financial banks\) but it makes the problem tractable.
* 似乎提供掌握文本的「主題」或「隱藏語意」。

應用

* 自動回答 TOFEL 的同義詞測驗。（51.5% vs.一般人 52.5%）
* 可用來模擬/預測語言心理現象（如 lexical priming effect）

實際計算例子請見本書「文本相似與關聯計算」章節。

## `word2vec`



`tmcn.word2vec`: R interface to word2vec

