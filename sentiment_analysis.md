# 文本中的情緒分析

* 情緒 \(emotion\) 是類別 \(class\) 的概念。
* 情緒極度 \(sentiment polarity\) 是連續性數值的概念，只是通常也簡化到三大類別 \(負向／中性／正向\)。
* 情緒與語意的關係必須要先想清楚。

---

## 動機

## 情緒的語言表達

* 情緒在各種文本粒度 text granularity （如： SMS messages, chat messages, tweets, product reviews, blog posts, and whole documents 等等）有不同要注意的地方。
* 語言細節常被忽略
  * 在語言處理上， stop word removal 這個步驟會造成重要訊息的忽略。


* 要知道想要偵測的對象：speaker\/writer, reader, 還是  one or more entities mentioned in the utterance. 

## Aspect, entity and their sentiment classification

* 通常做法：訓練語料＋監督式機器學習＋特徵集

## 情緒詞表

* 通常會利用手工或自動化產生的 **word–sentiment \(or valence\) association lexicon**
  * ```
    快樂 - positive
    難過 - negative
    桌子 - neutral
    ```

  * 
  * 






## 進階主題

\(Liu, 2015\)

---

## R 相關套件

* `syuzhet` - Extracts sentiment from text using three different sentiment dictionaries.

