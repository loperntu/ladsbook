---
description: 'tokenization, word segmentation and POS tagging'
---

# 自動分詞與詞類標記

## Tokenization

* 決定文本分析最小【單位】的過程。 
* 中文分詞（斷詞） Chinese word segmentation 可以看成是 tokenization 的一個特例，但是涉及更深一層的語言與認知互動。
  * 中文分詞演算法從早期的 `最大匹配查找`一直到隨著巨量訓練語料庫出現後的各種`統計機器學習模式` \(e.g., Conditional Ramdom Field\) 已經有很大的進展。\(如果不管語言學的討論\)
  * 主要面對的兩大問題是
    * 結構性的歧義消解
    * 新詞識別 

### 中文斷詞（分詞）

[jieba](https://github.com/fxsjy/jieba) 是一個用於中文斷詞的 \(Python\) 套件。[`jiebaR`](https://github.com/qinwf/jiebaR) 則是 jieba 的 R 版本。使用 `jiebaR` 進行斷詞只須兩個步驟：

1. 使用 `worker()` 初始化斷詞設定
2. 使用 `segment()` 將文本斷詞

* `jiebaR::segment()` 回傳一個 character vector，vector 內的每個元素都是一個被斷出來的詞：

```text
library(jiebaR)
seg <- worker()
txt <- "失業的熊讚陪柯文哲看銀翼殺手" 
segment(txt, seg)

#> [1] "失業" "的熊" "讚"   "陪"   "柯文" "哲看" "銀翼" "殺手"
```

* 可以看出 `jiebaR` 的斷詞有時會不太精準，尤其是遇到**專有名詞或是特殊詞彙**時，這些詞彙時常會被錯誤地斷開。若想避免這種情況，可以新增一份自訂辭典 \(儲存在一份純文字檔，每個詞佔一行\)，例如 [`user_dict.txt`](https://rlads2019.github.io/lab/notes/user_dict.txt) 的內容如下：

```text
熊讚
柯文哲
銀翼殺手
```

如此在 `worker()` 中設定自訂辭典，`jiebaR` 就不會將這些詞彙斷開：

```text
seg <- worker(user = "user_dict.txt")
segment(txt, seg)

#> [1] "失業"     "的"       "熊讚"     "陪"       "柯文哲"   "看"      
#> [7] "銀翼殺手"
```



## Stemmatization

* 詞幹 \(stem\)

```r
libray(SnowballC)
```

## 詞類自動標記 POS tagging

* 詞類是句法的概念。在文本解析的重要性上可以用 **named entity recognition** 來解釋。比方說， "the word general can be a job title as in the highest-ranking general, but in the general opinion it is not a job title. In the first example general is a noun, and in the second it is an adjective. If a part-of- speech tagger has already added these annotations, the named entity recognizer can use them to improve its precision."\(Wilcock, 2009\).
* 實作上， English part of speech tagging with`openNLP`\(which implements the Penn Treebank tag set.\) 

  See [http://www.ling.upenn.edu/courses/Fall\_2003/ling001/penn\_treebank\_pos.html](http://www.ling.upenn.edu/courses/Fall_2003/ling001/penn_treebank_pos.html).

```text

```

